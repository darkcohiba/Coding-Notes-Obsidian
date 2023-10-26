---
tags:
  - array
  - javascript
type: array method
---
# Basics
- The **`findLastIndex()`** method of [[Array]] instances iterates the array in reverse order and returns the index of the first element that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.
- See also the [[findLast()]] method, which returns the value of last element that satisfies the testing function (rather than its index). [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findLastIndex)
```javascript
const array1 = [5, 12, 50, 130, 44];

const isLargeNumber = (element) => element > 45;

console.log(array1.findLastIndex(isLargeNumber));
// Expected output: 3
// Index of element with value: 130
```

