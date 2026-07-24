Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. This algorithm is not efficient for large data sets as its average and worst-case time complexity is quite high.
- Sorts the array using multiple passes. After the first pass, the maximum goes to the end. Same way, after second pass, the second largest goes to second last position and so on.
- In every pass, process only those that have already not moved to correct position. After `k` passes, the largest `k` must have been moved to the last `k` positions.
- In a pass, we consider remaining elements and compare all adjacent and swap if larger element is before smaller element.
![[bubble-sort.webp]]
# Java
```java
public class Main {
	
	private static void bubbleSort(int[] arr, int n) {
		for (int i = 0; i < n; i++) {
			boolean swapped = false;
			for (int j = 0; j < n - i - 1; j++) {
				if (arr[j] > arr[j + 1]) {
					int temp = arr[j];
					arr[j] = arr[j + 1];
					arr[j + 1] = temp;
					swapped = true;
				}	
			}
			
			if (swapped == false) {
				break;
			}
		}
	}
	
	public static void main(String[] args) {
		int[] arr = { 5, 6, 1, 3 };
		int n = arr.length;
		
		bubbleSort(arr, n);
		
		for (int i = 0; i < n; i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println("");
	}
	
}
```
# Python
```python
def bubble_sort(arr, n):
	for i in range(0, n):
		swapped = False
		for j in range(0, n - i - 1):
			if arr[j] > arr[j + 1]:
				temp = arr[j]
				arr[j] = arr[j + 1]
				arr[j + 1] = temp
				swapped = True
		
		if swapped == False:
			break 

arr = [5, 6, 1, 3]
n = len(arr)

bubble_sort(arr, n)

for i in arr:
	print(i, end=" ")
print("")
```
# JavaScript
```js
function bubbleSort(arr, n) {
	for (let i = 0; i < n; i++) {
		let swapped = false;
		for (let j = 0; j < n - i - 1; j++) {
			if (arr[j] > arr[j + 1]) {
				let temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
				swapped = true;
			}
		}
		
		if (swapped == false) {
			break;
		}
	}
}

let arr = [5, 6, 1, 3];
let n = arr.length;

bubbleSort(arr, n);

for (let i = 0; i < n; i++) {
	process.stdout.write(arr[i] + " ");
}
console.log("");
```
# Complexity Analysis
## Time Complexity
- **Average Case**: `O(n^2)`.
## Space Complexity
- **Auxiliary Space**: `O(1)`.
# References
## Articles
- [Bubble Sort](https://www.geeksforgeeks.org/dsa/bubble-sort-algorithm/)

[[Data Structures and Algorithms MOC]]