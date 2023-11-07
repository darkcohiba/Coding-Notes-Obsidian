---
tags:
  - "#python"
type: python package
---
# Basics
- The [`tkinter`](https://docs.python.org/3/library/tkinter.html#module-tkinter "tkinter: Interface to Tcl/Tk for graphical user interfaces") package (“Tk interface”) is the standard Python interface to the Tcl/Tk GUI toolkit. 
- [Documentation](https://docs.python.org/3/library/tkinter.html)
## Installation
- We do not need to install tkinter since it is a base python package
- We do need to import it on the top of our file
```python
from tkinter import *
```

## Window
- First we need to up our window, we need our window before we can place widgets, text or images on it.
- We need to keep our window open with the window.mainloop() function
```python
#Creating a new window and configurations
window = Tk()
window.title("Widget Examples")
window.minsize(width=500, height=500)

window.mainloop()
```

## Widgets
- Tkinter has many different kinds of widgets for us to use on our gui.

### Labels
- Labels are a good place to store text and create titles
- We can create a label specifying the text and later using the .config method to change this text
```python
#Labels
label = Label(text="This is old text")
label.config(text="This is new text")
label.pack()
```

### Buttons
- Buttons have text and we can put a command that happens when clicked, this command is a function
```python
#Buttons
def action():
    print("Do something")

#calls action() when pressed
button = Button(text="Click Me", command=action)
button.pack()
```

### Entries/Inputs
- Entries are our traditional inputs that take a user input
- We can grab the input with the .get method
```python
#Entries
entry = Entry(width=30)
# Add some text to begin with
entry.insert(END, string="Some text to begin with.")
# Gets text in entry
print(entry.get())
# puts the entry onto the window
```

### Text
- This is used to take blocks of user input.
```python
#Text
text = Text(height=5, width=30)
#Puts cursor in textbox.
text.focus()
#Adds some text to begin with.
text.insert(END, "Example of multi-line text entry.")
#Get's current value in textbox at line 1, character 0
print(text.get("1.0", END))
```

### [Spinbox](https://docs.python.org/3/library/tkinter.ttk.html?highlight=listbox#spinbox)
- A spinbox is a number field that goes from the `from_` value to the `to` value. 
- We use a function attached to the command to get the value of the widget
```python
#Spinbox
def spinbox_used():
    #gets the current value in spinbox.
    print(spinbox.get())
spinbox = Spinbox(from_=0, to=10, width=5, command=spinbox_used)
```
- Display
![[Screenshot 2023-11-05 at 7.28.14 PM.png]]
### Scale
- The scale is a vertical bar that the user can move up down, the value goes from the `from_` value to the `to` value
- We use a function attached to the command to get the value of the widget
```python
#Scale
#Called with current scale value.
def scale_used(value):
    print(value)
scale = Scale(from_=0, to=100, command=scale_used)
```
- Display
![[Screenshot 2023-11-05 at 7.28.07 PM.png]]
### Check Button
- Check button is useful tool for getting the user input
- To properly use the check button widget we need to establish a variable state and a command function to use the variable.
```python
#Checkbutton
def checkbutton_used():
    #Prints 1 if On button checked, otherwise 0.
    print(checked_state.get())
#variable to hold on to checked state, 0 is off, 1 is on.
checked_state = IntVar()
checkbutton = Checkbutton(text="Is On?", variable=checked_state, command=checkbutton_used)
checked_state.get()
```

### Radio Button
- Raido button is a useful tool to give a user multiple options that the user can only select one of
```python
#Radiobutton
def radio_used():
    print(radio_state.get())
#Variable to hold on to which radio button value is checked.
radio_state = IntVar()
radiobutton1 = Radiobutton(text="Option1", value=1, variable=radio_state, command=radio_used)
radiobutton2 = Radiobutton(text="Option2", value=2, variable=radio_state, command=radio_used)
```

### Listbox
- A list of inputs that the user can select from
```python
#Listbox
def listbox_used(event):
    # Gets current selection from listbox
    print(listbox.get(listbox.curselection()))

listbox = Listbox(height=4)
fruits = ["Apple", "Pear", "Orange", "Banana"]
for item in fruits:
    listbox.insert(fruits.index(item), item)
listbox.bind("<<ListboxSelect>>", listbox_used)
listbox.pack()
```
- output
