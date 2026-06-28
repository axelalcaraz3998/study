Tags: #ComputerScience #SystemDesign
# What is a System Design?
System design is the process of defining the architecture, components, modules, interfaces, and overall structure of a system to meet specified requirements and goals. It involves creating a blueprint that outlines how various elements interact and work together to achieve the desired functionality, performance and reliability.

In software engineering, system design is a phase in the software development process that focuses on the high-level design of a software system, including the architecture and components. It involves translating high-level concepts into concrete designs that can be implemented and executed efficiently.
## Key Concepts in System Design
- **Modularity and Abstraction**: Breaking down a complex system into modular components promotes reusability, ease of maintenance, and efficient collaboration among developers.
- **Coupling and Cohesion**: Striking the right balance between component interdependence (coupling) and the functional relatedness within a component (cohesion) is crucial for a well-structured system.
- **Architectural Patterns**: Different architectural patterns, such as client-server, microservices, and monolithic, offer guidelines for organizing components and handling interactions.
- **Data Flow and Communication**: Designing effective data flow and communication mechanisms ensures seamless information exchange between system components.
- **Trade-offs and Constraints**: System designers often face trade-offs between factors like performance, cost, and development time. Understanding these trade-offs is vital to making informed decisions.
## Understanding the Components of System Design
- **Components and Modules**: Each component encapsulates a specific functionality, allowing for modularity and reusability. This means that developers can focus on refining and enhancing individual components without disrupting the entire system.
- **Data Management**: Data management involves designing databases, defining schemas, and implementing strategies for data storage, retrieval, and maintenance. A well-designed data management component ensures that information flows seamlessly through the system, enabling accurate and timely decision-making.
- **User Interfaces**: A user interface component involves creating intuitive, aesthetically pleasing, and user-friendly interfaces that facilitate smooth interactions. From buttons and menus to forms and visual elements, a well-designed user interface component enhances user experience, making it easy for users to navigate and engage with the application.
- **Communication Protocols**: Communication and protocols act as the language that enables effective dialogue. These protocols define the rules and conventions for data exchange between different components or between separate systems. A robust communication protocol ensures that information is transmitted accurately and efficiently.
- **Security Measures**: This component encompasses encryption, authentication, access control, and other measures to safeguard sensitive information and prevent unauthorized access. A well-designed security component shields the software system from potential threats and vulnerabilities.
# How to Approach a System Design?
- **Understand the Problem**: Gather information about the problem you are trying to solve and the requirements of the system. Identify the users and their needs, as well as any constraints or limitations of the system.
- **Identify the Scope of the System**: Define the boundaries of the system, including what the system will do and what it will not do.
- **Research and Analyze Existing Systems**: Look at similar systems that have been built in the past and identify what worked well and what didn't.
- **Create a High-level Design**: Outline the main components of the system and how they will interact with each other. This can include a rough diagram of the system's architecture, or a flowchart outlining the process the system will follow.
- **Refine the Design**: As you work on the details of the design, iterate and refine it until you have a complete and detailed design that meets all the requirements.
- **Document the Design**: Create detailed documentation of your design for future reference and maintenance.
- **Continuously Monitor and Improve the System**: The system design is not a one-time process, it needs to be continuously monitored and improved to meet the changing requirements.
# Performance vs Scalability
## What is Performance?
Performance refers to how quickly and efficiently a system executes tasks under current conditions. It measures the speed, responsiveness, and effectiveness of a system handling its workload within a given timeframe.
### Key Performance Characteristics
- **Response Time**: The total time taken from initiating a request to receiving a complete response.
- **Throughput**: The number of requests or transactions processed per unit of time.
- **Resource Utilization**: How effectively the system uses CPU, memory, storage, and network resources.
- **Latency**: The delay before processing begins after a request is made.
- **Efficiency**: The ratio of useful work performed to resources consumed.
## What is Scalability?
Scalability refers to a system's ability to handle increased workload by adding resources while maintaining or improving performance levels. Scalability is about capacity and growth, ensuring systems can adapt to increasing demands without degrading performance.
### Core Scalability Principles
- **Elasticity**: Dynamic adjustment of resources based on demand.
- **Capacity Planning**: Ability to accommodate future growth requirements.
- **Resource Scaling**: Adding computational power through various scaling strategies.
- **Load Distribution**: Efficiently spreading workload across available resources.
- **Architectural Flexibility**: System design that supports expansion without fundamental restructuring.
### Scalability Types
- **Horizontal Scaling (Scale-Out)**: Adding more machines or nodes to distribute load.
- **Vertical Scaling (Scale-Up)**: Increasing resources (CPU, RAM, storage) on existing machines.
- **Diagonal Scaling**: Hybrid approach combining vertical and horizontal scaling strategies.
## Performance vs Scalability Trade-offs
The fundamental challenge in system design is that optimizing for performance often conflicts with scalability requirements.

