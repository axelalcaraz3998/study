Tags: #ComputerScience #DSA 

An AVL Tree is defined as a self-balancing Binary Search Tree where the difference between the heights of left and right subtrees for any node cannot be more than one.

In an AVL Tree, each node maintains a balance factor, which represents the difference in heights between the left and right subtrees. The tree is considered balanced when the balance factor is -1, 0, or +1, and no rebalancing is required. However, if the balance factor deviates from these three values, the tree needs to be rebalanced.
![[avl-tree.webp]]
# Important Points About AVL Trees
- **Rotations**: rotations are designed to restore balance in `O(1)` time while ensuring the overall time complexity remains `O(log n)`. AVL Trees use four cases to rebalance themselves after insertions and deletions. Left-Left (LL), Right-Right (RR), Left-Right (LR), Right-Left (RL).
- **Insertion and Deletion**: While insertion is followed by upwards traversals to check balance and apply rotations, deletions can be more complex due to multiple rotations possibly being required. AVL Trees may required multiple rebalancing steps during deletion, unlike Red-Black Trees which limits this better.
# Rotations
## Left-Left (LL) Rotation
Occurs when a node is inserted into the left subtree of the left child, causing the balance factor to become more than +1.
![[avl-tree-left-left.webp]]
## Right-Right (RR) Rotation
Occurs when a node is inserted into the right subtree of the right child, making the balance factor less than -1.
![[avl-tree-right-right.webp]]
## Left-Right (LR) Rotation
Occurs when a node is inserted into the right subtree of a left child node, which disturbs the balance factor of an ancestor node, making it left-heavy.
![[avl-tree-left-right-1.webp]]

![[avl-tree-left-right-2.webp]]
## Right-Left (RL) Rotation
Occurs when a node is inserted into the left subtree of the right child node, which disturbs the balance factor of an ancestor node, making it right-heavy.
![[avl-tree-right-left-1.webp]]

![[avl-tree-right-left-2.webp]]
# Applications
- Used when insertions and deletions are less common but frequent data lookups along with other operations of BST like sorted traversal, floor, ceil, min, max, etc.
- AVL Trees can be used in a real time environment where predictable and consistent performance is required.
# Advantages
- AVL Trees can self-balance themselves and therefore provide time complexity of `O(log n)` for operations such as search, insert, and delete.
- Items can be traversed in sorted order.
- AVL Trees are less complex than Red-Black Trees.
# Disadvantages
- Difficult to implement compared to a normal BST.
- Less used compared to Red-Black Trees.
# References
## Articles
- [AVL Tree Data Structure](https://www.geeksforgeeks.org/dsa/introduction-to-avl-tree/)
- [DSA AVL Trees](https://www.w3schools.com/dsa/dsa_data_avltrees.php)
- [AVL Tree](https://medium.com/@ozgurmehmetakif/avl-tree-665476662bf3)
## Videos
- [AVL Tree Explained](https://www.youtube.com/watch?v=1BSj3crVaG4)

[[Tree Data Structure]]