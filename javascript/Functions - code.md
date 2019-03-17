# Functions - code

A function, divide, that takes two numbers as arguments. The function should return the first number divided by the second number.
```js
let divide = (a, b) => a / b; 

console.log(divide(4, 2)); // 2
console.log(divide(20, 2)); // 10
```

A function, divide3, that takes three numbers as arguments. The function should return the first number divided by the second number divided by the third number.
```js
let divide3 = (a, b, c) => a / b / c;

console.log(divide3(8, 2, 2)); // 2
console.log(divide3(100, 20, 5)); // 1
```

A function, stone, that takes a weight in kg and converts it to stone
```js
let stone = kg => kg / 6.35;

console.log(
    stone(74), // 11.653
    stone(50), // 7.87365
);
``````
A function, fahrenheit, that takes a temperature in Celsius and converts it to Fahrenheit
```js
let fahrenheit = celcius => {
	return (celcius * 9) / 5 + 32;
};

console.log(
    fahrenheit(12), // 53.6
);
```
A function, average5, that takes five numbers as arguments. The function should return the average of the numbers
```js
let average5 = (a, b, c, d, e) => (a + b + c + d + e) / 5;

console.log(
    average5(1, 2, 3, 4, 5), // 3
);
```

A function even, that takes a number as an argument. The function return true if the number is even and false if it is odd: 
```js
let odd = a => a % 2 !== 0;

let even = b => !odd(b);

console.log(even(1)); // false
console.log(even(2)); // true
```
A function max, that takes two numbers as arguments. The function should return the highest of the numbers.
```js
let max = (a,b) => a > b ? a: b;

console.log(
    max(1, 2), // 2
    max(3, -2), // 3
    max(-3, -5), // -3
);
```
A function min, that takes two numbers as arguments. The function should return the smallest of the numbers.
```js
let min = (a,b) => a < b ? a: b;

console.log(
    min(1, 2), // 1
    min(3, -2), // -2
    min(-3, -5), // -5
);
```
A function factorOf, that takes two numbers as arguments. The function should return true if the first number is a factor of the second number (i.e. the second number divided by the first has no remainder) and false if not.
```js
let factorOf = (a,b) => b % a === 0;

console.log(factorOf(2, 16)); // true
console.log(factorOf(3, 16)); // false
```
Write a function max3 that takes three numbers and returns the largest number. You're not allowed to use Math.max:
```js
let maxfn = (a,b) => a > b ? a: b;

let max3 = (a, b, c) => maxfn(maxfn(a,b),c);
``````

Find the secret message by writing a function that creates a string from every 7th character of the code:

```js
let crack = code => {
	let string = ""
	for (let i = 6; i < code.length; i += 7) {
		string += code.charAt(i)
	}
	return string;
}

const cracked = crack("_5X4EjG4Cm9#Eo 8Dd@Cov_6kNhdk6W8_J .hZ3yTwr6JZ#qoD.74mErj7 2Wbk_wEUx8.X7.v_. D9@Hq Y3Nu.7aot5Ay.8u.Z339z T!98NrdzD@7C2iJ.jf 8d.Upf6X r7P@BSi#xN7H t!YGp8h!5_SygM");

console.log(cracked);
``````

A function, longest, that takes an array of strings and returns the longest string:
```js
let maxfn = (a,b) => a.length > b.length ? a: b;

let longest = words => words.reduce(maxfn, [0]);

let result = longest(["cow", "wombat", "aardvark"]);
console.log("Expected: aardvark, Actual: " + result);

result = longest(["fish", "fishiest", "fishier"]);
console.log("Expected: fishiest, Actual: " + result);
```