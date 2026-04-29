Tags: #ComputerScience #DSA #Java #Python #JavaScript
# Array data structure
An array is a fundamental and linear data structure that stores items at contiguous locations. It offers mainly the following advantages over other data structures.
- Random Access: i-th item can be accessed in O(1) time as we have the base address and every item or reference is of same size.
- Cache Friendliness: Since items / references are stored at contiguous locations, we get the advantage of locality of reference.
An array is not useful in places where we have to operations like insert in the middle, delete from the middle and search unsorted data.
# Memory representation of an array
In an array, all the elements or their references are stored in contiguous memory locations. This allows for efficient access and manipulation of elements.
For example, an array of twelve 4-byte integer variables, with indices 0 through 11, may be stored at memory addresses 200, 204, 208, ..., 244, to that the element with index _i_ has the address 200 + (_i_ \*4). The memory address of the first element of an array is called first address, foundation address or base address.
![[memory-representation-of-array.jpg]]
# Arrays in different programming languages
## Java
```java
// Array initialization
int[] numbers = new int[]{ 1, 2, 3, 4, 5 };

// Accesing an element
System.out.println(numbers[0]); // Output: 1
```
## Python
```python
# Array initialization
numbers = [1, 2, 3, 4, 5]

# Accesing and element
print(numbers[0]) # Output: 1
```
## JavaScript
```javascript
// Array initialization
const numbers = [1, 2, 3, 4, 5];

// Accesing an element
console.log(numbers[0]); // Output: 1
```
# References
- https://www.geeksforgeeks.org/dsa/array-data-structure-guide/
- https://www.geeksforgeeks.org/dsa/introduction-to-arrays-data-structure-and-algorithm-tutorials/
- https://en.wikipedia.org/wiki/Array_(data_structure)
- https://www.w3schools.com/java/java_arrays.asp
- https://www.w3schools.com/python/python_arrays.asp
- https://www.w3schools.com/js/js_arrays.asp