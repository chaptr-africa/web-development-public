# Thinking in modules

When developing node.js apps, it's essential to think about modules as separate pieces of functionality that can be easily maintained and reused. By dividing your code into smaller, self-contained modules, you can create more modular, maintainable, reusable, and efficient code.

## What should be a module?

Each module should have a clear and specific purpose, and should not be overly complex or tightly coupled to other modules. This means that you should aim to create modules that are focused on a single task or responsibility, and that can be used in different parts of the app or in different apps altogether.

For example, a module that handles database connections should only be responsible for managing the connection to the database, and should not be responsible for any other tasks, such as data validation or business logic. This allows the module to be reused across different parts of the app or in different apps, without having to modify its code.

On the other hand, a module that handles user authentication should only be responsible for authenticating users, and should not be responsible for any other tasks, such as database access or UI rendering. This allows the module to be easily maintainable, as any changes to the authentication logic can be made without affecting other parts of the app.

## Best export and import patterns

When exporting from a module, use the `export` keyword followed by the name of the function, variable, or class you want to export. You can also use `export default` to export a single value from a module.

When importing a module, use the `import` keyword followed by the name of the module, and then use dot notation to access the exported values. This allows you to selectively import only the functions, variables, or classes that you need from a module, and to avoid polluting the global namespace of your app.

For example:

```
// modules/myModule.js
export function myFunction() {
  // ...
}

export const myVariable = 42;

// app.js
import { myFunction, myVariable } from './modules/myModule.js';

```

## Index.js pattern

It's common to use an `index.js` file inside a folder to export several modules at once. This allows you to group related modules together, and to provide a clean and simple interface for importing them.

For example, suppose you have two modules, `myModule1` and `myModule2`, that you want to export from a folder called `modules`. You can create an `index.js` file inside the `modules` folder that exports both modules:

```jsx
// modules/myModule1.js
export function myFunction1() {
  // ...
}

// modules/myModule2.js
export function myFunction2() {
  // ...
}

// modules/index.js
export { myFunction1 } from './myModule1.js';
export { myFunction2 } from './myModule2.js';

// app.js
import { myFunction1, myFunction2 } from './modules';

```

By using the `index.js` pattern, you can simplify your import statements and make your code more readable.

In conclusion, thinking in modules is a fundamental concept in node.js development that can help you create more modular, maintainable, and reusable code. By following these guidelines, you can write code that is easier to understand, easier to modify, and easier to scale.

# Internal Modules

Internal modules in Node.js refer to built-in modules that are available within the Node.js environment. These modules are part of the Node.js core and provide a range of functionalities and utilities that can be used in your application without the need to install any external packages.

There are several internal modules available in Node.js, including but not limited to:

- **fs**: used for file system operations
- **http**: used for creating HTTP servers and clients
- **path**: used for working with file paths
- **os**: used for retrieving operating system-related information
- **crypto**: used for cryptographic operations

To use these modules in your Node.js application, you need to import them using the `require()` function. For example, to use the `fs` module to read a file in your application, you would write:

```jsx
const fs = require('fs');
fs.readFile('file.txt', (err, data) => {
  if (err) throw err;
  console.log(data);
});
```

Starting from Node.js version 13, you can also use ES6 module syntax to import internal modules. 

```jsx
import fs from 'fs';
```

With Node.js V18, you can be explicit about importing core, internal modules like so:

```jsx
import fs from 'node:fs'
```

Using the `node:` prefix doesn’t change the behavior of the import, it’s just a way to be explicit about this module being a core module and not a 3rd party one.

In summary, internal modules in Node.js are built-in modules that provide a range of functionalities and utilities. You can import them using either the `require()` function or ES6 module syntax, depending on your Node.js version and the type of module you want to import.

# Using yargs

We’re now going to install and use a 3rd party module to help us create our Note taking app. Its called `yargs`.

```json
npm i yargs
```

Once you install it, create a src folder with a commands.js file and let’s add some commands.

```jsx
import yargs from 'yargs'
import { hideBin } from 'yargs/helpers'

yargs(hideBin(process.argv))
  .command('new <note>', 'create a new note', yargs => {
    return yargs.positional('note', {
      describe: 'The content of the note you want to create',
      type: 'string'
    })
  }, async (argv) => {
    
  })
  .option('tags', {
    alias: 't',
    type: 'string',
    description: 'tags to add to the note'
  })
  .command('all', 'get all notes', () => {}, async (argv) => {
    
  })
  .command('find <filter>', 'get matching notes', yargs => {
    return yargs.positional('filter', {
      describe: 'The search term to filter notes by, will be applied to note.content',
      type: 'string'
    })
  }, async (argv) => {
    
  })
  .command('remove <id>', 'remove a note by id', yargs => {
    return yargs.positional('id', {
      type: 'number',
      description: 'The id of the note you want to remove'
    })
  }, async (argv) => {
    
  })
  .command('web [port]', 'launch website to see notes', yargs => {
    return yargs
      .positional('port', {
        describe: 'port to bind on',
        default: 5000,
        type: 'number'
      })
  }, async (argv) => {
    
  })
  .command('clean', 'remove all notes', () => {}, async (argv) => {
    
  })
  .demandCommand(1)
  .parse()
```

We’re using yargs to setup different commands we can use from our cli, for example, the new command can be used like:

```jsx
note new "this is my new note"
```

Right now, the function for each command is blank, we need to make them actually do something next.