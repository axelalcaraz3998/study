Tags: #ComputerScience #DSA #Java #Python #JavaScript 

In linear search, we iterate over all elements of the array and check if the current element is equal to the target element. If we find any element to be equal to the target element, we return the index, otherwise we return -1 as the element was not found.
# Java
```java
private int search(int arr[], int n, int x) {
	// Iterate over the array to find the key
	for (int i = 0; i < n; i++) {
		if (arr[i] == x) {
			return i;
		}
	}
	
	// If key is not found return -1
	return -1;
}
```
# Python
```python
def search(arr, n, x):
	# Iterate over the array to find the key
	for i in range(0, n):
		if (arr[i] == x):
			return i
	
	# If key is not found return -1
	return -1
```
# JavaScript
```js
function search(arr, n, x) {
	// Iterate over the array to find the key
	for (let i = 0; i < n; i++) {
		if (arr[i] == x) {
			return i;
		}
	}
	
	// If key is not found return -1
	return -1;
}
```
# Complexity Analysis
## Time Complexity
- **Best Case**: In the best case, the key might be present at first index. So the best case complexity is `O(1)`.
- **Worst Case**: In the worst case, the key might be present at the last index. So the worst-case complexity is `O(n)`.
- **Average Case**: `O(n)`.
## Space Complexity
- **Auxiliary Space**: `O(1)`.
# Applications
- **Unsorted Lists**: When we have an unsorted array or list, linear search is the most commonly used to find any element in the collection.
- **Small Data Sets**: Linear search is preferred over binary search when we have small data sets.
- **Searching Linked Lists**: In linked lists implementations, linear search is commonly used to find elements within the list.
# References
## Articles
- [Linear Search Algorithm](https://www.geeksforgeeks.org/dsa/linear-search/)

[[Data Structures and Algorithms MOC]]