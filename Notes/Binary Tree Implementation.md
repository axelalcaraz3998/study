Tags: #ComputerScience #DSA #Java #Python #JavaScript 
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
	
	public static void main(String[] args) {
		Node root = new Node(1);
		root.left = new Node(2);
		root.right = new Node(3);
		root.left.left = new Node(4);
		root.left.right = new Node(5);
		root.right.left = new Node(6);
		root.right.right = new Node(7);
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

root = Node(1)
root.left = Node(2);
root.right = Node(3);
root.left.left = Node(4);
root.left.right = Node(5);
root.right.left = Node(6);
root.right.right = Node(7);
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

let root = new Node(1);
root.left = new Node(2);
root.right = new Node(3);
root.left.left = new Node(4);
root.left.right = new Node(5);
root.right.left = new Node(6);
root.right.right = new Node(7);
```
# References
## Articles
- [Introdution to Binary Tree](https://www.geeksforgeeks.org/dsa/introduction-to-binary-tree/)

[[Binary Tree]]