Tags: #ComputerScience #SystemDesign 

In a typical fail-over pattern, there's a primary component handling the workload, and a secondary component waiting in the wings. The primary component is constantly monitored for signs of failure. If it goes down, the secondary component is automatically activated to ensure uninterrupted service.

Two common approaches are active-passive and active-active fail-over.
# Active-Passive
Active-passive fail-over relies on a simple setup: one server actively handles all tasks while a secondary server stays in standby mode, monitoring the primary server's health. The primary server manages incoming traffic, processes requests, and maintains user connections. Meanwhile, the standby keeps an eye on the primary by receiving regular heartbeat signals.

If the primary server fails or stops responding, the system detects the issue almost instantly. The standby server then springs into action, taking over the primary server and resuming operations.

To ensure data consistency, active-passive setups use database replication, file synchronization, or shared storage. In some cases, both servers access a shared data repository. Which eliminates the need of constant synchronization between them.

When the primary server is back online, administrators can either revert operations to the original server (a process called fail-back) or maintain current setup. Fail-back is usually scheduled during maintenance windows to avoid disrupting operations.
![[active-passive-pattern.webp]]
# Active-Active
Active-active fail-over involves deploying multiple servers that handle live traffic simultaneously, sharing the workload equally. Unlike systems where backup servers sit idle, every server in an active-active setup is operational and contributes to traffic management.

A load balancer plays a critical role here, monitoring server health and redirecting traffic if one server goes down. This eliminates the delay seen in active-passive setups, where a standby server has to be activated. If a server fails the remaining servers immediately takeover its workload, ensuring uninterrupted service.

To maintain consistent data across servers, real-time data replication or distributed file systems are essential. User sessions must either be shared across servers or designed to be stateless. Techniques like session clustering or external session stores help preserve session continuity, even if a servers goes offline.
![[active-active-pattern.webp]]
# References
## Articles
- [System Design: Availability Patterns](https://dev.to/decoders_lord/system-design-availability-patterns-104i)
- [Active-Passive vs. Active-Active Failover](https://www.serverion.com/uncategorized/active-passive-vs-active-active-failover/)
## Videos
- [Availability | System Design Interview Basics 2022](https://www.youtube.com/watch?v=WC7kpQPGPp8)

[[Availability Patterns]]