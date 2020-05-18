# What is HTML?
Introduction to Basic HTML & HTML5

HTML, or HyperText Markup Language, is a markup language used to describe the structure of a web page. It uses a special syntax or notation to organize and give information about the page to the browser. Elements usually have opening and closing tags that surround and give meaning to content. For example, there are different tag options to place around text to show whether it is a heading, a paragraph, or a list.

# Basic HTML
```html
This is the DOCTYPE. It allows you to specify HTML will be going here. It's necessary for HTML programs.
<!DOCTYPE html>
<html>
  <!-- Your HTML code goes here -->
</html>
```
```html
Any markup with information about your page would go into the <head> tag. Then any markup with the content of the page (what displays for a user) would go into the <body> tag.

Metadata elements, such as <link>, <meta>, <title>, and <style>, typically go inside the head element.

Here's an example of a page's layout:
    <!DOCTYPE html>
<html>
  <head>
    <!-- metadata elements -->
  </head>
  <body>
    <!-- page contents -->
  </body>
</html>
```

## Basic Formatting
```html
<h1> Hello </h1> : Header 1
<h2> Cat Photo app </h2> : Header 2
<p> I'm a Paragraph! </p> : Paragraph tag
<!-- This is a comment! --> : Comment tag, doesn't interfere with code.
<main> Main Text </main> : Defines the main body of a DOC
<body> Body text </body> : Defines the body of the DOC
<id> : The <id> tags allow you to give an id to an attribute (example: <main id="id">
<div> : The div tag allows you to create blocks in your DOC as long as there is a following</div>
```
## Image/Link Formatting
```html
<img src="#"> : How to paste an img with a link
<img src="#" alt="it's a cat"> : The alt tag allows you to add text where an image would be **if** the image doesn't load. Use this for proper coding etiquette
<a href="#"> : The <a> tag is the anchor tag. Adding the <href> allows you to refer the anchor to a link outside of the DOC
<a href="#" target="_blank"> : The target atrribute allows you
<a href="#contacts-header">Contacts</a>
   > This is an example of an <a> and <href> tag working together to refer the anchor to an id of the DOC
<h2 id="contacts-header">Contacts</h2>
```
Here's an example of a nested attribute linking a image to a new page
```html
<a href="#"><img src="https://bit.ly/fcc-running-cats" alt="Three kittens running towards the camera."></a>
```
Here's an example of a nested target atrribute linking to a new page
```html
<p> Here's a <a target="_blank" href="http://freecodecamp.org"> link to freecodecamp.org</a> for you to follow </p>
```

## Ordered/Unordered Lists

### Unordered

This is an example of an unordered list. Everything on this list will be written with bullet points
```html
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```

### Ordered
This is an example of an ordered list. Everything on this list will be written with numbers of order.
```html
<ol>
  <li>Apples</li>
  <li>Oranges</li>
</ol>
```

## Input Type Fields
This is an input field. The "placeholder" attribute allows you to place text in te empty text box until data is entered.
```html
<input type="text" placeholder ="this is a placeholder">    
```
You can build web forms that actually submit data to a server using nothing more than pure HTML. You can do this by specifying an action on your form element.
```html
<form action="/submit photo">
    <input type="text" placeholder="cat photo url" required>
</form>
```
This will submit the data from the input to your form/server

You can also require specific form fields so that your user will not be able to submit your form until he or she has filled them out.
```html
<input type="text" required>
```

## Buttons/Radios/Checkboxes

### Button
Let's add a submit button to your form. Clicking this button will send the data from your form to the URL you specified with your form's action attribute.
```html
<button type="submit">this button submits the form</button>
```

### Radio
You can use radio buttons for questions where you want the user to only give you one answer out of multiple options.

All related radio buttons should have the same name attribute to create a radio button group.

By creating a radio group, selecting any single radio button will automatically deselect the other buttons within the same group ensuring only one answer is provided by the user.
```html
 <label for="indoor">
     <input id="indoor" value="indoor" type="radio" name="indoor-outdoor"> Indoor</label>
<label for="outdoor">
    <input id="outdoor" value="outdoor" type="radio" name="indoor-outdoor"> Outdoor</label>
```
This is an example of two radio buttons. One holding the "string" "Indoor" the other holding "Outdoor."
### Checkboxes
Forms commonly use checkboxes for questions that may have more than one answer.

Checkboxes are a type of input.

Each of your checkboxes can be nested within its own label element. By wrapping an input element inside of a label element it will automatically associate the checkbox input with the label element surrounding it.

All related checkbox inputs should have the same name attribute.
```html
<label><input type="checkbox" name="persona" value="loving"> Loving</label>
<label><input type="checkbox" name="persona" value="lazy"> Lazy</label>
<label><input type="checkbox" name="persona" value="excited"> Excited</label>
```

### Values
The Value attribute allows you to mark the value of a Radio button/Check Box
Example:

If the "Indoor" Radio was checked **WITHOUT** the <value> attribute it would return the data to the form as "on" which is useless.

So if we do **ADD** the <value> atrribute it will return the data to the form as "Indoor" which is usefull!
