# Python Concepts Overview

## 1. Types of Inheritance in Python

Python supports several types of inheritance:

**Single Inheritance**: A child class inherits from only one parent class.
```python
class Parent:
    def method1(self):
        print("Parent method")

class Child(Parent):  # Child inherits from Parent
    def method2(self):
        print("Child method")
```

**Multiple Inheritance**: A child class inherits from multiple parent classes.
```python
class Parent1:
    def method1(self):
        print("Parent1 method")

class Parent2:
    def method2(self):
        print("Parent2 method")

class Child(Parent1, Parent2):  # Child inherits from both parents
    pass
```

**Multilevel Inheritance**: A child class inherits from a parent class, which in turn inherits from another parent.
```python
class Grandparent:
    def method1(self):
        print("Grandparent method")

class Parent(Grandparent):
    def method2(self):
        print("Parent method")

class Child(Parent):  # Child inherits from Parent which inherits from Grandparent
    def method3(self):
        print("Child method")
```

**Hierarchical Inheritance**: Multiple child classes inherit from a single parent class.
```python
class Parent:
    def method1(self):
        print("Parent method")

class Child1(Parent):  # Child1 inherits from Parent
    def method2(self):
        print("Child1 method")

class Child2(Parent):  # Child2 also inherits from Parent
    def method3(self):
        print("Child2 method")
```

**Hybrid Inheritance**: Combination of multiple inheritance types.
```python
class A:
    pass

class B(A):  # Single inheritance
    pass

class C(A):  # Hierarchical inheritance
    pass

class D(B, C):  # Multiple inheritance
    pass
```

## 2. Compile Time vs Runtime Polymorphism

Python primarily uses runtime polymorphism since it's a dynamically typed language.

**Compile Time (Static) Polymorphism**:
- In Python, this is limited but represented by method overloading through default parameters or *args and **kwargs
- Determined during compilation
- Example of function overloading (simulated in Python):
```python
def add(a, b=0, c=0):
    return a + b + c
    
# Can be called as add(1), add(1, 2), or add(1, 2, 3)
```

**Runtime (Dynamic) Polymorphism**:
- Method overriding in inheritance
- Determined during execution
- Example:
```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    def speak(self):  # Method overriding
        print("Dog barks")

# Runtime polymorphism
animal = Dog()
animal.speak()  # Output: "Dog barks"
```

## 3. Access Modifiers in Python

Python uses naming conventions for access modifiers rather than strict keywords:

**Public**: No prefix, accessible from anywhere.
```python
class MyClass:
    def public_method(self):  # Public method
        print("Public method")
    
    public_var = "I am public"  # Public variable
```

**Protected**: Single underscore prefix (_), suggests the attribute shouldn't be accessed directly outside the class but can be.
```python
class MyClass:
    def _protected_method(self):  # Protected method
        print("Protected method")
    
    _protected_var = "I am protected"  # Protected variable
```

**Private**: Double underscore prefix (__), name mangling is applied to prevent direct access from outside.
```python
class MyClass:
    def __private_method(self):  # Private method
        print("Private method")
    
    __private_var = "I am private"  # Private variable
    
    def access_private(self):
        print(self.__private_var)
        self.__private_method()
```

## 4. Multiple Inheritance with a Suitable Program

Multiple inheritance allows a class to inherit attributes and methods from multiple parent classes.

```python
class Employee:
    def __init__(self, emp_id, name):
        self.emp_id = emp_id
        self.name = name
    
    def display_employee_details(self):
        print(f"Employee ID: {self.emp_id}, Name: {self.name}")

class Engineer:
    def __init__(self, specialization):
        self.specialization = specialization
    
    def display_specialization(self):
        print(f"Specialization: {self.specialization}")

class ProjectManager(Employee, Engineer):
    def __init__(self, emp_id, name, specialization, projects):
        Employee.__init__(self, emp_id, name)
        Engineer.__init__(self, specialization)
        self.projects = projects
    
    def display_projects(self):
        print(f"Managing projects: {self.projects}")

# Usage
pm = ProjectManager("E123", "John Doe", "Software Development", ["Project A", "Project B"])
pm.display_employee_details()
pm.display_specialization()
pm.display_projects()
```

## 5. Constructors and Their Types

A constructor is a special method that is automatically called when an object is created.

**Types of Constructors in Python**:

**Default Constructor**: Created by Python if no constructor is defined.
```python
class DefaultConstructor:
    pass  # Python provides an implicit constructor

obj = DefaultConstructor()  # Constructor called automatically
```

**Parameterized Constructor**: Accepts parameters for initialization.
```python
class Student:
    def __init__(self, name, age):  # Parameterized constructor
        self.name = name
        self.age = age

student = Student("Alice", 20)  # Pass values to constructor
```

**Non-parameterized Constructor**: Explicitly defined but takes no parameters.
```python
class Counter:
    def __init__(self):  # Non-parameterized constructor
        self.count = 0

counter = Counter()
```

## 6. The super() Function with a Suitable Program

