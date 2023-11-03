---
tags:
  - CLI
  - python
type: python package
---
# Basics
- Rich is a Python library for _rich_ text and beautiful formatting in the terminal.

- The [Rich API](https://rich.readthedocs.io/en/latest/) makes it easy to add color and style to terminal output. Rich can also render pretty tables, progress bars, markdown, syntax highlighted source code, tracebacks, and more — out of the box.[Documentation](https://github.com/Textualize/rich)

![[Pasted image 20231103104057.png]]
## [Installing](https://github.com/Textualize/rich#installing)

Install with `pip` or your favorite PyPI package manager.

```shell
python -m pip install rich
```

Run the following to test Rich output on your terminal:

```shell
python -m rich
```

## Basic Colors [](https://github.com/Textualize/rich#rich-print)
- To simply add blue to our color we can import the print tool from Rich and provide our colors in brackets
```python
from rich import print as pprint

pprint("[blue]Hello")
```
-  If we only have the color on the front of the string, the color will run into the end of the string. Below is how we can have multiple colors in one string. 
```python
pprint("[blue]Hello,[/blue] [red bold]Goodbye,[/red bold] have fun!")
```
- In the above example Hello is blue, Goodbye is blue and bold, and have fun is the typical terminal white.
## Emojis
- To print an emoji we can simply provide two :s and put the emoji text in between
```python
pprint(":vampire:")
# 🧛
```

## Console
- For complete control over terminal formatting, Rich offers a [`Console`](https://rich.readthedocs.io/en/latest/reference/console.html#rich.console.Console "rich.console.Console") class. Most applications will require a single Console instance, so you may want to create one at the module level or as an attribute of your top-level object. For example, you could add a file called “console.py” to your project:

```python
from rich.console import Console
console = Console()
```

- Then you can import the console from anywhere in your project like this:

```python
from my_project.console import console
```

- The console object handles the mechanics of generating ANSI escape sequences for color and style. It will auto-detect the capabilities of the terminal and convert colors if necessary.
- Simple use of this console
```python
console.print([1, 2, 3])

console.print("[blue underline]Looks like a link")

console.print("FOO", style="white on blue")
```
- output
![[Screenshot 2023-11-03 at 11.54.26 AM.png]]

- We also have access to a .log function console that gives user debugging tools like the time it was rendered
```python
# logging adds the time next to it
console.log("Hello, World!")
# output [11:59:36] Hello, World!
```

- We can also add a style variable and a width to our console
```python
# We can also set a width and a style variable and use it on console
console = Console(width=20)
style = "bold white on blue"
console.print("Rich", style=style)
```
- We can also align our terminal with the left, right, and center of the terminal output
```python
console.print("Rich", style=style, justify="left")
console.print("Rich", style=style, justify="center")
console.print("Rich", style=style, justify="right")
```
- output
![[Pasted image 20231103124937.png]]
- We can also take the user input with the console
```python
# taking input!
name = console.input("What is [i]your[/i] [bold red]name[/]? :smiley: ")
console.print(f'Hello {name}', style='italic white on black', justify='center')
```