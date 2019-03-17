# Data Structures: Objects

## Contents

- 4 Data Structures: Objects
   - 4.1 Object Literals
      - 4.1.1 Reading Properties
      - 4.1.2 Writing Properties
      - 4.1.3 Methods.
      - 4.1.4 this
   - 4.2 Standard Library.
      - 4.2.1 Strings.
      - 4.2.2 Date
      - 4.2.3 Math
   - 4.3 Advanced Object Techniques
      - 4.3.1 Destructuring
      - 4.3.2 The Spread Operator.
      - 4.3.3 Keys and Values
   - 4.4 Classes.
      - 4.4.1 An Example
   - 4.5 Additional Resources.

### 4.1 Object Literals

Objects are _unordered_ collections of values. We use objects to collect together a set of related values. Objects have **keys** (names) and **properties** (values).

Properties can be any type of value (numbers, strings, booleans, functions, arrays, and other objects). We tend not to iterate over the items in an object^1 , so it’s fine for different properties to store different types of values.
```js
// an empty object
let empty = {};

// an object representing and address
let address = {
number: 54 ,// assign the value 54 to the property "number"
road:"Park Street",
postcode:"BS5 9LD",
};

// an object representing a person
let person = {
name:"Kofi",
address:address,// using the address object from above
favouriteColours:["purple","green"],
};
``````

#### 4.1.1 Reading Properties

We use **dot-notation** to read the values of properties:
```js
console.log(address.number);// 54
console.log(person.name);// "Kofi"

You can also use array-style notation (although dot-notation is preferred):

console.log(address["number"]);// 54 - using array style notation
``````
#### 4.1.2 Writing Properties

You can change the value of a property:
```js
address.number = 82 ;
address.road = "Bath Road";
```
You can also use square bracket notation. This can be useful if you have the property name stored in a variable:
```js
let property = "road";

// elsewhere
address [property] = "Bristol Road";
```
You can also add new properties to an object after it’s been created:
```js
// creates a new property, "country", and gives it "UK" as a value
address.country = "UK";
```

#### 4.1.3 Methods.

Objects can have functions as property values. We normally refer to these as **methods**.

We can write them with => if we want, but there is an object-specific way of writing functions:
```js
let basicMaths = {
pi:3.141592654,

// object-style method (function)
add (a, b){
return a + b;
},

// fat-arrow style method
minus:(a, b) => a - b
};

basicMaths.add( 1 , 2 );// 3
basicMaths.minus( 1 , 2 );// -1
basicMaths.pi;// 3.141592654
```
When you used arr.sort(),str.split(" "), etc. you were calling methods of strings and arrays.

_Methods are still properties_ , so you can’t have a method that has the same name as another property (e.g. you can’t have a.pi()method and a.pi property)


#### 4.1.4 this

Objects can refer to themselves using thethiskeyword:

##### // 1000 * 60 * 60 * 24 * 365.2425

```js
let millisecondsPerYear = 31556952000 ;

let mark = {
name: "Mark",
birthdate: newDate("1984-04-16"),

getAge() {
let now = newDate();

// this.birthdate is the birthdate property above
let years = (now-this.birthdate) / millisecondsPerYear;

return Math.floor (years);
}
};

mark.getAge();// 33
```

In the example above, it looks like we _could_ have usedmarkinstead of _this_. But objects aren’t always assigned to named variables and what’s stored in a specific variable can change, whereas the value ofthiswill always point to the object it belongs to

### 4.2 Standard Library.

#### 4.2.1 Strings.

Under the hood strings are actually objects. That means that strings have various

properties and methods:
```js
let str ="A String";

// properties
str.length;// 8

// methods
str.charAt( 2 );// "S"
str.substr( 2 , 3 );// "Str" - start at index 2, for 3 characters
str.toLowerCase();// "a string"
str.toUpperCase();// "A STRING"
```
A full list of properties can be found onMDN.

#### 4.2.2 Date

The built-inDateobject allows you to manipulate dates.
```js
let now = new Date();// a date object representing now

// a date representing 5:08 am on 24th August 2018
let birthdate = newDate("2018-08-24T05:08:00");

birthdate.getFullYear();// 2018
birthdate.getDate();// 24
birthdate.getDay();// 5 (0 - 6, where 0 is Sunday and 6 is Saturday)
birthdate.getMonth();// 7 (0 - 11, where 0 is January and 11 is December - ç'est stupide)
birthdate.getTime();// 1535083680000
```
Generally it’s easier to use a library likemoment.js.


**The Beginning of Time**


You might be wondering what the 1535083680000 value from .getTime() represents.

It is, of course , the number of milliseconds between the given date and 00:00 GMT on the 1st of January 1970.

#### 4.2.3 Math

The Math object lets you do more complex mathematical operations:
```js
// Useful properties
Math.PI;// 3.141592653589793
Math.E;// 2.718281828459045

// Rounding
Math.floor(3.45);// 3
Math.ceil(3.45);// 4
Math.round(3.45);// 3

// Exponents
Math.sqrt( 4 );// 2
Math.pow( 2 , 3 );// 8

// Other mathematical functions
Math.log( 6 );// 1.791759469228055
Math.cos( 45 );// 0.5253219888177297
```

**Putting the Java in JavaScript**

The Date and Math objects both feel decidedly un-JavaScripty. That’s because they were taken directly from Java.

JavaScript was originally going to be called “Mocha” and then “LiveScript”. But Netscape, the creators of JavaScript, settled on “JavaScript” after making a deal with Sun, the creators of Java. Sun agreed to give Netscape some money as long as they
called their new language “JavaScript” to make it sound like a toy version of Java. Sun also insisted that JavaScript include the Date and Mathobjects from Java - despite the fact that Java and JavaScript have barely anything in common other than that they both ran in a browser.

