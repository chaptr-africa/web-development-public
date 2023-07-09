<h1 align="center">React Router Dom: Lesson 1</h1>

- React is referred to as a Single Page Application <code>SPA</code>. To implement routing in React you need an external library called <code>react-router-dom.</code>.
- In this lesson you will learn how to, install and use the <code>react-router-dom</code> library to implement routing in your React application.
- Installation
  - <a href="https://reactrouter.com">react-router-dom</a> -Website

  ```jsx
  //Install package
    $ npm install react-router-dom
  ```

<h2>Usage</h2>

- By default, your application will only have the home route<code> '/' </code> as the main route. Whatever is fed into the <code>App</code> component will be rendered on the home route.
- To have various paths in your application, you will need to configure the <code>react-router-dom</code> library and define the various paths in your application.
- Initially, if you created the React project with vite, you <code>main.jsx</code> file (the root file) had the following boiler-plate code.

```jsx 
import React from 'react'
import ReactDOM from 'react-dom'
import App from './App.jsx'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
)
```
- This meant that whatever was in you <code>App.jsx</code> file component will be the default render of the application.

<h3>Configuring Routes using React Router</h3>

**NOTE** All this is implemented inside the <code>main.jsx</code> file (the root file).
- We first need to import the required components from the <code>react-router-dom</code> library at the top of the file.
  
```jsx
//main.jsx
//... All other imports appear here

//react-router-dom imports
import { createBrowserRouter, RouterProvider} from "react-router-dom"
```

- We have imported two components from the <code>react-router-dom</code> library.
  - <code>createBrowserRouter</code> - Defines the various paths that will be in our application
  - <code>RouterProvider</code> - Provides the routes defined above to our application

- After that, utilize the imports

```jsx
//main.jsx

//... Imports appear here

const routes = createBrowserRouter([
  {
    path: '/',
    element: <App/>
  },
  {
    path: '/about',
    element: <AboutComponent/>
  }
])
```


- After defining our routes we now have to provide them to our applicaton.
  
```jsx
//main.jsx

//... Imports appear here

const routes = createBrowserRouter([...])

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <RouterProvider router={routes}>
  </React.StrictMode>
)
```

- We have called the RouterProvider from react-router-dom and passed the routes we defined above as a prop to the RouterProvider component.
- From the above code, we have initialized the home page to be the <code>App</code> component, so your application should appear the same as it was initially as <code>App</code> as the home page.
- On the other defined path, assuming you already have a component called the <code>AboutComponent</code> , it will be rendered on the <code>/about</code> path.
- Assuming you application is running on port <code>http://localhost:5173</code>, when you direct the url to <code>http://localhost:5173/about</code>, you should be able to see whatever is being rendered by the about component.
- And that's it, we already have configured routing in our application and defined the two paths that will be in our application. i.e <code>/</code> and <code>/about</code>


<h3>Linking Using the {Link} component from react-router-dom</h3>

- For now we can only navigate to the <code>/about</code> path by typing the url in the browser. We need to have a way of navigating from one page to the other.
- For navigating from one page to the other, we will use the <code>Link</code> component from the <code>react-router-dom</code> library.

- Inside your <code>App.jsx</code> file component, import the <code>Link</code> component from the <code>react-router-dom</code> library. We do not use the normal <code>a</code> tag to navigate between pages in React. We use the <code>Link</code> component from the <code>react-router-dom</code> library. The <code>to</code> property will act as the <code>href</code> attribute in the <code>a</code> tag. The <code>'/about'</code> value should match exactly with what is in you <code>main.jsx</code> file where the paths are defined.

```jsx
//App.jsx

//Link component import
import { Link } from "react-router-dom"

//App functional component
const App = ()=>{
  return (
    <>
      <h1>Home Page</h1>
      {/**Link component to direct to about page */}
      <Link to="/about">About</Link>
    </>
  )
}

export default App
```

- We can also implement the navigation back to our home page from the about page. We will use the same <code>Link</code> component to navigate back to the home page.

```jsx
//AboutComponent.jsx

//link import
import { Link } from "react-router-dom"

const AboutComponent = ()=>{
  return (
    <>
      <h1>About Page</h1>
      {/**Routing link back to home page */}
      <Link to="/">Home</Link>
    </>
  )
}
```

- This will take us back to our home page when the About link is clicked.
  
> Next Lesson: Dynamic Routing, deployment of SPAs.
