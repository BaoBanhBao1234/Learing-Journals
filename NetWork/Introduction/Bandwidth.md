1. What is Network Bandwidth?
- Network bandwidth is the maximum rate at which a network connection can transfer data under specified conditions.
- It describes a link’s capacity, not a guarantee that an application will always achieve that rate.
- A common analogy is a road: bandwidth is like the number of lanes available for traffic at one time.

2. Bandwidth Units
- Bandwidth is usually measured in bits per second (bps), such as kilobits per second (Kbps), megabits per second (Mbps), or gigabits per second (Gbps).
- Network rates use bits (`b`), while file sizes are often shown in bytes (`B`). One byte is 8 bits.
- For example, a 100 Mbps connection has a theoretical rate of 12.5 MB/s before accounting for protocol overhead and other conditions.

```text
100 megabits/second ÷ 8 = 12.5 megabytes/second (theoretical maximum)
```

3. Bandwidth and Throughput
- **Bandwidth** is the maximum capacity of a connection or network path.
- **Throughput** is the amount of data successfully transferred over a period of time.
- Real throughput is often lower than the advertised or theoretical bandwidth because of protocol overhead, congestion, packet loss, and equipment or server limits.
- A speed test estimates performance at a particular time and between particular endpoints; results can change as network conditions change.

4. Bandwidth, Latency, and Network Speed
- **Latency** is the time it takes data to travel between two points, often measured in milliseconds. It measures delay, not capacity.
- Bandwidth describes how much data a link can carry at once; latency describes how long data takes to travel.
- A connection can have high bandwidth and still feel slow for interactive tasks if latency is high.
- Internet plans often use “speed” to refer to bandwidth, but user experience also depends on latency, packet loss, and the performance of devices and services.

5. Shared Bandwidth and Bottlenecks
- Devices and applications may share the capacity of a home, office, or provider network.
- When many users transfer data at the same time, congestion can reduce the throughput available to each activity.
- End-to-end performance is limited by the constrained link or device along the route, such as a Wi-Fi connection, router, ISP link, or server connection.
- A connection’s advertised bandwidth does not necessarily equal the rate available to every application or device.

6. Factors That Affect Throughput
- **Network congestion:** too much traffic competing for available capacity.
- **Protocol overhead:** some transmitted data is used for headers, acknowledgments, and control rather than application content.
- **Packet loss and retransmissions:** lost or corrupted data may need to be sent again and can reduce useful throughput.
- **Latency:** delays can affect how efficiently some protocols use a connection, especially over long-distance paths.
- **Hardware and connection quality:** router, network adapter, Wi-Fi signal, cables, and ISP equipment can limit performance.
- **Endpoint limits:** a client device, application, or remote server may be unable to send or receive data at the connection’s maximum rate.

7. Measuring and Improving Network Performance
- Measure throughput, latency, and packet loss together to understand what users experience.
- Compare results at different times and, when troubleshooting, test close to the router and with a wired connection to help isolate Wi-Fi issues.
- Monitor which applications, devices, or network links use the most capacity.
- Reduce avoidable traffic, schedule large transfers outside busy periods, or use traffic shaping and quality-of-service policies when appropriate.
- Upgrade a connection or network component when measurements show that its capacity is the bottleneck.

8. Key Takeaways
- Bandwidth is a connection’s maximum data-transfer capacity, usually measured in bits per second.
- Throughput is the data rate actually achieved and is often lower than bandwidth.
- Latency is delay; it is related to network performance but measures something different.
- Congestion, packet loss, protocol overhead, hardware, and server limits can all affect throughput.

9. Sources
- [SolarWinds: What is Network Bandwidth?](https://www.solarwinds.com/resources/it-glossary/network-bandwidth)
- [YouTube video](https://www.youtube.com/watch?v=DHa9gxRfAmM)
- [Cloudflare: What is latency?](https://www.cloudflare.com/en-gb/learning/performance/glossary/what-is-latency/)
- [Cloudflare: Making home Internet faster has little to do with “speed”](https://blog.cloudflare.com/making-home-internet-faster/)
