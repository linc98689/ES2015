<style>
    .code-important{
        color:red;
        font-family:monospace;
        font-style:italic;
        padding:2px;
        background:#f0fbf7;
    }
</style>

# Destructuring Exercise

### Object Destructuring 1

What does the following code return/print?

```javascript
let facts = { numPlanets: 8, yearNeptuneDiscovered: 1846 };
let { numPlanets, yearNeptuneDiscovered } = facts;

console.log(numPlanets); // 8
console.log(yearNeptuneDiscovered); // 1846
```

### Object Destructuring 2

What does the following code return/print?

```javascript
let planetFacts = {
  numPlanets: 8,
  yearNeptuneDiscovered: 1846,
  yearMarsDiscovered: 1659,
};

let { numPlanets, ...discoveryYears } = planetFacts;

console.log(discoveryYears); // {yearNeptuneDiscovered: 1846,yearMarsDiscovered: 1659}
```

### Object Destructuring 3

What does the following code return/print?

```javascript
function getUserData({ firstName, favoriteColor = "green" }) {
  return `Your name is ${firstName} and you like ${favoriteColor}`;
}

getUserData({ firstName: "Alejandro", favoriteColor: "purple" }); // "Your name is Alejandro and you like purple"
getUserData({ firstName: "Melissa" }); // "Your name is Melissa and you like green"
getUserData({}); // "Your name is undefined and you like green"
```

### Array Destructuring 1

What does the following code return/print?

```javascript
let [first, second, third] = ["Maya", "Marisa", "Chi"];

console.log(first); // "Maya"
console.log(second); // "Marisa"
console.log(third); // "Chi"
```

### Array Destructuring 2

What does the following code return/print?

```javascript
let [raindrops, whiskers, ...aFewOfMyFavoriteThings] = [
  "Raindrops on roses",
  "whiskers on kittens",
  "Bright copper kettles",
  "warm woolen mittens",
  "Brown paper packages tied up with strings",
];

console.log(raindrops); // Raindrops on roses
console.log(whiskers); // whiskers on kittens
console.log(aFewOfMyFavoriteThings); // ["Bright copper kettles", "warm woolen mittens", "Brown paper packages tied up with strings"]
```

### Array Destructuring 3

What does the following code return/print?

```javascript
let numbers = [10, 20, 30];
[numbers[1], numbers[2]] = [numbers[2], numbers[1]];

console.log(numbers); // [10,30,20]
```

### ES2015 Refactoring

In this exercise, you’ll refactor some ES5 code into ES2015.

##### ES5 Assigning Variables to Object Properties

```javascript
var obj = {
  numbers: {
    a: 1,
    b: 2,
  },
};

var a = obj.numbers.a;
var b = obj.numbers.b;
```

##### Answer

```javascript
let obj = {
  numbers: {
    a: 1,
    b: 2,
  },
};

let {
  numbers: { a, b },
} = obj;
```

##### ES5 Array Swap

```javascript
var arr = [1, 2];
var temp = arr[0];
arr[0] = arr[1];
arr[1] = temp;
```

##### Answer

```javascript
let arr = [1, 2];
[arr[1], arr[0]] = [arr[0], arr[1]];
```

### raceResults()

Write a function called **_raceResults_** which accepts a single array argument. It should return an object with the keys **_first_**, **_second_**, **_third_**, and **_rest_**.

- first: the first element in the array
- second: the second element in the array
- third: the third element in the array
- rest: all other elements in the array

**Write a *one line* function to make this work using**

- An arrow function
- Destructuring
- <span class="code-important">Enhanced </span> object assignment (same key/value shortcut)

```javascript
const raceResults = ([first, second, third, ...rest]) => ({
  first,
  second,
  third,
  rest,
});

raceResults(["Tom", "Margaret", "Allison", "David", "Pierre"]);

/*
  {
    first: "Tom",
    second: "Margaret",
    third: "Allison",
    rest: ["David", "Pierre"]
  }
*/
```
