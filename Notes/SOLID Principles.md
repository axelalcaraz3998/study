Tags: #ComputerScience #SoftwareDesignAndArchitecture 

SOLID principles are five foundational object-oriented design guidelines. They help developer write software that is maintainable, scalable, and easy to test.

The following five concepts make up the SOLID principles:
- Single-responsibility Principle
- Open-closed Principle
- Liskov Substitution Principle
- Interface Segregation Principle
- Dependency Inversion Principle
# Single Responsibility Principle
This principle states that a class should only have one responsibility. Furthermore, it should only have one reason to change. Meaning that a class should have only one job.

How does this principle help us build better software?
- **Testing**: A class with only one responsibility will have far fewer test cases.
- **Lower Coupling**: Less functionality in a single class will have fewer dependencies.
- **Organization**: Smaller, well-organized classes are easier to search than monolithic ones.
# Open-closed Principle
Simply put, classes should be open for extension but closed for modification. This means that you should be able to add new functionality to a system without changing existing, already tested code.

How it works:
- **Closed For Modification**: Once code is written, tested, and deployed, you should not alter its source code to add new features.
- **Open For Extension**: You can adapt new behavior to the entity to meet new requirements by adding new code (e.g. creating new classes or methods)
# Liskov Substitution Principle
The Liskov Substitution principle is arguably the most complex of the five principles. Simpy put, if a class A is a subtype of class B, we should be able to replace B with A without disrupting the behavior of our program. This means that every subclass or derived class should be substitutable for their base or parent class.

Following the Liskov substitution principle requires the objects of your subclasses to behave the same way as the objects of your superclass.
# Interface Segregation Principle
The interface segregation principle states that a client should never be forced to implement an interface that it doesn't use, or clients shouldn't be forced to depend on methods they do not use.

Interface segregation emphasizes that large, general-purpose interfaces should be broken down into smaller, more specific ones. This way, client classes only need to know about the methods that are relevant to them.
# Dependency Inversion Principle
The principle of dependency inversion states that entities must depend on abstractions, not on concretions. It states that the high-level module must not depend on the low-level module, but they should depend on abstractions.

This principle refers to the decoupling of software modules. This way, instead of high-level modules depending on low-level modules, both will depend on abstractions.
# References
## Articles
- [SOLID Design Principles Explained: Building Better Software Architecture](https://www.digitalocean.com/community/conceptual-articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)
- [A Solid Guide to SOLID Principles](https://www.baeldung.com/solid-principles)
## Videos
- [SOLID Principles: Do You Really Understand Them?](https://www.youtube.com/watch?v=kF7rQmSRlq0)

[[Design Principles]]