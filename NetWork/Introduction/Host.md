1. What is a Network Host?
- A host is a computer or other device connected to a network that can send and receive data using network protocols.
- Examples include desktop computers, laptops, phones, servers, virtual machines, and network-connected devices.
- A host is an endpoint in network communication. It may request services, provide services, or do both, depending on the interaction.
- Hosts are generally identified on an IP network by one or more IP addresses. An IP address is assigned to a network interface and may change over time.

2. Host, Node, Client, and Server
- **Node** is a broad term for a device or connection point in a network. Hosts are nodes, but some network devices, such as switches, are usually described as nodes rather than end hosts.
- **Host** refers to a network-connected endpoint that can communicate using network protocols.
- **Client** describes a role: it requests data or a service.
- **Server** describes a role: it provides or processes a service. A server can be software running on a host; it does not always require dedicated hardware.
- A single host can act as a client in one exchange and a server in another. The terms describe different aspects: host identifies an endpoint, while client and server describe roles in a communication.

3. What a Host Needs to Communicate
- **Network interface**: a wired or wireless connection, commonly provided by a network interface card (NIC).
- **IP address**: identifies an interface for communication on an IP network.
- **Subnet mask or prefix**: indicates which IP addresses are considered part of the local network.
- **Default gateway**: forwards traffic from the local network to other networks when needed.
- **Network protocols**: rules that devices follow to exchange data. TCP and UDP are common transport protocols used by applications over IP.
- A host may communicate directly with devices on its local network or send traffic through a router to reach a remote network.

4. Hostname and IP Address
- A **hostname** is a human-readable name associated with a host, such as `laptop-01` or `www.example.com`.
- DNS can translate a domain name into IP address records so clients can locate network services by name.
- A hostname is easier for people to remember than an IP address, but it is not itself the address used to route IP packets.
- A host may have multiple network interfaces or IP addresses. Its hostname and address can also change depending on network configuration.

5. Host Components
- **Hardware**: CPU, memory, storage, and a network interface.
- **Operating system and network stack**: manage the device’s resources and implement network communication.
- **Applications and services**: create or use network connections, such as a browser, file-sharing service, or web server.
- **Network configuration**: may include IP address, subnet prefix, gateway, and DNS resolver settings.
- **Security controls**: firewalls, authentication, access controls, and encryption help protect a host and its communications.

6. Common Host Types and Examples
- **Client host**: a laptop or phone that requests a web page or another network service.
- **Server host**: a computer or virtual machine running services for other hosts.
- **Remote host**: a host accessed over a network rather than locally, for example through SSH or a remote desktop service.
- **Cloud or virtual machine host**: a virtual computer with its own operating system and network configuration, running on physical infrastructure managed by a provider.
- These labels describe a host’s use or environment; they do not change the basic idea that it is a network-connected endpoint.

7. Network Host and Web Hosting
- A **network host** is any endpoint connected to a network that can communicate with other hosts.
- **Web hosting** is a service that makes website files or application content available through web servers over the internet.
- A web-hosting provider supplies or manages server resources, storage, and network connectivity. A website’s server is a host, but “web host” can also refer to the hosting provider or hosting service.
- A domain name points visitors toward a service through DNS; the domain itself does not store the website’s files.

8. Key Takeaways
- A host is a network-connected endpoint that can send and receive data.
- An IP address identifies a network interface for IP communication; a hostname gives people a readable name to use.
- Client and server are communication roles. One host can take either role depending on the exchange.
- Web hosting is a particular service built on network hosts and web servers; it is narrower than the general networking meaning of “host.”

9. Sources
- Temok: What is a Host? https://blog.temok.com/what-is-a-host/
- YouTube: What is Web Hosting and How Does It Work? (For Complete Beginners) https://www.youtube.com/watch?v=H8oAvyqQwew 

