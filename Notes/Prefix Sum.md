Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Prefix sum is a technique used to quickly calculate the sum of any subarray. By precomputing cumulative sums in `O(n)` time, subsequent queries can be computed in `O(1)` time. The idea is simple:
- Construct a prefix sum array, where each element at index `i` stores the sum of all elements from index `0` to `i`.
- Once this array is built, any subarray sum query can be computed in constant time `O(1)` instead of `O(n)`.
![[prefix-sum.webp]]
# Java
```java
private static int[] prefixSum(int[] arr, int n) {
	int[] prefixSumArr = new int[n];
	// Initialize the first element
	prefixSumArr[0] = arr[0];
	
	for (int i = 1; i < n; i++) {
		prefixSumArr[i] = prefixSumArr[i - 1] + arr[i];
	}
	
	return prefixSumArr;
}
```
# Python
```python
def prefixSum(arr, n):
	prefixSumArr = [0] * n
	# Initialize the first element
	prefixSumArr[0] = arr[0]
	
	for i in range(1, n):
		prefixSumArr[i] = prefixSumArr[i - 1] + arr[i]
		
	return prefixSumArr
```
# JavaScript
```js
function prefixSum(arr, n) {
	let prefixSumArr = new Array(n);
	// Initialize the first element
	prefixSumArr[0] = arr[0];
	
	for (let i = 1; i < n; i++) {
		prefixSumArr[i] = prefixSumArr[i - 1] + arr[i];
	}
	
	return prefixSumArr;
}
```
# Complexity Analysis
## Time Complexity
- **Preprocessing**: `O(n)`.
- **Range Query**: `O(1)`.
## Space Complexity
- **Auxiliary Space**: `O(n)`.
# References
## Articles
- [Mastering the Prefix Sum Design Pattern](https://medium.com/@chetanshingare2991/mastering-the-prefix-sum-design-pattern-a-step-by-step-guide-a7e369e68ea7)
- [Prefix Sum Array](https://www.geeksforgeeks.org/dsa/prefix-sum-array-implementation-applications-competitive-programming/)
## Videos
- [Prefix Sum in 4 minutes | LeetCode Pattern](https://www.youtube.com/watch?v=yuws7YK0Yng)

[[Data Structures and Algorithms MOC]]