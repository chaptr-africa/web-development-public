#### HTML Semantics and Validations
### HTML Semantics

**Semantic HTML elements** clearly describe their meaning in a human- and machine-readable way. Using semantic elements improves the readability of the code and enhances SEO and accessibility.

### Common Semantic Elements
## Structural Elements

- <header>: Represents introductory content or a set of navigational links. Typically used for the top section of a page or a section.

```html
<header>

      <h1>My Website</h1>

      <nav>

          <ul>

              <li><a href="home">Home</a></li>

              <li><a href="about">About</a></li>

          </ul>

      </nav>

  </header>
```

  

- <nav>: Defines a set of navigation links.
```html
  <nav>

      <ul>

          <li><a href="home">Home</a></li>

          <li><a href="services">Services</a></li>

      </ul>

  </nav>
```

  

- <main>: Represents the dominant content of the <body>. It should only be used once per page and should not include content that is repeated across multiple pages like headers or footers.

```html
<main>

      <section>

          <h2>Main Content</h2>

          <p>This is the main content area.</p>

      </section>

  </main>
```

  

- <footer>: Defines footer content for a section or page. Typically includes copyright information, contact details, or links.

```html
<footer>

      <p>&copy; 2024 My Website. All rights reserved.</p>

</footer>
```

 

### Document Sections

- <section>: Represents a section of content that is thematically related. It often includes a heading.

```html
<section>

      <h2>About Us</h2>

      <p>Information about the company.</p>

</section>
```

  

- <article>: Represents a self-contained piece of content that could be distributed independently, such as a blog post or news article.

```html
 <article>

      <h2>Latest News</h2>

      <p>Details about the latest news.</p>

  </article>
```

  

- <aside>: Contains content indirectly related to the main content, such as sidebars or tangential information.

```html
<aside>

      <h3>Related Links</h3>

      <ul>

          <li><a href="link1">Link 1</a></li>

          <li><a href="link2">Link 2</a></li>

      </ul>

  </aside>
```

  

- <div>: A generic container used for grouping and styling purposes. It does not convey any semantic meaning.

```html
<div class="container">

      <h2>Container Title</h2>

      <p>Content inside the container.</p>

  </div>
```

  

### Text-Level Semantics

- <h1> to <h6>: Headings that define the hierarchy and structure of the content.

  <h1>Main Heading</h1>

  <h2>Subheading</h2>

  

- <p>: Represents a paragraph of text.

 <p>This is a paragraph of text.</p>

  

- <strong>: Indicates that the content has strong importance.

  <strong>Important text</strong>

  

- <em>: Indicates emphasized text.

  <em>Emphasized text</em>




- <code>: Represents a piece of computer code.

  <code>const x = 10;</code>

  

### HTML Validations

HTML validation ensures that web documents adhere to specified standards and syntactical rules. Proper validation helps in maintaining consistency, improving accessibility, and ensuring that web pages render correctly across different browsers.

## Built-in HTML5 Validation

HTML5 provides several built-in attributes and mechanisms for validating user input in forms.

## Attributes for Validation

- **required**: Specifies that an input field must be filled out before submitting the form.

```html
  <input type="text" name="username" required>
```

 

- **pattern**: Defines a regular expression that the input field's value must match.

```html
<input type="text" name="username" pattern="[A-Za-z]{3,10}" title="Username must be 3-10 letters long" required>
```




- **min and max**: Define the minimum and maximum values for numeric and date inputs.

```html
  <input type="number" name="age" min="18" max="100" required>
```

  

- **maxlength**: Sets the maximum number of characters allowed in a text field.

```html
  <input type="text" name="username" maxlength="20">
```

  

- **type**: Specifies the type of input and validates it accordingly (e.g., email, url, number).

  <input type="email" name="email" required>

  

### Form Validation Using JavaScript

JavaScript can be used to perform more complex validations or provide custom validation messages.

# Example:

```html
<form id="myForm">

    <label for="email">Email:</label>

    <input type="email" id="email" name="email" required>

    <br>

    <label for="age">Age:</label>

    <input type="number" id="age" name="age" min="18" max="100" required>

    <br>

    <input type="submit" value="Submit">

</form>
<script>

document.getElementById('myForm').addEventListener('submit', function(event) {

    let email = document.getElementById('email').value;

    let age = document.getElementById('age').value;




    if (!email.includes('@')) {

        alert('Please enter a valid email address.');

        event.preventDefault();

    }




    if (age < 18 || age > 100) {

        alert('Age must be between 18 and 100.');

        event.preventDefault();

    }

});

</script>
```

- The script listens for the submit event of the form.

- It checks the values of the email and age fields and displays an alert if the input does not meet the required criteria.

- event.preventDefault() is used to stop the form from being submitted if the validation fails.

### HTML Validators

You can use HTML validators to check if your HTML code follows the standards. Validators can help you identify errors and issues in your HTML code.

## Accessibility Considerations

Proper HTML semantics improve accessibility for users with disabilities. For instance:

- Use semantic elements to clearly define sections of the page, which helps screen readers interpret the content.

- Include aria attributes to provide additional context where necessary.

# Example:

```html
<article aria-labelledby="article-heading">

    <h2 id="article-heading">Article Title</h2>

    <p>This is an article.</p>

</article>
```

- The aria-labelledby attribute associates the article with its heading, helping users who rely on assistive technologies to understand the content's structure.