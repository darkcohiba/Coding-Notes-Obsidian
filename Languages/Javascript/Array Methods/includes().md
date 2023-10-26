---
tags:
  - array
  - javascript
type: array method
title: includes()
---
# Basics
- The **`includes()`** method of [[Array]] instances determines whether an array includes a certain value among its entries, returning `true` or `false` as appropriate. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)
```javascript
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// Expected output: true

const pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// Expected output: true

console.log(pets.includes('at'));
// Expected output: false
```
