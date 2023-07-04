<h1 align="center">Props vs State, Conditional Rendering: Lesson 3</h1>

<hr>
<br>


## Props vs State
- Props (short for “properties”) and state are both plain JavaScript objects. While both hold information that influences the output of component render, they are different in one important way: props get passed to the component (similar to function parameters) whereas state is managed within the component (similar to variables declared within a function).
- Essentially React component props are used to pass data from component to component. State is used to manage data within a single component.
- Read about state <a href="https://react.dev/learn/state-a-components-memory">here</a>
- Read about props <a href="https://www.robinwieruch.de/react-pass-props-to-component/">here</a>
### Rebuilding the Counter App
- Let's rebuild the counter app from the previous lesson using props and state.
- Assuming the App component in the App.jsx file is the parent component, but you needed it to render some other information, you could create a child component to handle the counter functionality. We'll keep the state variables and functions in the parent component and pass them down to the child component as props.
- Start up your <code>Counter Application</code> created from the previous lesson.
- We initially had everything in the App Component, but now we'll create a new component called <code>Counter</code> and move the counter functionality to it.

```jsx
//App.jsx
import { useState } from "react"

//App component (functional component/ParentComponent)
const App = ()=>{

  const [count, setCount] = useState(0)
  
  const handleIncrement = ()=>{
    setCount(count + 1)
  }

  const handleDecrement = ()=>{
    setCount(count - 1)
  }

  return (

    <div>
      {/**Pass the count state variable, handleIncrement and handleDecrement functions as props to the Counter component */}
      <Counter handleIncrement={handleIncrement} handleDecrement={handleDecrement} count={count}/>
    </div>

  )
}

//New Counter component, takes in props as parameter.
const Counter = (props)=>{
  return (
    <div>
      <h1>Counter App</h1>
      {/**Display the count variable */}
      <h2> {props.count} </h2>

      {/**Increment button, takes in handleIncrement as value */}
      <button onClick={props.handleIncrement}> + </button>
      {/**Decrement button, takes in handleDecrement as value */}
      <button onClick={props.handleDecrement}> - </button>
    </div>
  )
}

export default App
```
> Explanation
- In the code above, we've created a new functional Component called Counter, and inserted everything that was being returned in the App component into it. In the App component, we've rendered the Counter component as it's child and passed in the count state variable, handleIncrement and handleDecrement functions as props to the Counter component. The props can be accessed by the Counter component created in the App component as <code>props.count</code>, <code>props.handleIncrement</code> and <code>props.handleDecrement</code> respectively.
- We can also easily destructure the props in the Counter component as shown below:

```jsx
//New Counter component, takes in props as parameter.
const Counter = ({count, handleIncrement, handleDecrement}) =>{
  return (
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
```
- When running the application using <code>npm run dev</code>, the code will work as expected.
- And that's it, we've successfully passed the state variables and functions as props to the Counter component. This concept is commonly referred to as prop drilling, and it's a common pattern in React. It's not a bad pattern, but it can get tedious if you have to pass props through multiple levels of components. This is where React Context comes in handy.
**Note**: Props can only be passed from parent to child components, and not the other way round. If you need to pass data from a child component to a parent component, you'll need to use a callback function. It is also best to separate components into different files to achieve the concept of modularity and separation of concerns. E.g, the Counter component can be created in a separate file called Counter.jsx and imported into the App.jsx file.

<hr>
<br>
<hr>

## Conditional Rendering

- Conditional rendering in React works the same way conditions work in JavaScript. Use JavaScript operators like if or the conditional operator to create elements representing the current state, and let React update the UI to match them.
- Your components will often need to display different things depending on different conditions. In React, you can conditionally render JSX using JavaScript syntax like if statements, &&, and ? : operators.
- In React, we commonly use the <code>&&</code> and <code>ternary operator</code> to conditionally render elements. The && operator works by evaluating the expression to the left of the operator first. If the expression is true, the element to the right of the operator is returned. If the expression is false, the element to the right of the operator is returned.
- Read about conditional rendering <code>here</code>

### Conditional Rendering in React (Implementing conditional rendering with the Counter App)

- Let's implement conditional rendering in the Counter App we created in the previous topic
- We can conditionally render a message when the count is greater than 10, and another message when the count is less than 0. This can be implemented simply using the <code>if(){}else{}</code> logic, but that can bring about an issue called  <i>DRY</i> that we as developers try to avoid, we can easily conditionally render the messages using the <code>ternary operator</code> or the <code>&&</code> operator.

```jsx
//App.jsx

//counter component
const Counter = ({count, handleIncrement, handleDecrement}) =>{
  return (
    <div>
      <h1>Counter App</h1>
      <h2> {count} </h2>
      <button onClick={handleIncrement}> + </button>
      <button onClick={handleDecrement}> - </button>

      {/**Conditional rendering using the ternary operator */}
      {count > 10 ? <h3>Count is greater than 10</h3> : <h3>Count is less than 10</h3>}

      {/**Conditional rendering using the && operator */}
      {count < 0 && <h3>Count is less than 0</h3>}
    </div>
  )
}
```
> Explanation
- In the code above, we've implemented conditional rendering using the ternary operator and the && operator. The ternary operator is used to conditionally render the message <code>Count is greater than 10</code> when the count is greater than 10, and the message <code>Count is less than 10</code> when the count is less than 10. The && operator is used to conditionally render the message <code>Count is less than 0</code> when the count is less than 0.
- With that, we've successfully implemented conditional rendering in the Counter App. When running the application using <code>npm run dev</code>, the code will work as expected.

> Next Lesson - List and Keys, useEffect Hook