In object oriented programming, both abstract classes and interfaces serve as fundamental constructs for defining contracts. They establish a blueprint for other classes, ensuring consistent implementations of methods and behaviors.
## Interface
An interface is a description of the actions that an object can do, for example, when you flip a light switch, the light goes on, you don't care how, just that it does. In object oriented programming, an interface is a description of all functions that an object must have. The purpose of interfaces is to allow the computer to enforce these properties and to know that an object must have certain functions.
## Abstract Class
An abstract class is a template definition of methods and properties in a specific class, or category of objects.
Abstract classes are classes that contain on ore more abstracted behaviors or methods. Objects or classes can be abstracted, which means that they are summarized into characteristics relevant to the current program's operation.
## Interfaces vs Abstract Classes
An interface is another similar way to create an abstraction. Like abstract classes, interfaces can't be instantiated. But unlike abstract classes, an interface method can be set as abstract.
Abstract classes can also have final, non-final, static and non-static variables, whereas an interface has only static and final variables. Additionally, abstract methods can define public, protected and private concrete methods, while interfaces have all fields automatically public, static and final. Interfaces, however, support multiple inheritances where abstract classes don't.

| Points                    | Abstract Class                                                      | Interface                                                                          |
| ------------------------- | ------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| **Definition**            | Cannot be instantiated, contains both abstract and concrete methods | Specifies a set of methods a class must implement, methods are abstract by default |
| **Implementation Method** | Can have both implemented and abstract methods                      | Methods are abstract by default but allows default and static methods              |
| **Inheritance**           | A class can inherit from only one abstract class                    | A class can implement multiple interfaces                                          |
| **Access Modifiers**      | Methods and properties can have any access modifier                 | Methods and properties are implicitly public                                       |
| **Variables**             | Can have member variables                                           | Variables are implicitly public, static and final                                  |

[[Object Oriented Programming]]