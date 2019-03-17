# Fundamentals of programming

## Contents

- 1 Fundamentals of Programming
   - 1.1 Basic Types
      - 1.1.1 Numbers
      - 1.1.2 Strings.
   - 1.2 Variables.
      - 1.2.1 Naming Variables.
      - 1.2.2 Template Strings
   - 1.3 Basic Logic
      - 1.3.1 Booleans
      - 1.3.2 Equality.
      - 1.3.3 Logic Rules.
   - 1.4 Conditionals
      - 1.4.1 if statements
      - 1.4.2 Ternary Operator.
      - 1.4.3 switchStatements
   - 1.5 Loops.
      - 1.5.1 forLoops.
      - 1.5.2 whileLoops
      - 1.5.3 Infinite Loops
   - 1.6 FizzBuzz.
   - 1.7 Additional Resources.

## Chapter 1

# Fundamentals of Programming

There are four fundamental concepts underpinning _all_ programming languages:

- **Types** : sorts of things
- **Variables** : remembering things
- **Boolean Logic & Conditionals** : deciding things
- **Loops** : repeating things

We’re going to be learning these concepts using JavaScript, but once you under-

stand them you should be able to pick up new programming languages easily.


### 1.1 Basic Types

Types are the different sorts of things that a programming language can recognise and work with. Almost all languages have basic types representing numbers,

strings (sequences of characters), and booleans (true and false). Most languages also have types representing more complex “data structures” such as arrays and objects.

#### 1.1.1 Numbers

In JavaScript there is a single “Number” type. All of the following are valid number values:

* 10 // an integer
* -10 // a negative number
* 1.2345 // a number with a decimal point
* 1.5e3 // scientific notation for 1500
* 0 // zero
* -0 // negative zero!
* Infinity // the concept of Infinity

**Numerical Limitations**

Many languages have separate types for integers and decimal point numbers (often
referred to as “Yoats”), but JavaScript isn’t fussy.

This is a mixed blessing: you don’t have to worry about convertng between different
types of number, but you also get some fairly weird results at times:

##### 0.1+0.2// 0.

We get this weird result because JavaScript stores numbers in a binary system that’s not optimised for precision (the IEEE 754 format). It’s like how we can express one third as a
fracton exactly (^13 ) but we can’t represent it exactly in the decimal system ( 0 : 3333333)

The intricacies of how numbers are stored in JavaScript and why you get these weird results are all covered inan excellent talk by Bartek Szopka.

Basic types normally have a number of associated “operators”. Numbers have the following:

##### Operator Name Description
```
+ addition adds two numbers together
- subtraction subtracts the second number from the first number
* multiplication multiplies two numbers
/ division divides the first number by the second
% modulus remainder after dividing the first number by the second
```
You’re probably familiar with these concepts, except for **modulus** - but don’t forget

that one: it comes in handy in all sorts of places.

**Arity**

These are all binary operators , meaning that they require two values (have an arity of 2), one on each side: 40 + 2. You also get unary and ternary operators.


```
##### 10 + 10 // 20

##### 10 - 20 // -

##### 50 / 3 // 16.

##### 10 / 5 // 2

##### 100 * 2 // 200

##### 11 % 3 // 2
``````


#### 1.1.2 Strings.

Strings represent a sequence of characters. It’s probably easiest to think of them as storing words, but that’s not quite right as they can store parts of a word, whole sentences, entire books, or just a single emoji.

In order to get JavaScript to recognise a string we surround it with quotes:

```
"cow"
'a string'
"an even longer string"
```

You can use double or single quote marks around strings, but try and stick to one or the other.

There is a special string known as the **empty string** , which is simply two sets of quote marks with nothing in between (not even a space):"". You’ll probably use this a lot.

Strings only have a single operator,+, known as the **concatenation** operator. It joins two strings together:

```
"hello"+" " +"world"// "hello world"
"fish"+"sticks" // "fishsticks"
```

The above examples are a little contrived as you should write them both as a single string:

```
"hello world" // "hello world"
"fishsticks" // "fishsticks"
```
However, until we learn about variables there’s no other way to demonstrate concatenation.

* It’s also worth noting that “word” has atechnical meaning in computing
* This is not true in all programming languages: some only allow double quotes and some (e.g. PHP) treat single and double quotes slightly differently


**Strings & Numbers**

You need to be careful when using numbers and strings together: they won’t always do what you want.

The+operator has two meanings (it is **overloaded** ): additton _and_ concatenation. So JavaScript has some rules to work out what it should be:

```
12 + 12 // 24 - a number
"12"+ 12 // "1212" - a string
120 +"1" // "1201" - a string
5 + 6 +"1" // "111" - a string
```

Basically, if it comes across a string everything from that point on will be treated as a string too.

You can guard against this by puttng an addittonal+symbol before a value that might not be a number. This **casts** the string value into a number value:

```
##### +"12"+ 12 // 24
```
Again, this is a somewhat contrived example, as in the case above you could simply not write the quote marks (12 + 12), but once we start storing values in variables it will make more sense.

It is often necessary to cast a string to a number when gettng values from the browser (e.g. an input’s value will come back as a string).


### 1.2 Variables.

Variables are a way of storing a value using a name so that we can refer to it later.

This serves two purposes:

* 1.We can store the results of complex calculations so that we only have to calculate them once

* 2.If we’re sensible about what we call our variables it makes our code much easier to follow

Before we use a variable we must **declare** it using the **let** keyword:

```js
let email;
let age;
```

Declaring a variable lets JavaScript know that from that point on, if we use that series of characters in our code, it represents a value.

Once we’ve declared the variable, we can **assign** it a value:

```js
email="orb@is.horse";
age= 32 ;
```
We only need to declare a variable once. From that point on we can reassign the value if we want to:

```js
// elsewhere
email="farm@wisdom.com";

