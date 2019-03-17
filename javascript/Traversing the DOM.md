# Traversing the DOM

- 4 Traversing the DOM
   - 4.1 Relationships.
   - 4.2 Traversal.
   - 4.3 Selecting Children.
   - 4.4 Additional Resources.

### 4.1 Relationships.

The DOM is a **tree** structure, meaning that the elements within it have the following relationships:

- **Parent** : the containing element
- **Child** : the contained element
- **Sibling** : other Child elements with the same Parent
```html
<html>
  <body>
  <h1>Lists!</h1>
  <p>A list</p>
    <ul>
      <li>
        <a href="/one">First Thing</a>
      </li>
      <li>
        <a href="/two">Second Thing</a>
      </li>
      <li>
        <a href="/three">Third Thing</a>
      </li>
    </ul>
  </body>
</html>
```


### 4.2 Traversal.

With the DOM you can get elements using their relationships to other elements:
```js
let body = document.body;// the <body>

let header = body.firstElementChild;// the first child of body, <h1>
let bodyAgain = header.parentElement;// the <body>

let p = header.nextElementSibling;// the <p>
let ul= p.nextElementSibling;// the <ul>
let headerAgain =p.previousElementSibling; // the <h1>
```
You can also get all the children:
```js
let listItems = ul.children;
```
This returns an HTML Collection, so you will want to convert it to an array before you do anything with it.

### 4.3 Selecting Children.

You can use many of the selection methods on any element:
```js
container.getElementsByClassName("menu__item");
container.getElementsByTagName("li");
container.querySelector("li a");
container.querySelectorAll("li a");
```
It can be much more efficient to select a container element (particularly if you use getElementById) and then use these methods to select child elements.

It’s also preferable to use the getElement...methods over the querySelector...methods where you can as they are generally much faster.

### 4.4 Additional Resources.

- How to traverse the DOM
