Tags: #ComputerScience #DSA 

A tree is a hierarchical data structure used to organize and represent data in a parent-child relationship. It consists of nodes, where the topmost node is called the root, and every other node can have one or more child nodes.
![[tree-data-structure.webp]]
# Basic Terminology
- **Parent Node**: A node that is an immediate predecessor of another node.
- **Child Node**: A node that is an immediate successor of another node.
- **Root Node**: The topmost node in a tree, which does not have a parent.
- **Leaf Node**: Node that don't have any children.
- **Ancestor**: Any node on the path from the root to a given node (excluding the node itself).
- **Descendant**: A node `x` in a descendant of another node `y` if `y` is an ancestor of `x`.
- **Sibling**: Nodes that share the same parent.
- **Level of a Node**: The number of edges in the path from the root to that node.
- **Internal Node**: A node with at least one child.
- **Neighbor of a Node**: The parent or children of a node.
- **Subtree**: A node and all its descendants from a subtree.
# Properties
- **Number of Edges**: An edge is the connection between two nodes. A tree with `N` nodes will always have `N-1` edges.
- **Depth of a Node**: The depth of a node is the length of the path from the root to that node. Each edge in the path adds 1 unit to the length.
- **Height of the Tree**: The height of the tree is the length of the longest path from the root to any leaf node.
- **Degree of a Node**: The degree of a node is the number of subtrees attached to it. A leaf node has a degree of 0.
# Types of Trees
## Binary Tree
Each node can have a maximum of two children.

See [[Binary Tree]].
## Binary Search Tree
For each node, the left child hasa lower value, and the right child has a higher value.

See [[Binary Search Tree]].
## AVL Tree
A type of binary search tree that self-balances so that for every node, the difference in height between the left and right subtrees is at most one.
## Heap
Each parent node is always bigger or smaller than its child nodes.
# Tree Traversal
Tree traversal refers to the process of visiting nodes of a tree in a specific order.
## In-Order Traversal
Visits the nodes in the order: Left -> Root -> Right.

See [[In-Order Traversal]].
## Pre-Order Traversal
Visits the nodes in the order: Root -> Left -> Right.

See [[Pre-Order Traversal]].
## Post-Order Traversal
Visits the nodes in the order: Left -> Right -> Root.

See [[Post-Order Traversal]].
# Applications
- Trees are useful for storing data that naturally forms a hierarchy.
- File systems on computers are structured as trees, with folders containing subfolders and files.
- The DOM (Document Object Model) of an HTML page is a tree.
- Trees help in efficient data organization and retrieval of hierarchical relationships.
# References
## Articles
- [Introduction to Tree Data Structure](https://www.geeksforgeeks.org/dsa/introduction-to-tree-data-structure/)
## Videos
- [Tree Data Structure](https://www.youtube.com/watch?v=S2W3SXGPVyU)

[[Data Structures and Algorithms MOC]]