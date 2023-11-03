---
tags:
  - CLI
  - python
type: python package
---
# Basics
- Click is a Python package for creating beautiful command line interfaces in a composable way with as little code as necessary. It’s the “Command Line Interface Creation Kit”. It’s highly configurable but comes with sensible defaults out of the box.

- It aims to make the process of writing command line tools quick and fun while also preventing any frustration caused by the inability to implement an intended CLI API.

- Click in three points:
	- arbitrary nesting of commands
	- automatic help page generation
	- supports lazy loading of subcommands at runtime
- [Documentation](https://click.palletsprojects.com/en/8.1.x/)

## Installation
- To install it, just execute:

```bash
pipenv install click
```

- Import inquirer on the top of our file

```python
import click
```

## Basic Usage
- Create a function and apply the click property to it, we use click.echo instead of print with click. click.echo gives us access to click.style which provides styling to our print
```python
@click.command()
def hello():
	click.echo(click.style('Hello World!', bg='blue',fg='green'))

hello()
```
- We can also use the .secho command on click to add style within the echo.
```python
@click.command()
def hello():
	click.secho('HELLO!', bold=True)
	
hello()
```

## Groups
- Groups allow us to nest commands within one command. By calling one command we have access to multiple nested function
```python
@click.group()
def cli():
	pass
	
@click.command()
def initdb():
	click.echo('Initialized the database')

@click.command()
def dropdb():
	click.echo('Dropped the database')
 
cli.add_command(initdb)
cli.add_command(dropdb)

if __name__ == '__main__':
	cli()
```
- We can do this another way that removes the need to add `cli.add_command()`
```python
@click.group()
def cli():
	pass
	
@cli.command()
def initdb():
	click.echo('Initialized the database')

@cli.command()
def dropdb():
	click.echo('Dropped the database')
```

- With the above code we can only call one command at a time, we can add `chain=True`, show below
```python
@click.group(chain=True)
def cli():
	pass
```
## Progress bar
- With .progressbar we can create a progress bar that can take in an array value for its size
```python
import time

with click.progressbar([1, 2, 3]) as bar:
	for x in bar:
		print(f"sleep({x})...")
		time.sleep(x)
```

- output
```bash
$  python click_example.py
$  [------------------------------------]    0%sleep(1)...
$  [############------------------------]   33%  00:00:02sleep(2)...
$  [########################------------]   66%  00:00

```

## Single Character Input
- Get a single character input and assign it to a variable
```python
click.echo('Continue? [yn] ', nl=False)
c = click.getchar()
click.echo()
if c == 'y':
	click.echo('We will go on')
elif c == 'n':
	click.echo('Abort!')
else:
	click.echo('Invalid input :(')
```
## User Input and Parameters
- We can create click options as decorators that will ask the user prompts and use those prompts in functions
- We tell the option that is it a prompt and provide the prompt text through help
```python
@click.command()
@click.option('--name', prompt=True, help='Your name')
@click.option('--size', type=click.Choice(['Small', 'Medium', 'Large', 'Extra Large'], case_sensitive=False), prompt=True, help='Your clothing size')

def get_user_info(name, size):
# Output the collected information
	click.echo(f"Name: {name}, Selected size: {size}")

get_user_info()
```
