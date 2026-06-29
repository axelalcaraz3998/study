Tags: #ComputerScience #SystemDesign 

Consistency patterns refer to the ways in which data is stored and managed in a distributed system, and how that data is made available to users and applications. There are three main types of consistency patterns:
# Weak Consistency
After an update is made to the data, it is not guaranteed that any subsequent read operations will immediately reflect the changes made. The read may or may not see the recent write.

In a weakly consistent system, updates to the data may not be immediately propagated. This can lead to inconsistencies and conflicts between different versions of the data, but it also allows for high availability and low latency.
# Eventual Consistency
Eventual consistency is a form of weak consistency. After an update is made to the data, it will be eventually visible to any subsequent read operations. The data is replicated in an asynchronous manner, ensuring that all copies of the data are eventually updated.

In an eventually consistent system, data is typically stored in multiple locations, and updates to that data are eventually propagated to all locations. This means that the system is highly available and has low latency, but it also means that there may be inconsistencies and conflicts between different versions of the data.
# Strong Consistency
After an update is made to the data, it will be immediately visible to any subsequent read operations. The data is replicated in a synchronous manner, ensuring that all copies of the data are updated at the same time.

In a strong consistency system, any updates to some data are immediately propagated to all locations. This ensures that all locations have the same version of the data, but it also means that the system is not highly available and has high latency.
# References
## Articles
- [Consistency Patterns in Distributed Systems](https://cs.fyi/guide/consistency-patterns-week-strong-eventual)

[[System Design MOC]]