// elsewhere
email="shrimp.heaven@now.plumbing";
```

Once we’ve stored a value in a variable we can use it to represent that value elsewhere in our code:

```js
letpointless;
pointless=email+age;// "shrimp.heaven@now.plumbing32"
```

Generally we declare and assign variables at the same time :

```js
letname="Archie";
```
// can also declare multiple variables in one go

```js
letage= 4 ,
houseNumber= 21 ;

// using variables
letnotUseful=age+houseNumber;// 25
```

**Aside: Variable Types**

JavaScript actually supports three ways of declaring variables.

```js
let
//The most commonly used in modern JS. Use this unless you can think of a good reason not to.

let value= 10 ;

const
//Useful if you want to make sure a value can’t be changed, for example if you had a variable that stored some configuration.

const maxVolume= 10 ;
maxVolume= 11 ;// Error - you can't assign a new value to maxVolume

var
//Very common in older JS. Works almost idenঞcally toletexcept when it comes to
scoping. Stick to let unless you’re dealing with legacy code.

var meh= 10 ;
```

If you see old JavaScript code that usesvar, you will often find all the variables declared at the top of the file and values assigned to them later. This is because of something called “hoisting”. Luckily it’s not necessary if you uselet.


#### 1.2.1 Naming Variables.

We can call a variable pretty much anything we want, but it’s best to pick something that represents its purpose.

```js
letname="Ben";// good
leta= 394 ;// possibly ok for short bits of code
letaRidiculouslyLongVariableName= 83 ;// maybe a bit long
letappleSauce= 394 ;// huh?
letname="Not Ben";// already used that...
```
A variable name can contain:

- alphanumeric characters
- underscores
- the dollar sign

It cannot:

- contain spaces
- contain hyphens
- start with a number
- be areserved word(e.g.class,let,var,function,if, and many more)

We tend to use camel-case (lowercase first letter, uppercase beginnings of words - (likeThis) - as opposed to snake-case (all lowercase, underscores between words (like_this). You don’t have to, but if you don’t your code will look weird to everyone else and your friendship group will slowly dwindle.

If we pick our variable names sensibly then it’s easy to see what our code does:

```js
let username="potus";
let password="00000000";

armNuclearWeapons(username,password);
```

If we pick our variables names poorly it can be impossible to work out what’s goingon:

```js
leta="potus";
letb="00000000";

doWhatevs(a,b);// we just started a thermonuclear war - oops!
```

**Comments**

It’s a good idea to explain unusual parts of your code. You can do this with comments.

If you put//on a line in JavaScript then everything after that will be ignored when your code runs:

```js
// The number of milliseconds in a year: 1000 * 60 * 60 * 24 * 365.
letmillisecondsPerYear= 31556952000 ;
letanother= 12345 ;// you can put comments at the end of a line too
```

``` 
You can also do multi-line comments using/*and*/. Everything between the
opening/*and the closing*/will be ignored.
```
This can be useful if you need to temporarily disable a bit of code. But make sure you don’t leave unused code lying around once everything is working.

```js
* The number of milliseconds in a year
* Calculated using: 1000 * 60 * 60 24 * 365.
* Required for date calculations
*/
letmillisecondsPerYear= 31556952000 ;
```
If you change a bit of code, make sure you update the corresponding comments : old/incorrect comments are worse than no comments at all.


#### 1.2.2 Template Strings

We often want to include something stored in a variable as part of a string.

One option would be to concatenate the variables:

```js
let name="Chetna";
let greeting="Hello "+name+", how are you?";
```

However, rather than using quotation marks, we can put backticks ` around our strings. This allows us to **interpolate** values:

