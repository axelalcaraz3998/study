Tags: #ComputerScience #SystemDesign 

A reverse proxy is a server that sits in front of web servers and forwards client requests to those web servers. Reverse proxies are typically implemented to help increase security, performance, and reliability.
# Forward Proxy
A forward proxy, is a server that sits in front of a group of client machines. When those computers make requests to sites and services on the internet, the proxy server intercepts those requests and then communicates with web servers on behalf of those clients, like a middleman.
![[forward-proxy.png]]
There are a few reasons to use a forward proxy, such as:
- To avoid state or insitutional browsing restrictions.
- To block access to certain content.
- To protect your online identity.
# Reverse Proxy
A reverse proxy is a server that sits in front of one or more web servers, intercepting requests from clients. When clients send requests to the origin server of a website, those requests are intercepted at the network edge by the reverse proxy server. The reverse proxy server will then send requests to and receive responses from the origin server or servers.
![[reverse-proxy.png]]
Some of the benefits of using a reverse proxy are:
- Load balancing.
- Protection from attacks.
- Global server load balancing (GSLB).
- Caching.
- SSL encryption.
# References
## Articles
- [What is a reverse proxy?](https://www.cloudflare.com/learning/cdn/glossary/reverse-proxy/)

[[System Design MOC]]