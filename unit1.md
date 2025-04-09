# Python Guide

## 1. Introduction to Python

Python is a high-level, interpreted programming language known for its readability and simplicity. Created by Guido van Rossum and first released in 1991, Python has become one of the most popular programming languages globally. It emphasizes code readability with its clean syntax and use of indentation. Python supports multiple programming paradigms including procedural, object-oriented, and functional programming.

Key features include:
- Easy to learn and use
- Interpreted language (no compilation required)
- Dynamically typed
- Extensive standard library
- Strong community support and extensive third-party packages

## 2. Defining Variables in Python

In Python, variables are created when you assign a value to them. No explicit declaration is needed:

```python
# Syntax for variable assignment
variable_name = value

# Examples
age = 25                  # Integer
name = "Alice"            # String
price = 19.99             # Float
is_student = True         # Boolean
```

Variable names must start with a letter or underscore, followed by letters, numbers, or underscores. Python variables are case-sensitive.

## 3. Comments in Python

Python supports three types of comments:

1. Single-line comments: Begin with `#`
   ```python
   # This is a single-line comment
   ```

2. Multi-line comments: Multiple `#` symbols or triple quotes
   ```python
   # This is a multi-line comment
   # using multiple hash symbols
   
   """
   This is a multi-line comment
   using triple double quotes
   """
   
   '''
   This is also a multi-line comment
   using triple single quotes
   '''
   ```

3. Docstrings: Documentation strings that appear right after function/class definitions
   ```python
   def add(a, b):
       """
       This function adds two numbers and returns the result
       Parameters:
           a: first number
           b: second number
       """
       return a + b
   ```

## 4. Inbuilt Data Types in Python

Python has several built-in data types:

1. Numeric Types:
   - `int`: Integer numbers (e.g., 5, -17, 1000)
   - `float`: Floating-point numbers (e.g., 3.14, -0.001, 2.5e2)
   - `complex`: Complex numbers (e.g., 2+3j)

2. Sequence Types:
   - `str`: String of characters (e.g., "Hello")
   - `list`: Ordered, mutable collection (e.g., [1, 2, 3])
   - `tuple`: Ordered, immutable collection (e.g., (1, 2, 3))

3. Mapping Type:
   - `dict`: Key-value pairs (e.g., {"name": "John", "age": 30})

4. Set Types:
   - `set`: Unordered collection of unique elements (e.g., {1, 2, 3})
   - `frozenset`: Immutable version of a set

5. Boolean Type:
   - `bool`: True or False

6. Binary Types:
   - `bytes`: Immutable sequence of bytes
   - `bytearray`: Mutable sequence of bytes
   - `memoryview`: Memory view of an object

7. None Type:
   - `NoneType`: The None object represents absence of value

## 5. Input/Output Functions in Python

Input functions:
- `input()`: Reads a line from standard input (keyboard)
  ```python
  name = input("Enter your name: ")  # Displays prompt and waits for user input
  ```

Output functions:
- `print()`: Displays output to the console
  ```python
  print("Hello, World!")  # Basic usage
  print("Name:", name, "Age:", age)  # Multiple values
  print(f"Hello, {name}!")  # f-string (Python 3.6+)
  print("Score: %.2f" % score)  # Old-style formatting
  print("Hello {}, you are {} years old".format(name, age))  # str.format()
  ```

File I/O functions:
- `open()`: Opens a file and returns a file object
- `read()`, `readline()`, `readlines()`: Read from files
- `write()`, `writelines()`: Write to files
- `close()`: Close file objects

## 6. Difference Between List, Tuple, Set, Dictionary

| Feature | List | Tuple | Set | Dictionary |
|---------|------|-------|-----|------------|
| Syntax | `[1, 2, 3]` | `(1, 2, 3)` | `{1, 2, 3}` | `{"a": 1, "b": 2}` |
| Mutability | Mutable | Immutable | Mutable | Mutable |
| Ordered | Yes | Yes | No | Ordered (Python 3.7+) |
| Indexing | Yes | Yes | No | Via keys |
| Duplicates | Allowed | Allowed | Not allowed | Not allowed for keys |
| Use Case | General sequence of items | Immutable collection | Unique items | Key-value mapping |

## 7. Types of Operators in Python

Python supports several types of operators:

1. Arithmetic Operators: `+`, `-`, `*`, `/`, `%`, `**`, `//`
2. Assignment Operators: `=`, `+=`, `-=`, `*=`, `/=`, etc.
3. Comparison Operators: `==`, `!=`, `>`, `<`, `>=`, `<=`
4. Logical Operators: `and`, `or`, `not`
5. Identity Operators: `is`, `is not`
6. Membership Operators: `in`, `not in`
7. Bitwise Operators: `&`, `|`, `^`, `~`, `<<`, `>>`

