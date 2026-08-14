Tags: #ComputerScience #DSA 

A hash table is defined as a data structure used to insert, look up, and remove key-value pairs quickly. It operates on the hashing concept, where each key is translated by a hash function into a distinct index in an array. The index functions as a storage location for the matching value. In simple words, it maps the keys with the value.
![[hash-table.webp]]
# What is a Load Factor?
A hash table's load factor is determined by how many elements are kept there in relation to how big the table is. The table may be cluttered and have longer search times and collisions if the load factor is high. An idea load factor can be maintained with the use of a good hash function and proper table resizing.
# What is a Hash Function?
A hash function is a function that translates keys to array indices. The keys should be evenly distributed across the array via a decent hash function to reduce collisions and ensure quick lookup speeds.
- **Integer Universe Assumption**: The keys are assumed to be integers within a certain range according to the integer universe assumption. This enables basic hashing operations like division or multiplication hashing.
- **Hashing by Division**: This straightforward hashing technique uses the key's remaining value after dividing it by the array's size as the index. When an array size is a prime number and the keys are evenly spaced out, it performs well.
- **Hashing by Multiplication**: This straightforward hashing operation multiplies the key by a constant between 0 and 1 before taking the fractional portion of the outcome. After that, the index is determined by multiplying the fractional component by the array's size. Also, it functions effectively when the keys are scattered equally.
## Choosing a Hash Function
Selecting a decent hash function is based on the properties of the keys and the intended functionality of the hash table. Using a function that evenly distributes the keys and reduces collisions is crucial.
- To ensure that the number of collisions is kept to a minimum, a good hash function should distribute the keys throughout the hash table in a uniform manner. This implies that for all pairing keys, the likelihood of two keys hashing to the same position in the table should be rather constant.
- To enable speedy hashing and key retrieval, the hash function should be computationally efficient.
- It ought to be challenging to deduce the key from its hash value. As a result, attempts to guess the key using the hash value are less likely to succeed.
- A hash function should be flexible enough to adjust as the data being hashed changes. For instance, the hash function need to continue to perform properly if the keys being hashed change in size or format.
## Collision Resolution Techniques
Collisions happen when two or more keys point to the same array index. Chaining, open addressing, and double hashing are a few techniques for resolving collisions.
![[collision-in-hashing.webp]]
- **Open Addressing**: Collisions are handled by looking for the following empty space in the table. If the first slot is already taken, the hash function is applied to the subsequent slots until one is left empty. There are various ways to use this approach, including double hashing, linear probing, and quadratic probing.
- **Separate Chaining**: In separate chaining, a linked list of objects that hash to each slot is present. Two keys are included in the linked list if they hash to the same slot. This method is rather simple to use and can manage several collisions.
- **Robin Hood Hashing**: To reduce the length of the chain, collisions in Robin Hood hashing are addressed by switching off keys. The algorithm compares the distance between the slot and the occupied slot of the two keys if a new key hashes to an already-occupied slot. The existing key gets swapped out with the new one if it's closer to its ideal slot. This method has a tendency to cut down on collisions and average chain length.
# Implementation
See [[Hash Table Implementation]].
# References
## Articles
- [Hash Table Data Structure](https://www.geeksforgeeks.org/dsa/hash-table-data-structure/)
- [The Hash Table Data Structure: A Complete Guide](https://medium.com/@alejandro.itoaramendia/the-hash-table-data-structure-a-complete-guide-27fb7ebed2ff)
## Videos
- [Hash Table Data Structure](https://www.youtube.com/watch?v=jalSiaIi8j4)

[[Basic Data Structures]]