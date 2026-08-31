Absolutely. I’ll keep this as a **short, practical guide for someone who already knows how to program**, rather than explaining programming concepts from scratch.

# Python Tutorial by NMichael
## Table of contents
1. **The Basics** — indentation, program structure, comments
2. **Variables and Data Types** — variables, strings, numbers, booleans, `None`
3. **Operators and Expressions** — arithmetic, comparison, logical operators
4. **Control Flow** — `if`, `elif`, `else`, `match`
5. **Loops** — `for`, `while`, `break`, `continue`
6. **Lists and Tuples** — creating, accessing and modifying collections
7. **Dictionaries and Sets** — key/value data and unique collections
8. **Functions** — parameters, return values, defaults, scope
9. **Strings** — formatting, slicing and useful string methods
10. **Exceptions** — `try`, `except`, `finally`, `raise`
11. **Modules and Packages** — imports, creating modules and package structure
12. **Working with Files** — reading, writing and working with paths
13. **Classes and Objects** — Python's approach to object-oriented programming
14. **Inheritance and Polymorphism** — extending classes and using common interfaces
15. **List Comprehensions** — concise Python collection processing
16. **Iterators and Generators** — `iter`, `next`, `yield`
17. **Decorators** — modifying function behaviour
18. **Type Hints** — `str`, `int`, `list`, `Optional`, etc.
19. **Virtual Environments and pip** — managing Python projects and dependencies
20. **Testing** — introducing `pytest` and unit testing
21. **Working with JSON** — exchanging structured data
22. **Calling REST APIs** — using Python with web services
23. **A Practical Python Program** — putting the concepts together

## 1. The Basics

### A brief history

Python was created by **Guido van Rossum** and first released in **1991**.

### Python indentation

Python uses **indentation to define blocks of code**, rather than braces `{ }`.

The standard convention is **4 spaces** for each level of indentation.

```python
if age >= 18:
    print("Adult")
    print("Can vote")
```

The two `print()` statements belong to the `if` block because they are indented by four spaces.

### Structure of a Python program

A Python program is simply a collection of statements, functions, classes, and other definitions. A typical tutorial program can be organised like this:

```python
# Python Tutorial by NMichael

import math

def main():
    print("Hello, Python")

if __name__ == "__main__":
    main()
```

The important structural elements are:

* `#` — comment
* `import` — imports a module
* `def` — defines a function
* Indentation — defines code blocks
* `if __name__ == "__main__":` — runs code when the file is executed directly

Here is Chapter 2, keeping the same **short, code-oriented style** and assuming the reader already understands basic programming concepts.

---

## 2. Variables and Data Types

Python variables are created when a value is assigned to a name. You do not need to declare the variable's type.

```python
name = "Nico"
age = 70
height = 1.75
active = True
```

The main basic data types are:

* `str` — text
* `int` — integer
* `float` — decimal number
* `bool` — `True` or `False`
* `None` — represents no value

Python is **dynamically typed**, so a variable can be assigned a value of a different type later:

```python
value = 10
value = "Hello"
```

Use `type()` when you need to determine a value's type:

```python
print(type(value))
```

Python variables are names bound to objects rather than fixed type declarations. ([Python documentation][1])
---
# Python Tutorial by NMichael

## 3. Operators and Expressions

Python provides operators for arithmetic, comparisons and logical operations.

### Arithmetic operators

```python
a = 10
b = 3

print(a + b)   # addition
print(a - b)   # subtraction
print(a * b)   # multiplication
print(a / b)   # division
print(a // b)  # integer division
print(a % b)   # remainder
print(a ** b)  # exponentiation
```

### Comparison operators

Comparison operators return `True` or `False`.

```python
age = 20

print(age >= 18)
print(age == 20)
print(age != 10)
```

Python also allows comparisons to be chained:

```python
age = 25

if 18 <= age < 65:
    print("Working age")
```

### Logical operators

The logical operators are `and`, `or` and `not`.

```python
age = 25
has_license = True

if age >= 18 and has_license:
    print("Can drive")
```

### Operator precedence

Python follows a defined order when evaluating expressions. Parentheses can be used to make the intended order explicit.

```python
result = (10 + 5) * 2
```

---


## 4. Control Flow

Control flow determines which parts of a program are executed and when.

### `if`, `elif` and `else`

Use `if` to execute code when a condition is true. `elif` provides additional conditions, and `else` handles everything not matched by the preceding conditions.

```python
age = 25

if age < 18:
    print("Minor")
elif age < 65:
    print("Adult")
else:
    print("Senior")
```

