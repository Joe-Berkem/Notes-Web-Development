# Data Structures: Arrays

## Contents

- 3 Data Structures: Arrays
   - 3.1 Arrays
      - 3.1.1 Adding Values.
      - 3.1.2 Reading Values
      - 3.1.3 Length.
      - 3.1.4 Iterating.
      - 3.1.5 All For One and One For All
      - 3.1.6 Useful Operations
      - 3.1.7 The Spread Operator.
   - 3.2 Array Iterator Methods.
      - 3.2.1 forEach.
      - 3.2.2 find
      - 3.2.3 filter
      - 3.2.4 map.
      - 3.2.5 reduce
      - 3.2.6 Which Iterator Method?.
      - 3.2.7 Functional Programming.
   - 3.3 Additional Resources.
   
### 3.1 Arrays

Arrays are ordered collections of values. It’s probably easiest to think of them as being a list of values.

We can create an array using square brackets and put in values separated by commas:
```js
let values = [];// an empty array

let numbers = [ 1 , 2 , 3 , 4 , 5 , 6 , 7 ];// an array of numbers

let animals = [
"cow",
"chicken",
"fish",
"wombat"
];// an array of strings
```

Arrays can contain any of the value types: numbers, strings, booleans, functions, objects (which we’ll look at later), and, of course, other arrays.

It’s worth noting that in some programming languages there are different types of list, that have dif-
ferent performance characteristics

JavaScript isn’t fussy about types, so a single array can contain different types of values:

```js
// this is totally fine in JavaScript
let nope = [ 1 ,"fish", n => n * n, [ 1 , 2 , 3 ], true];
```
However, just because you _can_ , doesn’t mean you _should_. When we’re working with arrays we almost always want to go over every value in the array and run the same bit of code for each one. If you start having different types of values in your array you’re going to end up with a lot of conditionals. So, _an array should use the same__type for all its values_.

**Multi-Dimensional Arrays**

An array containing other arrays is often called a multi-dimensional array as it can
represent multi-dimensional values. For example, an array of arrays can represent a table:
```js
let table=[
[ 1 , 2 , 3 ],// first row
[ 4 , 5 , 6 ],// second row
[ 7 , 8 , 9 ],// third row
];
```

An array of arrays of arrays can represent three-dimensional structure; four levels deep can represent a four-dimensional structure (e.g. an animated 3D object); and so on.


#### 3.1.1 Adding Values.

We can add items to the end of the array:
```js
values.push ("a");// ["a"]
numbers.push ( 8 );// [1, 2, 3, 4, 5, 6, 7, 8]
animals.push ("kangaroo");// ["cow", "chicken", "fish", "wombat", "kangaroo"]
```
And to the beginning:
```js
values.unshift ("g");// ["g", "a"]
numbers.unshift ( 0 );// [0, 1, 2, 3, 4, 5, 6, 7, 8]
```
It’s important to note that these change the original array.

#### 3.1.2 Reading Values

You can reading values from an array using square brackets and passing in the

**index** of the item you want:
```js
let animals=["cow","chicken","fish","wombat"];
animals[ 0 ];// "cow" - arrays are "zero-indexed"
animals[ 2 ];// "fish"
```
Reading values this way does _not_ change the array.

Arrays are **zero-indexed** , which means the first item has index 0.

Getting values out of the array, changing the array:
```js
let animals = ["cow","chicken","fish","wombat"];
let last = animals.pop();// "wombat" - removed from end of array
let first = animals.shift();// "cow" - removed from beginning of array

console.log(animals);// ["chicken", "fish"]
```

#### 3.1.3 Length.

