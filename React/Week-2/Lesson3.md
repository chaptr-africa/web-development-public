<h1 align="center"> Custom Hooks: Lesson 3</h1>

- In React, a hook is a function that allows you to use React features in a functional component. Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.
- You can create your own custom hooks to reuse stateful behavior between different components. Custom hooks are more of a convention than a feature. If a function’s name starts with ”use” and it calls other hooks, we say it is a custom hook.

<h3>Best Practices</h3>

- Custom hooks should always start with the word <code>use</code> and should be written in camelCase.
- Custom hooks should be written as functions and not classes.
- Custom hooks should be written in a separate file and not in the same file as the component that is using the custom hook.
- Create a folder called <code>hooks</code> in the <code>src</code> folder to store your custom hooks.
  
<h3>Creating a custom hook</h3>

- We will create a custom hook that will fetch data from an API and return the data to the component that is using the custom hook.
- Create a file called <code>useFetch.jsx</code> in the <code>hooks</code> folder.
- In the <code>useFetch.jsx</code> file, we will create a function called <code>useFetch</code> that will take in a url as a parameter and return the data fetched from the url as a side effect when the component utilizing it is rendered.
- The <code>useFetch</code> function will use the <code>useEffect</code> hook to fetch the data from the url.
- The <code>useFetch</code> function will return the data fetched from the url.

```jsx
//useFetch.jsx

//react imports
import { useState, useEffect } from "react"

//useFetch custom hook function created, takes in url to be fetched as parameter
const useFetch = (url)=>{
  //state to store data fetched from url
  const [data, setData] = useState([])
  //state to store loading status
  const [loading, setLoading] = useState(true)


  //function to fetch data from url
  const fetchData = async ()=>{
    const response = await fetch(url)
    const data = await response.json()
    setData(data)
  } 
  
  //useEffect hook to fetch data from url 
  useEffect(()=>{
    fetchData()
    setLoading(false)

  }, [])
  //the useFetch function return an object that contains the data and loading state
  return { data, loading }
}

export default useFetch
```
  
- After that, we have a custom hook called <code>useFetch</code> that we can use in any component to fetch data from an API. It will only require the url of the API as an argument.
- We can now use the useFetch hook in any component to fetch data from an API.
- Example:
  
```jsx
//UserList.jsx

//...other imports
import useFetch from "../hooks/useFetch"

//UserList Component
const UserList = ()=>{
  //useFetch hook used to fetch users from api
  const { data, loading } = useFetch("https://jsonplaceholder.typicode.com/users")
  //if loading is true, display loading message
  if(loading){
    return <h1>Loading...</h1>
  }
  //if loading is false, display users
  return (
    <div>
      {
        users.map((user)=>{
          return (
            <div key={user.id}>
              <h1>{user.name}</h1>
              <h2>{user.email}</h2>
            </div>
          )
        })
      }
    </div>
  )
}

export default UserList
```

- In the example above, we used the <code>useFetch</code> hook to fetch users from an API. The <code>useFetch</code> hook returns an object that contains the data and loading state. We then used the data and loading state to display the users or a loading message depending on the loading state.
- And that's it! We have created a custom hook that we can use to fetch data from an API in any component.

> Next Lesson: Refs and useRef hook