Python executes **only the first matching branch**. Both `elif` and `else` are optional. ([Python documentation][1])

### `match`

Python also provides `match` for pattern matching when several possible values or patterns need to be handled.

```python
command = "start"

match command:
    case "start":
        print("Starting")
    case "stop":
        print("Stopping")
    case _:
        print("Unknown command")
```

The `_` pattern acts as a default case. ([Python documentation][1])

---


## 5. Loops

Loops are used to execute a block of code repeatedly.

### `for` loop

A `for` loop iterates over the items in an iterable such as a list, string or `range`.

```python
for number in range(5):
    print(number)
```

This prints the numbers `0` through `4`. `range(5)` does not include `5`. ([Python documentation][1])

A `for` loop can iterate directly over a collection:

```python
names = ["John", "Mary", "Peter"]

for name in names:
    print(name)
```

### `while` loop

A `while` loop continues while its condition is `True`.

```python
count = 0

while count < 5:
    print(count)
    count += 1
```

### `break` and `continue`

`break` exits the current loop. `continue` skips the remainder of the current iteration and starts the next one. ([Python documentation][1])

```python
for number in range(10):
    if number == 5:
        break
    print(number)
```

---



## 6. Lists and Tuples

Lists and tuples are used to store multiple values in a single object.

### Lists

A list is **ordered and mutable**, meaning its contents can be changed.

```python
names = ["John", "Mary", "Peter"]

names.append("Susan")
names[0] = "James"

print(names)
```

List elements are accessed using a zero-based index:

```python
print(names[0])
print(names[-1])
```

A list can contain values of different types, although lists containing similar types are common. ([Python documentation][1])

### Tuples

A tuple is **ordered but immutable**, meaning its elements cannot be changed after the tuple is created.

```python
person = ("Nico", 70, "South Africa")

print(person[0])
```

Tuples are often useful for representing a fixed group of related values. ([Python documentation][1])

A tuple can also be unpacked directly into variables:

```python
name, age, country = person
```

### Comparison to Java
* **Python `list`** ≈ **Java `ArrayList`**

  * Ordered
  * Mutable
  * Can grow/shrink
  * Python can mix types; Java normally uses one generic type.

* **Python `tuple`** ≈ **Java `List` that is unmodifiable**, but there is no exact Java equivalent.

  * Ordered
  * Immutable
  * Fixed after creation

Example:

```python
names = ["John", "Mary"]       # Python list
person = ("Nico", 70)          # Python tuple
```

Rough Java equivalents:

```java
List<String> names = new ArrayList<>();
List<Object> person = List.of("Nico", 70);
```

**Key difference:** Python has a built-in immutable sequence type (`tuple`); Java does not have a direct tuple equivalent.


---


## 7. Dictionaries and Sets

### Dictionaries

A **dictionary** stores data as **key/value pairs**. Each key is unique and is used to retrieve its associated value. ([Python documentation][1])

```python
person = {
    "name": "John",
    "age": 30,
    "city": "London"
}

print(person["name"])
```

Output:

```text
John
```

Add or change a value:

```python
person["age"] = 31
person["email"] = "john@example.com"
```

Useful operations:

```python
person.get("name")       # retrieve a value
"name" in person         # test whether a key exists
del person["age"]        # remove a key/value pair
```

`get()` is useful when a key might not exist because it returns `None` instead of raising a `KeyError`. ([Python documentation][1])

### Sets

A **set** is an unordered collection containing **unique values**. It is useful when duplicates are not wanted or when testing membership. ([Python documentation][1])

```python
numbers = {1, 2, 3, 2, 1}

print(numbers)
```

The result contains only:

```text
{1, 2, 3}
```

Values can be added and removed:

```python
numbers.add(4)
numbers.remove(2)
```

An empty set must be created with `set()`:

```python
numbers = set()
```

`{}` creates an empty dictionary, not an empty set. ([Python documentation][1])

Sets also support mathematical operations such as union and intersection:

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)    # union
print(a & b)    # intersection
```

Dictionaries and sets are both built-in Python data types. ([Python documentation][2])

### Java Comparison of Dictionaries and Sets

If you know Java, Python **dictionaries** are similar to Java's `HashMap`, storing key/value pairs. Python **sets** are similar to Java's `HashSet`, storing unique values without key/value pairs. ([download.java.net][1])

```text
Python dict  →  Java HashMap
Python set   →  Java HashSet
```

The main difference is syntax: Python provides dictionaries and sets as built-in types, while Java uses classes from the Collections Framework.

---
=====================
# Python Tutorial by NMichael

## 8. Functions

Functions let you group reusable code into a named block. They are defined with `def` and execute when called. ([Python documentation][1])

### Defining a Function

```python
def greet(name):
    print("Hello", name)

