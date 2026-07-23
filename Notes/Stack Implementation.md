Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Using Array
## Java
```java
class MyStack {
	
	// Array to store elements
	int[] arr;
	// Maximum size of stack
	int capacity;
	// Index of top element
	int top;
	
	MyStack(int capacity) {
		this.capacity = capacity;
		this.arr = new int[capacity];
		this.top = -1;
	}
	
	void push(int data) {
		// Abort if array is at max capacity
		if (this.isFull()) {
			return;
		}
		
		// Add element to the top
		this.arr[this.top + 1] = data;
		// Update index of top element
		this.top++;
	}
	
	int pop() {
		// Abort if array is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Get element at top of the stack
		int lastElement = this.arr[this.top];
		// Update index of top element
		this.top--;
		
		return lastElement;
	}
	
	int peek() {
		// Abort if array is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Return element at top of the stack
		return this.arr[this.top];
	}
	
	boolean isEmpty() {
		return this.top == -1;
	}
	
	boolean isFull() {
		return this.top == capacity - 1;
	}
	
	int size() {
		return this.top + 1;
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		MyStack stack = new MyStack(5);
		
		System.out.println(stack.isEmpty()); // True
		stack.push(1); // [1]
		stack.push(2); // [1, 2]
		stack.push(3); // [1, 2, 3]
		stack.push(4); // [1, 2, 3, 4]
		stack.push(5); // [1, 2, 3, 4, 5]
		System.out.println(stack.isFull()); // True	
		System.out.println(stack.pop()); // 5
		System.out.println(stack.pop()); // 4
		System.out.println(stack.pop()); // 3
		stack.push(6); // [1, 2, 6]
		System.out.println(stack.peek()); // 6
		System.out.println(stack.size()); // 3
		System.out.println(stack.isEmpty()); // False
		System.out.println(stack.isFull()); // False
	}
	
}
```
## Python
```python
class MyStack:
	def __init__(self, capacity):
		self.capacity = capacity
		self.arr = [0] * capacity
		self.top = -1
	
	def push(self, data):
		# Abort if array is at max capacity
		if self.isFull():
			return
		
		# Add element to the top
		self.arr[self.top + 1] = data
		# Update index of top element
		self.top = self.top + 1
	
	def pop(self):
		# Abort if array is empty
		if self.isEmpty():
			return -1
		
		# Get element at top of the stack
		lastElement = self.arr[self.top]
		# Update index of top element
		self.top = self.top - 1
		
		return lastElement
	
	def peek(self):
		# Abort if array is empty
		if self.isEmpty():
			return -1
		
		# Return element at top of the stack
		return self.arr[self.top]
	
	def isEmpty(self):
		return self.top == -1
	
	def isFull(self):
		return self.top == self.capacity - 1
	
	def size(self):
		return self.top + 1

stack = MyStack(5)

print(stack.isEmpty()) # True
stack.push(1) # [1]
stack.push(2) # [1, 2]
stack.push(3) # [1, 2, 3]
stack.push(4) # [1, 2, 3, 4]
stack.push(5) # [1, 2, 3, 4, 5]
print(stack.isFull()) # True
print(stack.pop()) # 5
print(stack.pop()) # 4
print(stack.pop()) # 3
stack.push(6) # [1, 2, 6]
print(stack.peek()) # 6
print(stack.size()) # 3
print(stack.isEmpty()) # False
print(stack.isFull()) # False
```
## JavaScript
```js
class MyStack {
	
	constructor(capacity) {
		this.capacity = capacity;
		this.arr = new Array(capacity);
		this.top = -1;
	}
	
	push(data) {
		// Abort if array is at max capacity
		if (this.isFull()) {
			return;
		}
		
		// Add element to the top
		this.arr[this.top + 1] = data;
		// Update index of top element
		this.top++;
	}
	
	pop() {
		// Abort if array is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Get element at top of the stack
		let lastElement = this.arr[this.top];
		// Update index of top element
		this.top--;
		
		return lastElement;
	}
	
	peek() {
		// Abort if array is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Return element at top of the stack
		return this.arr[this.top];	
	}
	
	isEmpty() {
		return this.top == -1;
	}
	
	isFull() {
		return this.top == this.capacity - 1;
	}
	
	size() {
		return this.top + 1;
	}
	
}

let stack = new MyStack(5);

console.log(stack.isEmpty()); // True
stack.push(1); // [1]
stack.push(2); // [1, 2]
stack.push(3); // [1, 2, 3]
stack.push(4); // [1, 2, 3, 4]
stack.push(5); // [1, 2, 3, 4, 5]
console.log(stack.isFull()); // True	
console.log(stack.pop()); // 5
console.log(stack.pop()); // 4
console.log(stack.pop()); // 3
stack.push(6); // [1, 2, 6]
console.log(stack.peek()); // 6
console.log(stack.size()); // 3
console.log(stack.isEmpty()); // False
console.log(stack.isFull()); // False
```
# Using Linked List
## Java
```java
class Node {
	
	int data;
	Node next;
	
	Node(int data) {
		this.data = data;
		this.next = null;
	}
	
}

class MyStack {
	
	Node top;
	int size;
	
	MyStack() {
		this.top = null;
		this.size = 0;
	}
	
	void push(int data) {
		// Create new node at append it at beginning of list
		Node temp = new Node(data);
		temp.next = this.top;
		this.top = temp;
		
		// Update size of stack
		this.size++;
	}
	
	int pop() {
		// Abort if stack is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Remove first element and move top to next one
		int lastElement = this.top.data;
		Node temp = this.top;
		this.top = this.top.next;
		temp = null;
		
		// Update size of stack
		this.size--;
		
		return lastElement;
	}
	
	int peek() {
		// Abort if stack is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Return first element in list
		return this.top.data;	
	}
	
	boolean isEmpty() {
		return this.size == 0;
	}
	
	int getSize() {
		return this.size;
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		MyStack stack = new MyStack();
		
		System.out.println(stack.isEmpty()); // True
		stack.push(1); // [1]
		stack.push(2); // [1, 2]
		stack.push(3); // [1, 2, 3]
		stack.push(4); // [1, 2, 3, 4]
		stack.push(5); // [1, 2, 3, 4, 5]
		System.out.println(stack.pop()); // 5
		System.out.println(stack.pop()); // 4
		System.out.println(stack.pop()); // 3
		stack.push(6); // [1, 2, 6]
		System.out.println(stack.peek()); // 6
		System.out.println(stack.getSize()); // 3
		System.out.println(stack.isEmpty()); // False
	}
	
}
```
## Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.next = None

