Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Queue
## Array Implementation
### Java
```java
class MyQueue {
	
	int[] arr;
	int capacity;
	int size;
	
	MyQueue(int capacity) {
		this.capacity = capacity;
		this.arr = new int[capacity];
		this.size = 0;
	}
	
	void enqueue(int data) {
		// Abort if queue is full
		if (this.isFull()) {
			return;
		}
		
		// Add element to queue
		this.arr[this.size] = data;
		// Increment queue size
		this.size++;
	}
	
	int dequeue() {
		// Abort if queue is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Get element at front
		int firstElement = this.arr[0];
		
		// Shift elements to the left
		for (int i = 1; i < this.size; i++) {
			this.arr[i - 1] = this.arr[i];
		}
		
		// Decrement array size
		this.size--;
		
		return firstElement;
	}
	
	int peek() {
		// Abort if queue is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		return this.arr[0];
	}
	
	boolean isEmpty() {
		return this.size == 0;
	}
	
	boolean isFull() {
		return this.size == this.capacity;
	}
	
	int getSize() {
		return this.size;
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		MyQueue queue = new MyQueue(5);
		
		System.out.println(queue.isEmpty()); // True
		queue.enqueue(1);
		queue.enqueue(2);
		queue.enqueue(3);
		queue.enqueue(4);
		queue.enqueue(5);
		System.out.println(queue.isFull()); // True
		System.out.println(queue.peek()); // 1
		queue.dequeue();
		System.out.println(queue.dequeue()); // 2
		System.out.println(queue.getSize()); // 3
		System.out.println(queue.isEmpty()); // False
	}
	
}
```
### Python
```python
class MyQueue:
	def __init__(self, capacity):
		self.capacity = capacity
		self.arr = [0] * capacity
		self.size = 0
	
	def enqueue(self, data):
		# Abort if queue is full
		if self.is_full():
			return
		
		# Add element to queue
		self.arr[self.size] = data
		# Increment queue size
		self.size += 1
	
	def dequeue(self):
		# Abort if queue is empty
		if self.is_empty():
			return -1
		
		# Get element at front
		firstElement = self.arr[0]
		
		# Shift elements to the left
		for i in range(1, self.size):
			self.arr[i - 1] = self.arr[i]
		
		# Decrement array size
		self.size -= 1
		
		return firstElement
	
	def peek(self):
		# Abort if queue is empty
		if self.is_empty():
			return -1
		
		return self.arr[0]
	
	def is_empty(self):
		return self.size == 0
	
	def is_full(self):
		return self.size == self.capacity
	
	def get_size(self):
		return self.size

queue = MyQueue(5)

print(queue.is_empty()) # True
queue.enqueue(1)
queue.enqueue(2)
queue.enqueue(3)
queue.enqueue(4)
queue.enqueue(5)
print(queue.is_full()) # True
print(queue.peek()) # 1
queue.dequeue()
print(queue.dequeue()) # 2
print(queue.get_size()) # 3
print(queue.is_empty()) # False
```
### JavaScript
```js
class MyQueue {

	constructor(capacity) {
		this.capacity = capacity;
		this.arr = new Array(capacity);
		this.size = 0;
	}
	
	enqueue(data) {
		// Abort if queue is full
		if (this.isFull()) {
			return;
		}
		
		// Add element to queue
		this.arr[this.size] = data;
		// Increment queue size
		this.size++;
	}
	
	dequeue() {
		// Abort if queue is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		// Get element at front
		let firstElement = this.arr[0];
		
		// Shift elements to the left
		for (let i = 1; i < this.size; i++) {
			this.arr[i - 1] = this.arr[i];
		}
		
		// Decrement array size
		this.size--;
		
		return firstElement;
	}
	
	peek() {
		// Abort if queue is empty
		if (this.isEmpty()) {
			return -1;
		}
		
		return this.arr[0];
	}
	
	isEmpty() {
		return this.size == 0;
	}
	
	isFull() {
		return this.size == this.capacity;
	}
	
	getSize() {
		return this.size;
	}
	
}

let queue = new MyQueue(5);

console.log(queue.isEmpty()); // True
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
queue.enqueue(4);
queue.enqueue(5);
console.log(queue.isFull()); // True
console.log(queue.peek()); // 1
queue.dequeue();
console.log(queue.dequeue()); // 2
console.log(queue.getSize()); // 3
console.log(queue.isEmpty()); // False
```
## Linked List Implementation
### Java
### Python
### JavaScript
# Double-Ended Queue (Deque)
## Array Implementation
### Java
### Python
### JavaScript
## Linked List Implementation
### Java
### Python
### JavaScript
# References
## Articles
- [Queue using Array](https://www.geeksforgeeks.org/dsa/array-implementation-of-queue-simple/)
- [Circular Queue Using Array](https://www.geeksforgeeks.org/dsa/introduction-to-circular-queue/)
- [Queue - Linked List Implementation](https://www.geeksforgeeks.org/dsa/queue-linked-list-implementation/)

[[Queue]]