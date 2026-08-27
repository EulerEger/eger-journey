---
title: 'Object-Oriented'
date: '2026-02-10'
draft: false
categories: ["Coding", "Python"]
category_weight: 60
weight: 60
---

## Introduction

Python is an object-oriented programming (OOP) language, which means it is designed around the concept of objects. An object is a collection of data (attributes) and methods (functions) that operate on that data. 

In Python, objects are created using classes, which act as blueprints for the objects. OOP allows for modular, reusable, and maintainable code by organizing related data and behavior into classes.

## Classes and Objects

### What is a Class?

A class is a blueprint for creating objects. It defines:

Attributes: Variables that store data.

Methods: Functions that perform operations on the data.

### What is an Object?

An object is an instance of a class. When you create an object, you are creating a specific instance of the class with its own data.

### Defining a Class

To define a class in Python, use the class keyword followed by the class name and parentheses.

Example: Particle Class

Let’s create a Particle class to represent a particle in 3D space with position, velocity, and mass.

{{< highlight python >}}
class Particle:
    def init(self, x, y, z, vx, vy, vz, m):
        self.x = x    # Position in x-axis
        self.y = y    # Position in y-axis
        self.z = z    # Position in z-axis
        self.vx = vx  # Velocity in x-axis
        self.vy = vy  # Velocity in y-axis
        self.vz = vz  # Velocity in z-axis
        self.m = m    # Mass
{{< /highlight >}}

### Explanation

**__init__**: A special method called the constructor. It is automatically called when an object is created.

**self**: Refers to the instance of the class. It allows you to access the attributes and methods of the class.

### Creating Objects

Once the class is defined, you can create objects (instances) of that class.

Example: Create Particle Objects

{{< highlight python >}}
p1 = Particle(3, 0, 1, 1, 0, 0, 3)
p2 = Particle(1, 0, 1, 1, 0, 0, 3)

print(p1.x, p2.x)  # Output: 3 1
{{< /highlight >}}

## Methods

Methods are functions defined inside a class that perform operations on the object’s data. They can access and modify the object’s attributes using self.

Example: Adding Methods to Particle

Let’s add two methods to the Particle class:

**move(t)**: Updates the particle’s position based on its velocity and time t.

**get_distance()**: Calculates the distance from the origin.

{{< highlight python >}}
import math

class Particle:
    def init(self, x, y, z, vx, vy, vz, m):
        self.x = x
        self.y = y
        self.z = z
        self.vx = vx
        self.vy = vy
        self.vz = vz
        self.m = m

def move(self, t):
    self.x += self.vx * t
    self.y += self.vy * t
    self.z += self.vz * t

def get_distance(self):
    return math.sqrt(self.x**2 + self.y**2 + self.z**2)

### Create a particle and move it

p = Particle(3, 0, 1, 1, 0, 0, 3)
p.move(2)
print(p.x, p.y, p.z)  # Output: 5 0 1
print(p.get_distance())  # Output: 5.0990195135927845
{{< /highlight >}}

## Inheritance

Inheritance allows a child class to inherit attributes and methods from a parent class. This promotes code reusability and hierarchical organization.

Example: Proton Inherits from Particle

A Proton is a type of Particle with additional attributes like electric charge.

{{< highlight python >}}
class Proton(Particle):
    def init(self, x, y, z, vx, vy, vz):
        self.q = 1.6e-19  # Electric charge of a proton
        self.m = 1.67e-27  # Mass of a proton
        super().init(x, y, z, vx, vy, vz, self.m)

### Create a proton

p = Proton(0, 0, 1, 1, 0, 0)
print(p.x)  # Output: 0
p.move(2)
print(p.x)  # Output: 2
{{< /highlight >}}

Explanation

**super().__init__(...)**: Calls the parent class’s __init__ method to initialize inherited attributes.

**Proton** inherits all attributes and methods from Particle and adds its own (q).

### Overriding Methods

You can override methods in the child class to provide specific behavior.

Example: Override move in Proton

Let’s modify the move method to account for the motion of the proton in an electric field.

{{< highlight python >}}
class Proton(Particle):
    def init(self, x, y, z, vx, vy, vz):
        self.q = 1.6e-19  # Electric charge
        self.m = 1.67e-27  # Mass
        super().init(x, y, z, vx, vy, vz, self.m)

