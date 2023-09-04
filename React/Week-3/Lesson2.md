<h1 align="center">State Management with CONTEXT API: Lesson 3</h1>

- Context API is a React API that allows you to share data between components without having to explicitly pass a prop through every level of the tree. It is a way to share values between components without having to explicitly pass a prop through every level of the tree. In a typical React application, data is passed top-down (parent to child) via props, but this can be cumbersome for certain types of props (e.g. locale preference, UI theme) that are required by many components within an application. Context provides a way to share values like these between components without having to explicitly pass a prop through every level of the tree.
- Read about Context API <a href="https://reactjs.org/docs/context.html">here</a>

<h2>Using the Context API and useContext hook</h2>

- The Context API is made up of two components, the Provider and the Consumer. The Provider component is used to wrap the components that need to access the data. The Consumer component is used to access the data.
- The useContext hook is used to access the data in the Provider component.
- The useContext hook takes in the context object as an argument and returns the value of the context object.

<h3>Best Practice</h3>
- Create a folder called <code>context</code> where all your context files will be stored.

<h2>Building a Dark/Light theme app using CONTEXT API</h2>

```jsx
//context/ThemeContext.jsx
import { createContext } from "react"

//create the context
const ThemeContext = createContext()
```

- The first step is to separate you context in a separate folder, inside the folder we have the file ThemeContext.jsx specifically meant for the theme context.
- After that we create the <code>context</code> or (store) that will hold our application's state. We do this by using the <code>createContext</code> function from the react library.
  
```jsx
//context/ThemeContext.jsx

//Provider function that will wrap your tree with the context and provide the values given in the props.
const ThemeProvider = ({children})=>{
    //use state to create the state
    const [ theme, setTheme ] = useState('light')

    //create a function that will update the state
    const handleThemeChange = ()=>{
        setTeheme(theme === 'light' ? 'dark' : 'light')
    }
    return (
        //return the provider with the value prop that contains the state and the function that will update the state
        <ThemeContext.Provider value={{theme, handleThemeChange}}>
            {children}
        </ThemeContext.Provider>
    )
}

export {
    ThemeProvider,
    ThemeContext
}
```

- The next step is you'll always create the Context Provider that will provide the state to the components that need it. The Provider is a component that takes in a prop called <code>value</code> which is an object that contains the state and the functions that will be used to update the state. It takes in a prop called <code>children</code> which is the components that will be wrapped by the Provider.
- Afterwards, we export the Provider and the Context object so that we can use them in other components.

<h3>Using the Provider and Context created</h3>

- The provider is usually given to the top level component that encapsulates your tree of components. In this case, we'll give it to the <code>main.jsx</code> component.

```jsx
//main.jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App'
// ... other imports
//ThemeProvider is the provider we created
import { ThemeProvider } from "./context/ThemeContext"

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <ThemeProvider>
        <App/>
    </ThemeProvider>
  </React.StrictMode>,
)
```

-After wrapping the <code>App</code> component with the ThemeProvider, this enables us to use the context in the App component and any other component that is a child of the App component.

```jsx
//App.jsx
import { useContext } from "react"
import { ThemeContext } from "./context/ThemeContext"

const App = ()=>{
    const { theme, handleThemeChange } = useContext(ThemeContext)

    const backgroundColor = {
        backgroundColor: theme === 'light' ? 'white' : 'black',
        color: theme === 'light' ? 'black' : 'white' 
    }

    return (
        <main style={backgroundColor}>
            <button onClick={handleThemeChange}>Change Theme</button>

            {/**Other content */}

        </main>
    )
}

export default App
```

- In this case, I provided the ThemeProvider inside the <code>main.jsx</code> file simply because I want the whole application to have access to the theme context. If you want to provide the context to a specific component, you can do so by providing the context in the component that needs it.
- Inside the <code>App.jsx</code> file, I used the <code>useContext</code> hook to access the context. The <code>useContext</code> hook takes in the context object as an argument and returns the value of the context object. That's why we imported the context object from the ThemeContext file.
- On accessing the objects, the items accessed should be the exact same values provided by the provider, I used object destructuring to access the values. (theme and handleThemeChange).
- To determine the background color of the application wrapped inside the <code>main</code> tag in the returned jsx of the App component, I used inline styling using the <code>style</code> attribute of the <code>main</code> tag. The value of the style attribute is an object that contains the styles to be applied to the element. The styles are determined by the value of the theme state. If the theme state is light, the background color will be white and the text color will be black. If the theme state is dark, the background color will be black and the text color will be white.
- Afterwards, there should be a button to change the theme of the application. The button should have an onClick event that calls the handleThemeChange function which changes the theme state to the opposite of what it was before.
- And that's it, you've successfully created a dark/light theme application using the context API.
- Running the application, you should be able to change the theme of the application by clicking the button.

> Next Lesson: 
