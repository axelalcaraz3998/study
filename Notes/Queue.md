Tags: #ComputerScience #DSA 

A queue is a linear data structure that follows the FIFO (First In First Out) principle. The element inserted first is the first one to be removed.
![[queue.webp]]
# The FIFO (First In First Out) Principle
The FIFO principle states that the first element added to the queue will be the first to be removed. So, a queue is like a line of people waiting to purchase tickets, where the first person in line is the first person served.
# Types of Queue
## Simple Queue
A simple queue follows the FIFO principle.
- Insertion is allowed only at the rear.
- Deletion is allowed only from the front.
- Can be implemented using a linked list or a circular array.
## Double-Ended Queue (Deque)
In a deque, insertion and deletion can be performed from both ends.
## Priority Queue
A queue where each element is assigned a priority, and deletion always happens based on priority (not just position).
# Common Operations
- **Enqueue**: Adds an element to the end of the queue. If queue is full an overflow occurs.
- **Dequeue**: Removes the element from the front of the queue. If the queue is empty an underflow occurs.
- **Peek**: Returns the element at the front of the queue without removing it.
- **Size**: Returns the number of elements in the queue.
# Applications
- **Job Scheduling**: These jobs are assigned to the processor one by one which are organized using a queue.
- **Buffer Management**: Working as a buffer between a slow and a fast device. For example, keyboard and CPU.
# Advantages
- Queues are useful when a particular service is used by multiple consumers.
- Queues are fast in speed for data inter-process communication.
- Queues can be used for the implementation of other data structures.
# Disadvantages
- Operations such as insertion and deletion of elements from the middle are time consuming.
- Searching elements takes linear time `O(n)`.
- Maximum size of a queue must be defined prior, in the case of the array implementation.
# Implementation
See [[Queue Implementation]].
# References
## Articles
- [Queue Introduction](https://www.geeksforgeeks.org/dsa/introduction-to-queue-data-structure-and-algorithm-tutorials/)
- [Applications, Advantages and Disadvantages of Queue](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-queue/)

[[Basic Data Structures]]