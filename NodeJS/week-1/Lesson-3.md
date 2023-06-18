

# What is a CLI

A Command-Line Interface (CLI) is a text-based interface that allows users to interact with a computer program or operating system by typing in text commands. A CLI is a powerful tool for developers and system administrators to perform various tasks quickly and efficiently.

Using CLI commands in bash is easy. For example, to list the contents of a directory, you can use the `ls` command. To change directories, you can use the `cd` command. To remove a file, you can use the `rm` command. These commands can also be combined with flags and arguments to perform more specific actions.

Flags are options that modify the behavior of a command. For example, the `-a` flag can be used with the `ls` command to show hidden files. Arguments, on the other hand, are values or inputs that are provided to a command. For example, the `mkdir` command requires an argument that specifies the name of the directory to be created.

Creating a CLI in Node.js is a popular choice for developers. It allows you to create a custom CLI that can be used to perform specific tasks. You can use third-party libraries such as `commander` and `yargs` to create a CLI in Node.js. These libraries provide an easy way to parse arguments and flags and execute commands.

When creating a CLI, you need to decide whether it should be installed globally or locally. A global installation allows the CLI to be used from any directory on your system, while a local installation requires the user to be in the directory where the CLI is installed.

Installing CLIs is easy. You can use the `npm` command to install a CLI from the Node.js package manager. For example, to install the `create-react-app` CLI globally, you can use the following command:

```bash
npm install -g create-react-app
```

# Creating a CLI

## CLI basics

We’re now ready to create the CLI for a note taking app. First thing we’re going to do is create a new Node.js project, we can do this by using the `npm` cli:

```bash
npm init
```

The init command will create a `package.json` file for us on the root of the directory in which we ran the command. Don’t worry about npm and the package.json, we’ll get to those soon enough.

Next, let’s create the file where we’ll write our JavaScript for the CLI. Create a file called `index.js` on the root if you don’t have one already. Here in this file add a for now, just add a `console.log`. We’ll create the logic for allowing a user to add a new note to the app. So we need a few things:

1. A command to use in the terminal
2. The ability for that command to accept arguments and flags
3.  Using the value of that argument to create a new note

Let’s start by creating a command we can use in our terminal. To do that, we have to register a command name in a package.json:

```bash
{
  "name": "note",
  "bin": {
    "note": "./index.js"
  }
}
```

Under the `bin` field, we can use pretty much any name we want. This name will end up being the command we use in the terminal as our CLI, so pick a good name! We’ll just use `note`. Notice we add the file path to that js file we created. That’s telling Node.js that we want to execute that file with the note command is ran. We need to augment that file with some hints for our machine. That’s because our computer might have many OS languages installed, like python or ruby, so it won’t know which one of these should be used to execute our program. We want to use Node.js to execute our js file. So at the top, the very first line of our JS file, we add:

```bash
#!/usr/bin/env node
```

This is a hashbang. A hashbang is a special comment placed at the top of a script that tells the operating system which interpreter to use when running the script. In the context of a Node.js CLI app, the hashbang tells the machine to use Node.js as the interpreter to execute the JS file. 

Next, we need to install this CLI on our machine so we can test it out. We could actually install this globally like it’s a 3rd party module, but instead we’re going to create a symlink.

A symlink, or symbolic link, is a special type of file that acts as a reference to another file or directory. In the context of a Node.js CLI app, creating a symlink allows us to run the CLI from anywhere in our file system, just like a globally installed third-party module. This means that we can run our `note` command from any directory on our machine, without having to navigate to the directory where the CLI code is stored. Creating a symlink is done using the `npm link` command, which creates a symlink from the globally installed npm package to the locally stored code. So run the command:

```bash
npm link
```

We should not be able to run the `note` command in our terminal and see our log output, try it out!

```bash
npm exec note
```

## Note logic

Now that we have a working CLI, let’s start creating the logic for a note taking app! For now, we want to be able to except some input from the terminal as a new note. Later we will figure out what to do with that input, but for now, lets just make sure we can read it. To do so, we can tap into the `process` . So in our index.js file:

```jsx
// index.js
const note = process.argv[2];
const newNote = {
  id: Date.now(),
  note,
}
console.log('your new note', newNote)
```

The above code assumes anything you place after the note command will be the note. It then takes that note and creates a new object and logs it. Simple. So the command would be:

```jsx
npm exec note "this is my note"
```

Notice I put the note in strings so the terminal doesn’t think each word is a new argument, but instead the while string is the argument. 

This is cool, but we need some more features here. We need to be able to save the notes somewhere, we also need some more flexibility on how we create notes. Like adding tags, a name, a status. Being able to list all notes and even removing a note would be useful too. So we’ll need more commands and flags for our CLI. We could parse this ourself, but there are some handy 3rd party modules we can install that will make this easier. What is a module you ask? We’re covering that next!


# What is a module

In Node.js, a module is a self-contained piece of code that performs a specific task. It can be a function, an object, or a piece of functionality that can be used in other parts of your application.

There are three types of modules in Node.js: internal, user-created, and third-party modules from npm.

## Internal Modules

