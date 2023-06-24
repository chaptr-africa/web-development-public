<h1 align="center">Lesson 3</h1>

# What is a server

In the context of node.js, a server is a program that listens for incoming network requests and responds to those requests by executing code or returning data. Servers are fundamental to the architecture of web applications and enable communication between clients (such as mobile apps or websites) and databases or other backend services.

Here is an example of a simple server written in node.js that listens on port 3000 and responds to all incoming requests with "Hello, World!":

```jsx
const http = require('http');

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, World!');
});

server.listen(3000, () => {
  console.log('Server running on port 3000');
});

```

One key difference between a server and a client app like a mobile app or website is that the server is responsible for managing data and state, while the client is responsible for presenting that data to the user. The server runs continuously and is always available to respond to requests, while the client is only active when the user is interacting with it.

Another key difference is that the server typically runs on a different machine than the client app. This allows the server to handle heavy computational tasks and manage data storage and retrieval, while the client app can focus on providing a smooth user experience.

Overall, servers are a critical component of modern web applications and provide the backbone for communication between clients and backend services.

<h2>PART 2</h2>

# Vanilla server

For the web command, we want to create a website that shows all our notes and serves it so we can view it in our browser.

Create an html file called `template.html` in the src folder.

Then install a package called `open`

```jsx
npm i open
```

This will allow our CLI to open a browser for us.

Next, create a server.js in the src folder:

```jsx
import fs from 'node:fs/promises'
import http from 'node:http'
import open from 'open'

const interpolate = (html, data) => {
  return html.replace(/\{\{\s*(\w+)\s*\}\}/g, (match, placeholder) => {
    return data[placeholder] || '';
  });
}

const formatNotes = (notes) => {
  return notes.map(note => {
    return `
      <div class="note">
        <p>${note.content}</p>
        <div class="tags">
          ${note.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
        </div>
      </div>
    `
  }).join('\n')
}

const createServer = (notes) => {
  return http.createServer(async (req, res) => {
    const HTML_PATH = new URL('./template.html', import.meta.url).pathname
    const template = await fs.readFile(HTML_PATH, 'utf-8')
    const html = interpolate(template, {notes: formatNotes(notes)})
    
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.end(html);
  });
}

export const start = (notes, port) => {
  const server = createServer(notes)
  server.listen(port, () => {
    console.log(`Server is listening on port ${port}`);
  });
  open(`http://localhost:${port}`)
}
```

The code above is a JavaScript file that creates a server using the Node.js `http` module. The server takes an array of notes, formats them into HTML, and serves the HTML to the client.

The `interpolate` function is a helper function that takes an HTML string and a data object, and replaces all instances of `{{placeholder}}` in the HTML with the corresponding value in the data object.

The `formatNotes` function takes an array of notes and formats them into HTML div elements with content and tags.

The `createServer` function takes an array of notes and returns a Node.js `http` server that serves the formatted HTML to the client. It reads in an HTML template file, replaces placeholders with the formatted notes, and sends the HTML as a response to the client's request.
Finally, the `start` function takes an array of notes and a port number, creates a server, starts listening to the port, and opens the website in the browser using the `open` package.

We can now use this module as a command in our web command. So go back and update that:

```jsx
.command('web [port]', 'launch website to see notes', yargs => {
    return yargs
      .positional('port', {
        describe: 'port to bind on',
        default: 5000,
        type: 'number'
      })
  }, async (argv) => {
    const notes = await getAllNotes()
    start(notes, argv.port)
  })

```