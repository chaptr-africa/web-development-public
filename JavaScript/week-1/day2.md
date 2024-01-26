**Title 1: Control Structures**

- **What are Control Structures?**
  - Control structures are statements that allow you to control the flow of your program. They enable you to make decisions and execute different code blocks based on conditions.

- **`if...else` Statements**
  - The `if...else` statement is used to perform different actions based on a condition.
  - Example:
    ```javascript
    if (condition) {
      // Code to run if the condition is true
    } else {
      // Code to run if the condition is false
    }
    ```

- **`switch...case` Statements**
  - The `switch...case` statement is used for multiple-choice decisions.
  - It provides a cleaner way to handle multiple conditions.
  - Example:
    ```javascript
    switch (value) {
      case option1:
        // Code to run for option1
        break;
      case option2:
        // Code to run for option2
        break;
      default:
        // Code to run if no matches are found
    }
    ```

<hr>
<hr>


**Title 2: Basic Math Operations**

- **Arithmetic Operators**
  - JavaScript supports standard arithmetic operators:
    - Addition (+)
    - Subtraction (-)
    - Multiplication (*)
    - Division (/)
    - Modulus (%) - Calculates the remainder

- **Example: Arithmetic Operations**
  ```javascript
  let x = 5;
  let y = 3;
  let sum = x + y; // Addition
  let difference = x - y; // Subtraction
  let product = x * y; // Multiplication
  let quotient = x / y; // Division
  let remainder = x % y; // Modulus
  ```

<hr>
<hr>


**Title 3: Functions and Scopes**

- **Functions in JavaScript**
  - Functions are blocks of code that can be defined and reused.
  - They encapsulate logic and can accept parameters and return values.
  - Example:
    ```javascript
    function greet(name) {
      return "Hello, " + name + "!";
    }
    let greeting = greet("Alice");
    ```

- **Scopes**
  - JavaScript has two main types of scope:
    1. Global Scope: Variables declared outside functions are in the global scope and can be accessed from anywhere.
    2. Local Scope: Variables declared inside functions are in a local scope and can only be accessed within that function.

- **Scope Example**
  ```javascript
  let globalVar = "I'm global!";

  function myFunction() {
    let localVar = "I'm local!";
    console.log(globalVar); // Accessible
    console.log(localVar);  // Accessible
  }

  myFunction();
  console.log(globalVar); // Accessible
  console.log(localVar);  // Not accessible (generates an error)
  ```

**Key Takeaways**:

- Control structures allow you to make decisions in your code.
- Basic math operations are essential for performing calculations.
- Functions and scopes are fundamental concepts in JavaScript, enabling code organization and data encapsulation.

<hr>
<hr>

**Title 4: Practical Examples**

- **Example 1: Conditional Statement**

  ```javascript
  let age = 20;

  if (age >= 18) {
    console.log("You are an adult.");
  } else {
    console.log("You are a minor.");
  }
  ```

- **Example 2: Arithmetic Operations**

  ```javascript
  let x = 10;
  let y = 4;
  let sum = x + y;
  let product = x * y;
  ```

- **Example 3: Functions and Scopes**

  ```javascript
  let globalVar = "I'm global!";

  function myFunction() {
    let localVar = "I'm local!";
    console.log(globalVar); // Accessible
    console.log(localVar);  // Accessible
  }

  myFunction();
  console.log(globalVar); // Accessible
  console.log(localVar);  // Not accessible (generates an error)
  ```

**Key Takeaways**:

- Practice is crucial for reinforcing your understanding.
- Use these examples as a starting point to experiment and expand your coding skills.
- Understanding control structures, math operations, functions, and scopes is vital for creating complex applications.

<hr>
<hr>

# Challenge: Sum of numbers between 1 and 'n'

Write a program that takes a positive integer n as input and outputs the sum of all numbers between 1 and n that are divisible by 3 or 5 (or both).

For example, if n is 15, the program should output 45, since the numbers between 1 and 15 that are divisible by 3 or 5 are: 3, 5, 6, 9, 10 and 12 and their sum is 45.

Here are some additional requirements and hints:

1. Use a loop to iterate over all the numbers between 1 and n.
2. Use an if statement and the modulus operator (%) to check if a number is divisible by 3 or 5.
3. Use a variable to keep track of the running sum, and update it on each iteration of the loop.
4. You can assume that the input n will be a positive integer.

Good luck!
