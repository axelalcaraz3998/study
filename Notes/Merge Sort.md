Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Merge sort is a popular sorting algorithm known for its efficiency and stability. It follows the divide and conquer approach. It works by recursively dividing the input array into two halves, recursively sorting the two halves and finally merging them together to obtain the sorted array.
- **Divide**: Divide the list or array recursively into two halves until it can't be divided anymore.
- **Conquer**: Each subarray is sorted individually using the merge sort algorithm.
- **Merge**: The sorted subarrays are merged back together in sorted order. The process continues until all elements from both subarrays have been merged.
![[merge-sort.webp]]
# Java
```java
public class Main {
	
	private static void merge(int[] arrLeft, int[] arrRight, int[] arr) {
		int nLeft = arrLeft.length;
		int nRight = arrRight.length;
		
		int i = 0, l = 0, r = 0;
		while (l < nLeft && r < nRight) {
			if (arrLeft[l] < arrRight[r]) {
				arr[i] = arrLeft[l];
				l++;
			} else {
				arr[i] = arrRight[r];
				r++;
			}
			
			i++;
		}
		
		// Add possible remaining elements
		while (l < nLeft) {
			arr[i] = arrLeft[l];
			l++;
			i++;
		}
		while (r < nRight) {
			arr[i] = arrRight[r];
			r++;
			i++;			
		}
	}
	
	private static void mergeSort(int[] arr) {
		int n = arr.length;
	
		// Base case
		if (n <= 1) {
			return;
		}
		
		int mid = n / 2;
		int[] arrLeft = new int[mid];
		int[] arrRight = new int[n - mid];
		
		int j = 0;
		for (int i = 0; i < n; i++) {
			if (i < mid) {
				arrLeft[i] = arr[i];
			} else {
				arrRight[j] = arr[i];
				j++;
			}
		}
		
		mergeSort(arrLeft);
		mergeSort(arrRight);
		merge(arrLeft, arrRight, arr);
	}
	
	public static void main(String[] args) {
		int[] arr = { 8, 2, 5, 3, 4, 7, 6, 1 };
		int n = arr.length;
		
		mergeSort(arr);
		
		for (int i = 0; i < n; i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println("");		
	}
	
}
```
# Python
```python
def merge(arrLeft, arrRight, arr):
	nLeft = len(arrLeft)
	nRight = len(arrRight)
	
	i = l = r = 0
	while l < nLeft and r < nRight:
		if arrLeft[l] < arrRight[r]:
			arr[i] = arrLeft[l]
			l += 1
		else:
			arr[i] = arrRight[r]
			r += 1
		
		i += 1
	
	# Add possible remaining elements
	while l < nLeft:
		arr[i] = arrLeft[l]
		l += 1
		i += 1
	while r < nRight:
		arr[i] = arrRight[r]
		r += 1
		i += 1

def merge_sort(arr):
	n = len(arr)
	
	# Base case
	if n <= 1:
		return
	
	mid = n // 2
	arrLeft = [0] * mid
	arrRight = [0] * (n - mid)
	
	j = 0
	for i in range(n):
		if i < mid:
			arrLeft[i] = arr[i]
		else:
			arrRight[j] = arr[i]
			j += 1
	
	merge_sort(arrLeft)
	merge_sort(arrRight)
	merge(arrLeft, arrRight, arr)

arr = [8, 2, 5, 3, 4, 7, 6, 1]
n = len(arr)

merge_sort(arr)

for i in arr:
	print(i, end=" ")
print("")
```
# JavaScript
```js
function merge(arrLeft, arrRight, arr) {
	let nLeft = arrLeft.length;
	let nRight = arrRight.length;
	
	let i = 0, l = 0, r = 0;
	while (l < nLeft && r < nRight) {
		if (arrLeft[l] < arrRight[r]) {
			arr[i] = arrLeft[l];
			l++;
		} else {
			arr[i] = arrRight[r];
			r++;
		}
		
		i++;
	}
	
	// Add possible remaining elements
	while (l < nLeft) {
		arr[i] = arrLeft[l];
		l++;
		i++;
	}
	while (r < nRight) {
		arr[i] = arrRight[r];
		r++;
		i++;			
	}
}

function mergeSort(arr) {
	let n = arr.length;

	// Base case
	if (n <= 1) {
		return;
	}
	
	let mid = n / 2;
	let arrLeft = new Array(mid);
	let arrRight = new Array(n - mid);
	
	let j = 0;
	for (let i = 0; i < n; i++) {
		if (i < mid) {
			arrLeft[i] = arr[i];
		} else {
			arrRight[j] = arr[i];
			j++;
		}
	}
	
	mergeSort(arrLeft);
	mergeSort(arrRight);
	merge(arrLeft, arrRight, arr);
}
	
let arr = [8, 2, 5, 3, 4, 7, 6, 1];
let n = arr.length;

mergeSort(arr);

for (let i = 0; i < n; i++) {
	process.stdout.write(arr[i] + " ");
}
console.log("");
```
# Complexity Analysis
## Time Complexity
- **Average Case**: `O(n log n)`.
## Space Complexity
- **Auxiliary Space**: `O(n)`.
# References
## Articles
- [Merge Sort](https://www.geeksforgeeks.org/dsa/merge-sort/)
## Videos
- [Learn Merge Sort in 13 minutes](https://www.youtube.com/watch?v=3j0SWDX4AtU)

[[Sorting Algorithms]]