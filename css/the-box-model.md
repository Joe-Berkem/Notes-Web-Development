## The Box Model

---

## Every HTML element has a default set of styles

---

One such style is the `display` property

Common default `display` values are `block` & `inline`

Sectioning elements are block, text elements are inline

---

### What are media?
### List item?
### A table

---

## The spec is changing

[https://developer.mozilla.org/en-US/docs/Web/CSS/display](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

---

![box model diagram](day02/03CSSboxModel/boxmodel.png)

---

### `display`

- `inline` |
- `block` |
- `inline-block` |

---

### Let's take a look at the nav

Note:
Display list items as display inline as demonstration, add margins and paddings. Note no width or height!

---

### Let's take a look at the images

Note:
Inline, then block, gaps, no gaps.

---

### Exercise

- Take what you have, add a `.wrapper` div inside the `<body>` element
- Give it a width
- Center it

---

### Googling

- Totally cool
- Check at least 3-4 results
- Check date
- Don't believe w3schools
- Use Stack Overflow with caution

---

### Aside: Let's look at MDN

- Probably the most dependable learning resource
- [https://developer.mozilla.org/en-US/](https://developer.mozilla.org/en-US/)

---

## Moving elements

- `position`
- `transform`

Not for layout, for moving/transforming

Only moves element & contents, not surroundings

---

### position

```
position: static;
position: relative;
position: absolute;
position: fixed;
```

---

### transform

```
transform: translate(10px,10px);
transform: translateX(10px);
transform: scale(x,y);
transform: rotate(30deg) skewX(25deg);
```

Further reading:
David DeSandro's transforms examples: [http://desandro.github.io/3dtransforms/](http://desandro.github.io/3dtransforms/)
CSS Transforms on CSS Tricks: [https://css-tricks.com/almanac/properties/t/transform/](https://css-tricks.com/almanac/properties/t/transform/)

---

### Exercise

- Make your page look like the picture with the things you have learnt

---

## One more thing

---

### Floats

```css
/* you can float left, right or none */
header h1, header nav {
	float: left;
}
```
---

Floating elements make them jump out of the block scope.

Their containing elements can't see them anymore.

We can get around this...

---

Give the containing (parent) element a *Block Formatting Context*

This happens when

- is floated
- is positioned absolute
- is displayed inline-block
- has an overflow property
- has a value other than visible

---

### Floats

```css
header {}

header h1, header nav {
	float: left;
}
```
---















