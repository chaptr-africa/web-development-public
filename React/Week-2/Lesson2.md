<h1 align="center">Dynamic Routing: Lesson 2</h1>

- Dynamic routing is the ability to pass parameters to the url and use those parameters to render different components based on the parameters passed to the url.
- For example, if we have a url like <code>http://localhost:5173/user/1</code>, we can use the <code>1</code> parameter to render a component that will display the details of the user with the id of <code>1</code>.
- To implement dynamic routing, you first need to define the dynamic route in your React application.

<h2>Defining Dynamic Routes</h2>
- To define a dynamic route, you need to add a <code>param</code> property to the route object.

```jsx
//main.jsx

//...imports

const routes = createBrowserRouter([
  {
    path: '/',
    element: <App/>
  },
  {
    //dynamc route
    path: '/user/:id',
    element: <User/>
  }
])

React.createRoot(...)
```

- The <code>param</code> property is an object that contains the name of the parameter and the type of the parameter. In this case the name of the parameter is <code>id</code> and the type is <code>number</code>. Every time a request is made to that specified url <code>http://localhost:5173/user/...</code> the <code>:id</code> param will be replaced with the given dynamic value, <code>http://localhost:5173/user/1</code>