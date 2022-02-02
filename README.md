<h1 align="center">Password Generator by Eur1p3des</h1>

[![Made With - Python](https://img.shields.io/badge/Made_With-Python-2ea44f?style=for-the-badge&logo=python)](https://python.org)

<p align="justify">This repository contains a python file that allows you to generate random passwords with an specific lenght defined by the user.</p>

<h3 align="center"> Code Structure </h3>
<p align="justify"> This code has the following structure</p>

1. Import the required libraries:

```py
from tkinter import *
from random import randint
```
2. The next step is to start our app and define the basic configurations:

```py
################################
#   Root window definitions    #
################################
root = Tk()
root.title('Password Generator by Eur1p3des')
root.geometry("900x400")
root.configure(background='#1d1d1d')
```
3. Now we can continue to define some functions that will be used later on our app:

```py
################################
#          Funtions            #
################################
# Funtion to generate the random password with the specified size
def new_rand():
    #Clear Entry Box
    pw_entry.delete(0, END)

    # Get passwd length
    pw_length = int(my_entry.get())

    # Create a variable to hold our password
    my_password = ''

    # Loop through lenght
    for x in range(pw_length):
        my_password += chr(randint(33,126))

    # Output our password
    pw_entry.insert(0, my_password)


# Function to copy the generated password to the clipboard
def clipper():
    root.clipboard_clear()
    root.clipboard_append(pw_entry.get())
```
4. We can now proceed create our input field and our text field where the password will be displayed:

```py
################################
#       Input Content          #
################################
lf = LabelFrame(root, text="How many characters do you want your password?", font=("Raleway", 24), bg='#1d1d1d', fg='#EDE2CB')
lf.pack(pady=20)


# Create entry box to designate number of chars.
my_entry = Entry(lf, font=("Raleway", 24), bg='#1d1d1d', fg='#EDE2CB')
my_entry.pack(pady=20, padx=20)


# Create Entry box for our returned password.
pw_entry = Entry(root, text='', font=("Raleway",24), bd=0, bg='#1d1d1d', fg='#EDE2CB')
pw_entry.pack(pady=20)

# Create a frame for our buttons
my_frame = Frame(root)
my_frame.pack(pady=20)
```
4. The final part of the code contains our buttons to generate the password and to copy it to the clipboard
and the tag to end our program:

```py
################################
#           Buttons            #
################################
# Button to generate the password
my_button = Button(my_frame, text="Generator Strong Password", bd=0, cursor="hand1", command=new_rand, font=("Raleway",18), bg='#1d1d1d', fg='#EDE2CB', activeforeground='#1d1d1d', activebackground='#EDE2CB')
my_button.grid(row=0, column=0)
# Button to copy the password to the clipboard
clip_button = Button(my_frame, text="Copy to clipboard", bd=0, cursor="hand1", command=clipper, font=("Raleway", 18), bg='#1d1d1d', fg='#EDE2CB', activeforeground='#1d1d1d', activebackground='#EDE2CB')
clip_button.grid(row=0, column=1)

#End program
root.mainloop()
```

If you want to run the app, in your command prompt you must run the following command:
```sh
python password.py
```
