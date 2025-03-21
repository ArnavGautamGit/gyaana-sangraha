---
{"dg-publish":true,"permalink":"/Python/","tags":["coding"]}
---

***Created on: 15/11/2023
Last updated: 30/12/2023***

----
# Index/Contents
[[Python#1. What is Python?\|#1. What is Python?]]
[[Python#2. Exception Handling in Python! (limited discussion)\|#2. Exception Handling in Python! (limited discussion)]]
[[Python#3. All about Libraries in Python! (limited discussion)\|#3. All about Libraries in Python! (limited discussion)]]
[[Python#4. Unit Tests in Python\|#4. Unit Tests in Python]]
[[Python#5. Data Structures in Python!\|#5. Data Structures in Python!]]
[[Python#6. Input/Output to other files using Python\|#6. Input/Output to other files using Python]]
[[Python#Footnotes\|#Footnotes]]

-----
# 1. What is Python?
_Python_ is a programming language (with syntax rules for writing what is considered valid Python code) and the Python interpreter software that reads source code (written in the Python language) and performs its instructions. You can download the Python interpreter for free [here at python.org](https://python.org/), and there are versions for Linux, macOS, and Windows.

## *1.1 Why name a language as 'Python'?*
The name Python comes from the surreal British comedy group Monty Python, not from the snake. Python programmers are affectionately called Pythonistas, and both Monty Python and serpentine references usually pepper Python tutorials and documentation.

## *1.2 Variables and Operators in Python*
If you wanna define a variable a, then directly write a. No need to have int/char/whateveer written before it. This is not C++.
```Python
a = 2 + 2
print(a)
# should give you 4 as output
```
Even though we have most basic C operators which include the basic plus, minus, multiply (use $*$), divide (use /)
We have some comparitively advance maths ones too
![Screenshot from 2023-11-15 16-41-13.png](/img/user/Vaulted%20Images/Screenshot%20from%202023-11-15%2016-41-13.png)

### 1.2.1 Valid vs Invalid Variable Names
![Var Names Python.png](/img/user/Vaulted%20Images/Var%20Names%20Python.png)

## *1.3 First Real Program*
```Python
# This Program asks my name, says hello, asks my age and does some very rudimentary calculations.  
print("Hello, Nice to meet you. What is your name?")  
print("(Please remember to hit enter after you type your name)")  
name = input()  
print("It feels good to meet you, " + name)  
print("The length of characters in the string for the name provided is:")  
print(len(name))  
print("What is your age? (if you don't mind)")  
age = input()  
print("You will be " + str(int(age) + 1) + " very soon!")  
print("We are reaching the end of my programming.")  
print("Sayonara. Goodbye.")
```
Mistakes I made: Not converting int to string before concatenation with string.
Convert integer to string by using str(int x)
Note, age is treated as string by python, so it is best to convert it to int first, do your expression, and convert the whole result to string to be concatenated with string.

## *1.4 Strings Formatting using Functions*
There are two types of functions in Coding Languages - functions can be either pre-defined or they can be user-defined. We are strictly using pre-defined functions.
We shall be using a simple example of a program asking for the user's name and displaying it.

### 1.4.1 Conventional Method:
Method used most often
```Python
name = input("What is your name? ")
print("hello,", name)
```

### 1.4.2 Alternate Method:
An alternate method some would love to use
```Python
name = input("What is your name?" )
print("hello," + name)
```

### 1.4.3 Formatted Print
Using Formatted String
``` Python
name = input("What is your name? ")
print(f"hello, {name}!") # The 'f' right before the quotes is important.
```

### 1.4.4 Remove Whitespaces and capitalises first letter
```Python
name = input("What is your name? ")
name = name.strip() # Strips whitespaces from the variable 'name'
name = name.capitalize() # Capitalises first letter of first word of 'name'
name = name.title() # Capitalises first letter of each word of 'name'
name = name.strip().title() # Pre-Defined functions can be chained
print(f"hello, {name}!")
```

### 1.4.5 Split the 'name' variable
```Python
name = input("What is your name? ") 
name = name.strip().title()
first, last = name.split(" ") # Splits the name into 2 halves upon spotting space.
print(f"hello, {first}!") # saying hello to first name only.
```

## *1.5 Integers Input and Formatting!* 
Anything that the `input()` function takes is basically treated as a string. Not an integer.
```Python
x = input("Give any value for x, please. x = ") # say x = 1
y = input("Give any value for y, please. y = ") # say y = 2
z = x + y
print(z) # Output is xy instead of x + y i.e., it will output 12 instead of 3
# It is because x and y are treated as "1" and "2" instead of 1 and 2.
# x and y are strings.
```

How to fix this? Solution:
```Python
x = input("Give any value for x, please. x = ") # say x = 1
y = input("Give any value for y, please. y = ") # say y = 2
z = int(x) + int(y)
print(z) # Now output is correct.
# Use print(f"{z:,}") to display 1000 as 1,000 instead (add commas in numbers)
```

Alternate:
```Python
x = float(input("Give any value for x, please. x = "))#converts 2 float b4 saving x.
y = float(input("Give any value for y, please. y = ")) 
print(x + y) # same output as before but also handles floats.
```

## *1.6 User-Defined Functions!*
Colon is used to indicate start of a funtion and indenting is used to tell the interpreter how long the function is and wherever the indent decreases, the function ends.
```Python
def hello(a = "world"): # Interpreter assumes that 'name' is now called 'a'.
	print("hello", a) # If nothing is provided, it will use a = "world"
name = input("What is your name? ")
hello(name) # Function called which takes 'name' as input.
```
Another example which allows Python to use main like other languages (example: C++)
```Python
def main():
	x = int(input("Give any value of x, please. x = "))
	print("x squared is:", square(x)) # x**2 can do same thing.

def square(n) # square is not a pre-defined function but pow (x,2) can be used.
	return n * n

main() # If 'main' is not called, it can't run; Nothing runs without it.
```

## *1.7 If Conditionals! (limited discussion)*
Use if-elif-else instead of if-else statement.
Pythonic way is to just use:
```Python
return True if {statement} else False
```
This condenses 4 lines of if-else statements into 1.
Or we could also use:
```Python
return {statement}
```
Although this works in limited situations only, it works just as well.
I still prefer the first option 90% of the times.

### 1.7.1 Match-Case (Python version of Switch-case)
![Match Case.png](/img/user/Vaulted%20Images/Match%20Case.png)

## *1.8 Loops in Python! (limited discussion)*
For Loops
```Python
for i in [0, 1, 2]: # use range(3) instead of [0, 1, 2] for same output.
	print("meow")
```
While Loops work the same as C++ but use i+=1 instead of i++...
```Python
i = 0
while i < 3
	print("meow")
```
Do-While Loops - run minimum once.

## *1.9 Dictionaries (dict) in Python*
To initialise an empty dict, we can easily use the code snippet `dict_name = {}`
But if we need to initialise it with a specific key-value pair, then we can do the following:
```Python
dict_name = {"key":var1 , "value":var2}
```

Assume we have to get a program to keep track of Hogwarts Students along with their Houses from the Harry Potter series...
Using Dictionaries it is easily achievable:
```Python
students = {
	"Hermione": "Gryffindor",
	"Harry": "Gryffindor",
	"Ron": "Gryffindor",
	"Draco": "Slytherin",
	"Cedric": "Hufflepuff", # new line added
	"Luna": "Ravenclaw", # new line added
}

for student in students:
	print(student, students[student], sep=", ")
# students is the name of the dictionary that is defined.
# student refers to individual key inside students dictionary.
# so students[student] refers to the value of the key named student.
# In C++ code, print (i, students[i]) has the same effect if i is an integer.
# The code prints name of student and the value corresponding to that name i.e., their house.
# sep is used as a command which separates the names and houses by a value assigned to it (which is a comma followed by a space, in this case).
```

## *1.10 List of Dictionaries*
If we were to also want to store not just a student's name and house but also their patronus, the code changes quite a bit. We can use a list of dictionaries where each dictionary is for a specific student.
```Python
students = [
	{"name": "Hermione", "house": "Gryffindor", "patronus": "Otter"},
	{"name": "Harry", "house": "Gryffindor", "patronus": "Stag"},
	{"name": "Ron", "house": "Gryffindor", "patronus": "Jack Russell Terrier"},
	{"name": "Draco", "house": "Slytherin", "patronus": None}
]
for student in students:
	print(student["name"], student["house"], student["patronus"], sep=", ")
# The code above adds a new attribute or column to the table/dictionary
# SO, the student names are no longer just mapped to 1 value, they are mapped to two separate values - namely their house AND their patronus.
# This implementation uses multiple dictionaries in a list and hence the curly brackets become essential.
# The curly brackets define 1 dictionary, whereas the square brackets define a list.
# SO the list of Students have dictionaries of their own.
```
Concetually, the code above represents the image attached herewith: ![Convert-Table-2-Python.png](/img/user/Vaulted%20Images/Convert-Table-2-Python.png)
### 1.10.1 Sorting a List of Dictionaries
Is it possible to sort a specific list of dictionaries? Apparently Yes!
With the same list given above, we can easily implement this with Python.
***==Python allows functions to be passed as arguments to other functions==***. The Function passed as an argument, will run and its returned value will be used in the other function.
```Python
# Add the following to the previous question.
def get_name(student):
	return student["name"] # returns names

def get_house(student):
	return student["house"] # returns houses

for student in sorted(students, key=get_name):  
	print(f"{student['name']} is in {student['house']}")
# change key to get_house to sort according to houses.
```
if functions like get_name and get_house are never going to get called again, use the lamda function (anonymous function) in 

# 2. Exception Handling in Python! (limited discussion)
Exceptions are handled using the try, except, else statements.
Try and Except are like Try and Catch statements from C++ and the Else statement is triggered if there are no exceptions and code is working noprmally.

```Python
# Basic Syntax
try: print("statement 1")
except: ValueError
	print("Value Error")
else: print("statement 2")
```

There are a few kinds of Errors:
1. ***SyntaxError*** (obvious)
2. ***ValueError*** (user entered value of different data type)
3. ***NameError*** (variable not defined)
4. ***TypeError*** (operating on two variables of different data types such as int + str)
5. ***Logical Error*** (when the logic or formulae in your code give no errors yet wrong results)
6. ***IndexError*** (When an index for a specific list exceeds the amount of elements in it)
Exception Handling cannot be used on Logical Errors. They are also the hardest to find.
# 3. All about Libraries in Python! (limited discussion)
Python allows you to share code with others in the form of modules. Check the [Python Documentation](https://www.docs.python.org/3/library) for more.
## 3.1 Random Library/Module
Used for functions which help you pick random numbers in a range, roll a dice or flip a coin (all using Python's version of STL).  If we want to avoid writing `random.choice` or `random.function` again and again, we could just simply write `from random import <function name>` for each function 

```Python
import random

def main():
	flipCoin()
	randomInteger()
	shuffle_cards()

def flipCoin():
	coin = random.choice(["heads","tails"]) # flips a coin and stores its value
	print(coin) # prints the value of coin

def randomInteger():
	integer = random.randint(1, 10) # chooses random integer from given range

def shuffle_cards():
	cards = ["K", "Q", "J", "10", "9", "8", "7", "6", "5", "4", "3", "2", "A" ]
	shuffle = random.shuffle(cards) # shuffles the items in the list named "cards"
	for card in cards
		print(card) # loop is not needed if we want to print only 1 card.
```
## 3.2 Statistics Library/Module
Use for statistical calculations using Python.
```Python
import statistics
mean = statistics.mean([100, 90])
```
## 3.3 APIs in Python using Requests Library &  JSON Library
Allows me to make API requests, but needs to be used in conjuction with another library JSON to read and translate that JSON response to the API request!
```Python
import json
import requests
import sys

if len(sys.argv)!= 2:
	sys.exit()

response = requests.get("https://itunes.apple.com/search?entity=song&limit=1&term=" + sys.argv[1])
print(json.dumps(response.json(), indent = 2))
# response.json gets the big blob of JSON text which is cryptic AF.
# json.dumps coverts json to human comprehendable text
# json.dumps converts response.json to human compatible formt i.e., the song we asked.
# indent = 2 is standard for indenting the words and make them look legible.
```

We can also do this for more than 1 track. Just tweak the code as follows after changing limit in the response URL from 1 to 50.
```Python
import json
import requests
import sys

if len(sys.argv)!= 2:
	sys.exit()

response = requests.get("https://itunes.apple.com/search?entity=song&limit=50&term=" + sys.argv[1]) 
# &limit is changed to 50 now in the URL above.

Obj = response.json()
for result in Obj["results"]
	print(result["trackName"])
# prints out the track name of all 50 songs by the artists (For Artists with names comprising multiple words. Use quotes like "One Direction" or "5 seconds of Summer")
```
## 3.4 CSV Library in Python
It is a Python Library that allows reading CSV by default.
Although there is a function named "reader" it is better if programmers use "DictReader" instead so that we can make our code more bulletproof. 

We have to just add extra header line denoted what the CSV file contains which map with our Python code in the line where we `student.append()` the file along with the names in our CSV

The CSV file:
```CSV
name, home
Harry, "Number Four, Privet Drive"
Ron, The Burrow
Draco, The Malfoy Manor
```

> Note: For any string containing a comma inside it, we need to put the entire string in quotes or inverted commas (example: "hello, there") and DictReader will handle the rest.
> 
> Also note:  even if someone were to flip the order of the columns in the CSV (writing it in home, name format instead of name, home) given that they are consistent in flipping each and every value... the code will not break thanks to DictReader!

The Python Code:
```Python
import csv

students = []

with open("students.csv") as file:
	reader: csv.DictReader(file):
	for row in reader:
		students.append({"name": row["name"], "home": row["home"]})
		# we can also use students.append(row) since this is in a loop.

for student in sorted(students, key=lambda student: student["name"]):
	print(f"{student:["name"]} is from {student:["home"]}")
```
 if we wish to add the hogwarts house as well in this csv, we just append the code to include `students.append({... same code.... "house": row["house"]})` and then make a small change to the CSV i.e., add the new field we want to reflect.
```CSV
name, home, house
Harry, "Number Four, Privet Drive", Gryffindor
Ron, The Burrow, Gryffindor
Draco, The Malfoy Manor, Slytherin
```

To write to a CSV file using the csv library:
```Python
import csv

name = input("What is your name? ")
home = input("Where do you live? ")

with open("students.csv", "a")as file:
	writer = csv.DictWriter(file, fieldnames=["name","home"])
	writer.writerow({"home": home, "name": name})
```
## 3.5 Pillow Library (PIL) in Python
Allows to navigate through image files & perform operations on image files.
Documentation for Pilliow is available [here](https://pillow.readthedocs.io)

Pillow Library can also allow creation of GIFs by flipping through 2 or more images fast enough to give the illusion of animation.

```Python
import sys

from PIL import Image # According to documentation, PIL is correct, pil is not.

images = [] # Creates an empty list

for arg in sys.argv:
	image = Image.open(arg)
	images.append(image)

images[0].save{
	"costumes.gif" save_all=True, append_images=[images[1]], duration=200, loop=0
}
# the last line refers to the image indexed at 0 being saved a gif
# we append image indexed 1 to the gif to-be-saved
# make them shuffle very 200 ms and loop them forever
```


# 4. Unit Tests in Python
A Unit Test is the Pythonic Way of testing each unit of our python code.
A popular choice to do this is ***pytest***. Dr. Malan prefers this third-party library due to simplicity over others.
```Python
from file_to_test import function_to_test

def testing_function():
	# placeholder code

```

And then, in the terminal use the following command:
```bash
pytest testing.py
```
notice NOT to run `python3 testing.py` instead.

# 5. Data Structures in Python!
A Section dedicated to all the Data Structures Possible in Python.
## 5.1 Lists in Python
A list is depicted using a name for the list and square brackets such as: `list_name = []` which initialises an empty list which can be appended using `list_name.append(data)` .

In-built List functions in Python:
- Append List: `list_name.append(data)`
- Sort List: `sorted(list_name)`


Note that we can also pass input strings inside the backets to append the input of the user!
In a loop, passing the code argument: `list_name.append(input("What is your input? "))` is one of the ways of doing it. Although it can be broken into two lines with a variable storing the input and parsing it the append function.

# 6. Input/Output to other files using Python

## 6.1 Write to & Read from a text file (.txt)
Lists stored in the program are stored in the Computer's RAM. Which means that all of the lists and their contents are lost as soon as the program exits. Best is to store data in a file!

Easily done by the following code:
```Python
name = input("what's your name? ") # Stores an input.

with open("names.txt" "w") as file: # Defines file, the intention to write to it.
	file.write(name) # Writes variable in a file instead of a loop to keep it longer.
# file.close() is need to close the file if 'with' is not used!
# 'with' statement automates the file closing process.
```
To avoid overwriting the old file and losing data, use `file = open("names.txt" "a")` where the letter `a` stands for append. However to add a line ending after each input, change the line 4 of the above code to: `file.write(f"{name}\n")`

To read the file, use:
```Python
with open("names.txt" "r") as file: # defines file, the intention to read it.
	for line in file:
		print("hello," , line.rstrip()) # say hello to all the names in names.txt
# rstrip removes the \n added in the appending process.
```

## 6.2 Write to & Read from a .csv file
Assume that there exists a .csv file you need to retreive data from and display it on the terminal. It is very easily done like this:
``` Python
with open("file.csv") as file # no need to write "r" since it is default beahviour.
	for line in file:
		row = line.rstrip().split(",") # Removes \n and splits at comma (,)
		# now we can print it however we want
		# assuming the file is carrying students & their Hogwarts Houses
		print(f"{row[0]} is in {row[1]}") # Prints "Harry is in Gryffindor" 
```

Now, if one has a name for the variables in `row[0]` and `row[1]`, then one can define the row as `var1, var2 = line.rstrip().split(",")` and then create an empty dictionary to store both variables as key-value pair. {see [[Python#*1.9 Dictionaries (dict) in Python*\|Python#*1.9 Dictionaries (dict) in Python*]]}

Easier way is to use a library for CSVs: like the [[Python#3.4 CSV Library in Python\|#3.4 CSV Library in Python]]

# Footnotes
It is impportant to note that a lot of written material and in some cases, even the code is taken directly from the Website where the book is hosted as Open Source i.e., [Automate the Boring Stuff Website](https://automatetheboringstuff.com/#toc) or the YouTube upload of the Harvard CS50 Course by freecodecamp.org



