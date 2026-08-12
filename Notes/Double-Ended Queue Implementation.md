Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Using Array
## Java
```java
class MyDeque {
	
	int[] arr;
	int capacity;
	int size;
	int front;
	
	MyDeque(int capacity) {
		arr = new int[capacity];
		this.capacity = capacity;
		size = 0;
		front = 0;
	}
	
	void insertFront(int data) {
		// Check that deque isn't full
		if (size == capacity) {
			return;
		}
		
		// Calculate front index using formula: (front - 1 + capacity) % capacity
		front = (front - 1 + capacity) % capacity;
		arr[front] = data;
		size++;
	}
	
	void insertRear(int data) {
		// Check that deque isn't full
		if (size == capacity) {
			return;
		}
		
		// Calculate rear index using formula: (front + size) % capacity
		int rear = (front + size) % capacity;
		arr[rear] = data;
		size++;
	}
	
	int deleteFront() {
		// Check that deque isn't empty
		if (isEmpty()) {
			return -1;
		}
		
		int ele = arr[front];
		// Calculate front index using formula: (front + 1) % capacity
		front = (front + 1) % capacity;
		size--;
		
		return ele;
	}
	
	int deleteRear() {
		// Check that deque isn't empty
		if (isEmpty()) {
			return -1;
		}
		
		// Calculate rear index using formula: (front + size - 1) % capacity
		int rear = (front + size - 1) % capacity;
		int ele = arr[rear];
		size--;
		
		return ele;
	}
	
	int getFront() {
		return arr[front];
	}
	
	int getRear() {
		// Calculate rear index using formula: (front + size - 1) % capacity
		int rear = (front + size - 1) % capacity;
		
		return arr[rear];
	}
	
	int getSize() {
		return size;
	}
	
	boolean isEmpty() {
		return size == 0;
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		MyDeque deque = new MyDeque(5);
		
		deque.insertRear(1);
		deque.insertFront(2);
		deque.insertRear(3);
		deque.insertFront(4);
		deque.insertRear(5);
		// [4, 2, 1, 3, 5]
		System.out.println(deque.getFront()); // 4
		System.out.println(deque.getRear()); // 5
		deque.deleteFront();
		deque.deleteRear();
		System.out.println(deque.getFront()); // 2
		System.out.println(deque.getRear()); // 3		
	}
	
}
```
## Python
```python
class MyDeque:
	def __init__(self, capacity):
		self.arr = [0] * capacity
		self.capacity = capacity
		self.size = 0
		self.front = 0
	
	def insert_front(self, data):
		# Check that deque isn't full
		if (self.size == self.capacity):
			return
		
		# Calculate front index using formula: (front - 1 + capacity) % capacity
		self.front = (self.front - 1 + self.capacity) % self.capacity
		self.arr[self.front] = data
		self.size += 1
	
	def insert_rear(self, data):
		# Check that deque isn't full
		if (self.size == self.capacity):
			return
		
		# Calculate rear index using formula: (front + size) % capacity
		rear = (self.front + self.size) % self.capacity
		self.arr[rear] = data
		self.size += 1
	
	def delete_front(self):
		# Check that deque isn't empty
		if self.is_empty():
			return -1
		
		ele = self.arr[self.front]
		# Calculate front index using formula: (front + 1) % capacity
		self.front = (self.front + 1) % self.capacity
		self.size -= 1
		
		return ele
	
	def delete_rear(self):
		# Check that deque isn't empty
		if self.is_empty():
			return -1
		
		# Calculate rear index using formula: (front + size - 1) % capacity
		rear = (self.front + self.size - 1) % self.capacity
		ele = self.arr[rear]
		self.size -= 1
		
		return ele
	
	def get_front(self):
		return self.arr[self.front]
	
	def get_rear(self):
		rear = (self.front + self.size - 1) % self.capacity
		
		return self.arr[rear]
	
	def get_size(self):
		return self.size
	
	def is_empty(self):
		return self.size == 0

deque = MyDeque(5);

deque.insert_rear(1);
deque.insert_front(2);
deque.insert_rear(3);
deque.insert_front(4);
deque.insert_rear(5);
# [4, 2, 1, 3, 5]
print(deque.get_front()); # 4
print(deque.get_rear()); # 5
deque.delete_front();
deque.delete_rear();
print(deque.get_front()); # 2
print(deque.get_rear()); # 3
```
## JavaScript
```js
class MyDeque {
	
	constructor(capacity) {
		this.arr = Array(capacity);
		this.capacity = capacity;
		this.size = 0;
		this.front = 0;
	}
	
	insertFront(data) {
		// Check that deque isn't full
		if (this.size == this.capacity) {
			return;
		}
		
		// Calculate front index using formula: (front - 1 + capacity) % capacity
		this.front = (this.front - 1 + this.capacity) % this.capacity;
		this.arr[this.front] = data;
		this.size++;
	}
	
	insertRear(data) {
		// Check that deque isn't full
		if (this.size == this.capacity) {
			return;
		}
		
		// Calculate rear index using formula: (front + size) % capacity
		let rear = (this.front + this.size) % this.capacity;
		this.arr[rear] = data;
		this.size++;
	}
	
	deleteFront() {
		// Check that deque isn't empty
		if (this.isEmpty()) {
			return -1;
		}
		
		let ele = this.arr[this.front];
		// Calculate front index using formula: (front + 1) % capacity
		this.front = (this.front + 1) % this.capacity;
		this.size--;
		
		return ele;
	}
	
	deleteRear() {
		// Check that deque isn't empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Calculate rear index using formula: (front + size - 1) % capacity
		let rear = (this.front + this.size - 1) % this.capacity;
		let ele = this.arr[rear];
		this.size--;
		
		return ele;
	}
	
	getFront() {
		return this.arr[this.front];
	}
	
	getRear() {
		// Calculate rear index using formula: (front + size - 1) % capacity
		let rear = (this.front + this.size - 1) % this.capacity;
		
		return this.arr[rear];
	}
	
	getSize() {
		return this.size;
	}
	
	isEmpty() {
		return this.size == 0;
	}
	
}

let deque = new MyDeque(5);

deque.insertRear(1);
deque.insertFront(2);
deque.insertRear(3);
deque.insertFront(4);
deque.insertRear(5);
// [4, 2, 1, 3, 5]
console.log(deque.getFront()); // 4
console.log(deque.getRear()); // 5
deque.deleteFront();
deque.deleteRear();
console.log(deque.getFront()); // 2
console.log(deque.getRear()); // 3
```
# Using Linked List
## Java
```java
class Node {
	
	int data;
	Node prev;
	Node next;
	
	Node (int data) {
		this.data = data;
		next = null;
		prev = null;
	}
	
}

class MyDeque {
	
	int size;	
	Node front;
	Node rear;
	
	MyDeque() {
		front = null;
		rear = null;
		size = 0;
	}
	
	void insertFront(int data) {
		Node newNode = new Node(data);
		
		if (front == null) {
			front = newNode;
			rear = newNode;
		} else {
			newNode.next = front;
			front.prev = newNode;
			front = newNode;
		}
		
		size++;
	}
	
	void insertRear(int data) {
		Node newNode = new Node(data);
		
		if (rear == null) {
			front = newNode;
			rear = newNode;
		} else {
			newNode.prev = rear;
			rear.next = newNode;
			rear = newNode;
		}
		
		size++;
	}
	
	int deleteFront() {
		// Check that deque isn't empty
		if (isEmpty()) {
			return -1;
		}
		
		int ele = front.data;
		front = front.next;
		if (front == null) {
			rear = null;
		} else {
			front.prev = null;
		}
		size--;
		
		return ele;
	}
	
	int deleteRear() {
		// Check that deque isn't empty
		if (isEmpty()) {
			return -1;
		}
		
		int ele = rear.data;
		rear = rear.prev;
		if (rear == null) {
			front = null;
		} else {
			rear.next = null;
		}
		size--;
		
		return ele;
	}
	
	int getFront() {
		return front.data;
	}
	
	int getRear() {
		return rear.data;
	}
	
	int getSize() {
		return size;
	}
	
	boolean isEmpty() {
		return size == 0;
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		MyDeque deque = new MyDeque();
		
		deque.insertRear(1);
		deque.insertFront(2);
		deque.insertRear(3);
		deque.insertFront(4);
		deque.insertRear(5);
		// [4, 2, 1, 3, 5]
		System.out.println(deque.getFront()); // 4
		System.out.println(deque.getRear()); // 5
		deque.deleteFront();
		deque.deleteRear();
		System.out.println(deque.getFront()); // 2
		System.out.println(deque.getRear()); // 3		
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

class MyDeque:
	def __init__(self):
		self.front = None
		self.rear = None
		self.size = 0
	
	def insert_front(self, data):
		new_node = Node(data)
		
		if self.front is None:
			self.front = new_node
			self.rear = new_Node
		else:
			new_node.next = self.front
			self.front.prev = new_node
			self.front = new_node
		
		self.size += 1
	
	def insert_rear(self, data):
		new_node = Node(data)
		
		if self.rear is None:
			self.front = new_node
			self.rear = new_node
		else:
			new_node.prev = self.rear
			self.rear.next = new_node
			self.rear = new_node
		
		self.size += 1
	
	def delete_front(self):
		# Check that deque isn't empty
		if self.is_empty():
			return -1
		
		ele = self.front.data
		self.front = self.front.next
		if self.front is None:
			self.rear = None
		else:
			self.prev = None
		self.size -= 1
		
		return ele
	
	def delete_rear(self):
		# Check that deque isn't empty
		if self.is_empty():
			return -1
		
		ele = self.rear.data
		self.rear = self.rear.prev
		if self.rear is None:
			self.front = None
		else:
			self.rear.next = None
		self.size -= 1
		
		return ele
	
	def get_front(self):
		return self.front.data
	
	def get_rear(self):
		return self.rear.data
	
	def get_size(self):
		return self.size
	
	def is_empty(self):
		return self.size == 0

deque = MyDeque();

deque.insert_rear(1);
deque.insert_front(2);
deque.insert_rear(3);
deque.insert_front(4);
deque.insert_rear(5);
# [4, 2, 1, 3, 5]
print(deque.get_front()); # 4
print(deque.get_rear()); # 5
deque.delete_front();
deque.delete_rear();
print(deque.get_front()); # 2
print(deque.get_rear()); # 3
```
## JavaScript
```js
class Node {
	
	constructor (data) {
		this.data = data;
		this.next = null;
		this.prev = null;
	}
	
}

class MyDeque {
	
	constructor() {
		this.front = null;
		this.rear = null;
		this.size = 0;
	}
	
	insertFront(data) {
		let newNode = new Node(data);
		
		if (this.front == null) {
			this.front = newNode;
			this.rear = newNode;
		} else {
			newNode.next = this.front;
			this.front.prev = newNode;
			this.front = newNode;
		}
		
		this.size++;
	}
	
	insertRear(data) {
		let newNode = new Node(data);
		
		if (this.rear == null) {
			this.front = newNode;
			this.rear = newNode;
		} else {
			newNode.prev = this.rear;
			this.rear.next = newNode;
			this.rear = newNode;
		}
		
		this.size++;
	}
	
	deleteFront() {
		// Check that deque isn't empty
		if (this.isEmpty()) {
			return -1;
		}
		
		let ele = this.front.data;
		this.front = this.front.next;
		if (this.front == null) {
			this.rear = null;
		} else {
			this.front.prev = null;
		}
		this.size--;
		
		return ele;
	}
	
	deleteRear() {
		// Check that deque isn't empty
		if (this.isEmpty()) {
			return -1;
		}
		
		let ele = this.rear.data;
		this.rear = this.rear.prev;
		if (this.rear == null) {
			this.front = null;
		} else {
			this.rear.next = null;
		}
		this.size--;
		
		return ele;
	}
	
	getFront() {
		return this.front.data;
	}
	
	getRear() {
		return this.rear.data;
	}
	
	getSize() {
		return this.size;
	}
	
	isEmpty() {
		return this.size == 0;
	}
	
}

let deque = new MyDeque();

deque.insertRear(1);
deque.insertFront(2);
deque.insertRear(3);
deque.insertFront(4);
deque.insertRear(5);
// [4, 2, 1, 3, 5]
console.log(deque.getFront()); // 4
console.log(deque.getRear()); // 5
deque.deleteFront();
deque.deleteRear();
console.log(deque.getFront()); // 2
console.log(deque.getRear()); // 3
```
# References
## Articles
- [Implementation of Deque using Circular Array](https://www.geeksforgeeks.org/dsa/implementation-deque-using-circular-array/)
- [Implementation of Deque using Doubly Linked List](https://www.geeksforgeeks.org/dsa/implementation-deque-using-doubly-linked-list/)

[[Queue]]