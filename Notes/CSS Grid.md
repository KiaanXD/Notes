# CSS Grid

## Introduction to the CSS Grid
CSS Grid helps you easily build complex web designs. It works by turning an HTML element into a grid container with rows and columns for you to place children elements where you want within the grid.

## Creating a basic CSS Grid
Turn any HTML element into a grid container by setting its `display` property to `grid`. This gives you the ability to use all the other properties associated with CSS Grid.

*(Note: In CSS Grid, the parent element is referred to as the container and its children are called items.)*
```HTML
display: grid;
```

### Add Columns with `grid-template-columns`
Simply creating a grid element doesn't get you very far. You need to define the structure of the grid as well. To add some columns to the grid, use the `grid-template-columns` property on a grid container. Here's an example
```CSS
.container {
  display: grid;
  grid-template-columns: 50px 50px;
}
```
This will give your grid two columns that are each 50px wide. The number of parameters given to the `grid-template-columns` property indicates the number of columns in the grid, and the value of each parameter indicates the width of each column.
```HTML
<style>
  .d1{background:LightSkyBlue;}
  .d2{background:LightSalmon;}
  .d3{background:PaleTurquoise;}
  .d4{background:LightPink;}
  .d5{background:PaleGreen;}

  .container {
    font-size: 40px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 100px 100px 100px;
  }
</style>

<div class="container">
  <div class="d1">1</div>
  <div class="d2">2</div>
  <div class="d3">3</div>
  <div class="d4">4</div>
  <div class="d5">5</div>
</div>
```
This is the above code **without** `grid-template-columns;`

