# Event delegation and bubbling.

- Event bubbling is a type of event propagation where the event first triggers on the innermost target element, and then successively triggers on the ancestors (parents) of the target element in the same nesting hierarchy till it reaches the outermost DOM element. This type of propagation is supported by all major browsers. The opposite of bubbling is event capturing, which is supported only by a few browsers.
  
> Example:
```html
<div class="outer">
  <div class="inner">
    <button>Click me</button>
  </div>
</div>
```
```javascript
const outer = document.querySelector('.outer');
const inner = document.querySelector('.inner');
const button = document.querySelector('button');

outer.addEventListener('click', () => {
  console.log('The outer div was clicked');
});

inner.addEventListener('click', () => {
  console.log('The inner div was clicked');
});

button.addEventListener('click', () => {
  console.log('The button was clicked');
});
```

- Event capturing is a type of event propagation where the event is first captured by the outermost element and then successively triggers on the descendants (children) of the target element in the same nesting hierarchy till it reaches the innermost DOM element. This type of propagation is supported only by a few browsers. The opposite of capturing is event bubbling, which is supported by all major browsers.

> Example:
```html
<div class="outer">
  <div class="inner">
    <button>Click me</button>
  </div>
</div>
```
```javascript
const outer = document.querySelector('.outer');
const inner = document.querySelector('.inner');
const button = document.querySelector('button');

outer.addEventListener('click', () => {
  console.log('The outer div was clicked');
}, true);

inner.addEventListener('click', () => {
  console.log('The inner div was clicked');
}, true);

button.addEventListener('click', () => {
  console.log('The button was clicked');
}, true);
```

- Event delegation is a technique for listening to events where you delegate a parent element as the listener for all of the events that happen inside it. The benefit of this is that you don't have to add event listeners to specific nodes; instead, the event listener is added to one parent. This is especially useful for elements that are added to the DOM dynamically, since you don't have to add event listeners to them directly.

> Example

```html
<ul id="parent-list">
  <li id="post-1">Item 1</li>
  <li id="post-2">Item 2</li>
  <li id="post-3">Item 3</li>
  <li id="post-4">Item 4</li>
  <li id="post-5">Item 5</li>
  <li id="post-6">Item 6</li>
</ul>
```
```javascript
const parentList = document.getElementById('parent-list');

parentList.addEventListener('click', (event) => {
  const clickedElement = event.target;
  const tagName = clickedElement.tagName;

  if (tagName === 'LI') {
    console.log('List item', clickedElement.id.replace('post-', ''), 'was clicked!');
  }
});
```

# Coding Challenge

## Expandable List

### Description
Create an expandable list where clicking on a list item expands or collapses a sub-list. Use event delegation to handle the click events on the parent list element, and bubbling to toggle the sub-list visibility.

### Instructions
- Create an HTML file with an unordered list element (<ul>) containing several list items (<li>).
- Each list item should have a title and a sub-list containing some content. The sub-list should be initially hidden with CSS (display: none;).
- Use JavaScript to add an event listener to the parent list element (<ul>), and use event delegation to handle click events on the list items (<li>).
- When a list item is clicked, toggle the visibility of its sub-list using the classList property to add or remove the hidden class (which should have the CSS display: none; rule).
- Use bubbling to handle the click events on the child elements of the list item. Clicking on the sub-list should not trigger the expand/collapse behavior.
- Add some basic styling to make the list look nice.

Good luck!