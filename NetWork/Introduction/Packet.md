1. What is a Network Packet?
- A packet is a formatted unit of data sent across a network. Larger messages, such as a web page or image, are carried as smaller units so network devices can forward them.
- The receiving device processes the units and, when the protocol requires it, puts the data back into the correct order or reconstructs the original message.
- Packets are used on the Internet and other packet-switched networks.

2. Why Networks Use Packets
- **Packet switching** allows many devices to share network links. Data from different communications can be interleaved instead of one sender occupying a link with a long, uninterrupted stream.
- Routers forward packets toward their destinations based on addressing and routing information.
- Packets belonging to one communication may take different paths and may arrive at different times or out of order.
- IP provides best-effort delivery. It does not guarantee that packets arrive, arrive once, or arrive in order. Protocols such as TCP can detect loss, retransmit data, and provide an ordered byte stream to an application.

3. Packet Structure: Header and Payload
- A **header** contains control information used to deliver or process the data. Depending on the protocol, it may include source and destination addresses, protocol identifiers, length, or other fields.
- The **payload** is the data carried by that protocol. For an IP packet, the payload commonly contains a TCP segment, UDP datagram, or another protocol’s data.
- Networking uses several layers, and each layer can add its own header. For example, an application message can be carried inside a TCP segment, inside an IP packet, inside a link-layer frame.
- Some protocols or link technologies add a trailer. For example, an Ethernet frame commonly ends with a frame check sequence (FCS) used to detect transmission errors.

4. Packets at Different Network Layers
- **TCP segment**: a transport-layer unit. TCP uses sequence numbers and acknowledgments to provide reliable, ordered delivery of a byte stream.
- **UDP datagram**: a transport-layer unit sent without TCP’s delivery and ordering guarantees. Applications can choose UDP when its behavior suits their needs.
- **IP packet (IP datagram)**: a network-layer unit with source and destination IP addresses. Routers use the destination address to forward it between networks.
- **Ethernet frame**: a link-layer unit used to carry data across a local network link. It includes link-layer addressing and an error-checking field.
- These terms name units at different layers. In casual use, “packet” is sometimes used broadly for network data units, but the precise term depends on the protocol layer.

5. How a Packet Travels
- The sender’s network stack wraps application data with the headers required by the protocols being used.
- A local network device forwards the frame toward the next hop. A router reads the IP header and chooses where to send the packet next.
- At each network link, the link-layer frame can change as the packet is forwarded. The IP packet is carried inside the frame for that link.
- At the destination, protocol layers process and remove their headers. The receiving application gets the data in the form provided by its transport protocol.

6. Packet Headers and Routing
- An IP header includes source and destination IP addresses and fields that help routers handle the packet, such as a hop limit (IPv6) or time to live (IPv4).
- The destination IP address helps routers forward a packet toward the destination network. It does not necessarily identify the final application; transport protocols also use port numbers to identify services or processes.
- A packet’s payload is not always readable by intermediate devices. Encryption such as TLS protects application data while it travels, though some network metadata remains visible.

7. Network Traffic and Malicious Packets
- **Network traffic** is the data moving through a network, including packets sent by users, applications, and network services.
- Malicious traffic can attempt to exploit a vulnerability, scan for exposed services, steal data, or overwhelm a service with requests, as in a denial-of-service attack.
- Firewalls, traffic filtering, rate limiting, monitoring, and secure configuration can help detect or reduce harmful traffic.

8. Key Takeaways
- A packet is a formatted unit of network data, and larger messages are commonly carried in multiple units.
- Packet switching lets many communications share network links; packets can take different paths and arrive out of order.
- Headers carry protocol and delivery information, while payloads carry the data for the next protocol layer.
- TCP segments, UDP datagrams, IP packets, and Ethernet frames belong to different network layers.
- IP is best effort; reliability and ordering depend on higher-level protocols such as TCP when they are used.

9. Sources
- Cloudflare: What is a packet? https://www.cloudflare.com/en-gb/learning/network-layer/what-is-a-packet/
- YouTube: https://www.youtube.com/watch?v=KjD3KANH-xc 
