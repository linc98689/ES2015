# Rest / Spread Operator Exercises

In this exercise, you’ll refactor some ES5 code into ES2015.

### Given this function:

```javascript
function filterOutOdds() {
  var nums = Array.prototype.slice.call(arguments);
  return nums.filter(function (num) {
    return num % 2 === 0;
  });
}
```

##### Answer

```javascript
function filterOutOdds(...args) {
  return args.filter((arg) => arg % 2 === 0);
}
```

### findMin

Write a function called findMin that accepts a variable number of arguments and returns the smallest argument.

Make sure to do this using the rest and spread operator.

##### Answer

```javascript
const findMin = (...arr) => Math.min(...arr);
```

### mergeObjects

Write a function called mergeObjects that accepts two objects and returns a new object which contains all the keys and values of the first object and second object.

##### Answer

```javascript
const mergeObjects = (obj1, obj2) => ({ ...obj1, ...obj2 });
```

### doubleAndReturnArgs

Write a function called **_doubleAndReturnArgs_** which accepts an array and a variable number of arguments. The function should return a new array with the original array values and all of additional arguments doubled.

##### Answer

```javascript
const doubleAndReturnArgs = (arr, ...moreArgs) => [
  ...arr,
  ...moreArgs.map((e) => 2 * e),
];
```

### Slice and Dice!

For this section, write the following functions using rest, spread and refactor these functions to be arrow functions!

Make sure that you are always returning a new array or object and not modifying the existing inputs.

##### Answer

```javascript
/** remove a random element in the items array
and return a new array without that item. */

function removeRandom(items) {
  let randNum = Math.floor(Math.random() * items.length);
  return items.filter((e, idx) => idx !== randNum);
}

/** Return a new array with every item in array1 and array2. */

function extend(array1, array2) {
  return [...array1, ...array2];
}
const extend_1 = (arr1, arr2) => [...arr1, ...arr2];

/** Return a new object with all the keys and values
from obj and a new key/value pair */

function addKeyVal(obj, key, val) {
  let copy = { ...obj };
  copy[key] = val;
  return copy;
}

/** Return a new object with a key removed. */

function removeKey(obj, key) {
  let copy = { ...obj };
  delete copy[key];
  return copy;
}

/** Combine two objects and return a new object. */

function combine(obj1, obj2) {
  return { ...obj1, ...obj2 };
}

/** Return a new object with a modified key and value. */

function update(obj, key, val) {
  let copy = { ...obj };
  copy[key] = val;
  return copy;
}
```
