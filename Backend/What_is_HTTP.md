1. What is HTTP?
- THe Hypertext Transfer Protocol (HTTP) is the foundation of the World Wide Web and is ised to load webpages using hypertext links. HTTP is an "application layer" protocol designed to transfer information between networked devices and runs on top of other layers of the network "protocol" stack. A tyical flow over HTTP involves a client machine making a requests to a server, which then sends a response message
2. What is a HTTP request?
- A HTTP request is the way Internet communications platforms such as web browsers ask for the information they need to load a website
- Each HTTp request made across the Internet carries with it  a series of ecoded data that carries different types of information. A typical HTTp request contains:
+ HTTP version type
+ A URL
+ A HTTP method
+ HTTP request headers
+ Optional HTTP body
3. What is a HTTP method?
- A HTTp method, sometimes referred to as a HTTP verb, indicates the action that the HTTP request expects from the queried server
4. What are HTTP request headers?
- HTTP headers contain text information stored in key-value pairs and they are included in every HTTP request. These headers communicate core information
Ex: Request headers:
:authority: www.google.com
:method: GET
:path: /
:scheme: https:
accept: text/html
accept-encoding: gzip, deflate, br
accept-language: en-US, en;, q = 0.9
upgrade-insecure-requests: 1
user-agent: Mozilla/5.0
5. What is in a HTTP request body?
- The body of a request is the part that contains the body of information the request is transfering. The body of a HTTP request contains any information being sumitted to the web server, such as a username and password, or any other data enterd into a form
6. What is in a HTTP response?
- A HTTP response is what web clients (often browsers) receive from an Internet server in answer to a HTTP request. These responses communicate valuable information based on what was asked for in the HTTP request
- A typically HTTP response contains:
+ a HTTP status code
+ HTTP response headers
+ optional HTTP body
7. What is a HTTP status code?
- HTTP status cpdes are 3-digit codes most often used to indicate whether a HTTP request has been successfully completed. Status codes are nroken into the following 5 blocks:
+ 1xx informational
+ 2xx success
+ 3xx redirection
+ 4xx client error
+ 5xx server error
- The "xx" refers to different numbers between 00 and 99
- Status codes starting with number "2" indicate a success. For example, after a client requests a webpage, the most commonly seen responses have a status code of "200 OK", indicating that the request was properly completed
- If the response starts with "4" or "5" that means there was an error and the webpage will not be displayed. A status code that begins with a "4" indicates a client-side error.A status code that begins with a "5" means something went wrong on the server side. Status codes can also begin with a "1" and "3" which indicate an informational response and a redirect, respectively
EX: Response headers
cache-control: private, max-age = 0
content-encoding: br
content-type: text/html; charset = UTF-8
date: Thu, 21 Dec 2017 18:25:00 GMT
status: 200
strict-transport-security: max-age = 86400
x-frame-options: SAME ORIGIN
7. What is in a HTTP response body?
- Succesful HTTP responses to "GET" requests generally have a body which contains the requested information. In most web requests, this is HTML data that a web browser will translate into a webpage
8. Can DDoS attacks be laucheed over HTTP?
- HTTP is a "stateless" protocol, which means that each command runs independent if any other command. In the original spec, HTTP requests each created and closed a "TCP" connection. In newer versions of the HTTP Protocol (HTTP 1.1 and above), persistent connection allows for multiple HTTP requests to pass over persistent TCP connection, improving resource consumption. In the context of DoS or DDoS attacks, HTTP requests in large quantities can be used to mount an attack on a target device and are considered part of application layer attacks or layer 7 attacks
9. Why do we need HTTP/3?
- HTTP/3 was created mostly because TCP became difficult to improve. TCP has existed for decades and is implemented in many devices such as routers, firewalls, proxies and load balancers. Changing TCP therefore requires many intermediate devices to support the new changes
10. What is QUIC?
- QUIC is a modern transport protocol designed to provide many of TCP's reliability features while solving some of TCP's limitations
- QUIC cannot work without encryption
- Advantages: Better security, Faster connection setup, Easier protocol evolution
- Potential Disadvantages: Firewalls/Network equipment may block QUIC, Debugging network problems may become harder, Encryption introduces processing overhead
- QUIC performs less revocery on individual streams instead of blocking all streams in the connection
- HTTP/3 uses QUIC instead of TCP
- QUIC runs over UDP
- QUIC integrates TLS 1.3
- QUIC supports multiple independent streams
- PAcket loss in one stream does not necessarily block aother streams 
- QUIC supports connection migration
- QUIC uses flexible frames
                  -> TLS -> Encryption Security
- HTTP/3 -> QUIC  -> Streams -> Less HoL Blocking -> UDP -> IP
                  -> CID -> Connection migration