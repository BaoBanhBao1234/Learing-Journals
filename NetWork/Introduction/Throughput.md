1. What is Network Throughput?
- Network throughput is the amount of data successfully transferred from a source to a destination over a period of time.
- It describes the data rate achieved in real network conditions, rather than the maximum capacity a link could theoretically provide.
- Throughput can be measured for one connection, one application, or the combined traffic on a network link.

2. Units and Calculation
- Throughput is commonly measured in bits per second (bps), such as Mbps or Gbps. File transfer tools may report bytes per second (B/s, MB/s, or GB/s).
- One byte contains 8 bits, so convert between the units before comparing results.
- A basic calculation is the amount of data transferred divided by the elapsed time.

```text
Throughput = data transferred / transfer time

50 MB / 10 seconds = 5 MB/s
5 MB/s × 8 = 40 Mb/s
```

- The example is an average rate. Protocol overhead and the way a tool measures data can affect the reported result.

3. Throughput, Bandwidth, and Goodput
- **Bandwidth** is the maximum capacity or data rate a connection can support under specified conditions.
- **Throughput** is the actual rate of data transfer achieved over time. It is usually below the available bandwidth because of overhead, congestion, loss, and device or server limits.
- **Goodput** is the rate of useful application data delivered, excluding protocol headers and retransmitted data.
- A high-bandwidth connection does not guarantee that a particular transfer will achieve high throughput.
- See [Bandwidth.md](Bandwidth.md) for bandwidth and [Latency.md](Latency.md) for network delay.

4. Throughput and Latency
- **Latency** measures how long data takes to travel between endpoints, usually in milliseconds.
- **Throughput** measures how much data is transferred over time, usually in bits or bytes per second.
- They describe different properties, but can influence each other. For example, packet loss or high latency can reduce the rate achieved by some transport protocols.
- A connection can have low latency but limited throughput, or high throughput but noticeable delay for interactive tasks.

5. Factors That Affect Throughput
- **Available bandwidth and bottlenecks:** the narrowest or most heavily used link can limit the transfer rate.
- **Congestion:** competing traffic can cause packets to queue or be dropped.
- **Packet loss and retransmissions:** lost data may need to be resent, reducing the rate of useful delivery.
- **Latency and protocol behavior:** protocols react to delay and loss differently, which can affect the rate they achieve.
- **Network equipment:** routers, switches, wireless access points, and network adapters have processing and link limits.
- **Endpoints and applications:** CPU, storage, software, and server capacity can limit how quickly data is sent or received.
- **Protocol overhead:** headers, acknowledgments, and control messages use some of the available capacity.

6. Measuring Throughput
- File-transfer measurements can estimate throughput by dividing the transferred data by the time taken.
- Network testing tools such as `iperf3` can measure throughput between two endpoints under controlled conditions.
- Internet speed tests estimate performance between your device and a selected test server; results can vary with time, server, Wi-Fi conditions, and other traffic.
- `ping` measures round-trip delay, not throughput. Use it alongside throughput measurements when diagnosing overall network performance.
- For a useful comparison, record the endpoints, test duration, connection type, and whether other traffic was active.

7. Improving Throughput
- First identify the limiting link, device, server, or application; upgrading bandwidth alone will not help if another component is the bottleneck.
- Reduce unnecessary competing traffic or schedule large transfers during less busy periods.
- Resolve packet loss, faulty equipment, and poor wireless conditions.
- Optimize server, storage, and application performance so endpoints can process data at the network’s available rate.
- Where appropriate, use traffic management or quality-of-service policies to prioritize important workloads.

8. Key Takeaways
- Throughput is the data rate actually achieved over a period of time.
- Bandwidth is capacity; latency is delay; throughput is realized transfer rate.
- Loss, congestion, protocol behavior, network equipment, and endpoint performance can all reduce throughput.
- Measure throughput together with latency and packet loss to understand network performance.

9. Sources
- [AWS: Throughput vs. Latency](https://aws.amazon.com/compare/the-difference-between-throughput-and-latency/)
- [YouTube video](https://www.youtube.com/watch?v=l23baEHJ9YQ)
- [AWS: What is Network Latency?](https://aws.amazon.com/what-is/latency/)
