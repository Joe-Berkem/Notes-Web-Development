# Events

- 7 Events
   - 7.1 Event Driven Programming.
   - 7.2 Window Events
   - 7.3 State
   - 7.4 Additional Resources.
   
### 7.1 Event Driven Programming.

Almost everything you do in JavaScript will be a response to an event. Some examples:

- the page loading
- user clicking an element
- user submitting a form
- user moving the mouse
- resizing the window

Events allow us to respond to a user’s actions.

We use the addEventListener method to tell the browser what we want to happen when the event is **triggered**.

We pass addEventListener a function, which gets called by the browser each time the registered event occurs. We call such a function an **event handler** :
```js
// this runs straight away
console.log("page loaded");

let container = document.getElementById("container");

// this runs when the element is clicked
container.addEventListener("click", () =>console.log("clicked"));

// this runs when the mouse moves over the element
container.addEventListener("mousemove", () =>console.log("mouse moving"));
```
There are all sorts of events:

- keydown: when a key is pressed down
- keyup: when the key is released
- click: when the element is clicked
- mousedown: when the mouse is pressed down
- mouseup: when it comes back up again
- focus/blur: when a form field gets/loses focus
- change/input: fires when a form input changes
- submit: fired on submitting a form

A full list is available on theMDN site

Some events will only apply to specific types of elements (e.g. you can only submit a form)


### 7.2 Window Events

Some events need to be on the window: most usefully, resizing and scrolling the page.
```js
window.addEventListener("scroll", ()=> {
console.log("scrolling");
});

window.addEventListener("resize", ()=> {
console.log("resizing");
});
```
### 7.3 State

Event handlers are **short-lived** : they are triggered by an event, run the code inside, and then they’re done. Any variables that are declared _inside_ an event handler will only exist temporarily.

Your main application code is (comparatively) **long-lived** : any variables will exist as long as the page isn’t refreshed.

This means if we want to keep track of any values _between_ events, we need to make sure the variables live _outside_ our event handlers. This is what we refer to as **state** : variables we use to keep track of changes in our app.
```js
// long-lived variables
letincrement = document.getElementById("increment");

// the state
// keep track of a value that changes over time
letcounter= 0 ;

// event handlers need to refer to variables outside their local scope
// otherwise they can't keep track of anything
increment.addEventListener("click", () =>counter+= 1 );
```
Remember, _you should avoid querying the DOM if you can_. Keep your state in JavaScript and use variables to keep track of changes.


### 7.4 Additional Resources.

- MDN:addEventListener
- State
- Eloquent JavaScript: Events

