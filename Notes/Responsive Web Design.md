# Introduction to the Responsive Web Design
There are many types of devices that can access the web. They range from large desktop computers to small mobile phones. These devices have different screen sizes, resolutions, and processing power.

Responsive Web Design is an approach to designing web content that responds to the constraints of different devices. The page structure and CSS rules should be flexible to accommodate these differences.

In general, design the page's CSS to your target audience. If you expect most of your traffic to be from mobile users, take a 'mobile-first' approach. Then add conditional rules for larger screen sizes. If your visitors are desktop users, then design for larger screens with conditional rules for smaller sizes.

CSS gives you the tools to write different style rules, then apply them depending on the device displaying the page. This section will cover the basic ways to use CSS for Responsive Web Design.

Here's a great site for a refresher on responsive design:

https://www.w3schools.com/html/html_responsive.asp


## Create a Media Query
Media Queries are a new technique introduced in CSS3 that change the presentation of content based on different viewport sizes. The viewport is a user's visible area of a web page, and is different depending on the device used to access the site.

Media Queries consist of a media type, and if that media type matches the type of device the document is displayed on, the styles are applied. You can have as many selectors and styles inside your media query as you want.

Here's an example of a media query that returns the content when the device's width is **less than or equal to** 100px:
```css
@media (max-width: 100px) { /* CSS Rules */ }
```
and the following media query returns the content when the device's height is **more than or equal to** 350px:
```css
@media (min-height: 350px) { /* CSS Rules */ }
```
*Remember, the CSS inside the media query is applied only if the media type matches that of the device being used.*

**(Note: `max-width/height` means LESS THAN OR EQUAL TOO. While `min-width/height` means GREATER THAN OR EQUAL TOO)**

Refer to this link: https://www.w3schools.com/howto/howto_css_media_query_breakpoints.asp for more info

## Making an Image Responsive
Making images responsive with CSS is actually very simple. You just need to add these properties to an image:
```CSS
img {
  max-width: 100%;
  height: auto;
}
```
The `max-width` of `100%` will make sure the image is never wider than the container it is in, and the `height` of `auto` will make the image keep its original aspect ratio.

![image](https://i.imgur.com/4AxorP8.png)

Here's an example of an img block that is responsive to the page, and one that isn't. The top one will resize to make sure it is never wider than the container, while the second does not, so it expands past the container.

## Use a Retina Image for Higher Resolution Displays
Pixel density is an aspect that could be different on one device from others and this density is known as Pixel Per Inch(PPI) or Dots Per Inch(DPI).

Due to the difference in pixel density between a "Retina" and "Non-Retina" displays, some images that have not been made with a High-Resolution Display in mind could look "pixelated" when rendered on a High-Resolution display.

The simplest way to make your images properly appear on High-Resolution Displays, such as the MacBook Pros "retina display" is to define their `width` and `height` values as only half of what the original file is.

Here's an example:
```html
<style>
  img { height: 250px; width: 250px; }
</style>
<img src="coolPic500x500" alt="A most excellent picture">
```

## Make Typography Responsive
Instead of using `em` or `px` to size text, you can use viewport units for responsive typography.

Viewport units, like percentages, are *relative units*, but they are based off different items. Viewport units are relative to the viewport dimensions (`width` or `height`) of a device, and percentages are relative to the size of the parent container element.

**Viewport is the browser window size. 1vw = 1% of viewport width. If the viewport is 50cm wide, 1vw is 0.5cm.**

The four different viewport units are:

- `vw` (viewport width): `10vw` would be 10% of the viewport's width.
- `vh` (viewport height): `3vh` would be 3% of the viewport's height.
- `vmin` (viewport minimum): `70vmin` would be 70% of the viewport's smaller dimension (height or width).
- `vmax` (viewport maximum): `100vmax` would be 100% of the viewport's bigger dimension (height or width).

```html
<style>
h2{
    width: 80vw;
}
p{
    width: 75vmin;
}
</style>
```
This code would output

![image](https://i.imgur.com/HDMUQFy.png)

But without the `viewport` sizing it would look like this:

![image](https://i.imgur.com/JOMqCL5.png)

The difference is slight in these examples. but the `p` text width expands to the edge of the container, but with the `width: 75vmin;` is only takes up 75% of the container.
