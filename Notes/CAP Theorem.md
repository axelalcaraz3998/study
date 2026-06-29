Tags: #ComputerScience #SystemDesign 

The CAP theorem states that, in a distributed system, you can only have two out of the following three guarantees across a read/write pair: Consistency, Availability and Partition Tolerance, one of these must be sacrificed.
- **Consistency**: A read is guaranteed to return the most recent write for a given client.
- **Availability**: A non-failing node will return a reasonable response within a reasonable amount of time.
- **Partition Tolerance**: The system will continue to function when network partition occur.
Given that networks aren't completely reliable, you must tolerate partitions in a distributed system. You'll need to make a trade-off between consistency and availability.
- **Consistency/Partition Tolerance (CP)**: Wait for a response from the partitioned node which could result in a timeout error. The system can also choose to return an error, depending on the scenario you desire. Choose consistency over availability when your business requirements dictate atomic reads and writes, such as in a banking app.
- **Availability/Partition Tolerance (AP)**: Return the most recent version of the data you have, which could be stale. This system state will also accept writes that can be processed later when the partition is resolved. Choose availability over consistency when your business requirements allow for some flexibility when the data in the system synchronizes, such as in a social media platform.
# References
## Articles
- [CAP Theorem: Revisited](https://robertgreiner.com/cap-theorem-revisited/)
## Videos
- [CAP Theorem Simplified](https://www.youtube.com/watch?v=BHqjEjzAicA)

[[Availability vs Consistency]]