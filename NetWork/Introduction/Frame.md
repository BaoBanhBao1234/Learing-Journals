1. What is a Network Frame?
- A frame is a formatted unit of data used by a data-link protocol to deliver data over a single network link.
- In the OSI model, framing is associated with the Data Link Layer (Layer 2).
- A frame carries a payload, often a network-layer packet such as an IP packet, together with link-layer control information.
- Frame formats depend on the link technology. Ethernet and Wi-Fi, for example, use different frame formats.

2. Why Frames Are Used
- Frames package data for transmission between devices on the same link or local network segment.
- Link-layer addresses help deliver a frame to the next device on that link. In Ethernet, these are source and destination MAC addresses.
- Frame fields identify or describe the carried data and can help detect transmission errors.
- Network devices such as switches use link-layer information to forward frames within a local network.

3. Typical Ethernet Frame Structure
- Ethernet II frames commonly contain these fields:
  - **Destination MAC address:** identifies the intended link-layer recipient.
  - **Source MAC address:** identifies the sending interface on the local link.
  - **EtherType:** indicates the protocol carried in the payload, such as IPv4 or IPv6.
  - **Payload and padding:** carries the upper-layer data; padding may be added when needed to meet the minimum frame size.
  - **Frame Check Sequence (FCS):** uses a cyclic redundancy check (CRC) to detect transmission errors.
- Ethernet also sends a preamble and Start Frame Delimiter before the frame so the receiver can synchronize and recognize the start of a frame. They are often shown alongside the frame in diagrams, but are not usually counted as fields in the Ethernet MAC frame itself.
- Other link-layer technologies can have different fields and formats.

```text
Preamble + SFD | Destination MAC | Source MAC | EtherType | Payload + Padding | FCS
```

4. Frame and Packet
- A **packet** is a Layer 3 unit, commonly an IP packet, used to carry data across networks.
- A **frame** is a Layer 2 unit used to carry that packet over a particular link.
- When an IP packet is sent over Ethernet, the Ethernet frame carries the packet as its payload.
- A frame uses link-layer addresses for the current link; the IP packet carries network-layer addresses used for delivery across networks.

```text
Application data -> TCP/UDP segment -> IP packet -> Ethernet frame -> physical signal
```

5. How Frames Move Through a Network
- A sender places an IP packet inside a frame addressed to the next device on the local link, such as a router or another host.
- A switch examines the destination MAC address to forward the frame within its network.
- When a router forwards the IP packet to another network, it removes the incoming link-layer frame and puts the packet into a new frame for the next link.
- Therefore, the frame is generally specific to one link and can change at each routed hop, while the IP packet is forwarded between networks.
- The source and destination MAC addresses on a frame are not necessarily the original sender and final destination of the end-to-end communication; they identify the devices for that link.

6. Error Detection and Delivery
- The Ethernet FCS helps a receiver detect whether a frame was corrupted in transit.
- A frame with an invalid FCS is normally discarded. Ethernet FCS provides error detection; it does not itself guarantee retransmission or end-to-end delivery.
- Other protocols or link technologies may provide their own recovery mechanisms. For example, TCP can retransmit missing data, while Wi-Fi can use link-layer acknowledgments and retransmissions.
- Delivery, ordering, and reliability depend on the protocols involved, not on the word “frame” alone.

7. Key Takeaways
- A frame is a Layer 2 data unit used to carry data across a local link.
- Ethernet frames use MAC addresses and commonly carry an IP packet as their payload.
- Routers typically place a forwarded packet into a new frame for each outgoing link.
- The Ethernet FCS detects errors; it does not by itself guarantee retransmission.

8. Sources
- [Coded Conversations: Frames and Packets in Computer Networks](https://www.patreon.com/posts/frames-and-in-101725193)
- [YouTube: Packets and Frames — The containers of networking](https://www.youtube.com/watch?v=-hkF4OyxzNQ)
- [RFC 894: A Standard for the Transmission of IP Datagrams over Ethernet Networks](https://datatracker.ietf.org/doc/html/rfc894)
- [Wireshark Wiki: Ethernet](https://wiki.wireshark.org/Ethernet)
