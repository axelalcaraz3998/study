Tags: #ComputerScience #SystemDesign 

Availability means that the system responds to a request even when there is a failure. The response might be outdated, but the key here is to keep you moving. This is often measured in terms of the percentage of time that the system is up and running, also known as its uptime.

Consistency ensures that all nodes in a distributed system reflect the most recent write. Everyone sees the same data, no matter which server they interact with. This is important for maintaining the integrity of the data stored in the system.

In distributed systems, it is often a trade-off between availability and consistency. Systems that prioritize high availability may sacrifice consistency, while systems that prioritize consistency may sacrifice availability.
## CAP Theorem
The CAP theorem states that, in a distributed system, you can only have two out of the following three guarantees: Consistency, Availability and Partition Tolerance, one of these must be sacrificed.

See [[CAP Theorem]]
# References
## Articles
- [Availability VS Consistency: The Backbone of Distributed Systems](https://medium.com/@Saravanansd/availability-vs-consistency-the-backbone-of-distributed-systems-e0aca8f441d7)

[[System Design MOC]]