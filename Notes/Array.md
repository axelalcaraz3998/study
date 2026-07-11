Tags: #ComputerScience #DSA 

An array is a linear data structure consisting of a collection of elements (values or variables), of the same memory size, each identified by at least one array index or key. In general, an array is a mutable and linear collection of elements with the same data type. An array is stored such that the position (memory address) of each element can be computed from its index tuple by a mathematical formula. The simplest type of data structure is a linear array, also called a one-dimensional array.
# Types of Arrays
## Fixed Sized
In fixed sized arrays we cannot alter or update the size of the array. Here only a fixed size of memory will be allocated for storage.
## Dynamic Size
With dynamic size arrays, the size of the array changes as per user requirements during execution of code so the coders do not have to worry about sizes. They can add and remove the elements as per needed. The memory is mostly dynamically allocated and de-allocated in these types of arrays.
## One-Dimensional
With one-dimensional arrays, you can imagine a 1D array as a row, where elements are stored one after another.
![[one-dimensional-array.webp]]
## Multi-Dimensional
A multi-dimensional array is an array with more than one dimension. We can use multidimensional arrays to store complex data in the forms of tables.
### Two-Dimensional Array
2D multidimensional arrays can be considered as an array of arrays or as a matrix consisting of rows and columns.
![[two-dimensional-array.webp]]
### Three-Dimensional Array
A 3D multidimensional array contains three dimensions, so it can be considered an array of two-dimensional arrays.
![[three-dimensional-array.webp]]
# Applications of Arrays
- **Storing and Accessing Data**: Arrays store elements in a specific order and allow a constant-time `O(1)` access to any element.
- **Searching**: If data in an array is sorted, we can search an item in `O(log n)` time. We can also find `floor()`, `celing()`, k-th smallest, k-th largest, etc efficiently.
- **Matrices**: Two-dimensional arrays are used for matrices in computations like graph algorithms and image processing.
- **Implementing Other Data Structures**: Arrays are used as the underlying data structure for implementing stacks and queues.
- **Dynamic Programming**: Dynamic programming algorithms often use arrays to store intermediate results of subproblems in order to solve a larger problem.
- **Data Buffers**: Arrays serve as data buggers and queues, temporarily storing incoming data like network packets, file streams, and database results before processing.s
# Advantages of Arrays
- **Efficient and Fast Access**: Arrays allow direct and efficient access to any element in the collection with constant access time, as the data is stored in contiguous memory locations.
- **Memory Efficiency**: Arrays store elements in contiguous memory, allowing efficient allocation in a single block and does not require extra storage for linking different blocks.
- **Versatility**: Arrays can be used to store wide range of data types, including integers, floating-point numbers, characters, and even complex data structures such as objects and pointers.
- **Compatibility with Hardware**: The array data structure is compatible with most hardware and architectures, making it a versatile tool for programming in a wide range of environments.
# Disadvantages of Arrays
- **Fixed Size**: Arrays have a fixed size set at creation. Expanding an array requires creating a new one and copying elements, which is time-consuming and memory-intensive. Even dynamic size arrays internally use fixed-size memory allocation and de-allocation.
- **Memory Allocation Issues**: Allocating large arrays can cause memory exhaustion, leading to crashes, specially on systems with limited resources.
- **Insertion and Deletion Challenges**: Adding or removing elements requires shifting subsequent elements, making these operations inefficient.
# References
## Articles
- [Array (data structure)](https://en.wikipedia.org/wiki/Array_(data_structure))
- [Array Data Structure](https://www.geeksforgeeks.org/dsa/array-data-structure-guide/
- [Array Introduction](https://www.geeksforgeeks.org/dsa/introduction-to-arrays-data-structure-and-algorithm-tutorials/)
- [Applications, Advantages and Disadvantages of Array](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-array-data-structure/)

[[Basic Data Structures]]