We can use the.lengthproperty to find out how many items there are in an array.
```js
let animals = ["cow","chicken","fish","wombat"];
console.log(animals.length);// 4

let values = [ 17 , 12 ];
console.log(values.length);// 2
``````
Note that.lengthis a **property** , not a function, so it doesn’t require brackets to get the value. We’ll learn more about properties tomorrow.

#### 3.1.4 Iterating.

So, how could we do something with every item in an array?

* We know how long an array is using.length
 We know we can read individual items usingarr[0],arr[1],arr[2], etc

We can use a forloop to do something with every item in an array. This is called **iterating** over an array.

If an array has a .length of 5 , then we know that the indexes will go from 0 to 4.

And we know we can access a specific index using the values[0](where 0 is the index) notation. So, we just need to loop from 0 to 4 and get back that index:
```js
let animals = ["cow","chicken","fish","wombat","kangaroo"];

// start at 0, because arrays are zero-indexed
// finish one less than the length of array
// so, this will loop i from 0 to 4
for (let i = 0 ; i < animals.length; i+= 1 ){
console.log(animals[i]);
}

// "cow", "chicken", "fish", "wombat", "kangaroo"
```

We could, for example, use this to add up all the values in an array:
```js
let values=[ 1 , 2 , 3 , 4 , 5 , 6 ];

// keep track of the cumulative total
let total = 0 ;

// iterate over each item in the array
// adding it to total
for (let i = 0 ; i < values.length; i += 1 ){
let current = values [i];
total += current;// the value of total will go up each iteration
}

console.log(total);// 21
```
Or we could use it to create a new array without odd numbers:
```js
let values = [ 1 , 2 , 3 , 4 , 5 , 6 ];

// an array to put the even numbers into
let even = [];

// iterate over each item in the array
for (let i = 0 ;i < values.length; i += 1 ){
let current = values [i];

// if the value is even add it to the even array
if ( current % 2 === 0 ){
even.push (current);
}
}

console.log(even);// [2, 4, 6]
```

#### 3.1.5 All For One and One For All

Although an array _contains_ multiple values, we treat it like a single value:
```js
// we store it in a single variable
let x =[ 1 , 2 , 3 , 4 , 5 , 6 ];
```
A function being passed arrays is being passed however many _arrays_ it is called with, not the number of items in the array:
```js
// when we pass it to a function it is a single value
let total = (arr) => {
let sum = 0 ;

for (let i= 0 ; i < arr.length; i += 1 ) {
let current = arr [i];
sum += current;
}
return sum;
}

// even though this array contains 6 values
// it gets passed to the function as a single value
// it's the number of arrays passed in that matters
total ([ 1 , 2 , 3 , 4 , 5 , 6 ]);
```
This is very useful as it lets us create functions that can deal with as many values as we like: we can pass in an array with one value, a hundred values, two values, or even no values and the function should work.


#### 3.1.6 Useful Operations

**Sorting**

We can sort an array alphabetically:
```js
let values = ["b","c","a","d"];
values.sort ();

console.log(values);// ["a", "b", "c", "d"]
```
However, this won’t be much use if you want to sort numbers:
```js
let values = [ 9 , 11 , 40 , 112 , 89 , 380 ];
values.sort();

// sorts numbers alphabetically
console.log(values);// [11, 112, 380, 40, 89, 9]
```

**Merging Arrays**

We can merge two arrays:
```js
let v1 =[ 1 , 2 , 3 , 4 ];
let v2 =[ 3 , 4 , 5 , 6 ];
let merged = v1.concat(v2);

console.log(merged);// [1, 2, 3, 4, 3, 4, 5, 6]
```
**Turning Arrays into Strings**

It’s often useful to join an array of string into a single string:
```js
let letters = ["a","b","c","d"];
let alphabet = letters.join (" - ");

console.log(alphabet);// "a - b - c - d"
```
You could pass an empty string in to.join("")which would join the strings with nothing between.


**Finding a Specific Value**

Finding a value:
```js
let letters = ["a","b","c","d"];

console.log(letters.indexOf("b"));// 1
console.log(letters.indexOf("d"));// 3
console.log(letters.indexOf("e"));// -1
```
We get back the index of the first match. If not match is found you get back-1.

**Getting Part of an Array**

Getting part of an array:
```js
let numbers = [ 3 , 4 , 5 , 6 , 7 , 8 , 9 ];

