---
tags:
  - python
  - CLI
---
# Basics
-  **Inquirer** should ease the process of asking end user **questions**, **parsing**, **validating** answers, managing **hierarchical prompts** and providing **error feedback**. [PyPi](https://pypi.org/project/inquirer/)
- [Documentation](https://python-inquirer.readthedocs.io/en/latest/)

## Installation
- To install it, just execute:
```bash
pip install inquirer
```

- Import inquirer on the top of our file
```python
import inquirer
```
## Text Question
- This is a simple text input similar to the python built in input
```python
import inquirer

questions = [
inquirer.Text(name='name', message="What's your name?"),
]
# call our questions through the prompt and add the green passion theme!
answers = inquirer.prompt(questions)
# to access the answers we can use block notation.
print(f"Name: {answers['name']}\n")
```

## Confirm Question
- This question renders a yes or no option for the user.
- This results in a true or false result
```python
questions = [
inquirer.Confirm('continue', message="Ready to Shop!"),
]
answers = inquirer.prompt(questions)

print(f"Excited: {answers['continue']}\n")
```

## List Question
- This question renders a list of options in the form of a dropdown, the user can only choose one
```python
questions = [
inquirer.Confirm('continue', message="Ready to Shop!"),
]
answers = inquirer.prompt(questions)

print(f"Excited: {answers['continue']}\n")
```

## Checkbox Question
- This question renders a dropdown of checkboxes, the user can select multiple options
```python
questions = [
inquirer.Checkbox(
"Language",
message="What is your favorite coding language?",
choices=["Javascript", "C++", "C#", "Python", "Go"],
),
]
answers = inquirer.prompt(questions)

print(f"Favorite Languages: {list(answers['Language'])}\n")
```

