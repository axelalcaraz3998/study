Tags: #ComputerScience #DSA #Java #Python #JavaScript 

In-Order Traversal visits the nodes in the order: Left -> Root -> Right.
- Traverse left subtree.
- Visit root.
- Traverse right subtree.
![[in-order-traversal.webp]]
# Java
```java
class Node {
	
	int data;
	Node left;
	Node right;
	
	public Node(int data) {
		this.data = data;
	}
	
}

public class Main {
	
	private static void traverseTree(Node root) {
		// Base condition
		if (root == null) {
			return;
		}
		
		traverseTree(root.left);
		System.out.print(root.data + " ");
		traverseTree(root.right);
	}
	
	public static void main(String[] args) {
		Node root = new Node(1);
		root.left = new Node(2);
		root.right = new Node(3);
		root.left.left = new Node(4);
		root.left.right = new Node(5);
		root.right.left = new Node(6);
		root.right.right = new Node(7);
		
		traverseTree(root);
	}
	
}
```
# Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.left = None
		self.right = None

def traverseTree(root):
	# Base condition
	if root is None:
		return
	
	traverseTree(root.left)
	print(root.data, end=" ")
	traverseTree(root.right)

root = Node(1)
root.left = Node(2);
root.right = Node(3);
root.left.left = Node(4);
root.left.right = Node(5);
root.right.left = Node(6);
root.right.right = Node(7);

traverseTree(root)
```
# JavaScript
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.left = null;
		this.right = null;
	}
	
}

function traverseTree(root) {
	// Base condition
	if (root == null) {
		return;
	}
	
	traverseTree(root.left);
	process.stdout.write(root.data + " ");
	traverseTree(root.right);
}

let root = new Node(1);
root.left = new Node(2);
root.right = new Node(3);
root.left.left = new Node(4);
root.left.right = new Node(5);
root.right.left = new Node(6);
root.right.right = new Node(7);

traverseTree(root);
```
# References
## Articles
- [Tree Traversal Techniques](https://www.geeksforgeeks.org/dsa/tree-traversals-inorder-preorder-and-postorder/)
## Videos
- [Learn Tree traversal in 3 minutes](https://www.youtube.com/watch?v=b_NjndniOqY)

[[Tree Data Structure]]