---
tags:
  - array
  - javascript
type: array method
---
# Basics
- The **`splice()`** method of [[Array]] instances changes the contents of an array by removing or replacing existing elements and/or adding new elements [in place](https://en.wikipedia.org/wiki/In-place_algorithm).

- To create a new array with a segment removed and/or replaced without mutating the original array, use [[toSpliced()]] To access part of an array without modifying it, see [[Languages/Javascript/String Methods/slice()]]. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)

```javascript
const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// Inserts at index 1
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, 'May');
// Replaces 1 element at index 4
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "May"]

```
