# Functions

## Contents

- 2 Functions
   - 2.1 Using Functions
      - 2.1.1 Calling Functions.
      - 2.1.2 Fat Arrow.
      - 2.1.3 Examples
      - 2.1.4 Writing Functions
   - 2.2 Scope.
   - 2.3 Recursive Functions
   - 2.4 Additional Resources.
  
In programs we often need to do the same thing multiple times in different places.

Because of this almost all programming languages have the concept of **functions**.

A function is a block of code that performs a specific action. We usually give the function a name, which allows us to use it elsewhere in our code. A function can accept and return values. For example, a function called authorize might accept
a username and password and return true if the combination is valid or false if not.

### 2.1 Using Functions

A function looks like this :
```js
// a function to add two numbers together
// this function gets given two values
function(a, b) {
// it adds the two values together
// and then returns the sum
return a + b;
}
``````
The above function isn’t useful because we haven’t given it a name (an **anonymous** **function** ), so we don’t have any way to use it in our code.

In fact, functions in JavaScript canlook a number of different ways. But a function is a value in JavaScript^2 , so, as with any other value, we can assign

functions to variables:
```js
let add = function(a, b) {
return a + b;
};
```

We can now refer to the function using theaddvariable.

#### 2.1.1 Calling Functions.

Functions do not run until you **call** them. You call a function by using the function name followed by a pair of brackets.

When you call it, you can send a function values (known as **arguments** ) which it can use.

For example, the add function takes two arguments:

```js
add( 1 , 2 );// call add, passing the values 1 and 2
add( 3 , 7 );// call add, passing the values 3 and 7
```
The arguments are passed to the function in the order that they are given. We can then use the passed values in the function:

```js
// if we call add(1, 2) then inside the function
// a = 1 and b = 2 as the values are passed in order
letadd=function(a,b){
returna+b;
};
```
Most the time functions will return a value:

```js
let onePlusTwo = add( 1 , 2 );// 3
let threePlusFive = add(onePlusTwo, 5 );// 8
```
A function can contain as much code as you like, although well-written functions should only try to do one thing.

A function that doesn’t explicitly return anything returns undefined:

```js
letoops=text=>{
text+"!";
};

let value = oops("Hello");
console.log(value);// undefined
```

If undefined sneaks into your calculations you’re likely to start getting strange results.

**Arguments & Parameters**

The values that we pass to the function when we call it are the arguments. When we
accept those values in the function declaration they are called parameters.

```js
// a and b are the function parameters
// the variable names we use inside the function body
letadd=function(a,b){
returna+b;
};


// 1 and 2 are the arguments
// the values we call the function with
add( 1 , 2 );
```

This is a fairly technical distinction that you can easily get by without knowing. A lot of programmers will use the term “arguments” in both cases.


#### 2.1.2 Fat Arrow.

In modern browsers we can use fat arrow (=>) to neaten up our function declarations:
```js
let add = (a, b)=>a + b;

// works exactly as before
let onePlusTwo = add( 1 , 2 );// 3
let threePlusFive = add(onePlusTwo, 5 );// 8
```
If the function does something simple then this can save quite a lot of boilerplate: you no longer need to write out function and as long as the function fits on one line you also don’t need curly braces or are turn- it automatically returns what-
ever the right-hand side evaluates to.

If the function only takes one argument, you can even skip the brackets:
```js
let square = n => n * n;

// call add with an argument
let twoSquared = square( 2 );// 4
let fiveSquared = square( 5 );// 25
```

You can still use => for multi-line functions:
```js
let sum41 = (a, b) => {
let total = a + b;
return total ;
};
```
We need to use curly braces in this instance - which also means we need to manually return a value.

It’s worth noting that fat arrow syntax is not identical to a traditional function declaration: it inherits its parent’s **context**. However, this is a technicality and is unlikely to cause you any issues.

Unless you have a good reason not to, you should use fat arrow syntax.


#### 2.1.3 Examples

A function to greet someone:
```js
// greet takes one argument
// multi-line, so we need curly-brackets
let greet = name => {
// get the current hour of the day
  let hour = newDate().getHours();

  if (hour< 12 ){
  return "Good morning " + name;
} else if (hour< 18 ){
return"Good afternoon "+name;
}

// when a function returns a value it stops running
// so this will only ever run if the two return statements
// above don't run
return"Good evening "+name;
};

let greeting = greet("Mark");
console.log(greeting);
```
A function to multiply three numbers:

```js
// product takes three arguments
let product3=(a,b,c)=>a*b*c;

