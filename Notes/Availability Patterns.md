Tags: #ComputerScience #SystemDesign 

Availability patterns are established architectural approaches used to ensure a system remains operational and accessible to users, even in the face of failures or unexpected events. These patterns focus on minimizing downtime and maintaining a consistent level of service by incorporating redundancy, fault tolerance, and recovery mechanisms into the system's design. They provide a structured way to address potential points of failure and ensure business continuity.
# Fail-Over Pattern
In a typical fail-over pattern, there's a primary component handling the workload, and a secondary component waiting in the wings. The primary component is constantly monitored for signs of failure. If it goes down, the secondary component is automatically activated to ensure uninterrupted service.

See [[Fail-Over Pattern]]
# Replication Pattern
Replication is a strategy that involves storing multiple copies of data across different locations. This redundancy ensures that even if one location experiences failure, the data can still be accessed from another.

See [[Replication Pattern]]
# Availability in Numbers
Availability is often quantified by uptime (or downtime) as a percentage of time the service is available. Availability is generally measured in number of 9.

See [[Availability in Numbers]]
# References
## Articles
- [System Design: Availability Patterns](https://dev.to/decoders_lord/system-design-availability-patterns-104i)

[[System Design MOC]]