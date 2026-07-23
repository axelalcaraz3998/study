Tags: #ComputerScience #DSA 

A stack is a linear data structure that follows a particular order in which the operations are performed, LIFO (Last In First Out). It behaves like a stack of plates, where the last plate added is the first one to be removed.
![[stack.webp]]
# The LIFO (Last In First Out) Principle
The LIFO principle means that the last element added to a stack is the first one to be removed.
- New elements are always pushed to the top.
- Removal (pop) also happens only from the top.
- This ensures a strict order: last in -> first out.
# Types of Stack
## Fixed Size Stack
- A fixed size stack has a predefined capacity.
- Once it becomes full, no more elements can be added.
- If the stack is empty and we try to remove an element it causes underflow.
- Typically implemented using a static array.
## Dynamic Size Stack
- A dynamic size stack can grow and shrink automatically as needed.
- If the stack is full, its capacity expands to allow for more elements.
- As elements are removed, memory usage can shrink as well.
- Can be implemented using a linked list or a dynamic array.
# Common Operations
- **Push**: Inserts an element into the sack.
- **Pop**: Removes an element from the stack.
- **Top**: Returns the top element of the stack.
- **Size**: Returns the size of the stack.
# Applications
- **Function Calls**: Stacks manage the *active* functions in a program. When a function is called, its execution state is pushed onto the stack, when it finishes, it is pooped to return control to the caller.
- **Recursion**: Since recursion is essentially a function calling itself, the stack stores a snapshot of each call so the program doesn't lose its place.
- **Expression Evaluation**: Stacks are used by compilers and calculators to handle the order of operations without needing complex parentheses.
- **Syntax Parsing**: Stacks are perfect for balancing symbols. They ensure that every opening bracket has a corresponding closing bracket in the correct order.
- **Memory Management**: The stack is a specific region of RAM used for automatic variable allocation. It is incredibly fast because it only allocates and deallocates memory in strict LIFO order.
# Advantages
- **Time and Memory Efficiency**: Push and pop operations on a stack can be performed in constant time `O(1)`, enabling efficient data access, they are memory-efficient because they only store pushed elements.
# Disadvantages
- **Limited Access**: Elements in a stack can only be accessed from the top, which makes it difficult to retrieve or modify elements in the middle.
- **Potential for Overflow**: Pushing more elements onto a stack that it can hold results in an overflow error, leading to data loss.
# Implementation
See [[Stack Implementation]].
# References
## Articles
- [Stack Data Structure](https://www.geeksforgeeks.org/dsa/stack-data-structure/)
- [Introduction to Stack Data Structure](https://www.geeksforgeeks.org/dsa/introduction-to-stack-data-structure-and-algorithm-tutorials/)
- [Applications of Stack](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-stack/)

[[Basic Data Structures]]