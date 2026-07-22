Tags: #ComputerScience #DSA 

A linked list is a linear data structure, similar to an array, but with a key difference: elements in a linked list are not stored at contiguous memory locations. Instead, each element, or node, contains a reference, or pointer, to the next node in the sequence.

A linked list has the following characteristics:
- **Nodes**: Each node contains two fields; data and a reference to the next node.
- **Head**: The first node in the list, which acts as an entry point to the list.
- **Tail**: The last node in the list, which typically points to `null`, indicating the end of the list.
![[linked-list.webp]]
# Types of Linked Lists
- **Singly Linked List**: Each node points to the next node in the sequence, and the last node points to `null`.
![[singly-linked-list.webp]]
- **Doubly Linked List**: Each node has two pointers, one to the next node and one to the previous node. This allows for bidirectional traversal.
![[doubly-linked-list.webp]]
- **Circular Linked List**: In this type, the last node points back to the head, forming a circle.
![[circular-linked-list.webp]]
# Linked List vs Arrays
At first glance, arrays and linked list seem similar, but they differ significantly in memory structure and operation efficiency.
## Memory Management
- **Array**: In an array, elements are stored in contiguous memory locations. This makes accessing an element by index very fast, with constant time complexity `O(1)`. However, the size of the array must be defined in advance. If the array fills up, resizing, usually involving copying the entire array to a new memory location, is required.
- **Linked List**: Elements in a linked list are stored in different memory locations, linked by pointers. You can add or remove nodes easily without worrying about resizing. Since linked lists dynamically allocate memory, the size is flexible, growing and shrinking as needed.
## Insertions and Deletions
- **Array**: Inserting and deleting elements in the middle of an array is inefficient because it requires shifting elements to maintain contiguous memory. This leads to a time complexity of `O(n)`.
- **Linked List**: In a linked list, inserting or deleting nodes is much faster because it only involves changing pointers, making the time complexity for insertions and deletions `O(1)`, assuming you already have a reference to the node before the one you're modifying.
## Access Speed
- **Array**: Arrays provide constant-time access `O(1)` to elements by index.
- **Linked List**: Linked lists require linear time `O(n)` to access an element, as you need to traverse the list from the head to the desired node.
# Applications
- Linked lists can be used to implement stacks, queues, dequeues, sparse matrices, and adjacency list representation of graphs.
- Dynamic memory allocation in operating systems and compilers (linked list of free blocks).
- Arithmetic operation on long integers.
- Process scheduling (round robin scheduling) and file systems.
- LRU cache, which uses a doubly linked list to keep track of the most recently used items in a cache.
- The list of songs in a music player's playlist.
- Previous and next web pages in web browsers.
# Advantages
- Linked lists are mostly used because of their effective insertion and deletion and only take `O(1)` time.
- More space efficient compared to arrays in cases where we cannot guess the number of elements in advance.
# Disadvantages
- **Slow Access Time**: Accessing elements in a linked list can be slow, as you need to traverse the linked list to find the element you are looking for, which is an `O(n)` operation.
- **Pointers or References**: Linked lists use pointers to access the next node, which can make them more complex to understand and use compared to arrays.
- **Higher Overhead**: Linked lists have a higher overhead compared to arrays, as each node in a linked list requires extra memory to store the reference to the next node.
- **Cache Inefficiency**: Linked lists are cache-inefficient because the memory is not contiguous. This means that when you traverse a linked list, you are not likely to get the data you need in the cache, leading to cache misses and slow performance.
# Linked List Implementation
## Singly Linked List
See [[Singly Linked List Implementation]].
## Doubly Linked List
See [[Doubly Linked List Implementation]].
## Circular Linked List
See [[Circular Linked List Implementation]].
# References
## Articles
- [Linked List Data Structure](https://www.geeksforgeeks.org/dsa/linked-list-data-structure/)
- [Understanding Linked Lists: A Beginner's Guide](https://medium.com/@ogundipe.eniola/understanding-linked-lists-a-beginners-guide-a7ca6aa6ee04)
- [Applications, Advantages and Disadvantages of Linked List](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-linked-list/)

[[Basic Data Structures]]