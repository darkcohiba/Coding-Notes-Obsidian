---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`padStart()`** method of [[String]] values pads this string with another string (multiple times, if needed) until the resulting string reaches the given length. The padding is applied from the start of this string. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padStart)
```javascript
const str1 = '5';

console.log(str1.padStart(2, '0'));
// Expected output: "05"

const fullNumber = '2034399002125581';
const last4Digits = fullNumber.slice(-4);
const maskedNumber = last4Digits.padStart(fullNumber.length, '*');

console.log(maskedNumber);
// Expected output: "************5581"
```
