1. What is the switch and why we need it?
- If we want the computers in the same environment to communicate, we can use a switch device
- We have CAT6: 10 Gbps,250MHz, distance <55m
          CAT6A: 10Gbps,500MHz, distance <100m
          CAT7/CAT8: 40-100Gbps,600-2000Mhz, distance <30m
*CAT = CATEGORY
- Fiber optic cables are much faster than copper cablesin general
- We always use cables to connect computers to the switch. A switch cannot use wireless technology
- If you want the devices in the same environment to be connected to each other over wireless technology, you should use an "Access Point"
- A local area network (LAN) is a computer network that connect computers within a restricted area such as a residence, school, laboratory, university campus or office building
*Packet/Frame
- In general, the higher the number of ports, the higher the price
*LAN ports
- We can plug the cables into the port we want. But it's always good to be organized
2. What is the router?
- The main task of a router is to enable computers to connect to the internet
- A special cable comes to our home and we connect to the internet by using this cable
- THis cable is given to us by the ISP (Internet Service Provider)
- There is definitely no need for a router for devices in the same LAN to communicate
- Either a switch or an access point device is sufficient for this purpose
- If the computer can send packets to the internet, this means that this computer can connect to the internet without any problems
- The device that delivers the packets from the LAN to the internet is the router
3. What does the internet represent?
- Connecting to the internet can stand for connecting to the another computer in any where in the world
- The structure that connects all LANs in the world is the internet
- Routers on the internet are distributed pretty widely
- A home-router is a combo device that is a mixture of router and switch
- Most home-routers nowadays also have an access point feature. In this way, you can use wireless technology as well if you want
- If there are to many devices in the environmet, you may have to use switches and routers as separate devices
- If we give entire the load to the single point, we call this problem "Single Point of Failure"
- LANs that are the furthest from the giant router would need very long cables
- If the internet uses only one router, this will overload the router
- Mess is minimized since not many cables are connected to routers in the distributed structure 
- Each router must a special table called "Routing Table". This table tells us which route the packet should choose
- The router learns the packet's destination then it looks at the routing table and learns over which port the packet will be sent
4. Forwarding
- Routers have special processors inside. These processors create Routing Tables by using special algorithms
5. Router Filtering
- A router always wants to deliver the packet to its destination in the fastest way possible
- When the routers create their routing tables, they are not only concerned with the number of points in order to choose the shortest route
6. Congestion Control
- The Internet is the network of networks:
+ Meaning of connecting to the Internet
- - We will only use the router feature of the Home-Router. As soon as you do something, your computer generates a request message and sends this message to do something. When you do something, it sends something to you piece by piece. We call it "Streaming"
- - Servers have to be much powerful than normal computers in terms of hardware
- All these servers have the same information:
+ Wide area network (WAN)
- - Thanks to WAN, we can ensure that LANs located in different parts of the world communicate as if they were in the same environment
- - The Internet is a public network and everyone owns the Internet
- -  There is always a possibility that a packet on the Internet could be seen and modified by others
- - People often use VPN (Virtual Private Network) to access restricted websites
- - The tunneling feature of the VPN provides us privacy, anonymity and security on the Internet
- - VPN tunnel does not represents high-security communication between two locations
- - A packet reaches its destination by passing through many routers, just as you know. But security is maximum thanks to VPN tunneling
- - Encryption + Encapsulation = Safe
- - Tunneling is a special encapsulation method 
- - End-to-end Encryption between end-points
7. What is the router
- Short distance
- We can create a single LAN by connecting 2 switches together
- Campus Area Network (CAN) is a special type of LAN
- Both of these methods are secure. However, LAN is more secure
- ISP WAN Network: dedicated line: Private WAN
- Private WAN can be quite costly, especially over long distances
- Lan -> switches, WAN -> routers
- The amin task if the router is to connect different networks. The location of thse networks does not matter 
8. Internet Service Provider (ISP)
- Each ISP is responsible for specific routers
- ISP represent companies that enable us to connect to the Internet for money
9. Point Of Presence (POP)
- In a POP, there can be routers, switches, servers and so on
- All of these router icons actually represent POPs
- Local ISPs connect: small places
- Regional ISP connect: big places
- Network of a country => Local ISP + Regional ISP
- Regional ISPs are ISPs that connect different cities within the same country
- If we connect all Local ISPs, we increase the complexity
- The ISP that connects different countries is the Global ISP
- Each router in Regional ISP makes a choice and the result of all these choices determines on which Global ISP the packet will be sent
- Packets can take a differnt route each turn:
+ Suitable location
+ Extra cost to build an infrastructure to direct connection. We have only 1 server in anywhere
- This response message contains all information re;lated to the webpage like images, videos, links HTML files and so on
+ User send a request message to the server
+ Server send a response message to the User
- A large companies want to communicate with their customers in the fasters and most efficient way, and distributed server structure is a very good solution
- Thanks to peering, we establishes an almost direct connection with the user
- Due to the direct connection, the packet passes through much less POP
10. Internet Backbone
- Internet Exchange Point is the structure that enables the Internet Backbone to work synchronously
- We can get service from any ISP serving for your location