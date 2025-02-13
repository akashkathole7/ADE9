# Intermediate Level Assessment Questions

## Java

### Multiple Choice Questions

1. What is the output of the following code involving a lambda expression?
```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
numbers.stream()
    .filter(n -> n % 2 == 0)
    .map(n -> n * 2)
    .forEach(System.out::println);
```
- A) 2 4 6 8 10
- B) 4 8
- C) 2 4
- D) 4 8 12

Correct Answer: B

2. Which statement about the `CompletableFuture` class is incorrect?
- A) It can be explicitly completed using the complete() method
- B) It can chain multiple asynchronous operations
- C) It must always be completed on the same thread that created it
- D) It can handle exceptions using exceptionally() method

Correct Answer: C

3. What happens when using the `synchronized` keyword on a static method?
```java
public class Counter {
    private static int count = 0;
    public static synchronized void increment() {
        count++;
    }
}
```
- A) Locks the instance of the class
- B) Locks the Class object
- C) No locking occurs
- D) Locks both instance and Class object

Correct Answer: B

### Coding Questions

1. Implement a custom ThreadPool with a fixed number of worker threads:
```java
// Requirements:
// - Fixed thread pool size
// - Task queue implementation
// - Ability to submit Runnable tasks
// - Proper shutdown mechanism

// Example Usage:
CustomThreadPool pool = new CustomThreadPool(3);
pool.submit(() -> System.out.println("Task 1"));

// Evaluation Criteria:
// - Thread safety
// - Resource management
// - Proper synchronization
// - Error handling
```

2. Create a caching mechanism using WeakHashMap:
```java
// Requirements:
// - Generic type support
// - Automatic cleanup of unused entries
// - Thread-safe implementation
// - Customizable cache size

// Example Interface:
public interface Cache<K, V> {
    V get(K key);
    void put(K key, V value);
    void remove(K key);
    void clear();
}

// Evaluation Criteria:
// - Proper use of WeakHashMap
// - Concurrency handling
// - Memory leak prevention
// - Performance optimization
```

## Python

### Multiple Choice Questions

1. Consider the following decorator implementation:
```python
def retry(max_attempts):
    def decorator(func):
        def wrapper(*args, **kwargs):
            attempts = 0
            while attempts < max_attempts:
                try:
                    return func(*args, **kwargs)
                except Exception:
                    attempts += 1
            return None
        return wrapper
    return decorator
```
What is the correct way to use this decorator?
- A) @retry
- B) @retry()
- C) @retry(3)
- D) @retry.decorator

Correct Answer: C

2. What is the output of this context manager usage?
```python
class MyContext:
    def __enter__(self):
        print("Enter")
        return self
    def __exit__(self, exc_type, exc_val, exc_tb):
        print("Exit")
        return True

with MyContext():
    print("Inside")
    raise ValueError()
print("Done")
```
- A) Enter Inside Exit
- B) Enter Inside Exit Done
- C) Enter Inside
- D) Enter Inside ValueError

Correct Answer: B

### Coding Questions

1. Implement a custom iterator that generates Fibonacci numbers:
```python
# Requirements:
# - Yield Fibonacci numbers up to n
# - Memory efficient implementation
# - Support for large numbers
# - Iterator protocol implementation

class FibonacciIterator:
    def __init__(self, n):
        # Your implementation here
        pass

# Example Usage:
for num in FibonacciIterator(100):
    print(num)

# Evaluation Criteria:
# - Iterator protocol implementation
# - Memory efficiency
# - Performance optimization
# - Error handling
```

2. Create a decorator for method rate limiting:
```python
# Requirements:
# - Limit method calls within time window
# - Support for multiple concurrent calls
# - Configurable time window and max calls
# - Thread-safe implementation

# Example Usage:
@rate_limit(calls=5, period=60)
def api_call():
    # Make API request
    pass

# Evaluation Criteria:
# - Proper time tracking
# - Thread safety
# - Resource cleanup
# - Error handling
```

## ReactJS

### Multiple Choice Questions

1. What is the output of this useEffect hook?
```jsx
function Example() {
  const [count, setCount] = useState(0);
  useEffect(() => {
    setCount(c => c + 1);
  }, []);
  return <div>{count}</div>;
}
```
- A) 0
- B) 1
- C) Infinite loop
- D) Runtime error

Correct Answer: B

2. Which statement about React's useCallback is correct?
- A) It always returns a new function reference
- B) It memoizes the function between renders
- C) It automatically memoizes all function arguments
- D) It only works with class components

Correct Answer: B

### Coding Questions

1. Implement a custom hook for form validation:
```jsx
// Requirements:
// - Support multiple validation rules
// - Real-time validation
// - Custom error messages
// - Field dependencies

// Example Usage:
const { values, errors, handleChange } = useForm({
  initialValues: { email: '', password: '' },
  validationSchema: {
    email: [required(), email()],
    password: [required(), minLength(8)]
  }
});

// Evaluation Criteria:
// - Hook implementation
// - Performance optimization
// - Error handling
// - Reusability
```

2. Create a virtualized list component:
```jsx
// Requirements:
// - Render only visible items
// - Support dynamic item heights
// - Smooth scrolling
// - Window resize handling

// Example Usage:
<VirtualList
  items={items}
  itemHeight={50}
  windowHeight={400}
  renderItem={(item) => <div>{item.name}</div>}
/>

// Evaluation Criteria:
// - Performance optimization
// - Memory management
// - Scroll handling
// - Resize handling
```

## AWS

### Multiple Choice Questions

1. Which statement about AWS Auto Scaling is correct?
- A) It only works with EC2 instances
- B) It can scale based on custom metrics
- C) It requires manual approval for scaling
- D) It only supports vertical scaling

Correct Answer: B

2. What happens when an SQS message is not processed within the visibility timeout?
- A) It is automatically deleted
- B) It becomes visible again in the queue
- C) It moves to a DLQ
- D) It triggers an SNS notification

Correct Answer: B

### Coding Questions

1. Create a serverless API with DynamoDB integration:
```yaml
# Requirements:
# - CRUD operations
# - Authentication
# - Error handling
# - Performance optimization

# Example serverless.yml:
functions:
  create:
    handler: handler.create
    events:
      - http:
          path: items
          method: post
          authorizer: aws_iam

# Evaluation Criteria:
# - Infrastructure as Code
# - Security best practices
# - Error handling
# - Performance optimization
```

2. Implement a Step Functions workflow:
```json
# Requirements:
# - Multiple state types
# - Error handling
# - Parallel execution
# - Service integration

# Example State Machine:
{
  "StartAt": "ProcessOrder",
  "States": {
    "ProcessOrder": {
      "Type": "Task",
      "Resource": "arn:aws:lambda:function:process-order",
      "Next": "CheckInventory"
    }
  }
}

# Evaluation Criteria:
# - State machine design
# - Error handling
# - Performance optimization
# - Monitoring integration
```

[Sections for Go, Angular, Data Science, and AI/ML follow similar patterns...]

# Guidelines for Intermediate Level Questions

## Question Characteristics
1. Integration of multiple concepts
2. Focus on practical use cases
3. Performance considerations
4. Error handling requirements
5. System design aspects

## MCQ Guidelines
- Test understanding of concept interactions
- Include edge cases
- Focus on best practices
- Cover common pitfalls
- Include practical scenarios

## Coding Question Guidelines
- Real-world problem scenarios
- Multiple implementation approaches
- Performance considerations
- Error handling requirements
- Integration aspects

## Evaluation Criteria
- Code quality and organization
- Performance optimization
- Error handling
- Best practices implementation
- Integration testing
