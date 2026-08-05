Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Post-Order Traversal visits the nodes in the order: Left -> Right -> Root.
- Traverse left subtree.
- Traverse right subtree.
- Visit root.
![[post-order-traversal.png]]
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
		traverseTree(root.right);
		System.out.print(root.data + " ");
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
	traverseTree(root.right)
	print(root.data, end=" ")

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
	traverseTree(root.right);
	process.stdout.write(root.data + " ");
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