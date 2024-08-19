### Introduction To HTML

## Definition

HTML stands for HyperText Markup Language. It is the standard language used to create and design web pages. HTML provides the structure for web documents by using a series of elements, which are essentially instructions for the web browser to display content in a specific way. HTML elements are used to define headings, paragraphs, links, images, lists, and other types of content on a web page.

## HTML Elements

# Tags, Elements, and Attributes

- **Tags**: Tags are the building blocks of HTML. They are used to define elements within a web page. Tags are enclosed in angle brackets, e.g., <tagname>. Most tags come in pairs: an opening tag and a closing tag. For example, <p> is an opening tag, and </p> is the closing tag.

- **Elements**: An element consists of an opening tag, content, and a closing tag. For example, <p>This is a paragraph.</p> is a paragraph element where <p> is the opening tag, This is a paragraph. is the content, and </p> is the closing tag.

- **Attributes**: Attributes provide additional information about an element. They are included in the opening tag and are written as name-value pairs. For example, <a href="https://www.example.com">Example</a> uses the href attribute to specify the URL for a link.

## Basic Structure

# Understanding <html>, <head>, and <body>

An HTML document is structured with a few key elements:

- <html>: This is the root element that contains all the other elements of the HTML document.

- <head>: This section contains meta-information about the document, such as its title, character encoding, linked stylesheets, and scripts. The content within the <head> is not displayed directly on the web page but is used by browsers and search engines.

- <body>: This section contains the content of the web page that is visible to users, such as text, images, links, and other media.

Here's an example of a very basic HTML page that includes all the fundamental elements:

```html
<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>My First Web Page</title>

</head>

<body>

    <h1>Welcome to My Web Page</h1>

    <p>This is a simple HTML document.</p>

    <a href="https://www.example.com">Visit Example.com</a>

</body>

</html>
```




- <!DOCTYPE html>: This declaration defines the document type and version of HTML being used. It helps the browser render the page correctly.

- <html lang="en">: This is the root element of the document. The lang attribute specifies the language of the document.

- <head>: Contains metadata about the document:

  - <meta charset="UTF-8">: Specifies the character encoding for the document.

  - <meta name="viewport" content="width=device-width, initial-scale=1.0">: Ensures proper rendering and touch zooming on mobile devices.

  - <title>My First Web Page</title>: Sets the title of the web page, which appears in the browser tab.




- <body>: Contains the content of the page:

  - <h1>Welcome to My Web Page</h1>: Defines a top-level heading.

  - <p>This is a simple HTML document.</p>: Defines a paragraph.

  - <a href="https://www.example.com">Visit Example.com</a>: Creates a hyperlink to "https://www.example.com".




## HTML Document Structure




- <!DOCTYPE html>: This declaration must be the first line of the HTML document. It tells the browser to expect HTML5, which is the latest version of HTML. It helps the browser to render the document in standards mode.

- <html>: Wraps the entire HTML document. It can also include a lang attribute to specify the language of the content.




- <head>: Contains metadata and links to external resources. Common elements in the <head> include:

  - <meta>: Provides metadata like character set and viewport settings.

  - <title>: Sets the title of the document shown in the browser tab.

  - <link>: Links to external resources like CSS stylesheets.

  - <script>: Links to JavaScript files or contains JavaScript code.




- <body>: Encloses the content that is visible to the user, such as:

  - Headings (<h1>, <h2>, <h3>, etc.)

  - Paragraphs (<p>)

  - Links (<a>)

  - Images (<img>)

  - Lists (<ul>, <ol>, <li>)

  - Tables (<table>, <tr>, <td>, <th>)

## Assignment:

# Instructions:

Create an HTML file named index.html.
Set up the basic HTML structure with <!DOCTYPE html>, <html>, <head>, and <body> tags.
Include a <title> in the <head> with a meaningful title for your page.
In the <body>, add:
A main heading (<h1>) with the text "Welcome to My Website".
A subheading (<h2>) with the text "About Me".
A paragraph (<p>) with a brief introduction about yourself.
An image (<img>) with a placeholder image URL and alt text.
A link (<a>) to your favorite website.
A list of your top three hobbies, using an unordered list (<ul>).