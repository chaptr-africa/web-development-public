### HTML Text Formatting

Welcome to the world of HTML! In this tutorial, we will learn about various text formatting tags in HTML. Text formatting helps in enhancing the appearance of your text on a webpage, making it more readable and visually appealing.

## Table of Contents

Heading Tags
Paragraph Tag
Bold Text
Strong Text
Italic Text
Emphasized Text
Underlined Text
Strikethrough Text
Superscript Text
Subscript Text
Combining Multiple Formatting Tags
Practice Examples
Assignments

HTML provides six levels of headings, <h1> to <h6>. Headings are used to define the titles and subtitles on your webpage. The <h1> tag represents the main heading and is the largest, while <h6> represents the smallest heading.

Example:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Heading Tags Example</title>
  </head>
  <body>
    <h1>This is a Heading 1</h1>
    <h2>This is a Heading 2</h2>
    <h3>This is a Heading 3</h3>
    <h4>This is a Heading 4</h4>
    <h5>This is a Heading 5</h5>
    <h6>This is a Heading 6</h6>
  </body>
</html>
```

- <h1> is used for the main heading of your webpage.
- <h2> to <h6> are used for subheadings.
- Headings are important for SEO and readability, as they help in organizing content.

Example Output:

- ###### Heading 1: The largest and most important heading.

- ##### Heading 2: Slightly smaller than <h1>.

- #### Heading 3: Smaller than <h2>.

- ### Heading 4: Smaller than <h3>.

- ## Heading 5: Smaller than <h4>.

- # Heading 6: The smallest heading.

## Paragraph Tag

The <p> tag is used to define paragraphs of text. It automatically adds some space before and after the paragraph to separate it from other content.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Paragraph Tag Example</title>
  </head>
  <body>
    <p>This is a paragraph of text. It is enclosed in a</p>
    <p>tag.</p>
    <p>This is another paragraph. Each</p>
    <p>tag creates a new paragraph.</p>
  </body>
</html>
```

- <p> is used to create a paragraph.
- It provides a block of text with some spacing around it, making it easier to read.

Example Output:

- Each <p> tag creates a separate paragraph of text with some space around it.

Bold Text

The <b> tag makes the enclosed text bold. Note that <b> does not add any extra emphasis, it just makes the text bold for visual purposes.

Example:

``` html
<!DOCTYPE html>
<html>
    <head>
        <title>Bold Text Example</title>
    </head>
    <body>
        <p>This is <b>bold</b> text using the <b> tag.</p>
    </body>
</html>
```

- <b> is used to make text bold.
- It visually emphasizes the text without adding semantic importance.

# Example Output:

- The word "bold" will appear in bold.

## **Strong Text**

The <strong> tag is used to define text with strong importance. Browsers typically render it as bold, but it also conveys semantic importance, indicating that the text is of high relevance.

Example:
``` html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Strong Text Example</title>
        </head>
        <body>
            <p>This is <strong>strong</strong> text using the <strong> tag.</p>
        </body>
    </html>
```

- <strong> is used to indicate that the text is of strong importance.
- It is often rendered as bold by browsers.

# Example Output:

- The word "**strong**" will appear in bold and is considered more important by search engines.

## Italic Text

The <i> tag is used to make the enclosed text italic. Like <b>, it does not add any extra emphasis, it just makes the text italic for visual purposes.

Example:

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Italic Text Example</title>
    </head>
    <body>
        <p>This is <i>italic</i> text using the <i> tag.</p>
    </body>
</html>
```

- <i> is used to make text italic.
- It visually emphasizes the text without adding semantic importance.

# Output:

- The word "italic" will appear in italics.

## Emphasized Text

The <em> tag is used to emphasize text. Browsers typically render it as italic, but it also conveys semantic emphasis, indicating that the text is of special importance.

Example:

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Emphasized Text Example</title>
        </head>
        <body>
            <p>This is <em>emphasized</em> text using the <em> tag.</p>
        </body>
    </html>
```

- <em> is used to indicate that the text is emphasized.
- It is often rendered as italic by browsers.

Output:

- The word "emphasized" will appear in italics and is considered more important by search engines.

## Underlined Text

The <u> tag is used to underline the text. Underlined text is often used to denote links or important information.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Underlined Text Example</title>
    </head>
    <body>
        <p>This is <u>underlined</u> text using the <u> tag.</p>
    </body>
</html>
```

- <u> is used to underline text.
- It visually emphasizes the text by adding an underline.

# Output:

- The word "underlined" will appear with an underline.

# ~~Strikethrough Text~~

The <s> tag is used to indicate that text is no longer correct or relevant. Browsers typically render it with a strikethrough.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Strikethrough Text Example</title>
    </head>
    <body>
        <p>This is <s>strikethrough</s> text using the <s> tag.</p>
    </body>
</html>
```

- <s> is used to indicate that the text has been struck through.
- It visually represents text that is no longer valid or relevant.

# Output:

