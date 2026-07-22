Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Java
## Traversal
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static void traversalIterative(Node head) {
		Node temp = head;
		while (temp != null) {
			System.out.print(temp.data);
			if (temp.next != null) {
				System.out.print(" -> ");
			}
			
			temp = temp.next;
		}
		
		System.out.println("");
	}
	
	private static void traversalRecursive(Node head) {
		if (head == null) {
			System.out.println("");
			return;
		}
		
		System.out.print(head.data);
		if (head.next != null) {
			System.out.print(" -> ");
		}
		
		traversalRecursive(head.next);
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		traversalIterative(head);
		traversalRecursive(head);
	}

}
```
## Insertion at Beginning
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static Node insertAtBeginning(Node head, int x) {
		// Insert at beginning
		Node newNode = new Node(x);
		newNode.next = head;
		return newNode;		
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		head = insertAtBeginning(head, 10);
	}

}
```
## Insertion at Given Position
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static Node insertAtPosition(Node head, int pos, int x) {
		// If position is 1 insert at beginning
		if (pos == 1) {
			Node newNode = new Node(x);
			newNode.next = head;
			return newNode;
		}
		
		// Traverse to node at pos - 1
		int i = 1;
		Node current = head;
		while (i < pos - 1 && current != null) {
			current = current.next;
			i++;
		}
		
		// Append node
		Node newNode = new Node(x);
		newNode.next = current.next;
		current.next = newNode;
		
		return head;
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		head = insertAtPosition(head, 3, 10);
	}

}
```
## Insertion at End
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static Node insertAtEnd(Node head, int x) {
		// Traverse to last node
		Node current = head;
		while (current.next != null) {
			current = current.next;
		}
		
		// Append node
		Node newNode = new Node(x);
		current.next = newNode;
		
		return head;
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		head = insertAtEnd(head, 10);
	}

}
```
## Deletion From Beginning
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static Node deleteFromBeginning(Node head) {
		Node temp = head;
		head = head.next;
		// Free memory from old head node
		temp = null;
		
		return head;
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		head = deleteFromBeginning(head);
	}

}
```
## Deletion From Given Position
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static Node deleteFromPosition(Node head, int pos) {
		Node temp = head;
	
		// If position 1 delete from beginning
		if (pos == 1) {
			head = temp.next;
			temp = null;
			
			return head;
		}
		
		// Traverse to the node at position - 1
		Node prev = null;
		for (int i = 1; i < pos; i++) {
			prev = temp;
			temp = temp.next;
		}
		
		prev.next = temp.next; 
		temp = null;
		
		return head;
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		head = deleteFromPosition(head, 3);
	}

}
```
## Deletion From End
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static Node deleteFromEnd(Node head) {
		// If list is empty or only has one node
		if (head == null || head.next == null) {
			return null;
		}
		
		// Find second to last node
		Node current = head;
		while (current.next.next != null) {
			current = current.next;
		}
		// Delete last node
		current.next = null;
		
		return head;
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		head = deleteFromEnd(head);
	}

}
```
## Reverse List
```java
class Node {

	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}

}

public class Main {

	private static Node reverseList(Node head) {
		Node current = head;
		Node prev = null;
		Node next = null;
		
		while (current != null) {
			next = current.next;
			current.next = prev;
			
			prev = current;
			current = next;
		}
		
		return prev;
	}

	public static void main(String[] args) {
		// Head node
		Node head = new Node(1);
		// Second node
		head.next = new Node(2);
		// Third node
		head.next.next = new Node(3);
		// Fourth node
		head.next.next.next = new Node(4);
		// Fifth node
		head.next.next.next.next = new Node(5);
		
		head = reverseList(head);
	}

}
```
# Python
## Traversal
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None
		
def traversal_iterative(head):
	temp = head;
	while temp is not None:
		print(temp.data, end="")
		if temp.next is not None:
			print(" -> ", end="")
		
		temp = temp.next
	
	print("")

def traversal_recursive(head):
	if head is None:
		print("")
		return
		
	print(head.data, end="")
	if (head.next is not None):
		print(" -> ", end="")
		
	traversal_recursive(head.next)
	
# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

traversal_iterative(head)
traversal_recursive(head)
```
## Insertion at Beginning
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None
		
def insert_at_beginning(head, x):
	# Insert at beginning
	newNode = Node(x)
	newNode.next = head
	return newNode

# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3)
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

head = insert_at_beginning(head, 10)
```
## Insertion at Given Position
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None

def insert_at_position(head, pos, x):
	# If position is 1 insert at beginning
	if pos == 1:
		newNode = Node(x)
		newNode.next = head
		return newNode
	
	# Traverse to node at position - 1
	i = 1
	current = head
	while (i < pos - 1 and current is not None):
		current = current.next
		i = i + 1
		
	# Append new node
	newNode = Node(x)
	newNode.next = current.next
	current.next = newNode
	
	return head

# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3)
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

head = insert_at_position(head, 3, 10)
```
## Insertion at End
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None

def insert_at_end(head, x):
	# Traverse to last node
	current = head
	while (current.next is not None):
		current = current.next

	# Append new node
	newNode = Node(x)
	current.next = newNode
	
	return head

# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3)
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

head = insert_at_end(head, 10)
```
## Deletion From Beginning
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None
		
def delete_from_beginning(head):
	temp = head
	head = head.next
	# Free memory from old head node
	temp = None
	
	return head

# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3)
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

head = delete_from_beginning(head)
```
## Deletion From Given Position
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None
		
def delete_from_position(head, pos):
	temp = head
	
	# If position 1 delete from beginning
	if pos == 1:
		head = temp.next
		temp = None
		
		return head
	
	# Traverse to the node at position - 1
	prev = None
	for i in range(1, pos):
		prev = temp
		temp = temp.next
		
	prev.next = temp.next
	temp = None
	
	return head

# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3)
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

head = delete_from_position(head, 3)
```
## Deletion From End
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None
		
def delete_from_end(head):
	# If list is empty or only has one node
	if head is None or head.next is None:
		return None
	
	# Find second to last node
	current = head
	while (current.next.next is not None):
		current = current.next

	# Delete last node
	current.next = None
	
	return head

# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3)
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

head = delete_from_end(head)
```
## Reverse List
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None
		
def reverse_list(head):
	current = head
	prev = None
	next = None
	
	while (current is not None):
		next = current.next
		current.next = prev
		
		prev = current
		current = next
		
	return head

# Head node
head = Node(1)
# Second node
head.next = Node(2)
# Third node
head.next.next = Node(3)
# Fourth node
head.next.next.next = Node(4)
# Fifth node
head.next.next.next.next = Node(5)

head = reverse_list(head)
```
# JavaScript
## Traversal
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function traversalIterative(head) {
	let temp = head;
	while (temp != null) {
		process.stdout.write(temp.data.toString());
		if (temp.next != null) {
			process.stdout.write(" -> ");
		}
		
		temp = temp.next;
	}
	
	console.log("");
}

function traversalRecursive(head) {
	if (head == null) {
		console.log("");
		return;
	}
	
	process.stdout.write(head.data.toString());
	if (head.next != null) {
		process.stdout.write(" -> ");
	}
	
	traversalRecursive(head.next);
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

traversalIterative(head);
traversalRecursive(head);
```
## Insertion at Beginning
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function insertAtBeginning(head, x) {
	// Insert at beginning
	let newNode = new Node(10);
	newNode.next = head;
	return newNode;
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

head = insertAtBeginning(head, 10);
```
## Insertion at Given Position
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function insertAtPosition(head, pos, x) {
	// If position is 1 insert at beginning
	if (pos == 1) {
		let newNode = new Node(x);
		newNode.next = head;
		return newNode;
	}
	
	// Traverse to node at pos - 1
	let i = 1;
	let current = head;
	while (i < pos - 1 && current != null) {
		current = current.next;
		i++;
	}
	
	// Append node
	let newNode = new Node(x);
	newNode.next = current.next;
	current.next = newNode;
	
	return head;
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

head = insertAtPosition(head, 3, 10);
```
## Insertion at End
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function insertAtEnd(head, x) {
	// Traverse to last node
	let current = head;
	while (current.next != null) {
		current = current.next;
	}
	
	// Append node
	let newNode = new Node(x);
	current.next = newNode;
	
	return head;
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

head = insertAtEnd(head, 10);
```
## Deletion From Beginning
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function deleteFromBeginning(head) {
	let temp = head;
	head = head.next;
	// Free memory from old head node
	temp = null;
	
	return head;
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

head = deleteFromBeginning(head);
```
## Deletion From Given Position
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function deleteFromPosition(head, pos) {
	let temp = head;
	
	// If position 1 delete from beginning
	if (pos == 1) {
		head = temp.next;
		temp = null;
		
		return head;
	}
	
	// Traverse to the node at position - 1
	let prev = null;
	for (let i = 1; i < pos; i++) {
		prev = temp;
		temp = temp.next;
	}
	
	prev.next = temp.next;
	prev = null;
	
	return head;
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

head = deleteFromPosition(head, 3);
```
## Deletion From End
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function deleteFromEnd(head) {
	// If list is empty or only has one node
	if (head == null || head.next == null) {
		return null;
	}
	
	// Find second to last node
	let current = head;
	while (current.next.next != null) {
		current = current.next;
	}
	
	// Delete last node
	current.next = null;
	
	return head;
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

head = deleteFromEnd(head);
```
## Reverse List
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function reverseList(head) {
	let current = head;
	let prev = null;
	let next = null;
	
	while (current != null) {
		next = current.next;
		current.next = prev;
		
		prev = current;
		current = next;
	}
	
	return prev;
}

// Head node
let head = new Node(1);
// Second node
head.next = new Node(2);
// Third node
head.next.next = new Node(3);
// Fourth node
head.next.next.next = new Node(4);
// Fifth node
head.next.next.next.next = new Node(5);

head = reverseList(head);
```
# References
## Articles
- [Singly Linked List Tutorial](https://www.geeksforgeeks.org/dsa/singly-linked-list-tutorial/)

[[Linked List]]