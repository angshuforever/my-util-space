# Python Cheat Sheet - Part 1: Basics and Data Types

## Table of Contents
1. [Python Basics](#python-basics)
2. [Variables and Data Types](#variables-and-data-types)
3. [Operators](#operators)
4. [Strings](#strings)
5. [Lists](#lists)
6. [Tuples](#tuples)
7. [Dictionaries](#dictionaries)
8. [Sets](#sets)

## Python Basics

### Comments
```python
# This is a single-line comment

"""
This is a
multi-line comment
"""
```

### Print Statement
```python
print("Hello, World!")
print("Value:", 42)
print("Multiple", "Arguments", sep="-")
```

### Input
```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))
```

### Indentation
Python uses indentation to define code blocks:
```python
if True:
    print("Indented code")
    if True:
        print("Nested indentation")
```

## Variables and Data Types

### Variable Assignment
```python
x = 5
y = "John"
z, w = 3.14, True
```

### Data Types
```python
# Integer
a = 10

# Float
b = 3.14

# String
c = "Hello"

# Boolean
d = True

# List
e = [1, 2, 3]

# Tuple
f = (4, 5, 6)

# Dictionary
g = {"name": "John", "age": 30}

# Set
h = {1, 2, 3}
```

### Type Conversion
```python
# String to Integer
x = int("10")

# Integer to String
y = str(20)

# String to Float
z = float("3.14")
```

## Operators

### Arithmetic Operators
```python
a = 10
b = 3

print(a + b)  # Addition
print(a - b)  # Subtraction
print(a * b)  # Multiplication
print(a / b)  # Division
print(a % b)  # Modulus
print(a ** b) # Exponentiation
print(a // b) # Floor division
```

### Comparison Operators
```python
x = 5
y = 10

print(x == y) # Equal to
print(x != y) # Not equal to
print(x > y)  # Greater than
print(x < y)  # Less than
print(x >= y) # Greater than or equal to
print(x <= y) # Less than or equal to
```

### Logical Operators
```python
a = True
b = False

print(a and b) # Logical AND
print(a or b)  # Logical OR
print(not a)   # Logical NOT
```

## Strings

### String Operations
```python
s = "Hello, World!"

# Length
print(len(s))

# Indexing
print(s[0])  # First character
print(s[-1]) # Last character

# Slicing
print(s[0:5])   # Characters from index 0 to 4
print(s[7:])    # Characters from index 7 to the end
print(s[:5])    # Characters from the beginning to index 4
print(s[::2])   # Every second character
print(s[::-1])  # Reverse the string

# Concatenation
s1 = "Hello"
s2 = "World"
print(s1 + " " + s2)

# Repetition
print("Ha" * 3)
```

### String Methods
```python
s = "hello, world!"

print(s.upper())        # Convert to uppercase
print(s.lower())        # Convert to lowercase
print(s.capitalize())   # Capitalize first letter
print(s.title())        # Capitalize first letter of each word
print(s.strip())        # Remove leading and trailing whitespace
print(s.replace("o", "0")) # Replace substring
print(s.split(","))     # Split string into list
```

## Lists

### List Operations
```python
fruits = ["apple", "banana", "cherry"]

# Length
print(len(fruits))

# Indexing
print(fruits[0])  # First item
print(fruits[-1]) # Last item

# Slicing
print(fruits[1:])  # From second item to the end

# Changing items
fruits[1] = "blackcurrant"

# Adding items
fruits.append("orange")
fruits.insert(1, "mango")

# Removing items
fruits.remove("cherry")
last_fruit = fruits.pop()

# Sorting
fruits.sort()
fruits.sort(reverse=True)

# Reversing
fruits.reverse()

# Copying
new_fruits = fruits.copy()
```

### List Comprehensions
```python
# Create a list of squares
squares = [x**2 for x in range(10)]

# Create a list of even numbers
evens = [x for x in range(20) if x % 2 == 0]
```

## Tuples

### Tuple Operations
```python
coordinates = (4, 5)

# Length
print(len(coordinates))

# Indexing
print(coordinates[0])  # First item
print(coordinates[-1]) # Last item

# Unpacking
x, y = coordinates

# Concatenation
more_coords = coordinates + (6, 7)

# Repetition
repeated = coordinates * 3
```

## Dictionaries

### Dictionary Operations
```python
person = {
    "name": "John",
    "age": 30,
    "city": "New York"
}

# Accessing items
print(person["name"])
print(person.get("age"))

# Changing items
person["age"] = 31

# Adding items
person["gender"] = "Male"

# Removing items
del person["city"]
removed_item = person.pop("gender")

# Keys and Values
print(person.keys())
print(person.values())

# Items
for key, value in person.items():
    print(f"{key}: {value}")
```

## Sets

### Set Operations
```python
fruits = {"apple", "banana", "cherry"}

# Adding items
fruits.add("orange")

# Updating with multiple items
fruits.update(["mango", "grapes"])

# Removing items
fruits.remove("banana")  # Raises an error if item doesn't exist
fruits.discard("kiwi")   # Doesn't raise an error if item doesn't exist

# Set operations
set1 = {1, 2, 3}
set2 = {3, 4, 5}
print(set1.union(set2))        # Union
print(set1.intersection(set2)) # Intersection
print(set1.difference(set2))   # Difference
```

This concludes Part 1 of the Python Cheat Sheet, covering Python basics and data types. Parts 2 and 3 will cover more advanced topics.

# Python Cheat Sheet - Part 2: Control Flow, Functions, and Modules

## Table of Contents
1. [Control Flow](#control-flow)
2. [Functions](#functions)
3. [Lambda Functions](#lambda-functions)
4. [List Comprehensions (Advanced)](#list-comprehensions-advanced)
5. [Exceptions](#exceptions)
6. [File Handling](#file-handling)
7. [Modules and Packages](#modules-and-packages)

## Control Flow

### If Statements
```python
x = 10

if x > 5:
    print("x is greater than 5")
elif x == 5:
    print("x is equal to 5")
else:
    print("x is less than 5")

# Ternary operator
result = "Even" if x % 2 == 0 else "Odd"
```

### For Loops
```python
# Iterating over a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# Iterating over a range
for i in range(5):
    print(i)

# Enumerate
for index, fruit in enumerate(fruits):
    print(f"{index}: {fruit}")

# Iterating over a dictionary
person = {"name": "John", "age": 30}
for key, value in person.items():
    print(f"{key}: {value}")
```

### While Loops
```python
count = 0
while count < 5:
    print(count)
    count += 1

# Break and Continue
while True:
    if count >= 10:
        break
    if count % 2 == 0:
        count += 1
        continue
    print(count)
    count += 1
```

## Functions

### Basic Function
```python
def greet(name):
    return f"Hello, {name}!"

print(greet("Alice"))
```

### Default Arguments
```python
def greet(name, greeting="Hello"):
    return f"{greeting}, {name}!"

print(greet("Bob"))
print(greet("Charlie", "Hi"))
```

### Variable-length Arguments
```python
# *args
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3, 4))

# **kwargs
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=30, city="New York")
```

### Docstrings
```python
def multiply(a, b):
    """
    Multiply two numbers and return the result.

    Args:
    a (int): The first number
    b (int): The second number

    Returns:
    int: The product of a and b
    """
    return a * b

# Accessing the docstring
print(multiply.__doc__)
```

## Lambda Functions

```python
# Basic lambda function
square = lambda x: x**2
print(square(5))

# With filter()
numbers = [1, 2, 3, 4, 5, 6]
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))

# With map()
squared_numbers = list(map(lambda x: x**2, numbers))
```

## List Comprehensions (Advanced)

```python
# Nested list comprehension
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
flattened = [num for row in matrix for num in row]

# Conditional list comprehension
even_squares = [x**2 for x in range(10) if x % 2 == 0]

# Set comprehension
unique_lengths = {len(word) for word in ["hello", "world", "python"]}

# Dictionary comprehension
squared_dict = {x: x**2 for x in range(5)}
```

## Exceptions

### Basic Exception Handling
```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero!")
except Exception as e:
    print(f"An error occurred: {e}")
else:
    print("Division successful")
finally:
    print("This always executes")
```

### Raising Exceptions
```python
def validate_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative")
    return age

try:
    validate_age(-5)
except ValueError as e:
    print(e)
```

## File Handling

### Reading from a File
```python
# Reading entire file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)

# Reading line by line
with open("example.txt", "r") as file:
    for line in file:
        print(line.strip())

# Reading into a list
with open("example.txt", "r") as file:
    lines = file.readlines()
```

### Writing to a File
```python
# Writing to a file
with open("output.txt", "w") as file:
    file.write("Hello, World!")

# Appending to a file
with open("output.txt", "a") as file:
    file.write("\nAppended line")
```

## Modules and Packages

### Importing Modules
```python
# Importing an entire module
import math
print(math.pi)

# Importing specific functions
from math import sqrt, sin
print(sqrt(16))

# Importing with an alias
import matplotlib.pyplot as plt

# Importing all functions (not recommended)
from math import *
```

### Creating a Module
```python
# In mymodule.py
def greet(name):
    return f"Hello, {name}!"

PI = 3.14159

# In main script
import mymodule
print(mymodule.greet("Alice"))
print(mymodule.PI)
```

### Working with Packages
```python
# Assuming the following structure:
# mypackage/
#     __init__.py
#     module1.py
#     module2.py

# Importing from a package
from mypackage import module1
from mypackage.module2 import function2

# Using __init__.py to define package behavior
# In mypackage/__init__.py
from .module1 import function1
from .module2 import function2
```

This concludes Part 2 of the Python Cheat Sheet, covering control flow, functions, and modules. Part 3 will cover more advanced topics and standard library features.

# Python Cheat Sheet - Part 3: Advanced Topics and Standard Library

## Table of Contents
1. [Object-Oriented Programming](#object-oriented-programming)
2. [Decorators](#decorators)
3. [Generators](#generators)
4. [Context Managers](#context-managers)
5. [Regular Expressions](#regular-expressions)
6. [Date and Time](#date-and-time)
7. [JSON Handling](#json-handling)
8. [Working with CSV Files](#working-with-csv-files)
9. [Working with SQLite Database](#working-with-sqlite-database)
10. [Multithreading and Multiprocessing](#multithreading-and-multiprocessing)

## Object-Oriented Programming

### Creating a Class
```python
class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def bark(self):
        return f"{self.name} says Woof!"

dog = Dog("Buddy", 5)
print(dog.bark())
```

### Inheritance
```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        pass

class Cat(Animal):
    def speak(self):
        return f"{self.name} says Meow!"

cat = Cat("Whiskers")
print(cat.speak())
```

### Static Methods and Class Methods
```python
class MathOperations:
    @staticmethod
    def add(x, y):
        return x + y
    
    @classmethod
    def multiply(cls, x, y):
        return x * y

print(MathOperations.add(5, 3))
print(MathOperations.multiply(4, 2))
```

## Decorators

### Basic Decorator
```python
def uppercase_decorator(function):
    def wrapper():
        result = function()
        return result.upper()
    return wrapper

@uppercase_decorator
def greet():
    return "hello, world!"

print(greet())
```

### Decorator with Arguments
```python
def repeat(times):
    def decorator(function):
        def wrapper(*args, **kwargs):
            for _ in range(times):
                result = function(*args, **kwargs)
            return result
        return wrapper
    return decorator

@repeat(3)
def say_hello(name):
    print(f"Hello, {name}!")

say_hello("Alice")
```

## Generators

### Basic Generator
```python
def countdown(n):
    while n > 0:
        yield n
        n -= 1

for number in countdown(5):
    print(number)
```

### Generator Expression
```python
squares = (x**2 for x in range(10))
print(list(squares))
```

## Context Managers

### Using with Statement
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

### Creating a Context Manager
```python
from contextlib import contextmanager

@contextmanager
def custom_open(filename):
    file = open(filename, "r")
    try:
        yield file
    finally:
        file.close()

with custom_open("example.txt") as file:
    content = file.read()
    print(content)
```

## Regular Expressions

```python
import re

text = "The quick brown fox jumps over the lazy dog"

# Search for a pattern
match = re.search(r"quick.*fox", text)
if match:
    print("Pattern found:", match.group())

# Find all occurrences
matches = re.findall(r"\b\w{4}\b", text)
print("Four-letter words:", matches)

# Replace pattern
new_text = re.sub(r"lazy", "energetic", text)
print("Modified text:", new_text)
```

## Date and Time

```python
from datetime import datetime, timedelta

# Current date and time
now = datetime.now()
print("Current date and time:", now)

# Formatting date
formatted_date = now.strftime("%Y-%m-%d %H:%M:%S")
print("Formatted date:", formatted_date)

# Parsing string to date
date_string = "2023-06-15 14:30:00"
parsed_date = datetime.strptime(date_string, "%Y-%m-%d %H:%M:%S")
print("Parsed date:", parsed_date)

# Date arithmetic
future_date = now + timedelta(days=7)
print("Date after a week:", future_date)
```

## JSON Handling

```python
import json

# Python object to JSON string
data = {
    "name": "John",
    "age": 30,
    "city": "New York"
}
json_string = json.dumps(data, indent=4)
print("JSON string:", json_string)

# JSON string to Python object
parsed_data = json.loads(json_string)
print("Parsed data:", parsed_data)

# Writing JSON to a file
with open("data.json", "w") as file:
    json.dump(data, file, indent=4)

# Reading JSON from a file
with open("data.json", "r") as file:
    loaded_data = json.load(file)
    print("Loaded data:", loaded_data)
```

## Working with CSV Files

```python
import csv

# Writing to a CSV file
data = [
    ["Name", "Age", "City"],
    ["John", 30, "New York"],
    ["Alice", 25, "Los Angeles"],
    ["Bob", 35, "Chicago"]
]

with open("data.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(data)

# Reading from a CSV file
with open("data.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)

# Using DictReader and DictWriter
with open("data.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(row)

data = [
    {"Name": "John", "Age": 30, "City": "New York"},
    {"Name": "Alice", "Age": 25, "City": "Los Angeles"}
]

with open("dict_data.csv", "w", newline="") as file:
    fieldnames = ["Name", "Age", "City"]
    writer = csv.DictWriter(file, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerows(data)
```

## Working with SQLite Database

```python
import sqlite3

# Connect to database (creates if not exists)
conn = sqlite3.connect("example.db")
cursor = conn.cursor()

# Create table
cursor.execute("""
    CREATE TABLE IF NOT EXISTS users (
        id INTEGER PRIMARY KEY,
        name TEXT NOT NULL,
        age INTEGER
    )
""")

# Insert data
cursor.execute("INSERT INTO users (name, age) VALUES (?, ?)", ("John", 30))
conn.commit()

# Query data
cursor.execute("SELECT * FROM users")
rows = cursor.fetchall()
for row in rows:
    print(row)

# Close connection
conn.close()
```

## Multithreading and Multiprocessing

### Threading
```python
import threading
import time

def worker(name):
    print(f"Worker {name} starting")
    time.sleep(2)
    print(f"Worker {name} finished")

threads = []
for i in range(5):
    t = threading.Thread(target=worker, args=(i,))
    threads.append(t)
    t.start()

for t in threads:
    t.join()

print("All workers finished")
```

### Multiprocessing
```python
import multiprocessing
import time

def worker(name):
    print(f"Worker {name} starting")
    time.sleep(2)
    print(f"Worker {name} finished")

if __name__ == "__main__":
    processes = []
    for i in range(5):
        p = multiprocessing.Process(target=worker, args=(i,))
        processes.append(p)
        p.start()

    for p in processes:
        p.join()

    print("All workers finished")
```

This concludes the third and final part of the Python Cheat Sheet, covering advanced topics and standard library features.

