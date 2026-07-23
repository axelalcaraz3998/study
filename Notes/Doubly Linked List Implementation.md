Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Traversal
## Java
```java
class Node {

	int data;
	Node prev;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.prev = null;
		this.next = null;
	}

}

public class Main {

	private static void forwardTraversal(Node head) {
		Node curr = head;
		while (curr != null) {
			if (curr.next != null) {
				System.out.print(curr.data + " <-> ");
			} else {
				System.out.print(curr.data);
			}
			
			curr = curr.next;
		}
		System.out.println("");
	}
	
	private static void backwardTraversal(Node tail) {
		Node curr = tail;
		while (curr != null) {
			if (curr.prev != null) {
				System.out.print(curr.data + " <-> ");
			} else {
				System.out.print(curr.data);
			}
		
			curr = curr.prev;
		}
		System.out.println("");
	}

	public static void main(String[] args) {
		Node head = new Node(1);
		Node second = new Node(2);
		Node third = new Node(3);
		Node fourth = new Node(4);
		Node fifth = new Node(5);
		
		head.next = second;
		second.prev = head;
		second.next = third;
		third.prev = second;
		third.next = fourth;
		fourth.prev = third;
		fourth.next = fifth;
		fifth.prev = fourth;
		
		forwardTraversal(head);
		backwardTraversal(fifth);
	}

}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.prev = None
		self.next = None

def forwardTraversal(head):
	curr = head
	while curr is not None:
		if curr.next is not None:
			print(curr.data, end=" <-> ")
		else:
			print(curr.data, end="")
			
		curr = curr.next
	print("")

def backwardTraversal(tail):
	curr = tail
	while curr is not None:
		if curr.prev is not None:
			print(curr.data, end=" <-> ")
		else:
			print(curr.data, end="")
			
		curr = curr.prev
	print("")

head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)
fifth = Node(5)

head.next = second
second.prev = head
second.next = third
third.prev = second
third.next = fourth
fourth.prev = third
fourth.next = fifth
fifth.prev = fourth

forwardTraversal(head)
backwardTraversal(fifth)
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.prev = null;
		this.next = null;	
	}

}

function forwardTraversal(head) {
	let curr = head;
	while (curr != null) {
		if (curr.next != null) {
			process.stdout.write(curr.data + " <-> ");
		} else {
			process.stdout.write(curr.data.toString());
		}
		
		curr = curr.next;
	}
	console.log("");
}

function backwardTraversal(tail) {
	let curr = tail;
	while (curr != null) {
		if (curr.prev != null) {
			process.stdout.write(curr.data + " <-> ");
		} else {
			process.stdout.write(curr.data.toString());
		}
	
		curr = curr.prev;
	}
	console.log("");
}

let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
let fourth = new Node(4);
let fifth = new Node(5);

head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
third.next = fourth;
fourth.prev = third;
fourth.next = fifth;
fifth.prev = fourth;

forwardTraversal(head);
backwardTraversal(fifth);
```
# Insertion at Beginning
## Java
```java
class Node {

	int data;
	Node prev;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.prev = null;
		this.next = null;
	}

}

public class Main {

	private static Node insertAtBeginning(Node head, int data) {
		Node newNode = new Node(data);
		newNode.next = head;
		head.prev = newNode;
		
		return newNode;
	}

	public static void main(String[] args) {
		Node head = new Node(1);
		Node second = new Node(2);
		Node third = new Node(3);
		Node fourth = new Node(4);
		Node fifth = new Node(5);
		
		head.next = second;
		second.prev = head;
		second.next = third;
		third.prev = second;
		third.next = fourth;
		fourth.prev = third;
		fourth.next = fifth;
		fifth.prev = fourth;
		
		head = insertAtBeginning(head, 10);
	}

}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.prev = None
		self.next = None

def insert_at_beginning(head, data):
	new_node = Node(data)
	new_node.next = head
	head.prev = new_node
	
	return new_node

head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)
fifth = Node(5)

head.next = second
second.prev = head
second.next = third
third.prev = second
third.next = fourth
fourth.prev = third
fourth.next = fifth
fifth.prev = fourth

head = insert_at_beginning(head, 10)
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.prev = null;
		this.next = null;	
	}

}

function insertAtBeginning(head, data) {
	let newNode = new Node(data);
	newNode.next = head;
	head.prev = newNode;
	
	return newNode;
}

let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
let fourth = new Node(4);
let fifth = new Node(5);

head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
third.next = fourth;
fourth.prev = third;
fourth.next = fifth;
fifth.prev = fourth;

head = insertAtBeginning(head, 10);
```
# Insertion at Given Position
## Java
```java
class Node {

	int data;
	Node prev;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.prev = null;
		this.next = null;
	}

}

public class Main {

	private static Node insertAtPosition(Node head, int pos, int data) {
		Node newNode = new Node(data);
		
		if (pos == 1) {
			newNode.next = head;
			head.prev = newNode;
			
			return newNode;
		}
		
		// Traverse to node at pos - 1
		Node curr = head;
		int i = 1;
		while (i < pos - 1 && curr != null) {
			curr = curr.next;
			i++;
		}
		
		newNode.prev = curr;
		newNode.next = curr.next;
		curr.next = newNode;
		
		// Update previous of next node to newNode
		if (newNode.next != null) {
			newNode.next.prev = newNode;
		}
		
		return head;
	}

	public static void main(String[] args) {
		Node head = new Node(1);
		Node second = new Node(2);
		Node third = new Node(3);
		Node fourth = new Node(4);
		Node fifth = new Node(5);
		
		head.next = second;
		second.prev = head;
		second.next = third;
		third.prev = second;
		third.next = fourth;
		fourth.prev = third;
		fourth.next = fifth;
		fifth.prev = fourth;
		
		head = insertAtPosition(head, 3, 10);
	}

}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.prev = None
		self.next = None

def insert_at_position(head, pos, data):
	new_node = Node(data)
	
	if pos == 1:
		new_node.next = head
		head.prev = new_node
		
		return new_node
	
	# Traverse to node at pos - 1
	curr = head
	i = 1
	while i < pos - 1 and curr is not None:
		curr = curr.next
		i = i + 1
	
	new_node.prev = curr
	new_node.next = curr.next
	curr.next = new_node
	
	# Update previous of next node to new_node
	if new_node.next is not None:
		new_node.next.prev = new_node
	
	return head

head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)
fifth = Node(5)

head.next = second
second.prev = head
second.next = third
third.prev = second
third.next = fourth
fourth.prev = third
fourth.next = fifth
fifth.prev = fourth

head = insert_at_position(head, 3, 10)
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.prev = null;
		this.next = null;	
	}

}

function insertAtPosition(head, pos, data) {
	let newNode = new Node(data);
	
	if (pos == 1) {
		newNode.next = head;
		head.prev = newNode;
		
		return newNode;	
	}
	
	// Traverse to node at pos - 1
	let curr = head;
	let i = 1;
	while (i < pos - 1 && curr != null) {
		curr = curr.next;
		i++;
	}
	
	newNode.prev = curr;
	newNode.next = curr.next;
	curr.next = newNode;
	
	// Update previous of next node to newNode
	if (newNode.next != null) {
		newNode.next.prev = newNode;
	}
	
	return head;
}

let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
let fourth = new Node(4);
let fifth = new Node(5);

head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
third.next = fourth;
fourth.prev = third;
fourth.next = fifth;
fifth.prev = fourth;

head = insertAtPosition(head, 3, 10);
```
# Insertion at End
## Java
```java
class Node {

	int data;
	Node prev;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.prev = null;
		this.next = null;
	}

}

public class Main {

	private static Node insertAtEnd(Node head, int data) {
		// Traverse to last node
		Node curr = head;
		while (curr.next != null) {
			curr = curr.next;
		}
		
		Node newNode = new Node(data);
		curr.next = newNode;
		newNode.prev = curr;
		
		return head;
	}

	public static void main(String[] args) {
		Node head = new Node(1);
		Node second = new Node(2);
		Node third = new Node(3);
		Node fourth = new Node(4);
		Node fifth = new Node(5);
		
		head.next = second;
		second.prev = head;
		second.next = third;
		third.prev = second;
		third.next = fourth;
		fourth.prev = third;
		fourth.next = fifth;
		fifth.prev = fourth;
		
		head = insertAtEnd(head, 10);
	}

}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.prev = None
		self.next = None

def insert_at_end(head, data):
	# Traverse to last node
	curr = head
	while curr.next is not None:
		curr = curr.next
		
	new_node = Node(data)
	curr.next = new_node
	new_node.prev = curr
	
	return head

head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)
fifth = Node(5)

head.next = second
second.prev = head
second.next = third
third.prev = second
third.next = fourth
fourth.prev = third
fourth.next = fifth
fifth.prev = fourth

head = insert_at_end(head, 10)
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.prev = null;
		this.next = null;	
	}

}

function insertAtEnd(head, data) {
	// Traverse to last node
	let curr = head;
	while (curr.next != null) {
		curr = curr.next;
	}
	
	let newNode = new Node(data);
	curr.next = newNode;
	newNode.prev = curr;
	
	return head;
}

let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
let fourth = new Node(4);
let fifth = new Node(5);

head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
third.next = fourth;
fourth.prev = third;
fourth.next = fifth;
fifth.prev = fourth;

head = insertAtEnd(head, 10);
```
# Deletion From Beginning
## Java
```java
class Node {

	int data;
	Node prev;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.prev = null;
		this.next = null;
	}

}

public class Main {

	private static Node deleteFromBeginning(Node head) {
		Node temp = head;
		head = head.next;
		head.prev = null;
		temp = null;
		
		return head;
	}

	public static void main(String[] args) {
		Node head = new Node(1);
		Node second = new Node(2);
		Node third = new Node(3);
		Node fourth = new Node(4);
		Node fifth = new Node(5);
		
		head.next = second;
		second.prev = head;
		second.next = third;
		third.prev = second;
		third.next = fourth;
		fourth.prev = third;
		fourth.next = fifth;
		fifth.prev = fourth;
		
		head = deleteFromBeginning(head);
	}

}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.prev = None
		self.next = None

def delete_from_beginning(head):
	temp = head
	head = head.next
	head.prev = None
	temp = None
	
	return head

head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)
fifth = Node(5)

head.next = second
second.prev = head
second.next = third
third.prev = second
third.next = fourth
fourth.prev = third
fourth.next = fifth
fifth.prev = fourth

head = delete_from_beginning(head)
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.prev = null;
		this.next = null;	
	}

}

function deleteFromBeginning(head) {
	let temp = head;
	head = head.next;
	head.prev = null;
	temp = null;
	
	return head;
}

let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
let fourth = new Node(4);
let fifth = new Node(5);

head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
third.next = fourth;
fourth.prev = third;
fourth.next = fifth;
fifth.prev = fourth;

head = deleteFromBeginning(head);
```
# Deletion Of Given Position
## Java
```java
class Node {

	int data;
	Node prev;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.prev = null;
		this.next = null;
	}

}

public class Main {

	private static Node deleteFromPosition(Node head, int pos) {
		Node curr = head;
	
		if (pos == 1) {
			head = head.next;
			head.prev = null;
			curr = null;
			
			return head;
		}
		
		// Traverse to node at pos
		int i = 1;
		while (i < pos && curr != null) {
			curr = curr.next;
			i++;
		}
		
		curr.prev.next = curr.next;
		if (curr.next != null) {
			curr.next.prev = curr.prev;
		}
		curr = null;
		
		return head;
	}

	public static void main(String[] args) {
		Node head = new Node(1);
		Node second = new Node(2);
		Node third = new Node(3);
		Node fourth = new Node(4);
		Node fifth = new Node(5);
		
		head.next = second;
		second.prev = head;
		second.next = third;
		third.prev = second;
		third.next = fourth;
		fourth.prev = third;
		fourth.next = fifth;
		fifth.prev = fourth;
		
		head = deleteFromPosition(head, 3);
	}

}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.prev = None
		self.next = None

def delete_from_position(head, pos):
	curr = head
	
	if pos == 1:
		head = head.next
		head.prev = None
		curr = None
		
		return head
	
	# Traverse to node at pos
	i = 1
	while i < pos and curr is not None:
		curr = curr.next
		i = i + 1
	
	curr.prev.next = curr.next
	if curr.next is not None:
		curr.next.prev = curr.prev
	curr = None
	
	return head

head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)
fifth = Node(5)

head.next = second
second.prev = head
second.next = third
third.prev = second
third.next = fourth
fourth.prev = third
fourth.next = fifth
fifth.prev = fourth

head = delete_from_position(head, 3)
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.prev = null;
		this.next = null;	
	}

}

function deleteFromPosition(head, pos) {
	let curr = head;
	
	if (pos == 1) {
		head = head.next;
		head.prev = null;
		temp = null;
		
		return head;
	}
	
	// Traverse to node at pos
	let i = 1;
	while (i < pos && curr != null) {
		curr = curr.next;
		i++;
	}
	
	curr.prev.next = curr.next;
	if (curr.next != null) {
		curr.next.prev = curr.prev;
	}
	curr = null;
	
	return head;
}

let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
let fourth = new Node(4);
let fifth = new Node(5);

head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
third.next = fourth;
fourth.prev = third;
fourth.next = fifth;
fifth.prev = fourth;

head = deleteFromPosition(head, 3);
```
# Deletion From End
## Java
```java
class Node {

	int data;
	Node prev;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.prev = null;
		this.next = null;
	}

}

public class Main {

	private static Node deleteFromEnd(Node head) {
		// Traverse to last node
		Node curr = head;
		while (curr.next != null) {
			curr = curr.next;
		}
		
		curr.prev.next = null;
		curr = null;
		
		return head;
	}

	public static void main(String[] args) {
		Node head = new Node(1);
		Node second = new Node(2);
		Node third = new Node(3);
		Node fourth = new Node(4);
		Node fifth = new Node(5);
		
		head.next = second;
		second.prev = head;
		second.next = third;
		third.prev = second;
		third.next = fourth;
		fourth.prev = third;
		fourth.next = fifth;
		fifth.prev = fourth;
		
		head = deleteFromEnd(head);
	}

}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.prev = None
		self.next = None

def delete_from_end(head):
	# Traverse to last node
	curr = head
	while curr.next is not None:
		curr = curr.next
	
	curr.prev.next = None
	curr = None
	
	return head

head = Node(1)
second = Node(2)
third = Node(3)
fourth = Node(4)
fifth = Node(5)

head.next = second
second.prev = head
second.next = third
third.prev = second
third.next = fourth
fourth.prev = third
fourth.next = fifth
fifth.prev = fourth

head = delete_from_end(head)
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.prev = null;
		this.next = null;	
	}

}

function deleteFromEnd(head) {
	// Traverse to last node
	let curr = head;
	while (curr.next != null) {
		curr = curr.next;
	}
	
	curr.prev.next = null;
	curr = null;
	
	return head;
}

let head = new Node(1);
let second = new Node(2);
let third = new Node(3);
let fourth = new Node(4);
let fifth = new Node(5);

head.next = second;
second.prev = head;
second.next = third;
third.prev = second;
third.next = fourth;
fourth.prev = third;
fourth.next = fifth;
fifth.prev = fourth;

head = deleteFromEnd(head);
```
# References
## Articles
- [Doubly Linked List](https://www.geeksforgeeks.org/dsa/doubly-linked-list/)

[[Linked List]]