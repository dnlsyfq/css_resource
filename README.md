# Padding & Margin

padding property adds space inside the element. The margin property adds space around the element. Each of these two properties has top, left, bottom and right sub-properties.

# Color 

* color - this property styles an element’s foreground color.
* background-color - this property styles an element’s background color.

```
selector | class | id {
  color: 'black';
  color: #000000;
  color: rgb(0,0,0);
  color: hsl(0,%,%); // hue saturation lightness // The first number represents the degree of the hue, and can be between 0 and 360. The second and third numbers are percentages representing saturation and lightness respectively // Red is 0 degrees, Green is 120 degrees, Blue is 240 degrees, and then back to Red at 360
  color: hsla(34, 100%, 50%, 0.1); //The first three values work the same as hsl. The fourth value (which we have not seen before) is the alpha(opacity) // Alpha can only be used with HSL and RGB colors
  background-color: black;
}
```

# Typography

fonts.google.com

```
selector | class | id {
  font-family: Garamond | "Courier New";
  font-weight:bold|normal|300|800;
  font-style:italic;
  word-spacing: .05em;
  letter-spacing: .03em;
  text-transform: uppercase|lowercase;
  text-align:;
  line-height:;
}
```
import fonts directly into stylesheets with the @font-face property
```
@font-face {
  font-family: 'Space Mono';
  font-style: normal;
  font-weight: 700;
  src: local('Space Mono Bold'), local('SpaceMono-Bold'), url(https://fonts.gstatic.com/s/spacemono/v5/i7dMIFZifjKcF5UAWdDRaPpZUFWaHi6WZ3Q.woff2) format('woff2');
  unicode-range: U+0000-00FF, U+0131, U+0152-0153, U+02BB-02BC, U+02C6, U+02DA, U+02DC, U+2000-206F, U+2074, U+20AC, U+2122, U+2191, U+2193, U+2212, U+2215, U+FEFF, U+FFFD;
}
```

using @font-face with local fonts
```
@font-face {
  font-family: "Roboto";
  src: url(fonts/Roboto.woff2) format('woff2'),
       url(fonts/Roboto.woff) format('woff'),
       url(fonts/Roboto.tff) format('truetype');
}
```
e.g.
```
@font-face {
  font-family: "Glegoo";
  src: url(../fonts/Glegoo-Regular.ttf) format("truetype")
}


```

400 is the default font-weight of most text.
700 signifies a bold font-weight.
300 signifies a light font-weight.

```
header {
  font-weight: 800;
}
 
footer {
  font-weight: 200;
}
```

```
font-style: italic | normal;
```
### word spacing

 The default amount of space between words is usually 0.25em and can be set with the value normal. If you provide a value for word-spacing that’s not normal, then the value you provide is added to the default spacing. Therefore, since the word-spacing is set to 0.3em, your <h1> elements get a total of 0.55em word spacing when rendered.
  
  
```
h1 {
  word-spacing: 0.3em;
}
```

### letter spacing 


```
h1 {
  letter-spacing: 0.3em;
}
```

### text transformation

```
h1 {
  text-transform: uppercase;
}
```

### text alignment

```
h1 {
  text-align: right|center|left;
}
```

### line height

```
p {
  line-height: 1.4;
}
```

* serif
> fonts that have extra details on the ends of each letter. Examples include fonts like Times New Roman or Georgi

* sans serif
> fonts that do not have extra details on the ends of each letter. 


```
h1 {
  font-family: "Garamond", "Times", serif;
}
```
* fonts.google.com

## linking fonts 

```
<head>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans" rel="stylesheet">
</head>
```

```
<head>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans&family=Playfair+Display" rel="stylesheet">
</head>
```

Multiple linked fonts, along with weights and styles. Here Open Sans has font weights of 400, 700, and 700i, while Playfair Display has font weights of 400, 700, and 900i

```
<head>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,400;0,700;1,700&family=Playfair+Display:ital,wght@0,400;0,700;1,900" rel="stylesheet">
</head>
```
* import font

to import fonts directly into stylesheets with the @font-face property.

