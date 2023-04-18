# Event delegation and bubbling.

[Read](https://vegibit.com/javascript-event-propagation-and-bubbling/)

[Watch video](https://www.youtube.com/watch?v=KaHZdW02Tg0) Event bubbling in JavaScript

[Watch Video](https://www.youtube.com/watch?v=aZ3JWv0ofuA) Event Delegation in JavaScript

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