# What is Applied Visual Design?
Visual Design in web development is a broad topic. It combines typography, color theory, graphics, animation, and page layout to help deliver a site's message. The definition of good design is a well-discussed subject, with many books on the theme.

At a basic level, most web content provides a user with information. The visual design of the page can influence its presentation and a user's experience. In web development, HTML gives structure and semantics to a page's content, and CSS controls the layout and appearance of it.

This section covers some of the basic tools developers use to create their own visual designs.
# Contents
- Text Alignment
- Adjusting Width/Height of an element
- Styling Text
- hr tag
- box-shadow tag
- Opacity of an element
- text-transform tag
- color theory
- transform property
- css positioning
- float

## Text Alignment
Text is often a large part of web content. CSS has several options for how to align it with the text-align property.
- `<text-align: justify;>` causes all lines of text except the last line to meet the left and right edges of the line box.
- `<text-align: center;>` centers the text.
- `<text-align: right;>` right-aligns the text.
- `<text-align: left;>`  left-aligns the text. *(the default)*
```css
<style>
    h4{
    text-align: center;
}
```

## Adjust the weight/height of an Element Using the width/height Property
You can specify the width/height of an element using the width/height property in CSS. Values can be given in relative length units (such as em), absolute length units (such as px), or as a percentage of its containing parent element
```css
img {
  width: 220px;
}
```
```css
img {
  height: 20px;
}
```
## Styling Text
There are multiple ways to style text. Here's a list of a few
- `<strong>` This tag makes text bold
- `<u>` This tag makes text underlined
- `<em>` This tag makes text italicized
- `<s>` This tag strikes through text

### Strong tag (bold text)
To make text bold, you can use the strong tag. With the strong tag, the browser applies the CSS of font-weight: bold; to the element.
```html
<p> Hey lets go for a walk <strong>tonight</strong> okay </p>
```
### Underline tag (underline text)
To underline text, you can use the u tag. With the u tag, the browser applies the CSS of text-decoration: underline; to the element.
```html
<p> Hey lets go <u>tomorrow</u> instead
```
### Emphasize tag (italicize text)
To emphasize text, you can use the em tag. This displays text as italicized, as the browser applies the CSS of font-style: italic; to the element.
```html
<p> Okay <em>well go</em> tomorrow</p>
```
### Strikethrough tag (line through text)
To strikethrough text, which is when a horizontal line cuts across the characters, you can use the s tag. With the s tag, the browser applies the CSS of text-decoration: line-through; to the element.
```html
<p> Hey lets go for a walk <s>tonight</s></p>
```
## Create a Horizontal Line Using the hr Element
You can use the hr tag to add a horizontal line across the width of its containing element. This can be used to define a change in topic or to visually separate groups of content.
```html
<h3>Google </h3>
<hr>
<p>Firefox </p>
```
This is what a `<hr>` tag looks like in use