@font-face{
  font-family:;
  font-style:;
  font-weight:;
  src:local('Space Mono'), local('SpaceMono-Regular'), url(https:// )('woff2');
}

```
@font-face {
  font-family: "Roboto";
  src: url(fonts/Roboto.woff2) format('woff2'),
       url(fonts/Roboto.woff) format('woff'),
       url(fonts/Roboto.tff) format('truetype');
}
```

---

# Box Model
to understand how elements are positioned and displayed on a website.

* height
* width
* padding
* border
* margin
* overflow

<center><img src="images/diagram-boxmodel_Updated_1-01.svg"></center>

* width and height
> specifies the width and height of the content area

* padding
> specifies amount of space between the content area and the border

* border
> specifies the thickness and style of the border surrounding the content area and padding

* margin
> specifies the amount of space between the border and the outside edge of the element

## Height and width 
element’s content has two dimensions: a height and a width
```
selector {
  height:px;
  width:px;
}
```
## Border
surround an elements 
```
selector {
  border: <width>px <style none|dotted|solid>  <color>;
  border-radius: px | 100%; 
}
```
## Padding
space between contents and border 
```
selector {
  padding:;
  padding-top:;
  padding-right:;
  padding-bottom:;
  padding-left:;
  padding: top right bottom left;
  padding: top&bottom left|right;
}
```

## Margin
space directly outside the box , used to specify this space 
```
selector {
  margin: px;
  margin-top: ;
  margin-bottom: ;
  margin-right: ;
  margin-left: ;
}
```
* Margin
0 sets the top and bottom margins to 0 pixels, auto value instructs the browser to adjust the left and right margins until the element is centered within its containing element.
```
div {
  margin: 0 auto;
}

# In order to center an element, a width must be set for that element. Otherwise, the width of the div will be automatically set to the full width of its containing element

div.headline {
  width: 400px;
  margin: 0 auto;
}

```

## Minimum and Maximum Height and Width
properties that can limit how narrow or how wide an element’s box can be sized to.

* min-width — this property ensures a minimum width of an element’s box.
* max-width — this property ensures a maximum width of an element’s box.
* min-height — this property ensures a minimum height for an element’s box.
* max-height — this property ensures a maximum height of an element’s box

```
p {
  min-width: 300px;
  max-width: 600px;
}

p {
  min-height: 150px;
  max-height: 300px;
}
```
## Overflow
controls what happens to content that spills, or overflows, outside its box.
* hidden - when set to this value, any content that overflows will be hidden from view.
* scroll - when set to this value, a scrollbar will be added to the element’s box so that the rest of the content can be viewed by scrolling.
* visible - when set to this value, the overflow content will be displayed outside of the containing element
```
p {
  overflow: scroll; 
}
```
## Resetting Default
default stylesheets are known as user agent stylesheets.
User agent stylesheets often have default CSS rules that set default values for padding and margin. This affects how the browser displays HTML elements, which can make it difficult for a developer to design or style a web page.

Many developers choose to reset these default values so that they can truly work with a clean slate.
```
* {
  margin: 0;
  padding: 0;
}
```
Note that both properties are both set to 0. When these properties are set to 0, they do not require a unit of measurement.

## Visibility
Elements can be hidden from view with the visibility property.

The visibility property can be set to one of the following values:

* hidden — hides an element.
* visible — displays an element.
```
<ul>
  <li>Explore</li>
  <li>Connect</li>
  <li class="future">Donate</li>
<ul>

.future {
  visibility: hidden;
}
```
Note: What’s the difference between display: none and visibility: hidden? An element with display: none will be completely removed from the web page. An element with visibility: hidden, however, will not be visible on the web page, but the space reserved for it will.

## New Box Model
targets all elements on the web page and sets their box model to the border-box model.
```
* {
  box-sizing: border-box;
}
```
You probably didn’t see a difference in the web page to the right - that’s ok! The new box model simply makes sure that the dimensions of elements remains the same regardless of border width and padding.


In the default box model, box dimensions are affected by border thickness and padding.
The box-sizing property controls the box model used by the browser.
The default value of the box-sizing property is content-box.
The value for the new box model is border-box.
The border-box model is not affected by border thickness or padding.
---
# Display and Positioning

Flow of HTML

A browser will render the elements of an HTML document that has no CSS from left to right, top to bottom, in the same order as they exist in the document. This is called the flow of elements in HTML.

In addition to the properties that it provides to style HTML elements, CSS includes properties that change how a browser positions elements. These properties specify where an element is located on a page, if the element can share lines with other elements, and other related attributes.

## Position
Block-level elements like these boxes create a block the full width of their parent elements, and they prevent other elements from appearing in the same horizontal space. 

The default position of an element can be changed by setting its position property. 
```
<div class="boxes"></div>
<div class="boxes"></div>

.boxes {
  width: 120px;
  height: 70px;
  position: 
}
```

* Position: Relative
 to modify the default position of an element is by setting its position property to relative
 ```
 .box-bottom {
  background-color: DeepSkyBlue;
  position: relative;
  top: 20px;
  left: 50px;
}

 ```
* Position: Absolute
When an element’s position is set to absolute all other elements on the page will ignore the element and act like it is not present on the page. The element will be positioned relative to its closest positioned parent element.
```
.box-bottom {
  background-color: DeepSkyBlue;
  position: absolute;
  top: 20px;
  left: 50px;
}
```
* Position: fixed
fix an element to a specific position on the page (regardless of user scrolling) by setting its position to fixed.
often used for navigation bars on a web page
```
.box-bottom {
  background-color: DeepSkyBlue;
  position: fixed;
  top: 20px;
  left: 50px;
}
```
## Z-Index
z-index property controls how far “back” or how far “forward” an element should appear on the web page when elements overlap. This can be thought of the depth of elements, with deeper elements appearing behind shallower elements.
```
# We changed position to relative, because the z-index property does not work on static elements. The z-index of 2 moves the .box-top element forward, because it is greater than the .box-bottom z-index, 1

.box-top {
  background-color: Aquamarine;
  position: relative;
  z-index: 2;
}

.box-bottom {
  background-color: DeepSkyBlue;
  position: absolute;
  top: 20px;
  left: 50px;
  z-index: 1;
}
```
## Inline Display
three values for the display property: inline, block, and inline-block
```
<div class="rectangle">
  <p>I’m a rectangle!</p>
</div>
<div class="rectangle">
  <p>So am I!</p>
</div>
<div class="rectangle">
  <p>Me three!</p>
</div>

.rectangle {
  display: inline-block;
  width: 200px;
  height: 300px;
}
```

## Float 
to specify the exact position of an element using offset properties. If you’re simply interested in moving an element as far left or as far right 

```
.boxes {
  width: 120px;
  height: 70px;
}

.box-bottom {
  background-color: DeepSkyBlue;
  float: right;
}
```
## Clear

float property can also be used to float multiple elements at once. However, when multiple floated elements have different heights, it can affect their layout on the page. Specifically, elements can “bump” into each other and not allow other elements to properly move to the left or right.

The clear property specifies how elements should behave when they bump into each other on the page

left — the left side of the element will not touch any other element within the same containing element.
right — the right side of the element will not touch any other element within the same containing element.
both — neither side of the element will touch any other element within the same containing element.
none — the element can touch either side.
```
# In the example above, all <div>s on the page are floated to the left side. The element with class special did not move all the way to the left because a taller <div> blocked its positioning. By setting its clear property to left, the special <div> will be moved all the way to the left side of the page.

div {
  width: 200px;
  float: left;
}

div.special {
  clear: left;
}
```
---

# Responsive Design
## Em
One unit of measurement you can use in CSS to create relatively-sized content is the em, written as em .
the em represents the size of the base font being used. For example, if the base font of a browser is 16 pixels (which is normally the default size of text in a browser), then
> 1 em is equal to 16 pixels. 2 ems would equal 32 pixels, and so on.
```
.splash-section {
  font-size: 18px;
}

.splash-section h1 {
  font-size: 1.5em;
}
```
## rem
Rem stands for root em. It acts similar to em, but instead of checking parent elements to size font, it checks the root element.
Most browsers set the font size of <html> to 16 pixels, so by default rem measurements will be compared to that value
  
```
# In the example above, the font size of the root element, <html>, is set to 20 pixels. All subsequent rem measurements will now be compared to that value and the size of h1 elements in the example will be 40 pixels.

html {
  font-size: 20px;
}

h1 {
  font-size: 2rem;
}
```

## Percentages: Height & Width
To size non-text HTML elements relative to their parent elements on the page you can use percentages.

Percentages are often used to size box-model values, like width and height, padding, border, and margins. They can also be used to set positioning properties (top, bottom, left, right).

```
# When percentages are used, elements are sized relative to the dimensions of their parent element (also known as a container)

.main {
  height: 300px;
  width: 500px;
}

.main .subsection {
  height: 50%;
  width: 50%;
}
```

## Percentages: Padding & Margin
Percentages can also be used to set the padding and margin of elements.

When height and width are set using percentages, you learned that the dimensions of child elements are calculated based on the dimensions of the parent element.

When percentages are used to set padding and margin, however, they are calculated based only on the width of the parent element.
```
.images {
  margin-bottom:20%;
}
```

## Width: Minimum & Maximum
limit how wide an element. When a browser window is narrowed or widened, text can become either very compressed or very spread out, making it difficult to read. These two properties ensure that content is legible by limiting the minimum and maximum widths.

* min-width — ensures a minimum width for an element.
* max-width — ensures a maximum width for an element.
```
p {
  min-width: 300px;
  max-width: 600px;
}
```
## Height: Minimum & Maximum
limit the minimum and maximum height of an element.

* min-height — ensures a minimum height for an element’s box.
* max-height — ensures a maximum height for an element’s box.

```
p {
  min-height: 150px;
  max-height: 300px;
}
```
## Scaling Images and Videos
 make sure that it is scaled proportionally so that users can correctly view it
```
.container {
  width: 50%;
  height: 200px;
  overflow: hidden;
}

.container img {
  max-width: 100%;
  height: auto;
  display: block;
}
```
## Scaling Background Images
```
body {
  background-image: url('#');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
```

## Media Queries
With media queries, CSS can detect the size of the current screen and apply different CSS styles depending on the width of the screen.

```
media query defines a rule for screens smaller than 480
# @media — This keyword begins a media query rule and instructs the CSS compiler on how to parse the rest of the rule.
# only screen — Indicates what types of devices should use this rule. In early attempts to target different devices, CSS incorporated different media types (screen, print, handheld). The rationale was that by knowing the media type, the proper CSS rules could be applied. However, “handheld” and “screen” devices began to occupy a much wider range of sizes and having only one CSS rule per media device was not sufficient. screen is the media type always used for displaying content, no matter the type of device. The only keyword is added to indicate that this rule only applies to one media type (screen).
# and (max-width : 480px) — This part of the rule is called a media feature, and instructs the CSS compiler to apply the CSS styles to devices with a width of 480 pixels or smaller.
# CSS rules are nested inside of the media query’s curly braces. The rules will be applied when the media query is met. In the example above, the text in the body element is set to a font-size of 12px when the user’s screen is less than 480px.

@media only screen and (max-width: 480px) {
  body {
    font-size: 12px;
  }
}

```
```
# When the screen is less than 480px wide, give the .page-title class a width of 270px.

@media only screen and (max-width: 480px){
  .page-title{
    width:270px;
  }
}
```
## Range
Specific screen sizes can be targeted by setting multiple width and height media features
```
@media only screen and (min-width: 320px) and (max-width: 480px) {
    /* ruleset for 320px - 480px */
}
```

## Dots Per Inch (DPI)
To target by resolution, we can use the min-resolution and max-resolution media features. These media features accept a resolution value in either dots per inch (dpi) or dots per centimeter (dpc).

```
@media only screen and (min-resolution: 300dpi) {
    /* CSS for high resolution screens */
}
```

## And Operator
and operator can be used to require multiple media features.

## Comma Separated List
If only one of multiple media features in a media query must be met, media features can be separated in a comma separated list.

if we needed to apply a style when only one of the below is true:

* The screen is more than 480 pixels wide
* The screen is in landscape mode
```
@media only screen and (min-width: 480px), (orientation: landscape) {
    /* CSS ruleset */
}
```

