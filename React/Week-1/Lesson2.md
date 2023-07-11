<h1 align="center">Styling, State and Events:Lesson 2</h1>

- In this lesson you'll be introduced to a styling pre-processor(Saas) and a utility-first CSS framework (Tailwind CSS). You'll also be introduced to the useState hook and event handling in React by building a simple calculator app.
  - Sass <a href="https://sass-lang.com/guide">documentation.</a>
  - useState Hook <a href="https://reactjs.org/docs/hooks-state.html">documentation.</a>
  - TailwindCSS <a href="https://tailwindcss.com/docs">documentation</a>

<hr>
<br>
<hr>

## Using a pre-processer for styling (Saas)
- A preprocessor is a program that takes one type of data and converts it to another type of data. In the case of Sass, it takes your <code>.scss</code> files and converts them into regular <code>.css</code> files that you can use in your web pages.
- You'll only be familiarized with the basics of Saas in this lesson assuming you are from a background of CSS. You'll be introduced to the concept of variables and nesting. Find SASSs documentation above.
- How to install SASS in your React Application

  ```jsx
  //installing sass
  $ npm install sass
  ```

- After installing sass, you can now create a <code>.scss</code> file in your project and start writing your styles in it. You can also import your <code>.scss</code> file into your <code>.scss</code> file and use it as a regular CSS file.

  ```jsx
  //importing your .scss file into your .js file
  import './styles.scss';
  ```
## Using Tailwind CSS 
- Tailwind CSS is a utility-first CSS framework for rapidly building custom user interfaces. It is a highly customizable, low-level CSS framework that gives you all of the building blocks you need to build bespoke designs without any annoying opinionated styles you have to fight to override.
- To set up Tailwind in a React application created with vite, <a href="https://tailwindcss.com/docs/guides/vite">follow these steps.</a> 
- To set up Tailwind in a React application created with CRA, <a href="https://tailwindcss.com/docs/guides/create-react-app">follow these steps</a>
- After setting up Tailwind, you can now start using it in your project as shown below.
  
```jsx
const Component = ()=>{
  return (
    <div className="w-full h-full bg-gray-700">
      {/* your code here */}
    </div>
  )
}
```

<hr>
<br>
<hr>

# useState Hook

- Hooks in React are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes.
- Hooks are usually called at the top level of a React component.
- The <a href="https://react.dev/reference/react/useState">useState</a> hook that lets you add a state variable to your component.
- useState returns a pair: the current state value and a function that lets you update it. You can call this function from an event handler or somewhere else. It’s similar to this.setState in a class, except it doesn’t merge the old and new state together. It has one argument which is the initial state.

```jsx
//the useState hook- syntax
/** 
 *state -> the current state value/variable
 *setState -> a function that lets you update the state
 *initialState -> the initial state value, can be a string, number, boolean, object, array, etc
*/
const [state, setStateFunction] = useState(initialState);

```

# Event Handling in React

- Handling events with React elements is very similar to handling events on DOM elements. There are some syntactic differences:
  - React events are named using camelCase, rather than lowercase.
  - With JSX you pass a function as the event handler, rather than a string.
- React lets you add event handlers to your JSX. Event handlers are your own functions that will be triggered in response to interactions like clicking, hovering, focusing form inputs, and so on.
- The value of the event handler is a function that gets called when the event is triggered.
- ***Note*** Do not call the event handler function when passing it to the event handler. For example, do not do this: <code>onClick={handleClick()}</code>. Instead, do this: <code>onClick={handleClick}</code>.
- Let's build a simple counter app with the knowledge provided on  useState and event handling in React.

## Simple Counter App
- Create a new React application using CRA or Vite.

```jsx
//using vite (recommended)
$ npm create vite@latest counter-app

$ cd counter-app

$ npm install
```
- Inside the <code>App.jsx</code>, remove the boilerplate code and add the code below.

  
```jsx
//App.jsx

//useState import
import { useState } from "react"

//App component (functional component)
const App = ()=>{

  //useState hook to create a state variable
  /**
   * count -> the state variable
   * setCount -> the function that lets you update the state variable
   * 0 -> the initial state value
   */
  const [count, setCount] = useState(0)
  
  //function to handle incrementing the count
  const handleIncrement = ()=>{
    //setCount function to update the count state variable
    setCount(count + 1)
  }

  //function to handle decrementing the count
  const handleDecrement = ()=>{
    //setCount function to update the count state variable
    setCount(count - 1)
  }

  return (

    //JSX code
    <div>
      <h1>Counter App</h1>
      {/**Display the count variable */}
      <h2> {count} </h2>

      {/**Increment button, takes in handleIncrement as value */}
      <button onClick={handleIncrement}> + </button>
      {/**Decrement button, takes in handleDecrement as value */}
      <button onClick={handleDecrement}> - </button>
    </div>

  )
}

export default App
```

- Run your application and see the result.
  
```jsx
//using vite
$ npm run dev
```
- From the code above:
  - When the <code> + </code> button containing the <code>handleIncrement</code> function is clicked, the count state variable is updated by adding 1 to it. 
  - When the <code> - </code> button containing the <code>handleDecrement</code> function is clicked, the count state variable is updated by subtracting 1 from it.
- And that's it, you've successfully built a simple counter app with React.

> Next Lesson - Props vs State, Conditional Rendering in React.
