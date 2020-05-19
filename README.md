# Color 

* color - this property styles an element’s foreground color.
* background-color - this property styles an element’s background color.

```
selector | class | id {
  color: 'black';
  color: #000000;
  color: rgb(0,0,0);
  color: hsl(0,%,%); // hue saturation lightness 
  color: hsla(34, 100%, 50%, 0.1); //a , opacity
}
```

# Typography

fonts.google.com

```
selector | class | id {
  font-family:;
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
  border: <width>px <style> none|dotted|solid <color>;
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
