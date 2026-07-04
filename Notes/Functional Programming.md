Tags: #ComputerScience #SoftwareDesignAndArchitecture 

Functional programming is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects. Functional programming is declarative rather than imperative, and application state flows through pure functions. Contrast with object-oriented programming, where application state is usually shared and collocated with method in objects.
# Core Concepts
## Pure Functions
A pure function is a function which: given the same inputs, always produces the same output, and has no side-effects. A dead giveaway that a function is impure is if it makes sense to call it without using its return value.

Pure functions have the following key properties:
- **Deterministic Behavior**: A pure function always yield the same result for identical inputs. This predictability helps simplify debugging and testing.
- **No Side Effects**: A pure function does not alter any external state, such as modifying global variables, printing output, or updating a database.
## Function Composition
Function composition is the process of combining two or more functions in order to produce a new function or perform some computation. Like the usual composition of functions in mathematics, the result of each function is passed as the argument to the next, and the result of the last one is the result of the whole.

The ability to easily compose functions encourages factoring (breaking apart) functions for maintainability and code reuse.
## Shared State
Shared state is any variable, object, or memory space that exists in a shared scope, or as the property of an object being passed between scopes. A shared scope can include global scope or closure scopes. Often, in object-oriented programming, objects are shared between scopes by adding properties to other objects.

The problem with shared state is that in order to understand the effects of a function, you have to know the entire history of every shared variable that the function uses or affects.
Another common problem associated with shared state is that changing the order in which functions are called can cause a cascade of failures because functions which act on shared state are timing dependent.

When you avoid shared state, the timing and order of function calls don't change the result of calling the function. With pure functions, given the same input, you'll always get the same output. This makes function calls completely independent of other function calls, which can radically simplify changes and refactoring.
## Immutability
An immutable object is an object that can't be modified after it's created. Conversely, a mutable object is any object which can be modified after it's created.

Immutability offers several benefits that make it a cornerstone of reliable software design:
- Thread safety and concurrency.
- Predictability and debugging.
- Data integrity.
- Efficient caching.
- Simplified state management.
## Side Effects
A side effect is any application stage change that is observable outside the called function other than its return value. Side effects include:
- Modifying any external variable or object property.
- Logging to the console.
- Writing to the screen.
- Writing to a file.
- Writing to a network.
- Triggering any external process.
- Calling any other function with side-effects.
## Higher Order Functions
A higher order function is any function which takes a function as an argument, returns a function or both. Higher order functions are often used to:
- Abstract or isolate actions, effects or async flow control using callback functions, promises, monads, etc.
- Create utilities which an act on a wide variety of data types.
- Partially apply a function to its arguments or create a curried function for the purpose of reuse or function composition.
- Take a list of functions and return some composition of those input functions.
# References
## Articles
- [Master the JavaScript Interview: What is Functional Programming?](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0)
- [Understanding Pure Functions: A Core Concept in Functional Programming](https://medium.com/@linz07m/understanding-pure-functions-a-core-concept-in-functional-programming-d2189b688e00)

[[Programming Paradigms]]