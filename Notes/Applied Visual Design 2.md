# Applied Visual Design
### Continued

## Create a graphic using CSS
By manipulating different selectors and properties, you can make interesting shapes. One of the easier ones to try is a crescent moon shape.

The code below will create a round, transparent object with a crisp shadow that is slightly offset to the side - the shadow is actually going to be the moon shape you see.
```HTML
<style>
  .center {
    position: absolute;
    margin: auto;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    width: 100px;
    height: 100px;
    background: transparent;
    border-radius: 50%;
    box-shadow: 25px 10px 0px 0px blue;
  }

</style>
<div class="center"></div>
```
by making the boxes background color transparent, this allows us to have the shadow form the shape we want, in this case, a crescent moon.

![image](https://i.imgur.com/IUch0zS.png)

![image](https://i.imgur.com/ENpiAjn.png)

## Create a More Complex Shape Using CSS and HTML
First, you need to understand the `::before` and `::after` pseudo-elements. These pseudo-elements are used to add something before or after a selected element.

For the `::before` and `::after` pseudo-elements to function properly, they must have a defined content property. This property is usually used to add things like a photo or text to the selected element. When the `::before` and `::after` pseudo-elements are used to make shapes, the content property is still required, but it's set to an empty string.

Let's break this down step by step with examples:

### The base heart class
```CSS
.heart {
  position: absolute;
  margin: auto;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: pink;
  height: 50px;
  width: 50px;
  transform: rotate(-45deg) ;
}
```
This outputs

![image](https://i.imgur.com/Wrpnucz.png)

### The base heart class + `::before` heart class
```CSS
.heart {
  position: absolute;
  margin: auto;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: pink;
  height: 50px;
  width: 50px;
  transform: rotate(-45deg) ;
}

.heart::before {
  content: "";
  background-color: pink;
  border-radius: 50%;
  position: absolute;
  width: 50px;
  height: 50px;
  top: -25px;
  left: 0px;
}
```
This outputs

![image](https://i.imgur.com/Sw4sUem.png)

### The base heart class + `::before` + `::after` heart class
```css
.heart {
  position: absolute;
  margin: auto;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: pink;
  height: 50px;
  width: 50px;
  transform: rotate(-45deg) ;
}
.heart::before {
  content: "";
  background-color: pink;
  border-radius: 50%;
  position: absolute;
  width: 50px;
  height: 50px;
  top: -25px;
  left: 0px;
}
.heart::after {
  background-color: pink;
  content: "";
  border-radius: 50%;
  position: absolute;
  width: 50px;
  height: 50px;
  top: 0px;
  left: 25px;
}
```
This outputs

![image](https://i.imgur.com/B0SzY9X.png)

## Animation using `@keyframes`
To animate an element, you need to know about the animation properties and the `@keyframes` rule.

`animation-name` sets the name of the animation, which is later used by `@keyframes` to tell CSS which rules go with which animations.

`animation-duration` sets the length of time for the animation.

`@keyframes` is how to specify exactly what happens within the animation over the duration. This is done by giving CSS properties for specific "frames" during the animation, with percentages ranging from 0% to 100%.
```HTML
<style>
  div {
    height: 40px;
    width: 70%;
    background: black;
    margin: 50px auto;
    border-radius: 5px;
  }

  #rect {
    animation-name: rainbow;
    animation-duration: 4s;
  }
  @keyframes rainbow {
    0%{
      background-color: blue;
    }
    50%{
      background-color: green;
    }
    100%{
      background-color: yellow;
    }
  }
</style>
<div id="rect"></div>
```
This will output:
(in this order)

![image](https://i.imgur.com/bLtNgpJ.png) ![image](https://i.imgur.com/jQ5cIRK.png) ![image](https://i.imgur.com/NLefPaK.png)

If you compare this to a movie, the CSS properties for 0% is how the element displays in the opening scene. The CSS properties for 100% is how the element appears at the end, right before the credits roll.

### Animating Pseudo Classes
The most important thing to remember when trying to animate `pseudo` classes is that **you must redeclare the animation classes in the pseudo class** See any example below.
```HTML
<style>
  img:hover {
    animation-name: widthimg;
    animation-duration: 1s;
  }

  @keyframes widthimg {
    100% {
      width: 50%;
    }
  }
</style>

<img src="https://bit.ly/smallgooglelogo" alt="Google's Logo" />
```
Here's a before / after the `::hover`

![image](https://i.imgur.com/G7LCt71.png)

![image](https://i.imgur.com/0mFN6eb.png)

This is because the `img:hover` has the animation `widthimg` is re-applied directly to the pseudo class.

### Modify Fill Mode of an Animation
How to I keep a `@keyframe` highlighted while hovered? This can be done by setting the animation-fill-mode property to forwards. The animation-fill-mode specifies the style applied to an element when the animation has finished. You can set it like so:

`animation-fill-mode: forwards;`

Here's an example:

```HTML
<style>
  button {
    border-radius: 5px;
    color: white;
    background-color: #0F5897;
    padding: 5px 10px 8px 10px;
  }
  button:hover {
    animation-name: background-color;
    animation-duration: 500ms;
    animation-fill-mode: forwards;
  }
  @keyframes background-color {
    100% {
      background-color: purple;
    }
  }
</style>
<button>Register</button>
```

![image](https://i.imgur.com/1vFGUfp.png)

![image](https://i.imgur.com/zLpAvBZ.png)

Under the button `:hover` we have the `animation-fill-mode` which negates the `animation-duration` and keeps it on as long as it is hovered upon.

## Create Movement Using CSS Animation
When elements have a specified position, such as `fixed` or `relative`, the CSS offset properties `right left top` and `bottom` can be used in animation rules to create movement.

```css
@keyframes rainbow {
  0% {
    background-color: blue;
    top: 0px;
  }
  50% {
    background-color: green;
    top: 50px;
  }
  100% {
    background-color: yellow;
    top: 0px;
  }
}
```
This will allow the `rainbow` animation to change in color **and** move during the duration of the animation.

![image](https://i.imgur.com/mxgI4g0.png)

![image](https://i.imgur.com/RTw8q41.png)

![image](https://i.imgur.com/Qd4Tiiu.png)

![image](https://i.imgur.com/YoaqiIX.png)

This is the step by step movement / color the above code will follow in order.

## Create Visual Direction by Fading an Element from Left to Right using opacity
By changing the opacity of an animated element you can make it seem like it's gradually fading as it reaches the right side of the screen.
```HTML
<style>

  #ball {
    width: 70px;
    height: 70px;
    margin: 50px auto;
    position: fixed;
    left: 20%;
    border-radius: 50%;
    background: purple;
    animation-name: fade;
    animation-duration: 3s;
  }

  @keyframes fade {
    50% {
      left: 60%;
      opacity: 0.1;

    }
  }

</style>

<div id="ball"></div>
```
As the image goes to the left it will drop in opacity thanks to the `@keyframes fade` animation.

![image](https://i.imgur.com/B89kTAV.png)

![image](https://i.imgur.com/DB7adxx.png)

## Animate Elements Continually
The previous challenges covered how to use some of the animation properties and the `@keyframes` rule. Another animation property is the `animation-iteration-count`, which allows you to control how many times you would like to loop through the animation. Here's an example:
```HTML
<style>

  #ball {
    width: 100px;
    height: 100px;
    margin: 50px auto;
    position: relative;
    border-radius: 50%;
    background: purple;
    animation-name: bounce;
    animation-duration: 1s;
    animation-iteration-count: 3;
  }

  @keyframes bounce{
    0% {
      top: 0px;
    }
    50% {
      top: 249px;
      width: 130px;
      height: 70px;
    }
    100% {
      top: 0px;
    }
  }
</style>
<div id="ball"></div>
```
The `animation-iteration-count` is what allows this animation to keep playing a specified amount of times, up to `infinite`.

## Change Animation Timing with Keywords
In CSS animations, the `animation-timing-function` property controls how quickly an animated element changes over the duration of the animation.

If the animation is a car moving from point A to point B in a given time (your animation-duration), the `animation-timing-function` says how the car accelerates and decelerates over the course of the drive.

There are a number of predefined keywords available for popular options.

- `ease` : *(default value)* starts slow, speeds up in the middle, and then slows down again in the end.
- `ease-out` : quick in the beginning then slows down.
- `ease-in` : slow in the beginning, then speeds up at the end.
- `linear` : applies a constant animation speed throughout.
<hr>

```HTML
<style>

.balls {
  border-radius: 50%;
  background: linear-gradient(
    35deg,
    #ccffff,
    #ffcccc
  );
  position: fixed;
  width: 50px;
  height: 50px;
  margin-top: 50px;
  animation-name: bounce;
  animation-duration: 2s;
  animation-iteration-count: infinite;
}
#ball1 {
  left:27%;
  animation-timing-function: linear;
}
#ball2 {
  left:56%;
  animation-timing-function: ease-out;
}
body{
  background: black;
}
@keyframes bounce {
  0% {
    top: 0px;
  }
  100% {
    top: 249px;
  }
}

</style>

<div class="balls" id="ball1"></div>
<div class="balls" id="ball2"></div>
```
Here's an example **without** the `animation-timing-function: linear;` and `animation-timing-function: ease-out;` code

![image](https://i.imgur.com/oGafrKl.gif)

Here's an example **with** the `animation-timing-function: linear;` and `animation-timing-function: ease-out;` code

![image](https://i.imgur.com/0Irfn0B.gif)

## Learn How Bezier Curves Work
In CSS animations, **Bezier curves** are used with the `cubic-bezier` function. The shape of the curve represents how the animation plays out. The curve lives on a 1 by 1 coordinate system. The **X-axis** *of this coordinate system is the duration of the animation (think of it as a time scale)*, and the **Y-axis** *is the change in the animation.*

The `cubic-bezier` function consists of four main points that sit on this 1 by 1 grid: `p0, p1, p2, and p3`

`p0 and p3` are set for you - they are the beginning and end points which are always located respectively at the origin (0, 0) and (1, 1). You set the x and y values for the other two points, and where you place them in the grid dictates the shape of the curve for the animation to follow.

This is done in CSS by declaring the x and y values of the p1 and p2 "anchor" points in the form: (x1, y1, x2, y2). Pulling it all together, here's an example of a Bezier curve in CSS code

In general, changing the p1 and p2 anchor points drives the creation of different Bezier curves, which controls how the animation progresses through time. Here's an example of a Bezier curve using values to mimic the ease-out style:
```HTML
<style>
  .balls{
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    margin-top: 50px;
    animation-name: bounce;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 27%;
    animation-timing-function: cubic-bezier(0, 0, 0.58, 1);
  }
  #blue {
    background: blue;
    left: 56%;
    animation-timing-function: ease-out;
  }
  @keyframes bounce {
    0% {
      top: 0px;
    }
    100% {
      top: 249px;
    }
  }
</style>

<div class="balls" id= "red"></div>
<div class="balls" id= "blue"></div>
```

![image](https://i.imgur.com/DTauVPv.gif)

The red ball only matches the `ease-out` speed of the blue ball because of the cubic-bezier. `animation-timing-function: cubic-bezier(0, 0, 0.58, 1)`

### Making Motion More Natural Using a Bezier Curve
The animation-timing-function automatically loops at every keyframe when the animation-iteration-count is set to infinite.

The following cubic Bezier curve simulates a juggling movement:

`cubic-bezier(0.3, 0.4, 0.5, 1.6);`

Notice that the value of y2 is larger than 1. **Although the cubic Bezier curve is mapped on a 1 by 1 coordinate system, and it can only accept x values from 0 to 1, the y value can be set to numbers larger than one.** This results in a bouncing movement that is ideal for simulating the juggling ball.
```HTML
<style>
  .balls {
    border-radius: 50%;
    position: fixed;
    width: 50px;
    height: 50px;
    top: 60%;
    animation-name: jump;
    animation-duration: 2s;
    animation-iteration-count: infinite;
  }
  #red {
    background: red;
    left: 25%;
    animation-timing-function: linear;
  }
  #blue {
    background: blue;
    left: 50%;
    animation-timing-function: ease-out;
  }
  #green {
    background: green;
    left: 75%;
    animation-timing-function: cubic-bezier(0.311, 0.441, 0.444, 1.649);
  }

  @keyframes jump {
    50% {
      top: 10%;
    }
  }
  body{
    background: black;
  }
</style>

<div class="balls" id="red"></div>
<div class="balls" id="blue"></div>
<div class="balls" id="green"></div>
```
This outputs:

![image](https://i.imgur.com/Uu8QJ2j.gif)

Notice the differnce between the red/blue/green ball.

- The red ball has `animation-timing-function: linear;`
- The blue ball has `animation-timing-function: ease-out;`
- The green ball has `animation-timing-function: cubic-bezier(0.311, 0.441, 0.444, 1.649)`

Out of these three the best and most fluid looking animation is the green ball.
