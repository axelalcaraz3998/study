Tags: #ComputerScience #DSA 

Asymptotic notation is a language that allows us to analyzed an algorithm's running time by identifying its behavior as the input size for the algorithm increases. This is also known as algorithm's growth rate.

You can label an algorithm with an asymptotic notation in many different ways. Some examples are, you can describe an algorithm by its best case, worst case, or average case. The most common is to analyze an algorithm by its worst case. You typically don't evaluate by best case because those conditions aren't what you're planning for.
# Big-O
Big-O, commonly written as `O`, is an asymptotic notation for the worst case, or ceiling of growth for a given function. It provides us with an asymptotic upper bound for the growth rate of the runtime of an algorithm.
# Big-Omega
Big-Omega, commonly written as `Ω`, is an asymptotic notation for the best case, or a floor growth rate for a given function. It provides us with an asymptotic lower bound for the growth of the runtime of an algorithm.
# Big-Theta
Big-Theta, commonly written as `Θ`, is an asymptotic notation to denote the asymptotically tight bound on the growth rate of runtime of an algorithm. Theta notation provides and exact bound on time or space complexity as it bounds a function from both upper and lower side. Compared to Big-O or Big-Omega, it gives more information in cases where we have exact bound available and should be preferred.
# Common Runtimes
![[big-o-cheat-sheet.png|697]]
- **Constant Time - `O(1)`**: The runtime of the algorithm does not depend on the input size.
- **Logarithmic Time - `O(log n)`**: The runtime of the algorithm grows logarithmically with the input size.
- **Linear Time - `O(n)`**: The runtime of the algorithm grows linearly with the input size.
- **Square Root Time - `O(√n)`**: The runtime of the algorithm grows as the square root of the input size.
- **Loglinear Time `O(n log n)`**: The runtime of the algorithm combines linear time and logarithmic time.
- **Bilinear Time - `O(n*m)`**: This is the complexity of a nested loop where the inner loop runs `m` tines for each iteration of the outer loop.
- **Quadratic Time - `O(n^2)`**: The runtime of the algorithm grows quadratically with the input size. This typically happens when we do `n*n` operations, such as a nested loop over the same array.
- **Cubic Time - `O(n^3)`**: The runtime of the algorithm grows cubically with the input size.
- **Exponential Time - `O(2^n)`**: The runtime of the algorithm grows exponentially with the input size. This often appears in include/exclude decision trees, such as generating all subsets of `n` elements.
- **Factorial time - `O(!n)`**: The runtime of the algorithm grows factorially with the input size. This often appears when generating all permutations of `n` distinct elements, where order matters.
# Common Data Structure Operations
![[common-data-structure-operations.png]]
# Array Sorting Algorithms
![[array-sorting-algorithms.png]]
# References
## Articles
- [Asymptotic Notation](https://learnxinyminutes.com/asymptotic-notation/)
- [Big O Notation Cheat Sheet](https://neetcode.io/cheatsheets/big-o-notation)
- [Big-O Algorithm Complexity Cheat Sheet](https://www.bigocheatsheet.com/)

[[Data Structures and Algorithms MOC]]