![image](https://i.imgur.com/US49n6Z.png)
 ## Adjust the background-color Property of Text

 Instead of adjusting your overall background or the color of the text to make the foreground easily readable, you can add a background-color to the element holding the text you want to emphasize. This challenge uses rgba() instead of hex codes or normal rgb().

 >rgba stands for:
- r = red
- g = green
- b= blue
- a= alpha/level or opacity

```css
h4{
 background-color: rgba(45, 45, 45, 0.1);
}
```
## Add a box-shadow to a Card-like Element
The box-shadow property applies one or more shadows to an element.

The box-shadow property takes values for

    offset-x (how far to push the shadow horizontally from the element),
    offset-y (how far to push the shadow vertically from the element),
    blur-radius,
    spread-radius and
    color, in that order.

The blur-radius and spread-radius values are optional.

Multiple box-shadows can be created by using commas to separate properties of each box-shadow element.

Here's an example of the CSS to create multiple shadows with some blur, at mostly-transparent black colors:
```css
box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
```
This is an example of the output **BEFORE** the above code

![image](https://i.imgur.com/cprc32B.png)

This is an example of the out **AFTER** the above code

![image](https://i.imgur.com/NeyLbSo.png)

Its very slight, but the second card has a slight shadow around the edge that makes it look nicer.
## Decrease the Opacity of an Element
The opacity property in CSS is used to adjust the opacity, or conversely, the transparency for an item.
-  A value of 1 is opaque, which isn't transparent at all.
- A value of 0.5 is half see-through.
- A value of 0 is completely transparent.
```css
.link{
	text-align: left;
    color: black;
    opacity: 0.7;
}
```
**Note:** *The value given will apply to the entire element, whether that's an image with some transparency, or the foreground and background colors for a block of text.*

## Altering Text
Applied Visual Design allows us too use these commands to alter text
- `text-transform`
- `font-size`
- `font-weight`
- `line-height`

### text-transform
The text-transform property in CSS is used to change the appearance of text. It's a convenient way to make sure text on a webpage appears consistently, without having to change the text content of the actual HTML elements.

The following table shows how the different text-transform values change the example text "Transform me".

Value : Result

- lowercase : "transform me"
- uppercase :	"TRANSFORM ME"
- capitalize :	"Transform Me"
- initial :	Use the default value
- inherit :	Use the text-transform value from the parent element
- none :	Default: Use the original text

```css
h4 {
	text-align: center;
    background-color: rgba(45, 45, 45, 0.1);
    padding: 10px;
    font-size: 27px;
    text-transform: uppercase;
}
```
### font-size
The font-size property is used to specify how large the text is in a given element.
```css
.bigtext{
  font-size: 48px;
}
```
### font-weight
```CSS
.boldtext{
  font-weight: 400;
}
```
## line-height
CSS offers the line-height property to change the height of each line in a block of text. As the name suggests, it changes the amount of vertical space that each line of text gets.
```CSS
  p{
    line-height: 25px;
  }
```
Before:

![image](https://i.imgur.com/5qZNgsI.png)

After:

![image](https://i.imgur.com/XNRn63l.png)

## Pseudo-Classes
A pseudo-class is a keyword that can be added to selectors, in order to select a specific state of the element.

For example, the styling of an anchor tag can be changed for its hover state using the :hover pseudo-class selector. Here's the CSS to change the color of the anchor tag to red during its hover state:
```css
a:hover{
  color: orange;
}
```
As you can see here, using the pseudo class `hover` we're able to change the hover color of an `a` tag orange.

![image](https://i.imgur.com/4CqqCep.png)

## Understanding and Using CSS Positions
CSS treats each HTML element as its own box, which is usually referred to as the CSS Box Model. Block-level items automatically start on a new line (think headings, paragraphs, and divs) while inline items sit within surrounding content (like images or spans). The default layout of elements in this way is called the normal flow of a document, but CSS offers the position property to override it.

The CSS offsets of top or bottom, and left or right tell the browser how far to offset an item relative to where it would sit in the normal flow of the document. You're offsetting an element away from a given spot, which moves the element away from the referenced side **(effectively, the opposite direction)**

![image](https://i.imgur.com/tnwPQMA.png)

*Remember think of `top or bottom, and left or right` as `pixels away from top or bottom, and pixels away from left or right`*

#### Commands to remember
- `top:`
- `bottom:`
- `left:`
- `right:`
- `z-index` *(controls the vertical stacking order of elements, and take only numbered integers. The higher the integer, the more forward this element is.)*

### Relative Positioning
When the position of an element is set to relative, it allows you to specify how CSS should move it relative to its current position in the normal flow of the page. It pairs with the CSS offset properties of left or right, and top or bottom. These say how many pixels, percentages, or ems to move the item away from where it is normally positioned.

Here is an example:
```HTML
<style>
  h2 {
    position: relative;
    top:15px;
  }
</style>
<body>
  <h1>On Being Well-Positioned</h1>
  <h2>Move me!</h2>
  <p>I still think the h2 is where it normally sits.</p>
</body>
```

Output **without** `relative position`

![image](https://i.imgur.com/29UUpP8.png)

Output **with** `relative position`

![image](https://i.imgur.com/4cfxB5V.png)

**Changing an element's position to relative does not remove it from the normal flow - other elements around it still behave as if that item were in its default position.**

*Note: Positioning gives you a lot of flexibility and power over the visual layout of a page. It's good to remember that no matter the position of elements, the underlying HTML markup should be organized and make sense when read from top to bottom.*

![image](https://i.imgur.com/CHiTpMb.png)

### Absolute Positioning

The next option for the CSS position property is absolute, which locks the element in place relative to its parent container. Unlike the relative position, **this removes the element from the normal flow of the document, so surrounding items ignore it.** The CSS offset properties (top or bottom and left or right) are used to adjust the position.

One nuance with absolute positioning is that it will be **locked relative to its closest positioned ancestor.** If you forget to add a position rule to the parent item, (this is typically done using position: relative;), the browser will keep looking up the chain and ultimately default to the body tag.
```HTML
<style>
  #searchbar {
    position: absolute;
    top: 50px;
    right: 50px;
  }
  section {
    position: relative;
  }
</style>
<body>
  <h1>Welcome!</h1>
  <section>
    <form id="searchbar">
      <label for="search">Search:</label>
      <input type="search" id="search" name="search">
      <input type="submit" name="submit" value="Go!">
    </form>
  </section>
</body>
```
Here's the output **without** absolute positioning.

![image](https://i.imgur.com/HHIT92V.png)

Here's the output **with** absolute positioning.

![image](https://i.imgur.com/DMLz7EK.png)

*Note: from the example code above, that absolute positioning is locked to the* **nearest** *positioned ancestor*.

![image](https://i.imgur.com/3Bkt9zT.png)

### Fixed Positioning
Similar to position absolute, an element that has fixed position is **taken out of the document flow.**

*The two major difference is: elements with position fixed is always positioned relative to the browser window / body (default).*

*And the difference between the fixed and absolute positions is that an element with a fixed position won't move when the user scrolls.*


![image](https://i.imgur.com/erp7EK6.png)

### z-index Property
When elements are positioned to overlap (i.e. using position: absolute | relative | fixed | sticky), the element coming later in the HTML markup will, by default, appear on the top of the other elements.

However, the z-index property can specify the order of how elements are stacked on top of one another. It must be an integer (i.e. a whole number and not a decimal), and higher values for the z-index property of an element move it higher in the stack than those with lower values.

```HTML
<style>
  div {
    width: 60%;
    height: 200px;
    margin-top: 20px;
  }

  .first {
    background-color: red;
    position: absolute;
    z-index: 2;

  }
  .second {
    background-color: blue;
    position: absolute;
    left: 40px;
    top: 50px;
    z-index: 1;
  }
</style>

<div class="first"></div>
<div class="second"></div>
```
**Note the `z-index` between the first and second class**

Output of above code

![image](https://i.imgur.com/cbqUoYi.png)

*The red box overlaps the blue box because of the `z-index` value*

### Static
All positions are static by default. Meaning they take up the appropriate amount of space they are supposed to take up. Its the default positioning value and every element will use this value, unless otherwise stated.

## Float property

### How floated elements are positioned
The next positioning tool does not actually use position, but sets the float property of an element. **Floating elements are removed from the normal flow of a document and pushed to either the left or right of their containing parent element.** It's commonly used with the width property to specify how much horizontal space the floated element requires.

**As mentioned above, when an element is floated, it is taken out of the normal flow of the document (though still remaining part of it).** It is shifted to the left, or right, until it touches the edge of its containing box, or another floated element.
```HTML
<style>
section {
  border: 1px solid blue;
  width: 30%;
  float: left;
}

div {
  margin: 5px;
  width: 50px;
  height: 150px;
}

.left {
  float: left;
  background: pink;
}

.right {
  float: right;
  background: cyan;
}
</style>
<section>
  <div class="left">1</div>
  <div class="right">3</div>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
  </p>
</section>
```
What this would output **without** the float values

![image](https://i.imgur.com/6iRSKEj.png)

This is the output **with** the float values

![image](https://i.imgur.com/QwxVldg.png)

*Note: A floated element is at least as tall as it's tallest nested floated children. We gave the parent width: 30% and floated it to ensure it is tall enough to encompass it's floated children, and to make sure it takes up the width of the parent so we don't have to clear it's adjacent sibling.*

*example if the `section` had no `float` value*

![image](https://i.imgur.com/KnpeX0D.png)

## Color theory
Color theory and its impact on design is a deep topic and only the basics are covered in the following challenges. On a website, color can draw attention to content, evoke emotions, or create visual harmony.

When two colors are opposite each other on the color wheel, they are called complementary colors. They have the characteristic that if they are combined, they "cancel" each other out and create a gray color. However, when placed side-by-side, these colors appear more vibrant and produce a strong visual contrast.

Some examples of complementary colors with their hex codes are:

    red (#FF0000) and cyan (#00FFFF)
    green (#00FF00) and magenta (#FF00FF)
    blue (#0000FF) and yellow (#FFFF00)

### Tertiary colors
Tertiary colors are the result of combining a primary color with one of its secondary color neighbors. For example, within the RGB color model, red (primary) and yellow (secondary) make orange (tertiary). This adds six more colors to a simple color wheel for a total of twelve.

There are various methods of selecting different colors that result in a harmonious combination in design. One example that can use tertiary colors is called the split-complementary color scheme. This scheme starts with a base color, then pairs it with the two colors that are adjacent to its complement. The three colors provide strong visual contrast in a design, but are more subtle than using two complementary colors.

Here are three colors created using the split-complement scheme:
```html
| color  | hexcode |
| ------ | ------- |
| Orange | #FF7F00 |
| Cyan   | #00FFFF |
| Raspberry | #FF007F |
```
![image](https://i.imgur.com/o3x9Dvq.png)

*Note: Do not overuse complementary colors as it can become jarring. Allow one of your complementary colors to be dominant while the rest can complement the dominant color.*

### Adjusting the Hue
Colors have several characteristics including hue, saturation, and lightness.
The `hsl()` lets you take advantage of a colors three differenct aspects.

- Hue is what people generally think of as 'color'. If you picture a spectrum of colors starting with red on the left, moving through green in the middle, and blue on right, the hue is where a color fits along this line. In hsl(), hue uses a color wheel concept instead of the spectrum, where the angle of the color on the circle is given as a value between 0 and 360.

- Saturation is the amount of gray in a color. A fully saturated color has no gray in it, and a minimally saturated color is almost completely gray. This is given as a percentage with 100% being fully saturated.

- Lightness is the amount of white or black in a color. A percentage is given ranging from 0% (black) to 100% (white), where 50% is the normal color.

Here are some examples of basic colors using the `hs1` command
```html
| color   | hsl                 |
| ------- | ------------------- |
| red     | hsl(0, 100%, 50%)   |
| yellow  | hsl(60, 100%, 50%)  |
| green   | hsl(120, 100%, 50%) |
| cyan    | hsl(180, 100%, 50%) |
| blue    | hsl(240, 100%, 50%) |
| magenta | hsl(300, 100%, 50%) |
```
```CSS
.green {
  background-color: hsl(120, 100%, 50%);
}

.cyan {
  background-color: hsl(180, 100%, 50%);
}

.blue {
  background-color: hsl(240, 100%, 50%);
}
```

![image](https://i.imgur.com/A19qeDk.png)

### Create a Gradual CSS Linear Gradient
Applying a color on HTML elements is not limited to one flat hue. CSS provides the ability to use color transitions, otherwise known as gradients, on elements. This is accessed through the background property's linear-gradient() function. Here is the general syntax:

`background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);`

The first argument specifies the direction from which color transition starts - it can be stated as a degree, where 90deg makes a vertical gradient and 45deg is angled like a backslash. The following arguments specify the order of colors used in the gradient.
```HTML
<style>
  div {
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin: 50px auto;
    background: linear-gradient(35deg, #CCFFFF, #FFCCCC);
  }
</style>

<div></div>
```
This will output:

![image](https://i.imgur.com/sg87dma.png)

### Using linear gradient to make a striped element
The repeating-linear-gradient() function is very similar to linear-gradient() with the major difference that it repeats the specified gradient pattern. repeating-linear-gradient() accepts a variety of values

```HTML
<style>

  div{
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin:  50 auto;
    background: repeating-linear-gradient(
      90deg,
      yellow 0px,
      blue 40px,
      green 40px,
      red 80px
    );
  }

</style>

<div></div>
```
In the example demonstrated in the code editor, the gradient starts with the color yellow at 0 pixels which blends into the second color blue at 40 pixels away from the start. Since the next color stop is also at 40 pixels, the gradient immediately changes to the third color green, which itself blends into the fourth color value red as that is 80 pixels away from the beginning of the gradient.

![image](https://i.imgur.com/NH2vsy9.png)

For this example, it helps to think about the color stops as pairs where every two colors blend together.

`0px [yellow -- blend -- blue] 40px [green -- blend -- red] 80px`

If every two color stop values are the same color, the blending isn't noticeable because it's between the same color, followed by a hard transition to the next color, so you end up with stripes.

```HTML
<style>

  div{
    border-radius: 20px;
    width: 70%;
    height: 400px;
    margin:  50 auto;
    background: repeating-linear-gradient(
      45deg,
      yellow 0px,
      yellow 40px,
      black 40px,
      black 80px
    );
  }

</style>

<div></div>
```
![image](https://i.imgur.com/xycRC0K.png)

## Create Texture by Adding a Subtle Pattern as a Background Image
One way to add texture and interest to a background and have it stand out more is to add a subtle pattern. The key is balance, as you don't want the background to stand out too much, and take away from the foreground. The `background` property supports the `url()` function in order to link to an image of the chosen texture or pattern. The link address is wrapped in quotes inside the parentheses.
```html
<style>
  body {
    background: url(https://cdn-media-1.freecodecamp.org/imgr/MJAkxbh.png)
  }
</style>
```

![image](https://cdn-media-1.freecodecamp.org/imgr/MJAkxbh.png)

This small image with a pattern, used as a background, adds a subtle texture to catch a users eye without it being so strong it takes away from the rest of the document

## Transform Scale Property
To change the scale of an element, CSS has the transform property, along with its scale() function.
```HTML
<style>
  .ball {
    width: 40px;
    height: 40px;
    margin: 50 auto;
    position: fixed;
    background: linear-gradient(
      35deg,
      #ccffff,
      #ffcccc
    );
    border-radius: 50%;
  }
  #ball1 {
    left: 20%;
  }
  #ball2 {
    left: 65%;
    transform: scale(1.5);
  }
</style>

<div class="ball" id= "ball1"></div>
<div class="ball" id= "ball2"></div>
```
This code gives us two balls. One has no transform scaling, while the other one has a scaling of 1.5. Notice the difference.

![image](https://i.imgur.com/xNREqQ8.png)

### Scale an Element on Hover
The transform property has a variety of functions that let you scale, move, rotate, skew, etc., your elements. When used with **pseudo-classes** such as `:hover` that specify a certain state of an element, the transform property can easily add interactivity to your elements.
```HTML
<style>
  div {
    width: 70%;
    height: 100px;
    margin:  50px auto;
    background: linear-gradient(
      53deg,
      #ccfffc,
      #ffcccf
    );
  }
  div:hover{
    transform: scale(1.1);
  }
  body{
    background: black;
  }
</style>

<div></div>
```
Here's an example of the `:hover` pseudo class in action:

![image](https://i.imgur.com/loZdIdo.png)

![image](https://i.imgur.com/hgpXHXQ.png)

The `:hover` `transform` scaling allows this `div` to increase in scaling when hovered over

### Skew an Element Along the X-Axis using transform
The next function of the transform property is `skewX()`, which skews the selected element along its X (horizontal) axis by a given degree.
```HTML
<style>
  div {
    width: 70%;
    height: 100px;
    margin:  50px auto;
  }
  #top {
    background-color: red;
  }
  #bottom {
    background-color: blue;
    transform: skewX(-32deg);

  }
</style>

<div id="top"></div>
<div id="bottom"></div>
```
Notice the `skewX()` between ID top and bottom and realize the difference.

![image](https://i.imgur.com/OAOIDsM.png)

### Skew an Element Along the Y-Axis using transform
Given that the `skewX()` function skews the selected element along the X-axis by a given degree, it is no surprise that the `skewY()` property skews an element along the Y (vertical) axis.
```html
<style>
  div {
    width: 70%;
    height: 100px;
    margin: 50px auto;
  }
  #top {
    background-color: red;
    transform: skewY(-20deg);

  }
  #bottom {
    background-color: blue;
    transform: skewX(24deg);
  }
</style>

<div id="top"></div>
<div id="bottom"></div>
```
Notice the `skewY()` between ID top and bottom and see the differnce.

![image](https://i.imgur.com/G5RKXsx.png)
