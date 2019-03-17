# CSS Best Practice 
When starting to style a page:

### 1. Make it Readable
### 2. Use Reset and Normalize CSS
### 3. Organize the Stylesheet

Use a top-down format that follows the flow of the page:

i) Generic Element (body, a, p, h1, etc.)
ii) .header
iii) .nav
iv) .wrapper

Also, use commented CSS like below:

```css
/* header */
styles goes here...
/****** navigation ******/
styles goes here...
/****** main content ******/
styles goes here...
/****** footer ******/
styles go here...
```

## 4. Combine CSS Elements

Elements during a stylesheet typically share properties. Rather than re-writing previous code, why not simply mix them? As an example, your h1, h2, and h3 components would possibly share identical font and color. Hence you can combine the same:

```css
h1, h2, h3 {
    font-family: verdana;
    color: #e1e1e1;
}
```
## 5. Use Appropriate Naming Convention

```css
.header-main {
background: #ccc
}
section-gallery {
  width: 100%;
}
```
## 6. Always avoid inline styling
## 7. Always use External CSS

## 8. Shorthand CSS

Use shorthand properties and values. Most properties and values have acceptable shorthand alternatives.

```css 
mg {
    margin-top: 5px;
    margin-right: 10px;
    margin-bottom: 5px;
    margin-left: 10px;
}

img {
    margin: 5px 10px;
} 
``````
## 9. Minify CSS file size with CSS Compressors

It’s an excellent thought to minify the CSS file to reduce the file size. Through this, you can help browsers to accelerate the stacking of your CSS codes. So you can use a tool like CSS Compressor and Minifier to get this going.

You can minify your CSS here: https://csscompressor.net/

# TIPS

group css by: 
* Layout Properties (position, float, clear, display)
* Box Model Properties (width, height, margin, padding)
* Visual Properties (color, background, border, box-shadow)
* Typography Properties (font-size, font-family, text-align, text-transform)
* Misc Properties (cursor, overflow, z-index)

[“Outside In” — Ordering CSS Properties by Importance](https://webdesign.tutsplus.com/articles/outside-in-ordering-css-properties-by-importance--cms-21685)



Other tips
* add max width e.g 1100px - wide screen
* Give all sections padding in one declaration
* Create one class for repeated styles (buttons, headers )
* Add font size, font family and color of most used text to body element
* Give styling to all headers in 1 declaration (h1, h2)
* Use a background color as well as a background image incase the image fails.
*  add hover to nav anchor

### Planning

- Consistency: What is repeated?
- Content first
- What elements are reused, where?
- Do containers have consistent padding or margin?
- Fixed size? Responsive design... what if content changed?

---

> I am not looking for a pixel perfect design, I am looking for a responsive design, that resizes well

---

### Do a bit of prototyping

HTML sectioning elements first

Think about your boxes…

Layout early, test it

---

### Naming things

- What am I targeting?
- Do I want to target all of them on the whole site, or just for this particular use case?
- ...as that will inform how you target an element to change its styling

---

> I want to see classes being used

---

### The *cascade* is really important

Remember for now, what comes last is added last

It overrides what has been declared before

---

### CSS File Order

```css
/* 1) Layout */
Stuff to lay out your page structure

/* 2) Generic */
Fonts, colours, bullet point styles, link hover state, forms

/* 3) Specific */
Page/content specific, e.g. this one button
```
---

> Don't worry it's going to get messy, we'll talk more about file structure and order with next weeks project

---

### Browsers add styles

Start clean - add reset.css

[https://meyerweb.com/eric/tools/css/reset/](https://meyerweb.com/eric/tools/css/reset/)

- Google it :)
- Either
	- Copy and paste it into the TOP of your CSS
	- Create a new file `reset.css` and remember to include it in your build

---

### Normalize

> Normalize.css is a small CSS file that provides better cross-browser consistency in the default styling of HTML elements.

[https://necolas.github.io/normalize.css/](https://necolas.github.io/normalize.css/)

- Download it
- Set it as first stylesheet
- Then pull in your stylesheet

---

### Use comments!

HTML
```
<div class=“header”>

</div><!-- /.header -->
```

CSS
```css
/* forms, input and buttons */
form {
	border: 1px solid red;
}
```

---

### Start as you mean to go on

- Keep your code neat
	- indenting
	- spacing
- keep CSS structured/organised
- USE DEVTOOLS!!

---

### Folder structure & filenames

- lowercase
- NO spaces, use underscore _ or hyphen -
- pick a style and stick to it
- new-january-newsletter-logo.jpg

---

### Something like

- index.html
- styles
	- reset.css
	- style.css
- fonts
	- font files here
- images
	- myimage.jpg
- scripts
 	- javascript would go here

---