greet("Nico")
```

`name` is a **parameter** and `"Nico"` is an **argument**.

### Return Values

Use `return` to send a value back to the caller.

```python
def add(a, b):
    return a + b

result = add(10, 20)
```

### Default Parameters

Parameters can have default values.

```python
def greet(name, greeting="Hello"):
    print(greeting, name)

greet("Nico")
greet("Nico", "Welcome")
```

### Scope

Variables created inside a function normally have **local scope**. Variables defined outside functions are in the surrounding/global scope. ([Python documentation][2])

```python
message = "Hello"

def show():
    local_message = "World"
    print(message, local_message)
```

Keep functions small and focused on a single task. This makes code easier to reuse, test and maintain.

---

## 9. Strings

A **string** is a sequence of characters. Python strings are created using single or double quotes.

```python
name = "Nico"
message = 'Hello, ' + name
```

### String Formatting

**f-strings** provide a concise way to insert values into a string.

```python
name = "Nico"
age = 70

print(f"{name} is {age} years old")
```

Expressions can also be used inside `{}`.

```python
print(f"Total: {10 * 5}")
```

### Slicing

Strings can be indexed and sliced. Indexing starts at `0`.

```python
text = "Python"

print(text[0])       # P
print(text[1:4])     # yth
print(text[:2])      # Py
print(text[-1])      # n
```

The slice `start:end` includes `start` but excludes `end`.

### Useful String Methods

Strings provide methods for common operations such as searching, replacing, splitting and changing case. ([Python documentation](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str))

```python
text = "  Hello Python  "

print(text.strip())          # Hello Python
print(text.upper())          # HELLO PYTHON
print(text.lower())          # hello python
print(text.replace("Python", "World"))
print("Python" in text)      # True
```

`split()` converts a string into a list, while `join()` combines strings into one string.

```python
words = "one two three".split()
text = ", ".join(words)
```

Python strings are **immutable**: string operations create a new string rather than changing the original string. ([Python documentation](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str))

### Python vs Java Strings

Python and Java strings are very similar: both are **immutable**, support zero-based indexing, slicing/substrings, searching and common text operations. ([Python documentation][1])

The main differences are:

* **Python:** `str` is a built-in type; there is no separate `char` type.
* **Java:** `String` is a class, and Java also has the primitive `char` type.
* **Python:** slicing is built into the syntax: `text[1:4]`.
* **Java:** substring uses a method: `text.substring(1, 4)`.
* **Python:** f-strings provide convenient formatting: `f"Hello {name}"`.
* **Java:** commonly uses `String.format()` or formatted string methods.

For a Java programmer, Python strings should feel very familiar, with **simpler syntax for many common operations**. ([Google for Developers][2])


---

## 10. Exceptions

Exceptions handle errors that occur while a program is running. Python uses `try`, `except`, `finally`, and `raise`. ([Python documentation][1])

### Handling Exceptions

Put code that may fail in a `try` block and handle the error in `except`.

```python
try:
    value = int(input("Enter a number: "))
except ValueError:
    print("Invalid number")
```

Multiple exception types can be handled separately.

```python
try:
    result = 10 / value
except ValueError:
    print("Not a number")
except ZeroDivisionError:
    print("Cannot divide by zero")
```

### finally

`finally` runs when the `try` statement is leaving, whether an exception occurred or not. It is commonly used for cleanup. ([Python documentation][1])

```python
try:
    process()
finally:
    cleanup()
```

### raise

Use `raise` when your program needs to explicitly generate an exception.

```python
if age < 0:
    raise ValueError("Age cannot be negative")
```

### Java Comparison to Exceptions

Python uses `try` / `except` / `finally`, while Java uses `try` / `catch` / `finally`. Both languages use `raise`-style mechanisms to explicitly throw exceptions, but Java uses the keyword `throw`. ([docs.oracle.com][2])

```text
Python:  try → except → finally
Java:    try → catch  → finally
```

A major difference is that Java has **checked exceptions** and requires certain exceptions to be caught or declared with `throws`; Python does not have this checked-exception requirement. ([docs.oracle.com][3])

---

## 11. Modules and Packages

A **module** is a Python file containing code that can be imported and reused. A **package** is a way of organising related modules into a hierarchy. ([Python documentation][1])

### Importing Modules

```python
import math

