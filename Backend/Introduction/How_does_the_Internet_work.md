1. What is the Internet?
- The Internet is a global network of interconnected networks. It connects private, public, academic, business, and government networks so devices can exchange data.
- No single organization owns or runs the entire Internet. Independent organizations operate networks and connect them using shared protocols and interconnection agreements.
- The Internet is the infrastructure that carries data. The World Wide Web is one service that uses it; email, voice calls, file sharing, and other services also use the Internet.
- The Internet is physical as well as logical: it relies on fiber-optic and copper cables, undersea cables, radio links, routers, switches, and data centers.

2. Local Networks: Switches, Access Points, and Routers
- A Local Area Network (LAN) connects devices in a limited area, such as a home, office, school, or campus.
- A switch connects devices in a LAN and forwards local network traffic toward the correct device. Ethernet cables are commonly used to connect devices to a switch.
- A wireless access point lets devices join a LAN over Wi-Fi. The access point provides wireless connectivity; it does not by itself route traffic between separate IP networks.
- A router connects different IP networks and forwards packets between them. A home router commonly connects a home LAN to an Internet Service Provider (ISP).
- Many home gateways combine router, switch, and Wi-Fi access point functions in one device. Some also include a modem or fiber terminal.
- Devices on the same LAN can often communicate through a switch without sending their local traffic through the router. Traffic destined for another network is sent to a router, usually the device's default gateway.

3. Packets and How Data Travels
- Data sent over the Internet is divided into smaller units called packets.
- A packet carries data and a header with delivery information, including source and destination addresses.
- A device sends a packet through its local network to a router. Routers inspect the destination IP address and use routing information to forward the packet toward the destination network.
- A packet may cross several routers and independently operated networks. The route can vary as network conditions and routing information change.
- Packets can be delayed, lost, or arrive out of order. Protocols such as TCP provide mechanisms to detect missing data and deliver an ordered stream to an application.
- At the destination, network and transport protocols process the received packets so the application can use the data.

4. IP Addresses, Domain Names, and DNS
- An IP address identifies a network interface so packets can be routed to it. IPv4 and IPv6 are the main versions of Internet Protocol.
- A domain name, such as `example.com`, is a human-readable name for an Internet service.
- The Domain Name System (DNS) looks up DNS records, commonly including IP addresses associated with a domain name, so a client can find the service it wants to reach.
- DNS is hierarchical and distributed. Resolvers query DNS servers and cache answers for a period of time.

5. Internet Service Providers and the Wider Network
- An Internet Service Provider (ISP) gives homes, businesses, and other customers a connection to the Internet and operates network infrastructure that carries traffic.
- ISP networks connect to other networks through routing and interconnection arrangements. The exact structure is not a single fixed hierarchy; networks may connect in several ways.
- The video uses local, regional, and global ISPs as a simplified model for showing how traffic can travel across networks and between cities or countries.
- A Point of Presence (PoP) is a location where a network provider places equipment and connects to customers or other networks. It can contain routers, switches, and other network equipment.
- The Internet backbone consists of high-capacity, long-distance networks, often using fiber-optic links, that carry traffic between regions and networks.
- Undersea fiber-optic cables carry much of the long-distance traffic between continents. The Internet also uses terrestrial fiber, copper, and wireless links.
- Internet Exchange Points (IXPs) are facilities where networks interconnect and exchange traffic.
- Peering is an arrangement where networks exchange traffic directly. It can reduce the number of intermediary networks, cost, or latency for some routes; the effect depends on the networks and their interconnection.

6. LAN, WAN, and VPN
- A Wide Area Network (WAN) connects networks across larger geographic areas. A company may use a WAN to connect offices in different locations.
- A private WAN can use dedicated connections from a provider, but these can be costly.
- A Virtual Private Network (VPN) creates a logical private connection across an existing network, often the public Internet.
- VPN tunneling encapsulates one packet inside another so it can travel across an intermediate network. VPN encryption protects the tunneled data from being read or altered in transit, when properly configured.
- A VPN is not a physical tunnel and does not make every activity anonymous or guarantee perfect security. It protects particular traffic between VPN endpoints.

7. What Happens When You Open a Website or Stream a Video?
- You enter a URL or select a link in a browser or application.
- The device uses DNS to look up the domain name and find the service's network address.
- The device sends packets through its LAN, router, and ISP toward the server. Routers forward packets between networks along a route.
- The client sends an application request, commonly using HTTP or HTTPS. For HTTPS, TLS protects the connection.
- A server processes the request and sends back a response containing the requested page, data, or media.
- A browser uses the response to display a page and may request more resources. Video and other media are commonly delivered in chunks, allowing playback to begin before the entire file has arrived.
- Large services may use servers or caches in multiple locations, so a user can be served from a nearby system. Distributed infrastructure can improve capacity and response time, depending on the service and network route.

8. Internet Protocols and the Web
- A protocol is a shared set of rules that devices and software follow to communicate.
- IP provides addressing and packet delivery between networks.
- TCP provides reliable, ordered delivery of data between applications. UDP provides datagrams without built-in guarantees of delivery or ordering; protocols such as QUIC can add reliability and other features over UDP.
- HTTP is used by web clients and servers to exchange resources. HTTPS is HTTP protected by TLS.
- The Web is one application of the Internet. A browser uses HTTP or HTTPS to request resources from web servers, while other Internet services use other protocols.

9. Key Takeaways
- The Internet is a network of networks built from independently operated networks and physical infrastructure.
- Switches connect devices within a LAN; routers connect different networks and forward packets between them.
- Data travels in packets through routers and networks. IP addressing and routing help packets reach their destination.
- ISPs provide connectivity and interconnect with other networks. PoPs, backbones, IXPs, and peering are parts of this wider infrastructure.
- VPNs use tunneling and encryption to protect traffic between endpoints across another network.
- When a browser loads a site, it resolves a domain with DNS, sends a request to a server, and receives a response over Internet protocols.

10. Sources
- Ian Frost, freeCodeCamp: How does the internet work? (Full Course, YouTube) https://www.youtube.com/watch?v=zN8YNNHcaZc
- freeCodeCamp: How does the internet work? https://www.freecodecamp.org/news/how-does-the-internet-work/
- CS.FYI: How does the Internet Work? https://cs.fyi/guide/how-does-internet-work
- Vox: The internet, explained (updated May 14, 2015): https://www.vox.com/2014/6/16/18076282/the-internet
