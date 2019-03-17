# Loops - code

### Fizz Buzz
```js
for (let i = 1; i < 100; i += 1) {
	
	if ((i % 3 === 0) && (i % 5 === 0)) {
		console.log("fizzbuzz");
	} else if (i % 3 === 0) {
		console.log("fizz");
	} else if (i % 5 === 0) {
		console.log("buzz");
	}

    console.log(i);
}
```


### for loops
Code that lists the numbers from 1 to 100 using a for loop
```js
for (let i = 1; i < 101; i += 1) {
    console.log(i);
}
```
Code that lists all multiples of 13 up to 1,000 using a for loop
```js
for (let i = 0; i <= 1001; i += 13) {
    console.log(i);
}
``````
Code that outputs any even numbers between 1 and 50 that are also divisible by 3
```js
for (let i = 1; i < 50; i += 1)

    if (i % 3 === 0 && i % 2 === 0) {            
    console.log(i);  
 } 
 ```
 
Code that outputs 50 lines, alternating between ☃☃☃ and ❄❄❄
 ```js
 for (let i = 1; i < 50; i += 1) {

    if (i % 2 === 0)  {         
    console.log("☃☃☃");  
	}

	else {            
    console.log("❄❄❄"); 
	}

 } 
 ```
 
Code that outputs a cumulative total of the current line number for 1 to 50:
 ```js
let total = 0;

for (let i = 1; i <= 50; i += 1) {
	  total += i
	  console.log(total)
} 
 ```
 
 ### while loops
 Code that lists all multiples of 13 up to 1,000 using a while loop
 ```js
let i = 0;   
                   
while (i < 1000) {              
    i += 13;                     
    console.log(i);   
}
 ```