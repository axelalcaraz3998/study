Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Min Heap
## Java
```java
import java.util.List;
import java.util.ArrayList;

class MinHeap {
	
	private List<Integer> heap;
	
	public MinHeap() {
		heap = new ArrayList<>();
	}
	
	public void insert(int val) {
		// Append value at the end of the heap
		heap.add(val);
		
		// Bubble up to restore heap property
		int currIdx = heap.size() - 1;
		while (currIdx > 0 && heap.get(currIdx) < heap.get(parent(currIdx))) {
			swap(currIdx, parent(currIdx));
			currIdx = parent(currIdx);
		}
	}
	
	public int getMin() {
		if (heap.isEmpty()) {
			return -1;
		}
		
		// Min value
		int min = heap.get(0);
		// Get last element
		int lastElement = heap.remove(heap.size() - 1);
		
		if (!heap.isEmpty()) {
			// Move last element to the root
			heap.set(0, lastElement);
			
			int currIdx = 0;
			while (true) {
				int left = leftChild(currIdx);
				int right = rightChild(currIdx);
				
				int smallest = currIdx;
				
				if (left < heap.size() && heap.get(left) < heap.get(smallest)) {
					smallest = left;
				}
				
				if (right < heap.size() && heap.get(right) < heap.get(smallest)) {
					smallest = right;
				}
				
				if (smallest == currIdx) {
					break;
				}
				
				swap(currIdx, smallest);
				currIdx = smallest;
			}
		}

        return min;
	}
	
	public boolean isEmpty() {
		return heap.isEmpty();
	}
	
	// Get index of the parent node
	private int parent(int i) {
		return (i - 1) / 2;
	}
	
	// Get index of the left child node
	private int leftChild(int i) {
		return 2 * i + 1;
	}
	
	// Get index of the right child node
	private int rightChild(int i) {
		return 2 * i + 2;
	}
	
	// Swap elements at indices i and j
	private void swap(int i, int j) {
		int temp = heap.get(i);
		heap.set(i, heap.get(j));
		heap.set(j, temp);
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		MinHeap minHeap = new MinHeap();
		
		minHeap.insert(10);
		minHeap.insert(5);
		minHeap.insert(15);
		minHeap.insert(20);
		minHeap.insert(25);
		
		System.out.println("Min: " + minHeap.getMin());
		System.out.println("Min: " + minHeap.getMin());
	}
	
}
```
## Python
```python
class MinHeap:
	def __init__(self):
		self.heap = []
	
	def insert(self, val):
		# Append value at the end of heap
		self.heap.append(val)
		
		# Bubble up to restore heap property
		curr_idx = len(self.heap) - 1
		
		while (
		  curr_idx > 0
		  and self.heap[curr_idx] < self.heap[self._parent(curr_idx)]
		):
		  parent_idx = self._parent(curr_idx)
		  self._swap(curr_idx, parent_idx)
		  curr_idx = parent_idx
	
	def get_min(self):
		if len(self.heap) == 0:
			return -1
		
		# Save minimum value
		min_val = self.heap[0]
		
		# Remove and get the last element
		last_element = self.heap.pop()
		
		if len(self.heap) != 0:
			# Move last element to the root
			self.heap[0] = last_element
			
			# Bubble down to restore heap property
			curr_idx = 0
			
			while True:
				left = self._left_child(curr_idx)
				right = self._right_child(curr_idx)
				
				smallest = curr_idx
				
				if (
				  left < len(self.heap)
				  and self.heap[left] < self.heap[smallest]
				):
				  smallest = left
				
				if (
				  right < len(self.heap)
				  and self.heap[right] < self.heap[smallest]
				):
				  smallest = right
				
				if smallest == curr_idx:
				  break
				
				self._swap(curr_idx, smallest)
				curr_idx = smallest
		
		return min_val
	
	def is_empty(self):
		return len(self.heap) == 0
	
	# Get index of parent node
	def _parent(self, i):
		return (i - 1) // 2
	
	# Get index of left child node
	def _left_child(self, i):
		return 2 * i + 1
	
	# Get index of right child node
	def _right_child(self, i):
		return 2 * i + 2
	
	# Swap elements at indices i and j
	def _swap(self, i, j):
		self.heap[i], self.heap[j] = self.heap[j], self.heap[i]

min_heap = MinHeap()

min_heap.insert(10)
min_heap.insert(5)
min_heap.insert(15)
min_heap.insert(20)
min_heap.insert(25)

print("Min:", min_heap.get_min())
print("Min:", min_heap.get_min())
```
## JavaScript
```js
class MinHeap {

	constructor() {
		this.heap = new Array();
	}
	
	insert(val) {
		// Append value at the end of heap
		this.heap.push(val);
		
		// Bubble up to restore heap property
		let currIdx = this.heap.length - 1;
		while (currIdx > 0 && this.heap[currIdx] < this.heap[this.#parent(currIdx)]) {
			this.#swap(currIdx, this.#parent(currIdx));
  			currIdx = this.#parent(currIdx);
		}
	}
	
	getMin() {
		if (this.isEmpty()) {
			return -1;
		}
		
		// Min value
		let min = this.heap[0];
		// Get last element
		let lastElement = this.heap.pop();
		
		if (!this.isEmpty()) {
			// Move last element to the root
			this.heap[0] = lastElement;
			
			let currIdx = 0;
			while (true) {
				let left = this.#leftChild(currIdx);
				let right = this.#rightChild(currIdx);
				
				let smallest = currIdx;
				
				if (left < this.heap.length && this.heap[left] < this.heap[smallest]) {
					smallest = left;
				}
				
				if (right < this.heap.length && this.heap[right] < this.heap[smallest]) {
					smallest = right;
				}
				
				if (smallest == currIdx) {
					break;
				}
				
				this.#swap(currIdx, smallest);
				currIdx = smallest;
			}
		}

        return min;
	}
	
	isEmpty() {
		return this.heap.length == 0;
	}
	
	// Get index of the parent node
	#parent(i) {
		return Math.floor((i - 1) / 2);
	}
	
	// Get index of the left child node
	#leftChild(i) {
		return 2 * i + 1;
	}
	
	// Get index of the right child node
	#rightChild(i) {
		return 2 * i + 2;
	}
	
	// Swap elements at indices i and j
	#swap(i, j) {
		let temp = this.heap[i];
		this.heap[i] = this.heap[j];
		this.heap[j] = temp;
	}
	
}

let minHeap = new MinHeap();

minHeap.insert(10);
minHeap.insert(5);
minHeap.insert(15);
minHeap.insert(20);
minHeap.insert(25);

console.log("Min: " + minHeap.getMin());
console.log("Min: " + minHeap.getMin());
```
# Max Heap
## Java
```java
import java.util.List;
import java.util.ArrayList;

class MaxHeap {
	
	private List<Integer> heap;
	
	public MaxHeap() {
		heap = new ArrayList<>();
	}
	
	public void insert(int val) {
		// Append value at the end of the heap
		heap.add(val);
		
		// Bubble up to restore heap property
		int currIdx = heap.size() - 1;
		while (currIdx > 0 && heap.get(currIdx) > heap.get(parent(currIdx))) {
			swap(currIdx, parent(currIdx));
			currIdx = parent(currIdx);
		}
	}
	
	public int getMax() {
		if (heap.isEmpty()) {
			return -1;
		}
		
		// Max value
		int max = heap.get(0);
		// Get last element
		int lastElement = heap.remove(heap.size() - 1);
		
		if (!heap.isEmpty()) {
			// Move last element to the root
			heap.set(0, lastElement);
			
			int currIdx = 0;
			while (true) {
				int left = leftChild(currIdx);
				int right = rightChild(currIdx);
				
				int largest = currIdx;
				
				if (left < heap.size() && heap.get(left) > heap.get(largest)) {
					largest = left;
				}
				
				if (right < heap.size() && heap.get(right) > heap.get(largest)) {
					largest = right;
				}
				
				if (largest == currIdx) {
					break;
				}
				
				swap(currIdx, largest);
				currIdx = largest;
			}
		}

        return max;
	}
	
	public boolean isEmpty() {
		return heap.isEmpty();
	}
	
	// Get index of the parent node
	private int parent(int i) {
		return (i - 1) / 2;
	}
	
	// Get index of the left child node
	private int leftChild(int i) {
		return 2 * i + 1;
	}
	
	// Get index of the right child node
	private int rightChild(int i) {
		return 2 * i + 2;
	}
	
	// Swap elements at indices i and j
	private void swap(int i, int j) {
		int temp = heap.get(i);
		heap.set(i, heap.get(j));
		heap.set(j, temp);
	}
	
}

public class Main {
	
	public static void main(String[] args) {
		MaxHeap maxHeap = new MaxHeap();
		
		maxHeap.insert(10);
		maxHeap.insert(5);
		maxHeap.insert(15);
		maxHeap.insert(20);
		maxHeap.insert(25);
		
		System.out.println("Max: " + maxHeap.getMax());
		System.out.println("Max: " + maxHeap.getMax());
	}
	
}
```
## Python
```python
class MaxHeap:
	def __init__(self):
		self.heap = []
	
	def insert(self, val):
		# Append value at the end of heap
		self.heap.append(val)
		
		# Bubble up to restore heap property
		curr_idx = len(self.heap) - 1
		
		while (
		  curr_idx > 0
		  and self.heap[curr_idx] > self.heap[self._parent(curr_idx)]
		):
		  parent_idx = self._parent(curr_idx)
		  self._swap(curr_idx, parent_idx)
		  curr_idx = parent_idx
	
	def get_max(self):
		if len(self.heap) == 0:
			return -1
		
		# Save max value
		max_val = self.heap[0]
		
		# Remove and get the last element
		last_element = self.heap.pop()
		
		if len(self.heap) != 0:
			# Move last element to the root
			self.heap[0] = last_element
			
			curr_idx = 0
			while True:
				left = self._left_child(curr_idx)
				right = self._right_child(curr_idx)
				
				largest = curr_idx
				
				if (
				  left < len(self.heap)
				  and self.heap[left] > self.heap[largest]
				):
				  largest = left
				
				if (
				  right < len(self.heap)
				  and self.heap[right] > self.heap[largest]
				):
				  largest = right
				
				if largest == curr_idx:
				  break
				
				self._swap(curr_idx, largest)
				curr_idx = largest
		
		return max_val
	
	def is_empty(self):
		return len(self.heap) == 0
	
	# Get index of parent node
	def _parent(self, i):
		return (i - 1) // 2
	
	# Get index of left child node
	def _left_child(self, i):
		return 2 * i + 1
	
	# Get index of right child node
	def _right_child(self, i):
		return 2 * i + 2
	
	# Swap elements at indices i and j
	def _swap(self, i, j):
		self.heap[i], self.heap[j] = self.heap[j], self.heap[i]

max_heap = MaxHeap()

max_heap.insert(10)
max_heap.insert(5)
max_heap.insert(15)
max_heap.insert(20)
max_heap.insert(25)

print("Max:", max_heap.get_max())
print("Max:", max_heap.get_max())
```
## JavaScript
```js
class MaxHeap {

	constructor() {
		this.heap = new Array();
	}
	
	insert(val) {
		// Append value at the end of heap
		this.heap.push(val);
		
		// Bubble up to restore heap property
		let currIdx = this.heap.length - 1;
		while (currIdx > 0 && this.heap[currIdx] > this.heap[this.#parent(currIdx)]) {
			this.#swap(currIdx, this.#parent(currIdx));
  			currIdx = this.#parent(currIdx);
		}
	}
	
	getMax() {
		if (this.isEmpty()) {
			return -1;
		}
		
		// Min value
		let max = this.heap[0];
		// Get last element
		let lastElement = this.heap.pop();
		
		if (!this.isEmpty()) {
			// Move last element to the root
			this.heap[0] = lastElement;
			
			let currIdx = 0;
			while (true) {
				let left = this.#leftChild(currIdx);
				let right = this.#rightChild(currIdx);
				
				let largest = currIdx;
				
				if (left < this.heap.length && this.heap[left] > this.heap[largest]) {
					largest = left;
				}
				
				if (right < this.heap.length && this.heap[right] > this.heap[largest]) {
					largest = right;
				}
				
				if (largest == currIdx) {
					break;
				}
				
				this.#swap(currIdx, largest);
				currIdx = largest;
			}
		}

        return max;
	}
	
	isEmpty() {
		return this.heap.length == 0;
	}
	
	// Get index of the parent node
	#parent(i) {
		return Math.floor((i - 1) / 2);
	}
	
	// Get index of the left child node
	#leftChild(i) {
		return 2 * i + 1;
	}
	
	// Get index of the right child node
	#rightChild(i) {
		return 2 * i + 2;
	}
	
	// Swap elements at indices i and j
	#swap(i, j) {
		let temp = this.heap[i];
		this.heap[i] = this.heap[j];
		this.heap[j] = temp;
	}
	
}

let maxHeap = new MaxHeap();

maxHeap.insert(10);
maxHeap.insert(5);
maxHeap.insert(15);
maxHeap.insert(20);
maxHeap.insert(25);

console.log("Max: " + maxHeap.getMax());
console.log("Max: " + maxHeap.getMax());
```

# References
## Articles
- [Heap Implementation in Java](https://www.geeksforgeeks.org/java/heap-implementation-in-java/)

[[Heap]]