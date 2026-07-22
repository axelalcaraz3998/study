Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Binary search is a searching algorithm that operates on a sorted or monotonic search space, repeatedly dividing it into halves to find a target value or optimal answer.
- Divide the search space into two halves by finding the middle index.
- Compare the middle of the search with the key.
- If the key is found at middle, the process is terminated.
- If the key is not found at middle, choose which half will be used as the next search space.
	- If the key is smaller than the middle, then the left side is used for next search.
	- If the key is larger than the middle, then the right side is used for next search.
- The process is continued until the key is found or the total search space is exhausted.
![[binary-search.webp]]
# Java
```java
public class Main {

	private static int binarySearch(int arr[], int n, int x) {
		int low = 0;
		int high = n - 1;
		while (low <= high) {
			int mid = low + (high - low) / 2;
			
			if (arr[mid] == x) {
				return mid;
			}
			
			if (arr[mid] < x) {
				low = mid + 1;
			} else {
				high = mid - 1;
			}
		}
		
		return -1;
	}

	public static void main(String[] args) {
		int[] arr = { -5, -2, 0, 1, 2, 4, 5, 6, 7, 10 };
		int n = arr.length;
		int target = 4;
		
		int result = binarySearch(arr, n, target);
	}

}
```
# Python
```python
def binary_search(arr, n, x):
	low = 0
	high = n - 1
	while low <= high:
		mid = low + (high - low) // 2
		
		if arr[mid] == x:
			return mid
		elif arr[mid] < x:
			low = mid + 1
		else:
			high = mid -1
			
	return -1
	
arr = [-5, -2, 0, 1, 2, 4, 5, 6, 7, 10]
n = len(arr)
target = 4

result = binary_search(arr, n, target)
```
# JavaScript
```js
function binarySearch(arr, n, x) {
	let low = 0;
	let high = n - 1;
	while (low <= high) {
		let mid = Math.floor(low + (high - low) / 2);
		
		if (arr[mid] == x) {
			return mid;
		}
		
		if (arr[mid] < x) {
			low = mid + 1;
		} else {
			high = mid - 1;
		}
	}
	
	return -1;	
}

let = arr = [-5, -2, 0, 1, 2, 4, 5, 6, 7, 10];
let n = arr.length;
let target = 4;

let result = binarySearch(arr, n, target);
```
# Complexity Analysis
## Time Complexity
- **Best Case**: `O(1)`
- **Worst Case**: `O(log n)`
- **Average Case**: `O(log n)`
## Space Complexity
- **Auxiliary Space**: `O(1)`
# Applications
- **Database Indexing**: Used in B-Trees and similar structures for fast data lookup.
- **Debugging in Version Control**: Tools like `git bisect` use binary search to isolate faulty commits.
- **Networking Routing & IP Lookup**: Efficiently find routing entries in tables sorted by address ranges.
- **File Systems & Libraries**: Fast search through sorted directories or symbol tables.
- **Gaming and Graphics**: Collision detection or ray tracing using sorted spatial data.
- **Machine Learning Tuning**: Efficient hyperparameter search (e.g., learning rate, thresholds).
- **Optimization Problems & Competitive Programming**: Solve boundary-value challenges by narrowing search space.
- **Advanced Data Structures**: Binary search trees, self-balancing BSTs, and fractional cascading rely on search logic.
# References
## Articles
- [Binary Search](https://www.geeksforgeeks.org/dsa/binary-search/)

[[Data Structures and Algorithms MOC]]