```js
let name = "Chetna";
let greeting= `Hello${name}, how are you?`;
```

As you can see, we use **${variable}** inside the backticks to insert the value contained in a variable.


### 1.3 Basic Logic

#### 1.3.1 Booleans

Modern digital computers^4 use **boolean** logic: true and false. Because these are

such fundamental ideas in computing, JavaScript has the special true and false values (lowercase, no quotation marks).

```js
// setting variables to boolean values
let news = true;
let lies =  false;

// don't use strings!
letfakeNews="false";// as far as JS is concerned, this is true
```

#### 1.3.2 Equality.

The ideas oftrueandfalseare most useful when it comes to comparing things.

We can compare things with various operators:

##### Operator Name Description
```
=== strict equality trueif the values are the same
!== non-equality falseif the values are the same
< less than trueif the first value is less than the second value
> greater than trueif the first value is greater than the second
value
<= less than or equal to trueif the first value is less than or equal to the second value
>= greater than or equal to trueif the first value is greater than or equal to the second value
```
Analogue computers are another matter

For example:
```
10 === 10 ; // true
10 === 12 ; // false
"12"=== 12 ;// false - a string is not a number
10 <= 12 ; // true
10 < 10 ; // false
10 >= 12 ; // false
10 > 9 ; // true
10 !== 14 ; // true

**Sort of Equal**

```
In many languages if you tried to compare a string and a number they’d think you were mad. But JavaScript isn’t fussy about what types of things your variables store. That
means you can compare different sorts of things and JavaScript will give it a go.

Because of this JavaScript also has the == and != operators. 

These type cast : they convert one or the other side of the operator to be the same sort of thing as the other
side before checking if the values are the same.

This lets you do things like 12 == "12" and get true back.

This might seem really useful, but using it suggests you don’t know what types of values you’re dealing with, which means you don’t really understand what your code is doing.

So you should stick to ===, which Cast checks if both values are the same type and immediately returns false if they aren’t.


#### 1.3.3 Logic Rules.

There are a number of operators that we can use when working with boolean val-

ues, these represent the key rules of boolean logic: **and** , **or** , and **not**.

**and (** && **)**

If either value is false, the result is false:
```js
( 10 > 12 )&&( 1 < 2 );// false
( 10 < 12 )&&( 1 < 2 );// true
( 10 > 12 )&&( 1 > 2 );// false
```
If you think about the phrase “My name is Mark and I live in Bristol”, we’d say that the whole phrase is false if either (or both) of the sides are false: “My name is Brian and I live in Bristol” is false, even though the right side is true. The phrase
as a whole can only be true if both sides are true.

**or (** || **)**

If either value is true, the result istrue:

```js
( 10 === 10 )||( 2 !== 1 );// true
( 10 === 12 )||( 1 !== 2 );// true
( 10 >= 12 )||( 2 <= 1 ); // false
```
This one doesn’t work quite so well with the common sense notion of “or”. If you think about the phrase “My name is Mark or I live in Bristol”, some people might be inclined to think that it’s true when exactly one side is true. However, the
standard interpretation in boolean logic is that as long as at least one side of the phrase is true, then the whole phrase is true. This is a useful concept and is known as **exclusive or** or XOR


**not (**! **)**

Reverses the truth value. Turns true to false and false to true:
```js
!true;// false
!!true;// true
!( 10 > 12 );// true
!!( 10 > 12 );// false
```
Notice that not is a **unary** operator: it only takes a single value.

**Casting to Boolean**

When we use ! twice, it Crst Yips the boolean value (either from true to false or vice versa) and then Yips it again, so you end up with the original boolean value.

This is completely pointless if the values are already boolean, but it can be useful for casting a non-boolean value to a boolean:

```js
!! 0 ; // false
!! 10 ; // true
!!""; // false
!!"false";// true
```

### 1.4 Conditionals

#### 1.4.1 if statements

Computers need to be able to make decisions: if such-and-such is the case then do something. Without this ability we couldn’t write programs that do anything other than basic calculations.

We can use our logic rules in combination withifstatements to decide what our program will do:
```js
let value= 8 ;
let max= 10 ;

if(value<=max){
console.log("Valid");// this will run
}
```
The part inside the if brackets is the **truth condition**^6 - this will always be evaluated as either true or false. If it evaluates to true, then the block of code will execute, if it evaluates to false then it won’t.

