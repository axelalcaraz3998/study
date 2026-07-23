Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Traversal
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 5 };
		
		for (int i = 0; i < arr.length; i++) {
			System.out.print(arr[i] + " ");
		}
		System.out.println("");
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 5]
n = len(arr)

for i in range(n):
	print(arr[i], end=" ")
print("")
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 5];

for (let i = 0; i < arr.length; i++) {
	process.stdout.write(arr[i] + " ");
}
console.log("");
```
# Insertion at Beginning
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 0 };
		int n = arr.length;
		int x = 5;
		
		// Shift elements to the right
		for (int i = n - 2; i >= 0; i--) {
			arr[i + 1] = arr[i];
		}
		// Insert new elment at the beginning
		arr[0] = x;
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 0]
n = len(arr)
x = 5

# Shift elements to the right
for i in range(n - 2, -1, -1):
	arr[i + 1] = arr[i]
# Insert new element at the beginning
arr[0] = x
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 0];
let n = arr.length;
let x = 5;

// Shift elements to the right
for (let i = n - 2; i >= 0; i--) {
	arr[i + 1] = arr[i];
}
// Insert new elment at the beginning
arr[0] = x;
```
# Insertion at Given Index
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 0 };
		int n = arr.length;
		int x = 5;
		int idx = 2;
		
		// Shift elements to the right
		for (int i = n - 2; i >= idx; i--) {
			arr[i + 1] = arr[i];
		}
		// Insert new elment at given index
		arr[idx] = x;
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 0]
n = len(arr)
x = 5
idx = 2

# Shift elements to the right
for i in range(n - 2, idx - 1, -1):
	arr[i + 1] = arr[i]
# Insert new element at given index
arr[idx] = x
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 0];
let n = arr.length;
let x = 5;
let idx = 2;

// Shift elements to the right
for (let i = n - 2; i >= idx; i--) {
	arr[i + 1] = arr[i];
}
// Insert new elment at given index
arr[idx] = x;
```
# Insertion at End
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 0 };
		int n = arr.length;
		int x = 5;
		
		// Insert new elment at the end
		arr[n - 1] = x;
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 0]
n = len(arr)
x = 5

# Insert new element at the end
arr[n - 1] = x
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 0];
let n = arr.length;
let x = 5;

// Insert new elment at the end
arr[n - 1] = x;
```
# Deletion From Beginning
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 5 };
		int n = arr.length;
		
		// Shift elements to the left
		for (int i = 1; i < n; i++) {
			arr[i - 1] = arr[i];
		}
		// Upate array size
		n = n - 1;
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 5]
n = len(arr)

# Shift elements to left
for i in range(1, n):
	arr[i - 1] = arr[i]
# Update array size
n = n -1
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 5];
let n = arr.length;

// Shift elements to the left
for (let i = 1; i < n; i++) {
	arr[i - 1] = arr[i];
}
// Update array size
n = n - 1;
```
# Deletion Of Given Index
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 5 };
		int n = arr.length;
		int idx = 2;
		
		// Shift elements to the left from given index
		for (int i = idx; i < n - 1; i++) {
			arr[i] = arr[i + 1];
		}
		// Upate array size
		n = n - 1;
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 5]
n = len(arr)
idx = 2

# Shift elements to left from given index
for i in range(idx, n - 1):
	arr[i] = arr[i + 1]
# Update array size
n = n -1
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 5];
let n = arr.length;
let idx = 2;

// Shift elements to the left from given index
for (let i = idx; i < n - 1; i++) {
	arr[i] = arr[i + 1];
}
// Update array size
n = n - 1;
```
# Deletion Of Given Element
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 5 };
		int n = arr.length;
		int ele = 3;
		
		boolean found = false;
		for (int i = 0; i < n; i++) {
			// If element has been found shift elements to the left
			if (found == true) {
				arr[i - 1] = arr[i];
			} else if (arr[i] == ele) {
				found = true;
			}
		}
		
		if (found == true) {
			n = n - 1;
		}
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 5]
n = len(arr)
ele = 3

found = False
for i in range(n):
	# If element has been found shift elements to the left
	if (found is True):
		arr[i - 1] = arr[i]
	elif arr[i] is ele:
		found = True

if found is True:
	n = n - 1
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 5];
let n = arr.length;
let ele = 3;

let found = false;
for (let i = 0; i < n; i++) {
	// If element has been found shift elements to the left
	if (found == true) {
		arr[i - 1] = arr[i];
	} else if (arr[i] == ele) {
		found = true;
	}
}

if (found == true) {
	n = n - 1;
}
```
# Deletion From end
## Java
```java
public class Main {

	public static void main(String[] args) {
		int[] arr = { 1, 2, 3, 4, 5 };
		int n = arr.length;
		
		// Upate array size
		n = n - 1;
	}

}
```
## Python
```python
arr = [1, 2, 3, 4, 5]
n = len(arr)

# Update array size
n = n -1
```
## JavaScript
```js
let arr = [1, 2, 3, 4, 5];
let n = arr.length;

// Update array size
n = n - 1;
```
# References
## Articles
- [Arrays in Java](https://www.geeksforgeeks.org/java/arrays-in-java/)
- [Python Lists](https://www.geeksforgeeks.org/python/python-lists/)
- [JavaScript Arrays](https://www.geeksforgeeks.org/javascript/javascript-arrays/)

[[Array]]