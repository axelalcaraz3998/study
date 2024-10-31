Both composition and inheritance are object oriented programming concepts. They are not tied up with any specific programming language.
Composition over inheritance is the principle that classes should favor polymorphic behavior and code reuse by their composition (by containing instances of other classes that implement the desired functionality) over inheritance from a base or parent class. Ideally all reuse can be achieved by assembling existing components, but in practice inheritance is often needed to make new ones. Therefore inheritance and object composition typically work hand-in-hand.
## Inheritance
It is a type of relationship where a child acquires all behaviors from the parent. This is one of the core principles of object oriented programming. In this relationship, a child and the base class will have tight coupling between them. In other words, any change in the implementation detail's of the base class will impact the child's class.
## Composition
It is a type of relationship where a complex class is created combining other classes. This is also the most important principle of object oriented programming. In this type of relationship, both of the classes will have a loose coupling between them. In other words, any change in the implementation details of the one class will not impact another class.
## Is-A vs Has-A
In object oriented programming  "Is-A" s a relationship where one object is a subtype of another. A *Car* is a *Vehicle*, a *Dog* is an *Animal*. This relationship is manifested through inheritance. The "Has-A" relationship is where one object contains or uses another object. A *Car* has an *Engine*, a *Dog* has a *Tail*. This relationship is realized through composition.
Inheritance allows you to define a new class based on an existing one, thereby promoting reusability and code organization. On the other hand, composition is a way to combine simple objects or data types into more complex ones.
## Composition Over Inheritance
Despite the benefits of inheritance, it has its downsides. A major one is the tight coupling it creates, making a system rigid and harder to modify. Also, it can lead to a confusing hierarchy when overused. This is where the concept of favoring composition over inheritance comes into play.
With composition, you build complex objects by composing them of simple ones. Changing the behavior of a system involves changing the components, which are easier to manage than tangled inheritance hierarchies.
A rule of thumb for when to use composition over inheritance is when you want to model a Has-A relationship, or when you find yourself waiting to inherit from multiple classes, which is not supported in many classes.
Inheritance is often better suited when there is a clear Is-A relationship, and the subclass really is a type of a superclass. If you're dealing with an Is-A relationship that doesn't require much flexibility or change, inheritance might still be the way to go.

[[Object Oriented Programming]]