#### else

You can also add an else block. In this case either the top or the bottom block of code will run (always one, never both). If the conditional is true then the first block of code runs, otherwise the second block of code will run.


```js
letusername="mark";

// the truth condition
if(username==="admin"){
// this runs if it's true
console.log("Hello Admin");// won't run
}else{
// this runs if it's false
console.log("Unauthorized!");// will run
}
```
Hence “conditional”


#### else if

You can also use else if blocks. These let you check multiple conditions. You can have as many of these as you like.

As in the previous case, one and only one of these blocks of code will run. If the first condition is false then the first else if condition is checked; if that is also false then it will move onto the next; and so on until it reaches the final else block, which will only run if _all_ of the previous conditions have returned false.

```js
let average = ( 10 + 13 + 15 ) / 3 ;

if average <= 10 ){
console.log("Less than 10");// won't run

} else if (average< 20 ){
console.log("Less than 20");// will run

}else{
console.log("20 or more"); // won't run
}
```
If we hadn’t included the final else block, then it’s possible that none of the code blocks would run:
```js
let average = ( 30 + 50 + 100 ) / 3 ;

if (average <= 10 ) {
console.log("Less than 10");// won't run

}else if (average< 20 ){
console.log("Less than 20");// won't run
}
```

**Truthy & Falsey Values**

Because JavaScript isn’t that fussy about types, if you try and use a non-boolean value as a condition it will do its best to make things work:
```js
let value = "Hello";

if (value){
// even though the condition isn't a boolean value
// this will run as a non-empty string is "truthy"
}
```

Falsey values (ones that type cast to false) in JavaScript are:

- false
- 0
- ""(the empty string)
- null
- undefined
- NaN

Everything else is truthy (i.e. it type casts to true).


#### 1.4.2 Ternary Operator.

If the blocks of your conditional are both short, it can sometimes save space to use

the **ternary operator**.

Unlike an if **statement** the ternary operator is an **expression** , meaning that it equates to a value.
```js
let current = 3 ;

// set the value of next, dependent on the value of current
let next = current > 5? 0 : current + 1 ;// next is set to 4
```
Does the same as:
```js
let current = 3 ;
let next;

if (current> 5 ){
next = 0 ;
} else {
next = current + 1 ;
}
```

The ternary operator consists of three parts:

* 1.The condition (before the?)

* 2.The _if true_ result (before the:)

* 3.The _if false_ result (after the:)

In other words, if the bit before the ? is true, then evaluate to the bit before the : , otherwise evaluate to the bit after the:.


**Statements & Expressions**

An **expression** is any bit of code that equates to some value. If you could assign the whole bit of code to a variable, then it’s an expression. An expression can be made up of sub-expressions.

For example, all of the following equate to a value, so they are expressions:

```js
12 + 34 ;// equates to 46
((true&&false)||false)===false;// equates to true
(celsius* 9 / 5 )+ 32 ;// equates to some number, assuming celsius is a number
```
A **statement** is just an instruction. Things like if statements or variable assignments: they do something, but aren’t equal to a value. Statements can be made up of other statements and expressions. All expressions are also statements.


#### 1.4.3 switch Statements

If your if statement is just a series of checks against the same value, then a switch statement can sometimes save space:
```js
let user name ="admin";

switch (username) {
case "admin": console.log("Authorized");break;
case "Admin": console.log("Authorized");break;
case "root": console.log("Authorized");break;
default: console.log("Unauthorized");
}
```
We use the switch keyword and then in brackets we put the value we want to check against. Inside the block, we list a series ofcasestatements: if the value in the switch matches a specific case then that case statement will run. It will only run
the first matching case. We can also have adefaultcase which works much like an else block: it will run if none of the case statements are true.

Switch statements are neater than multiple else if statements, but make sure you remember to use break at the end of each case, otherwise you’ll get unexpected behaviour.

If you don’t use break then every case statement below the one that was true will also run. This is called **fall-through** and is occasionally useful, but if you see it in code it’s hard to know whether it’s deliberate or not, so it’s best not to use it


**Indenting**

You’ll notice that all of the code inside theifblocks is indented:

```js
// anything between the opening and closing curly braces should be indented
if(x=== 10 ){
console.log("x is 10");// indented
}// <-- first block block stops here, so don't indent anymore

// new block, so indent everything inside the braces
if(x< 20 ){
console.log("Less than 20");// indented

// a new block, so indent another level
if(average< 20 ){
console.log("Less than 20");// indented two times
}// <-- end of a block, indent one less
}// <-- end of outermost block, so stop indenting

console.log("Less than 20");// <-- outside of a block, so not indented
```
This makes it clear which bits of the code are part of the if blocks and which bits are not.

