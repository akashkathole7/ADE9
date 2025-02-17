# RAG Implementation and Storage Design Documentation

## 1. RAG (Retrieval Augmented Generation) Architecture

### 1.1 Overview
RAG combines the power of LLMs with a knowledge base of existing questions to generate contextually appropriate assessment questions. This approach ensures:
- Questions align with proficiency levels
- Technical accuracy
- Consistency with existing question patterns
- Domain-specific relevance

### 1.2 RAG Implementation Components

#### A. Document Processing Pipeline
```python
def process_sample_questions():
    return {
        'technologies': ['Java', 'Python', 'ReactJS', 'Go', 'Angular', 'AWS', 'Data Science', 'AI/ML'],
        'levels': ['beginner', 'intermediate', 'expert'],
        'types': ['mcq', 'coding'],
        'structure': {
            'question_text': str,
            'options': List[str],  # for MCQs
            'correct_answer': str,
            'explanation': str,
            'difficulty_level': str,
            'technology': str,
            'concepts': List[str]
        }
    }
```

#### B. Embedding Generation
```python
from langchain.embeddings import OpenAIEmbeddings
from langchain.text_splitter import RecursiveCharacterTextSplitter

def create_embeddings():
    embeddings = OpenAIEmbeddings()
    text_splitter = RecursiveCharacterTextSplitter(
        chunk_size=1000,
        chunk_overlap=200
    )
    return {
        'chunk_size': 1000,  
        'overlap': 200,    
        'model': 'text-embedding-ada-002'  
    }
```

#### C. RAG Query Pipeline
```python
def rag_pipeline():
    return {
        'steps': [
            '1. Receive generation request with parameters',
            '2. Retrieve similar questions from vector store',
            '3. Build context prompt with retrieved questions',
            '4. Generate new questions using LLM',
            '5. Validate and store new questions'
        ],
        'example_flow': {
            'input': {
                'technology': 'Python',
                'level': 'intermediate',
                'question_type': 'mcq',
                'count': 5
            },
            'retrieval': {
                'similar_questions': 3,
                'similarity_threshold': 0.85
            }
        }
    }
```

## 2. Question Database Sizing

### 2.1 Sample Question Requirements

#### A. Base Requirements per Technology
```python
question_distribution = {
    'per_technology': {
        'beginner': {
            'mcq': 50,
            'coding': 20
        },
        'intermediate': {
            'mcq': 40,
            'coding': 15
        },
        'expert': {
            'mcq': 30,
            'coding': 10
        }
    },
    'total_per_technology': 165  # Sum of all questions
}
```

#### B. Total Initial Dataset Size
```python
total_dataset = {
    'technologies': 8,  # Number of supported technologies
    'questions_per_tech': 165,
    'total_questions': 1320,  # 8 * 165
    'storage_requirements': {
        'question_text': '~2KB',
        'metadata': '~1KB',
        'embeddings': '~8KB',
        'total_per_question': '~11KB',
        'total_storage': '~14MB'  # Initial dataset
    }
}
```

### 2.2 Growth Projections
- Monthly question generation: ~100 per technology
- Annual growth: ~9,600 questions
- 3-year projection: ~30,000 questions

## 3. Storage Solution Architecture

### 3.1 Hybrid Storage Approach

#### A. Vector Store (ChromaDB)
```python
vector_store_config = {
    'primary_use': 'Semantic search and retrieval',
    'data_stored': {
        'question_embeddings': 'Vector representations',
        'metadata': {
            'technology': str,
            'level': str,
            'type': str,
            'concepts': List[str]
        }
    },
    'performance_metrics': {
        'query_time': '<100ms',
        'similarity_threshold': 0.85,
        'max_results': 10
    }
}
```

#### B. PostgreSQL Database
```python
postgres_schema = {
    'tables': {
        'questions': {
            'id': 'UUID PRIMARY KEY',
            'question_text': 'TEXT',
            'options': 'JSONB',  # For MCQs
            'correct_answer': 'TEXT',
            'explanation': 'TEXT',
            'difficulty_level': 'VARCHAR(20)',
            'technology': 'VARCHAR(50)',
            'created_at': 'TIMESTAMP',
            'updated_at': 'TIMESTAMP'
        },
        'question_metadata': {
            'question_id': 'UUID REFERENCES questions(id)',
            'concepts': 'JSONB',
            'usage_stats': 'JSONB',
            'performance_metrics': 'JSONB'
        }
    }
}
```

### 3.2 Caching Layer (Redis)
```python
redis_config = {
    'cache_structure': {
        'recently_generated': {
            'key_pattern': 'gen:{technology}:{level}:{type}',
            'ttl': '24 hours'
        },
        'frequently_used': {
            'key_pattern': 'freq:{question_id}',
            'ttl': '72 hours'
        }
    },
    'max_memory': '2GB',
    'eviction_policy': 'allkeys-lru'
}
```

## 4. Implementation Recommendations

### 4.1 Initial Setup
1. Deploy PostgreSQL for structured data storage
2. Set up ChromaDB for vector storage
3. Implement Redis caching layer
4. Create initial sample question dataset

### 4.2 RAG Implementation Steps
1. Process and embed sample questions
2. Implement retrieval logic with similarity thresholds
3. Create generation pipelines with LLM integration
4. Set up validation and storage workflows

### 4.3 Scaling Considerations
- Implement horizontal scaling for vector store
- Use connection pooling for PostgreSQL
- Set up Redis cluster for distributed caching
- Monitor storage usage and performance metrics

## 5. Performance Optimization

### 5.1 Query Optimization
```python
optimization_strategies = {
    'vector_search': {
        'batch_size': 50,
        'parallel_queries': True,
        'max_concurrent': 5
    },
    'postgres': {
        'index_types': ['B-tree', 'GiST'],
        'partitioning': 'by technology and level'
    },
    'caching': {
        'strategy': 'write-through',
        'invalidation': 'time-based'
    }
}
```

### 5.2 Monitoring Metrics
- Query response time
- Cache hit ratio
- Storage usage
- Question generation latency