- The word "~~strikethrough~~" will appear with a line through it.

## Superscript Text

The <sup> tag is used to define superscript text, which is text raised slightly above the normal line. Superscript is commonly used for footnotes, mathematical expressions, and chemical formulas.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Superscript Text Example</title>
    </head>
    <body>
        <p>This is <sup>superscript</sup> text using the <sup> tag.</p>
        <p>H<sub>2</sub>O is the chemical formula for water.</p>
    </body>
</html>
```

- <sup> is used to raise text above the normal line.
- Commonly used for footnotes and mathematical expressions.

# Output:

- The word "superscript" will appear raised above the normal line.
- The text "H2O" will show "2" as a subscript.

## Subscript Text

The <sub> tag is used to define subscript text, which is text lowered slightly below the normal line. Subscript is commonly used in chemical formulas and mathematical expressions.

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Subscript Text Example</title>
        </head>
        <body>
            <p>This is <sub>subscript</sub> text using the <sub> tag.</p>
            <p>E = mc<sup>2</sup> is Einstein's famous equation.</p>
        </body>
    </html>
```

- <sub> is used to lower text below the normal line.
- Commonly used in chemical formulas and mathematical expressions.

# Output:

- The word "subscript" will appear lowered below the normal line.
- The text "E = mc2" will show "2" as a superscript.

## Combining Multiple Formatting Tags

You can combine multiple formatting tags to apply different styles to the same text. Nesting tags allows for complex formatting.

```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Combined Formatting Example</title>
        </head>
        <body>
            <p>This is <b><i>bold and italic</i></b> text.</p>
            <p>This is <strong><em>strong and emphasized</em></strong> text.</p>
            <p>This is <u><sup>underlined and superscript</sup></u> text.</p>
            <p>This is <b><i><u><strong>bold, italic, underlined, and strong</strong></u></i></b> text.</p>
        </body>
    </html>
```

- You can nest tags like <b> and <i> to make text both bold and italic.
- Similarly, <strong> and <em> can be combined for strong emphasis and italics.
- Combining tags provides greater flexibility in formatting your text.

# Output:

- Various combinations of text formatting will be displayed, showcasing bold, italic, underlined, and superscript styles.

## Practice Examples

Practice Example 1: Formatting Text

Create an HTML file named text-formatting.html and apply different text formatting tags.

<!DOCTYPE html>
<html>
<head>
<title>Text Formatting Practice</title>
</head>
<body>
<h1>Text Formatting Practice</h1>
<p>This is a paragraph with <b>bold</b> text.</p>
<p>This is a paragraph with <i>italic</i> text.</p>
<p>This is a paragraph with <u>underlined</u> text.</p>
<p>This is a paragraph with <s>strikethrough</s> text.</p>
<p>This is a paragraph with <strong>strong</strong> text.</p>
<p>This is a paragraph with <em>emphasized</em> text.</p>
<p>This is a paragraph with <sup>superscript</sup> text.</p>
<p>This is a paragraph with <sub>subscript</sub> text.</p>
</body>
</html>



Practice Example 2: Combining Formatting Tags

Create an HTML file named combined-formatting.html and combine different formatting tags.

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Combined Formatting Practice</title>
    </head>
    <body>
        <h1>Combined Formatting Practice</h1>
        <p>This is <b><i>bold and italic</i></b> text.</p>
        <p>This is <strong><em>strong and emphasized</em></strong> text.</p>
        <p>This is <u><sup>underlined and superscript</sup></u> text.</p>
        <p>This is <b><i><u><strong>bold, italic, underlined, and strong</strong></u></i></b> text.</p>
    </body>
</html>
```

## Assignments

# Create a Bio Page:

- Create an HTML file named bio.html.
- Include a heading with your name.
- Write a short biography in a paragraph.
- Bold your name wherever it appears in the biography.
- Italicize any important achievements.
- Use <em> for any emphasis in the biography.
- Underline any key points you want to highlight.

# Recipe Page:

- Create an HTML file named recipe.html.
- Include a heading with the name of a recipe.
- Write the ingredients in a paragraph.
- Bold the quantities of the ingredients.
- Italicize any optional ingredients.
- Use <sup> and <sub> where necessary (e.g., chemical notations).

# Math Formulas:

- Create an HTML file named math-formulas.html.
- Write a few mathematical equations using <sup> and <sub>.
- Use <strong> to highlight important formulas.

#### HTML Lists

We will learn about different types of lists in HTML and how to use them. Lists are a great way to organize and present information in a structured manner.

## Unordered Lists

Unordered lists are used to group a set of related items in no particular order. Each item in the list is marked with a bullet point.

```html
<ul>

    <li>Item 1</li>

    <li>Item 2</li>

    <li>Item 3</li>

</ul>
```

 ```html
    <!DOCTYPE html>

    <html>

    <head>

        <title>Unordered List Example</title>

    </head>

    <body>

        <h1>Unordered List</h1>

        <ul>

            <li>Apple</li>

            <li>Banana</li>

            <li>Cherry</li>

        </ul>

    </body>

    </html>
