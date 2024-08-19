#### HTML Multimedia

We'll explore how to embed multimedia elements such as videos and audio in HTML. Multimedia elements can enhance the user experience on your website by adding dynamic content like videos and sound.

HTML provides tags for embedding multimedia content such as videos and audio. These tags include <video> for videos and <audio> for audio files. Both tags support a variety of attributes to control playback and provide alternative sources.

### Embedding Videos

# Basic Video Syntax

The basic syntax for embedding a video is as follows:

```html
<video src="URL" controls>

    Your browser does not support the video tag.

</video>
```

# Example
```html
<!DOCTYPE html>

<html>

<head>

    <title>Basic Video Example</title>

</head>

<body>

    <h1>Basic Video</h1>

    <video src="https://www.example.com/video.mp4" controls width="600">

        Your browser does not support the video tag.

    </video>

</body>

</html>
```


- <video>: The video tag defines the video element.

- src: The "source" attribute specifies the URL of the video file.

- controls: This attribute adds video controls like play, pause, and volume.

- width: Sets the width of the video player in pixels.

## Multiple Sources

You can provide multiple video sources to ensure compatibility across different browsers.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Multiple Video Sources</title>

</head>

<body>

    <h1>Multiple Video Sources</h1>

    <video controls width="600">

        <source src="https://www.example.com/video.mp4" type="video/mp4">

        <source src="https://www.example.com/video.ogg" type="video/ogg">

        Your browser does not support the video tag.

    </video>

</body>

</html>
```


- <source>: Specifies an alternative video source and its type.

- type: The MIME type of the video file (e.g., video/mp4, video/ogg).




## Embedding Audio

# Basic Audio Syntax

The basic syntax for embedding audio is as follows:

```html
<audio src="URL" controls>

    Your browser does not support the audio tag.

</audio>
```

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Basic Audio Example</title>

</head>

<body>

    <h1>Basic Audio</h1>

    <audio src="https://www.example.com/audio.mp3" controls>

        Your browser does not support the audio tag.

    </audio>

</body>

</html>
```




- <audio>: The audio tag defines the audio element.

- src: The "source" attribute specifies the URL of the audio file.

- controls: This attribute adds audio controls like play, pause, and volume.

## Multiple Sources

You can provide multiple audio sources to ensure compatibility across different browsers.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Multiple Audio Sources</title>

</head>

<body>

    <h1>Multiple Audio Sources</h1>

    <audio controls>

        <source src="https://www.example.com/audio.mp3" type="audio/mp3">

        <source src="https://www.example.com/audio.ogg" type="audio/ogg">

        Your browser does not support the audio tag.

    </audio>

</body>

</html>
```

- <source>: Specifies an alternative audio source and its type.

- type: The MIME type of the audio file (e.g., audio/mp3, audio/ogg).


## Custom Controls

By default, the <video> and <audio> tags come with built-in controls. However, you can create custom controls using JavaScript and CSS.

# Example
```html
<!DOCTYPE html>

<html>

<head>

    <title>Custom Video Controls</title>

    <style>

        controls {

            display: flex;

            justify-content: center;

            margin-top: 10px;

        }

        button {

            padding: 5px 10px;

            margin: 0 5px;

        }

    </style>

</head>

<body>

    <h1>Custom Video Controls</h1>

    <video id="video" src="https://www.example.com/video.mp4" width="600"></video>

    <div id="controls">

        <button onclick="playVideo()">Play</button>

        <button onclick="pauseVideo()">Pause</button>

        <button onclick="stopVideo()">Stop</button>

    </div>

    <script>

        var video = document.getElementById('video');




        function playVideo() {

            video.play();

        }




        function pauseVideo() {

            video.pause();

        }




        function stopVideo() {

            video.pause();

            video.currentTime = 0;

        }

    </script>

</body>

</html>
```




- The video element is controlled by JavaScript functions that play, pause, and stop the video.

- Custom controls are created using HTML buttons and styled with CSS.

## bResponsive Multimedia

Responsive multimedia elements adjust their size based on the screen size of the device.

# Example Using CSS

```html
<!DOCTYPE html>

<html>

