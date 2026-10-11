1. Hardware Abstraction and System Architecture
- Hardware Components and CPU Execution loop
+ THe physical Machinery: CPU, Registers, Bus and RAM
+ CPU: Control Unit (CU): decodes-opcodes
                          generates signal
                          directs dataflow
       Arithmetic Logic Unit (ALU): Arithmetic
                                    Logic
                                    Comparisons
       Registers: PC/IP
                  IR
                  SP
                  General (Rx)
+ System Bus: Address Bus (unidirectional from CPU)
              Data Bus (bidirectional)
              Control Bus (read/write, clock, status)
+ Main memory (RAM): Byte-addressable storage holding machine instructions and runtime data
- The Central Processing Unit (CPU)
+ The CPU contains three primary internal functional blocks
- - Control Unit (CU): Decodes incoming binary machine instructions and issues electrical control signals to orchestrate data movement across internal registers, the arithmetic units and external buses
- - Arithmetic Logic Unit (ALU): Executes mathematical computations (such as integer addition and substraction) and boolean logic operations (such as bitwise AND, OR, XOR, and comparisons)
- - Internal Registers: Extremely fast, on-chip storage location directly accessible by the ALU and CU within a single clock cycle 
2. Window commands
- ipconfig: View and manage network configuration.
- ipconfig /all: Display detailed network configuration.
- findstr: Search for text in command output or files.
- ipconfig /release: Release the current DHCP lease.
- ipconfig /renew: Request a new DHCP lease.
- ipconfig /displaydns: Display the DNS resolver cache.
- clip: Copy command output to the clipboard.
- ipconfig /flushdns: Clear the DNS resolver cache.
- nslookup: Query DNS records and name-resolution servers.
- cls: Clear the Command Prompt screen.
- getmac /v: Display detailed MAC address information.
- powercfg /energy:  Analyze energy efficiency and related issues.
- powercfg /batteryreport: Generate a battery usage and capacity report.
- assoc:  View or change file-extension associations in CMD.
- chkdsk /f: Find and fix file-system errors.
- chkdsk /r: Locate bad sectors and attempt to recover readable data; this also performs /f checks.
- sfc /scannow: Scan and repair protected Windows system files.
- DISM /Online /Cleanup-Image /CheckHealth: Check previously recorded image corruption.
- DISM /Online /Cleanup-Image /ScanHealth: Scan the Windows component store for corruption.
- DISM /Online /Cleanup-Image /RestoreHealth: Repair Windows component-store corruption.
- tasklist | findstr "script": Filter the process list for matching text.
- taskkill /F /PID <PID>: Force termination of the specified process; replace <PID> with its process ID.
- netsh: View and configure network settings.
- netsh interface show interface: List network interfaces.
- netsh interface ip show address | findstr "IP Address": Filter the output by its English label.
- netsh interface ip show dnsservers: Display configured DNS servers.
- netsh advfirewall set allprofiles state off: Disable Windows Firewall for all profiles.
- netsh advfirewall set allprofiles state on: Enable Windows Firewall for all profiles.
- ping checks ICMP responses and round-trip times, not download/upload throughput. Missing replies can also result from ICMP being blocked.
- ping -t: Continuously send ICMP echo requests to observe connectivity over time.
- tracert: Trace the route to a destination.
- tracert -d: Trace the route without resolving router addresses to hostnames.
- netstat: Display network connections and listening ports.
- netstat -af: -a shows connections and listening ports; -f shows fully qualified destination names when resolvable.
- netstat -o: Show the PID of the process owning each connection.
- netstat -e 5: Display Ethernet statistics every 5 seconds.
- route print: Display the IP routing table.
- route add: Add a route to the routing table.
- route delete: Remove a route from the routing table.
- shutdown: Shut down or restart the computer, or sign out, depending on the options used.
