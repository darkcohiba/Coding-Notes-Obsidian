---
tags:
  - string
  - python
type: string method
---
# Basics
- The `encode()` method encodes the string, using the specified encoding. If no encoding is specified, UTF-8 will be used. [W3](https://www.w3schools.com/python/ref_string_encode.asp)
```python
txt = "My name is Ståle"

x = txt.encode()

print(x)
# output: b'My name is St\xc3\xa5le'
```
