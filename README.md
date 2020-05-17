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
