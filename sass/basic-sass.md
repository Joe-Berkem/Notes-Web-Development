# SASS

Sass is a preprocessor. Most companies use SASS over other alternatives. 

**A browser can not read a SASS file!**

2 file types: 

* .sass (DON'T USE)
* **.scss** 

---
## Variables

```css
$brand-font: Helvetica, sans-serif;
$content-padding: 40px;

p {
font-family: $brand-font;
padding: $content-padding;
}
```

## Nesting
```css
nav {

  ul {
    margin: 0;
    padding: 1px;
  }
  li {
    display block;
  }
}
```

DON'T GO MORE THAN 3- 4 LEVELS DEEP!

You can keep the media queries relevant to specific components by nesting them with the other css.


## Extends

```css
%green-background {
background-color: green;


.header-main {
@extend %green-background;
}

```

## Functions
lighten(green, 10%)

There are color functions, maths.

## Mixins

@mixins 

like functions in sass. 

```css
@mixin border-radius($radius) {
-webkit-border-radius: $radius;
-moz-border-radius: $radius;
-ms-border-radius: $radius;
border-radius: $radius;
}

.box {
include border-radius 10px}
 ```
# Imports
This is now CSS spec

```css 
@import 'reset.css'
```