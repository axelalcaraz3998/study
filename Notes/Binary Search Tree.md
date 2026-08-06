Tags: #ComputerScience #DSA 

A binary search tree is a type of binary tree in which each node contains an unique key and satisfies a specific ordering property:
- All nodes in the left subtree of a node contain values strictly less than the node's value.
- All nodes in the right subtree of a node contain values strictly greater than the node's value.
This structure enables efficient operations for searching, insertion, and deletion of elements, specially when the tree remains balanced.
![[binary-search-tree.webp]]
# Properties
- Unique ordering of elements means duplicates are usually not allowed.
- Inorder traversal of BST gives sorted order of elements.
- Average height is `O(log n)` for balanced BST.
- Worst case height is `O(n)`.
# Applications
- BST are used to maintain sorted stream of data.
- A Self-Balancing Binary Search Tree is used to implement double ended priority queue.
- BST can be used to sort large datasets.
- Variations of BST, like B trees and B+ trees are used in database indexing.
- TreeMap and TreeSet in Java, aswell as set and map in C++, are internally implemented using Self-Balancing Binary Search Trees.
# Advantages
- **Efficient Searching**: `O(log n)` time complexity for searching with a Self-Balancing Binary Search Tree.
- **Ordered Structure**: Elements are stored in sorted order, making it easy to find the next or previous element.
- **Dynamic Insertion and Deletion**: Elements can be added or removed efficiently.
- **Balanced Structure**: Balanced BSTs maintain a logarithmic height, ensuring efficient operations.
# Disadvantages
- **Not Self Balancing**: Unbalanced BST can lead to poor performance.
- **Wors-Case Time Complexity**: In the worst case, BST can have a linear time complexity for searching and insertion.
- **Memory Overhead**: BST require additional memory to store pointers to child nodes.
- **Not Suitable for Large Datasets**: BST can become inefficient for very large datasets.
- **Limited Functionality**: BST only support searching, insertion, and deletion operations.
# Implementation
See [[Binary Search Tree Implementation]].
# References
## Articles
- [Binary Search Tree](https://www.geeksforgeeks.org/dsa/binary-search-tree-data-structure/)
- [Introduction to Binary Search Tree](https://www.geeksforgeeks.org/dsa/introduction-to-binary-search-tree/)

[[Tree Data Structure]]