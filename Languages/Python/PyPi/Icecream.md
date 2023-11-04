---
tags:
  - python
type: python package
---
# Basics
## [IceCream — Never use print() to debug again](https://github.com/gruns/icecream#icecream--never-use-print-to-debug-again)

- Do you ever use `print()` or `log()` to debug your code? Of course you do. IceCream, or `ic` for short, makes print debugging a little sweeter.
- `ic()` is like `print()`, but better:

1. It prints both expressions/variable names and their values.
2. It's 60% faster to type.
3. Data structures are pretty printed.
4. Output is syntax highlighted.
5. It optionally includes program context: filename, line number, and parent function.

- [Documentation](https://github.com/gruns/icecream)

## Installation
- To install it, just execute:

```bash
pipenv install icecream
```

- Import ic from icecream on the top of our file

```python
from icecream import ic
```

##  Variables
- We can use *ic* to print our variables with more detail then a typical print statement.

```python
num1 = 2
ic(num1)
# output ic| num1: 2
```

## Functions
- We can use *ic* inside a basic greeting function, we seed the function call and the resulting output
```python
def greeting(name):
	return f'Hello {name}'

ic(greeting("Sam"))
# ic| greeting("Sam"): 'Hello Sam'
```

- A basic if function
```python
def check_weight(weight, height):
	if height + weight > 200:
		return "Good"
	elif height + weight > 150:
		return 'Good Too'
	elif height + weight > 100:
		return 'Still Good'
	else:
		return 'The most good, but everything is good!'

ic(check_weight(100, 94))

# output ic| check_weight(100, 94): 'Good Too'
```

- Using *ic()* without any arguments is returns helpful information, `ic| icecream_example.py:40 in foo() at 07:55:33.534`
```python
def foo():
	name = input("What is your name ")
	ic(name)
	greeting(name)
	if 1 > 2:
		name = input("What is your name ")
		ic(name)
		greeting(name)
		ic()
	else:
		name = input("What is your name else ")
		ic(name)
		ic(greeting(name))
		ic()
foo()
```
- outcome
```bash
What is your name Sam
ic| name: 'Sam'
What is your name else Still Sam
ic| name: 'Still Sam'
ic| greeting(name): 'Hello Still Sam'
ic| icecream_example.py:40 in foo() at 08:01:30.870
```