```




- <ul>: Stands for "unordered list." It defines the start and end of the list.

- <li>: Stands for "list item." Each <li> tag represents an item in the list.

## Ordered Lists

Ordered lists are used to group a set of related items in a specific order. Each item in the list is marked with a number.

 Syntax

```html
    <ol>

        <li>Step 1</li>

        <li>Step 2</li>

        <li>Step 3</li>

    </ol>
```




Example:

```html
    <!DOCTYPE html>

    <html>

    <head>

        <title>Ordered List Example</title>

    </head>

    <body>

        <h1>Ordered List</h1>

        <ol>

            <li>Preheat the oven</li>

            <li>Mix the ingredients</li>

            <li>Bake for 30 minutes</li>

        </ol>

    </body>

    </html>
```




- <ol>: Stands for "ordered list." It defines the start and end of the list.

- <li>: Stands for "list item." Each <li> tag represents an item in the list.


You can nest lists inside each other to create more complex structures. Both ordered and unordered lists can be nested.

 Syntax

```html
<ul>

    <li>Fruit

        <ul>

            <li>Apple</li>

            <li>Banana</li>

        </ul>

    </li>

    <li>Vegetables

        <ul>

            <li>Carrot</li>

            <li>Broccoli</li>

        </ul>

    </li>

</ul>
```

Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Nested List Example</title>

</head>

<body>

    <h1>Nested List</h1>

    <ul>

        <li>Fruit

            <ul>

                <li>Apple</li>

                <li>Banana</li>

            </ul>

        </li>

        <li>Vegetables

            <ul>

                <li>Carrot</li>

                <li>Broccoli</li>

            </ul>

        </li>

    </ul>

</body>

</html>
```




- A <ul> or <ol> can be nested inside an <li>.

- This allows for creating hierarchical lists.


### Description Lists

Description lists are used for defining terms and descriptions. They consist of a <dl> (description list), <dt> (description term), and <dd> (description definition).

 Syntax

```html
<dl>

    <dt>HTML</dt>

    <dd>A markup language for creating web pages.</dd>

    <dt>CSS</dt>

    <dd>A stylesheet language for styling web pages.</dd>

</dl>
```



```html
<!DOCTYPE html>

<html>

<head>

    <title>Description List Example</title>

</head>

<body>

    <h1>Description List</h1>

    <dl>

        <dt>HTML</dt>

        <dd>A markup language for creating web pages.</dd>

        <dt>CSS</dt>

        <dd>A stylesheet language for styling web pages.</dd>

        <dt>JavaScript</dt>

        <dd>A programming language for creating interactive web pages.</dd>

    </dl>

</body>

</html>
```




- <dl>: Stands for "description list." It defines the start and end of the list.

- <dt>: Stands for "description term." Each <dt> represents a term.

- <dd>: Stands for "description definition." Each <dd> provides the definition of the term.

# Output

- HTML

  - A markup language for creating web pages.

- CSS

  - A stylesheet language for styling web pages.

- JavaScript

  - A programming language for creating interactive web pages.

Combining Lists

You can combine ordered, unordered, and description lists to create complex layouts.

# Example

```html
<!DOCTYPE html>

<html>

<head>

    <title>Combining Lists Example</title>

</head>

<body>

    <h1>Combining Lists</h1>

    <ul>

        <li>HTML

            <ol>

                <li>Syntax</li>

                <li>Elements</li>

                <li>Attributes</li>

            </ol>

        </li>

        <li>CSS

            <dl>

                <dt>Selectors</dt>

                <dd>Patterns used to select elements.</dd>

                <dt>Properties</dt>

                <dd>Characteristics to style elements.</dd>

            </dl>

        </li>

    </ul>

</body>

</html>
```




- A combination of unordered, ordered, and description lists can create intricate layouts.

- Nesting lists of different types allows for structured and comprehensive content.





### Practice Examples
# Practice Example 1: Creating an Unordered List

Create an HTML file named grocery-list.html and list your grocery items.

# Practice Example 2: Creating an Ordered List

Create an HTML file named to-do-list.html and list your tasks for the day.

# Practice Example 3: Creating a Description List

Create an HTML file named course-descriptions.html and describe some courses.

# Practice Example 4: Creating a Nested List

Create an HTML file named nested-list.html with nested lists of your favorite movies and books.

## Assignments

# Travel Itinerary:

   - Create an HTML file named itinerary.html.

   - Create an ordered list of places you plan to visit.

   - Under each place, create an unordered list of things to do there.


# Recipe List:

   - Create an HTML file named recipes.html.

   - Create a description list of recipes, where each term is a recipe name and each definition is a short description of the recipe.




# Personal Goals:

   - Create an HTML file named goals.html.

   - Create a nested list of your personal and professional goals.

   - Use an unordered list for personal goals and an ordered list for professional goals.




