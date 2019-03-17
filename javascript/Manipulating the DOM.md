# Manipulating the DOM

- 5 Manipulating the DOM
   - 5.1 Querying Elements
   - 5.2 documentandwindowProperties
   - 5.3 Manipulating Elements
   - 5.4 Attributes
   - 5.5 Form Fields.
   - 5.6 Data Attributes.
   - 5.7 Additional Resources.

### 5.1 Querying Elements

You can find out all sorts of information about an element:
```js
let container = document.getElementById("container");

// the height of the element (in pixels)
container.clientHeight;
// the width of the element (in pixels)
container.clientWidth;
// the inline style border colour
container.style.borderColor;
// the border colour - including CSS
window.getComputedStyle(container).borderColor;
// the html inside the element (e.g. "<p>Text</p>")
container.innerHTML;
// the text inside the element (e.g. "Text")
container.textContent;
// returns the position of the element relative to the page
container.getBoundingClientRect();
```
You can store these in variables to use later:
```js
let height = container.clientHeight;
// add 300 pixels to the height of the container
container.style.height= (height+ 300 ) +"px";
```

_It’s always better to not query the DOM if you can avoid it._ If you can use variables to keep track of changes your code will be much easier to understand and it will run faster.

### 5.2 documentandwindowProperties

You can find useful information out about the page^1 :
```js
window.pageYOffset;// the current vertical scroll position
window.pageXOffset;// the current horizontal scroll position

window.innerHeight;// the height of the viewport
window.innerWidth; // the width of the viewport

document.body.clientHeight;// the height of the document
document.body.clientWidth;// the width of the document
```

### 5.3 Manipulating Elements

You can also edit the styling of the element directly by setting sub-properties of the style property:
```js
let container = document.getElementById("container");

container.style.border= "1px solid red";
container.style.position= "absolute";
container.style.left= "20px";
container.style.top= "20px";

// notice we have to write marginTop, not margin-top
// due to property naming rules
container.style.marginTop= "20px";
```
The window object is part of the **BOM** (Browser Object Model). As well as having the window specific 2 properties/methods, it actually represents the **global scope** in a browser. This is part of the **CSSOM** (CSS Object Model) - we do like our object models in JavaScript

You can set the height and width too:
```js
let container = document.getElementById("container");

// make sure you include the units (px in this case)
container.style.height= "200px";
container.style.width= "200px";
```
It is preferable to use CSS classes where you can, but sometimes you will need to use the.styleproperty if the styling is dependent on values calculated by JavaScript.

You can also change the text inside an element:
```js
let title= document.getElementById("title");
title.textContent= "New Title"; // replaces text of #title
```
Be careful, _setting_ .textContent _will remove everything inside the element_.

### 5.4 Attributes

We can query/edit any attribute of an element:
```js
<input id="age" name="age" value="20" />

let input= document.getElementById("age");

input.getAttribute("name");// returns "age"
input.getAttribute("value");// returns "20" (as a string)
input.setAttribute("value", "600");// set the value attribute to "600"
input.removeAttribute("disabled");// remove the disabled attribute
```

### 5.5 Form Fields.

To get the _actual_ value of the input (as opposed to the default value), we can use the .valueproperty: 
```js
input.value; // a string containing the current value of the input
```
The.valueproperty will _always_ return a string - so be careful if you’re doing any addition!

We can also call the.focus()method on a form field to give it focus:
```js
input.focus();// gives the input focus
```
### 5.6 Data Attributes.

Sometimes we want to let JavaScript know something about an element that isn’t a standard property. We can usedata-*attributes for this. For example, if we wanted to store additional information about some books:
```js
<ul id="books">
<li data-id="12"data-author="Marijn Haverbeke">
Eloquent JavaScript
</li>
<li data-id="35"data-author="Douglas Crockford">
JavaScript: The Good Parts
</li>
<li data-id="59"data-author="David Flanagan">
JavaScript: The Definitive Guide
</li>
</ul>
```

We could then access this using the dataset property:
```js
let first= document.getElementById("books").firstElementChild;

if(first) {
console.log(first.dataset.id);
console.log(first.dataset.author);
}
```
You should only usedata-*attributes as a last resort, as reading from the DOM is slow. Ideally the data would be used and stored only in JavaScript.

### 5.7 Additional Resources.

- MDN:window.getComputedStyle()
- MDN:getBoundingClientRect()
- MDN:data-*Attributes
- MDN:window