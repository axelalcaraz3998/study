Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Heap Sort is a comparison based sorting algorithm based on the Binary Heap data structure. The algorithm finds the maximum (or minimum) element and swaps it with the last (or first) element.
# Java
```java
public class Main {
	
	private static void heapify(int[] arr, int n, int i) {
		int largest = i;
		
		int left = 2 * i + 1;
		int right = 2 * i + 2;
		
		if (left < n && arr[left] > arr[largest]) {
			largest = left;
		}
		
		if (right < n && arr[right] > arr[largest]) {
			largest = right;
		}
		
		if (largest != i) {
			int temp = arr[i];
			arr[i] = arr[largest];
			arr[largest] = temp;
			
			heapify(arr, n, largest);
		}
	}
	
	private static void heapSort(int[] arr) {
		int n = arr.length;
		
		// Build heap
		for (int i = n / 2 - 1; i >= 0; i--) {
			heapify(arr, n, i);
		}
		
		// Extract elements from the heap
		for (int i = n - 1; i > 0; i--) {
			// Move root to end
			int temp = arr[0];
			arr[0] = arr[i];
			arr[i] = temp;
			
			// Max heapify on reduced heap
			heapify(arr, i, 0);
		}
	}
	
    public static void main(String[] args) {
        int[] arr = { 9, 4, 3, 8, 10, 2, 5 };
		
        heapSort(arr);
		
        for (int i = 0; i < arr.length; i++) {
	        System.out.print(arr[i] + " ");
        }
    }
	
}
```
# Python
```python
def heapify(arr, n, i):
	largest = i
	
	left = 2 * i + 1
	right = 2 * i + 2
	
	if left < n and arr[left] > arr[largest]:
		largest = left
	
	if right < n and arr[right] > arr[largest]:
		largest = right
	
	if largest != i:
		arr[i], arr[largest] = arr[largest], arr[i]
		
		heapify(arr, n, largest)

def heapSort(arr):
	n = len(arr)
	
	# Build heap
	for i in range(n // 2 - 1, -1, -1):
		heapify(arr, n, i)
	
	# Extract elements from the heap
	for i in range(n - 1, 0, -1):
		# Move root to end
		arr[0], arr[i] = arr[i], arr[0]
		
		# Max heapify on reduced heap
		heapify(arr, i, 0)

arr = [9, 4, 3, 8, 10, 2, 5]

heapSort(arr)

for num in arr:
	print(num, end=" ")
```
# JavaScript
```js
function heapify(arr, n, i) {
	let largest = i;
	
	let left = 2 * i + 1;
	let right = 2 * i + 2;
	
	if (left < n && arr[left] > arr[largest]) {
		largest = left;
	}
	
	if (right < n && arr[right] > arr[largest]) {
		largest = right;
	}
	
	if (largest != i) {
		let temp = arr[i];
		arr[i] = arr[largest];
		arr[largest] = temp;
		
		heapify(arr, n, largest);
	}
}

function heapSort(arr) {
	let n = arr.length;
	
	// Build heap
	for (let i = Math.floor(n / 2) - 1; i >= 0; i--) {
		heapify(arr, n, i);
	}
	
	// Extract elements from the heap
	for (let i = n - 1; i > 0; i--) {
		// Move root to end
		let temp = arr[0];
		arr[0] = arr[i];
		arr[i] = temp;
		
		// Max heapify on reduced heap
		heapify(arr, i, 0);
	}
}

let arr = [9, 4, 3, 8, 10, 2, 5];

heapSort(arr);

for (let i = 0; i < arr.length; i++) {
	process.stdout.write(arr[i] + " ");
}
```
# References
## Articles
- [Heap Sort](https://www.geeksforgeeks.org/dsa/heap-sort/)

[[Sorting Algorithms]]