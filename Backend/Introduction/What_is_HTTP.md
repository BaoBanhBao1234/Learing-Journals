1. What is HTTP?
- ==HTTP (Hypertext Transfer Protocol) is an application-layer protocol used to exchange resources between clients and servers on the Web.==
- ==A client, commonly a web browser or an application, sends a request. A server processes it and returns a response.==
- ==HTTP can transfer HTML, images, video, JSON, and other resource formats. It runs over lower-level network protocols that handle delivery between devices.==
- ==HTTP is stateless: each request is independent, and the protocol itself does not remember earlier requests. Applications can maintain state with mechanisms such as cookies, session identifiers, or tokens.==

2. URLs and HTTP Requests
- ==A URL identifies a resource and can include a scheme, host, optional port, path, query string, and fragment.==
+ ==The scheme indicates how to access the resource, such as `http` or `https`.==
+ ==The host identifies the server, usually with a domain name.==
+ ==The port identifies a service on the server. HTTP commonly uses port 80 and HTTPS commonly uses port 443, but other ports can be used.==
+ ==The path identifies a resource on the server; the query string can provide parameters to the request.==
+ ==The fragment identifies a location within a resource and is generally handled by the client rather than sent as part of the HTTP request.==
- ==A typical HTTP request contains a method, request target, HTTP version, headers, and sometimes a body.==
- ==Request headers are key-value fields that provide metadata, such as accepted content types, authentication data, or information about the client.==
- ==A request body carries data sent to the server, often with methods such as `POST`, `PUT`, or `PATCH`. Many `GET` requests do not have a body.==

3. HTTP Methods
- ==A method describes the intended action for a request.==
+ ==`GET`: Retrieve a resource.==
+ ==`POST`: Submit data, often to create a resource or trigger processing.==
+ ==`PUT`: Create or replace a resource at a specified location.==
+ ==`PATCH`: Apply a partial update to a resource.==
+ ==`DELETE`: Request removal of a resource.==
+ ==`HEAD`: Request the response headers without the response body.==
+ ==`OPTIONS`: Ask which communication options are available for a resource.==
- ==A method communicates intent; the server's behavior and whether an operation changes data depend on the application and its implementation.==

4. HTTP Responses and Status Codes
- ==An HTTP response contains a status code, response headers, and sometimes a body.==
- ==Response headers describe the response and its content, such as the content type, caching instructions, or encoding.==
- ==A response body may contain the requested HTML, JSON, an image, or an error message.==
- Status codes are three-digit numbers grouped into five classes:
+ ==`1xx`: Informational response.==
+ ==`2xx`: The request succeeded.== `200 OK` is a common example.
+ ==`3xx`: Redirection or another response that requires the client to take further action.==
+ ==`4xx`: A problem with the request==, such as `404 Not Found` when a resource cannot be found.
+ ==`5xx`: The server encountered an error while handling a request.==
- ==An error status does not necessarily mean that no response body is sent; a server may return a page or data explaining the error.==

5. HTTP and HTTPS
- ==HTTP itself does not encrypt data. If plain HTTP is used, traffic may be readable or modifiable by parties able to observe the network path.==
- ==HTTPS is HTTP protected by TLS (Transport Layer Security).==
- ==TLS helps provide confidentiality (encryption), integrity (detecting changes), and authentication of the server through certificates.==
- ==HTTPS is important whenever a site handles logins, personal information, payments, or other data that should be protected in transit.==

6. How HTTP Has Evolved: HTTP/1, HTTP/2, and HTTP/3
- ==HTTP versions preserve the basic request-and-response semantics while changing how messages are framed and transported.==
- ==HTTP/1.0 commonly used a separate TCP connection for each request. HTTP/1.1 introduced persistent connections (keep-alive), allowing multiple requests and responses to reuse a TCP connection.==
- ==HTTP/1.1 pipelining can send multiple requests without waiting for each response, but responses must remain in order. This can cause head-of-line (HoL) blocking, where an earlier slow response delays later responses.==
- ==HTTP/2 uses binary framing and multiplexes multiple streams over one TCP connection. It also introduced header compression (HPACK) and stream prioritization. Multiplexing reduces application-level waiting, but TCP still delivers one ordered byte stream; packet loss can delay data across all HTTP/2 streams on that connection.==
- ==HTTP/2 also defined server push, which lets a server proactively send resources. Support and practical use have been limited, so it should not be treated as the main reason to use HTTP/2.==
- ==HTTP/3 carries HTTP semantics over QUIC, which runs over UDP. QUIC provides reliable delivery, congestion control, and multiplexed streams; it is not simply unreliable UDP.==
- ==QUIC integrates TLS 1.3 and uses connection IDs. These IDs can help a connection continue when a device changes networks, such as moving from Wi-Fi to cellular.==
- ==HTTP/3 handles independent streams at the transport layer. Packet loss affecting one stream does not necessarily block other streams, although data within an affected stream still follows ordered delivery.==
- ==HTTP/3 can reduce some connection and packet-loss delays, but it is not automatically faster in every situation. Performance depends on network conditions, server and client support, and the workload.==

7. A Basic Request and Response Flow
- ==A client parses a URL and identifies the destination host and resource.==
- ==The client establishes the appropriate network connection. For HTTPS, it also establishes a TLS-protected connection; TLS 1.3 is integrated into QUIC for HTTP/3.==
- ==The client sends an HTTP request containing the method, target, headers, and any request body.==
- ==The server processes the request and returns a status code, headers, and any response body.==
- ==The client interprets the response. A browser may then request more resources, such as stylesheets, scripts, images, or data for an application.==

8. HTTP, APIs, and Security Context
- ==Web APIs commonly use HTTP to exchange structured data, often JSON, between applications and servers.==
- ==HTTP headers can communicate content types, authentication information, caching rules, and other metadata.==
- ==Since HTTP is stateless, applications that need a user session usually send a cookie, token, or other identifier with requests and maintain the related state separately.==
- ==A large volume of HTTP requests can be used in an application-layer denial-of-service (DoS) or distributed denial-of-service (DDoS) attack. Servers and network services use defenses such as rate limiting and traffic filtering.==

9. Key Takeaways
- HTTP defines how clients request resources and how servers respond.
- Requests include a method, target, and headers, with an optional body; responses include a status code, headers, and an optional body.
- HTTP is stateless by itself, while applications can add session behavior using cookies or tokens.
- HTTPS protects HTTP traffic with TLS.
- HTTP/1.1 added reusable connections, HTTP/2 added multiplexed streams over TCP, and HTTP/3 uses QUIC over UDP to handle streams independently at the transport layer.

10. Sources
- Cloudflare: What is HTTP? https://www.cloudflare.com/en-gb/learning/ddos/glossary/hypertext-transfer-protocol-http/
- ByteByteGo: HTTP/1 to HTTP/2 to HTTP/3 (YouTube) https://www.youtube.com/watch?v=a-sBfyiXysI
- freeCodeCamp: Full HTTP Networking Course (YouTube) https://www.youtube.com/watch?v=2JYT5f2isg4
