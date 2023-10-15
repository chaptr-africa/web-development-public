**Title 1: Objects in JavaScript**

- **What are Objects?**
  - In JavaScript, objects are complex data structures that can store multiple values as key-value pairs.
  - Objects are widely used for organizing and managing data.

- **Object Syntax**
  - Objects are defined using curly braces `{}` and contain one or more key-value pairs.
  - Example:
    ```javascript
    let person = {
      name: "John",
      age: 30,
      isStudent: false
    };
    ```

- **Accessing Object Properties**
  - You can access object properties using dot notation or square brackets.
  - Example:
    ```javascript
    console.log(person.name); // John
    console.log(person["age"]); // 30
    ```

<hr>
<hr>


**Title 2: Object Methods**

- **Object Methods**
  - Object methods are functions that are stored as values in object properties.
  - They allow you to perform actions on the object's data.

- **Defining Object Methods**
  - Example:
    ```javascript
    let person = {
      name: "John",
      age: 30,
      greet: function() {
        console.log("Hello, " + this.name + "!");
      }
    };
    ```

- **Invoking Object Methods**
  - You can call object methods using dot notation.
  - Example:
    ```javascript
    person.greet(); // Hello, John!
    ```

<hr>
<hr>

**Title 3: Array Methods**

- **What are Array Methods?**
  - Array methods are built-in functions that you can use to perform various operations on arrays.

- **Common Array Methods**

  - **`push()` and `pop()`**
    - `push()` adds elements to the end of an array, and `pop()` removes the last element.
    
  - **`shift()` and `unshift()`**
    - `shift()` removes the first element, and `unshift()` adds elements to the beginning of an array.

  - **`concat()`**
    - `concat()` is used to merge two or more arrays.
    
  - **`slice()`**
    - `slice()` extracts a portion of an array into a new array.
    
  - **`forEach()`**
    - `forEach()` iterates over array elements and applies a function to each.

- **Example: Using `forEach()`**

  ```javascript
  let numbers = [1, 2, 3, 4, 5];
  numbers.forEach(function(number) {
    console.log(number * 2);
  });
  ```

**Key Takeaways**:

- Objects are a fundamental data structure in JavaScript, used for storing key-value pairs.
- Object methods are functions that are stored as properties in objects.
- Array methods provide convenient ways to manipulate and work with arrays in JavaScript.

<hr>
<hr>

**Title 4: Practical Examples**

- **Example 1: Working with Objects**

  ```javascript
  // Object methods
  let person = {
    name: "John",
    age: 30,
    greet: function() {
      console.log("Hello, " + this.name + "!");
    }
  };

  person.greet();
  ```

- **Example 2: Array Methods**

  ```javascript
  // Array methods
  let numbers = [1, 2, 3, 4, 5];

  // Using forEach to double each number
  numbers.forEach(function(number) {
    console.log(number * 2);
  });
  ```

- **Example 3: Array Manipulation**

  ```javascript
  // Array manipulation
  let fruits = ["apple", "banana", "cherry"];

  // Adding elements
  fruits.push("date");
  fruits.unshift("kiwi");

  // Removing elements
  fruits.pop();
  fruits.shift();
  ```

**Key Takeaways**:

- Practical examples help solidify your understanding of objects and array methods.
- Experiment with different scenarios to master these concepts.
- Objects and arrays are crucial for data management and manipulation in JavaScript.

<hr>
<hr>

# Challenge: GroupBy

Write a function called groupBy that takes two parameters: an array of objects and a string that represents a property name. The function should group the objects in the array by the value of the specified property, and return an object where each key is the distinct value of the specified property, and the value is an array of objects that have that property value.

For example, if the array of objects is:

```
[
  { name: 'Alice', age: 25, city: 'New York' },
  { name: 'Bob', age: 30, city: 'Chicago' },
  { name: 'Charlie', age: 35, city: 'New York' },
  { name: 'Dave', age: 40, city: 'Chicago' }
]
```
and the property name is `"city"`, the function should return:

```
{
  'New York': [
    { name: 'Alice', age: 25, city: 'New York' },
    { name: 'Charlie', age: 35, city: 'New York' }
  ],
  'Chicago': [
    { name: 'Bob', age: 30, city: 'Chicago' },
    { name: 'Dave', age: 40, city: 'Chicago' }
  ]
}
```
If the property name is "`age`", the function should return:

```
{
  25: [{ name: 'Alice', age: 25, city: 'New York' }],
  30: [{ name: 'Bob', age: 30, city: 'Chicago' }],
  35: [{ name: 'Charlie', age: 35, city: 'New York' }],
  40: [{ name: 'Dave', age: 40, city: 'Chicago' }]
}
```
**Note:** Your solution should be able to handle arrays of any length and objects with any number of properties.
