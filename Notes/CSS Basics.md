# CSS Basics
# What is CSS?
Cascading Style Sheets (CSS) tell the browser how to display the text and other content that you write in HTML.
Note that CSS is case-sensitive so be careful with your capitalization.

CSS has been adopted by all major browsers and allows you to
control:
- color
- fonts
- positioning
- spacing
- sizing
- decorations
- transitions

### An Example of the following in a class
```html
<style>
.bigclass{
    color: red;
    font-size: 30px;
    font-family: sans-serif;
    padding: 20px;
    margin-bottom: 20px;
    border-style: dashed solid;
    text-align: left;

   }
</style>
```

## Difference between id/class
In the CSS, a class selector is a name preceded by a full stop (“.”) and an ID selector is a name preceded by a hash character (“#”).

So the CSS might look something like:
```css
#top {
      background-color: #ccc;
      padding: 20px
  }

  .intro {
      color: red;
      font-weight: bold;
  }
```
The HTML refers to the CSS by using the attributes id and class. It could look something like this:
```html

<div id="top">

  <h1>Chocolate curry</h1>

  <p class="intro">This is my recipe for making curry purely with chocolate</p>

  <p class="intro">Mmm mm mmmmm</p>

</div>
```
The difference between an ID and a class is that an ID can be used to identify one element, whereas a class can be used to identify more than one.

## Style / Colors
The style tag is used in an HTML DOC incase you don't have a separate DOC for CSS (which you should for readability)

**NOTE: YOU DO NOT HAVE TO USE THE STYLE TAG FOR CLASSES IF YOU HAVE A SEPRATE DOC FOR CSS**
```html
<style>
  h2 {
    color: red;
  }
</style>
```
This would in turn make all h2 elements in your HTML DOC "red"

You can also make the entire, or certain portions, of the DOC's background color change like this:
```html
<background-color: red;>
```
### CSS Style Blocks
A style begins with a "." (fullstop) then the selector. Under the selector, declare what you would like it to do.
```html
<style>
  .blue-text {
    color: blue;
  }
</style>
```
This would make a .blue-text variable that can turn objects blue when applied
```html
<style>
  .red-text {
    color: red;
    font-family: Helvetica;
    font-size: 20%;
  }
</style>
<!-- This is an example of a Style class with multiple styles. This could be applied to the "p" tag for example: -->
  <p class="red-text"> </p>
```
### Inline styling
Or if you don't to assign a new class, you can change the color directly using the "style" tag
```html
  <p style="color: red"> This text is red </p>
```
### Hexcode
To review, hex codes use 6 hexadecimal digits to represent colors, two each for red (R), green (G), and blue (B) components.

From these three pure colors (red, green, and blue), we can vary the amounts of each to create over 16 million other colors!

For example, orange is pure red, mixed with some green, and no blue. In hex code, this translates to being #FFA500.

The digit 0 is the lowest number in hex code, and represents a complete absence of color.

The digit F is the highest number in hex code, and represents the maximum possible brightness.
**Example:** *Orange = #FFA500*
### RGB mixing
Just like with hex code, you can mix colors in RGB by using combinations of different values.
```html
| Color  | RGB                |
| ------ | ------------------ |
| blue   | rgb(0, 0, 255)     |
| red    | rgb(255, 0, 0)     |
| orchid | rgb(218, 112, 214) |
| sienna | rgb(160, 82, 45)   |
```
## Importing a Google font
Google Fonts is a free library of web fonts that you can use in your CSS by referencing the font's URL.

To import a Google Font, you can copy the font(s) URL from the Google Fonts library and then paste it in your HTML. For this example, we'll import the Lobster font.
**(before the opening style element):**
```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
```
Family names are case-sensitive and need to be wrapped in quotes if there is a space in the name. For example, you need quotes to use the "Open Sans" font, but not to use the Lobster font.

## Fonts
There are several default fonts that are available in all browsers. These generic font families include monospace, serif and sans-serif

When one font isn't available, you can tell the browser to "degrade" to another font.
```css
  p {
    font-family: Helvetica, sans-serif;
  }

```
It is good etiquette to always have a font family to fall back on.
## Image Sizing
CSS has a property called width that controls an element's width. Just like with fonts, we'll use px (pixels/percent) to specify the image's width.
```html
<style>
  .larger-image {
    width: 500px;
  }
</style>
OR
<img src="#" width=500px>
```
## Borders
CSS borders have properties like style, color and width.

For example, if we wanted to create a red, 5 pixel border around an HTML element, we could use this class:
```html
<style>
  .thin-red-border {
    border-color: red;
    border-width: 5px;
    border-style: solid;
  }
</style>
```
### Border Styling
Using the "border-radius" tag we can make circular borders
```html
<style>
  .thick-green-border {
  border-color: green;
    border-width: 10px;
    border-style: solid;
    border-radius: 30px;
  }
</style>
```
This output would be a thicker, green, circular, border.
## ID's
One cool thing about id attributes is that, like classes, you can tyle them using CSS.
However, an id is not reusable and should only be applied to **one** element. *An id also has a higher specificity (importance) than a class so if both are applied to the same element and have conflicting styles, the styles of the* **id** will be applied.
```css
  #example{
  	background-color: black;
  	font-size: 12%
  	font-weight: bold;
  }
```
## Padding, Margins, and Border
### Padding
all HTML elements are essentially little rectangles.

Three important properties control the space that surrounds each HTML element: padding, margin, and border.

An element's padding controls the amount of space between the **element's content** and its **border**.
~~(Larger)~~
```css
.red-box {
    background-color: crimson;
    color: #fff;
    padding: 20px;
  }
```
Sometimes you will want to customize an element so that it has different amounts of padding on each of its sides.

CSS allows you to control the padding of all four individual sides of an element with the *padding-top, padding-right, padding-bottom, and padding-left* properties.
```css
  .blue-box {
    background-color: blue;
    color: #fff;
    padding-top: 40px;
    padding-left: 40px;
    padding-right: 20px;
    padding-bottom: 20px;
  }
```
### Margin
*An element's margin controls the amount of **space** between an **element's border** and surrounding **elements**.*
~~(Smaller)~~
```css
 .blue-box {
    background-color: blue;
    color: #fff;
    padding: 20px;
    margin: 20px;
  }
```
If you set an element's margin to a negative value, the element will grow larger.
```css
 .blue-box {
    background-color: blue;
    color: #fff;
    padding: 20px;
    margin: -15px;
  }
```
### Clockwise Notation
Instead of specifying an element's *padding-top, padding-right, padding-bottom, and padding-left* **/** *margin-top, margin-right, margin-bottom, margin-left* properties individually, you can specify them all in one line, like this:
```html
<padding: 10px, 20px, 0px, 10px>
<margin: 20px, 0px, 15px, 0px>
```
### Auto margin
Another positioning technique is to center a block element horizontally. One way to do this is to set its margin to a value of auto.

This method works for images, too. Images are inline elements by default, but can be changed to block elements when you set the display property to block.
```HTML
<style>
  div {
    background-color: blue;
    height: 100px;
    width: 100px;
    margin: auto;
  }
</style>
<div></div>
```
This is the result:

![image](https://i.imgur.com/iqaE8ke.png)

## Attribute Selectors
You have been adding id or class attributes to elements that you wish to specifically style. These are known as ID and class selectors. There are other CSS Selectors you can use to select custom groups of elements to style.

Using the `[attr=value]` attribute selector to style a radio box
This selector matches and styles elements with a specific attribute value. For example, the below code changes the margins of all elements with the attribute type and a corresponding value of radio:
```css
  [type='radio'] {
    margin: 20px 0px 20px 0px;
  }
```
## Absolute vs Relative units
The two main types of length units are absolute and relative. Absolute units tie to physical units of length. For example, in and mm refer to inches and millimeters, respectively. Absolute length units approximate the actual measurement on a screen, but there are some differences depending on a screen's resolution. (This also includes pixels (px))

**Relative units**, such as *em, rem, or %* are relative to another length value. For example, em is based on the size of an element's font. If you use it to set the font-size property itself, it's relative to the parent's font-size
```css
. yellow box {
  background-color: yellow;
  margin: 20px, 40px, 20px, 40px;
  padding: 1.5em;
```
## Prioritization
Sometimes your HTML elements will receive multiple styles that conflict with one another. Example:
```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  .pink-text {
    color: pink;
  }
</style>
<body>
  <h1 class="pink-text"> Hello World!</h1>
</body>
```
What would this output? The h1 text will end up being pink as **classes override the body element declaration**

### What is the full priority list?

The list goes as follows *(Top having highest priority)*
- !important tag:
```html
  .pink-text {
    color: pink !important;
  }

 <h1 class="pink-text"> Hello </h1>
```
- Style tag
  ```css
  <h1 style="color: green;"> Hello </h1>
  ```
- ID's
  ```css
  #brown-text {
    color: brown;
  }
  <h1 id="brown-text"> Hello </h1>
```
- Classes
```css
  .pink-text {
    color: pink;
  }
  .blue-text{
    color: blue;
  }
<h1 class="pink-text blue-text">Hello World!</h1>
<!-- This output would be blue-->
```
(Note: It doesn't matter which order the classes are listed in the HTML element.
However, **the order of the class declarations in the "style" section is what is important**.The second declaration will always take precedence over the first. Because .blue-text is declared second, it overrides the attributes of .pink-text)
- Body
```html
<style>
  body {
    color: green;
  }
 .pink-text {
   color: pink;
  }
</style>
<h1 class="pink-text">Hello World!</h1>
<!-- This would return h1 as pink -->
```
The body tag is very general allowing for all previous tags to have priority over it. This is a general rule of thumb, the more broad, the less priority it will have.
### An example of priorities together
This is an example of the above priority list in action
```html
<style>
  body {
    background-color: black;
    font-family: monospace;
    color: green;
  }
  #orange-text {
    color: orange;
  }
  .pink-text {
    color: pink !important;
  }
  .blue-text {
    color: blue;
  }
</style>
<h1 id="orange-text" class="pink-text blue-text" style="color: white"> Hello World!</h1>
```
It will return this:

![image](https://i.imgur.com/eHrQd3g.png)

This is because the !important tag attached to the .pink-text class.

## CSS Variables
CSS Variables are a powerful way to change many CSS style properties at once by changing only one value.

To create a CSS variable, you just need to give it a name with **two hyphens in front of it and assign it a value** like this:
```css
  --penguin-skin: gray;
```
This will create a variable named --penguin-skin and assign it the value of gray. Now you can use that variable elsewhere in your CSS to change the value of other elements to gray.

### Fallback CSS value
When using your variable as a CSS property value, you can attach a fallback value that your browser will revert to if the given variable is invalid.

*(Note: This fallback is not used to increase browser compatibility, and it will not work on IE browsers. Rather, it is used so that the browser has a color to display if it cannot find your variable.)*
```css
  background: var(--penguin-skin, black);
```
## Improve Compatibility with Browser Fallbacks
When working with CSS you will likely run into browser compatibility issues at some point. This is why it's important to provide browser fallbacks to avoid potential problems.

When your browser parses the CSS of a webpage, it ignores any properties that it doesn't recognize or support.

This means that if you do want to provide a browser fallback, it's as easy as providing another more widely supported value immediately before your declaration. That way an older browser will have something to fall back on, while a newer browser will just interpret whatever declaration comes later in the cascade.
```css
<style>
  :root {
    --red-color: red;
  }
  .red-box {
    background: red;
    background: var(--red-color);
    height: 200px;
    width:200px;
  }
</style>
<div class="red-box"></div>
```
Pay close attention to the additonal background color declaration above our CSS variable, this keeps the browser from seleciting a default as we have a basic "background: red;".
  ## Inheriting CSS Variables / :root

```css
<style>
 :root {
  --main-bg-color: brown;
}
 element {
  background-color: var(--main-bg-color);
}
  }
</style>
```
The :root selector allows you to declare global CSS variables to be used throughtout the rest of our DOC. This way you can use the :root class variables to apply multiple changes to an element with one variable
```css
:root{
    --okay: red; margin: 20px; padding: 20%;
  }
body{
	background: var(--okay);
}
```
### Change a variable for a specific area
When you create your variables in :root they will set the value of that variable for the whole page.

You can then over-write these variables by setting them again within a specific element. Or with the **!important tag**.

![image](https://i.imgur.com/GTYoRoh.png)
Notice in the :root tag te --penguin-belly is declared as "pink" yet it turns white. Why? Because it is redeclared in the .penguin class.
##  Use a media query to change a variable
CSS Variables can simplify the way you use media queries.

For instance, when your screen is smaller or larger than your media query break point, you can change the value of a variable, and it will apply its style wherever it is used.
```css
<style>
:root {
  --penguin-size: 300px;
  --penguin-skin: gray;
  --penguin-belly: white;
  --penguin-beak: orange;
    }

  @media (max-width: 350px) {
    :root {
      --penguin-size: 200px;
      --penguin-skin: black;
      }
    }
</style>
```
This allows the :root declration to change based on size of the image. If it goes past the max, the `@media :root` will be followed instead.

For example: If the above code has a width lower than 350px, this will return.
![image](https://i.imgur.com/R6Np4fz.png)

Else...if the width is goes past the max of 350px, this will return.
![image](https://i.imgur.com/Apxjooi.png)

## Specificity
The most important aspect of CSS is **specificity.** The goal is to be able to specifically change the class of a *element even if it is nested within another  class.*
