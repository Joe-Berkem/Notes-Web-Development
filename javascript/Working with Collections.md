# Working with Collections

- 3 Working with Collections
   - 3.1 Selecting Multiple Elements
   - 3.2 NodeLists and HTML Collections
   - 3.3 Using forEach()
   - 3.4 Additional Resources.

### 3.1 Selecting Multiple Elements

Sometimes you’ll want to work with multiple elements on a page. For example,
you might want all the elements that area particular type or have a particular class.

These methods return an **HTML Collection** :
```js
let menuItems = document.getElementsByClassName("menu__item");
let divs = document.getElementsByTagName("div");
```
These methods return a **NodeList** :
```js
// all items with menu__item class
document.querySelectorAll(".menu__item");
// all the <li> elements
document.querySelectorAll("li");
// all the <a> elements inside <li> elements
document.querySelectorAll("li a");
// any elements with a disabled attribute
document.querySelectorAll("[disabled]");
// the first item
document.querySelectorAll("p:first-child");
// any elements with the list or table class
document.querySelectorAll(".list, .table");
```

### 3.2 NodeLists and HTML Collections

NodeLists and HTML Collections are **array-like objects**, meaning that they sort of act like arrays, but not really.

Generally, we just want to turn them into an actual array so that they behave how we’d expect. We can do this using Array.from():
```js
let items = Array.from(document.getElementsByClassName("menu__item"));
```
Once we’ve turned them into an array we can use the standard array methods like
```js
forEach(),filter(),map(), andreduce().
```
If you forget to convert them into an array then - as well as missing the array methods that you’re used to - there can be some performance issues.

### 3.3 Using forEach()

Once we’ve converted the selection to an array we can use forEach() to work with each item in turn:
```js
let items = Array.from(document.getElementsByClassName("menu__item"));

items.forEach(el=>el.classList.add("spoon"));
```
We use forEach()in this case as many of the DOM methods don’t return useful
values.


##### IDs, Classes, and Prefixes

How do you know when to use an id or aclass?

In CSS you should never use id selectors, as they make it hard to override rules using
cascading. However, in JavaScript it is much more efficient to select elements using an id than a class. If an element can only ever appear in the HTML once, then use an id. Otherwise, use a class

It’s also a good idea to use a special js__prefix on any classes you add for use with JavaScript. Although it can look a little verbose, this means that someone editing the styling for an element won’t accidentally break your JavaScript.
```js
<!-- .list-item is for styling, js__selector is for JavaScript -->
<li class="list-item js__selector">Blah blah</li>
```
You can also add ajs__prefix to anyids - but as ids shouldn’t be used for styling, this is
not strictly necessary.

### 3.4 Additional Resources.

- A Comprehensive Dive into NodeLists
- HTMLCollections and NodeLists
- MDN:Array.from()
- MDN:NodeList
- MDN:HTMLCollection