# Applied Accessibility

## What is Applied Accessibility?
"Accessibility" generally means having web content and a user interface that can be understood, navigated, and interacted with by a broad audience. This includes people with visual, auditory, mobility, or cognitive disabilities.

Websites should be open and accessible to everyone, regardless of a user's abilities or resources. Some users rely on assistive technology such as a screen reader or voice recognition software. Other users may be able to navigate through a site only using a keyboard. Keeping the needs of various users in mind when developing your project can go a long way towards creating an open web.

Here are three general concepts this section will explore throughout the following challenges:
- have well-organized code that uses appropriate markup
- ensure text alternatives exist for non-text and visual content
- create an easily-navigated page that's keyboard-friendly

## Use Headings to Show Hierarchical Relationships of Content
Headings (h1 through h6 elements) are workhorse tags that help provide structure and labeling to your content. Screen readers can be set to read only the headings on a page so the user gets a summary. This means it is important for the heading tags in your markup to have semantic meaning and relate to each other, not be picked merely for their size values.
```html
<h1>How to Become a Ninja</h1>
<main>
  <h2>Learn the Art of Moving Stealthily</h2>
  <h3>How to Hide in Plain Sight</h3>
  <h3>How to Climb a Wall</h3>

  <h2>Learn the Art of Battle</h2>
  <h3>How to Strengthen your Body</h3>
  <h3>How to Fight like a Ninja</h3>

  <h2>Learn the Art of Living with Honor</h2>
  <h3>How to Breathe Properly</h3>
  <h3>How to Simplify your Life</h3>
</main>
```

## Wrap Content in the `article` Element
`article` is another one of the new HTML5 elements that adds semantic meaning to your markup. article is a sectioning element, and is used to wrap independent, self-contained content. The tag works well with blog entries, forum posts, or news articles.

Determining whether content can stand alone is usually a judgement call, but there are a couple simple tests you can use. Ask yourself if you removed all surrounding context, would that content still make sense?

*(Note about section and div)*

The section element is also new with HTML5, and has a slightly different semantic meaning than article. An article is for standalone content, and a section is for grouping thematically related content. They can be used within each other, as needed. For example, if a book is the article, then each chapter is a section. When there's no relationship between groups of content, then use a div.
```HTML
<div> - groups content
<section> - groups related content
<article> - groups independent, self-contained content
```

## Screen Reader Navigation

### Make Screen Reader Navigation Easier with the `header` tag
The next HTML5 element that adds semantic meaning and improves accessibility is the `header` tag. It's used to wrap introductory information or navigation links for its parent tag and works well around content that's repeated at the top on multiple pages.

Header shares the embedded landmark feature you saw with main, allowing assistive technologies to quickly navigate to that content.

