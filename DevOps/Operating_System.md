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
- ipconfig: xem và quản lý cấu hình mạng
- ipconfig /all: xem chi tiết mạng
- findstr ... tìm kiếm
- ipconfig /release: khắc phục bằng giải phóng IP hiện tại
- ipconfig /renew: xin cấp lại IP mới từ router
- ipconfig /displaydns: hiển thị cache DNS
- clip: sao chép cache
- ipconfig /flushdns: xóa bộ nhớ đệm
- nslookup: tra cứu và truy vấn hệ thống phân giải dns
- cls: xóa màn hình
- getmac /v: hiển thị địa chỉ mac
- pơercfg /energy: đánh giá hiệu suất năng lượng và kiểm tra thời lượng pin
- pơercfg /batteryreport: kiểm tra độ chai pin và lịch sử sạc
- asoc: xem hoặc thay đổi mối liên kết định dạng với tập tin
- chkdsk /f: quét, phát hiện , tự động sửa lỗi tâpk tin ổ cứng
- chkdsk /r: quét sâu và mạnh
- sfc /scannow: quét toàn bộ tập tin, tự thay thế tệp lỗi
- DISM /Online /Cleanup /CheckHealth
- DISM /Online /Cleanup /ScanHealth
- DISM /Online /Cleanup /RestoreHealth
- táklist /findstr script 
- tákill /f: ép dừng ngay lập tức các tiến trình
- netsh: xem, cấu hình và quản lý toàn bộ các thiết lập mạng
- netsh interface show interface: hiển thị card mạng
- netsh interface ip show address /findstr "IP Address"
- netsh interdace ip show dnsservers: hiển thị DNS servers
- netsh firewall set allprofiles state off : tắt firewall
- netsh firewall set allprofiles state on : bật firewall
- ping: kiểm tra có kết nối mạng, đo tốc độ
- ping -t: kiểm tra mạng chập chờn, đo độ ổn định
- tracert: theop dõi và hiển thị lộ trình
- tracert -d: hiển thị địa chỉ ip chuẩn
- netstat: hiển thị toàn bộ kết nối mạng
- netstat -af: hiển thị DNS hoàn chỉnh
- néttat -o: bổ sung PID
- néttat -e -t 5: thống kê Ethernet
- route print: hiển thị bảng định tuyến
- route add: thêm route
- route delete: xóa route
- shutdown: tắt máy, reset máy, reset và lưu hoạt động, sleep, sign out
