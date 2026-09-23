Tags: #ComputerScience #SystemDesign 

DNS is the phone book of the internet. Human access information online through domain names. Web browsers interact through IP addresses. DNS translates domain names to IP addresses so browsers can load internet resources.
# How Does DNS Work?
The process of DNS resolution involves converting a hostname (e.g. www.example.com) into a computer-friendly IP address (e.g. 192.168.1.1). When a user wants to load a webpage, a translation must occur between what the user types into the browser and the machine-friendly address necessary to locate the website.
# Types of DNS Servers
All DNS servers fall into one of four main categories. Recursive resolvers, root nameservers, Top-Level-Domain (TLD) nameservers, and authoritative nameservers. In a typical DNS lookup, these four DNS servers work together to complete the task of delivering the IP address for a specified domain.
## DNS Recursive Resolver
A recursive resolver is the first stop in a DNS query, it acts as a middleman between a client and a DNS nameserver. After receiving a DNS query from the web client, a recursive resolver will either respond with cached data, or send a request to a root nameserver, followed by another request to a TLD nameserver, and the one last request to an authoritative nameserver. After receiving a response from the authoritative nameserver containing the requested IP address, the recursive resolver then sends a response to the client.

During this process, the recursive resolver will cache information received from authoritative nameservers. When a client requests the IP address of a domain that was recently requested by another client, the resolver can circumvent the process of communicating with the nameservers, and just deliver the client the requested record from its cache.
![[dns-recursive-resolver.png]]
## DNS Root Nameserver
The 13 DNS root nameservers are known to every recursive resolver, and they are the first stop in a recursive resolver's quest for DNS records. A root server accepts a recursive resolver's query which includes a domain name, and the root nameserver responds by directing the recursive resolver to a TLD nameserver, based on the extension of that domain (.com, .net, .org, etc).
![[dns-root-nameserver.png]]
## TLD Nameserver
A TLD nameserver maintains information for all the domain names that share a common domain extension. For example, a .com TLD nameserver contains information for every website that ends in .com. If a user was searching for "google.com", after receiving a response from a root nameserver, the recursive resolver would then send a query to a .com TLD server, which would respond by pointing to the authoritative nameserver for that domain.
![[dns-tld-nameserver.png]]
## Authoritative Nameserver
When a recursive resolver receives a response from a TLD nameserver, that response will direct the resolver to an authoritative nameserver. The authoritative nameserver is usually the resolver's last step in the journey for an IP address. The authoritative nameserver contains information specific to the domain name it servers and it can provide a recursive resolver with the IP address of the server found in the DNS A record, or if the domain has a CNAME record it will provide the recursive resolver with an alias domain, at which point the recursive resolver will have to perform a whole new DNS lookup to procure a record from an authoritative nameserver.
![[dns-authoritative-nameserver.png]]
# DNS Records
DNS records are instructions that live in authoritative DNS servers and provide information about a domain including what IP address is associated with that domain and how to handle requests for that domain. These records consist of a series of text files written in what is known as DNS syntax. All DNS records have a Time-To-Live (TTL) that indicates how often DNS servers will refresh that record.
## Common DNS Records
- **A record**: The record that holds the IP address of a domain.
- **AAAA record**: The record that contains the IPv6 address of a domain.
- **CNAME record**: Forwards one domain or subdomain to another domain, does not provide an IP address.
- **MX record**: Directs mail to an email server.
- **TXT record**: Lets an admin store text notes in the record. These are often used for email security.
- **NS record**: Stores the name server for a DNS entry.
- **SOA record**: Stores admin information about a domain.
- **SRV record**: Specifies a port for specific services.
- **PTR record**: Provides a domain name in reverse-lookups.
# DNS Caching
The purpose of caching is to temporarily store data in a location that results in improvements in performance for data requests. DNS caching involves storing data closer to the requesting client so that the DNS query can be resolved earlier and additional queries further down the DNS lookup chain can be avoided.
## Browser DNS Caching
Modern browsers are designed to cache DNS records for a set amount of time. The purpose here is obvious; the closer the DNS caching occurs to the web browser, the fewer processing steps must be taken in order to check the cache and make the correct requests to an IP address.
## Operating System DNS Caching
The OS level DNS resolver is the second and last local stop before a DNS query leaves your machine. The process inside your operating system that is designed to handle this query is commonly called a "stub resolver" or DNS client. When a stub resolver gets a request from an application, it first checks its own cache to see if it has the record. If it does not, it then sends a DNS query outside the local network to a DNS recursive resolver inside the Internet Service Provider (ISP).
# References
## Articles
- [What is DNS?](https://www.cloudflare.com/learning/dns/what-is-dns/)
- [DNS server types](https://www.cloudflare.com/learning/dns/dns-server-types/)
- [DNS records](https://www.cloudflare.com/learning/dns/dns-records/)
## Videos
- [How a DNS Server (Domain Name System) works.](https://www.youtube.com/watch?v=mpQZVYPuDGU)

[[System Design MOC]]