Membership Operators in detail:
- `in`: Returns True if a value exists in the sequence
- `not in`: Returns True if a value does not exist in the sequence

```python
fruits = ["apple", "banana", "cherry"]
print("apple" in fruits)      # True
print("mango" not in fruits)  # True
```

Bitwise Operators in detail:
- `&` (AND): Sets each bit to 1 if both bits are 1
- `|` (OR): Sets each bit to 1 if one of the bits is 1
- `^` (XOR): Sets each bit to 1 if only one of the bits is 1
- `~` (NOT): Inverts all the bits
- `<<` (Left shift): Shifts bits left by pushing zeros from the right
- `>>` (Right shift): Shifts bits right by pushing copies of the leftmost bit from the left

```python
a = 10  # 1010 in binary
b = 4   # 0100 in binary

print(a & b)   # 0 (0000 in binary)
print(a | b)   # 14 (1110 in binary)
print(a ^ b)   # 14 (1110 in binary)
print(~a)      # -11 (inversion of bits plus 1 for signed integers)
print(a << 1)  # 20 (10100 in binary)
print(a >> 1)  # 5 (0101 in binary)
```

## 8. Strings and String Functions

A string is a sequence of characters enclosed in quotes (single, double, or triple).

Common string methods include:
- `upper()`, `lower()`, `title()`: Change case
- `strip()`, `lstrip()`, `rstrip()`: Remove whitespace
- `replace(old, new)`: Replace occurrences
- `split(separator)`: Split string into list
- `join(iterable)`: Join elements using the string as separator
- `find(substring)`, `index(substring)`: Find substring
- `count(substring)`: Count occurrences
- `startswith(prefix)`, `endswith(suffix)`: Check prefix/suffix
- `isalpha()`, `isdigit()`, `isalnum()`, `isspace()`: Check character types
- `format()`: Format string with placeholders
- `len()`: Get length (this is a function, not a method)

```python
s = "Hello, World!"
print(s.upper())        # HELLO, WORLD!
print(s.find("World"))  # 7
print(s.replace("World", "Python"))  # Hello, Python!
print(len(s))           # 13
```

## 9. List Functions and Item Removal

Common list methods:
- `append(item)`: Add item to end
- `extend(iterable)`: Add all items from an iterable
- `insert(index, item)`: Insert at position
- `remove(item)`: Remove first occurrence
- `pop([index])`: Remove and return item at index (default: last)
- `clear()`: Remove all items
- `index(item)`: Find position of item
- `count(item)`: Count occurrences
- `sort()`: Sort in place
- `reverse()`: Reverse in place
- `copy()`: Return a shallow copy

Ways to remove items from a list:
```python
numbers = [1, 2, 3, 4, 5]

# Method 1: remove() - removes by value
numbers.remove(3)  # [1, 2, 4, 5]

# Method 2: pop() - removes by index and returns the value
value = numbers.pop(1)  # numbers = [1, 4, 5], value = 2

# Method 3: del statement - removes by index or slice
del numbers[0]  # [4, 5]

# Method 4: clear() - removes all items
numbers.clear()  # []

# Method 5: list comprehension - filtering
numbers = [1, 2, 3, 4, 5]
numbers = [x for x in numbers if x != 3]  # [1, 2, 4, 5]
```

## 10. Types of Functions

Python has several types of functions:

1. Built-in Functions:
   - Functions that are part of Python's standard library (e.g., `print()`, `len()`, `map()`)

2. User-defined Functions:
   - Created using the `def` keyword
   ```python
   def greet(name):
       return f"Hello, {name}!"
   ```

3. Anonymous Functions (Lambda):
   - Small, one-line functions without a name
   ```python
   square = lambda x: x**2
   ```

4. Methods:
   - Functions that belong to objects
   ```python
   my_list = [1, 2, 3]
   my_list.append(4)  # append() is a method of the list object
   ```

5. Recursive Functions:
   - Functions that call themselves
   ```python
   def factorial(n):
       if n <= 1:
           return 1
       return n * factorial(n-1)
   ```

6. Generator Functions:
   - Functions that return an iterator using `yield`
   ```python
   def countdown(n):
       while n > 0:
           yield n
           n -= 1
   ```

7. Higher-order Functions:
   - Functions that take other functions as arguments or return functions
   ```python
   def apply(func, value):
       return func(value)
   ```

