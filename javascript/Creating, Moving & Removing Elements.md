# Creating, Moving & Removing Elements

- 6 Creating, Moving & Removing Elements
   - 6.1 Creating Elements.
   - 6.2 Document Fragments
   - 6.3 Inserting/Moving Elements.
   - 6.4 Removing Elements.
   - 6.5 Additional Resources.

### 6.1 Creating Elements.

You can create elements and add them to the page using appendChild():
```js
// create a new <p> element and store it in a variable
let p = document.createElement("p");

// set the text inside the <p> to "A paragraph"
p.textContent= "A paragraph";

let container = document.getElementById("container");
container.appendChild(p);// append the new <p> to the container
```
_Don’t use_ innerHTML _to add elements!_

### 6.2 Document Fragments

Every time you add an element to the DOM the browser will redraw the webpage. This can be quite a slow process. If we’re only adding a few items to the DOM then it probably won’t have a huge affect on performance, but if we were adding 1,000 items it could be noticeably slower. 

Rather than appending items to the DOM one by one, we can use a **Document Fragment** to prepare them all, and then add them in one go.
```js
// the list is already on the page, so if we append
// to it we will cause a redraw
let list = document.getElementById("list");
let fragment =document.createDocumentFragment();

for(let i = 0 ; i< 1000 ; i+= 1 ) {
let el= document.createElement("li");
el.textContent ="Blah";

// append to the document fragment
// this isn't on the page, so won't cause a redraw
fragment.appendChild(el);
}

// append the fragment once
// this appends all 1000 items in one go
// so we only get one redraw instead of 1000
list.appendChild(fragment);
```
### 6.3 Inserting/Moving Elements.

Sometimes we want to move the position of elements or insert elements that are not currently on the page.

We can use the appendChild()and insertBefore()methods to do this:
```js
// create a new element
let p = document.createElement("p");
p.textContent= "Hello, world";

// select an existing element
let container = document.getElementById("container");

// puts the paragraph inside the container as the last element
container.appendChild(p);
// puts the paragraph inside the container as the first element
container.insertBefore(p, container.firstElementChild);
```

If the element already exists on the page, running these commands will move the element around the page.

We can also use the insertAdjacentElement method to place elements.
```js
// add the element before the target
target.insertAdjacentElement("beforebegin", element);

// add the element after the target
target.insertAdjacentElement("afterend", element);
```
The first argument can take one of four strings:

1. "beforebegin": before the element itself
2."afterbegin": just inside the element, before its first child
3. "beforeend": just inside the element, after its last child
4."afterend": after the element itself

### 6.4 Removing Elements.

You can remove elements from a page use the.remove()method:
```js
// find the element with id mobile-nav
let mobileNav = document.getElementById("mobile-nav");

// remove the element from the page
mobileNav.remove();

// we can reinsert the item later
document.body.insertBefore(mobileNav,document.body.firstElementChild);
```

#### jQuery
jQuery is JavaScript library that makes working with the DOM much nicer - it can also support browsers going back to IE8.
```js
// selecting
// native DOM
let items= Array.from(document.querySelectorAll(".menu_item"));
// jQuery
let items= $(".menu_item");

// prepending
// native DOM
body.insertBefore(mobileNav, body.firstElementChild);
// jQuery
body.prepend(mobileNav);

// setting text and adding a class in native DOM
body.textContent= "Blah";
body.classList.add("foo");

// setting text and adding a class in jQuery
body.text("Blah").addClass("foo");
```
Over the years browsers have slowly adopted many of the jQuery methods and concepts like remove and querySelector.

If you’re working on a site that already uses jQuery you’d be mad not to use it. However, jQuery is an additional download, so you shouldn’t add it to sites unless you’re using it a lot.

### 6.5 Additional Resources.

- MDN: Document Fragments
- The problem with innerHTML
- jQuery: Getting Started
