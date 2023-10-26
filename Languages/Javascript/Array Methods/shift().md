---
tags:
  - array
  - javascript
type: array method
---
# Basics
- The **`shift()`** method of [[Array]] instances removes the **first** element from an array and returns that removed element. This method changes the length of the array. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
```javascript
const array1 = [1, 2, 3];

const firstElement = array1.shift();

console.log(array1);
// Expected output: Array [2, 3]

console.log(firstElement);
// Expected output: 1

```