*(Note: The header is meant for use in the body tag of your HTML document. This is different than the head element, which contains the page's title, meta information, etc.)*
```HTML
<body>
  <header>
    <h1>This is a heading</h1>
  </header>
</body>
```

###  Make Screen Reader Navigation Easier with the `nav` tag

The `nav` element is another HTML5 item with the embedded landmark feature for easy screen reader navigation. This tag is meant to wrap around the main navigation links in your page.

If there are repeated site links at the bottom of the page, it isn't necessary to markup those with a nav tag as well. Using a footer is sufficient.
```HTML
<nav>
  <ul>
    <li><a href="#stealth">Stealth &amp; Agility</a></li>
    <li><a href="#combat">Combat</a></li>
    <li><a href="#weapons">Weapons</a></li>
  </ul>
</nav>
```

### Make Screen Reader Navigation Easier with the `footer` tag
The `footer` element has a built-in landmark feature that allows assistive devices to quickly navigate to it. It's primarily used to contain copyright information or links to related documents that usually sit at the bottom of a page.
```HTML
<footer>&copy; 2018 Camper Cat</footer>
```

## Improve Accessibility of Audio Content with the audio Element
HTML5's `audio` element gives semantic meaning when it wraps sound or audio stream content in your markup. Audio content also needs a text alternative to be accessible to people who are deaf or hard of hearing. This can be done with nearby text on the page or a link to a transcript.

The `audio` tag supports the `controls` attribute. This shows the browser default play, pause, and other controls, and supports keyboard functionality. This is a boolean attribute, meaning it doesn't need a value, its presence on the tag turns the setting on.
```HTML
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg" />
  <source src="audio/meow.ogg" type="audio/ogg" />
</audio>
```
*(Note: Multimedia content usually has both visual and auditory components. It needs synchronized captions and a transcript so users with visual and/or auditory impairments can access it. Generally, a web developer is not responsible for creating the captions or transcript, but needs to know to include them.)*

Here's another example:
```HTML
<audio controls>
      <source src="https://s3.amazonaws.com/freecodecamp/screen-reader.mp3" type="audio/mpeg"/>
    </audio>
```

## Improve Chart Accessibility with the `figure` Element
HTML5 introduced the `figure` element, along with the related `figcaption`. Used together, these items wrap a visual representation (like an image, diagram, or chart) along with its caption. This gives a two-fold accessibility boost by both semantically grouping related content, and providing a text alternative that explains the figure.

For data visualizations like charts, the caption can be used to briefly note the trends or conclusions for users with visual impairments. Another challenge covers how to move a table version of the chart's data off-screen (using CSS) for screen reader users.
```HTML
<figure>
  <img src="roundhouseDestruction.jpeg" alt="Photo of Camper Cat executing a roundhouse kick">
  <br>
  <figcaption>
    Master Camper Cat demonstrates proper form of a roundhouse kick.
  </figcaption>
</figure>
```

## Form Field Accessibility

### Improve Form Field Accessibility with the label Element
The `label` tag wraps the text for a specific form control item, usually the name or label for a choice. This ties meaning to the item and makes the form more readable. The `for` attribute on a `label` tag explicitly associates that `label` with the form control and is used by screen readers.

The value of the `for` attribute must be the same as the value of the `id` attribute of the form control. Here's an example:
```HTML
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" name="name">
</form>
```
Here's one last example:
```HTML
<section>
    <form>
      <p>Sign up to receive Camper Cat's blog posts by email here!</p>
      <label for="email">Email:</label>
      <input type="text" id="email" name="email">
      <input type="submit" name="submit" value="Submit">
    </form>
</section>
```
This is the result:

![image](https://i.imgur.com/HmmOPFb.png)

### Wrap Radio Buttons in a `fieldset` Element for Better Accessibility
The next form topic covers accessibility of radio buttons. Each choice is given a `label` with a `for` attribute tying to the `id` of the corresponding item. Since radio buttons often come in a group where the user must choose one, there's a way to semantically show the choices are part of a set.

The `fieldset` tag surrounds the entire grouping of radio buttons to achieve this. It often uses a `legend` tag to provide a description for the grouping, which is read by screen readers for each choice in the `fieldset` element.

The `fieldset` wrapper and `legend` tag are not necessary when the choices are self-explanatory, like a gender selection. Using a `label` with the for attribute for each radio button is sufficient.
```HTML
<form>
  <fieldset>
    <legend>Choose one of these three items:</legend>
    <input id="one" type="radio" name="items" value="one">
    <label for="one">Choice One</label><br>
    <input id="two" type="radio" name="items" value="two">
    <label for="two">Choice Two</label><br>
    <input id="three" type="radio" name="items" value="three">
    <label for="three">Choice Three</label>
  </fieldset>
</form>
```
This would output:

![image](https://i.imgur.com/jgJ23QN.png)

*(Note: The white outline around the radio buttons and `legend` is because of the `fieldset` make sure to make use of this element when you need to tie a portion of radio buttons together.)*

## Add an Accessible Date/Time Picker
Forms often include the input field, which can be used to create several different form controls. The type attribute on this element indicates what kind of input will be created.

HTML5 introduced an option to specify a `date` field. Depending on browser support, a date picker shows up in the `input` field when it's in focus, which makes filling in a form easier for all users.

For older browsers, the type will default to text, so it helps to show users the expected date format in the label or as placeholder text just in case.
```HTML
<label for="input1">Enter a date:</label>
<input type="date" id="input1" name="input1">
```

### Standardize Times with the HTML5 datetime Attribute
HTML5 also introduced the `time` element along with a `datetime` attribute to standardize times. This is an inline element that can wrap a date or time on a page. A valid format of that date is held by the datetime attribute. **This is the value accessed by assistive devices.** It helps avoid confusion by stating a standardized version of a time, even if it's written in an informal or colloquial manner in the text.
```HTML
<p>Master Camper Cat officiated the cage match between Goro and Scorpion <time datetime="2013-02-13">last Wednesday</time>, which ended in a draw.</p>
```

## Make Elements Only Visible to a Screen Reader by Using Custom CSS
Most applied accessibility so far hasn't used any CSS? This is to show the importance of a logical document outline, and using semantically meaningful tags around your content before introducing the visual design aspect.

However, CSS's magic can also improve accessibility on your page when you want to visually hide content meant only for screen readers. This happens when information is in a visual format (like a chart), but screen reader users need an alternative presentation (like a table) to access the data. CSS is used to position the screen reader-only elements off the visual area of the browser window.

Here's an example of the CSS rules that accomplish this:
```CSS
.sr-only {
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  top: auto;
  overflow: hidden;
}
```
This can be used to hide elements on the table from everyone but a screen reader. So if you wanted to have a picture graph on your webpage, you could make a table to show the stats of said picture graph, then hide this table so only the screen reader can receive it.

*(Note: The following CSS approaches will NOT do the same thing:)*

- `display: none;` or `visibility: hidden;` hides content for everyone, including screen reader users
- Zero values for pixel sizes, such as `width: 0px; height: 0px;` removes that element from the flow of your document, meaning screen readers will ignore it

## Improve Readability with High Contrast Text
Low contrast between the foreground and background colors can make text difficult to read. Sufficient contrast improves the readability of your content, but what exactly is "sufficient?"

The Web Content Accessibility Guidelines (WCAG) recommend **at least a 4.5 to 1 contrast ratio for normal text.** The ratio is calculated by comparing the relative luminance values of two colors. This ranges from 1:1 for the same color, or no contrast, to 21:1 for white against black, the strongest contrast. There are many contrast checking tools available online that calculate this ratio for you.
```CSS
body {
    color: #D3D3D3;
    background-color: #FFF;
  }
```
The above code is a poor contrast coming in at 1.5:1 making the text and background almost the same color.

![image](https://i.imgur.com/kpPE756.png)

However, if we tweak the text color we can have a ratio to 6:1 using this code instead
```css
body {
  color: #636363;
  background-color: #FFF;
}
```
This code will output:

![image](https://i.imgur.com/PZNEi4B.png)

Much easier to read as the ratio goes up.  *(1.5:1 to 6:1.)*

### Avoid Colorblindness Issues by Using Sufficient Contrast
Color is a large part of visual design, but its use introduces two accessibility issues. First, color alone should not be used as the only way to convey important information because screen reader users won't see it. Second, foreground and background colors need sufficient contrast so colorblind users can distinguish them.

Colorblind users have trouble distinguishing some colors from others - **usually in hue but sometimes lightness as well.** You may recall the contrast ratio is calculated using the relative luminance (or lightness) values of the foreground and background colors.
```css
body {
    color: hsl(0, 55%, 20%);
    background-color: hsl(120, 25%, 35%);
  }
```
The above code has a ration of 2.5:1 which is relatively low, and looks like this:

![image](https://i.imgur.com/8NGfcZQ.png)
We can see this decently clearly, but if someone had a form of color blindness this ratio might not suffice.

We can easily adjust the lightness of the colors since they were declared using the `CSS hsl()` property **(which stands for hue, saturation, lightness)**
```CSS
body {
   color: hsl(0, 55%, 15%);
   background-color: hsl(120, 25%, 55%);
 }
```
By slightly tweaking the colors lightness value we can bring our ratio up from 4.5:1 to 5.9:1 just from altering the lightness values slightly. The following code will not output this:

![image](https://i.imgur.com/LtVcWvK.png)

### Avoid Colorblindness Issues by Carefully Choosing Colors that Convey Information
There are various forms of colorblindness. These can range from a reduced sensitivity to a certain wavelength of light to the inability to see color at all. *The most common form is a reduced sensitivity to detect greens.*

For example, if two similar green colors are the foreground and background color of your content, a colorblind user may not be able to distinguish them. **Close colors can be thought of as neighbors on the color wheel, and those combinations should be avoided when conveying important information.**

*(Note: Some online color picking tools include visual simulations of how colors appear for different types of colorblindness. These are great resources in addition to online contrast checking calculators.)*
```css  
button {
    color: #33FF33;
    background-color: #FFFF33;
    font-size: 14px;
    padding: 10px;
  }
```
![image](https://i.imgur.com/q9gQgHy.png)

The button color and button text are neighbors on the color wheel making them almost indistinguishable for color blind users. Let's tweak the colors a little. *(Their lightness values also fail the contrast ratio check)*
```CSS
button {
   color: #003366;
   background-color: #FFFF33;
   font-size: 14px;
   padding: 10px;
 }
```
Changing the button text color to a dark blue should help the lightness ratio, while helping color blind users distinguish the button text color and the button background color.

![image](https://i.imgur.com/4lpXHZ9.png)

## Give Links Meaning by Using Descriptive Link Text
Screen readers do this by reading the link text, or what's between the anchor (a) tags.
**Having a list of "click here" or "read more" links isn't helpful. Instead, you should use brief but descriptive text within the a tags to provide more meaning for these users.**
```HTML
<p>This red nemesis combines both cunning stealth and lightening speed. But
chin up, fellow fighters, our time for victory may soon be near.
<a href="">Click here</a> for information about batteries</p>
```

![image](https://i.imgur.com/pfN1xSZ.png)

Screen readers that read over an `a` link that just says "click here" aren't very useful, let's change it to be descriptive.
```HTML
<p>This red nemesis combines both cunning stealth and lightening speed. But
chin up, fellow fighters, our time for victory may soon be near.
<a href="">Click here for information about batteries</a></p>
```

![image](https://i.imgur.com/fbzwfP4.png)

This will be much more valuable to screen readers as they can get a sense of what the link is instead of simply just "click here"

## Make Links Navigable with HTML Access Keys
HTML offers the accesskey attribute to specify a shortcut key to activate or bring focus to an element. This can make navigation more efficient for keyboard-only users.

HTML5 allows this attribute to be used on any element, but it's particularly useful when it's used with interactive ones. This includes links, buttons, and form controls.

Here's an example:
```HTML
<button accesskey="b">Important Button</button>
```
Here's another:
```HTML
<h2><a id="first" href="#" accesskey="g">The Garfield Files: Lasagna as Training Fuel?</a></h2>
```
## Using the `tabindex` attribute

### Use tabindex to Add Keyboard Focus to an Element
The HTML `tabindex` attribute has three distinct functions relating to an element's keyboard focus. When it's on a tag, it indicates that element can be focused on. The value (an integer that's positive, negative, or zero) determines the behavior.

Certain elements, such as links and form controls, automatically receive keyboard focus when a user tabs through a page. It's in the same order as the elements come in the HTML source markup. This same functionality can be given to other elements, such as `div`, `span`, and `p`, by placing a `tabindex="0"` attribute on them. Here's an example:
```html
<div tabindex="0">I need keyboard focus!</div>
```
Here's another using `tabindex` on a `p` tag:
```HTML
<p tabindex="0">Instructions: Fill in ALL your information then click <b>Submit</b></p>
```
As a bonus using `tabindex` also enables the CSS pseudo-class `:focus` to work on the `p` tag.
```CSS
p:focus {
    background-color: yellow;
  }
```
The output *(when highlighted/focused on)* will now look like this:

![image](https://i.imgur.com/hxYxlhI.png)

### Use tabindex to Specify the Order of Keyboard Focus for Several Elements
The `tabindex` attribute also specifies the exact tab order of elements. This is achieved when the value of the attribute is set to a positive number of 1 or higher.

Setting a `tabindex="1"` will bring keyboard focus to that element first. Then it cycles through the sequence of specified tabindex values (2, 3, etc.), before moving to default and `tabindex="0"` items.

*(It's important to note that when the tab order is set this way, it overrides the default order (which uses the HTML source). This may confuse users who are expecting to start navigation from the top of the page. This technique may be necessary in some circumstances, but in terms of accessibility, take care before applying it.)*

Here's an example:
```HTML
<div tabindex="1">I get keyboard focus, and I get it first!</div>

<div tabindex="2">I get keyboard focus, and I get it second!</div>
```
This will give the first div keyboard focus as it has the value of 1.
