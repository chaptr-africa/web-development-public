**Title 1**: Introduction to JavaScript, Variables, and Expressions


**Introduction to JavaScript**

- JavaScript is a versatile and widely-used programming language that plays a central role in web development.
- It allows you to make web pages interactive and dynamic by enabling client-side scripting.
- JavaScript is supported by all major web browsers and is a fundamental technology for both front-end and back-end web development.

**Variables in JavaScript**

- In JavaScript, variables are used to store data, such as numbers, text, or objects, for use in your programs.
- Variables are declared using keywords like `var`, `let`, or `const`, followed by a name (identifier).
- Variables can hold different types of data, including numbers, strings, arrays, objects, and more.

**Expressions in JavaScript**

- Expressions are combinations of values, variables, and operators that can be evaluated to produce a result.
- Examples of expressions include arithmetic operations like addition, subtraction, multiplication, and division.
- Expressions can also involve variables, functions, and complex operations, making them a fundamental part of JavaScript.

**Key Takeaways**

- JavaScript is a crucial language for web development, enabling interactive and dynamic web pages.
- Variables are used to store and manage data in your JavaScript programs.
- Expressions are combinations of values and operations that produce results in JavaScript.

<hr>
<hr>

**Title 2**: Declaring and Using Variables in JavaScript

**Declaring Variables**

- In JavaScript, you can declare variables using the `var`, `let`, or `const` keywords.
- Use `var` for older code, `let` for variables that can be reassigned, and `const` for variables that should remain constant.

**Variable Names (Identifiers)**

- Variable names, also known as identifiers, must follow certain rules:
  - They can contain letters, digits, underscores, or dollar signs.
  - They must begin with a letter, an underscore (_), or a dollar sign ($).
  - They are case-sensitive, meaning "myVariable" and "myvariable" are treated as different variables.

**Assigning Values**

- To assign a value to a variable, use the assignment operator `=`:
  - `let age = 30;`
  - `const pi = 3.14159;`

**Using Variables**

- You can use variables in expressions and statements.
- For example:
  - `let x = 5;`
  - `let y = 3;`
  - `let sum = x + y; // sum is now 8`

**Reassigning Variables**

- Variables declared with `let` can be reassigned:
  - `let count = 10;`
  - `count = 20; // count is now 20`

**Constants**

- Variables declared with `const` cannot be reassigned:
  - `const daysInWeek = 7;`
  - `daysInWeek = 8; // This will result in an error`

**Key Takeaways**

- Use `var`, `let`, or `const` to declare variables in JavaScript.
- Variable names (identifiers) must follow specific rules.
- Variables can store and manipulate data in your JavaScript programs.

<hr>
<hr>

**Title 3**: JavaScript Data Types

**What are Data Types?**

- In programming, data types define the type of data that a variable can hold.
- JavaScript has several data types that allow you to work with different kinds of information.

**Common Data Types**

1. **Number**: Represents numeric values, e.g., `5`, `3.14`.
2. **String**: Represents text, e.g., `"Hello, World"`.
3. **Boolean**: Represents true or false values, e.g., `true`, `false`.
4. **Array**: Represents ordered lists, e.g., `[1, 2, 3]`.
5. **Object**: Represents key-value pairs, e.g., `{ name: "John", age: 30 }`.
6. **Null**: Represents the absence of a value, e.g., `null`.
7. **Undefined**: Represents a variable that has been declared but not assigned a value, e.g., `undefined`.

**Dynamic Typing**

- JavaScript is dynamically typed, meaning a variable's data type can change during runtime.
- For example, a variable can hold a number one moment and a string the next.

**Typeof Operator**

- You can use the `typeof` operator to determine the data type of a variable.
- Example: `typeof "Hello"` returns `"string"`.

**Key Takeaways**

- JavaScript supports various data types, including numbers, strings, booleans, arrays, and objects.
- JavaScript is dynamically typed, allowing variables to change their data type.
- The `typeof` operator helps identify the data type of a variable.

<hr>
<hr>
---

**Title 4**: Running JavaScript on the browser.

**Setting up a Local Development Environment**

- To run JavaScript locally, you need a development environment.
- Here's how to get started:

**1. Code Editor**

- Choose a code editor like Visual Studio Code, Sublime Text, or Atom.
- These editors offer features for writing and debugging JavaScript.

**2. HTML File**

- Create an HTML file and include a `<script>` tag inside it.
- This is where you write your JavaScript code.

**3. Opening the HTML File**

- Open the HTML file in your web browser (e.g., Google Chrome, Firefox).
- The JavaScript code inside the `<script>` tag will run in the browser.

**4. Using the Console**

- You can use the browser's developer console to view and test your JavaScript code.
- Press `F12` or `Ctrl + Shift + I` to open the console.

**External JavaScript Files**

- For larger projects, it's common to use external JavaScript files.
- Link to these files using the `<script>` tag's `src` attribute.

**Node.js for Local JavaScript**

- Node.js is a runtime environment that allows you to run JavaScript on your computer without a browser.
- Install Node.js and use it to run JavaScript scripts directly from the command line.

**Key Takeaways**

- To run JavaScript locally, you need a code editor, an HTML file, and a web browser.
- The browser's developer console is a useful tool for testing and debugging code.
- Node.js is an alternative for running JavaScript outside of the browser.

<hr>
<hr>

**Title 5**: Running JavaScript locally

**Example 1: Hello, World!**

```javascript
// This is a simple "Hello, World!" program in JavaScript.
console.log("Hello, World!");
```

- `console.log()` is used to print messages to the console.
- To run the script locally, you need NodeJS installed, then run this on your terminal
- `node {filename}`

# Challenge: Area and Perimeter of a Rectangle

The program should:

- Prompt the user to enter the length and width of the rectangle.
- Calculate the area and perimeter of the rectangle using the length and width entered by the user.
