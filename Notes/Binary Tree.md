Tags: #ComputerScience #DSA 

A binary tree is a hierarchical data structure in which each node has at most two childre, referred to as the left child and the right child.
![[binary-tree.webp]]
# Properties
- The maximum number of nodes at level `L` of a binary tree is `2^L`.
- The maximum number of nodes in a binary tree of height `H` is `2^(H+1)-1`.
- Total number of leaf nodes in a binary tree is equal to number of nodes with 2 children + 1.
- In a binary tree with `N` nodes, the minimum possible height is `log2 N`.
- A binary tree with `L` leaves has at least `log2 L + 1` levels.
# Applications
- Binary tree can be used to represent hierarchical data.
- Huffman coding trees are used in data compression algorithms.
- Binary trees are used to implement decision trees.
# Advantages
- **Efficient Search**: Binary search trees are efficient when searching for a specific element, as each node has at most two children when compared to linked list and arrays.
- **Memory Efficient**: Binary trees require lesser memory as compared to other tree data structures.
- **Easy to Implement**: Binary trees are relatively easy to implement and understand as each node has at most two children.
# Disadvantages
- **Limited Structure**: Binary trees are limited to two child nodes per node, which can limit their usefulness in certain applications.
- **Space Inefficient**: Binary trees can be space inefficient when compared to other data structures like arrays and linked list. This is because each node requires two child references pointers.
# Implementation
See [[Binary Tree Implementation]].
# References
## Articles
- [Binary Tree Data Structure](https://www.geeksforgeeks.org/dsa/binary-tree-data-structure/)

[[Tree Data Structure]]