// call product, separating arguments with commas
let result=product3( 2 , 3 , 4 );// 24
```

#### 2.1.4 Writing Functions

Here’s the process to go through when you’re writing a function:

* 1.Think of a sensible name for the function: a short way of describing its purpose

* 2.Think about how many arguments the function needs to accept: this will
depend on what you’re trying to do

* 3.Think about what type of thing the function should return

* 4.Write out the boilerplate

* 5.The thinky bit: Work about how to turn the arguments into the return value

* 6.Test it with a few values you know the answer to

For example, a function to convert Fahrenheit to Celsius:

* 1.Let’s call it celsius

* 2.It should take a single argument: a number (the temperature in Fahrenheit), let’s call the parameterfahrenheit

* 3. It should return a number

* 4.First put in the boilerplate:

```js
let celsius = fahrenheit => {
// needs to return a number: fahrenheit in celsius
};
```
* 5.To convert Fahrenheit into Celsius you need to take away 32 and divide by 1.8 (seeGoogle)

```js
let celsius = fahrenheit => {
return (fahrenheit - 32 ) / 1.8;
};
```
* 6.Check it with a few values:

```js
celsius( 45 );// 7.222222
celsius( 32 );// 0
```

**Function Reuse**

If you write a function that works, then don’t be tempted to add additional functionality

later. Instead, write a new function that calls the one you’ve already written.

For example, say you had a function that works out if a number is divisible by 3. You then need to write a function that works out if a number is divisible by 3 _and_ a square number. Rather than edittng your existing divisibleBy3function, create a new function that calls the divisibleBy3 function.
```js
// does number divide by 3 with no remainder
let divisibleBy3 = n => n % 3 === 0 ;

// is square root of number an integer
let isSquare =  n => Math.sqrt(n) % 1 === 0 ;

// combine the two bits of functionality in one new function
let divisibleBy3Square = n =>divisibleBy3(n) && isSquare(n);
```
If you get used to writng short functons that do one thing well, you’ll find it much easier to perfect the art of **function composition** , arguably one of the most important skills in writing complex programs.


### 2.2 Scope.

The **scope** of a variable is the parts of code that you can use the variable name in.

letandconstare **block scoped**. This means that the variable’s value is only accessible from within the block in which it is declared (including any blocks within that block).

Variables created without declaring them will go into **global** scope.
```js
let  x= 10 ;

if (x === 10 ) {// new block
  let x = 20 ;
  y = 50 ;// goes into global scope, no variable declaration
console.log(x);// 20 - different x
}

console.log(x);// 10 - the x inside the if statement is scoped to that block of code
```
Function parameters are always scoped to the function they belong to. Variables

created withvarare also scoped to the containing function, _not_ block scoped like let and const.
```js
var x = 1 ;// in the global scope

var fn = y => {// y is only available inside the function
// z is only available inside the function
var z = 2 ;


if ( z < 3 ){
var z = 4 ; // this overwrites the z above - var isn't block scoped
}
// we can reference x, because it was declared outside of the function
returnz+x+y;
};

// we can only access x, result, and fn here
varresult=fn( 12 );
```

This is probably the most common form of scoping in programming languages


### 2.3 Recursive Functions

A function can call itself. This can be surprisingly powerful:
```js
// works out the factorial of n
let factorial = n =>{
// this condition stops the function calling itself forever
if (n <= 1 ){
return 1 ;
}

// to find the factorial of n
// times n by the factorial of n - 1
// e.g. 5! = 5 * 4! = 5 * 4 * 3! etc.
return n * factorial (n - 1 );
};
```
Or if that’s too long:
```js
let factorial = n => (n <= 1 )? 1 : n * factorial (n - 1 );
```
Effectively a recursive function creates a loop.

Anything we can do with recursion can also be done using traditional loops, but it’s often much less elegant.

As with other types of loop, we need to be careful not to create an infinite loop. If we didn’t have then <= 1check in thefactorialfunction, it would keep going forever.


### 2.4 Additional Resources.

- Functions
    **-** Eloquent JavaScript: Functions
    **-** MDN: Functions
- Scope
    **-** Scope in JavaScript
- Recursion
    **-** Recursion in Functional JavaScript
    **-** Wikipedia: Recursion
    **-** Algorithms: Recursion: _deep_ dive into recursion
- Advanced
    **-** A Gentle Introduction to Functional JavaScript
    **-** What the heck is the event loop anyway?