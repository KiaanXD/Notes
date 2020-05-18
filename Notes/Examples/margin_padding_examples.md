# Margin/Padding Examples
## Padding
You may have already noticed this, but all HTML elements are essentially little rectangles.

Three important properties control the space that surrounds each HTML element: padding, margin, and border.

An element's padding controls the amount of space between the element's content and its border.
```css
.box {
   border-style: solid;
   border-color: black;
   border-width: 5px;
   text-align: center;
 }

 .yellow-box {
   background-color: yellow;
   padding: 10px;
 }

 .red-box {
   background-color: crimson;
   color: #fff;
   padding: 20px;
 }

 .blue-box {
   background-color: blue;
   color: #fff;
   padding: 10px;
 }
```
This results in:

![image](https://i.imgur.com/sREq8ug.png)

If you would increase the blue box's padding, it will increase the distance (padding) between the text and the border around it.

**(Higher padding = Looks bigger)**
## Margin
An element's margin controls the amount of space between an element's border and surrounding elements.

Here, we can see that the blue box and the red box are nested within the yellow box. Note that the red box has a bigger margin than the blue box, making it appear smaller.
```css
<style>
.box {
   border-style: solid;
   border-color: black;
   border-width: 5px;
   text-align: center;
 }

 .yellow-box {
   background-color: yellow;
   padding: 10px;
 }

 .red-box {
   background-color: crimson;
   color: #fff;
   padding: 20px;
   margin: 20px;
 }

 .blue-box {
   background-color: blue;
   color: #fff;
   padding: 20px;
   margin: 10px;
 }
</style>
<div class="box yellow-box">
 <h5 class="box red-box">padding</h5>
 <h5 class="box blue-box">padding</h5>
```
This results in

![image](https://i.imgur.com/OkeJoyD.png)

If you would increase the blue box's margin, it will increase the distance between its border and surrounding elements, thus becoming smaller.
**(Higher margin = Looks smaller)**
## Negative Margin
An element's margin controls the amount of space between an element's border and surrounding elements.

If you set an element's margin to a negative value, the element will grow larger.
```css
<style>
   .box {
   border-style: solid;
   border-color: black;
   border-width: 5px;
   text-align: center;
 }

 .yellow-box {
   background-color: yellow;
   padding: 10px;
 }

 .red-box {
   background-color: crimson;
   color: #fff;
   padding: 20px;
   margin: -15px;
 }

 .blue-box {
   background-color: blue;
   color: #fff;
   padding: 20px;
   margin: 20px;
 }
</style>

<div class="box yellow-box">
 <h5 class="box red-box">padding</h5>
 <h5 class="box blue-box">padding</h5>
</div>
```
This results in:

![image](https://i.imgur.com/UBL70l9.png)

This is because the red margin has a negative interger causing it to become larger as **Smaller margin = Larger element**

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