print(math.sqrt(25))
```

You can import specific items:

```python
from math import sqrt

print(sqrt(25))
```

### Creating a Module

Suppose `calculator.py` contains:

```python
def add(a, b):
    return a + b
```

Another program can use it:

```python
from calculator import add

print(add(10, 20))
```

### Packages

A simple package might look like:

```text
myapp/
    main.py
    utils/
        __init__.py
        calculator.py
```

The module can then be imported with:

```python
from utils.calculator import add
```

Packages allow larger applications to organise related modules into separate directories. ([Python documentation][2])

### Java Comparison to Packages

Python **modules** are roughly similar to Java source files, while Python **packages** are similar to Java packages. Both languages use `import` to make code from elsewhere available. ([docs.oracle.com][3])

---

## 12. Working with Files

Python provides `open()` for reading and writing files. Use `with` so the file is automatically closed when the block finishes. ([Python documentation](https://docs.python.org/3/library/functions.html#open))

### Reading and Writing

```python
with open("data.txt", "r") as file:
    text = file.read()

with open("output.txt", "w") as file:
    file.write("Hello Python")
```

Common modes include:

```text
r   read
w   write, replacing existing content
a   append
rb  read binary
wb  write binary
```

### Paths

`pathlib.Path` provides an object-oriented way to work with filesystem paths and is generally preferable to manually constructing path strings. ([Python documentation](https://docs.python.org/3.14/library/pathlib.html))

```python
from pathlib import Path

path = Path("data") / "file.txt"

if path.exists():
    text = path.read_text()
```

`Path` also provides methods such as `mkdir()`, `read_text()`, `write_text()` and `iterdir()`. ([Python documentation](https://docs.python.org/3.14/library/pathlib.html))

### Java Comparison to Files

Python `pathlib.Path` is similar to Java's `java.nio.file.Path`, while Python's file operations correspond broadly to Java's `Files` API. Both provide platform-independent filesystem operations. ([Java documentation](https://docs.oracle.com/en/java/javase/26/docs/api/java.base/java/nio/file/Path.html))

---

## 13. Classes and Objects

A **class** defines the data and behaviour of a type of object. An **object** is an instance of a class. Python uses `class` to define classes and `__init__()` to initialise objects. ([Python documentation][1])

### Defining a Class

```python
class Person:
    def __init__(self, name):
        self.name = name

    def greet(self):
        return f"Hello {self.name}"

person = Person("Nico")
print(person.greet())
```

`self` refers to the current object. Instance attributes such as `self.name` belong to that object.

Python does not require a separate declaration for fields or a constructor keyword. `__init__()` is called automatically when an object is created.

### Java Comparison to Classes and Objects

Python classes are conceptually similar to Java classes, containing **state and methods**. Python creates an object by calling the class directly:

```text
Python:  person = Person("Nico")
Java:    Person person = new Person("Nico");
```

Python requires less syntax and does not require explicit type declarations for attributes. ([Oracle Documentation][2])
---

## 14. Iterators and Generators

An **iterator** produces values one at a time. `iter()` creates an iterator and `next()` retrieves the next value. A `for` loop uses this mechanism automatically. ([Python documentation][1])

```python
numbers = iter([10, 20, 30])

print(next(numbers))  # 10
print(next(numbers))  # 20
```

When there are no more values, `next()` raises `StopIteration`.

### Generators

A **generator** is a simple way to create an iterator. A function containing `yield` becomes a generator function. Each `yield` produces a value and suspends the function until the next value is requested. ([Python documentation][2])

```python
def numbers():
    yield 1
    yield 2
    yield 3

for number in numbers():
    print(number)
```

Generators are useful when values can be produced one at a time rather than creating the complete collection in memory.

### Java Comparison to Iterators and Generators

Python iterators are similar to Java's `Iterator`, with `next()` corresponding roughly to Java's `next()`. Python generators provide a concise language feature for creating iterators; Java has no direct equivalent to Python's `yield`. ([Python documentation][2])

---

## Bibliography

1. Python Software Foundation. *The Python Tutorial — Python 3.14*. [Python documentation](https://docs.python.org/3/tutorial/)
2. Python Software Foundation. *The Python Standard Library — Python 3.14*. [Python documentation](https://docs.python.org/3/library/)
3. Python Software Foundation. *The Python Language Reference — Python 3.14*. [Python documentation](https://docs.python.org/3/reference/)