// first argument is index to start on
// second argument is index to finish before
let middle = numbers.slice( 2 , 5 );// [5, 6, 7]
```
#### 3.1.7 The Spread Operator.

We can use the **spread operator** (...) to copy an array:
```js
let numbers = [ 3 , 4 , 5 , 6 , 7 , 8 , 9 ];

// ...numbers represents all the values in the array
// but as separate values
let copied = [...numbers];// [3, 4, 5, 6, 7, 8, 9]

// without the spread operator we'd get an array inside an array

let oops = [numbers];// [[3, 4, 5, 6, 7, 8, 9]]
```
It doesn’t returnfalsebecause it’s a good idea for functions to always return the same type of value

We can also use it to merge two arrays into a new array:
```js
let odd = [ 3 , 5 , 7 , 9 ];
let even = [ 4 , 6 , 8 ];

let mergedOddEven=[...odd,...even];// [3, 5, 7, 9, 4, 6, 8]
let mergedEvenOdd=[...even,...odd];// [4, 6, 8, 3, 5, 7, 9]
```
This is useful because a lot of operations on arrays (like pop and push) alter the original array, which can lead to confusing results:
```js
// a badly written function to get the last item in an array
let last = arr => arr.pop();

let values=[ 1 , 2 , 3 ]
last (values);// 3 - but values is now [1, 2]

If we make a copy first, we don’t need to worry about this:

let last=arr=>[...arr].pop();

let values=[ 1 , 2 , 3 ]
last (values);// 3 - values still [1, 2, 3]
```

### 3.2 Array Iterator Methods.

Because we almost always want to loop over an array, JS has some built in func-

tions for looping over arrays in commonly used ways. This saves us from writing

the boilerplate for aforloop every time.

We’re going to look at:

- forEach
- find
- **filter**
- some
- every
- **map**
- **reduce**

These can (and _should_ ) be used in place of a forloop.

**Performance vs Elegance**

There are some posts on the internet that will tell you to always use aforloop as it is much more performant than using the iterator methods. While it is true that the iterator methods are not quite as quick as using aforloop, that’s not reason not to use them.

Firstly, this might not always be the case: how di@erent bits of code perform is always being worked on by the people working on the JavaScript engines in browsers. Sec-
ondly, they’re both incredibly quick: if you’re app is having performance issues then there are probably much bigger issues to sort out than using the array iterator meth-
ods. 

And lastly, your main aim when writing code should be to make it maintainable: that means easy to follow and make changes to. The iterator methods are much better
than using aforloop.

Programmers waste enormous amounts of time thinking about, or worrying about, the speed of non-critical parts of their programs, and these attempts at efficiency actually have a strong negative impact when debugging and maintenance are considered. We should forget about small
effciencies: premature optimization is the root of all evil.



#### 3.2.1 forEach.

forEach goes over each item in the array. You can always use it instead of a forloop for iterating arrays.
```js
let numbers=[ 1 , 2 , 3 , 4 , 5 , 6 ];

numbers.forEach(val=>console.log(val));
numbers.forEach((val,index)=>console.log(index));
```
This is tidier than using aforloop and is the preferred method. Although, more often than not,filter,map, andreducecan be used to create more succinct code.

#### 3.2.2 find

find goes over every item in an array until it finds the first value that returns true when passed into the provided function, it then returns the value it found.
```js
let words=["fish","cow","monkey"];

// each item in the array is passed into the function
// returns the first value in the array for which
// the given function returns true
let result = words.find ( word => word.length === 3 ); // "cow"
```
#### 3.2.3 filter

filter can be used to remove items from an array:
```js
let numbers=[ 1 , 2 , 3 , 4 , 5 , 6 ];

// iterates over an array passing each value into the supplied function
// removes any items that the function returns false for
let evenNumbers = numbers.filter ( va l=> val % 2 === 0 );

