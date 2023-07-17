<h1 align="center">Refs and useRef Hook: Lesson 4</h1>

- Refs are a way to access DOM nodes or React elements created in the render method.
- Instead of using `document.getElementById()` or `document.querySelector()`, we can use refs to access DOM nodes.
- Refs can also be used with functional components via the `useRef()` hook.
- Read more about the <code>ref</code> and <code>useRef</code> hook <a href="https://react.dev/learn/referencing-values-with-refs">here</a>.

<h2>Uses of <code>ref</code></h2>

- Refs are used to access DOM nodes or React elements created in the render method.
- Refs can also be used to store mutable values in the ref object.
- Refs can be used to access child components.
- When you want a component to “remember” some information, but you don’t want that information to trigger new renders, you can use a ref. It can act as an alternative of the <code>useState</code> hook but without triggering a re-render when the value changes.

<h2>DOM manipulation with <code>ref</code></h2>

- Import <code>useRef</code> hook from react.
- Create a ref using <code>useRef()</code> hook.
- The <code>useRef</code> hook takes an initial value as an argument and returns a ref object. It has a property called <code>current</code> which is initialized to the initial value passed to <code>useRef</code>.


```jsx
/**
 * @ref -> Ref object returned by useRef hook
 * @initialValue -> Initial value of the ref object
 */
const ref = useRef(initialValue);
```
- Under the hood, the useRef initial value has the current property set to the value passed to the hook. The current property is mutable and can be changed looking something similar to this.
```jsx 
const ref = useRef({
  current: initialValue
})
```
- To access the intialc value, you have to access the current property <code>ref.current</code>.
- The <code>current</code> property of the ref object can be used to access the current value of the ref.
- In vanilla JS, for you to access the DOM properties (HTML Tags), you have to use <code>document.getElementById()</code> or <code>document.querySelector()</code> to access the DOM node. But with refs, you can access the DOM node directly.
- Here's an example of DOM manipulation using the useRef hook.

```jsx
// Import useRef hook from react
import { useRef } from "react"

const App = ()=>{
  // Create a ref using useRef hook
  const boxRef = useRef(null)

  // Function to handle color change
  const handleColorChange = ()=>{
    // Access the DOM node using the ref.current property and setting it's background color to red
    boxRef.current.style.backgroundColor = "red"
  }
  return (
    <div>
      {/**Box referrenced by useRef hook to change it's color */}
      <div className="box w-40 h-40 bg-black"></div>

      {/**Button to handle color change */}       
      <button class="button" onClick={handleColorChange}>Change Color</button>
    </div>
  )
}

export default App;

```
- By this, we have changed the background color of the box to red by referencing the DOM node using the <code>useRef</code> hook.
- This can be translated to the code below in vanilla JS:
```jsx
const boxRef = document.querySelector(".box")
const button = document.querySelector(".button")

const handleColorChange = ()=>{
  boxRef.style.backgroundColor = "red"
}

button.addEventListener("click", handleColorChange)
```

<h2> Remembering state with <code>useRef</code> without trigerring rerender.</h2>

- The <code>useRef</code> hook can be used to store mutable values in the ref object.
- When you want a component to “remember” some information, but you don’t want that information to trigger new renders, you can use a ref.
- The <code>useRef</code> hook can be used as an alternative to the <code>useState</code> hook but without triggering a re-render when the value changes.
- We can rebuild the simple counter app using the <code>useRef</code> hook. The counter app will increment the count value by 1 when the increment button is clicked and decrement the count value by 1 when the decrement button is clicked. This will not trigger a re-render when the count value changes.
  
```jsx
import { useRef } from "react"

const App = ()=>{
  // Create a ref using useRef hook
  const count = useRef(0)

  // Function to handle increment
  const handleIncrement = ()=>{
    //Accessing the current value of the ref and incrementing it by 1
    count.current +=1
  }

  // Function to handle decrement
  const handleDecrement = ()=>{
    //Accessing the current value of the ref and decrementing it by 1
    count.current -=1
  }
  return (
    <div>
      <h1>Counter App</h1>
      {/** Referrencing the count ref valuess */}
      <p> { count } </p>

      <button onClick={handleIncrement}> + </button>
      <button onClick={handleDecrement}> - </button>
    </div>
  )
}
```

- From the code above, we have created a ref using the <code>useRef</code> hook and initialized it to 0. We have also created two functions to handle increment and decrement. The functions access the current value of the ref and increment or decrement it by 1. And that's it. We have created a counter app without triggering a re-render when the count value changes.

> Next Lesson: State Management