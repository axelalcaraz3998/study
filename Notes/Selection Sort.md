Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Selection sort is a comparison-based sorting algorithm. It sorts by repeatedly selecting the smallest (or largest) element from the unsorted portion and swapping it with the first unsorted element.
- Find the smallest element and swap it with the first element. This way we get the smallest element and its correct position.
- Then find the second smallest and swap it with the second element.
- We keep doing this until we get all elements moved to their correct positions.
![[selection-sort.png]]
# Java
```java
public class Main {
	
	private static void selectionSort(int arr[], int n) {
		for (int i = 0; i < n - 1; i++) {
			int minIdx = i;
			for (int j = i + 1; j < n; j++) {
				if (arr[j] < arr[minIdx]) {
					minIdx = j;
				}
			}
			int temp = arr[i];
			arr[i] = arr[minIdx];
			arr[minIdx] = temp;
		}
	}
	
	public static void main(String[] args) {
		int[] arr = { 64, 25, 12, 22, 11 };
		int n = arr.length;
		
		selectionSort(arr, n);
		
		for (int i = 0; i < n; i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println("");		
	}
	
}
```
# Python
```python
def selection_sort(arr, n):
	for i in range(n - 1):
		min_idx = i
		for j in range(i + 1, n):
			if arr[j] < arr[min_idx]:
				min_idx = j
		temp = arr[i]
		arr[i] = arr[min_idx]
		arr[min_idx] = temp

arr = [64, 25, 12, 22, 11]
n = len(arr)

selection_sort(arr, n)

for i in arr:
	print(i, end=" ")
print("")
```
# JavaScript
```js
function selectionSort(arr, n) {
	for (let i = 0; i < n - 1; i++) {
		let minIdx = i;
		for (let j = i + 1; j < n; j++) {
			if (arr[j] < arr[minIdx]) {
				minIdx = j;
			}
		}
		let temp = arr[i];
		arr[i] = arr[minIdx];
		arr[minIdx] = temp;
	}
}

let arr = [64, 25, 12, 22, 11];
let n = arr.length;

selectionSort(arr, n);

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
- [Selection Sort](https://www.geeksforgeeks.org/dsa/selection-sort-algorithm-2/)
## Videos
- [Learn Selection Sort in 8 minutes](https://www.youtube.com/watch?v=EwjnF7rFLns)

[[Sorting Algorithms]]