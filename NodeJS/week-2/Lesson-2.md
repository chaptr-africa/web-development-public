<h1 align="center"></h1>

# Note CRUD

CRUD stands for Create, Read, Update, and Delete. In the context of a JSON file being a database with notes in it, CRUD operations refer to the basic functions that can be performed on the notes in the database.

- **Create**: This operation involves adding a new note to the database. It can be done by providing the necessary information about the note, such as its title, content, and any relevant tags.
- **Read**: This operation involves retrieving an existing note from the database. It can be done by searching for the note by its title, content, or tags.
- **Update**: This operation involves modifying an existing note in the database. It can be done by changing the values of the note's attributes, such as its title, content, or tags.
- **Delete**: This operation involves removing an existing note from the database. It can be done by searching for the note by its title, content, or tags, and then deleting it.

By using these CRUD operations, users can easily manage their notes in the JSON file database.

Let’s create a file for these crud methods. In src, create notes.js:

```jsx
import { insert, getDB, saveDB } from './db.js'

export const newNote = async (note, tags) => {
  const data = {
    tags,
    content: note,
    id: Date.now(),
  }
  await insert(data)
  return data
}
export const getAllNotes = async () => {
  const db = await getDB()
  return db.notes
}

export const findNotes = async (filter) => {
  const notes = await getAllNotes()
  return notes.filter(note => note.content.toLowerCase().includes(filter.toLowerCase()))
}

export const removeNote = async (id) => {
  const notes = await getAllNotes()
  const match = notes.find(note => note.id === id)

  if (match) {
    const newNotes = notes.filter(note => note.id !== id)
    await saveDB({notes: newNotes})
    return id
  }
}

export const removeAllNotes = async () => {
  await saveDB({notes: []})
}
```

Now, we can use the db helper functions we created.  We then created. few functions to help us work with notes better:

The `newNote` function creates a new note with the provided content and tags and inserts it into the database using the `insert` function from `db.js`. It returns the newly created note.

The `getAllNotes` function retrieves all notes from the database using the `getDB` function from `db.js`. It returns an array of all notes.

The `findNotes` function retrieves all notes from the database and filters them based on the provided filter string. It returns an array of notes that contain the filter string in their content, regardless of case.

The `removeNote` function removes the note with the provided ID from the database. It retrieves all notes from the database, finds the note with the provided ID, removes it from the array, and saves the updated array back to the database using the `saveDB` function from `db.js`. It returns the ID of the removed note.

The `removeAllNotes` function removes all notes from the database. It saves an empty array of notes back to the database using the `saveDB` function from `db.js`.