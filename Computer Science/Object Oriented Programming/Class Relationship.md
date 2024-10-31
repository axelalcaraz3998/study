A class relationship is a logical connection between classes in a class diagram that describes how classes interact with each other.
Unified Modeling Language (UML) is a standardized visual language for modeling systems and software. It's used to specify, visualize, construct, and document software systems, as well as for business modeling and other non-software systems.
UML relationships are grouped into the following categories:

| Category        | Function                                                                                         |
| --------------- | ------------------------------------------------------------------------------------------------ |
| Activity edges  | Represent the flow between activites                                                             |
| Associations    | Indicate that instances of one model element are connected to instances of another model element |
| Dependencies    | Indicate that a change to one model element can affect another model element                     |
| Generalizations | Indicate that one model element is a specialization of another model element                     |
| Realizations    | Indicate that one model element provides a specification that another model element implements   |
| Transitions     | Represent changes in state                                                                       |
The following topics describe the relationships that you can use in a class diagram:
## Abstraction
An abstraction relationship is a dependency between model elements that represents the same concept at different levels of abstraction or from different viewpoints.
In an abstraction relationship, one model element, the client, is more refined or detailed than the other, the supplier. The different types of abstraction relationships include derivation, realization, refinement, and trace relationships.
## Aggregation
An aggregation is a special type of association in which objects are assembled or configured together to create a more complex object. An aggregation describes a group of objects and how you interact with them. Aggregation protects the integrity of an assembly of objects by defining a single control point, called the aggregate, in the object that represents the assembly. Aggregation also uses the control object to decide how the assembled objects respond to changes or instructions that might affect the collection.
## Association
An association represents a structural relationship that connects two classifiers. Like attributes, associations record the properties of classifiers. For example, in relationships between classes, you can use association to show the design decisions that you made about classes in your application that contain data, and to show which of those classes need to share data. You can use an association's navigability feature to show how an object of one class gains access to an object of another class, or, in reflexive association, to an object of the same class.
## Binding
A binding relationship is a relationship that assigns values to template parameters and generates a new model from the template.
The template is the supplier in the binding relationship, and the model element is the consumer. The binding does not affect the template, so you can bind the template to any number of model elements. The binding does affect the model element, however, because the model element is defined by replacing the template parameters with the template arguments that the binding relationship provides.
## Composition Association
A composition association relationship represents a whole-part relationship and is a form of aggregation. A composition association relationship specifies that the lifetime of the part classifier is dependent on the lifetime of the whole classifier.
In a composition association relationship, data usually flows in only one direction (that is, from the whole classifier to the part classifier).
## Dependency
A dependency relationship is a relationship in which one element, the client, uses or depends on another element, the supplier. You an use dependency relationships in class diagrams, component diagrams, deployment diagrams and use-case diagrams to indicate that a change to the supplier might require a change to the client.
You can also use dependency relationship to represent precedence, where one model element must precede another.
## Direct Association
Direct association relationships are associations that are navigable in only one direction.
A directed association indicates that control flows from one classifier to another, for example, an actor to an use case. This flow of control means that only one of the association ends specifies navigability.
## Element Import
An element import relationship identifies a model element in another package, and allows the element in the other package to be referenced by using its name without a qualifier.
An element import relationship is a direct relationship between an importing namespace and a package able element. The name of the package able element, or its alias, is added to the namespace of the importing namespace. You can also control whether the imported element can be further imported.
## Generalization
A generalization relationship is a relationship in which a one model element, the child, is based on another model element, the parent. Generalization relationships are used in class, component, deployment, and use-case diagrams to indicate that the child receives all the attributes, operations, and relationships that are defined in the parent.
## Interface Realization
An interface realization relationship is a specialized type of implementation relationship between a classifier and a provided interface. The interface realization relationship specifies that the realizing classifier must conform to the contract that the provided interface specifies.
## Instantiation
An instantiation relationship is a type of usage dependency between classifiers that indicates that the operations in one classifier create instances of the other classifier.
A dependency signifies that a single model element or set of elements require other model elements for their specification or implementation. This relationship means that the definition of the client model elements is either semantically or structurally dependent on the definition of the supplier model element.
## Package Import
A package import relationship allows other namespaces to use unqualified names to refer to package members.
A package import is a direct relationship that identifies packages whose members are imported by a namespace. A package import relationship between packages means that a package imports and can access elements within another package. A package import allows a package to import the member of another package making it possible to refer to elements of the imported package as if they were defined in the importing package.
## Realization
A realization relationship is a relationship between two model elements, in which one model element, the client, realizes the behavior that the other model element, the supplier, specifies. Several clients can realize the behavior of a single supplier.
## Usage
An usage relationship is a type of dependency relationship in which one model element, the client, requires another model element, the supplier, for full implementation or operation.
The usage dependency does not specify how the client uses the supplier.

[[Object Oriented Programming]]