8. Closures:
   - Functions that capture and remember the environment in which they were created
   ```python
   def outer(x):
       def inner(y):
           return x + y
       return inner
   ```

9. Decorators:
   - Functions that modify the behavior of other functions
   ```python
   def my_decorator(func):
       def wrapper():
           print("Before function call")
           func()
           print("After function call")
       return wrapper
       
   @my_decorator
   def say_hello():
       print("Hello!")
   ```

## 11. Use of Range Function in For Loop

The `range()` function generates a sequence of numbers which is commonly used in for loops. It can take 1-3 arguments:

- `range(stop)`: Generates numbers from 0 to stop-1
- `range(start, stop)`: Generates numbers from start to stop-1
- `range(start, stop, step)`: Generates numbers from start to stop-1 with step increment

```python
# Print numbers 0-4
for i in range(5):
    print(i)  # 0, 1, 2, 3, 4

# Print numbers 2-5
for i in range(2, 6):
    print(i)  # 2, 3, 4, 5

# Print even numbers 0-10
for i in range(0, 11, 2):
    print(i)  # 0, 2, 4, 6, 8, 10

# Count backwards
for i in range(10, 0, -1):
    print(i)  # 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```

## 12. Conditional Control Statements

Python has several conditional control statements:

1. `if` statement: Executes a block if condition is True
```python
age = 18
if age >= 18:
    print("You are an adult")
```

2. `if-else` statement: Executes one block if condition is True, another if False
```python
age = 16
if age >= 18:
    print("You are an adult")
else:
    print("You are a minor")
```

3. `if-elif-else` statement: Checks multiple conditions
```python
score = 85
if score >= 90:
    print("A grade")
elif score >= 80:
    print("B grade")
elif score >= 70:
    print("C grade")
else:
    print("Below C grade")
```

4. Nested if statements: if statements inside another if statement
```python
age = 25
income = 50000
if age >= 18:
    if income >= 30000:
        print("Eligible for loan")
    else:
        print("Income too low")
else:
    print("Age not sufficient")
```

5. Ternary operator: Shorthand for if-else
```python
age = 20
status = "adult" if age >= 18 else "minor"
```

## 13. Jump Statements in Python

Python has four jump statements:

1. `break`: Exits the loop completely
```python
for i in range(10):
    if i == 5:
        break  # Exit when i equals 5
    print(i)  # 0, 1, 2, 3, 4
```

2. `continue`: Skips the current iteration and moves to the next
```python
for i in range(10):
    if i % 2 == 0:
        continue  # Skip even numbers
    print(i)  # 1, 3, 5, 7, 9
```

3. `pass`: Does nothing, acts as a placeholder
```python
for i in range(5):
    if i == 2:
        pass  # Do nothing special
    print(i)  # 0, 1, 2, 3, 4
```

4. `return`: Exits a function and returns a value
```python
def find_element(lst, element):
    for i, value in enumerate(lst):
        if value == element:
            return i  # Return index and exit function
    return -1  # Return -1 if element not found
```

## 14. Program to Display Prime Numbers till N

```python
def is_prime(n):
    """Check if a number is prime."""
    if n <= 1:
        return False
    if n <= 3:
        return True
    if n % 2 == 0 or n % 3 == 0:
        return False
    
    i = 5
    while i * i <= n:
        if n % i == 0 or n % (i + 2) == 0:
            return False
        i += 6
    return True

def print_primes_till_n(n):
    """Print all prime numbers from 2 to n."""
    print(f"Prime numbers up to {n}:")
    for num in range(2, n + 1):
        if is_prime(num):
            print(num, end=" ")
    print()  # New line after all primes

# Example usage
n = 50
print_primes_till_n(n)
```

Output:
```
Prime numbers up to 50:
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47
```

## 15. Program to Check for Palindrome

```python
def is_palindrome(input_str):
    """
    Check if a string is a palindrome.
    A palindrome reads the same forward and backward.
    """
    # Convert to lowercase and remove non-alphanumeric characters
    clean_str = ''.join(char.lower() for char in input_str if char.isalnum())
    
    # Check if the string equals its reverse
    return clean_str == clean_str[::-1]

# Test the function with different inputs
test_strings = ["radar", "A man, a plan, a canal: Panama", "hello", "Madam", "12321"]

for test_str in test_strings:
    if is_palindrome(test_str):
        print(f'"{test_str}" is a palindrome')
    else:
        print(f'"{test_str}" is not a palindrome')
```

Output:
```
"radar" is a palindrome
"A man, a plan, a canal: Panama" is a palindrome
"hello" is not a palindrome
"Madam" is a palindrome
"12321" is a palindrome
```