![img](https://i.imgur.com/fcEwTR4.png)

This is the above code **with** `grid-template-columns;`

![img](https://i.imgur.com/kuKxc11.png)

*(Note: You can continue to add more and more grids by adding additional dimensions for columns)*

### Adding Rows with `grid-template-rows`
You can adjust rows manually using the `grid-template-rows` property the same way you used the `grid-template-columns` property.
```HTML
<style>
  .d1{background:LightSkyBlue;}
  .d2{background:LightSalmon;}
  .d3{background:PaleTurquoise;}
  .d4{background:LightPink;}
  .d5{background:PaleGreen;}

  .container {
    font-size: 40px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 100px 100px 100px;
    grid-template-rows: 100px 100px ;

  }
</style>

<div class="container">
  <div class="d1">1</div>
  <div class="d2">2</div>
  <div class="d3">3</div>
  <div class="d4">4</div>
  <div class="d5">5</div>
</div>
```
*(Note: The `grid-template-rows` property adjusts the row dimensions of each line. adding additional dimensions will continue to add these dimensions to the next line.)*

Here's an example of the above code:

![img](https://i.imgur.com/ElAcmU8.png)

### Using CSS Grid units to Change the Size of Columns and Rows
You can use absolute and relative units like `px` and `em` in CSS Grid to define the size of rows and columns. You can use these as well:
- `fr`: Sets the column or row to a fraction of the available space.
- `auto`: Sets the column or row to the width or height of its content automatically.
- `%`: Adjusts the column or row to the percent width of its container

Here is an example of code using all of these units:
```HTML
<style>
  .d1{background:LightSkyBlue;}
  .d2{background:LightSalmon;}
  .d3{background:PaleTurquoise;}
  .d4{background:LightPink;}
  .d5{background:PaleGreen;}

  .container {
    font-size: 40px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: auto 50px 10% 2fr 1fr;
    grid-template-rows: 50px 50px;
  }
</style>

<div class="container">
  <div class="d1">1</div>
  <div class="d2">2</div>
  <div class="d3">3</div>
  <div class="d4">4</div>
  <div class="d5">5</div>
</div>
```
![img](https://i.imgur.com/ZcmbQEw.png)

*(Note: This `grid-template-columns` snippet creates five columns. The first column is as wide as its content, the second column is 50px, the third column is 10% of its container, and for the last two columns; the remaining space is divided into three sections, two are allocated for the fourth column, and one for the fifth.)*

## Creating Gaps using `grid-column-gap` and `grid-row-gap`
### Using `grid-column-gap` to create gaps between Columns
So far in the grids you have created, the columns have all been tight up against each other. Sometimes you want a gap in between the columns. To add a gap between the columns, use the `grid-column-gap` property like this:
```HTML
<style>
  .d1{background:LightSkyBlue;}
  .d2{background:LightSalmon;}
  .d3{background:PaleTurquoise;}
  .d4{background:LightPink;}
  .d5{background:PaleGreen;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-column-gap: 20px;

  }
</style>

<div class="container">
  <div class="d1">1</div>
  <div class="d2">2</div>
  <div class="d3">3</div>
  <div class="d4">4</div>
  <div class="d5">5</div>
</div>
```
Here is the output of the above code:

![img](https://i.imgur.com/RYD0nrv.png)

### Create a Row Gap using `grid-row-gap`
You can add a gap in between the rows of a grid using grid-row-gap in the same way that you added a gap in between columns.
```HTML
<style>
  .d1{background:LightSkyBlue;}
  .d2{background:LightSalmon;}
  .d3{background:PaleTurquoise;}
  .d4{background:LightPink;}
  .d5{background:PaleGreen;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-column-gap: 20px;
    grid-row-gap: 20px;
  }
</style>

<div class="container">
  <div class="d1">1</div>
  <div class="d2">2</div>
  <div class="d3">3</div>
  <div class="d4">4</div>
  <div class="d5">5</div>
</div>
```
The above code output:

![img](https://i.imgur.com/Nd15Ebm.png)

### Add Gaps Faster with `grid-gap`
`grid-gap` is a shorthand property for `grid-row-gap` and `grid-column-gap` that's more convenient to use. If `grid-gap` has one value, it will create a gap between all rows and columns. *However, if there are two values, it will use the first one to set the gap between the rows and the second value for the columns.*
```HTML
<style>
  .d1{background:LightSkyBlue;}
  .d2{background:LightSalmon;}
  .d3{background:PaleTurquoise;}
  .d4{background:LightPink;}
  .d5{background:PaleGreen;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
</style>
<div class="container">
  <div class="d1">1</div>
  <div class="d2">2</div>
  <div class="d3">3</div>
  <div class="d4">4</div>
  <div class="d5">5</div>
</div>
```
Using `grid-gap: 10px;` it sets a flat 10px value for rows and columns.

![img](https://i.imgur.com/QirDAsD.png)

## Use `grid-column` and `grid-row` to Control Spacing
Up to this point, all the properties that have been discussed are for grid containers. The `grid-column` property is the first one for use on the grid items themselves.

The hypothetical horizontal and vertical lines that create the grid are referred to as lines. These lines are numbered starting with 1 at the top left corner of the grid and move right for columns and down for rows, counting upward.

This is what the lines look like for a 3x3 grid:

![img](https://i.imgur.com/lAS5Rj0.png)

### Using `grid-column`
To control the amount of columns an item will consume, you can use the `grid-column` property in conjunction with the line numbers you want the item to start and stop at.
```HTML
<style>
  .item1{background:LightSkyBlue;}
  .item2{background:LightSalmon;}
  .item3{background:PaleTurquoise;}
  .item4{background:LightPink;}

  .item5 {
    background: PaleGreen;
    grid-column: 2/4;
  }

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```
*(Note: In this example we're making item 5 stretch from its original point to the end of the of the grid)*

![img](https://i.imgur.com/KZalMW1.png)

### Using `grid-row`
To control the amount of rows an item will consume. you can use `grid-row` property in conjunction with line numbers you want the item to start and stop at.
```HTML
<style>
  .item1{background:LightSkyBlue;}
  .item2{background:LightSalmon;}
  .item3{background:PaleTurquoise;}
  .item4{background:LightPink;}

  .item5 {
    background: PaleGreen;
    grid-column: 2 / 4;
    grid-row: 1 / 4;
  }

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```
*(Note: Item 5 is placed on rows beginning on 1 and ending on 4. This takes up all space from the rows from 1-4 so it places it on a whole different row, one dedicated to this object.)*

![img](https://i.imgur.com/PRsPJh4.png)

## Align items using `justify-self` and `align-self`
In CSS Grid, the content of each item is located in a box which is referred to as a cell. You can align the content's position within its cell horizontally using the `justify-self` property on a grid item. **By default, this property has a value of `stretch`, which will make the content fill the whole width of the cell**. This CSS Grid property accepts other values as well:
- `start`: aligns the content at the left of the cell,
- `center`: aligns the content in the center of the cell.
- `end`: aligns the content at the right of the cell.

### Aligning a item horizontally using `justify-self`
We can use the above properties to align an item horizontally
```HTML
<style>
  .item1{background: LightSkyBlue;}

  .item2 {
    background: LightSalmon;
    justify-self: center;

  }

  .item3{background:PaleTurquoise;}
  .item4{background:LightPink;}
  .item5{background:PaleGreen;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```
This will put object 2 in the center, see the example below:

![img](https://i.imgur.com/jM775r3.png)

### Aligning an item vertically using `align-self`
We can use the above properties to align an item vertically
```HTML
<style>
  .item1{background:LightSkyBlue;}
  .item2{background:LightSalmon;}

  .item3 {
    background: PaleTurquoise;
    align-self: end;
  }

  .item4{background:LightPink;}
  .item5{background:PaleGreen;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```
This will put object 3 at the end of the cell vertically

![img](https://i.imgur.com/HyzNjcr.png)

### Positioning all items in a container using `justify-items` and `align-items`
Sometimes you want all the items in your CSS Grid to share the same alignment. You can use the previously learned properties and align them individually, or you can align them all at once horizontally / vertically by using `justify-items` / `align-items` on your grid container.
```HTML
<style>
  .item1{background:LightSkyBlue;}
  .item2{background:LightSalmon;}
  .item3{background:PaleTurquoise;}
  .item4{background:LightPink;}
  .item5{background:PaleGreen;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
    justify-items: center;
    align-items: start;
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```
Using `justify-items` and `align-items` we've positioned every object horizontally and vertically in the grid container.

![img](https://i.imgur.com/w55bIv8.png)

## CSS grid template
### Divide the Grid Into an Area Template
You can group cells of your grid together into an *area* and give the area a custom name. Do this by using `grid-template-areas` on the container like this:
```html
grid-template-areas:
  "header header header"
  "advert content content"
  "footer footer footer";
```
The code above merges the top three cells together into an area named `header`, the bottom three cells into a `footer` area, and it makes two areas in the middle row; `advert` and `content`.

*(Note: Every word in the code represents a cell and every pair of quotation marks represent a row. In addition to custom labels, you can use a period (.) to designate an empty cell in the grid.)*

### Place Items in Grid Areas Using the `grid-area` Property
After creating an area's template for your grid container, as shown previously, you can place an item in your custom area by referencing the name you gave it. To do this, you use the `grid-area` property on an item like this:
```css
.item1 {
  grid-area: header;
}
```
This lets the grid know that you want the item1 class to go in the area named `header`. In this case, the item will use the entire top row because that whole row is named as the header area.
```HTML
<style>
  .item1{
    background:LightSkyBlue;
    grid-area: header;
    }
  .item2{
    background:LightSalmon;
    grid-area: advert;
    }
  .item3{
    background:PaleTurquoise;
    grid-area: content;
    }
  .item4{
    background:LightPink;
    grid-area: content;
    }

  .item5 {
    background: PaleGreen;
    grid-area: footer;
  }

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    grid-gap: 10px;
    grid-template-areas:
      "header header header"
      "advert content content"
      "footer footer footer";
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
</div>
```
There's a lot going on here. First off the grid `.container` has the property `grid-template-area` defines the area of the grid. Then under the induvial items you must use the `grid-area` property to define their place in the `grid-template-area` This is why in the example:
- `.item 1` takes up the whole defined `header` area
- `.item 2` takes up the `advert` area
- `.item 2` takes up the `content` area
- `.item 4` also takes up the `content` area **overlapping** `.item 3` because it is declared second in the CSS, thus takes priority
- `.item 5` takes up the whole defined `footer` area

Here is the final output of the above code:

![img](https://i.imgur.com/YPPErQJ.png)

### Creating a `grid-area` without creating a Area Template
The `grid-area` property you learned previously can be used in another way. If your grid doesn't have an areas template to reference, you can create an area on the fly for an item to be placed like this:
```CSS
item1 { grid-area: 1/1/2/4; }
```
This is using the line numbers you learned about earlier to define where the area for this item will be. The numbers in the example above represent these values:

`grid-area: horizontal line to start at / vertical line to start at / horizontal line to end at / vertical line to end at;`

So the item in the example above will consume the rows between lines 1 and 2, and the columns between lines 1 and 4.
