Tags: #ComputerScience #SoftwareDesignAndArchitecture 

Object-oriented programming (OOP) is a programming paradigm that organizes software around objects rather than function and logic. An object contains both data (attributes) and methods (behavior), making programs more modular and reusable. OOP helps developers build scalable, maintainable, and real-world applications efficiently.
# Core Concepts
## Class
A class is a blueprint or template used to create objects. It defines the properties (data) and behaviors (methods) that objects will have.
- Contains data members and methods.
- Does no occupy memory until an object is created.
## Object
An object is an instance of a class. It represents a real-world entity and can access the properties and methods defined in the class.
- Occupies memory when created.
- Used to access class members.
## Methods
Methods are functions that objects can perform. They are defined inside a class that describe the behaviors of an object. Programmers use methods for reusability or keeping functionality encapsulated inside one object at a time.
## Attributes
Attributes represent the state of an object. In other words, they are the characteristics that distinguish classes. Objects have data stored in the attributes field. Class attributes belong to the class itself and are defined in the class template.
# OOP Principles
## Inheritance
A class that is at the top of a hierarchy is known as the superclass (or base class, or parent class) whilst a class that is derived from another class is called a subclass (or derived class, extended class, or child class).

The primary goal of inheritance is to promote the concept of recycling code. We never want to copy and paste but rather extend upon it an utilizing inheritance in our apps ensures that we use as little code as possible. It achieves this by allowing a subclass to inherit attributes and behaviors from its superclass.
## Polymorphism
Polymorphism allows a single interface, method, or operator to behave differently depending on the specific object or data type it is interacting with. Polymorphism enhances the flexibility, readability, and scalability of software, improving the overall development process.

Polymorphism can be achieved through method overloading, where the method to be executed is determined at compile time based on different parameter types, or through method overriding, where a method in a subclass overrides a method in its superclass.
## Encapsulation
Encapsulation involves bundling the attributes and the methods that operate on the data into a single unit called a class. More importantly, encapsulation allows for restricting access to certain components of the object to ensure that the data is only accessible and modified through well-defined methods. This makes programs more secure, maintainable, and robust.

Encapsulation is achieved using access modifiers that define the visibility of a class member. The most common access modifiers are:
- **Private**: Members are not accessible from outside the class.
- **Protected**: Members are accessible within the class and by subclasses.
- **Public**: Members are accessible from anywhere in the program.
## Abstraction
Encapsulation and abstraction come hand in hand. The goal of abstraction is to hide the implementation details and display only the essential features of the object. It manages complexity by allowing users to interact with high-level interfaces without needing to know the background mechanisms.

Abstraction is typically achieved using two primary tools:
- **Abstract Classes**: Classes that cannot be instantiated on their own and serve as a blueprint. They contain a mix of implemented methods and abstract methods.
- **Interfaces**: Contracts that specify what a class should do, but not how it should do it. A class that implements an interface must provide the concrete implementation for all of its methods.
# References
## Articles
- [Introduction to Object Oriented Programming](https://www.geeksforgeeks.org/dsa/introduction-of-object-oriented-programming/)
- [What is Object-Oriented Programming?](https://www.techtarget.com/searchapparchitecture/definition/object-oriented-programming-OOP)
- [Object-Oriented Principles Explained](https://medium.com/codex/object-oriented-principles-explained-2d1d4bdd3be7)
- [Object-Oriented Programming: Polymorphism](https://medium.com/@hasan_denli/object-oriented-programming-polymorphism-fc6c7782f93b)
## Videos
- [Intro to Object Oriented Programming - Crash Course](https://www.youtube.com/watch?v=SiBw7os-_zI)

[[Programming Paradigms]]