<head>

    <title>Responsive Multimedia</title>

    <style>

        video, audio {

            max-width: 100%;

            height: auto;

        }

    </style>

</head>

<body>

    <h1>Responsive Multimedia</h1>

    <video src="https://www.example.com/video.mp4" controls></video>

    <audio src="https://www.example.com/audio.mp3" controls></audio>

</body>

</html>
```

- max-width: 100%;: Ensures that the multimedia element does not exceed the width of its container.

- height: auto;: Maintains the aspect ratio of the multimedia element.




## Practice Examples
# Practice Example 1: Basic Video

Create an HTML file named basic-video.html and embed a video with controls.

# Practice Example 2: Basic Audio

Create an HTML file named basic-audio.html and embed an audio file with controls.

# Practice Example 3: Multiple Video Sources

Create an HTML file named multiple-video-sources.html and provide multiple video sources.

# Practice Example 4: Responsive Multimedia

Create an HTML file named responsive-multimedia.html and ensure that multimedia elements are responsive.

## Assignments
# Create a Video Gallery:

   - Create an HTML file named video-gallery.html.

   - Embed at least three different videos from different sources.

   - Use the controls attribute for each video.

   - Make sure the videos are responsive.


# Create an Audio Playlist:

   - Create an HTML file named audio-playlist.html.

   - Embed at least three different audio files from different sources.

   - Use the controls attribute for each audio file.

   - Ensure that the audio files are responsive.


# Custom Video Controls:

   - Create an HTML file named

#### HTML Tables

Tables are a powerful way to present data in a structured format.

## Introduction to HTML Tables

Tables are used to organize and display data in a grid format. They are made up of rows and columns, with each cell containing data or information.

## Basic Table Structure

The basic structure of an HTML table consists of several key elements:

- <table>: Defines the table element.

- <tr>: Defines a table row.

- <td>: Defines a table cell (data).

- <th>: Defines a table header cell.

# Example

```
<!DOCTYPE html>

<html>

<head>

    <title>Basic Table Example</title>

</head>

<body>

    <h1>Basic Table</h1>

    <table border="1">

        <tr>

            <th>Name</th>

            <th>Age</th>

            <th>Occupation</th>

        </tr>

        <tr>

            <td>John Doe</td>

            <td>30</td>

            <td>Web Developer</td>

        </tr>

        <tr>

            <td>Jane Smith</td>

            <td>25</td>

            <td>Graphic Designer</td>

        </tr>

    </table>

</body>

</html>
```


- <table>: Defines the table.

- <tr>: Defines a row in the table.

- <th>: Defines a header cell in the table, which is bold and centered by default.

- <td>: Defines a data cell in the table.


## Table Elements
 <table>

The <table> element defines the entire table.

 <tr>

The <tr> element defines a row in the table.

 <th>

The <th> element defines a header cell, which is typically bold and centered.

 <td>

The <td> element defines a standard data cell in the table.

# Example with More Elements

```html
<!DOCTYPE html>

<html>

<head>

    <title>Table Elements Example</title>

</head>

<body>

    <h1>Table Elements</h1>

    <table border="1">

        <thead>

            <tr>

                <th>Product</th>

                <th>Price</th>

                <th>Quantity</th>

            </tr>

        </thead>

        <tbody>

            <tr>

                <td>Apple</td>

                <td>$1.00</td>

                <td>10</td>

            </tr>

            <tr>

                <td>Banana</td>

                <td>$0.50</td>

                <td>20</td>

            </tr>

        </tbody>

        <tfoot>

            <tr>

                <td>Total</td>

                <td></td>

                <td>30</td>

            </tr>

        </tfoot>

    </table>

</body>

</html>
```




- <thead>: Defines the header section of the table.

- <tbody>: Defines the body section of the table.

- <tfoot>: Defines the footer section of the table.

## Table Attributes
# border

The border attribute specifies the width of the table border. (Note: The border attribute is deprecated in favor of CSS styling.)

# cellpadding

The cellpadding attribute specifies the space between the cell content and its border.

# cellspacing

The cellspacing attribute specifies the space between cells.

# Example with Attributes

```html
<!DOCTYPE html>

<html>

<head>

    <title>Table Attributes Example</title>

</head>

