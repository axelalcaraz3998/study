Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Quick sort is a sorting algorithm based on divide and conquer that picks an element as a pivot and partitions the given array around the picked pivot by placing the pivot in its correct position in the sorted array.
- **Choose a Pivot**: Select an element from the array as the pivot. The choice of pivot can vary (e.g., first element, last element, random element, or median).
- **Partition the Array**: Re arrange the array around the pivot. After partitioning, all elements smaller than the pivot will be on its left, and all elements greater than the pivot will be on its right.
- **Recursively Call**: Recursively apply the same process to the two partitioned subarrays.
- **Base Case**: The recursion stops when there is only one element left in the subarray, as a single element is already sorted.
![[quick-sort.webp]]
# Java
```java
public class Main {
	
	private static int partition(int[] arr, int start, int end) {
		int pivot = arr[end];
		
		int i = start - 1;
		int j = start;
		while (j <= end - 1) {
			// If value is less than pivot swap it
			if (arr[j] < pivot) {
				i++;
				int temp = arr[i];
				arr[i] = arr[j];
				arr[j] = temp;
			}
			
			j++;
		}
		// Swap pivot to correct position
		i++;
		int temp = arr[i];
		arr[i] = arr[end];
		arr[end] = temp;
		
		return i;
	}
	
	private static void quickSort(int[] arr, int start, int end) {
		// Base case
		if (end <= start) {
			return;
		}
		
		// Find index of the pivot
		int pivot = partition(arr, start, end);
		
		quickSort(arr, start, pivot - 1);
		quickSort(arr, pivot + 1, end);
	}
	
	public static void main(String[] args) {
		int[] arr = { 8, 2, 5, 3, 4, 7, 6, 1 };
		int n = arr.length;
		
		quickSort(arr, 0, n - 1);
		
		for (int i = 0; i < n; i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println("");		
	}
	
}
```
# Python
```python
def partition(arr, start, end):
	pivot = arr[end]
	
	i = start - 1
	j = start
	while j <= end - 1:
		# If value is less than pivot swap it
		if arr[j] < pivot:
			i += 1
			temp = arr[i]
			arr[i] = arr[j]
			arr[j] = temp
		
		j += 1
	# Swap pivot to correct position
	i += 1
	temp = arr[i]
	arr[i] = arr[j]
	arr[j] = temp
	
	return i

def quick_sort(arr, start, end):
	# Base case
	if end <= start:
		return
	
	# Find index of the pivot
	pivot = partition(arr, start, end)
	
	quick_sort(arr, start, pivot - 1)
	quick_sort(arr, pivot + 1, )

arr = [8, 2, 5, 3, 4, 7, 6, 1]
n = len(arr)

quick_sort(arr, 0, n - 1)

for i in arr:
	print(i, end=" ")
print("")
```
# JavaScript
```js
function partition(arr, start, end) {
	let pivot = arr[end];
	
	let i = start - 1;
	let j = start;
	while (j <= end - 1) {
		// If value is less than pivot swap it
		if (arr[j] < pivot) {
			i++;
			let temp = arr[i];
			arr[i] = arr[j];
			arr[j] = temp;
		}
		
		j++;
	}
	// Swap pivot to correct position
	i++;
	let temp = arr[i];
	arr[i] = arr[end];
	arr[end] = temp;
	
	return i;
}

function quickSort(arr, start, end) {
	// Base case
	if (end <= start) {
		return;
	}
	
	// Find index of the pivot
	let pivot = partition(arr, start, end);
	
	quickSort(arr, start, pivot - 1);
	quickSort(arr, pivot + 1, end);
}

let arr = [8, 2, 5, 3, 4, 7, 6, 1];
let n = arr.length;

quickSort(arr, 0, n - 1);

for (let i = 0; i < n; i++) {
	process.stdout.write(arr[i] + " ");
}
console.log("");
```
# Complexity Analysis
## Time Complexity
- **Average Case**: `O(n log n)`.
## Space Complexity
- **Auxiliary Space**: `O(log n)`.
# References
## Articles
- [Quick Sort](https://www.geeksforgeeks.org/dsa/quick-sort-algorithm/)
## Videos
- [Learn Quick Sort in 13 minutes](https://www.youtube.com/watch?v=Vtckgz38QHs)

[[Sorting Algorithms]]