def move(self, t, Ex=0, Ey=0, Ez=0):
    # Update position based on velocity and electric field
    self.x += self.vx * t + (0.5 * (self.q / self.m) * Ex * t**2)
    self.y += self.vy * t + (0.5 * (self.q / self.m) * Ey * t**2)
    self.z += self.vz * t + (0.5 * (self.q / self.m) * Ez * t**2)
    # Update velocity based on electric field
    self.vx += (self.q / self.m) * Ex * t
    self.vy += (self.q / self.m) * Ey * t
    self.vz += (self.q / self.m) * Ez * t

def get_position(self):
    return [self.x, self.y, self.z]

def get_velocity(self):
    return [self.vx, self.vy, self.vz]

Create a proton and move it in an electric field

p = Proton(0, 0, 1, 1, 0, 0)
p.move(t=2, Ex=4e-12, Ey=3e-12, Ez=6e-12)
print(p.get_position())  # Output: [3.4050494, 1.05378705, 3.10757409]

p.move(t=2, Ex=4e-12, Ey=3e-12, Ez=6e-12)
print(p.get_position())  # Output: [13.78155873, 8.16684962, 14.17233809]
{{< /highlight >}}

### Polymorphism

Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables flexibility and dynamic method resolution.

Example: Polymorphism with Particle and Proton

Both Particle and Proton objects can call the move method, but the behavior differs based on the object’s class.

{{< highlight python >}}

### Create a Particle and a Proton

particle = Particle(0, 0, 0, 1, 0, 0, 1)
proton = Proton(0, 0, 0, 1, 0, 0)

Both objects have a move method, but they behave differently

particle.move(1)
proton.move(1, Ex=1e-12, Ey=0, Ez=0)

print("Particle position:", particle.x, particle.y, particle.z)
print("Proton position:", proton.x, proton.y, proton.z)
{{< /highlight >}}

## Encapsulation

Encapsulation is the concept of bundling data (attributes) and methods that operate on the data within a single unit (class). It also involves restricting direct access to some of the object’s components, which is a way of preventing accidental modification of data.

### Private Attributes

In Python, you can use name mangling to make attributes private by prefixing them with double underscores (__).

Example: Private Attributes

{{< highlight python >}}
class BankAccount:
    def init(self, balance):
        self.__balance = balance  # Private attribute

def deposit(self, amount):
    if amount > 0:
        self.__balance += amount

def get_balance(self):
    return self.__balance

account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())  # Output: 1500

print(account.__balance)  # Error: AttributeError

{{< /highlight >}}

## Class Methods and Static Methods

### Class Methods

A class method is a method that is bound to the class rather than its object. It takes the class (cls) as the first argument instead of the instance (self).

Example: Class Method

{{< highlight python >}}
class Particle:
    count = 0  # Class attribute

def __init__(self, x, y, z):
    self.x = x
    self.y = y
    self.z = z
    Particle.count += 1

@classmethod
def get_count(cls):
    return cls.count

p1 = Particle(1, 2, 3)
p2 = Particle(4, 5, 6)
print(Particle.get_count())  # Output: 2
{{< /highlight >}}

### Static Methods

A static method is a method that belongs to the class rather than an instance of the class. It does not take self or cls as an argument.

Example: Static Method

{{< highlight python >}}
class MathUtils:
    @staticmethod
    def add(a, b):
        return a + b

print(MathUtils.add(5, 3))  # Output: 8
{{< /highlight >}}

### Special Methods (Magic Methods)

Python classes can define special methods (also called "magic methods") to customize the behavior of built-in operations like +, -, ==, etc.

Example: __str__ Method

The __str__ method defines how an object is represented as a string.

{{< highlight python >}}
class Particle:
    def init(self, x, y, z):
        self.x = x
        self.y = y
        self.z = z

def __str__(self):
    return f"Particle at ({self.x}, {self.y}, {self.z})"

p = Particle(1, 2, 3)
print(p)  # Output: Particle at (1, 2, 3)
{{< /highlight >}}

## Conclusion

Object-Oriented Programming (OOP) in Python allows you to:

Organize code into classes and objects.

Reuse code through inheritance.

Customize behavior with polymorphism.

Protect data using encapsulation.

Add flexibility with class and static methods.

OOP is a powerful paradigm for writing modular, reusable, and maintainable code.



{{< pageview >}}
