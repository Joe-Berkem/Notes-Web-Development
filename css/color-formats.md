# CSS Colour Formats

---

### Colour names

Red, blue, green, purple…

Aliceblue, firebrick, goldenrod(!)

https://en.wikipedia.org/wiki/X11_color_names

---

### Hex

3 bit hexidecimal format

Each single or pair represent R G or B channel

- `#000`
- `#FF0000`
- `#F00`

---

### rgb

Each value 0-255 represents red, green or blue channel

- `rgb(255, 255, 255)`
- `rgb(0, 255, 0)`

---

### rgba

Same as rgb but with alpha (opacity/transparency) channel

- `rgba(255, 255, 255, 1)`
- `rgba(0, 255, 0, 0.5)`

---

### hsl

Like rgb, but each value represents *hue*, *saturation* and *lightness* rather than a colour channel

Hue on the colour wheel 0-360 Saturation & lightness percentage

- `hsl(100, 50%, 50%)`

---

### hsla

Same as before but with alpha channel

- `hsla(200, 20%, 20%, 1)`
- `hsla(0, 80%, 90%, 0.5)`

---

### Anywhere you use a colour value

```css
border: 1px solid #fafafa;
background-color: hsla(146, 56%, 48%, 0.8);
```


---



### Colours
```css
/* Color */

h1  {
	color: red; /*choose from given colours */

	color: #000;
	color: ##ff0000; /*hex codes */
	color: #f00;

	color: rgb(0, 255, 0); /*RGB colors*/

	color: rgba(0, 255, 0, 0.5); /*RGBA colors are RGB with alpha = gives opacity, transparency*/

	color: hsl(100, 50%, 50%); /*hue saturation and lightness. first value is degrees 0-360. next 2 values always percentages.*/

	color: hsla(100, 50%, 50%, 0.5); /*hue saturation and lightness with alpha */

```