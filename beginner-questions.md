# Beginner Level Assessment Questions

## Java

### Multiple Choice Questions

1. What is the correct way to declare a variable of type integer in Java?
- A) int x;
- B) integer x;
- C) Int x;
- D) Number x;

Correct Answer: A

2. Which statement is used to print "Hello World" to the console?
- A) Console.println("Hello World");
- B) System.out.println("Hello World");
- C) print("Hello World");
- D) echo("Hello World");

Correct Answer: B

3. What is the output of this code?
```java
int x = 5;
if(x > 3) {
    System.out.println("Higher");
} else {
    System.out.println("Lower");
}
```
- A) Higher
- B) Lower
- C) 5
- D) Error

Correct Answer: A

### Coding Questions

1. Write a program to check if a number is even or odd:
```java
// Input: An integer number
// Output: Print "Even" if the number is even, "Odd" if the number is odd

// Evaluation Criteria:
// - Use of modulo operator
// - Proper if-else statement
// - Correct output format
```

2. Create a program that finds the largest of three numbers:
```java
// Input: Three integers
// Output: The largest number

// Evaluation Criteria:
// - Use of comparison operators
// - Proper if-else statements
// - Handle equal numbers correctly
```

## Python

### Multiple Choice Questions

1. What is the correct way to create a list in Python?
- A) list = [1, 2, 3]
- B) list = (1, 2, 3)
- C) list = {1, 2, 3}
- D) list = <1, 2, 3>

Correct Answer: A

2. How do you create a comment in Python?
- A) // This is a comment
- B) /* This is a comment */
- C) # This is a comment
- D) -- This is a comment

Correct Answer: C

3. What is the output of this code?
```python
x = 5
print(type(x))
```
- A) integer
- B) <class 'int'>
- C) int
- D) number

Correct Answer: B

### Coding Questions

1. Write a program to calculate the sum of numbers from 1 to n:
```python
# Input: A positive integer n
# Output: Sum of numbers from 1 to n

# Evaluation Criteria:
# - Use of loop or range function
# - Handle positive integers only
# - Print the final sum
```

2. Create a program that converts temperature from Celsius to Fahrenheit:
```python
# Input: Temperature in Celsius (float)
# Output: Temperature in Fahrenheit (float)
# Formula: (C × 9/5) + 32

# Evaluation Criteria:
# - Correct formula implementation
# - Proper float handling
# - Formatted output to 2 decimal places
```

## ReactJS

### Multiple Choice Questions

1. What is the correct way to create a functional component in React?
- A) function MyComponent() { return <div>Hello</div>; }
- B) class MyComponent { render() { return <div>Hello</div>; } }
- C) const MyComponent = <div>Hello</div>;
- D) new Component(<div>Hello</div>);

Correct Answer: A

2. Which hook is used to manage state in a functional component?
- A) useStatus
- B) useState
- C) stateHook
- D) handleState

Correct Answer: B

3. What is the correct way to render a component?
```jsx
function Welcome() {
  return <h1>Hello</h1>;
}
```
- A) <Welcome>
- B) <Welcome/>
- C) Welcome()
- D) render(Welcome)

Correct Answer: B

### Coding Questions

1. Create a simple button component that changes its text when clicked:
```jsx
// Requirements:
// - Button should initially display "Click me"
// - When clicked, should display "Clicked!"
// - Use useState hook

// Evaluation Criteria:
// - Proper use of useState
// - Correct event handling
// - Proper JSX syntax
```

2. Create a component that displays a list of names:
```jsx
// Input: Array of names ["John", "Jane", "Bob"]
// Output: Unordered list of names

// Evaluation Criteria:
// - Use of map function
// - Proper key assignment
// - Correct list rendering
```

## Go

### Multiple Choice Questions

1. What is the correct way to declare a variable in Go?
- A) var x int = 5
- B) int x = 5
- C) x := 5
- D) Both A and C

Correct Answer: D

2. How do you print to the console in Go?
- A) console.log("Hello")
- B) print("Hello")
- C) fmt.Println("Hello")
- D) System.out.println("Hello")

Correct Answer: C

3. What is the zero value for an integer in Go?
- A) null
- B) undefined
- C) 0
- D) nil

Correct Answer: C

### Coding Questions

1. Write a program to find the factorial of a number:
```go
// Input: Positive integer n
// Output: Factorial of n

// Evaluation Criteria:
// - Use of loop
// - Error handling for negative numbers
// - Proper variable declarations
```

2. Create a program that reverses a string:
```go
// Input: String
// Output: Reversed string

// Evaluation Criteria:
// - String manipulation
// - Use of for loop
// - Handle empty string case
```

## AWS

### Multiple Choice Questions

1. What is Amazon S3?
- A) A database service
- B) An object storage service
- C) A compute service
- D) A networking service

Correct Answer: B

2. Which AWS service is used to run containers?
- A) EC2
- B) S3
- C) ECS
- D) RDS

Correct Answer: C

3. What is the default time limit for an AWS Lambda function?
- A) 1 minute
- B) 3 minutes
- C) 5 minutes
- D) 15 minutes

Correct Answer: D

### Coding Questions

1. Write an AWS Lambda function that responds to an HTTP GET request:
```python
# Requirements:
# - Return "Hello, World!"
# - Include proper status code
# - Handle basic errors

# Evaluation Criteria:
# - Correct handler function
# - Proper response format
# - Basic error handling
```

2. Create an S3 bucket using AWS CLI commands:
```bash
# Requirements:
# - Create bucket with specific name
# - Set basic permissions
# - Enable versioning

# Evaluation Criteria:
# - Correct CLI syntax
# - Proper command sequence
# - Basic configuration settings
```

[Sections for Angular, Data Science, and AI/ML follow the same pattern...]

# Guidelines for Beginner Level Questions

## Question Characteristics
1. Focus on fundamental concepts
2. Use simple, clear language
3. Test single concepts rather than combinations
4. Include basic examples
5. Avoid complex terminology

## MCQ Guidelines
- Questions should be direct and unambiguous
- Include at least one clearly incorrect option
- Avoid "trick" questions
- Use simple code snippets when needed
- Focus on core concepts

## Coding Question Guidelines
- Clear problem statements
- Simple, specific requirements
- Basic input/output examples
- Fundamental programming concepts
- Limited scope and complexity

## Evaluation Criteria
- Basic syntax understanding
- Fundamental concept application
- Simple problem-solving skills
- Basic error handling
- Code readability
