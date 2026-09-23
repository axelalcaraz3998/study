Tags: #ComputerScience #SystemDesign 

A Content Delivery Network (CDN) is a geographically distributed group of servers that caches content close to end users. A CDN allows for the quick transfer of assets needed for loading internet content, including HTML, JavaScript, CSS, images, and videos.

The primary benefits of using a CDN, for most users, can be broken down into four different components:
- **Improving Website Load Time**: By distributing content closer to the visitor, visitors experience faster page loading times.
- **Reducing Bandwidth Costs:** Bandwidth consumption costs for website hosting is a primary expense for websites. Through caching and other optimizations, CDNs are able to reduce the amount of data an origin server must provide.
- **Increasing Content Availability and Redundancy:** Large amount of traffic or hardware failures can interrupt normal website function. Thanks to their distributed nature, a CDN can handle more traffic and withstand hardware failure better than many origin servers.
- **Improving Website Security:** A CDN may improve security by providing DDoS mitigation, improvements to security certificates, and other optimizations.
# How Does a CDN Work?
A CDN is a network of servers linked together with the goal of delivering content as quickly, cheaply, reliably, and securely as possible. In order to improve speed and connectivity, a CDN will place servers at the exchange points between different networks.

These Internet exchange points (IXPs) are the primary locations where different Internet providers connect in order to provide each other access to traffic originating on their different networks.

Beyond placement of servers in IXPs, a CDN makes a number of optimizations on standard client/server data transfers. CDNs place data centers at strategic locations across the globe, enhance security, and are designed to survive various types of failures and Internet congestion.
![[cdn-distributed-server.png]]
# Pull CDN
In a pull CDN, the cache is updated based on request. When the client sends a request that requires static assets to be fetched from the CDN, if the CDN doesn't have it, then it will fetch the newly updated assets from the origin server and populate its cache with this new asset, and then send this new cached asset to the user.
# Push CDN
In a push CDN, it is the responsibility of the engineers to push the assets to the origin server which will then propagate to other CDN nodes across the network. The assets that are received through propagation are then cached onto these CDN servers such that when a client sends a request the CDN provides this cached asset.
# References
## Articles
- [What is a CDN?](https://www.cloudflare.com/learning/cdn/what-is-a-cdn/)
- [Push CDN vs Pull CDN](https://medium.com/@ajin.sunny/push-cdn-vs-pull-cdn-a13145df5e13)
## Videos
- [CDN - Content Delivery Network - Explained](https://www.youtube.com/watch?v=nhhfSBm6v4A)

[[System Design MOC]]