The `super()` function allows a child class to access methods and properties from its parent class.

```python
class Vehicle:
    def __init__(self, make, model):
        self.make = make
        self.model = model
    
    def vehicle_info(self):
        return f"{self.make} {self.model}"

class Car(Vehicle):
    def __init__(self, make, model, year):
        super().__init__(make, model)  # Call parent's constructor
        self.year = year
    
    def car_info(self):
        return f"{super().vehicle_info()}, Year: {self.year}"

# Usage
my_car = Car("Toyota", "Corolla", 2020)
print(my_car.car_info())  # Output: Toyota Corolla, Year: 2020
```

## 7. The self Keyword and Its Use

The `self` keyword is a reference to the current instance of a class. It's the first parameter in any instance method.

Uses of `self`:
- Access instance variables
- Call instance methods
- Reference the current object

```python
class Person:
    def __init__(self, name, age):
        self.name = name  # Using self to create instance variables
        self.age = age
    
    def introduce(self):
        # Using self to access instance variables
        print(f"My name is {self.name} and I am {self.age} years old")
    
    def birthday(self):
        self.age += 1  # Using self to modify instance variables
        self.introduce()  # Using self to call another instance method

# Usage
person = Person("Alice", 30)
person.introduce()
person.birthday()
```

## 8. try-except-finally Clause with Example

The try-except-finally structure is used for exception handling in Python.

```python
def divide_numbers(a, b):
    try:
        # Code that might raise an exception
        result = a / b
        print(f"Result: {result}")
    except ZeroDivisionError:
        # Handling specific exception
        print("Error: Division by zero is not allowed")
    except Exception as e:
        # Handling any other exception
        print(f"An error occurred: {e}")
    finally:
        # This block always executes
        print("Execution completed")

# Test cases
divide_numbers(10, 2)  # Normal execution
divide_numbers(10, 0)  # ZeroDivisionError
```

## 9. Abstraction in Python

Abstraction is the concept of hiding the complex implementation details and showing only the necessary features.

In Python, abstraction is achieved using abstract classes and methods:

```python
from abc import ABC, abstractmethod

class Shape(ABC):  # Abstract Base Class
    @abstractmethod
    def area(self):
        pass
    
    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width
    
    def area(self):  # Implementation of abstract method
        return self.length * self.width
    
    def perimeter(self):  # Implementation of abstract method
        return 2 * (self.length + self.width)

# Usage
# shape = Shape()  # Would raise an error - cannot instantiate abstract class
rectangle = Rectangle(5, 3)
print(f"Area: {rectangle.area()}")
print(f"Perimeter: {rectangle.perimeter()}")
```

## 10. Reading and Writing Files in Python

Python provides built-in functions for file operations:

**Opening a File**:
```python
# Modes: 'r' (read), 'w' (write), 'a' (append), 'r+' (read & write), 'b' (binary)
file = open('filename.txt', 'r')  # Open for reading
# Always close files when done
file.close()

# Better approach using context manager (automatically closes file)
with open('filename.txt', 'r') as file:
    # Operations with file
    pass  # File automatically closed after this block
```

**Reading from a File**:
```python
# Read entire file
with open('filename.txt', 'r') as file:
    content = file.read()
    print(content)

# Read line by line
with open('filename.txt', 'r') as file:
    for line in file:
        print(line, end='')

# Read specific number of characters
with open('filename.txt', 'r') as file:
    chunk = file.read(10)  # Read first 10 characters
    print(chunk)

# Read all lines into a list
with open('filename.txt', 'r') as file:
    lines = file.readlines()
    print(lines)
```

**Writing to a File**:
```python
# Write to file (overwrites existing content)
with open('filename.txt', 'w') as file:
    file.write("Hello, World!\n")
    file.write("This is a new line.")

# Append to file
with open('filename.txt', 'a') as file:
    file.write("\nThis line is appended.")

# Write multiple lines
lines = ["Line 1", "Line 2", "Line 3"]
with open('filename.txt', 'w') as file:
    file.writelines(line + '\n' for line in lines)
```

## 11. Program to Create even.txt and odd.txt Files

```python
def create_even_odd_files():
    # Create and write even numbers to even.txt
    with open('even.txt', 'w') as even_file:
        for i in range(1, 51):
            even_number = i * 2
            even_file.write(f"{even_number}\n")
    
    # Create and write odd numbers to odd.txt
    with open('odd.txt', 'w') as odd_file:
        for i in range(1, 51):
            odd_number = (i * 2) - 1
            odd_file.write(f"{odd_number}\n")
    
    print("Files created successfully!")
    
    # Verify by reading and printing the first few numbers from each file
    print("\nFirst 5 even numbers:")
    with open('even.txt', 'r') as even_file:
        for _ in range(5):
            print(even_file.readline().strip())
    
    print("\nFirst 5 odd numbers:")
    with open('odd.txt', 'r') as odd_file:
        for _ in range(5):
            print(odd_file.readline().strip())

# Execute the function
create_even_odd_files()
```
