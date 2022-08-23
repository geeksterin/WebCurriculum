- [What is CSS?](#what-is-css)
- [Syntax of CSS](#syntax-of-css)
    - [Selector](#selector)
    - [Declaration](#declaration)
    - [Properties](#properties)
    - [Property Value](#property-value)
- [Different types of selectors](#different-types-of-selectors)
    - [Element Selector](#element-selector)
    - [Id Selector](#id-selector)
    - [Class Selector](#class-selector)
- [Some Best practices to use css selectors](#some-best-practices-to-use-css-selectors)
- [Applying CSS to HTML](#applying-css-to-html)
    - [External StyleSheet](#external-stylesheet)
    - [Internal StyleSheet](#internal-stylesheet)
        - [NOTE](#note)
    - [Inline Styles](#inline-styles)
        - [NOTE](#note-1)
- [CSS colors](#css-colors)
    - [rgb() function in CSS](#rgb-function-in-css)
    - [RGBA Colors](#rgba-colors)
    - [CSS HEX Colors](#css-hex-colors)
- [Few CSS properties](#few-css-properties)
    - [color](#color)
    - [Syntax](#syntax)
    - [background-color](#background-color)
    - [Syntax](#syntax-1)

# What is CSS?
Like HTML, CSS is not a programming language. It's not a markup language either. CSS is a style sheet language. CSS is what you use to selectively style HTML elements. For example, this CSS selects paragraph text, setting the color to red:

```css
p {
  color: red;
}
```

# Syntax of CSS 

![Syntax](./Images/css-declaration-small.png)

The whole structure is called a ruleset. (The term ruleset is often referred to as just rule.) Note the names of the individual parts:

## Selector
This is the HTML element name at the start of the ruleset. It defines the element(s) to be styled (in this example, <p> elements). To style a different element, change the selector.

## Declaration
This is a single rule like color: red;. It specifies which of the element's properties you want to style.

## Properties
These are ways in which you can style an HTML element. (In this example, color is a property of the <p> elements.) In CSS, you choose which properties you want to affect in the rule.

## Property value
To the right of the property—after the colon—there is the property value. This chooses one out of many possible appearances for a given property. (For example, there are many color values in addition to red.)

Note the other important parts of the syntax:

1. Apart from the selector, each ruleset must be wrapped in curly braces. ({})
2. Within each declaration, you must use a colon (:) to separate the property from its value or values.
3. Within each ruleset, you must use a semicolon (;) to separate each declaration from the next one.
To modify multiple property values in one ruleset, write them separated by semicolons, like this:

```css
p {
  color: red;
  width: 500px;
  border: 1px solid black;
}
```

# Different types of selectors
There are many different types of selectors. The examples above use element selectors, which select all elements of a given type. But we can make more specific selections as well. Here are some of the more common types of selectors:

## Element selector 
Element selector: The element selector selects HTML elements based on the element name (or tag) for **example** p, h1, div, span, etc.

```css
h1 {
    color: red;
    font-size: 3rem;
}

p {
    color: white;
    background-color: gray;
}
```

## Id selector
The id selector uses the id attribute of an HTML element to select a specific element.

**Note:** An id of element is unique on a page to use id selector.

**Example:**
```css
#div-container{
    color: blue;
    background-color: gray;
}
```

## Class-selector
The class selector selects HTML elements with a specific class attribute.

To use class selector you must use ( . ) followed by class name in CSS. This rule will be applied to the HTML element with the class attribute “paragraph-class“

**Example**

```css
.paragraph-class {
    color:white;
    font-family: monospace;
    background-color: purple;
}
```

# Some Best practices to use css selectors

1. Use classes to select elements that are more specific, reusable and flexible than type selectors.
2. ID values can only be used once per page, so stick to using them for unique styles and global elements that are not repeated.


# Applying CSS to HTML
First, let's examine three methods of applying CSS to a document: with an external stylesheet, with an internal stylesheet, and with inline styles.

## External stylesheet
An external stylesheet contains CSS in a separate file with a .css extension. This is the most common and useful method of bringing CSS to a document. You can link a single CSS file to multiple web pages, styling all of them with the same CSS stylesheet.

You reference an external CSS stylesheet from an HTML ``<link>`` element:

```html
<!DOCTYPE html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <!-- bringing css -->
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>Hello Folks!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
```

## Internal stylesheet
An internal stylesheet resides within an HTML document. To create an internal stylesheet, you place CSS inside a ``<style>`` element contained inside the HTML ``<head>``.

The HTML for an internal stylesheet might look like this:

```html
<!DOCTYPE html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <!-- internal css -->
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Hello Folks!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
```

### NOTE

1. In some circumstances, internal stylesheets can be useful. For example, perhaps you're working with a content management system where you are blocked from modifying external CSS files.

2. But for sites with more than one page, an internal stylesheet becomes a less efficient way of working. To apply uniform CSS styling to multiple pages using internal stylesheets, you must have an internal stylesheet in every web page that will use the styling. The efficiency penalty carries over to site maintenance too. With CSS in internal stylesheets, there is the risk that even one simple styling change may require edits to multiple web pages.

## Inline styles
Inline styles are CSS declarations that affect a single HTML element, contained within a style attribute. The implementation of an inline style in an HTML document might look like this:

```html
<!DOCTYPE html>
<html lang="en-GB">
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
  </head>
  <body>
    <h1 style="background-color: yellow;border: 1px solid black;">Hello Folks!</h1>
    <p style="color:red;">This is my first CSS example</p>
  </body>
</html>
```

### NOTE

1. Avoid using CSS in this way, when possible. It is the opposite of a best practice. First, it is the least efficient implementation of CSS for maintenance. One styling change might require multiple edits within a single web page. Second, inline CSS also mixes (CSS) presentational code with HTML and content, making everything more difficult to read and understand. Separating code and content makes maintenance easier for all who work on the website.

2. There are a few circumstances where inline styles are more common. You might have to resort to using inline styles if your working environment is very restrictive. For example, perhaps your CMS only allows you to edit the HTML body. You may also see a lot of inline styles in HTML email to achieve compatibility with as many email clients as possible.

# CSS Colors

## rgb() function in CSS
RGB is a combination of three colors (Red, Green and Blue) that is used in all computer systems for colored display. As we know, these are the basic colors and by combining them we can obtain any color which is visible in the color spectrum.

In CSS, these colors are defined in the form of a function rgb(): (red, green, blue). The range of all these colors is defined from 0 to 255 defines the intensity of a color, and we can change the colors by changing these values. The intensity of these colors is well defined in the given example.

**Example**

```css
rgb (0, 255, 0)
```
This combination returns the green color because it has the highest intensity and the other two colors have 0 intensity.

By changing the intensities of all three colors we get the different colors such as

```
rgb(255, 255, 255) displays the white color
and rgb(0, 0, 0) gives the black color.
```

## RGBA Colors
In CSS RGBA is also a format to display colors with the extension of Alpha. The structure of this color function is given below.

rgba(Red, Green, Blue, Alpha)
In this function, an Alpha is used to express the opacity of a color. In CSS opacity property is used to set the transparency of a color and its range lies between 0.0 to 1.0, where 0.0 represents the fully transparent and 1.0 represents the fully opaque. You will better understand from the given example.

```html
<!DOCTYPE html>
<html>
<head>
</head>
<body>
<h1 style="background-color:rgba(0,255,0,0.0);">Green</h1>
<h1 style="background-color:rgba(0,255,0,0.25);">Green</h1>
<h1 style="background-color:rgba(0,255,0,0.5);">Green</h1>
<h1 style="background-color:rgba(0,255,0,0.75)">Green</h1>
<h1 style="background-color:rgba(0,255,0,1.0)">Green</h1>
</body>
</html>
```

![color](./Images/Color-in-CSS-2.png)

In the above given example, we set the value of alpha from 0.0 (fully transparent) to 1.0 (fully opaque) and you can see the difference in intensity of transparency.

## CSS HEX Colors
In CSS colors can also be specified with hexadecimal values, it is just another way to represent colors. In CSS, it is the most common way to specify a color by using hexadecimal values with an “#” sign such as #RRGGBB. Whereas, R, G, B are the codes for red, green and blue, respectively.

Hexadecimal numbers with the combination of 0-9 and A-F are used to represent a color in CSS. Some examples of basic HEX colors are given below:

```
#ffffff: it represents the white color and
#000000: it represents the black color.
```

# Few CSS properties

## color
The color CSS property sets the foreground color value of an element's text and text decorations, and sets the currentcolor value. currentcolor may be used as an indirect value on other properties and is the default for other color properties, such as border-color.

## Syntax

```css
/* Keyword values */
color: currentcolor;

/* <named-color> values */
color: red;
color: orange;
color: tan;
color: rebeccapurple;

/* <hex-color> values */
color: #090;
color: #009900;
color: #090a;
color: #009900aa;

/* <rgb()> values */
color: rgb(34, 12, 64, 0.6);
color: rgb(34.0 12 64 / 60%);
```

The color property is specified as a single ``<color>`` value.

Note that the value must be a uniform color. It can't be a ``<gradient>``, which is actually a type of ``<image>``.

Values
``<color>``
Sets the color of the textual and decorative parts of the element.

## background-color
The background-color CSS property sets the background color of an element.

## Syntax

```css
/* Keyword values */
background-color: red;
background-color: indigo;

/* Hexadecimal value */
background-color: #bbff00;    /* Fully opaque */
background-color: #bf0;       /* Fully opaque shorthand */
background-color: #11ffee00;  /* Fully transparent */
background-color: #1fe0;      /* Fully transparent shorthand  */
background-color: #11ffeeff;  /* Fully opaque */
background-color: #1fef;      /* Fully opaque shorthand  */

/* RGB value */
background-color: rgb(255, 255, 128);        /* Fully opaque */
background-color: rgba(117, 190, 218, 0.5);  /* 50% transparent */
```