Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Sliding window is a method used to solve problems that involve subarrays or substring or window.
- Instead of repeatedly iterating over the same elements, the sliding window maintains a range that moves step-by-step through the data, updating results incrementally.
- The main idea is to use the results of previous window to do computations for the next window.
- Commonly used for problems like finding subarrays with a specific sum, finding the longest substring with unique characters, or solving problems that require a fixed-size window to process elements efficiently.
![[sliding-window.webp]]
# Java
```java
private static int maxSubArrSum(int[] nums, int k) {
	int n = nums.length;
	
	int windowSum = 0;
	for (int i = 0; i < k; i++) {
		windowSum += nums[i];
	}
	
	int maxSum = windowSum;
	for (int i = k; i < n; i++) {
		windowSum += nums[i] - nums[i - k];
		result = Math.max(maxSum, windowSum);
	}
	
	return maxSum;
}
```
# Python
```python
def maxSubArrSum(nums, k):
	n = len(nums)

	window_sum = sum(arr[:k])
	
	max_sum = window_sum
	for i in range(k, n):
		window_sum = window_sum + nums[i] - nums[i - k]
		max_sum = max(max_sum, window_sum)
		
	return max_sum
```
# JavaScript
```js
function maxSubArrSum(nums, k) {
	let n = nums.length;
	
	let windowSum = 0;
	for (let i = 0; i < k; i++) {
		windowSum += nums[i];
	}
	
	let maxSum = windowSum;
	for (let i = k; i < n; i++) {
		windowSum += nums[i] - nums[i - k];
		result = Math.max(maxSum, windowSum);
	}
	
	return maxSum;
}
```
# Complexity Analysis
## Time Complexity
- **Average Case**: `O(n)`.
## Space Complexity
- **Auxiliary Space**: `O(1)`.
# References
## Articles
- [Mastering Sliding Window Technique](https://medium.com/@rishu__2701/mastering-sliding-window-techniques-48f819194fd7)
## Videos
- [Sliding Window in 7 minutes | LeetCode Pattern](https://www.youtube.com/watch?v=y2d0VHdvfdc)

[[Data Structures and Algorithms MOC]]