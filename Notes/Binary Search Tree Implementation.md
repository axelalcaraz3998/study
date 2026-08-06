Tags: #ComputerScience #DSA #Java #Python #JavaScript  
# Java
```java
class Node {
	
	int data;
	Node left;
	Node right;
	
	public Node(int data) {
		this.data = data;
		this.left = null;
		this.right = null;
	}
	
}

class BinarySearchTree {
	
	Node root;
	
	public BinarySearchTree() {
		root = null;
	}
	
	public void insert(Node node) {
		root = insertHelper(root, node);
	}
	
	public void display() {
		displayHelper(root);
	}
	
	public boolean search(int data) {
		return searchHelper(root, data);
	}
	
	public void remove(int data) {
		if (search(data)) {
			root = removeHelper(root, data);
		}
	}
	
	private Node insertHelper(Node root, Node node) {
		if (root == null) {
			root = node;
			return root;
		}
		
		if (node.data < root.data) {
			root.left = insertHelper(root.left, node);
		} else {
			root.right = insertHelper(root.right, node);
		}
		
		return root;
	}
	
	private void displayHelper(Node root) {
		if (root == null) {
			return;
		}
		
		displayHelper(root.left);
		System.out.print(root.data + " ");
		displayHelper(root.right);
	}
	
	private boolean searchHelper(Node root, int data) {
		if (root == null) {
			return false;
		}
		
		if (root.data == data) {
			return true;
		}
		
		if (root.data > data) {
			return searchHelper(root.left, data);
		} else {
			return searchHelper(root.right, data);
		}
	}
	
	private Node removeHelper(Node root, int data) {
		if (root == null) {
			return root;
		}
		
		if (data < root.data) {
			root.left = removeHelper(root.left, data);
		} else if (data > root.data) {
			root.right = removeHelper(root.right, data);
		} else {
			if (root.left == null && root.right == null) {
				return null;
			} 
			
			if (root.right != null) {
				root.data = successor(root);
				root.right = removeHelper(root.right, root.data);
			} else if (root.left != null) {
				root.data = predecessor(root);
				root.left = removeHelper(root.left, root.data);
			}		
		}
		
		return root;
	}
	
	private int successor(Node root) {
		root = root.right;
		while (root.left != null) {
			root = root.left;
		}
		
		return root.data;
	}
	
	private int predecessor(Node root) {
		root = root.left;
		while (root.right != null) {
			root = root.right;
		}
		
		return root.data;
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		BinarySearchTree tree = new BinarySearchTree();
		
		tree.insert(new Node(5));
		tree.insert(new Node(1));
		tree.insert(new Node(9));
		tree.insert(new Node(7));
		tree.insert(new Node(3));
		tree.insert(new Node(6));
		tree.insert(new Node(4));
		tree.insert(new Node(8));
		
		tree.display();
		
		System.out.println("");
		System.out.println(tree.search(7));
		System.out.println(tree.search(8));
		System.out.println(tree.search(9));
		System.out.println(tree.search(0));
		System.out.println(tree.search(-5));
		
		tree.remove(5);
		tree.remove(9);
		tree.remove(4);
		
		tree.display();
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

class BinarySearchTree:
	def __init__(self):
		self.root = None
	
	def insert(self, node):
		self.root = self.__insert_helper(self.root, node)
	
	def display(self):
		self.__display_helper(self.root)
	
	def search(self, data):
		return self.__search_helper(self.root, data)
	
	def remove(self, data):
		if self.search(data) is True:
			self.root = self.__remove_helper(self.root, data)
	
	def __insert_helper(self, root, node):
		if root is None:
			root = node
			return root
		
		if node.data < root.data:
			root.left = self.__insert_helper(root.left, node)
		else:
			root.right = self.__insert_helper(root.right, node)
		
		return root
	
	def __display_helper(self, root):
		if root is None:
			return
		
		self.__display_helper(root.left)
		print(root.data, end=" ")
		self.__display_helper(root.right)
	
	def __search_helper(self, root, data):
		if root is None:
			return False
		
		if root.data == data:
			return True
		
		if data < root.data:
			return self.__search_helper(root.left, data)
		else:
			return self.__search_helper(root.right, data)
	
	def __remove_helper(self, root, data):
		if root is None:
			return root
		
		if data < root.data:
			root.left = self.__remove_helper(root.left, data)
		elif data > root.data:
			root.right = self.__remove_helper(root.right, data)
		else:
			if root.left is None and root.right is None:
				return None
			
			if root.right is not None:
				root.data = self.__successor(root)
				root.right = self.__remove_helper(root.right, root.data)
			elif root.left is not None:
				root.data = self.__predecessor(root)
				root.left = self.__remove_helper(root.left, root.data)
		
		return root
	
	def __successor(self, root):
		root = root.right
		while root.left is not None:
			root = root.left
		
		return root.data
	
	def __predecessor(self, root):
		root = root.left
		while root.right is not None:
			root = root.right
		
		return root.data

tree = BinarySearchTree()
tree.insert(Node(5))
tree.insert(Node(1))
tree.insert(Node(9))
tree.insert(Node(7))
tree.insert(Node(3))
tree.insert(Node(6))
tree.insert(Node(4))
tree.insert(Node(8))

tree.display()

print("")
print(tree.search(7))
print(tree.search(8))
print(tree.search(9))
print(tree.search(0))
print(tree.search(-5))

tree.remove(5)
tree.remove(9)
tree.remove(4)

tree.display()
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

class BinarySearchTree {
	
	constructor() {
		this.root = null;
	}
	
	insert(node) {
		this.root = this.#insertHelper(this.root, node);
	}
	
	display() {
		this.#displayHelper(this.root);
	}
	
	search(data) {
		return this.#searchHelper(this.root, data);
	}
	
	remove(data) {
		if (this.search(data)) {
			this.#removeHelper(this.root, data);
		}
	}
	
	#insertHelper(root, node) {
		if (root == null) {
			root = node;
			return node;
		}
		
		if (node.data < root.data) {
			root.left = this.#insertHelper(root.left, node);
		} else {
			root.right = this.#insertHelper(root.right, node);
		}
		
		return root;
	}
	
	#displayHelper(root) {
		if (root == null) {
			return;
		}
		
		this.#displayHelper(root.left);
		process.stdout.write(root.data + " ");
		this.#displayHelper(root.right);
	}
	
	#searchHelper(root, data) {
		if (root == null) {
			return false;
		}
		
		if (data == root.data) {
			return true;
		}
		
		if (data < root.data) {
			return this.#searchHelper(root.left, data);
		} else {
			return this.#searchHelper(root.right, data);
		}
	}
	
	#removeHelper(root, data) {
		if (root == null) {
			return root;
		}
		
		if (data < root.data) {
			root.left = this.#removeHelper(root.left, data);
		} else if (data > root.data) {
			root.right = this.#removeHelper(root.right, data);
		} else {
			if (root.left == null && root.right == null) {
				return null;
			}
			
			if (root.right != null) {
				root.data = this.#successor(root);
				root.right = this.#removeHelper(root.right, root.data);
			} else if (root.left != null) {
				root.data = this.#predecessor(root);
				root.left = this.#removeHelper(root.left, root.data);
			}
		}
		
		return root;
	}
	
	#successor(root) {
		root = root.right;
		while (root.left != null) {
			root = root.left;
		}
		
		return root.data;
	}
	
	#predecessor(root) {
		root = root.left;
		while (root.right != null) {
			root = root.right;
		}
		
		return root.data;
	}
	
}

let tree = new BinarySearchTree();

tree.insert(new Node(5));
tree.insert(new Node(1));
tree.insert(new Node(9));
tree.insert(new Node(7));
tree.insert(new Node(3));
tree.insert(new Node(6));
tree.insert(new Node(4));
tree.insert(new Node(8));

tree.display();

console.log("");
console.log(tree.search(7));
console.log(tree.search(8));
console.log(tree.search(9));
console.log(tree.search(0));
console.log(tree.search(-5));

tree.remove(5);
tree.remove(9);
tree.remove(4);

tree.display();
```
# References
## Articles
- [DSA Binary Search Trees](https://www.w3schools.com/dsa/dsa_data_binarysearchtrees.php)
## Videos
- [Learn Binary Search Tree in 20 minutes](https://www.youtube.com/watch?v=Gt2yBZAhsGM)

[[Binary Search Tree]]