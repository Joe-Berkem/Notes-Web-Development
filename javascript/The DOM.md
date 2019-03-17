# The DOM

- 2 The DOM
   - 2.1 Selecting Individual Elements
   - 2.2 Storing Elements
   - 2.3 Adding and Removing Classes
   - 2.4 Additional Resources.

The DOM ( **Document Object Model** ) is how JavaScript represents the HTML on a web page. It turns the elements from the HTML into a JavaScript object that represents the hierarchy of elements.

In all browsers there is a global object called document that allows us to interact with the DOM.
```js
console.log(document);
```
The document object has three important properties that represent the main parts of a page:
```js
document.documentElement;// the < html > element
document.head;// the head element
document.body;// the body element
```
These properties represent **HTML Element** objects, which share various properties and methods that we’ll be learning about tomorrow.


### 2.1 Selecting Individual Elements

The document object also has methods that allow us to select elements.

#### ID
You can use document .getElementById( ) to get an element using its id:
```js
// get the container element on a page
let container = document.getElementById("container");
```
This returns an HTML Element object representing which ever element in the document has the given ID.

This is the most efficient way to select an element from the DOM - but ids need to be unique, so you can’t always use this.

#### querySelector

You can also use almost any CSS selector to get an element:
```html
<html>
  <body>
    <section id="container">
      <ul>
        <li class="menu__item"><a href="/about">About</a></li>
        <li class="menu__item"><a href="/contact">Contact</a></li>
      </ul>
    </section>
  </body>
</html>
```
```js
// returns first matching element
let list = document.querySelector("ul") // the ul element

// the first item with menu__item class
let firstMenuItem= document.querySelector(".menu__item")
```
This method also returns an HTML Element object.
```js
document.querySelector (".className") // will return the first element with that class.
```

### 2.2 Storing Elements

Once you’ve selected an element, it’s a good idea to store it in a variable so that you
can do things with it later:

```js
// a variable holding the #container element
let container = document.getElementById("container");
let body = document.body;// a variable holding the <body> element

// later on...
// do some things with container
container.classList.add("current");
```

If you only use an element once in your code then you don’t necessarily need to
store it in a variable, but it’s good to get used to doing it.


#### IIFEs with Arguments

You’ve probably noticed that we’re using document a lot. We can save ourselves a little bit of typing by passing in an argument to our IIFE:

```js
// call whatever the first argument is d
( d => {
// now inside our IIFE we can use d instead of document
d.getElementById("foo");
}) (document);// pass the document object in as the first argument
```
You don’t have to call the argument d, you could use doc or anything else, but d is nice and short and fairly obvious. Just don’t use a variable named d for anything else inside your IIFE.

### 2.3 Adding and Removing Classes

Once we’ve got our element, we can start to do things with it. One of the most useful things you can do is add and remove classes in order to change how it appears on screen:
```js
let container = document.getElementById("container");

// Add the current class to the #container
container.classList.add("current");

// Remove the hidden class from the #container
container.classList.remove("hidden");
```

### 2.4 Additional Resources.

- Eloquent JavaScript: The DOM
- MDN:HTMLElement
- MDN:classList
- CSS Selectors
- I Love My IIFE