Internal modules are built into Node.js and can be accessed using the require function without any additional installation. For example, the built-in `http` module is used to create a web server:

```jsx
const http = require('http');

http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello World!');
}).listen(8080);

```

In this example, we use the `require()` function to load the `http` module and use it to create a web server that listens on port 8080.

## User-created Modules

User-created modules are modules that you create yourself and can be included in your application using the require function. For example, you can create a module that exports a function that adds two numbers:

```jsx
// math.js

function add(a, b) {
  return a + b;
}

module.exports = add;

```

And then use it in another file:

```jsx
// index.js

const add = require('./math');

console.log(add(2, 3)); // output: 5

```

In this example, we create a module called `math.js` that exports a function called `add`. We then use the `require()` function to load the `add` function from the `math.js` module and use it to add two numbers.

## Third-party Modules

Third-party modules from npm are modules that are created by other developers and can be downloaded from the npm registry using the npm package manager. For example, you can use the `axios` module to make HTTP requests:

```jsx
const axios = require('axios');

axios.get('<https://jsonplaceholder.typicode.com/users>')
  .then(function (response) {
    console.log(response.data);
  })
  .catch(function (error) {
    console.log(error);
  });

```

In this example, we use the `require()` function to load the `axios` module and use it to make an HTTP GET request to the `jsonplaceholder` API.

## Exporting Modules

To export a module from a file, you need to use the `module.exports` or `export` keyword. This allows you to make the module available to other parts of your application. For example, you can create a module that exports an object:

```jsx
// logger.js

const logger = {
  log: function(message) {
    console.log(message);
  }
};

module.exports = logger;

```

And then use it in another file:

```jsx
// index.js

const logger = require('./logger');

logger.log('Hello, world!'); // output: Hello, world!

```

In this example, we create a module called `logger.js` that exports an object with a `log` function. We then use the `require()` function to load the `logger.js` module and use it to log a message.

## Importing Modules

In the latest versions of Node.js, you can also use the `import` statement to import a module. This statement is similar to the `require()` function but has some differences in syntax and behavior. For example, you can import a named export:

```jsx
// math.js

export function add(a, b) {
  return a + b;
}

```

And then use it in another file:

```jsx
// index.js

import { add } from './math';

console.log(add(2, 3)); // output: 5

```

In this example, we create a module called `math.js` that exports a named function called `add`. We then use the `import` statement to load the `add` function from the `math.js` module and use it to add two numbers.

## Conclusion

Modules are an essential part of Node.js development, and understanding how to create, import, and export them is crucial to building efficient and scalable applications.

# Require vs. Import

In Node.js, `require` and `import` are two ways to include external modules in your code. Both of them serve the same purpose, but they have some differences that are worth noting.

## Require

`require` is a built-in function in Node.js that allows you to load external modules. It works synchronously, which means that it blocks the execution of the rest of the code until the module is loaded. Here is an example:

```jsx
const fs = require('fs');
const data = fs.readFileSync('file.txt', 'utf8');
console.log(data);

```

In this example, we are loading the `fs` module, which provides a way to interact with the file system. We then use the `readFileSync` method to read the contents of a file called `file.txt`. Finally, we log the contents to the console.

## Import

`import` is a newer way to include external modules in your code. It is part of the ES6 (ECMAScript 2015) specification, and it works asynchronously. Here is an example:

```jsx
import fs from 'fs/promises';
async function readFile() {
  const data = await fs.readFile('file.txt', 'utf8');
  console.log(data);
}
readFile();

```

In this example, we are using the `import` statement to load the `fs/promises` module, which provides a way to interact with the file system using promises. We then define an `async` function called `readFile`, which uses the `readFile` method to read the contents of a file called `file.txt`. Finally, we log the contents to the console.

## Exporting

In addition to loading external modules, you may also want to export your own code as a module that can be used by other parts of your application. There are several ways to do this, depending on the module system you are using.

### CommonJS

CommonJS is the module system used by Node.js. To export a module in CommonJS, you can use the `module.exports` or `exports` objects. Here is an example:

```jsx
// module.js
function hello(name) {
  console.log(`Hello, ${name}!`);
}
module.exports = { hello };

// app.js
const module = require('./module');
module.hello('world');

```

In this example, we define a function called `hello` in a module called `module.js`. We then export the function using `module.exports`. In `app.js`, we load the module using `require`, and we call the `hello` function.

### ES6 Modules

ES6 modules are a newer module system that is supported by some browsers and by Node.js with the `--experimental-modules` flag. To export a module in ES6, you can use the `export` keyword. Here is an example:

```jsx
// module.js
function hello(name) {
  console.log(`Hello, ${name}!`);
}
export { hello };

// app.js
import { hello } from './module.js';
hello('world');

```

In this example, we define a function called `hello` in a module called `module.js`. We then export the function using the `export` keyword. In `app.js`, we load the module using `import`, and we call the `hello` function.

## Conclusion

In conclusion, `require` and `import` are two ways to load external modules in Node.js. They have some differences in their syntax and behavior, but they both serve the same purpose. Additionally, there are different ways to export your own code as a module, depending on the module system you are using.