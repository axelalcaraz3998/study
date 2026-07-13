Tags: #ComputerScience #DSA #Java #Python #JavaScript 

The two pointers technique is a simple yet powerful strategy where you use two indices (pointers) that traverse a data structure, such as an array, list, or string, either toward each other or in the same direction to solve problems more efficiently.

When to use two pointers:
- **Sorted Input**: If the array is already sorted (or can be sorted), two pointers can efficiently find pairs of ranges.
- **Pairs of Subarrays**: When the problem asks about two elements, subarrays, or ranges instead of working with single elements.
- **Sliding Window Problems**: When you need to maintain a window of elements that grows/shrinks based on conditions.

There are three main strategies for using two pointers:
- **Inward Traversal**: This approach has pointers starting at opposite ends of the data structure and moving inward toward each other.
- **Unidirectional Traversal**: In this approach, both pointers start at the same end of the data structure and move in the same direction.
- **Staged Traversal**: In this approach, we traverse with one pointer, and when it lands on an element that meets a certain condition, we traverse with the second pointer.
# Java
```java
private static String reverseString(String s) {
	int n = s.length();
	char[] charArr = s.toCharArray();
	
	int left = 0, right = n - 1;
	while (left < right) {
		char temp = charArr[left];
		charArr[left] = charArr[right];
		charArr[right] = temp;
		
		left++;
		right--;
	}
	
	return new String(charArr);
}
```
# Python
```python
def reverse_string(s): 
	n = len(charr_arr)
    char_arr = list(s)

    left, right = 0, n - 1
    while left < right:
		char_arr[left], char_arr[right] = char_arr[right], char_arr[left]
        
        left += 1
        right -= 1

    return "".join(char_arr)
```
# JavaScript
```js
function reverseString(s) {
	let n = s.length;
	let charArr = s.split("");
	
	let left = 0, right = n -1;
	while (left < right) {
		let temp = charArr[left];
		charArr[left] = charArr[right];
		charArr[right] = temp;
		
		left++;
		right--;
	}
	
	return charArr.join("");
}
```
# Complexity Analysis
## Time Complexity
- **Average Case**: `O(n)`.
## Space Complexity
- **Auxiliary Space**: `O(1)`.
# References
## Articles
- [Two Pointers Technique](https://www.geeksforgeeks.org/dsa/two-pointers-technique/)
- [Introduction to Two Pointers](https://bytebytego.com/courses/coding-patterns/two-pointers/introduction-to-two-pointers)
## Videos
- [Two Pointers in 7 Minutes | LeetCode Pattern](https://www.youtube.com/watch?v=QzZ7nmouLTI)

[[Data Structures and Algorithms MOC]]