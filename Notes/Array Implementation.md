Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Java
## Array Declaration
```java
int size = 5;
int[] array = new int[size];
```
## Array Initialization
```java
int[] array = new int[]{ 1, 2, 3 };
```
## Access Array Element
```java
int[] array = new int[]{ 2, 3, 8, 11, 14 };
// Output: 8
System.out.println(array[2]);
```
## Update Array Element
```java
int[] array = new int[]{ 2, 3, 8, 11, 14 };
// Array is now: [2, 90, 8, 11, 14]
array[1] = 90;
```
## Traverse Array
```java
int[] array = new int[]{ 2, 4, 8, 16, 32, 64 };
for (int i = 0; i < array.length; i++) {
	// Output: 2, 4, 8, 16, 32, 64
	System.out.print(array[i] + " ");
}
```
# Python
## Array Declaration
```python
# Empty list
my_list = []

# List of fixed size
size = 5
my_list_fixed_size = [None] * size
```
## Array Initialization
```python
my_list = [1, 2, 3]
```
## Access Array Element
```python
my_list = [2, 3, 8, 11, 14]
# Output: 8
print(my_list[2])
```
## Update Array Element
```python
my_list = [2, 3, 8, 11, 14]
# Array is now: [2, 90, 8, 11, 14]
my_list[1] = 90 
```
## Adding Elements
```python
my_list = [2, 3, 8, 11, 14]
# Array is now: [2, 3, 8, 11, 14, 16]
my_list.append(16)
```
## Removing Elements
```python
my_list = [2, 3, 8, 11, 14]
# Array is now: [2, 3, 11, 14]
my_list.remove(8)
```
## Traverse Array
```python
my_list = [2, 4, 8, 16, 32, 64]
for item in my_list:
	# Output: 2, 4, 8, 16, 32, 64
	print(item)
```
# JavaScript
## Array Declaration
```js
// Emtpy array
let array = [];
```
## Array Initialization
```js
let array = [1, 2, 3];
```
## Access Array Element
```js
let array = [2, 3, 8, 11, 14];
// Output: 8
console.log(array[2]);
```
## Update Array Element
```js
let array = [2, 3, 8, 11, 14];
// Array is now: [2, 90, 8, 11, 14]
array[1] = 90;
```
## Adding Elements
```js
let array = [2, 3, 8, 11, 14];
// Array is now: [2, 3, 8, 11, 14, 16]
array.push(16);
```
## Removing Elements
```js
let array = [2, 3, 8, 11, 14];
// Array is now: [2, 3, 8, 11]
array.pop();
```
## Traverse Array
```js
let array = [2, 4, 8, 16, 32, 64];
for (int i = 0; i < array.length; i++) {
	// Output: 2, 4, 8, 16, 32, 64
	console.log(array[i]);
}
```
# References
## Articles
- [Arrays in Java](https://www.geeksforgeeks.org/java/arrays-in-java/)
- [Python Lists](https://www.geeksforgeeks.org/python/python-lists/)
- [JavaScript Arrays](https://www.geeksforgeeks.org/javascript/javascript-arrays/)

[[Array]]