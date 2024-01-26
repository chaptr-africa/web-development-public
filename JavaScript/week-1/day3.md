**Title 1: Primitive vs Non-primitive Data Types (Focus on Arrays)**

- **Data Types in JavaScript**
  - JavaScript has two categories of data types: primitive and non-primitive (also known as reference) data types.

- **Primitive Data Types**
  - Primitive data types are immutable and include:
    - Number: Represents numeric values.
    - String: Represents text.
    - Boolean: Represents true or false values.
    - Undefined: Represents an undefined or uninitialized value.
    - Null: Represents the absence of a value.
    - Symbol (ES6): Represents a unique and immutable value.

- **Non-primitive Data Types (Reference Types)**
  - Non-primitive data types are mutable and include:
    - Objects: A collection of key-value pairs.
    - Arrays: A special type of object used to store lists of data.

**Focus on Arrays**:

- **Arrays in JavaScript**
  - Arrays are a type of non-primitive data type that allow you to store collections of data.
  - They are ordered and indexed, starting from zero.
  - Example: `let fruits = ["apple", "banana", "cherry"];`

- **Working with Arrays**
  - You can access, manipulate, and iterate through arrays using various methods and loops.

<hr>
<hr>

---

**Title 2: Loops in JavaScript**

- **Why Use Loops?**
  - Loops are used to repeatedly execute a block of code until a specified condition is met.
  - They are essential for iterating through data structures like arrays.

- **Types of Loops**

  - **`for` Loop**
    - Used when you know how many times you want to execute the code.
    - Example:
      ```javascript
      for (let i = 0; i < 5; i++) {
        console.log("Iteration " + i);
      }
      ```

  - **`while` Loop**
    - Used when the number of iterations is not known in advance.
    - Example:
      ```javascript
      while (true) {
        //do something
      }
      ```

  - **`do...while` Loop**
    - Similar to the `while` loop, but it always executes the code block at least once.
    - Example:
      ```javascript
      let i = 0;
      do {
        console.log("Iteration " + i);
        i++;
      } while (i < 5);
      ```

<hr>
<hr>


**Title 3: Recursion in JavaScript**

- **What is Recursion?**
  - Recursion is a programming technique where a function calls itself to solve a problem.

- **Recursion in JavaScript**
  - JavaScript fully supports recursive functions.

- **Example: Factorial Calculation**
  - A common example of recursion is calculating the factorial of a number:
    ```javascript
    function factorial(n) {
      if (n === 0) {
        return 1;
      } else {
        return n * factorial(n - 1);
      }
    }
    ```

- **When to Use Recursion**
  - Recursion is suitable for solving problems that can be broken down into smaller, similar sub-problems.

- **Pros and Cons**
  - Pros: Elegant, can simplify complex problems.
  - Cons: Inefficient for some tasks, potential for stack overflow errors.

**Key Takeaways**:

- Understand the difference between primitive and non-primitive data types, with a focus on arrays.
- Explore the three types of loops in JavaScript: `for`, `while`, and `do...while`.
- Learn the concept of recursion and its application in solving problems using self-replicating functions.

<hr>
<hr>

**Title 4: Practical Examples**

- **Example 1: Arrays**

  ```javascript
  // Working with arrays
  let fruits = ["apple", "banana", "cherry"];
  console.log(fruits[1]); // Accessing an element
  fruits.push("date");   // Adding an element
  ```

- **Example 2: `for` Loop**

  ```javascript
  // Using a for loop
  for (let i = 0; i < 5; i++) {
    console.log("Iteration " + i);
  }
  ```

- **Example 3: `while` Loop**

  ```javascript
  // Using a while loop
  while (true) {
    //do something
  }
  ```

- **Example 4: Recursion (Factorial)**

  ```javascript
  // Recursive factorial calculation
  function factorial(n) {
    if (n === 0) {
      return 1;
    } else {
      return n * factorial(n - 1);
    }
  }
  ```

**Key Takeaways**:

- Practice is vital for mastering data types, loops, and recursion.
- Experiment with different scenarios and data types to deepen your understanding.
- Loops and recursion are essential tools for solving a wide range of programming problems.

# Challenge: Fibonacci Sequence 

Create a function called fibonacci_sequence that takes in an integer n as its parameter and returns a list of the first n numbers in the Fibonacci sequence.

The Fibonacci sequence is a series of numbers in which each number is the sum of the two preceding ones. The sequence starts with 0 and 1, and each subsequent number is the sum of the previous two.

Example input/output:

```
fibonacci_sequence(5) => [0, 1, 1, 2, 3]
fibonacci_sequence(10) => [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

**Hint:** You can use a recursive function to generate the sequence, and utilize the concept of function scope to keep track of the previous two numbers.
