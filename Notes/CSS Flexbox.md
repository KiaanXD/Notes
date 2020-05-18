# CSS Flexbox

## Introduction to CSS Flexbox
A website's User Interface ("UI") has two components. First, there are the visual elements, such as colors, fonts, and images. Second, there is the placement or positioning of those elements. In Responsive Web Design, a UI layout must accommodate many different browsers and devices accessing the content.

CSS3 introduced Flexible Boxes, or flexbox, to create page layouts for a dynamic UI. It is a layout mode that arranges elements in a predictable way for different screen sizes and browsers. While somewhat new, all popular modern browsers support flexbox. This section covers how to use flexbox and the different layout options it offers.

## Using `display: flex`

### Defining a `flex` container
Placing the CSS property display: flex; on an element allows you to use other flex properties to build a responsive page.

This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.
```html
<style>
  #box-container {
    height: 500px;
    display: flex;

  }

  #box-1 {
    background-color: dodgerblue;
    width: 50%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 50%;
    height: 50%;
  }
</style>
<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
Here's the output of the above code:

![image](https://i.imgur.com/w3uqOsK.png)

Here's what the output would be **without** `display: flex;`

![image](https://i.imgur.com/vePSgjI.png)

### Use the `flex-direction` Property to Make a Row
Adding `display: flex` to an element turns it into a flex container. This makes it possible to align any children of that element into rows or columns.

You do this by adding the `flex-direction` property to the parent item and setting it to row or column. Creating a row will align the children horizontally, and creating a column will align the children vertically.

Other options for `flex-direction` are `row-reverse` and `column-reverse`.

*(Note: The default value for the flex-direction property is row.)*
```html
<style>
  #box-container {
    display: flex;
    height: 500px;
    flex-direction: row-reverse;

  }
  #box-1 {
    background-color: dodgerblue;
    width: 50%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 50%;
    height: 50%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
Here is an output of the above code:

![image](https://i.imgur.com/uTo5QT0.png)

**(Note the `flex-direction: row-reverse` as this will keep the flexed elements in a row but reverse the order)**

Here's the output **without** `flex-direction: row-reverse;`

![image](https://i.imgur.com/w3uqOsK.png)

### Use the `flex-direction` Property to Make a Column
Adding `display: flex` to an element turns it into a flex container. This makes it possible to align any children of that element into rows or columns.

You do this by adding the `flex-direction` property to the parent item and setting it to row or column. Creating a column will align the children vertically, and creating a row will align the children horizontally.
```html
<style>
  #box-container {
    display: flex;
    height: 500px;
    flex-direction: column;

  }
  #box-1 {
    background-color: dodgerblue;
    width: 50%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 50%;
    height: 50%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
The above code will output:

![image](https://i.imgur.com/11JFmY7.png)

## Align Elements Using the `justify-content`, `align-items`, `flex-wrap` Property

### Spacing items with the `justify-content` Property
Sometimes the flex items within a flex container do not fill all the space in the container. It is common to want to tell CSS how to align and space out the flex items a certain way.

Fortunately, the `justify-content` property has several options to do this. But first, there is some important terminology to understand before reviewing those options.

![image](https://www.w3.org/TR/css-flexbox-1/images/flex-direction-terms.svg)

Recall that setting a flex container as a row places the flex items side-by-side from left-to-right. A flex container set as a column places the flex items in a vertical stack from top-to-bottom. For each, the direction the flex items are arranged is called the main axis. For a row, this is a horizontal line that cuts through each item. And for a column, the main axis is a vertical line through the items.

There are several options for how to space the flex items along the line that is the main axis. One of the most commonly used is `justify-content: center;`, which aligns all the flex items to the center inside the flex container. Others options include:
- `flex-start`: aligns items to the start of the flex container. For a row, this pushes the items to the left of the container. For a column, this pushes the items to the top of the container. This is the default alignment if no justify-content is specified.
- `flex-end`: aligns items to the end of the flex container. For a row, this pushes the items to the right of the container. For a column, this pushes the items to the bottom of the container.
- `space-between`: aligns items to the center of the main axis, with extra space placed between the items. The first and last items are pushed to the very edge of the flex container. For example, in a row the first item is against the left side of the container, the last item is against the right side of the container, then the remaining space is distributed evenly among the other items.
- `space-around`: similar to `space-between` but the first and last items are not locked to the edges of the container, the space is distributed around all the items with a half space on either end of the flex container.
- `space-evenly`: Distributes space evenly between the flex items with a full space at either end of the flex container

```html
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 500px;
    justify-content: ;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 25%;
    height: 100%;
  }

  #box-2 {
    background-color: orangered;
    width: 25%;
    height: 100%;
  }
