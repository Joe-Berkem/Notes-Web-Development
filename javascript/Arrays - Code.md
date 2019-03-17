# Arrays - Code

A function, squares, that takes an array of numbers as an argument. Return a new array containing the square of each number.
```js
let squares = values => {
	let newArray = [];

	for (let i = 0; i < values.length; i += 1) {
		 	newArray.push (values[i] * values[i]);
	}
	return newArray;	
};

console.log(
    squares([2, 3, 4]), // [4, 9, 16]
    squares([2, 3, 4, 5, 6]), // [4, 9, 16, 25, 36]
);
```

A function, odd, that takes an array of numbers. Return an array containing only the odd numbers.
```js
let odd = values => {
    let oddArray = [];

	for (let i = 0; i < values.length; i += 1) {
		let current = values[i];

		if (current % 2 !== 0) {
		 	oddArray.push(current);
		 }
	}
	return oddArray;		
}

console.log(
    odd([1, 2, 3]), // [1, 3]
    odd([1, 2, 3, 4, 5, 6]), // [1, 3, 5]
);
```

A function, max, that takes an array of numbers. Return the largest number.
```js
let max = values => {
	let maxNum = values [0];
	
	for (let i = 1; i < values.length; i += 1) {
		
		let current = values[i];

		if (current > maxNum) {
		 	maxNum = current;
		}
	}
	return maxNum;	
}

console.log(
    max([2, 4, 6, 4, 7, 5]), // 7
    max([-2, 4, 6, 4, 2, -7, 5]), // 6
    max([-2, -4, -4, -7, -5]), // -2
);
```
## Array Iterator method functions
a function, squares, that takes an array of numbers as an argument. Using .map() return a new array containing the square of each number.
```js
let squares = values => {
    return values.map(val => val * val);
};

console.log(
    squares([2, 3, 4]), // [4, 9, 16]
    squares([2, 3, 4, 5, 6]), // [4, 9, 16, 25, 36]
);
```
A function odd, that takes an array of numbers. Using .filter() return an array containing only the odd numbers.

```js
let odd = values => {
	let oddArray = values.filter(val => val % 2 !== 0);
    return oddArray;
};

console.log(
    odd([1, 2, 3]), // [1, 3]
    odd([1, 2, 3, 4, 5, 6]), // [1, 3, 5]
);
```
A function, max, that takes an array of numbers. Using .reduce() return the largest number
```js
let maxfn = (a,b) => a > b ? a: b;

let max = values => values.reduce(maxfn, [0]);
```

A function, average, that takes an array of numbers as an argument. Using .reduce() return the average value of all the numbers.
```js
let average = values => values.reduce((a, b) => a + b / values.length, 0);
```
A function oddSquares that takes an array of numbers as an argument. Using .map() and .filter() return a new array containing the squares of each number, but only if the square is odd.
```js
let oddSquares = values => values.map(val => val * val).filter(val => val % 2 !== 0);
```
A function, total, that takes an array of shopping item objects and adds their price together.
```js
let total = items => {
    let newArr = items.map(obj => obj.price).reduce((a, b) => a + b, 0);
    return newArr.toFixed(2);
};

(() => {
    let shoppingList = [{
        name: "coffee",
        price: 3.50,
    }, {
        name: "tea",
        price: 2.50,
    }, {
        name: "toblerone",
        price: 3.20,
    }, {
        name: "newspaper",
        price: 0.10,
    }];

    console.log(
        total(shoppingList), // "9.30"
    );
})();
```
A function, names, that takes an array of objects as an argument. Return a string containing all of the object names separated by a comma.
```js
let names = items => items.map(obj => obj.name).join(", ");

(() => {
    let a = { name: "Alice", age: 52 };
    let b = { name: "Bob", age: 34 };
    let c = { name: "Charlie", age: 24 };

    let people = [a, b, c];

    console.log(
        names(people), // "Alice, Bob, Charlie"
    );
})();
```