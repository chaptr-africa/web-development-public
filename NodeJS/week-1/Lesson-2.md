<h1 align="center">Lesson 2</h1>

## PART 1
# Browser vs. Node.js

JavaScript is a popular programming language used in both the browser and server-side applications. However, there are significant differences between how it works in the browser and in Node.js.

### Global Object

In a browser, the global object is `window`, while in Node.js, it is `global`. For example, to log the global object in a browser, we can use:

```jsx
console.log(window);
```

To do the same in Node.js, we use:

```jsx
console.log(global);
```

### Modules

We can import modules in the browser using script tags with the `type` attribute set to `module` and the `src` attribute set to the path of the module file. For example:

```html
<script type="module" src="./module.js"></script>
```

We can then use the exported functions in our JavaScript code. For instance, we can import a `sayHello` function from a module called `module.js` and use it in our main JavaScript file as follows:

```jsx
import { sayHello } from './module.js';
sayHello();
```

On the other hand, in Node.js, we use the `require`  or `import` statement to import modules:

```jsx
const module = require('./module.js');
```

### DOM

The browser has a Document Object Model (DOM) that allows us to interact with HTML elements. For example, to change the text of an HTML element in the browser, we can use:

```jsx
document.getElementById('elementId').innerHTML = 'New text';
```

However, in Node.js, there is no DOM, so we cannot access or manipulate HTML elements.

### Server vs. Website

Node.js is mainly used for server-side applications, while the browser is used for websites. For example, we can create a simple server in Node.js using:

```jsx
const http = require('http');

const server = http.createServer((req, res) => {
  res.write('Hello World!');
  res.end();
});

server.listen(3000);
```

On the other hand, in the browser, we can create a website using HTML, CSS, and JavaScript.

### Console

The `console` object works the same way in both the browser and Node.js. For example, to log a message in the browser, we can use:

```jsx
console.log('Hello World!');
```

Similarly, in Node.js, we can use:

```jsx
console.log('Hello World!');
```

JavaScript is used in both the browser and Node.js, but there are significant differences in how it works in each environment. However, there are also many similarities, and if you already know JavaScript, you should be able to quickly pick up Node.js. Understanding the differences and similarities between the two environments is crucial when developing applications in either of them.

## PART 2
# Non blocking I/O

Node.js is known for its efficient and scalable I/O model, which is based on a non-blocking, event-driven architecture. This means that I/O operations are handled asynchronously and do not block the execution of the main program. In contrast to traditional blocking I/O models, where the program waits for each I/O operation to complete before continuing to the next one, Node.js can execute multiple I/O operations simultaneously.

Here are some key points that explain how Node.js achieves non-blocking I/O:

- **Event Loop**: Node.js uses an event loop to manage I/O operations. The event loop is a loop that listens for events and triggers the corresponding callback functions. When an I/O operation is initiated, Node.js registers the corresponding callback function with the event loop. Once the operation completes, the event loop triggers the callback function, which can then process the result.
- **Callbacks**: Callbacks are functions that are passed as arguments to other functions. In Node.js, callbacks are used to handle the results of I/O operations. When an I/O operation is initiated, a callback function is provided that will be called when the operation completes. By using callbacks, Node.js can execute other code while waiting for I/O operations to complete.
- **Non-Blocking APIs**: Node.js provides a set of non-blocking APIs that allow developers to perform I/O operations asynchronously. For example, the `fs` module provides non-blocking methods for reading and writing files. When these methods are called, Node.js immediately returns control to the program, allowing it to continue executing other code. Once the I/O operation completes, the callback function is called with the result.
- **Single-Threaded**: Node.js is a single-threaded environment, which means that all I/O operations are handled by a single thread. This allows Node.js to handle large numbers of simultaneous connections without consuming a lot of system resources. In contrast, other environments like Python and Ruby use multiple threads to handle I/O operations, which can lead to higher resource consumption and slower performance.

## Example

Blocking code example:

```jsx
const getUserSync = (userId) => {
  const users = {
    1: { name: 'John', age: 35 },
    2: { name: 'Jane', age: 28 }
  };
  return users[userId];
}

const user = getUserSync(1);
console.log(user);
```

In this example, the `getUserSync` function returns a user object from a hardcoded list of users. This function is **blocking**, because it executes synchronously and returns the result immediately.

Non-blocking code example:

```jsx
const getUserAsync = (userId, callback) => {
  const users = {
    1: { name: 'John', age: 35 },
    2: { name: 'Jane', age: 28 }
  };
  setTimeout(() => {
    callback(users[userId]);
  }, 1000);
}

getUserAsync(1, (user) => {
  console.log(user);
});
```

In this example, the `getUserAsync` function returns a user object from a hardcoded list of users, but it executes asynchronously, using the `setTimeout` function to delay the execution of the callback function by 1 second. The `getUserAsync` function takes a callback function as its second argument, which is called with the user object once it has been retrieved.