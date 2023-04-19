# Maps and Sets Exercise

### Quick Question #1

What does the following code return?

```javascript
new Set([1, 1, 2, 2, 3, 4]);
// return a set with content of 1,2,3,4
```

### Quick Question #2

What does the following code return?

```javascript
[...new Set("referee")].join("");
//ref
```

### Quick Questions #3

What does the Map m look like after running the following code?

```javascript
let m = new Map();
m.set([1, 2, 3], true);
m.set([1, 2, 3], false);
// value false replaces true
```

### hasDuplicate

Write a function called hasDuplicate which accepts an array and returns true or false if that array contains a duplicate

```javascript
const hasDuplicate = (arr) => arr.length !== new Set(arr).size;

hasDuplicate([1, 3, 2, 1]); // true
hasDuplicate([1, 5, -1, 4]); // false
```

### vowelCount

Write a function called vowelCount which accepts a string and returns a map where the keys are numbers and the values are the count of the vowels in the string.

```javascript
const vowelCount = (str) => {
  const arrVowels = "aeiou".split("");
  let [a, e, i, o, u] = arrVowels;
  let vowels = str.split("").filter((elm) => {
    const setVowels = new Set(arrVowels);
    return setVowels.has(elm);
  });
  const counts = new Map();
  counts.set(a, 0);
  counts.set(e, 0);
  counts.set(i, 0);
  counts.set(o, 0);
  counts.set(u, 0);
  for (let el of vowels) {
    counts.set(el, counts.get(el) + 1);
  }
  // remove key-value with value=0
  let entries = counts.entries();
  for (let [key, value] of entries) {
    if (counts.get(key) === 0) counts.delete(key);
  }
  return counts;
};

vowelCount("awesome"); // Map { 'a' => 1, 'e' => 2, 'o' => 1 }
vowelCount("Colt"); // Map { 'o' => 1 }
```
