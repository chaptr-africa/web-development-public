<h1 align="center">Introduction To React: Lesson 1</h1>

You will be introduced to the basics of React and learn some of the important fundamentals needed to build your first React application. By the end of this lesson you should be able to initialize a React application, understand the folder structure, and be able to create your first React component and pass information to it using props.

> Requirements
- Text Editor (Preffarably VS code)
- NodeJS installed: Version 18.15.0 or above <br>
  <a href="https://nodejs.org/en">Download Link</a>
- Git installed: Version 2.32.0 or above <br>
  <a href="https://git-scm.com/downloads">Download link</a>

<hr>
<br>
<hr>

# What is React?

- React is an open-source JavaScript library for building user interfaces. It was developed by Facebook and released in 2013. React allows developers to create reusable UI components and build interactive and dynamic web applications. Read more about React <a href="https://reactjs.org/docs/getting-started.html">here</a>

<br>

# CLI Tooling (Vite VS CRA)

- There are several ways you can start up a React Application but the most popular ones are <a href="https://vitejs.dev/guide/">Vite</a> and <a href="https://create-react-app.dev/docs/getting-started">CRA</a>.

  - ## Using <a href="https://vitejs.dev/guide/">Vite</a> (Recommended) 
    - Vite is a build tool that aims to provide a faster and leaner development experience for modern web projects.
    - To start a React application with vite, simply type in this command in yout terminal.
  <br>
  <br>

  ```jsx
  //command for creating a new project
  $ npm create vite@latest
  
  //changing directory to the newly created React project
  $ cd <project-name>

  //installing packages and dependancies
  $ npm install

  //starting the development server
  $ npm run dev
  ```

  <br>
  <br>

  - ## Using <a href="https://create-react-app.dev/docs/getting-started">CRA</a>.
    - Create React App is an officially supported way to create single-page React applications. It offers a modern build setup with no configuration.
    - To start a React application with CRA, simply type in this command in yout terminal.

  <br>
  <br>

  ```jsx
  //command for creating a new project
  $ npx create-react-app my-app
  
  //changing directory to the newly created React project
  $ cd my-app

  //starting the development server
  $ npm start
  ```
> **💡** CRA takes a longer time building up the application than Vite. This is because CRA comes with a lot of dependancies and packages that are not needed for a simple React application. Vite on the other hand is a lot faster and easy to configure.

- Folder Structure
  - <a href="https://create-react-app.dev/docs/folder-structure">Read</a>
  - <a href="https://www.youtube.com/watch?v=VcGAxR1Ui3w&list=PL_c9BZzLwBRKFRIBWEWYCnV4Lk9HE3eYJ&index=4">watch video</a>

<hr>
<br>
<hr>

# Introduction to Components

- Components are the building blocks of any React application, and a single app usually consists of multiple components. A component is essentially a piece of the user interface. It splits the user interface into independent, reusable parts that can be processed separately.
- Previously React applications were built using class-based components, but now React has introduced a new way of building components called functional components. Functional components are easier to read and test, and they also perform better than class-based components.
- A functional component in React is simply a JavaScript function that returns JSX. (JavaScript XML)

```jsx

//functional component
const FunctionalComponent = ()=> {
  //component logic here

  return ( //returns JSX elements

    <div>
      {/**Component UI rendered here */}
    </div>

  )
}
```

- Read more about components <a href="https://react.dev/learn/your-first-component">here</a>

## Introduction to JSX

- JSX is a syntax extension to JavaScript. It is similar to a template language, but it has full power of JavaScript. JSX gets compiled to React.createElement() calls which return plain JavaScript objects called “React elements”. JSX is simply HTML/Markdown inside JavaScript! Read more about JSX <a href="https://react.dev/learn/writing-markup-with-jsx">here</a>. JSX comes with various rules and syntaxes that must be followed.
  
>JSX Rules
1. JSX must have one parent element. This means that all the JSX elements must be wrapped in a single parent element.
2. JSX must be written in camelCase. This means that all the HTML attributes must be written in camelCase. For example, class becomes className, and tabindex becomes tabIndex.
3. Make sure to close all the tags. For example, <img> must be written as <img />.

```jsx
//JSX
const FunctionalComponent = ()=>{

  return (
    //JSX codes returned here
    <>
      <h1>Hello World</h1>
    </>
  )
}
```

## Challenge

- Create a new React application using Vite that returns a simple JSX element rendering Hello World in your browser.

> Next Lesson - Styling && Props vs State in React


