Tags: #ComputerScience #SystemDesign 

Load balancing is the practice of distributing computational workloads between two or more computers. On the internet, load balancing is often employed to divide network traffic among several servers. This reduces the strain on each server and makes the servers more efficient, speeding up performance and reducing latency.
![[load-balancer.png]]
# How Does Load Balancing Work?
Load balancing is handled by a load balancer. A load balancer can be either hardware-based or software-based.

When a request arrives from a user, the load balancer assigns the request to a given server, and this process repeats for each request. Load balancers determine which server should handle each request based on a number of different algorithms.
# Load Balancing Algorithms
There are two primary approaches to load balancing. Dynamic load balancing uses algorithms that take into account the current state of each server and distribute traffic accordingly. Static load balancing distributes traffic without making these adjustments. Some static algorithms send an equal amount of traffic to each server in a group, either in specified order or at random.
## Dynamic Load Balancing Algorithms
- **Least Connections**: Checks which server have the fewest connections opens at the time and sends traffic to those servers.
- **Weighted Least Connections**: Gives administrators the ability to assign different weights to each server, assuming that some servers can handle more connections than others.
- **Least Response Time**: Routes traffic to servers combining the least connections and the fastest response latency.
- **Resource-based**: Distributes load based on what resources each server has available at the time. A specialized software, called an agent, running on each server measures the server's available CPU and memory.
## Static Load Balancing Algorithms
- **Round Robin**: Distributes the traffic to a list of servers in a sequential, repeating rotation. It is used when servers have identical capabilities.
- **Weighted Round Robin**: Allows administrators to assign different weights to each server. Servers deemed able to handle more traffic will receive slightly more.
- **IP Hash**: Uses a mathematical function to convert the client's IP address into a hash. Based on the hash, the connection is assigned to a specific server.
# Layer 4 Load Balancer
Layer 4 load balancing operates at the transport layer of the OSI model. This layer enables connection-oriented data streaming, reliability, flow control, and multiplexing to handle concurrent requests on a single connection.

Layer 4 load balancing distributes network traffic based on information found in the transport layer headers of the data packets. This typically includes information such as source and destination IP addresses, as well as ports. 

Layer 4 load balancers forward client requests based on this information, directing traffic to available servers based on various algorithms to help optimize resource consumption. It functionally emulates a firewall while performing health checks along the way. They also handle TCP and UDP traffic.

Layer 4 load balancing comes in multiple forms:
- **Direct Routing (DR)**: The load balancer routes requests directly to backend servers by rewriting destination MAC addresses.
- **Network Address Translation (NAT)**: The load balancer distributes traffic across multiple similar network interfaces. NAT methods can include sticky IP, round-robin, remapping, and random distribution.
- **Source Network Address Translation (SNAT)**: The load balancer forwards incoming traffic attributed to one IP address to one of multiple firewall-protected servers.
# Layer 7 Load Balancer
Layer 7 load balancing describes traffic distribution at the application layer of the OSI model, which is where human-application interaction occurs and where applications access network services.

Layer 7 load balancers base their routing decisions on protocol-specific information, and information available on lower layers. They function as proxies by maintaining separate TCP connections with both the client and server.

Layer 7 load balancing is slower than Layer 4 load balancing, since packets are reassembled and inspected. However, Layer 7 acceleration features such as caching, improved routing, and others generally compensate.

Layer 7 load balancing occurs at the highest level within the OSI model. It primarily uses HTTP/HTTPS header content, message content, cookie information, and URLs to determine routing behaviors.
- The load balancer negotiates a TLS connection with the client, enabling it to read the contents of the message itself.
- The load balancer inspects each message's contents.
- The load balancer opens a new TCP connection with the backend server and routes the request in conjunction with a number of rules and algorithms.
# References
## Articles
- [What is load balancing?](https://www.cloudflare.com/learning/performance/what-is-load-balancing/)
- [Types of load balancing algorithms](https://www.cloudflare.com/learning/performance/types-of-load-balancing-algorithms/)
- [Layer 4 load balancing](https://www.haproxy.com/glossary/what-is-layer-4-load-balancing)
- [Layer 7 load balancing](https://www.haproxy.com/glossary/what-is-layer-7-load-balancing)

[[System Design MOC]]