---
tags:
  - array
  - javascript
type: array method
---

# Basics
- The **`findLast()`** method of [[Array]] instances iterates the array in reverse order and returns the value of the first element that satisfies the provided testing function. If no elements satisfy the testing function, [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) is returned. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLast)
```javascript
const array1 = [5, 12, 50, 130, 44];

const found = array1.findLast((element) => element > 45);

console.log(found);
// Expected output: 130
```

- If you need to find:

	- the _first_ element that matches, use [[Languages/Python/String Methods/find()]].
	- the _index_ of the last matching element in the array, use [`findLastIndex()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLastIndex).
	- the _index of a value_, use [`indexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf). (It's similar to [[findIndex()]], but checks each element for equality with the value instead of using a testing function.)
	- whether a value _exists_ in an array, use [`includes()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes). Again, it checks each element for equality with the value instead of using a testing function.
	- if any element satisfies the provided testing function, use [`some()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some).
