
**Title 1:  More of Events, Event Listeners, Event Handlers, Event Propagation**

- Event listeners are a fundamental part of web development. They allow us to respond to user actions such as clicks, mouse movements, and keyboard input.
- In this session, we'll provide comprehensive coverage of event listeners, including different types of events, attaching event listeners, and removing event listeners.

**Title 2: Event Listeners vs. Event Handlers**
- Let's compare event listeners and event handlers with practical examples.
- Event Listeners (JavaScript):
  
    ```javascript
    const button = document.getElementById('myButton');
    button.addEventListener('click', () => {
        console.log('Button clicked with an event listener.');
    });
    ```
- In this JavaScript example, we use `addEventListener` to attach a click event listener to the button with the ID 'myButton.' When the button is clicked, it logs a message to the console.
- Event Handlers (HTML):
    ```html
    <button id="myButton" onclick="handleClick()">Click Me</button>
    <script>
      function handleClick() {
        console.log('Button clicked with an event handler.');
      }
    </script>
    ```
-  In this HTML example, we define an event handler using the `onclick` attribute in the button element. When the button is clicked, the `handleClick` function is called, which logs a message to the console.

**Title 4: Event Propagation**
- Event propagation is how events in the DOM traverse the tree structure of elements. Understanding event propagation is crucial for handling events efficiently.
- We'll cover the two phases of event propagation, capturing and bubbling, and how they influence event handling.

**Title 5: Capturing Phase vs. Bubbling Phase**
-  We'll provide a clear distinction between the capturing and bubbling phases of event propagation with code examples.
- Capturing Phase:
    ```javascript
    document.getElementById('myElement').addEventListener('click', () => {
        console.log('Capturing phase');
    }, true);
    ```
- In this JavaScript example, we use the third parameter `true` to indicate that the event listener should be in the capturing phase. When an element with the ID 'myElement' is clicked, it logs 'Capturing phase' to the console before the bubbling phase occurs.
- Bubbling Phase:
    ```javascript
    document.getElementById('myElement').addEventListener('click', () => {
        console.log('Bubbling phase');
    });
    ```
- In this JavaScript example, we omit the third parameter, allowing the event listener to operate in the default bubbling phase. When an element with the ID 'myElement' is clicked, it logs 'Bubbling phase' to the console after the capturing phase.

  
**Title 7: Practical Example: Building an Image Gallery**
- Let's apply what we've learned by building an image gallery that responds to user clicks and swipes. This hands-on example will cover event listeners, event propagation, and efficient event handling.
- We'll walk through the HTML, CSS, and JavaScript code used to create the image gallery.

**Key Takeaways**
- The main takeaways from today's session, providing a solid understanding of how to work with events in web development.

# Challenge
- Create a simple web page with two buttons, each with a different background color. When a button is clicked, the background color of the page should change to the color of the clicked button. Additionally, if the user clicks anywhere on the page outside of the buttons, the background color should return to its original color.
