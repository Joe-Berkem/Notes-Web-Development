# JavaScript in the Browser

- 1 JavaScript in the Browser
   - 1.1 JavaScript Lifecycle
   - 1.2 IIFEs
   - 1.3 Developer Tools
   - 1.3.1 Errors
   - 1.4 Additional Resources

To use JavaScript in the browser we need to use a < script > tag. These go at the bottom of the page and come in two forms:

**Inline**: Can be useful for running tiny bits of code or checking things are working. Generally, it’s better to use external script files.

``` html
<script>
let hello= "Hello, World";
console.log(hello);
</script>
```

**External Script Files** : It’s best to store our JavaScript in separate .jsfiles and then link to them using a src attribute:
```html
<!-- can be relative, absolute, or remote link -->
<script src="js/app.js"></script>
```

**You can’t use a** src **tag and inline JS in the same** < script > **tag** - only one of them will run.

Used to put the script tags in the head. 10 years ago developers started putting the tag at the bottom of the body.

Modern browsers have the **defer** attribute, which means we can put script tags back in the head: 

```html
<defer script src = "js/app.js"></script>
```
Not widely used as yet but likely to be the preferred method moving forward.

For multiple external files, each script is run and loaded in order they are on the page so 1 file can't refer to another file without throwing an error - because it hasn't been loaded yet.

### 1.1 JavaScript Lifecycle

When a browser loads a web page it will load the raw HTML from the server and then work its way through each line of code in order. So if you have multiple **script** tags on your page they will run in the order that they appear in the HTML.

The JavaScript and any variables that you create using it will only exist until you refresh the page: at that point everything starts again from scratch. _Refreshing the page restarts your JavaScript from scratch_

### 1.2 IIFEs: **Immediately Invoked Function Expression**

You can include as many JavaScript files as you like on a webpage, but you might not have written all of them or be aware of the variables that they’ve set up. So we need a way to make sure that the variables we declare don’t clash with variables that may already exist
```js
// perfectly innocent bit of code
// won't work, as browsers already have a top
// variable defined in global scope
let top = 100 ;
console.log(top);
```
We can do this by writing a function - which creates new scope - and then call it immediately:
```js
let start = () =>{
// no problems as top is scoped to the start function
let top = 100 ;
console.log(top);
};

start();
```

You use a single IIFE for all your code. All functions etc are nested within the IFE, you don't need an IIFE for every function etc.
However, this still adds a variable called start to global scope.

We can tidy it up using an **Immediately Invoked Function Expression** :
```js
// create a function
( ( ) => {
// your code here
// any variables will be local
} ) ( );// and call it immediately
```
We write an **anonymous function** , wrap it in brackets, and then call it immediately. Because we don’t assign the function to a variable we’ve not added anything to global scope.

It’s good practice to wrap all of your code in an IIFE to avoid variable naming issues.

**Note** : you don’t need to do this with ES6 modules (which we’ll use later in the course) as they are self-contained by default.

### 1.3 Developer Tools

_Always have the Developer Tools Console open when you’re working with JavaScript in the browser._ (Mac:Cmd+Alt+j/ Windows:Ctrl+Shift+j)

You can use the JavaScript console to experiment with different bits of code if you get stuck.

#### 1.3.1 Errors

If there is a single error in your code nothing will work, so make sure you immediately fix any errors that show up in the console.

You could also add the JavaScript Errors Notifier extension to Chrome. This will let you know if there are errors even if you forget to have Developer Tools open.


### 1.4 Additional Resources.

- Eloquent JavaScript: JavaScript and the Browser
- MDN: IIFEs
- IIFEs in Detail
- Deep Dive into the Murky Depths of Script Loading
- Using the Console
- Beyondconsole.log()
