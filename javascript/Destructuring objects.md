# Destructuring objects

We saw earlier how spread operator can effectively spread, or unpack, the contents of the array.

We can do something similar with objects as well. _Destructuring assignment_ is a special syntax for neatly assigning values taken directly from an object to variables.

Consider the following ES5 code:
  ```
    var voxel = {x: 3.6, y: 7.4, z: 6.54 };
    var x = voxel.x; // x = 3.6
    var y = voxel.y; // y = 7.4
    var z = voxel.z; // z = 6.54
  ```

Here's the same assignment statement with ES6 destructuring syntax:

    const { x, y, z } = voxel; // x = 3.6, y = 7.4, z = 6.54

If instead you want to store the values of `voxel.x` into `a`, `voxel.y` into `b`, and `voxel.z` into `c`, you have that freedom as well.

    const { x : a, y : b, z : c } = voxel // a = 3.6, b = 7.4, c = 6.54

You may read it as "get the field `x` and copy the value into `a`," and so on.

# Destructuring from nested objects

We can similarly destructure nested objects into variables.

Consider the following code:

    const a = {
      start: { x: 5, y: 6},
      end: { x: 6, y: -9 }
    };
    const { start : { x: startX, y: startY }} = a;
    console.log(startX, startY); // 5, 6

In the example above, the variable `start` is assigned the value of `a.start`, which is also an object.

# Destructuring to assign variables from arrays

ES6 makes destructuring arrays as easy as destructuring objects.

One key difference between the spread operator and array destructuring is that the spread operator unpacks all contents of an array into a comma-separated list. Consequently, you cannot pick or choose which elements you want to assign to variables.

Destructuring an array lets us do exactly that:

    const [a, b] = [1, 2, 3, 4, 5, 6];
    console.log(a, b); // 1, 2

The variable `a` is assigned the first value of the array, and `b` is assigned the second value of the array.

We can also access the value at any index in an array with destructuring by using commas to reach the desired index:

    const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
    console.log(a, b, c); // 1, 2, 5


# Use Destructuring Assignment with the Rest Operator to Reassign Array Elements

In some situations involving array destructuring, we might want to collect the rest of the elements into a separate array.

The result is similar to `Array.prototype.slice()`, as shown below:

    const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
    console.log(a, b); // 1, 2
    console.log(arr); // [3, 4, 5, 7]

Variables `a` and `b` take the first and second values from the array. After that, because of rest operator's presence, `arr` gets rest of the values in the form of an array.

The rest element only works correctly as the last variable in the list. As in, you cannot use the rest operator to catch a subarray that leaves out last element of the original array.

# Use Destructuring Assignment to Pass an Object as a Function's Parameters

In some cases, you can destructure the object in a function argument itself.

Consider the code below:

    const profileUpdate = (profileData) => {
      const { name, age, nationality, location } = profileData;
      // do something with these variables
    }

This effectively destructures the object sent into the function. This can also be done in-place:

    const profileUpdate = ({ name, age, nationality, location }) => {
      /* do something with these fields */
    }

This removes some extra lines and makes our code look neat.

This has the added benefit of not having to manipulate an entire object in a function; only the fields that are needed are copied inside the function.

# Other links
[Mozilla Hacks](https://hacks.mozilla.org/2015/05/es6-in-depth-destructuring/)  - excellent

[MDN reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
