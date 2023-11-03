---
tags:
  - python
  - CLI
type: python package
---
# Basics
- Python Fire is a Python library that will turn any Python component into a command line interface with just a single call to `Fire`.
## Installation

- To install Python Fire from pypi, run:

```bash
pipenv install fire
```

## Basic Usage
- We can create a function and called it with Fire
```python
def hello(name):
	return f'Hello {name}'

if __name__ == '__main__':
	# we can either pass one argument in, multiple arguments in or leave it      blank and fire.Fire will automatically take in every argument from our      file
	fire.Fire(hello)
```

- If we run the file with the argument name, it will look like this
```bash
$ python fire_example.py --name sam
$ Hello sam
```