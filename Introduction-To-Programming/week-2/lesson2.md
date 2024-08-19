### HTML Links Tutorial

We will learn how to create hyperlinks in HTML. Links are a crucial part of the web, allowing users to navigate between different pages and websites.

## Introduction to Links

**Links**, or **hyperlinks**, are used to connect one web page to another. They can link to different sections within the same page, different pages on the same website, or external websites. Links are created using the <a> (anchor) tag in HTML.

# Basic Link Syntax

The basic syntax for creating a link is as follows:

```html
    <a href="URL">Link Text</a>
```



# Example:
```html
<!DOCTYPE html>

<html>

<head>

    <title>Basic Link Example</title>

</head>

<body>

    <h1>Basic Link</h1>

    <p>Visit <a href="https://www.example.com">Example</a> for more information.</p>

</body>

</html>
```




- <a>: The anchor tag defines the start and end of the link.

- **href**: The "hypertext reference" attribute specifies the URL of the page the link goes to.

- **Link Text**: The text between the <a> and </a> tags is the clickable part of the link.

# Example Output

- Visit (https://www.example.com) for more information.

## Link Attributes
# href Attribute

The **href** attribute specifies the URL of the destination page.

# target Attribute

The **target** attribute specifies where to open the linked document. Common values include:

# _self:

Opens the link in the same window/tab (default).

# _blank

Opens the link in a new window/tab.

```html
    <!DOCTYPE html>

    <html>

    <head>

        <title>Link Attributes Example</title>

    </head>

    <body>

        <h1>Link Attributes</h1>

        <p>Open <a href="https://www.example.com" target="_blank">Example</a> in a new tab.</p>

    </body>

    </html>
```


- **target="_blank"**: This attribute-value pair opens the link in a new tab or window.

# title Attribute

The **title** attribute provides additional information about the link, usually displayed as a tooltip when the mouse hovers over the link.

```html
<!DOCTYPE html>

<html>

<head>

    <title>Link Title Example</title>

</head>

<body>

    <h1>Link Title</h1>

    <p>Visit <a href="https://www.example.com" title="Go to Example website">Example</a> for more information.</p>

</body>

</html>
```




- **title="Go to Example website"**: This attribute-value pair displays a tooltip when the mouse hovers over the link.

## Relative vs Absolute URLs
# Absolute URLs

An absolute URL contains the complete address to a resource, including the protocol (e.g., https://).

# Example

```html
<a href="https://www.example.com">Visit Example</a>
```


# Relative URLs

A relative URL contains only the path to the resource relative to the current page's location.

# Example

```html
<a href="about.html">About Us</a>
```




- **Absolute URLs** are used for linking to external websites.

- **Relative URLs** are used for linking to pages within the same website.




## Linking to Different Sections of the Same Page

You can create links that jump to specific sections within the same page using fragment identifiers.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Anchor Links Example</title>

</head>

<body>

    <h1>Anchor Links</h1>

    <p><a href="section2">Go to Section 2</a></p>

    <h2 id="section1">Section 1</h2>

    <p>Content for section 1...</p>

    <h2 id="section2">Section 2</h2>

    <p>Content for section 2...</p>

</body>

</html>
```




- href="section2": Links to the element with the id attribute set to "section2".

- id="section2": Sets the identifier for the element to be linked to.




## Creating Email Links

You can create links that open the user's default email client with a pre-filled email address using the mailto: scheme.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Email Link Example</title>

</head>

<body>

    <h1>Email Link</h1>

    <p>Contact us at <a href="mailto:info@example.com">info@example.com</a>.</p>

</body>

</html>
```



- href="mailto:info@example.com": This attribute-value pair opens the default email client with the email address pre-filled.

### Styling Links

Links can be styled using CSS to change their appearance.

```html
<!DOCTYPE html>

<html>

<head>

    <title>Styled Link Example</title>

    <style>

        a {

            color: blue;

            text-decoration: none;

        }

        a:hover {

            color: red;

            text-decoration: underline;

        }

    </style>

</head>

<body>

    <h1>Styled Links</h1>

    <p>Visit <a href="https://www.example.com">Example</a> for more information.</p>

</body>

</html>
```




- **color**: blue;: Sets the link color to blue.

- **text-decoration: none;**: Removes the default underline from the link.

- **a:hover**: Styles applied when the mouse hovers over the link.

- **color: red;**: Sets the link color to red on hover.

- **text-decoration: underline;**: Underlines the link on hover.

## Practice Examples
# Practice Example 1: Creating Basic Links

Create an HTML file named basic-links.html and add a few links to different websites.

# Practice Example 2: Creating Relative Links

Create an HTML file named relative-links.html and add links to other pages in your project.

#### HTML Images

We will learn how to insert and manage images in HTML. Images are an essential part of web design, enhancing the visual appeal and user experience of your website.

## Introduction to Images

Images are added to web pages using the <img> tag. Unlike other HTML tags, the <img> tag is self-closing, meaning it does not have a closing tag. The <img> tag requires the src attribute, which specifies the path to the image file.

## Basic Image Syntax

The basic syntax for inserting an image is as follows:

```html
<img src="URL" alt="Description">
```

# Example:

```html
<!DOCTYPE html>

<html>

<head>

    <title>Basic Image Example</title>

</head>

<body>

    <h1>Basic Image</h1>

    <img src="https://www.example.com/image.jpg" alt="Example Image">

</body>

</html>
```




- <img>: The image tag defines the start and end of the image element.

- **src**: The "source" attribute specifies the URL of the image.

- **alt**: The "alternative text" attribute provides a text description of the image for accessibility and when the image cannot be displayed.

### Image Attributes
# src Attribute

The src attribute specifies the path to the image file.

# alt Attribute

The alt attribute provides alternative text for the image, which is displayed if the image cannot be loaded. It is also used by screen readers to describe the image for visually impaired users.

# width and height Attributes

The width and height attributes specify the dimensions of the image. They can be set in pixels or as percentages of the containing element.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Image Attributes Example</title>

</head>

<body>

    <h1>Image Attributes</h1>

    <img src="https://www.example.com/image.jpg" alt="Example Image" width="300" height="200">

</body>

</html>
```

- **width="300"**: Sets the width of the image to 300 pixels.

- **height="200"**: Sets the height of the image to 200 pixels.

# title Attribute

The title attribute provides additional information about the image, usually displayed as a tooltip when the mouse hovers over the image.

```html
    <!DOCTYPE html>

    <html>

    <head>

        <title>Image Title Example</title>

    </head>

    <body>

        <h1>Image Title</h1>

        <img src="https://www.example.com/image.jpg" alt="Example Image" title="This is an example image">

    </body>

    </html>
```

# Explanation

- title="This is an example image": This attribute-value pair displays a tooltip when the mouse hovers over the image.

## Using Different Image Formats

# JPEG

- Best for photographs and images with many colors.

- Supports millions of colors.

- Compressed format, resulting in smaller file sizes.

```html
<img src="image.jpg" alt="JPEG Image">
```




# PNG

- Best for images with transparent backgrounds or images requiring high quality.

- Supports lossless compression and transparency.

- Larger file sizes compared to JPEG.

```html
<img src="image.png" alt="PNG Image">
```




# GIF

- Best for simple graphics, animations, and images with limited colors.

- Supports animations and transparency.

- Limited to 256 colors.

# Example
```html
<img src="image.gif" alt="GIF Image">
```


### Responsive Images

Responsive images adjust their size and resolution based on the screen size and resolution of the device being used.

# Using srcset Attribute

The srcset attribute allows you to define a list of image sources with different resolutions.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Responsive Images Example</title>

</head>

<body>

    <h1>Responsive Images</h1>

    <img src="image-300.jpg" srcset="image-300.jpg 300w, image-600.jpg 600w, image-900.jpg 900w" sizes="(max-width: 600px) 100vw, 50vw" alt="Responsive Image">

</body>

</html>
```


- srcset="image-300.jpg 300w, image-600.jpg 600w, image-900.jpg 900w": Defines different image sources and their widths.

- sizes="(max-width: 600px) 100vw, 50vw": Specifies the sizes of the image for different viewport widths.

## Using CSS

You can also make images responsive using CSS.

```html
<!DOCTYPE html>

<html>

<head>

    <title>Responsive Images with CSS</title>

    <style>

        img {

            max-width: 100%;

            height: auto;

        }

    </style>

</head>

<body>

    <h1>Responsive Images with CSS</h1>

    <img src="https://www.example.com/image.jpg" alt="Responsive Image with CSS">

</body>

</html>
```

- max-width: 100%;: Ensures the image width does not exceed the width of its container.

- height: auto;: Maintains the aspect ratio of the image.

## Image Maps

Image maps allow you to create clickable areas on an image that link to different destinations.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Image Map Example</title>

</head>

<body>

    <h1>Image Map</h1>

    <img src="https://www.example.com/map.jpg" alt="Map" usemap="map">

    <map name="map">

        <area shape="rect" coords="34,44,270,350" href="https://www.example.com/location1" alt="Location 1">

        <area shape="circle" coords="477,300,50" href="https://www.example.com/location2" alt="Location 2">

    </map>

</body>

</html>
```

- usemap="map": Associates the image with the map element.

- <map name="map">: Defines the map element with the name "map".

- <area>: Defines a clickable area within the map. The shape attribute specifies the shape of the area (e.g., rect for rectangle, circle for circle). The coords attribute specifies the coordinates of the area.

## Practice Examples
# Practice Example 1: Basic Image

Create an HTML file named basic-image.html and add an image.

# Practice Example 2: Image Attributes

Create an HTML file named image-attributes.html and add an image with different attributes.

# Practice Example 3: Responsive Images

Create an HTML file named responsive-images.html and add a responsive image.

# Practice Example 4: Image Map

Create an HTML file named image-map.html and add an image map.




