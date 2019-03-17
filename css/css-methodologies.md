# CSS Methodologies
---
## OOCSS
[Object-oriented CSS](http://oocss.org/)
Encourages reusable, scalable CSS

Example: Button used on site, regardless of code around it

Seperates structure from skin
```css
.skin {
background-color: green;
border: 1pc solid blue;
}
```
---
## Atomic Design
[Atomic Design by Brad Frost](http://atomicdesign.bradfrost.com/)

**Atoms**: elements (p, button, input etc)
**Molecules**: set of elements (serach form etc)
**Organism**: set of molecules (header, footer)
**Templates**: set of organisms (repeated)
**Pages**: final site

---

## BEM
[BEM — Block Element Modifier](http://getbem.com/)
block element modifier

Name convention for classes

(promotional page):

.promo (for the block)
.promo__header
.promo__image

for something that differs
promo__image--half

---

## SMASCSS
[Home - Scalable and Modular Architecture for CSS](https://smacss.com/)

scalable and modular architecture for css

Way of structurring/ organising CSS with conventions
* Base rules
* layout rules 
* module rules
* state rules
* theme rules*

