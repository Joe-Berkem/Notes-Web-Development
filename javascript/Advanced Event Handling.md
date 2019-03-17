# Advanced Event Handling

- 8 Advanced Event Handling
   - 8.1 The Event Object.
   - 8.2 .preventDefault().
   - 8.3 Bubbling.
      - 8.3.1 Event Delegation
   - 8.4 Additional Resources.

### 8.1 The Event Object.

Whenever you set up an event handler the first argument passed to your function is the **event object**.
```js
let input = document.getElementById("input");

input.addEventListener("keyup", event=>{
if (event.key === "Escape") {
input.value= "";
}
});
```
The event object has all sorts of useful properties:

- Keyboard events: The key that was pressed (event.key)
- Mouseevents: Thecoordinatesofthemouse(event.clientX,event.clientY)
- The event type, e.g.mousedown(event.type)


### 8.2 .preventDefault().

Bydefaultthebrowserwillrunthefunctionandthenresumeitsnormalbehaviour.

For example, if you registered aclickevent on a link, the browser would run your code, but then follow the link, which would load a new page. You can prevent this using 
```js
event.preventDefault():

let link = document.getElementById("link");

link.addEventListener("click", event=> {
event.preventDefault();

// do something...
});
```
This will be necessary for any event that navigates away from the current page, e.g. submitting a form, clicking a link

### 8.3 Bubbling.

Events **bubble** up the page hierarchy: all parent elements of the element that the
event was fired on will also fire the event.
```js
<div id="container">
  <ul>
    <li>
      <a href="/link">Link</a>
    </li>
  </ul>
</div>
```
We can use event.target to find out which element the event originated from.
```js
let container = document.getElementById("container");

container.addEventListener("click", event=>{
let clicked=event.target;
clicked.classList.add("clicked");
});
```

#### 8.3.1 Event Delegation

This allows to add an event for multiple items in an efficient manner:
```js
<ul id="list">
  <li><a href="/one">One</a></li>
  <li><a href="/two">Two</a></li>
  <li><a href="/one-thousand">One Thousand</a></li>
</ul>
```
We can listen on the parent< ul >rather than setting up an event handler for every list item:
```js
let list = document.getElementById("list");

list.addEventListener("click", e =>{
let clicked= e.target;

// only add class if it's a link
if (clicked.tagName ==="A") {
e.preventDefault();
clicked.classList.add("clicked");
}
});

.matches()
```
Sometimes when we’re using event delegation our conditional might get quite complicated. If that’s the case we can use the.matches()method to check if the element matches a given CSS selector.
```js
<ul id="list">
  <li class="list-item">
    <a href="/one">One</a>
  </li>
  <li class="list-item">
    <a href="/two">Two</a>
  </li>

  <li class="list-item current">
    <a href="/one-thousand">One Thousand</a>
  </li>
</ul>

let list= document.getElementById("list");

list.addEventListener("click", e=>{
letclicked= e.target;

// only add class if it matches the given CSS selector
if(clicked.matches("li.list-item.current a")) {
e.preventDefault();
clicked.classList.add("clicked");
}
});
```
### 8.4 Additional Resources.

- How JavaScript Event Delegation Works
- MDN:.matches()
- Debouncing & Throttling

