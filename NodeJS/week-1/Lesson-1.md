<h1 align="center">Intro to NodeJS: Lesson 1</h1>

## PART 1
<p>Welcome to this introductory course on Node.js! In this course, you will learn what Node.js is, its history, and how to install it. You will also learn how to create a Command Line Interface (CLI), what are npm and modules, the different types of modules available, how to interact with files, how to download modules using npm, how to write tests with Jest, and how to create an HTTP server, handle requests, and serve a simple website.</p>

<h2>Pre-requisites</h2>

<ul>
  <li>Basic knowledge of HTML, CSS, and JavaScript</li>
  <li>Code Editor -> VSCode</li>
  <li>Install Nodejs and NPM on your machine</li>
  <li>Installation link <a href="https://nodejs.org/en">https://nodejs.org/en</a></li>



# The Story of Node.js

- Introduction to Node.js:

Node.js is a cool tech that lets you run JavaScript code outside of a web browser. Ryan Dahl created it in 2009 and the Node.js community has been keeping it up ever since.

- The Birth of Node.js:

Ryan Dahl was tired of dealing with the limitations of web browsers and the inefficiencies of server-side scripting languages, so he decided to create Node.js. He wanted a way to build scalable network applications that could handle a large number of connections with high throughput.

- The First Release of Node.js:

Node.js was released in 2009. It was based on the V8 JavaScript engine developed by Google for its Chrome web browser. The first version of Node.js included a limited set of core modules, including a HTTP server, a file system module, and a module for working with streams.

- The Rise of Node.js:

Node.js became popular quickly because it could handle a large number of concurrent connections with high throughput. It was also popular because it allowed developers to use JavaScript on the server-side, which was already familiar to many front-end developers. As Node.js gained popularity, the Node.js community grew, and many new modules and frameworks were developed to extend its capabilities.

- Node.js Today:

Node.js is now a mature and stable platform used by many companies to build high-performance network applications. It has a large and active community of developers who continue to develop new modules and frameworks to extend its capabilities. Node.js is often used in combination with other technologies, such as databases, front-end frameworks, and cloud platforms, to build full-stack web applications.

## PART 2
# Hello World

Let’s get started with writing our very first Node.js program. But, what is a Node.js program? Simple, some JavaScript!

```jsx
console.log('hello world')
```

Ok, this is cool, but now what? How do we go about executing this code? We can use the Node CLI for this. In your terminal, run:

```bash
node index.js
```

By use the Node CLI, we can then execute a JavaScript file by using path to that file. That’s it! You’ve created your first JavaScript program. If you did this right, you’ll see hello world in the terminal, which in Node.js, is the console.

# Node REPL

Node.js is a popular open-source server environment built on Chrome's V8 JavaScript engine. One of the most useful tools provided by Node.js is the REPL (Read-Eval-Print-Loop), which allows you to execute JavaScript code interactively in a terminal.

The Node REPL is similar to a command-line interface for JavaScript. It is an interactive environment where you can enter JavaScript code and see the results immediately. It is great for testing out small pieces of code or experimenting with new features.

To start the Node REPL, simply open your terminal and type `node`. This will give you access to the Node REPL prompt where you can start typing your JavaScript code.

Here are some examples of how to use the Node REPL:

```bash
// Basic arithmetic
> 2 + 2
4

// String manipulation
> 'hello, world'.toUpperCase()
'HELLO, WORLD'

// Defining a variable
> var x = 10
undefined
> x
10

// Using a function
> function add(a, b) { return a + b }
undefined
> add(3, 5)
8
```

The Node REPL is a great tool for quickly testing out ideas, debugging code, or experimenting with new features. It can also be useful for prototyping code before integrating it into a larger project.

However, the Node REPL is not a substitute for a proper development environment. It is not designed for writing large or complex code, and it lacks many of the features and tools that are available in a full-fledged IDE or text editor.

Overall, the Node REPL is a useful tool for any JavaScript developer, but it should be used in tandem with a proper development environment to ensure the best results.