Ironically JavaScript went on to eclipse Java as the language of choice for apps that would run on any system.

This also means that Oracle, who bought Sun in 2010, own the trademark on the name “JavaScript”. That’s why it’s generally referred to as ECMAScript (after the European Computer Manufacturers Association, who control the standard) in any technical documentation.

### 4.3 Advanced Object Techniques

#### 4.3.1 Destructuring

**Destructuring** allows us to pull property values out of an object and into variables of the same name as the original property:
```js
// creates the firstName and lastName variables
// from those properties of person
let {firstName, lastName} = person;
``````
When passing an object to a function we can use destructuring syntax in the function parameters, which an make the function a bit tidier:
```js
let person={
firstName: "Mark",
lastName: "Wales",
};

// destructure in the parameters
letfullName=({firstName,lastName})=>firstName+" "+lastName;

fullName(person);// "Mark Wales"
```
Without:
```js
let fullName = ob => ob.firstName +" "+ ob.lastName;
```
Destructuring can’t be used on two objects with the same property names at the same time, as they would need to use the same variable name.
```js
// creates the firstName and lastName variables from
// those properties of person
let {firstName,lastName} = person1;

// won't work, because firstName and lastName already taken
let {firstName,lastName} = person2;
```

#### 4.3.2 The Spread Operator.

The spread operator with objects is similar to the array spread operator. It lets us create a copy of an object:
```js
let person = {
name: "Sandy",
age: 54 ,
};

// creates a copy of person
let copied = {...person};
```
We can also change a property whilst copying:
```js
let person ={
name: "Sandy",
age: 54 ,
};

// creates a copy of person and changes the age property
let copied = {...person, age: 55 };
```
And we can merge two objects together:
```js
let personProps={
name: "Sandy",
age: 54 ,
};

let otherPersonProps={
name: "Noel",
favouriteColour: "orange",
};

// merges two objects
// the second object overwrites any matching properties of the first
let merged = {...personProps,...otherPersonProps};
// gives us: { name: "Noel", age: 54, favouriteColour: "orange"}
```
As with arrays, this can be useful if we need to make sure we’re not changing the original object.


#### 4.3.3 Keys and Values

It is sometimes useful to get just the keys or values of an object. To do this we can use the Object.keys()  and Object.values() functions:
```js
let person={
firstName:"Mark",
lastName:"Wales",
};

let keys=Object.keys(person);
let values=Object.values(person);

console.log(keys);// ["firstName", "lastName"]
console.log(values);// ["Mark", "Wales"]

keys.forEach (key => console.log(person [key]));
```
These are useful when you treat an object more like an array: as a collection of the same sorts of thing.

This can be useful as it allows us to immediately access an item based on its key without having to go over every item in the structure:
```js
// we can use the key to access each item individually
let people = {
345 :{
id: 345 ,
name:"Ta-Nehisi",
age: 43 ,
},
789 :{
id: 789 ,
name:"Reni",
age: 29 ,
}
};
```
When objects are used this way we call them **maps**.

Modern JavaScript actually has aMaptype built in, but it’s not used much


### 4.4 Classes.

We can also create abstract concepts ( **classes** ) of objects:
```js
class Person{
constructor (name, dob){
this.name = name;
this.dob = dob;
}


getAge(){
let now = newDate();
let millisecondsPerYear= 31556952000 ;
let years=(now-this.dob)/millisecondsPerYear;

return Math.floor(years);
}
}
```

This allows us to create **instances** of the same object type, without having to repeat the same object literal.

Each instance has its own set of properties and internally this refers to the specific instance it belongs to:

```js
// we use the "new" keyword to create an "instance" of Person
let mark = newPerson("Mark",newDate("1984-04-16"));
let jane = newPerson("Jane",newDate("1973-11-27"));

// we get back two separate ages, as they are different instances
console.log(mark.getAge(), jane.getAge());
```
Note that we give classes names with capital letters:Personrather thanperson.

You don’t have to, but it makes it much more obvious what your code is doing.


#### 4.4.1 An Example

A book class:
```js
class Book{
constructor(title,author){
this.title = title;
this.author = author;
this.price = null;
}

set Price(value){
this.price=value;
return this;
}

get Price(){
if (this.price=== null){
return "Unknown";
}

return "£"+this.price.toFixed( 2 );
}
}

let book = newBook ("Lord of the Rings","JRRRRR Tolkien");
console.log (book.getPrice());// "Unknown"

book.setPrice(9.9);
console.log(book.getPrice());// "£9.99"
```
It’s considered good practice to write **getter** and **setter** methods for reading and writing properties when using classes.

In the example above if we just didbook.pricewe’d get backnullsome of the time. Whereas if we write a **getter** function we can guarantee that it always comes back with a useful value that we can show to a user.

**Returning** this

We often return this from **setter** methods: i.e. methods that accept values but don’t have an obvious return value.
```js
class Book{
// 


set Price(value){
this.price = value;


// return this from set Price
return this;
}
```
##### // ...

##### }

This allows us to **chain** together methods on an object:
```js
// because .setPrice returns the book object
// we can then run .getPrice on it
book.setPrice( 99 ).getPrice();
```
**Note** : it wouldn’t make sense to returnthisfrom **getter** methods, as the whole point of a getter method is to return a specific value


### 4.5 Additional Resources.

- Eloquent JavaScript: Objects and Arrays
- MDN: Objects
- MDN: Object Basics
- MDN:Math
- MDN:Date
- The JavaScriptDateObject
- MDN: Object Destructuring
- MDN: Classes
- ES5 Getters and Setters- an alternative way to do getters/setters