console.log(evenNumbers);// [2, 4, 6]
```
Takes an array and returns an array containing the **same number or fewer** items.

If the given function takes two arguments the second one will be the current index.


**Some & Every**


There are also some and every methods which work like filter.some returns true if any of the test functions return true.every returns true if all of the test functions
return true.

#### 3.2.4 map.

map transforms each value in array to another value:
```js
let numbers=[ 1 , 2 , 3 , 4 , 5 , 6 ];

// iterates over an array passing each item into the supplied function
// transforms the value using the supplied function
let squares = numbers.map (val => val * val);

console.log(squares);// [1, 4, 9, 16, 25, 36]
```
Takes an array and returns an array containing the **same** number of items.

If the given function takes two arguments the second one will be the current index.

#### 3.2.5 reduce

map and filter always return an array. However, it’s often useful to turn an array into some other value type reduce turns an array into a single value:
```js
let numbers = [ 1 , 2 , 3 , 4 , 5 , 6 ];

// iterates over the array, passing in the previous return value and new value
// the final value is the return value from the final iteration
let sum = numbers.reduce ((total,val)=>total+val, 0 );

console.log(sum);// 21
```
Takes an array and returns a value (number, string, boolean, array, object, function, etc.)

If the given function takes _three_ arguments the _third_ one will be the current index.

**Note** : make sure you use _both_ arguments inside the function you pass to reduce, otherwise you don’t need a reduce.

#### 3.2.6 Which Iterator Method?.

Firstly, you can only use iterator methods on arrays, so if you’re not working with an array, you can’t use the iterator methods (although, if you’re sneaky, you might be able to turn the problem into one involving arrays).

- Do you need to filter out some values? Usefilter
- Do you need to transform each value? Usemap
- Do you need to turn the array into some other value? Usereduce
- Do you need to turn the array into another array, but which isn’t just filtered
    or mapped? Usereduce
- Do you just need to run some code, but you’re not interested in getting back
    a result? UseforEach

You shouldn’t ever need to use aforloop for working with arrays.

#### 3.2.7 Functional Programming.

The beauty of the iterator methods is that we can use functions that we’ve already

written:
```js
let numbers = [ 1 , 2 , 3 , 4 , 5 , 6 ];

let sum = numbers.reduce ((total,val) => total + val, 0 );
```
The function we’ve passed into sum is just a function that takes two arguments and adds them together - which is what add did:
```js
let numbers = [ 1 , 2 , 3 , 4 , 5 , 6 ];
let add = (a, b) => a + b;

let sum = numbers.reduce (add, 0 );
```

So rather than passing in anonymous functions, we can **reuse functions we’ve al-**

**ready written**. This is one of the key ideas behind **functional programming**.

**Range**

We can only use the iterator methods if we have an array to work with, which won’t always be the case. For example, say you just want to do something 100 times: un-
less you have an array with 100 things in lying around you’ll 
need to use a forloop.

For the forloop averse, there is a way to turn any looping problem into an array iterator method:

```js
let range = (start, end, increment)=> {
let arr=[];

// allows us to ignore the increment argument
increment=increment?increment: 1 ;

for (let i = start; i <= end; i += increment) {
arr.push (i);
}

return arr;
};
```
Now we can use the range() function to create an array of arbitrary length:

```js
// get all the numbers between 1 and 100 that are divisble by 5 or 9
let divisibleBy5Or9 = range( 1 , 100 ).filter ( i=>i % 5 === 0 || i % 9 === 0 );

// all the numbers between 3 and 100 that are divisble by 3
letdivisibleBy3=range( 3 , 100 , 3 );
```

A function like range is included in many popular JS libraries - so in the real world you wouldn’t need to write it yourself.


### 3.3 Additional Resources.

- Eloquent JavaScript: Objects and Arrays
- MDN: Arrays
- MDN: Filter
- MDN: Map
- MDN: Reduce
- JavaScript’s Map, Reduce, and Filter
- JavaScript Functional Programming: Map, Filter, and Reduce
- How to create range in JavaScript
