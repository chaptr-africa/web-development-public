<h1 align="center">Lists and Keys, useEffect, Vercel Deployment</h1>

- In this lesson we will get to learn the concept of lists and keys (Displaying Multiple dynamic data), useEffect (Component Lifecycle), Vercel Deployment (Deploying our React App)

<hr>
<br>
<hr>

# Lists and Keys
- In this section we will learn how to display multiple data dynamically using lists and keys.
- Most data that will be displayed, probably from an API or a JSON object, will be in the form of an array.
- Getting to display this sort of data is a bit different from displaying a single data. You'll need high knowledge of JavaScript ES6 list manipulation methods like <code>map</code>, <code>filter</code>, <code>reduce</code> etc.
- We'll mostly be using the <code>map</code> method to display our data.
- <code>Filtering</code> will mostly be used to perform search functionalities on our data.

## Displaying a list of data
- Using the <code>map</code> method, we can display a list of data.
- Assuming we have a list of data in an array, the list contains objects with the properties <code>language</code> and <code>description</code>. We need to display the values of the properties in our UI.

```jsx

const data = [
  {
    id: 0,
    language: "JavaScript",
    description: "Software Engineering",
  },
  {
    id: 1,
    language: "Python",
    description: "Data Science",
  },
  {
    id: 2,
    language: "Kotlin",
    description: "Android Development",
  }
]
```
- We now need to display the data using the <code>map</code>, creating the <code>divs</code> and <code>h1</code> tags dynamically will be done in the <code>map</code> method.

```jsx
//Component to display Data called DisplayData
const DisplayData = ()=>{
  return (
    <>

    {/**Map function to loop over our rata */}

      {data.map((item)=>{
        return (

          {/**Using the id as the key */}

          <div key={item.id}>

          {/**Accessing the language property */}

            <div>{item.language}</div>

            {/**Accessing the description property */}
            
            <div>{item.description}</div>
          </div>
        )

      })}
    </>
  )
}

export default DisplayData;
```

- One important thing to note is that, when displaying a list of data, you need to provide a unique key to each item in the list. Keys tell React which array item each component corresponds to, so that it can match them up later. This becomes important if your array items can move (e.g. due to sorting), get inserted, or get deleted. A well-chosen key helps React infer what exactly has happened, and make the correct updates to the DOM tree.

- Rather than generating keys on the fly, you should include them in your data:
- The above code will display the values of the language and description properties in our UI.

<h2>Challenge: Create A List of Data, Use the <code>Filter</code> method to display the data conditionally.</h2>

<hr>
<br>
<hr>

# useEffect
- The <code>useEffect</code> hook is used to perform side effects in our React App.
- We can use the <code>useEffect</code> hook to perform side effects like fetching data from an API, updating the DOM, subscribing to an event, etc.
- Fetching Data mainly from APIs (Rest/GraphQL) is crucial concept in Frontend Development, we'll be using the <code>useEffect</code> hook to fetch data from an API.
- The <code>useEffect</code>'s syntax is as follows:
  <code>useEffetc(side-effect, dependancy-array)</code>

- The <code>side-effect</code> is a function that will be executed when the component is mounted, updated or unmounted. 
- This is all dependent on the <code>dependancy-array</code> which is an array of values that the <code>useEffect</code> hook will watch for changes, if any of the values in the array changes, the <code>side-effect</code> function will be executed.


## Fetching Data from an API
- We'll be using the <code>useEffect</code> hook to fetch data from an API.
- We'll use the RickAndMorty API and display the information from the API on our UI.
- The API is <a href="https://rickandmortyapi.com/">here</a>.

```jsx
//RickAndMorty.jsx


//RickAndMorty Component
const RickAndMorty = ()=>{
  //useState hook to store the data from the API (Default is an empty list)
  const [characters, setCharacters] = useState([])

  //Async function to fetch data from the API
  const fetchCharacters = async ()=>{
    const response = await fetch("https://rickandmortyapi.com/api/character")
    const data = await response.json()
    //Sets the data from the API to the characters state
    setCharacters(data.results)
  }

  //useEffect hook to fetch data from the API when the component is mounted
  useEffect (()=>{
    fetchCharacters()
    //Dependancy array is empty, so the useEffect hook will only run once when the component is mounted
  }, [])

  return (

    <div>
      {/**The data is mapped through and information will be displayed on the UI */}
      {characters.map((character)=>{
        <div key={character.id}>
          <div>{character.name}</div>
          <img src={character.image} alt={character.name}/>
        </div>
      })}
    </div>
  )
}

export default RickAndMorty;
```
- **NOTE** The dependancy array is empty, this means that the <code>useEffect</code> hook will only run once when the component is mounted. The execution of the side effect is highly dependent on the dependancy array. When the dependancy array has a state variable, the sideEffect will be executed when the state variable changes.
- With the code sample above, you are able to fetch data from the API and display any information you require from the API on your UI.
- We've also used the same concept we've learnt under lists and keys because we are displaying a list of data from the API.
- We've also used the <code>useState</code> hook to store the data from the API.

## Vercel 
Vercel is a cloud platform for static sites and Serverless Functions. It enables developers to host Jamstack websites and web services that deploy instantly, scale automatically, and requires no supervision, all with no configuration. Vercel is a company behind Next.js, a popular framework for building server-rendered React applications.
Deploying our React App to Vercel is very easy, this will be guided by the TM and the TAs.
- Read about vercel <a href="https://vercel.com/">here</a> and create an account.
