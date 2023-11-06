# Creating and removing elements dynamically.

> How to create HTML elements using JavaScript

```javascript
const div = document.createElement('div');
div.classList.add('wrapper');
div.textContent = 'Hello World';

const body = document.querySelector('body');
body.appendChild(div);
```

> How to remove HTML elements using JavaScript

```javascript
const body = document.querySelector('body');
const div = document.querySelector('.wrapper');
body.removeChild(div);
```

> How to add elements to the DOM using innerHTML

```javascript
const body = document.querySelector('body');
const div = document.createElement('div');
div.classList.add('wrapper');
div.innerHTML = `
  <ul>
    <li>One</li>
    <li>Two</li>
    <li>Three</li>
  </ul>
`;

body.appendChild(div);
```

> How to remove elements from the DOM using innerHTML

```javascript
const body = document.querySelector('body');
const div = document.querySelector('.wrapper');
div.innerHTML = '';
```
[Watch video](https://www.youtube.com/watch?v=R1liBYYF9k4) Adding Elements dynamically on Click

[Watch video](https://www.youtube.com/watch?v=0aWGMxrdUZE) Removing Elements dynamically on Click

<h1>Challenge</h1>

- Simple to do app.
    - Use JavaScript to handle tasks like adding, deleting, and marking tasks as complete.
    - Practice working with DOM manipulation and events to make the list interactive.
- Update your github repository created earlier with the day 1 lesson and challenge
    - Write a brief description about the lesson and the challenge on the Readme of the project