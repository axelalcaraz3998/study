Tags: #ComputerScience #SystemDesign 

An API gateway is an API management tool that sits between a client and a collection of backend services. It is a component of application delivery and acts as a reverse proxy to accept all API calls, aggregate the various services required to fulfill them, and return the appropriate result. In simpler terms, it is a piece of software that intercepts API calls from a user and routes them to the appropriate backend service.
# An API Gateway's Role
It's usual for API gateways to handle common tasks that are used across a system of API services, such as user authentication, rate limiting, and statistics.

API gateways provide these benefits:
- **Low Latency**: By distributing incoming requests and offloading common tasks such as SSL termination and caching, API gateways optimize traffic routing and load balancing across backend services to ensure optimal performance and resource utilization.
- **Rate Limiting**: With rate limiting policies, you can specify the maximum number of requests allowed within a certain time period for each client or API key, protecting backend services from overload.
- **Request Throttling**: Using request throttling policies you can define rules and limits for regulating request traffic, such as maximum request rates, burst allowances, and quotas.
- **Concurrency Control**: Concurrency control policies specify the maximum number of concurrent connections or requests that can be handled simultaneously by the backend servers.
- **Circuit Breaking**: Circuit breaking policies monitor the health and responsiveness of backend servers and temporarily block or redirect traffic away from failing or slow services to prevent cascading failures and maintain overall system stability.
- **Dynamic Load Balancing**: API gateways continuously monitor server health and adjust traffic routing in real-time to handle spikes in demand, minimize response times, and maximize throughput.
# Common Gateway Patterns
- **Single Gateway**: All traffic flows through a single central gateway. Ideal for small to mid-sized systems but can become a bottleneck at scale.
- **Backend-for-Frontend (BFF)**: Separate gateways are optimized for each client type, allowing tailored payloads and performance.
- **Microgateway**: Lightweight gateways deployed alongside individual services or teams. Ideal for large enterprises prioritizing autonomy and scale, though it requires coordination to maintain consistency.
# References
## Articles
- [What does an API gateway do?](www.redhat.com/en/topics/api/what-does-an-api-gateway-do)
- [What is an API Gateway?](https://blog.postman.com/what-is-an-api-gateway/)
## Videos
- [What is an API gateway?](www.youtube.com/watch?v=hWRRdICvMNs&pp=ygULYXBpIGdhdGV3YXk%3D)

[[System Design MOC]]