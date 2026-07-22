Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Java
## Singly Linked List
### Traversal
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

	public static void traversalIterative(Node head) {
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
	
	public static void traversalRecursive(Node head) {
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
		
		traversalIterative(head);
		traversalRecursive(head);
	}

}
```
## Doubly Linked List
## Circular Linked List
# Python
## Singly Linked List
### Traversal
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
```
## Doubly Linked List
## Circular Linked List
# JavaScript
## Singly Linked List
### Traversal
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

function traversalIterative(Node head) {
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

function traversalRecursive(Node head) {
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

traversalIterative(head);
traversalRecursive(head);
```
## Doubly Linked List
## Circular Linked List
# References
- [Singly Linked List Tutorial](https://www.geeksforgeeks.org/dsa/singly-linked-list-tutorial/)
- [Doubly Linked List Tutorial](https://www.geeksforgeeks.org/dsa/doubly-linked-list/)
- [Introduction to Circular Linked List](https://www.geeksforgeeks.org/dsa/circular-linked-list/)

[[Linked List]]