<body>

    <h1>Table Attributes</h1>

    <table border="1" cellpadding="10" cellspacing="5">

        <tr>

            <th>Header 1</th>

            <th>Header 2</th>

        </tr>

        <tr>

            <td>Data 1</td>

            <td>Data 2</td>

        </tr>

    </table>

</body>

</html>
```




- border="1": Adds a border of 1 pixel around the table.

- cellpadding="10": Adds 10 pixels of space inside each cell.

- cellspacing="5": Adds 5 pixels of space between cells.


### Styling Tables with CSS

You can use CSS to style tables, including borders, padding, colors, and more.

```html
<!DOCTYPE html>

<html>

<head>

    <title>Styled Table Example</title>

    <style>

        table {

            width: 100%;

            border-collapse: collapse;

        }

        th, td {

            border: 1px solid black;

            padding: 10px;

            text-align: left;

        }

        th {

            background-color: f2f2f2;

        }

        tr:nth-child(even) {

            background-color: f9f9f9;

        }

    </style>

</head>

<body>

    <h1>Styled Table</h1>

    <table>

        <tr>

            <th>Name</th>

            <th>Age</th>

            <th>Occupation</th>

        </tr>

        <tr>

            <td>John Doe</td>

            <td>30</td>

            <td>Web Developer</td>

        </tr>

        <tr>

            <td>Jane Smith</td>

            <td>25</td>

            <td>Graphic Designer</td>

        </tr>

    </table>

</body>

</html>
```




- **border-collapse**: collapse;: Collapses the borders into a single border.

- **padding**: 10px;: Adds padding inside each cell.

- **background-color: f2f2f2;**: Sets a background color for header cells.

- **tr:nth-child(even) { background-color: f9f9f9; }**: Alternates row colors for better readability.



## Responsive Tables

To make tables responsive, you can use CSS to allow tables to scroll horizontally on smaller screens.

# Example
```html
<!DOCTYPE html>

<html>

<head>

    <title>Responsive Table Example</title>

    <style>

        .table-container {

            overflow-x: auto;

            -webkit-overflow-scrolling: touch;

        }

        table {

            width: 100%;

            border-collapse: collapse;

        }

        th, td {

            border: 1px solid black;

            padding: 10px;

            text-align: left;

        }

        th {

            background-color: f2f2f2;

        }

    </style>

</head>

<body>

    <h1>Responsive Table</h1>

    <div class="table-container">

        <table>

            <tr>

                <th>Name</th>

                <th>Age</th>

                <th>Occupation</th>

                <th>Country</th>

                <th>City</th>

            </tr>

            <tr>

                <td>John Doe</td>

                <td>30</td>

                <td>Web Developer</td>

                <td>USA</td>

                <td>New York</td>

            </tr>

            <tr>

                <td>Jane Smith</td>

                <td>25</td>

                <td>Graphic Designer</td>

                <td>UK</td>

                <td>London</td>

            </tr>

        </table>

    </div>

</body>

</html>
```

- **.table-container**: Wraps the table and allows horizontal scrolling.

- **overflow-x**: auto;: Adds horizontal scroll if needed.

## Practice Examples
# Practice Example 1: Basic Table

Create an HTML file named basic-table.html and add a simple table.

# Practice Example 2: Table with Header, Body, and Footer

Create an HTML file named table-header-footer.html and use the <thead>, <tbody>, and <tfoot> elements.

# Practice Example 3: Styled Table

Create an HTML file named styled-table.html and apply CSS styling to the table.

# Practice Example 4: Responsive Table

Create an HTML file named responsive-table.html and ensure the table is responsive.

## Assignments

# Create a Product Table:

   - Create an HTML file named product-table.html.

   - Create a table listing products with columns for Name, Description, Price, and Quantity.

   - Use CSS to style the table with borders, padding, and alternating row colors.

# Build a Student Grades Table:

   - Create an HTML file named grades-table.html.

   - Create a table to display student names, grades, and comments.

   - Include a header row, a body section, and a footer with a total number of students.

# Responsive Product List:

   - Create an HTML file named responsive-products.html.

   - Design a table for a product list with columns for Name, Price, and Availability.

   - Ensure the table is responsive and fits well on mobile devices.
