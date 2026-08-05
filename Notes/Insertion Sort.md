Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Insertion sort is a simple sorting algorithm that works by iteratively inserting each element of an unsorted list into its correct position in a sorted portion of the list. It is like sorting playing cards in your hands. You split the cards into two groups: the sorted cards and the unsorted cards. Then, you pick a card from the unsorted group and put it in the right place in the sorted group.
- Start with the second element as the first element is assumed to be sorted.
- Compare the second element with the first, if the second is smaller then swap them.
- Move to the third element, compare it with the first two, and put it in its correct position.
- Repeat until the entire array is sorted.
![[insertion-sort.png]]
# Java
```java
public class Main {
	
	private static void insertionSort(int arr[], int n) {
		for (int i = 1; i < n; i++) {
			int key = arr[i];
			int j = i - 1;
			while (j >= 0 && arr[j] > key) {
				arr[j + 1] = arr[j];
				j--;
			}
			arr[j + 1] = key;
		}
	}
	
	public static void main(String[] args) {
		int[] arr = { 23, 1, 10, 5, 2 };
		int n = arr.length;
		
		insertionSort(arr, n);
		
		for (int i = 0; i < n; i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println("");		
	}
	
}
```
# Python
```python
def insertion_sort(arr, n):
	for i in range(1, n):
		key = arr[i]
		j = i - 1
		while j >= 0 and arr[j] > key:
			arr[j + 1] = arr[j]
			j -= 1
		arr[j + 1] = key

arr = [23, 1, 10, 5, 2]
n = len(arr)

insertion_sort(arr, n)

for i in arr:
	print(i, end=" ")
print("")
```
# JavaScript
```js
function insertionSort(arr, n) {
	for (let i = 1; i < n; i++) {
		let key = arr[i];
		let j = i - 1;
		while (j >= 0 && arr[j] > key) {
			arr[j + 1] = arr[j];
			j--;
		}
		arr[j + 1] = key;
	}
}

let arr = [23, 1, 10, 5, 2];
let n = arr.length;

insertionSort(arr, n);

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
- [Insertion Sort Algorithm](https://www.geeksforgeeks.org/dsa/insertion-sort-algorithm/)
## Videos
- [Learn Insertion Sort in 7 minutes](https://www.youtube.com/watch?v=8mJ-OhcfpYg)

[[Sorting Algorithms]]