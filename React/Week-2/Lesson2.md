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
  
<h2>Accessing Dynamic Route Parameters</h2>
- To access the dynamic route parameters, you need to use the <code>useParams()</code> hook from <code>react-router-dom</code>.

```jsx
//User.jsx
import { useParams } from "react-router-dom"

const User =()=>{
  const { id } = useParams()

  return (
    <div>
      <h1>Showing User { id }</h1>
    </div>
  )
}
export default User
```

- From the code above, we are in the <code>User.jsx</code> file component, and we are using the <code>useParams()</code> hook to get the dynamic route parameters. The <code>useParams()</code> hook returns an object that contains the dynamic route parameters. In this case, the object returned will contain the <code>id</code> property which will have the value of the dynamic route parameter.

<h2>Linking Dynamic Paths from data</h2>

- You might be wondering how you can be able to access the dynamic path that is just defined.
- Assuming we have data consumed from an API, and we have a details page that is supposed to show each and every item in the data, how can we be able to link to the details page of each item in the data?
- The <code>Link to={} state={}>Link</code> component takes in an additional <code>state</code> property that can be used to pass data to the component that is being linked to.
- We will create a random component that will fetch users/(API of your choice), and display the users in a list. Each user will have a link that will link to the details page of the user.

```jsx
//UserList.jsx

//...other imports
import { Link } from "react-router-dom"

//UserList Component
const UserList = ()=>{
  //state to store users fetched from Api
  const [users, setUsers] = useState([])

  //function to fetch users from api
  const fetchUsers = ()=>{...}

  //useEffect to fetch users from api
  useEffect(()=>{
    fetchUsers()
  }, [])
  return (
    <div>
      {
        users.map(( user )=>{
          return (
            <div key={user.id}>
              {/** Link component to direct to dynamic path and pass in state */}
              <Link to={`/users/${user.id}`} state={user}>View User</Link>
            </div>
          )
        })
      }
    </div>
  )
}

export default UserList
```
- The <code>Link</code> component when clicked will redirect use to the <code>http://localhost:5173/users/{id}</code>, note that the id will be dynamic depending on the specific user that is clicked. Since we linked the <code>User</code> component to the specified url that is dynamic, we can now access the data that is passed to the <code>state</code> property of the <code>Link</code> component. We will use the <code>useLocation()</code> hook to access the data passed to the <code>state</code> property.

```jsx
//User.jsx
//.. other previous imports
import { useLocation } from "react-router-dom"

const User = ()=>{
  const user = useLocation().state
  return (
    <div>
      <h1>Showing User { user.id }</h1>
    </div>
  )
}
```
- When the component is rendered, it will display the text with the id being dynamic representing the id of the specific user clicked on the <code>UserList</code> component.
- And that's it, We have successfully implemented dynamic routing in our React application and passed dynamic data to the component that is being linked to.

<h2>Deployment of SPAs</h2>
- One major issue you'll face when deploying a Single Page Application with multiple path to your desired hosting service, (Vercel/Netlify) is when you refresh the page, you'll get a 404 error. This is because the hosting service is trying to find the path you are trying to access on the server, but the path is not found on the server, it is found on the client side.
- To fix this error, simply create a <code>vercel.json</code> file (If your site is deployed to vercel) and insert these settings.
  
```json
{
    "routes": [{ "src": "/[^.]+", "dest": "/", "status": 200 }]
}
```
- The <code>vercel.json</code> file will tell the hosting service to redirect all requests to the <code>index.html</code> file, which is the entry point of the React application. And that's it, your application will be error free.

> Next Lesson: Custom Hooks