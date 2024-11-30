# Bài tập Buổi 4: Cấu trúc điều khiển


### **Phần 1: `if`, `else if`, `else`**

1. **Kiểm tra số chẵn hay số lẻ:**
   - Nhập một số nguyên từ người dùng và kiểm tra xem số đó là số chẵn hay số lẻ.

2. **Kiểm tra độ tuổi:**
   - Nhập tuổi từ người dùng. In ra "Trẻ em" nếu tuổi dưới 12, "Thanh thiếu niên" nếu từ 12-17, và "Người lớn" nếu từ 18 trở lên.

3. **Tính điểm trung bình:**
   - Nhập ba điểm số từ người dùng. Kiểm tra nếu điểm trung bình:
     - Nếu >= 9: "Xuất sắc"
     - Nếu>= 7: "Khá"
     - Nếu>= 5: "Trung bình"
     - Nếu Dưới 5: "Yếu".

4. **Xếp loại khách hàng:**
   - Số tiền mua hàng của khách:
     - Nếu>= 1,000,000: "Khách VIP"
     - Nếu>= 500,000: "Khách Thân Thiết"
     - Nếu< 500,000: "Khách Thường".

5. **Tính thuế thu nhập cá nhân:**
   - Nhập thu nhập từ người dùng, tính thuế theo các mức:
     - Nếu <= 10 triệu: 10%
     - Nếu từ 10-20 triệu: 15%
     - Nếu  > 20 triệu: 20%.

6. **Kiểm tra tam giác:**
   - Nhập ba cạnh của một tam giác và kiểm tra xem đó có phải là tam giác không. Nếu có, xác định là tam giác thường, cân, hay đều.

7. **Tính tiền điện:**
   - Nhập số kWh tiêu thụ. Tính tiền điện theo mức giá:
     - Nếu <= 50 kWh: 1,500 đồng/kWh
     - Nếu 51-100 kWh: 2,000 đồng/kWh
     - Nếu > 100 kWh: 2,500 đồng/kWh.

8. **Tính tiền mua vé xem phim:**
   - Nếu tuổi dưới 12: giá vé 50k
   - 12-18 tuổi: 75k
   - Trên 18 tuổi: 100k.

9. **Xếp loại học sinh:**
   - Nhập điểm 5 môn học, tính điểm trung bình và xếp loại:
     - Giỏi: >= 8
     - Khá: 6.5-7.9
     - Trung bình: 5-6.4
     - Kém: < 5.

10. **Phân loại người dùng khách sạn:**
    - Khách du lịch nước ngoài: Thu thêm phí 10%.
    - Khách nội địa: Thu bình thường.
    - Nếu ở hơn 3 ngày: Giảm giá 5%.

---

### **Phần 2: `switch`**

1. **Ngày trong tuần:**
   - Nhập một số từ 1 đến 7 và in ra ngày tương ứng (1: "Thứ Hai", 7: "Chủ Nhật").

2. **Kiểm tra mùa trong năm:**
   - Nhập một số từ 1 đến 12 và in ra mùa tương ứng:
     - 1-3: Xuân
     - 4-6: Hạ
     - 7-9: Thu
     - 10-12: Đông.

3. **Tính giá trị đơn vị tiền:**
   - Nhập ký hiệu đồng tiền (`USD`, `EUR`, `VND`) và in ra giá trị quy đổi tương ứng.

4. **Chọn món ăn trong thực đơn:**
   - Dựa vào số món ăn khách chọn (1: Pizza, 2: Burger, 3: Salad), in ra giá của món đó.
   - Giá bạn tự quy định tương ứng cho mỗi loại.

5. **Tính số ngày trong tháng:**
   - Nhập tháng và năm, trả về số ngày trong tháng đó.

6. **Chọn phương thức thanh toán:**
   - 1: Tiền mặt
   - 2: Thẻ ngân hàng
   - 3: Ví điện tử.

   Sau đó in ra với cú pháp: Bạn đã chọn + tên phương thức đã chọn

7. **Kiểm tra học kỳ:**
   - Nhập số (1: Học kỳ 1, 2: Học kỳ 2, 3: Hè) và in ra thời gian tương ứng.

8. **Xác định loại phương tiện:**
   - Nhập loại phương tiện giao thông (car, bike, bus), in ra số ghế trung bình.
   - Số ghế bạn tự quy định phù hợp cho mỗi loại phương tiện

9. **Quản lý vé máy bay:**
   - Nhập hạng vé (1: Economy, 2: Business, 3: First Class), in ra giá vé.
   - Giá bạn tự quy định tương ứng cho mỗi loại.

10. **Chương trình khuyến mãi:**
    - Nhập mã khuyến mãi, in ra chiết khấu tương ứng.
    - Thông tin bạn tự quy định tương ứng cho mỗi loại.

---

### **Phần 3: Regular Expression**

1. **Kiểm tra email hợp lệ:**
   - Nhập một chuỗi, kiểm tra xem nó có phải email hợp lệ không.

2. **Kiểm tra số điện thoại hợp lệ:**
   - Số điện thoại bắt đầu bằng `09` hoặc `08` và có 10 chữ số.

3. **Xác định mã bưu chính:**
   - Kiểm tra xem chuỗi có phải mã bưu chính Việt Nam (gồm 6 chữ số) không.

4. **Kiểm tra mật khẩu mạnh:**
   - Mật khẩu cần ít nhất 8 ký tự, có chữ hoa, chữ thường, số, và ký tự đặc biệt.

5. **Xác định URL hợp lệ:**
   - Kiểm tra chuỗi có phải một URL đúng định dạng không (bắt đầu bằng `http://` hoặc `https://`).

6. **Đếm số từ trong chuỗi:**
   - Dùng regex đếm xem chuỗi nhập vào có bao nhiêu từ.

7. **Loại bỏ ký tự đặc biệt:**
   - Nhập một chuỗi và loại bỏ tất cả ký tự đặc biệt trong đó.

8. **Kiểm tra biển số xe:**
   - Biển số hợp lệ gồm 2-3 chữ số đầu, dấu cách, và 4 chữ số cuối (VD: `30A 12345`).

9. **Kiểm tra tên người:**
   - Nhập tên, kiểm tra xem có phải chỉ gồm chữ cái và khoảng trắng không.

10. **Tách số khỏi chuỗi:**
    - Nhập một chuỗi và tách tất cả các số trong chuỗi đó ra.

---
