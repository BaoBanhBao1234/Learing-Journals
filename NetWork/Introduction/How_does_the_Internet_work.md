1. What is the Internet?
- ==The Internet is a global network of interconnected networks. It allows computers, phones, servers, and other devices to exchange data.==
- ==Networks connect through routers and communication links, including fiber-optic cables, copper cables, and wireless radio signals.==
- ==The Internet is distributed: it has no single central computer that controls all communication. Many organizations operate parts of its infrastructure and use shared protocols to connect them.==
- ==An Internet Service Provider (ISP) connects homes, businesses, or other networks to the wider Internet and forwards traffic through its network and connections to other networks.==

2. How Data Travels Across the Internet
- ==Data is divided into smaller units called **packets** and encoded as bits for transmission over a physical or wireless link.==
- ==Each packet carries protocol information, including addressing information used to deliver it.==
- ==A **switch** forwards frames between devices on a local network. A **router** forwards IP packets between different networks.==
- ==Routers examine destination IP addresses and use routing information to choose a next hop. Packets from one communication can travel through multiple networks and may take different paths.==
- ==At the destination, network protocols process the packets and pass the data to the appropriate application. When a transport protocol such as TCP is used, it can retransmit lost data and present the received data in order.==

3. Addresses and Names
- ==An **IP address** identifies a network interface for communication using Internet Protocol. IPv4 and IPv6 are the two main versions.==
- ==A **MAC address** is used for delivery on a local network link. Routers use IP addressing to forward traffic between networks, while local link technologies deliver frames to the next device.==
- ==A **domain name**, such as `example.com`, is a human-readable name.==
- ==**DNS (Domain Name System)** lets a device look up DNS records for a domain name, including IP address records used to locate a service. DNS does not carry the website itself.==

4. Protocols Make Communication Work
- ==A **protocol** defines rules for formatting, sending, receiving, and interpreting data.==
- ==**Ethernet and Wi-Fi** carry data across local network links.==
- ==**IP** provides addressing and best-effort packet delivery between networks.==
- ==**TCP** provides a reliable, ordered byte stream by detecting missing data and retransmitting it when necessary. Not every Internet application uses TCP.==
- ==**UDP** provides a lightweight datagram transport without TCP’s built-in delivery and ordering guarantees.==
- ==**HTTP** is used by web clients and servers to exchange web resources. **HTTPS** uses TLS to protect the HTTP connection with encryption and authentication.==

5. What Happens When a Website Loads?
- ==The browser uses DNS to look up the domain name and find an address for the website’s service.==
- ==The device sends traffic through its local network and router to the ISP and then across other networks toward the destination.==
- ==The browser establishes a transport connection. For HTTPS, it also negotiates TLS encryption and verifies the server’s identity.==
- ==The browser sends an HTTP request for a resource, such as a page, image, or script.==
- ==The web server returns an HTTP response. The data travels back in packets, and the browser interprets the response and renders the page.==
- ==Actual connections can use different protocol details and may involve intermediaries such as proxies or content delivery networks (CDNs).==

6. The Internet and the World Wide Web
- ==The **Internet** is the global network infrastructure and the protocols that allow connected networks to exchange data.==
- ==The **World Wide Web (the Web)** is a service built on top of the Internet. It uses technologies such as URLs, HTTP, web servers, and browsers to access linked web resources.==
- Email, voice calls, file transfer, and other services also use the Internet; they are not the Web itself.

7. Why the Internet Uses a Distributed Design
- ==Networks are operated by many organizations and connect through shared protocols and agreements.==
- ==If a router, link, or data center becomes unavailable, routing may send traffic through another available path when one exists.==
- ==This design helps the Internet continue operating when individual parts fail, although outages can still interrupt access to particular networks or services.==

8. Key Takeaways
- The Internet is a network of networks connected by physical and wireless links.
- Packets carry data; switches forward traffic within local networks and routers forward IP packets between networks.
- IP addresses help route traffic, while DNS helps devices look up information associated with domain names.
- Protocols such as IP, TCP, UDP, HTTP, and TLS define different parts of communication.
- The Web is one service that runs on the Internet, alongside services such as email and file transfer.

9. Sources
- roadmap.sh: How does the internet work? https://roadmap.sh/guides/what-is-internet
- Cloudflare: How does the Internet work? https://www.cloudflare.com/en-gb/learning/network-layer/how-does-the-internet-work/
- How does the Internet work? https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/How_does_the_Internet_work
