1. Tạo List
- List có thể chứa nhiều kiểu dữ liệu, thay đổi được sau khi tạo, chứa được các phần tử trùng nhau
2. Truy cập phần tử thông qua index của phần tử đó
- Index sẽ đi từ 0 đến n
3. Cắt list bằng slicing
- list[vị trí bắt đầu : vị trí kết thúc (sẽ bị -1) : bước nhảy]
- nếu để trống hết như này [::] thì sẽ lấy toàn bộ phần tử có trong list 
- nếu để step là số âm thì nó sẽ lấy từ phải sang
4. Thay đổi giá trị của phần tử trong list
- Thông qua truy cập phần tử bằng index để thay đổi value của phần tử đó
5. Các phương thức của list
+ append(): Thêm phần tử vào cuối list
+ extend(): Thêm nhiều phần tử cùng lúc
+ insert(index,value): Chèn một phần tử vào vị trí 
+ remove(): Xóa phần tử bắt gặp đầu tiên theo value
+ pop(index): xóa theo vị trí và lưu lại value của phần tử đó
- Nếu để trống index thì nó sẽ xóa phần từ cuối cùng của list
+ clear(): xóa toàn bộ list
+ index(): Tìm vị trí của phần tử
+ count(): Đếm số lần xuất hiện của phần tử
+ sort(): Sắp xếp trực tiếp List theo chiều tăng dần 
- Không trả về list mới đã sắp xếp mà sắp xếp trực tiếp trên list hiện có, sắp xếp giảm dần thì sort(reverse = True), theo độ dài chuỗi thì sort(Key = len)
+ reverse(): Đảo ngược thứ tự trực tiếp List
+ copy(): sao chép list
6. Xóa bằng del
7. Các toán tử với list
+ Nối hai list bằng dấu '+'
+ Lặp list bằng dấu '*'
+ Kiểm tra phần tử bằng 'in' hoặc 'not in'
+ So sánh 2 list
8. Các hàm thường dùng với list
+ len(): số lượng phần từ
+ sum(): tính tổng
+ min() và max(): tìm min và max
+ sorted(): sắp xếp tăng dần và lưu list đã sắp xếp trong một list khác
+ reversed(): đảo ngược thứ tự list và lưu list đã đảo ngược sang một list khác
+ any(): kiểm tra ít nhất 1 phần tử đúng
+ all(): kiểm tra tất cả phần tử đúng 
9. Duyệt list
+ Duyệt trực tiếp: for tên biến in list
+ Duyệt bằng index: for index in range(len(list))
+ Duyềt bằng enumerate: for index, value in enumerate(list)
- có thể thêm start = n để khi in ra nó sẽ in ra index + n
+ Duyệt bằng vòng lặp while: index - 0 và while index < len(list) và i+=1
10. List comprehension - Tạo list ngắn gọn hơn
+ [Giá trị đúng + for + tên biến + in range()]
+ [Giá trị đúng + for + têm biến + in + list + if + điều kiện]
+ [Giá trị đúng + if + điều kiện + else + Giá trị sai + for + phần tử in + list]
11. Map() và filter()
+ Map(): biến đổi từng phần tử
Ex: list(map(lambda tên biến: giá trị đúng, list))
+ filter(): lọc phần tử
Ex: list(filter(lambda tên biến: điều kiện, list))
12. Duyệt nhiều list bằng zip()
+ for tên biến1, tên biến2 in zip(list1,list2)
+ tạo list mới bằng zip(): zip(list1,list2)\
13. Loại bỏ phần tử trùng nhau
+ list(set(list))
+ list(dict.fromkeys(list))
14. Nhâp list từ bàn phím
+ tạo một list trống và số lượng phần tử cần thêm
+ chạy for i in range(số lượng phần tử)
+ nhập giá trị 
+ thêm vào cuối bằng append()
15. Chuyển đổi list sang các kiểu dữ liệu khác
+ "".join(list): chuyển list thành chuỗi
+ split() để chuyển chuỗi thành list
16. Gán nhiều biến bằng unpacking
Ex: numbers = [1,2,3] a,b,c = numbers #a= 1,b=2,c=3
    numbers = [1,2,3,4,5] first,*middle,last = numbers #first = 1, middle = [2,3,4], last = 5
17. Tìm kiếm trong list
+ Kiểm tra tồn tại
+ Tìm vị trí
+ Tìm tất cả vị trí
18. List 2 chiều - ma trận
+ Truy cập thông qua hai chỉ số index để lấy được chính xác phần tử cần lấy còn nếu chỉ có 1 index thì nó sẽ trả về một là hàng 2 là dòng
+ Duyệt ma trận thì dùng 2 vòng for lồng nhau để duyệt 
+ Tạo ma trận
19. Sao chép list và lỗi tham chiều
+ Gán trực tiếp không sao chép
Ex: a = [1, 2, 3]
    b = a
    b.append(4)
    print(a)  # [1, 2, 3, 4]
+ Sao chép nông
Ex: b = a.copy()
    b = list(a)
    b = a[:]   
+ List lồng nhau
Ex: a = [[1, 2], [3, 4]]
    b = a.copy()
    b[0][0] = 99
    print(a)  # [[99, 2], [3, 4]] 
hoặc
    import copy
    b = copy.deepcopy(a)
20. Sắp xếp nâng cao
+ sắp xếp cho tuple: cần có key lambda tên biến: tên list[index]
21. List dùng như stack
+ append() xong lại pop()
22. List dùng như quene 
+ append() xxong pop(0) đối với list không quá lớn
+ deque và popleft() đối với list lớn
23. Độ phức tạp cơ bản
+ Truy cập: O(1)
+ Thêm cuối: trung bình O(1)
+ pop(): O(1)
+ Chèn đầu: O(n)
+ Xóa đầu pop(0): O(m)
+ Tìm bằng in: O(n)
+ index(): O(n)
+ remove(): O(n)
+ sort(): O(nlogn)
