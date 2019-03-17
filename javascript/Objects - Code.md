# Objects - Code

An object that uses a string, number, boolean, array, and object for the properties.
```js
let me = {
	name: "Joe",
	age: 31,
	birthplace: "Bath",
	male: true, 
	sports: ["football", "squash", "hiking", "cycling"],
	wife: { name: "Mei", age: 31 };
};
console.log(me);
```

A function, oap, that takes a object with an age property. It should return true if the age property is greater than 65 otherwise it should return false.
```js
let oap = (person) => person.age > 65;

(() => {
    let a = { name: "Alice", age: 52 };
    let b = { name: "Bob", age: 67 };
    let c = { name: "Charlie", age: 24 };
    let d = { name: "Bob", age: 97 };

    console.log(
        oap(a), // false
        oap(b), // true
        oap(c), // false
        oap(d), // true
    );
})();
```
Create a function, daysSince, that you pass a date. It should tell you how many days have passed since that date:
```js
let daysSince = (givendate) => {
	let today = new Date();
	let past =  new Date(givendate);
	let difference =  Math.floor((today - past) / (1000 * 60 * 60 * 24));
	return difference
}
console.log(
    daysSince("1984-04-16"), // 12 thousand and something
);
``````

Write a function that takes two object literals and returns true if they have the same value for their name or value properties:
```js
let comparePeople = (a, b) => a.name === b.name || a.value === b.value;

(() => {
    let first = {
        name: "age",
        value: 36,
    };

    let second = {
        name: "cars",
        value: 56,
    };

    let third = {
        name: "age",
        value: 56,
    };

    let result = comparePeople(first, second);
    console.log("Expected: false, Actual: " + result);

    result = comparePeople(first, third);
    console.log("Expected: true, Actual: " + result);

    result = comparePeople(second, third); // true
    console.log("Expected: true, Actual: " + result);
})();
```