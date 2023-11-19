---
tags:
  - string
  - python
type: string method
---
# Basics
- Replace a given character with another character using acsii codes [W3](https://www.w3schools.com/python/ref_string_translate.asp)
```python
#use a dictionary with ascii codes to replace 83 (S) with 80 (P):
mydict = {83:  80}

txt = "Hello Sam!"

print(txt.translate(mydict))
# output Hello Pam!
```
