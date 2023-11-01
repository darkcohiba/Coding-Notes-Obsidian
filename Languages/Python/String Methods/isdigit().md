---
tags:
  - string
  - python
type: string method
---
# Basics
- The `isdigit()` method returns True if all the characters are digits, otherwise False.
- Exponents, like ², are also considered to be a digit. [W3](https://www.w3schools.com/python/ref_string_isdigit.asp)
```python
txt = "\u00B2"
x = txt.isdigit()
print(x)
# output True
```
