1. What is Network Latency?
- Network latency is the time delay that occurs as data travels between two points on a network.
- It is commonly measured in milliseconds (ms). Lower latency generally means a faster response; higher latency means more delay.
- Latency can include delays from the network path, network devices, and the server or application processing a request.

2. Round-Trip Time and Time to First Byte
- **Round-Trip Time (RTT)** measures the time for a request or probe to travel from a source to a destination and for a response to return.
- **One-way latency** measures travel in one direction. It can be difficult to measure accurately without synchronized clocks at both endpoints.
- **Time to First Byte (TTFB)** measures how long it takes for the first response byte to reach a client after a request. It can include server processing time as well as network delay.
- A `ping` test commonly reports an RTT estimate using ICMP. It does not necessarily measure the response time of a specific application or website.

```text
Client sends request --------> Server
Client receives response <---- Server
             total time = RTT
```

3. Common Causes of Latency
- **Distance:** data traveling farther between endpoints generally takes longer.
- **Transmission medium:** signals travel through fiber, copper, or wireless links, each with different characteristics.
- **Network hops:** routers and other devices need time to process and forward traffic.
- **Congestion and queuing:** when links or devices are busy, packets may wait before they can be sent or processed.
- **Server or application processing:** a slow server response can increase the time a user experiences, even when the network path is working normally.
- **Packet loss and retransmissions:** lost data may need to be sent again, adding delay for some protocols and applications.

4. Why Latency Matters
- High latency can make websites and APIs feel slow because clients wait longer for responses.
- It affects interactive activities such as online gaming, video calls, remote control, and real-time analytics.
- Applications that make many sequential network requests can be especially sensitive because each response may need to arrive before the next step begins.
- Low latency is important for responsiveness, but it does not by itself guarantee high data-transfer rates or reliable delivery.

5. Latency vs. Bandwidth, Throughput, Jitter, and Packet Loss
- **Latency** measures delay, usually in milliseconds.
- **Bandwidth** is the maximum data-transfer capacity of a connection, usually measured in bits per second.
- **Throughput** is the amount of data actually transferred over time.
- **Jitter** is variation in packet delay over time. It can disrupt real-time audio and video even when average latency is acceptable.
- **Packet loss** is the proportion of packets that fail to reach their destination.
- These metrics describe different aspects of network performance. See [Bandwidth.md](Bandwidth.md) for more about bandwidth and throughput.

6. Measuring Latency
- Use RTT measurements to observe the time for a request and response between endpoints.
- Use tools such as `ping` for a basic connectivity and RTT check, and `traceroute` or `tracert` to inspect the route and per-hop responses where available.
- Use TTFB or application-specific monitoring when diagnosing website or API response time, because it can include server processing.
- Repeat measurements over time and compare the same endpoints. A single measurement may not represent typical conditions, and some devices or networks may block diagnostic probes.

7. Reducing Latency
- Host services or use edge locations closer to the users who access them, reducing the distance data must travel.
- Review routing and network paths to identify avoidable delays or congested links.
- Improve overloaded or outdated network devices and monitor queues, packet loss, and response times.
- Optimize server and application processing so requests do not wait unnecessarily before a response is sent.
- Traffic prioritization can reduce queuing delays for important real-time traffic on a busy network, but it cannot remove the physical delay caused by distance.

8. Key Takeaways
- Latency is the delay involved in sending data between network endpoints; it is commonly measured in milliseconds.
- RTT measures a trip to a destination and back, while TTFB also reflects server processing and response delivery.
- Distance, network devices, congestion, packet loss, and server processing can all contribute to perceived delay.
- Latency, bandwidth, throughput, jitter, and packet loss are related performance measures, but they are not interchangeable.

9. Sources
- [AWS: What is Network Latency?](https://aws.amazon.com/what-is/latency/)
- [YouTube video](https://www.youtube.com/watch?v=S0NKk86HRdg&pp=ygUZd2hhdCBpcyBhIGxhdGVuY3kgbmV0b3drcg%3D%3D)
- [Cloudflare: What is latency?](https://www.cloudflare.com/en-gb/learning/performance/glossary/what-is-latency/)