Basically, when you get to a { you should indent another level and when you get to a } you should de-indent. Your text editor will probably do this for you and, at this
stage, it probably knows best.

_Fix indenting problems as soon as you spot them_ - it will save you some later!


### 1.5 Loops.

We use a loop when we want to do something similar more than once.

#### 1.5.1 forLoops.

forloops are useful when you know how many times the loop should run.

They consist of three parts:

* 1.let i = 0: setup a variable that we use as a counter

* 2.i < 10: keep running the loop as long as this is true

* 3.i += 1: incrementiby 1 every time the loop runs
```js
// will keep running until i is 9
for (let i= 0 ; i < 10 ; i += 1 ){
console.log(i);
}

// 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
```
It is traditional to use **i** as the counter variable - one of the few places it’s good practice to use a single letter variable name. If you need a loop inside a loop then just keep going down the alphabet (j,k, ...).

#### 1.5.2 While Loops

We use a while loop if we aren’t sure how many times the loop needs to run.

For example, say we wanted to add 1 to 2 to 3 to 4 and so on until we get to a number bigger than 100. We know when we want it to stop (when the total is bigger than 100), but we don’t know how many times it needs to run.

```js
leti= 0 ; // keeps track of which number we're adding
lettotal= 0 ;// keeps track of the total so far

// will keep running until total is more than 100
while(total<= 100 ){
total+=i;
i+= 1 ;
}

console.log(total);// 105
console.log(i);// 15 - so the loop ran 15 times
```

#### 1.5.3 Infinite Loops

We need to be careful to avoid infinite loops: loops that never stop running. These sometimes occur because of typos, but more often because you use a variable that isn’t equal to what you’re expecting.
```js
for (let i= 0 ; i< 10; i -= 1 ){
// will never stop
// why not?
}
```
An infinite loop will keep running until you kill the process that’s running it. If you’re running code innodeand you think you’ve got an infinite loop then press Ctrl+c, which will kill the node process.


### 1.6 FizzBuzz.

_a.k.a. Everyone’s Favourite Job Interview Question_

The FizzBuzz challenge is as follows:

- write some code that will output the numbers 1 to 100 in the console
- _unless_ the number is divisible by 3, in which case output “Fizz”
- _or_ the number is divisible by 5, in which case output “Buzz”
- _if_ the number is divisible by 3 _and_ 5, output “FizzBuzz”

The first lines of output should look like this:
```js
1 
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
16
```
If you can solve FizzBuzz, then you understand the basic concepts of programming:

* 1.Types: you have to work with numbers and strings

* 2.Variables: more elegant solutions require variables

* 3.Conditionals: you have to make decisions

* 4.Loops: you’ll need to use a loop


**Elegance & Changeability**

You should try and write the most elegant code that you can. But how do you know if your code is elegant?

Many people associate elegance with brevity: if you have two pieces of code that do the same thing, generally the shorter of the two does it more elegantly.

But this shouldn’t be our key metric, as it can encourage people to write code that’s so short as to be impossible to follow.

A better metric of elegance is “changeability”: if we need to change the functionality of our code, how many lines of code would we need to update?

For example, if we wanted to update FizzBuzz so it outputs “Spoon” for lines divisible by 4 (so, for example, we’d get “Spoon” on line 4, “FizzSpoon” on line 12, and “SpoonBuzz”
on line 20) we should only need to add an extra line or two to the code. If we need to add lots of additional code or make lots of changes to the existing code then the
solution we’ve come across might not be the most elegant way to do it.

Design is more the art of preserving changeability than it is the act of achieving perfection


### 1.7 Additional Resources.

- Types & Variables
    **-** Eloquent JavaScript: Values, Types, and Operators
    **-** JavaScript for Impatient Programmers: Variables & Values
    **-** Template Strings
    **-** The Why Behind the Wat: An Explanation of JavaScript’s Weird Type
       System
- Conditionals & Loops
    **-** MDN: Conditionals
    **-** MDN: Loops
    **-** Eloquent JavaScript: Program Structure
    **-** JavaScript for Impatient Programmers: Control Flow
- FizzBuzz
    **-** FizzBuzz in Almost Every Language
    **-** FizzBuzz: One Simple Interview Question
- Computer Science
    **-** Code: The Hidden Language of Computer Hardware and Software
    **-** Turing Completeness