Performance-First Approach Trade-offs:
- **Benefits**: Faster response times, better resource utilization, lower latency for current users.
- **Limitations**: May not handle growth effectively, could create bottlenecks under increased load.
- **Examples**: Highly optimized single-server applications, in-memory databases, monolithic architecture.

Scalability-First Approach Trade-offs:
- **Benefits**: Better growth handling, fault tolerance, distributed load management.
- **Limitations**: Increased complexity, potential latency from distributed operations, higher resource overhead.
- **Examples**: Microservices architectures, distributed databases, load-balanced systems.
# Latency vs Throughput
## Latency
Latency is a measure of how long it takes for a system to complete a task or process data. It is often measured in milliseconds or microseconds and is an important metric for determining the performance of a system. High latency can lead to slow performance, while low latency can result in faster and more responsive systems.

Latency can be caused by various factors, such as, network, network congestion, inefficient algorithms, load on the resources and so on.
## Throughput
Throughput refers to the number of requests that a system can handle at the same time or the number of units of data that can be processed in a given period of time. Throughput is often measured in requests per second, transactions per second or bits per second.

Throughput can be limited by various factors, such as the capacity of the systems involved, the number of available resources, and the efficiency of the algorithms used to process the data. For example, in a network, throughput can be limited by the bandwidth available or the number of connections that can be made at the same time. In a computer, it can be limited by the CPU or memory capacity.
# Availability vs Consistency
Availability means that the system responds to a request even when there is a failure. The response might be outdated, but the key here is to keep you moving. This is often measured in terms of the percentage of time that the system is up and running, also known as its uptime.

Consistency ensures that all nodes in a distributed system reflect the most recent write. Everyone sees the same data, no matter which server they interact with. This is important for maintaining the integrity of the data stored in the system.

In distributed systems, it is often a trade-off between availability and consistency. Systems that prioritize high availability may sacrifice consistency, while systems that prioritize consistency may sacrifice availability.
## CAP Theorem
The CAP theorem states that, in a distributed system, you can only have two out of the following three guarantees across a read/write pair: Consistency, Availability and Partition Tolerance, one of these must be sacrificed.
- **Consistency**: A read is guaranteed to return the most recent write for a given client.
- **Availability**: A non-failing node will return a reasonable response within a reasonable amount of time.
- **Partition Tolerance**: The system will continue to function when network partition occur.
Given that networks aren't completely reliable, you must tolerate partitions in a distributed system. You'll need to make a trade-off between consistency and availability.
- **Consistency/Partition Tolerance (CP)**: Wait for a response from the partitioned node which could result in a timeout error. The system can also choose to return an error, depending on the scenario you desire. Choose consistency over availability when your business requirements dictate atomic reads and writes, such as in a banking app.
- **Availability/Partition Tolerance (AP)**: Return the most recent version of the data you have, which could be stale. This system state will also accept writes that can be processed later when the partition is resolved. Choose availability over consistency when your business requirements allow for some flexibility when the data in the system synchronizes, such as in a social media platform.
# Consistency Patterns
## Weak Consistency
## Eventual Consistency
## Strong Consistency
# References
- https://swimm.io/learn/system-design/system-design-complete-guide-with-patterns-examples-and-techniques
- https://www.crio.do/blog/a-comprehensive-guide-to-system-design/
- https://blog.professorbeekums.com/performance-vs-scalability/
- https://medium.com/@shivanimutke2501/performance-vs-scalability-whats-the-difference-and-why-it-matters-e3f0253dca3e
- https://cs.fyi/guide/latency-vs-throughput
- https://medium.com/@Saravanansd/availability-vs-consistency-the-backbone-of-distributed-systems-e0aca8f441d7
- https://robertgreiner.com/cap-theorem-revisited/