</style>
<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
Use the above code to see references of each type of `justify-content`

**`justify-content: flex-start;` (default)**

![image](https://i.imgur.com/fr19ekS.png)

`justify-content: flex-end;`

![image](https://i.imgur.com/bMYOlkS.png)

`justify-content: space-between;`

![image](https://i.imgur.com/fMtBrrM.png)

`justify-content: space-around;`

![image](https://i.imgur.com/Tof5PyU.png)

`justify-content: space-evenly;`

![image](https://i.imgur.com/dGbs2Fu.png)

`justify-content: center;`

![image](https://i.imgur.com/ywHRAo5.png)

### Align Elements Using the `align-items` Property
The `align-items` property is similar to `justify-content`. Recall that the `justify-content` property aligned flex items along the main axis. For rows, the main axis is a horizontal line and for columns it is a vertical line.

Flex containers also have a **cross axis** which is the opposite of the main axis. For rows, the cross axis is vertical and for columns, the cross axis is horizontal.

CSS offers the `align-items` property to align flex items along the cross axis. For a row, it tells CSS how to push the items in the entire row up or down within the container. And for a column, how to push all the items left or right within the container.

The different values available for `align-items` include:
- `flex-start`: aligns items to the start of the flex container. For rows, this aligns items to the top of the container. For columns, this aligns items to the left of the container.
- `flex-end`: aligns items to the end of the flex container. For rows, this aligns items to the bottom of the container. For columns, this aligns items to the right of the container.
- `center`: align items to the center. For rows, this vertically aligns items (equal space above and below the items). For columns, this horizontally aligns them (equal space to the left and right of the items).
- `stretch`: stretch the items to fill the flex container. For example, rows items are stretched to fill the flex container top-to-bottom. *(This is the default value if no align-items value is specified.)*
- `baseline`: align items to their baselines. Baseline is a text concept, think of it as the line that the letters sit on.

```html
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 500px;
    align-items: ;

  }
  #box-1 {
    background-color: dodgerblue;
    width: 200px;
    font-size: 24px;
  }

  #box-2 {
    background-color: orangered;
    width: 200px;
    font-size: 18px;
  }
</style>

<div id="box-container">
  <div id="box-1"><p>Hello</p></div>
  <div id="box-2"><p>Goodbye</p></div>
</div>
```
Use the above code to see references of each type of `align-items`

`align-items: stretch;` **(default value if no `align-items` value is specified)**

![image](https://i.imgur.com/kb11ur1.png)

`align-items: flex-start;`

![image](https://i.imgur.com/86yCOM6.png)

`align-items: flex-end;`

![image](https://i.imgur.com/EJU5zur.png)

`align-items: center;`

![image](https://i.imgur.com/Vegz5VC.png)

`align-items: baseline;`

![image](https://i.imgur.com/UmWTk9G.png)

### Use the `flex-wrap` Property to Wrap a Row or Column
CSS flexbox has a feature to split a flex item into multiple rows (or columns). By default, a flex container will fit all flex items together. For example, a row will all be on one line.

However, using the `flex-wrap` property tells CSS to wrap items. This means extra items move into a new row or column. The break point of where the wrapping happens depends on the size of the items and the size of the container.

- `flex-wrap: nowrap;`: this is the default setting, and does not wrap items.
- `flex-wrap: wrap;`: wraps items from left-to-right if they are in a row, or top-to-bottom if they are in a column.
- `flex-wrap: wrap-reverse;`: wraps items from right-to-left if they are in a row, or bottom-to-top if they are in a column.

```html
<style>
  #box-container {
    background: gray;
    display: flex;
    height: 100%;
    flex-wrap: ;

  }
  #box-1 {
    background-color: dodgerblue;
    width: 25%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 25%;
    height: 50%;
  }
  #box-3 {
    background-color: violet;
    width: 25%;
    height: 50%;
  }
  #box-4 {
    background-color: yellow;
    width: 25%;
    height: 50%;
  }
  #box-5 {
    background-color: green;
    width: 25%;
    height: 50%;
  }
  #box-6 {
    background-color: black;
    width: 25%;
    height: 50%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
  <div id="box-3"></div>
  <div id="box-4"></div>
  <div id="box-5"></div>
  <div id="box-6"></div>
</div>
```
Use the above code to see references of each type of `flex-wrap`

`flex-wrap: nowrap;` **(This is the default value if none is specified)**

![iamge](https://i.imgur.com/DPn2pN8.png)

`flex-wrap: wrap;`

![image](https://i.imgur.com/HdD8te3.png)

`flex-wrap: wrap-reverse;`

![image](https://i.imgur.com/uRKngll.png)

## Use the `flex-shrink`, `flex-grow`, `flex-basis` to adjust flexed Elements
### Use the `flex-shrink` Property to Shrink Items
The first is the `flex-shrink` property. When it's used, it allows an item to shrink if the flex container is too small. Items shrink when the width of the parent container is smaller than the combined widths of all the flex items within it.

The `flex-shrink` property takes numbers as values. The higher the number, the more it will shrink compared to the other items in the container. For example, if one item has a `flex-shrink` value of 1 and the other has a `flex-shrink` value of 3, the one with the value of 3 will shrink three times as much as the other.
```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 100%;
    height: 200px;
    flex-shrink: 1;

  }

  #box-2 {
    background-color: orangered;
    width: 100%;
    height: 200px;
    flex-shrink: 2;

  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
The above code will output:

![image](https://i.imgur.com/ZPw2Uar.png)

### Use the `flex-grow` Property to Expand Items
The opposite of `flex-shrink` is the `flex-grow` property. Recall that `flex-shrink` controls the size of the items when the container shrinks. The `flex-grow` property controls the size of items when the parent container expands.

Using a similar example from the last challenge, if one item has a `flex-grow` value of 1 and the other has a `flex-grow` value of 3, the one with the value of 3 will grow three times as much as the other.
```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-grow: 1;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    flex-grow: 2;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
The above code will output:

![image](https://i.imgur.com/eJb7YSx.png)

## Use the `flex-basis` Property to Set the Initial Size of an Item
The `flex-basis` property specifies the initial size of the item before CSS makes adjustments with `flex-shrink` or `flex-grow`.

The units used by the flex-basis property are the same as other size properties (`px, em, %, etc.`). The value auto sizes items based on the content.
```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }

  #box-1 {
    background-color: dodgerblue;
    height: 200px;
    flex-basis: 90em;

  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    flex-basis: 20em;

  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
The above code will output:

![image](https://i.imgur.com/d8srpPk.png)

## Use the flex Shorthand Property
There is a shortcut available to set several flex properties at once. The `flex-grow`, `flex-shrink`, and `flex-basis` properties can all be set together by using the `flex` property.

For example, `flex: 1 0 10px;` will set the item to `flex-grow: 1;, flex-shrink: 0;, and flex-basis: 10px;`.

The default property settings are `flex: 0 1 auto;`.
```html
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    flex: 2 2 150px;
    height: 200px;
  }

  #box-2 {
    background-color: orangered;
    flex: 1 1 150px;
    height: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
These values will cause `#box-1` to grow to fill the extra space at twice the rate of `#box-2` when the container is greater than `300px` and shrink at twice the rate of `#box-2` when the container is less than `300px`. `300px` is the combined size of the `flex-basis` values of the two boxes.

Knowing this, the code will output:

![image](https://i.imgur.com/VLpIblX.png)

## Use the `order` Property to Rearrange Items
The `order` property is used to tell CSS the order of how flex items appear in the flex container. By default, items will appear in the same order they come in the source HTML. The property takes numbers as values, and negative numbers can be used.
```HTML
<style>
  #box-container {
    display: flex;
    height: 500px;
  }
  #box-1 {
    background-color: dodgerblue;
    order: 1;
    height: 200px;
    width: 200px;
  }

  #box-2 {
    background-color: orangered;
    height: 200px;
    width: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
*(Note: This property behaves like the `z-index` property. Elements that do not have an `order` property will be above this property compared to elements that do have it.)*

The above code will output:

![image](https://i.imgur.com/5S2VAoE.png)

This is because `#box-2` does not have an `order` property while `#box-1` does. Even with the `order` property set to 1, it will not come before `#box-2` because it **lacks** the `order` property.

## Use the align-self Property
The final property for flex items is `align-self`. This property allows you to adjust each item's alignment individually, instead of setting them all at once. This is useful since other common adjustment techniques using the CSS properties `float`, `clear`, and `vertical-align` do not work on flex items.

`align-self` accepts the same values as `align-items` and will **override** any value set by the `align-items` property.

Here are the `align-items` values incase you forgot, to see examples of these values, scroll to the appropriate section

![image](https://i.imgur.com/9ZQb1Pc.png)

```HTML
<style>
  #box-container {
    display: flex;
    height: 500px;
    align-items: stretch;
  }
  #box-1 {
    background-color: dodgerblue;
    align-self: center;
    height: 200px;
    width: 200px;
  }

  #box-2 {
    background-color: orangered;
    align-self: flex-end;
    height: 200px;
    width: 200px;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```
*(Note: Notice how the `#box-container` has the property `align-items: stretch;` yet `#box-1 , #box-2` are not following this rule. This is because `align-self`* **Overules** `align-items`)

The above code will output:

![image](https://i.imgur.com/6ckl1IJ.png)
