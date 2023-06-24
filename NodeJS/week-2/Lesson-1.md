<h1 align="center">Week 2: Lesson 1</h1>


<h2>PART 1</h2>

# Async in node

Asynchronous code is an important concept in Node.js. It allows the program to run non-blocking code, which means that other operations can be performed while waiting for a task to complete.

## Callbacks

Callbacks are a traditional way of handling asynchronous code in Node.js. A callback function is passed as an argument to a function that performs an asynchronous operation. When the operation is complete, the callback function is executed.

```jsx
fs.readFile('file.txt', (err, data) => {
  if (err) {
    console.error(err)
    return
  }
  console.log(data)
})

```

In the example above, the `readFile` function reads the contents of `file.txt`. When the file is read, the callback function is executed. If an error occurs during the operation, the error is passed to the callback function as the first argument.

## Promises

Promises provide a cleaner way of handling asynchronous code in Node.js. Promises represent a value that may not be available yet and allow you to chain multiple asynchronous operations together.

```jsx
const fs = require('fs/promises')

fs.readFile('file.txt')
  .then(data => {
    console.log(data)
  })
  .catch(err => {
    console.error(err)
  })

```

In the example above, the `readFile` function returns a promise. When the promise is resolved, the `then` function is executed. If the promise is rejected, the `catch` function is executed.

## Async/Await

Async/await is a newer way of handling asynchronous code in Node.js. It provides a more readable and concise way of writing asynchronous code by using the `async` and `await` keywords.

```jsx
const fs = require('fs/promises')

async function readFile() {
  try {
    const data = await fs.readFile('file.txt')
    console.log(data)
  } catch (err) {
    console.error(err)
  }
}

readFile()

```

In the example above, the `readFile` function is marked as `async`. This allows us to use the `await` keyword to wait for the `readFile` function to complete before executing the next line of code. If an error occurs during the operation, it is caught by the `try/catch` block.

## Error Handling

Error handling is an important part of handling asynchronous code in Node.js. In all of the examples above, error handling is performed using a `try/catch` block or a `catch` function.

It's important to handle errors properly to avoid crashing the application. In addition, it's important to provide meaningful error messages to help with debugging.

<h2>PART 2</h2>

# The FS module

The FS (File System) module is a built-in module in Node.js that provides an API for interacting with the file system. This module allows developers to perform various file operations such as reading, writing, updating, deleting, and renaming files.

One of the most commonly used methods in the FS module is the `fs.readFile()` method, which reads the content of a file asynchronously and returns its content in a callback function. Another popular method is `fs.writeFile()`, which writes data to a file asynchronously.

Other frequently used methods include:

- `fs.mkdir()` to create a new directory
- `fs.readdir()` to read the contents of a directory
- `fs.stat()` to get information about a file
- `fs.unlink()` to delete a file
- `fs.rename()` to rename a file

The FS module also provides synchronous versions of these methods, which can be useful for simple scripts or small applications where performance is not a major concern. However, it's generally recommended to use the asynchronous versions of these methods, as they are non-blocking and allow for better performance in larger applications.

Overall, the FS module is a powerful tool for developers working with Node.js, as it enables them to easily interact with the file system and perform a wide range of file operations.

<h2>Task</h2>

# Using a file as a DB

We’re going to use the fs module and a json file as our DB to store our notes. Create a `db.json` file on the root:

```jsx
{
	"notes": []
}
```

Next, create a `db.js` file in the src directory. Here we will create helper functions to interact with the JSON file.

```jsx
import fs from 'node:fs/promises'

const DB_PATH = new URL('../db.json', import.meta.url).pathname

export const getDB = async () => {
  const db = await fs.readFile(DB_PATH, 'utf-8')
  return JSON.parse(db)
}

export const saveDB = async (db) => {
  await fs.writeFile(DB_PATH, JSON.stringify(db, null, 2))
  return db
}

export const insert = async (data) => {
  const db = await getDB()
  db.notes.push(data)
  await saveDB(db)
  return data 
}
```

First we import the fs module. However, we want to use async/await which works with promises. So instead of using the callback versions of fs methods, node has a promise version of fs methods that we can import instead.

Next we define the path to where the json file is. Then we create 3 functions:

- `getDB`: reads the `db.json` file and parses it into a JavaScript object
- `saveDB`: writes a given JavaScript object into the `db.json` file
- `insert`: takes a JavaScript object representing a note and adds it to the `notes` array in the `db.json` file

We will use these methods in another file to help us work with our notes