class MyStack:
	def __init__(self):
		self.top = None
		self.size = 0
	
	def push(self, data):
		# Create new node at append it at beginning of list
		temp = Node(data)
		temp.next = self.top
		self.top = temp
		
		# Update size of stack
		self.size = self.size + 1
	
	def pop(self):
		# Abort if stack is empty
		if self.isEmpty():
			return -1
		
		# Remove first element and move top to next one
		lastElement = self.top.data
		temp = self.top
		self.top = self.top.next
		temp = None
		
		# Update size of stack
		self.size = self.size - 1
		
		return lastElement
	
	def peek(self):
		# Abort if array is empty
		if self.isEmpty():
			return -1
		
		# Return first element in list
		return self.top.data
	
	def isEmpty(self):
		return self.size == 0
			
	def get_size(self):
		return self.size

stack = MyStack()

print(stack.isEmpty()) # True
stack.push(1) # [1]
stack.push(2) # [1, 2]
stack.push(3) # [1, 2, 3]
stack.push(4) # [1, 2, 3, 4]
stack.push(5) # [1, 2, 3, 4, 5]
print(stack.pop()) # 5
print(stack.pop()) # 4
print(stack.pop()) # 3
stack.push(6) # [1, 2, 6]
print(stack.peek()) # 6
print(stack.get_size()) # 3
print(stack.isEmpty()) # False
```
## JavaScript
```js
class Node {

	constructor(data) {
		this.data = data;
		this.next = null;
	}

}

class MyStack {
	
	constructor() {
		this.top = null;
		this.size = 0;
	}
	
	push(data) {
		// Create new node at append it at beginning of list
		let temp = new Node(data);
		temp.next = this.top;
		this.top = temp;
		
		// Update size of stack
		this.size++;
	}
	
	pop() {
		// Abort if stack is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Remove first element and move top to next one
		let lastElement = this.top.data;
		let temp = this.top;
		this.top = this.top.next;
		temp = null;
		
		// Update size of stack
		this.size--;
		
		return lastElement;
	}
	
	peek() {
		// Abort if array is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		return this.top.data;
	}
	
	isEmpty() {
		return this.size == 0;
	}
	
	getSize() {
		return this.size;
	}
	
}

let stack = new MyStack();

console.log(stack.isEmpty()); // True
stack.push(1); // [1]
stack.push(2); // [1, 2]
stack.push(3); // [1, 2, 3]
stack.push(4); // [1, 2, 3, 4]
stack.push(5); // [1, 2, 3, 4, 5]
console.log(stack.pop()); // 5
console.log(stack.pop()); // 4
console.log(stack.pop()); // 3
stack.push(6); // [1, 2, 6]
console.log(stack.peek()); // 6
console.log(stack.getSize()); // 3
console.log(stack.isEmpty()); // False
```
# References
## Articles
- [Stack using Array](https://www.geeksforgeeks.org/dsa/implement-stack-using-array/)
- [Stack - Linked List Implementation](https://www.geeksforgeeks.org/dsa/implement-a-stack-using-singly-linked-list/)

[[Stack]]