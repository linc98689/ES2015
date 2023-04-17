# Object Enhancements Exercise

In this exercise, you’ll refactor some ES5 code into ES2015. Write your code in the sections with a comment to “Write an ES2015 Version”.

### Same keys and values

```javascript
function createInstructor(firstName, lastName) {
  return {
    firstName: firstName,
    lastName: lastName,
  };
}
```

##### Answer

```javascript
const createInstructor = (firstName, lastName) => ({
  firstName,
  lastName,
});
```

### Computed Property Names

```javascript
var favoriteNumber = 42;

var instructor = {
  firstName: "Colt",
};

instructor[favoriteNumber] = "That is my favorite!";
```

##### Answer

```javascript
let favoriteNumber = 42;

let instructor = {
  firstName: "Colt",
  [favoriteNumber]: "That is my favorite!",
};
```

### Object Methods

```javascript
var instructor = {
  firstName: "Colt",
  sayHi: function () {
    return "Hi!";
  },
  sayBye: function () {
    return this.firstName + " says bye!";
  },
};
```

##### Answer

```javascript
let instructor = {
  firstName: "Colt",
  sayHi() {
    return "Hi!";
  },
  sayBye() {
    return this.firstName + " says bye!";
  },
};
```

### createAnimal function

Write a function which generates an animal object. The function should accepts 3 arguments:

- species: the species of animal (‘cat’, ‘dog’)
- verb: a string used to name a function (‘bark’, ‘bleet’)
- noise: a string to be printed when above function is called (‘woof’, ‘baaa’)

Use one or more of the object enhancements we’ve covered.

##### Answer

```javascript
const createAnimal = (species, verb, noise) => ({
  species,
  [verb]() {
    console.log(noise);
  },
});
```
