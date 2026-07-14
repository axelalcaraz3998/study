Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Top K Elements is a useful pattern to find the K largest, K smallest, or K most frequent elements in a dataset.

This pattern can be applied to problems like:
- Finding the top 5 highest scores in a game leaderboard.
- Retrieving the 3 most frequent words in a document.

A straightforward approach to solve these types of problems is to sort the entire dataset and take the first or last K elements, but this approach isn't the most optimal approach since sorting takes `O(nlogn)` time. The top K elements pattern allows us to solve this problem more optimally using heaps, bringing down the time complexity down from `O(nlogn)` to `O(nlogk)`
# References
## Articles
- [Top K Elements](https://algomaster.io/learn/dsa/top-k-elements-introduction)
## Videos
- [Top K Elements in 6 minutes | LeetCode Pattern](https://www.youtube.com/watch?v=6_v6OoxvMOE)

[[Data Structures and Algorithms MOC]]