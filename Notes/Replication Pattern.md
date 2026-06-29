Tags: #ComputerScience #SystemDesign 

Replication is a strategy that involves storing multiple copies of data across different locations. This redundancy ensures that even if one location experiences failure, the data can still be accessed from another.

There are three types of replication techniques based on architecture: Single-leader replication (master-slave), multi-leader replication (master-master), and no-leader replication.
# Single-leader Architecture (Master-Slave)
In single-leader replication, there is a single leader (master) and several follower replicas (slaves). All write requests are served by the leader node and all read requests are served by the leader or any of the follower nodes. The best idea would be to use the leader only for write requests and distribute read requests across followers.
- After serving the write request, the leader node sends a stream of data changes to the follower nodes to update their current state of data.
- As write operations are concentrated on a single node, if the node fails, the system may become unavailable until a new leader is elected.
- During the replication process, we need to handle one of the critical problems, reads from follower nodes may not reflect the latest change as there can be some delay in the replication process (replication lag).
- This architecture is a good option when read-write ratio is very high.
![[single-leader-replication.png]]
# Multi-leader Architecture (Master-Master)
In multi-leader replication, clients can send write requests to one of the leader nodes, and each leader node works as a follower for the other leader. So whenever a leader node performs the write operation, it will forward streams of data change to all other leader nodes.

Conflicts can arise when two or more leader nodes receive conflicting write requests simultaneously. So it's important to have conflict resolution mechanisms in place to ensure data consistency.
- When data needs to be available in multiple regions, a multi-leader architecture can help reduce latency and improve performance. The idea is simple, each region can designate its own leader node.
- By having multiple leader nodes, a multi-leader architecture can provide redundancy and ensure that the system remains available even if one or more nodes fail. It can also enable write scaling because write requests can be distributed across multiple nodes.
![[multi-leader-replication.png]]
# No-leader Architecture
In no-leader replication, clients send write requests to several nodes and read from several nodes in parallel. There is no concept of leader, which allows any replica to directly accept writes from the clients.

Leaderless replication can provide high availability and fault tolerance. Because there is no single point of failure, the system can continue to function even if some nodes fail. It can also provide high read and write throughput because requests can be distributed across multiple nodes.

This method also poses challenges for synchronization, as it can be difficult to ensure that all nodes have the same view of the data at all times. In addition, handling conflicts that may arise from concurrent writes can be complex.
# References
## Articles
- [System Design: Availability Patterns](https://dev.to/decoders_lord/system-design-availability-patterns-104i)
- [Introduction to Database Replication](https://www.enjoyalgorithms.com/blog/introduction-to-database-replication-system-design)
- [Master-Slave Replication](https://www.enjoyalgorithms.com/blog/master-slave-replication-databases)
## Videos
- [Availability | System Design Interview Basics 2022](https://www.youtube.com/watch?v=WC7kpQPGPp8)

[[Availability Patterns]]