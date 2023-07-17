<h1 align="center">Week 3 Lesson 1: Intro To State Management</h1>

- State management in React is a way to store data that can be used throughout the application.
- State is just another fancy word for a JavaScript data structure representing the state with JavaScript primitives and objects. For instance, a simple state could be a JavaScript boolean whereas a more complex UI state could be a JavaScript object.

## useReducer hook

- <code>useReducer</code> is a React Hook that lets you add a reducer to your component.
- A reducer is a function that determines changes to an application’s state. It uses the action it receives to determine this change. <a href="https://react.dev/reference/react/useReducer">Read more</a>
- The idea: A reducer function takes the current state and an action with payload and computes it to a new state.
- <code>useReducer</code> can be used to manage state in a component. It is similar to <code>useState</code> but is more suitable for complex state logic that involves multiple sub-values or when the next state depends on the previous one.

<h2>Managing State using useReducer</h2>

```jsx
//App.jsx
//import the useReducer hook at the top level of your component
import { useReducer } from "react"

//create the reducer
/**
 * @param {object} state - the current state
 * @param {object} action - the action with payload
 */
const reducer = (state, action)=>{
  switch (action.type) {
    case '...':
      return ...
      break;
    default: 
      break;
  }
}
```

- The reducer, which is a function, takes in two parameters, the current state and an action with payload and computes it to a new state. It always returns a new state rather than manipulating the original state.
- After creating the reducer, we can now use it in our component in the same file.

```jsx
//App.jsx
//create the component
const App = ()=>{
  /**
   * @argument {object} reducer - the reducer function
   * @argument {object} initialState - the initial state
   */
  const [state, dispatch] = useDispatch(reducer, initialState)
}

```

- The initial state can be any Data type similar to the <code>useState</code> hook. 
- The <code>dispatch</code> function is used to dispatch an action with payload to the reducer function.
- An action is an object that contains a type and a payload. The type is a string that describes the action and the payload is the data that is passed to the reducer function.
- The initial state will be referenced as <code>state</code> and the reducer function will be referenced as <code>dispatch</code> in the component.
- The dispatch can be created in a handler function which will be executed when the event is triggered.

```jsx
//Example use case.
import { useReducer } from "react"

//NOTE: State is read-only. Don’t modify any objects or arrays in state: instead, return a new object or array that includes the changes you want to make.
const countReducer = (state, action)=>{
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1}
      break;
    case 'decrement':
      return {count: state.count - 1}
      break;
    default:
      break;
  }
}

const App = ()=>{
  const [state, dispatch] = useReducer(countReducer, { count: 0 })

  const increment = ()=>{
    dispatch({type: 'increment'})
  }

  const decrement = ()=>{
    dispatch({type: 'decrement'})
  }
  return (
    <div>
      <h1>Count</h1>
      <p> { count } </p>
      <button onClick={increment}> + </button>
      <button onClick={decrement}> - </button>
    </div>
  )
}

export default App;
```
- The <code>dispatch</code> function takes in an action object as an argument. The action object contains a type and a payload. The type is a string that describes the action and the payload is the data that is passed to the reducer function.
- From the code above we can see that the <code>dispatch</code> function is called when the button is clicked. The <code>dispatch</code> function takes in an action object as an argument. The action object contains a type and a payload. The type is a string that describes the action and the payload is the data that is passed to the reducer function.

- We have so far looked at what state management is in a nutshell and used the useReducer hook as an alternative of using the useContext hook to manage our state, we have a better aproach of state management using the React's in built state management library called Context API.
  
> Next Lesson: Global State Management with Context API 