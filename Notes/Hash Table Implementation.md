Tags: #ComputerScience #DSA #Java #Python #JavaScript 
# Java
```java
import java.util.List;
import java.util.ArrayList;
import java.util.Objects;

class HashNode<K, V> {
	K key;
	V value;
	HashNode<K, V> next;
	final int hashCode;
	
	public HashNode(K key, V value, int hashCode) {
		this.key = key;
		this.value = value;
		this.hashCode = hashCode;
	}
}

class HashTable<K, V> {
	List<HashNode<K, V>> bucketArray;
	int numBuckets;
	int size;
	
	public HashTable() {
		bucketArray = new ArrayList<>();
		numBuckets = 10;
		size = 0;
		
		// Populate with empty chains
		for (int i = 0; i < numBuckets; i++) {
			bucketArray.add(null);
		}
	}
	
	public void add(K key, V value) {
		int bucketIndex = getBucketIndex(key);
		int hashCode = hashCode(key);
		
		HashNode<K, V> head = bucketArray.get(bucketIndex);
		while (head != null) {
			if (head.key.equals(key) && head.hashCode == hashCode) {
				head.value = value;
				
				return;
			}
			
			head = head.next;
		}
		
		// Insert key in chain
		size++;
		head = bucketArray.get(bucketIndex);
		HashNode<K, V> newNode = new HashNode<>(key, value, hashCode);
		newNode.next = head;
		bucketArray.set(bucketIndex, newNode);
		
		// Double hash table size if load factor goes beyond treshold
		if ((1.0 * size) / numBuckets >= 0.7) {
			List<HashNode<K, V>> temp = bucketArray;
			bucketArray = new ArrayList<>();
			numBuckets *= 2;
			size = 0;
			
			for (int i = 0; i < numBuckets; i++) {
				bucketArray.add(null);
			}
			
			for (HashNode<K, V> headNode : temp) {
				while (headNode != null) {
					add(headNode.key, headNode.value);
					headNode = headNode.next;
				}
			}
		}
	}
	
	public V get(K key) {
		int bucketIndex = getBucketIndex(key);
		int hashCode = hashCode(key);
		
		HashNode<K, V> head = bucketArray.get(bucketIndex);
		while (head != null) {
			if (head.key.equals(key) && head.hashCode == hashCode) {
				return head.value;
			}
			
			head = head.next;
		}
		
		return null;
	}
	
	public V remove(K key) {
		int bucketIndex = getBucketIndex(key);
		int hashCode = hashCode(key);
		
		HashNode<K, V> head = bucketArray.get(bucketIndex);
		HashNode<K, V> prev = null;
		while (head != null) {
			if (head.key.equals(key) && hashCode == head.hashCode) {
				break;
			}
			
			prev = head;
			head = head.next;
		}
		
		if (head == null) {
			return null;
		}
		
		size--;
		if (prev != null) {
			prev.next = head.next;
		} else {
			bucketArray.set(bucketIndex, head.next);
		}
		
		return head.value;
	}
	
	public int getSize() {
		return size;
	}
	
	public boolean isEmpty() {
		return size == 0;
	}
	
	private int hashCode(K key) {
		return Objects.hashCode(key);
	}
	
	private int getBucketIndex(K key) {
		int hashCode = hashCode(key);
		int index = hashCode % numBuckets;
		index = index < 0 ? index * -1 : index;
		
		return index;
	}
}

class Main {
	
	public static void main(String[] args) {
		HashTable<String, Integer> hashTable = new HashTable<>();
		
		hashTable.add("John", 12);
		hashTable.add("Maria", 16);
		hashTable.add("Marcus", 15);
		
		System.out.println(hashTable.getSize());
		System.out.println(hashTable.remove("Marcus"));
		System.out.println(hashTable.get("John"));
	}
	
}
```
# Python
```python
class HashNode:
    def __init__(self, key, value, hash_code):
        self.key = key
        self.value = value
        self.next = None
        self.hash_code = hash_code


class HashTable:
    def __init__(self):
        self.bucket_array = [None] * 10
        self.num_buckets = 10
        self.size = 0
	
    def add(self, key, value):
        bucket_index = self._get_bucket_index(key)
        hash_code = self._hash_code(key)
		
        head = self.bucket_array[bucket_index]
		
        # Check whether key already exists
        while head is not None:
            if head.key == key and head.hash_code == hash_code:
                head.value = value
                return
			
            head = head.next
		
        # Insert key at the beginning of the chain
        self.size += 1
		
        head = self.bucket_array[bucket_index]
        new_node = HashNode(key, value, hash_code)
        new_node.next = head
        self.bucket_array[bucket_index] = new_node
		
        # Resize if load factor >= 0.7
        if self.size / self.num_buckets >= 0.7:
            old_bucket_array = self.bucket_array
			
            self.num_buckets *= 2
            self.bucket_array = [None] * self.num_buckets
            self.size = 0
			
            # Rehash all existing entries
            for head_node in old_bucket_array:
                while head_node is not None:
                    self.add(head_node.key, head_node.value)
                    head_node = head_node.next

    def get(self, key):
        bucket_index = self._get_bucket_index(key)
        hash_code = self._hash_code(key)
		
        head = self.bucket_array[bucket_index]
		
        while head is not None:
            if head.key == key and head.hash_code == hash_code:
                return head.value
			
            head = head.next
		
        return None
	
    def remove(self, key):
        bucket_index = self._get_bucket_index(key)
        hash_code = self._hash_code(key)
		
        head = self.bucket_array[bucket_index]
        prev = None
		
        while head is not None:
            if head.key == key and head.hash_code == hash_code:
                break
		
            prev = head
            head = head.next
		
        if head is None:
            return None
		
        self.size -= 1
		
        if prev is not None:
            prev.next = head.next
        else:
            self.bucket_array[bucket_index] = head.next
		
        return head.value
	
    def get_size(self):
        return self.size

    def is_empty(self):
        return self.size == 0

    def _hash_code(self, key):
        return hash(key)

    def _get_bucket_index(self, key):
        hash_code = self._hash_code(key)
        return abs(hash_code % self.num_buckets)


hash_table = HashTable()

hash_table.add("John", 12)
hash_table.add("Maria", 16)
hash_table.add("Marcus", 15)

print(hash_table.get_size())
print(hash_table.remove("Marcus"))
print(hash_table.get("John"))
```
# JavaScript
```js
class HashNode {
    constructor(key, value, hashCode) {
        this.key = key;
        this.value = value;
        this.next = null;
        this.hashCode = hashCode;
    }
}


class HashTable {
    constructor() {
        this.bucketArray = new Array(10).fill(null);
        this.numBuckets = 10;
        this.size = 0;
    }
	
    add(key, value) {
        const bucketIndex = this.getBucketIndex(key);
        const hashCode = this.hashCode(key);
		
        let head = this.bucketArray[bucketIndex];
		
        // Check whether key already exists
        while (head !== null) {
            if (head.key === key && head.hashCode === hashCode) {
                head.value = value;
                return;
            }
			
            head = head.next;
        }
		
        // Insert key at the beginning of the chain
        this.size++;
		
        head = this.bucketArray[bucketIndex];
		
        const newNode = new HashNode(key, value, hashCode);
        newNode.next = head;
		
        this.bucketArray[bucketIndex] = newNode;
		
        // Resize if load factor >= 0.7
        if (this.size / this.numBuckets >= 0.7) {
            const oldBucketArray = this.bucketArray;
			
            this.numBuckets *= 2;
            this.bucketArray = new Array(this.numBuckets).fill(null);
            this.size = 0;
			
            // Rehash all existing entries
            for (let headNode of oldBucketArray) {
                while (headNode !== null) {
                    this.add(headNode.key, headNode.value);
                    headNode = headNode.next;
                }
            }
        }
    }
	
    get(key) {
        const bucketIndex = this.getBucketIndex(key);
        const hashCode = this.hashCode(key);
		
        let head = this.bucketArray[bucketIndex];
		
        while (head !== null) {
            if (head.key === key && head.hashCode === hashCode) {
                return head.value;
            }
			
            head = head.next;
        }
		
        return null;
    }
	
    remove(key) {
        const bucketIndex = this.getBucketIndex(key);
        const hashCode = this.hashCode(key);
		
        let head = this.bucketArray[bucketIndex];
        let prev = null;
		
        while (head !== null) {
            if (head.key === key && head.hashCode === hashCode) {
                break;
            }
			
            prev = head;
            head = head.next;
        }
		
        if (head === null) {
            return null;
        }
		
        this.size--;
		
        if (prev !== null) {
            prev.next = head.next;
        } else {
            this.bucketArray[bucketIndex] = head.next;
        }
		
        return head.value;
    }
	
    getSize() {
        return this.size;
    }
	
    isEmpty() {
        return this.size === 0;
    }
	
    hashCode(key) {
        if (key === null || key === undefined) {
            return 0;
        }
		
        if (typeof key === "string") {
            let hash = 0;
			
            for (let i = 0; i < key.length; i++) {
                hash = ((hash << 5) - hash) + key.charCodeAt(i);
                hash |= 0; // Convert to signed 32-bit integer
            }
			
            return hash;
        }
		
        // Simple handling for numbers
        if (typeof key === "number") {
            return key | 0;
        }
		
        // Fallback for other objects
        return this.objectHashCode(key);
    }
	
    objectHashCode(obj) {
        // Assign a stable hash to objects
        if (!obj.__hashCode) {
            Object.defineProperty(obj, "__hashCode", {
                value: HashTable.nextHashCode++,
                enumerable: false,
                writable: false
            });
        }
		
        return obj.__hashCode;
    }
		
    getBucketIndex(key) {
        const hashCode = this.hashCode(key);
		
        return Math.abs(hashCode % this.numBuckets);
    }
}

HashTable.nextHashCode = 1;

const hashTable = new HashTable();

hashTable.add("John", 12);
hashTable.add("Maria", 16);
hashTable.add("Marcus", 15);

console.log(hashTable.getSize());
console.log(hashTable.remove("Marcus"));
console.log(hashTable.get("John"));

```
# References
## Articles
- [Implementing Our Own Hash Table with Separate Chaining](https://www.geeksforgeeks.org/java/implementing-our-own-hash-table-with-separate-chaining-in-java/)

[[Hash Table]]