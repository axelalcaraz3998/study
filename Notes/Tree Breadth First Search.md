Tags: #ComputerScience #DSA #Java #Python #JavaScript 

Breadth-First-Search (BFS) is a traversal algorithm that explores all the vertices of a graph or tree level by level. It starts with the root node, or an arbitrary node and visits all the nodes at the same level before moving on to the next level.

The algorithm works by maintaining a queue of nodes that need to be visited. It starts by adding the initial node to the quue and marking it as visited. Then, it dequeues the node from the front of the queue and visits all its neighboring nodes that haven't been visited yet.

Each unvisited neighboring node is added to the back of the queue. The algorithm continues dequeuing nodes and visiting their neighbors until the queue is empty.
![[tree-breadth-first-search.jpg]]
# Java
```java
import java.util.List;
import java.util.ArrayList;

class Node {
	
	int data;
	Node left;
	Node right;
	
	Node(int data) {
		this.data = data;
		left = null;
		right = null;
	}
	
}

public class Main {
	
	private static void levelOrderTraversalHelper(Node root, int level, List<List<Integer>> result) {
		if (root == null) {
			return;
		}
		
		// If level has not been visited append array
		if (result.size() <= level) {
			result.add(new ArrayList<>());
		}
		
		// Add data to corresponding level
		result.get(level).add(root.data);
		
		levelOrderTraversalHelper(root.left, level + 1, result);
		levelOrderTraversalHelper(root.right, level + 1, result);
	}
	
	private static List<List<Integer>> levelOrderTraversal(Node root) {
		List<List<Integer>> result = new ArrayList<>();
		levelOrderTraversalHelper(root, 0, result);
		
		return result;
	}
	
	public static void main(String[] args) {
		Node root = new Node(0);
		root.left = new Node(1);
		root.right = new Node(2);
		root.left.left = new Node(3);
		root.left.right = new Node(4);
		root.right.left = new Node(5);
		root.right.right = new Node(6);
		
		List<List<Integer>> result = levelOrderTraversal(root);
		for (List<Integer> level : result) {
			for (int data : level) {
				System.out.print(data + " ");
			}
			System.out.println("");
		}
	}
	
}
```
# Python
```python
class Node:
	def __init__(self, data):
		self.data = data
		self.left = None
		self.right = None

def level_order_traversal_helper(root, level, result):
	if root is None:
		return
	
	# If level has not been visited append list
	if len(result) <= level:
		result.append([])
	
	# Add data to corresponding level	
	result[level].append(root.data)
	
	level_order_traversal_helper(root.left, level + 1, result)
	level_order_traversal_helper(root.right, level + 1, result)

def level_order_traversal(root):
	result = []
	level_order_traversal_helper(root, 0, result)
	
	return result

root = Node(0)
root.left = Node(1);
root.right = Node(2);
root.left.left = Node(3);
root.left.right = Node(4);
root.right.left = Node(5);
root.right.right = Node(6);

result = level_order_traversal(root)
for level in result:
	for data in level:
		print(data, end=" ")
	print("")
```
# JavaScript
```js
class Node {
	
	constructor(data) {
		this.data = data;
		this.left = null;
		this.right = null;
	}
	
}

function levelOrderTraversalHelper(root, level, result) {
	if (root == null) {
		return;
	}
	
	// If level has not been visited append array]
	if (result.length <= level) {
		result.push([]);
	}
	
	// Add data to corresponding level
	result[level].push(root.data);
	
	levelOrderTraversalHelper(root.left, level + 1, result);
	levelOrderTraversalHelper(root.right, level + 1, result);	
}

function levelOrderTraversal(root) {
	let result = Array();
	levelOrderTraversalHelper(root, 0, result);
	
	return result;
}

let root = new Node(0);
root.left = new Node(1);
root.right = new Node(2);
root.left.left = new Node(3);
root.left.right = new Node(4);
root.right.left = new Node(5);
root.right.right = new Node(6);

let result = levelOrderTraversal(root);
for (let level of result) {
	for (let data of level) {
		process.stdout.write(data + " ");
	}
	console.log("");
}
```
# References
## Articles
- [Getting Started with Trees: Breadth First Search (BFS)](https://medium.com/@elfrmkr98/getting-started-with-trees-breadth-first-search-bfs-344dc92cbd30)
- [Level Order Traversal (Breadth-First-Search) of Binary Tree](https://www.geeksforgeeks.org/dsa/level-order-tree-traversal/)
## Videos
- [Breadth-First-Search in 4 minutes](https://www.youtube.com/watch?v=HZ5YTanv5QE)

[[Tree Data Structure]]