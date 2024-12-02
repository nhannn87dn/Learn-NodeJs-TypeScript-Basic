# Bài tập Buổi 6: Objects

### **Bài Tập Về Object**

#### **1. Khai báo và in Object**
Khai báo object `car` với các thuộc tính:
- `brand: "Toyota"`, 
- `model: "Corolla"`, 
- `year: 2020`.

In ra toàn bộ thuộc tính của object.

---

#### **2. Thêm thuộc tính mới**
Với object `car` từ bài 1, thêm thuộc tính `color: "Red"` vào object. In lại object sau khi thêm.

---

#### **3. Xóa thuộc tính**
Xóa thuộc tính `model` trong object `car` và in lại object.

---

#### **4. Duyệt qua các thuộc tính**
Sử dụng vòng lặp `for...in` để in ra danh sách các thuộc tính và giá trị của object `car`.

---

#### **5. Gộp hai Object**
Cho hai object:
```javascript
const person = { name: "John", age: 30 };
const contact = { phone: "123-456-789", email: "john@example.com" };
```
Gộp hai object này thành một object duy nhất `merged`.

---

#### **6. Kiểm tra thuộc tính**
Cho object:
```javascript
const student = { name: "Alice", age: 22, grade: "A" };
```
Viết chương trình kiểm tra xem thuộc tính `age` có tồn tại trong object không.

---

#### **7. Object lồng nhau**
Tạo object `company`:
```javascript
const company = {
  name: "TechCorp",
  employees: [
    { name: "Alice", position: "Developer" },
    { name: "Bob", position: "Designer" },
    { name: "Charlie", position: "Manager" }
  ]
};
```
In ra danh sách tên của tất cả nhân viên.

---

#### **8. Trích xuất giá trị thuộc tính**
Cho object:
```javascript
const user = { username: "john_doe", password: "1234", email: "john@example.com" };
```
Viết hàm `getProperty(obj, key)` trả về giá trị của thuộc tính `key` trong object `obj`.

---

#### **9. Sao chép Object**
Sao chép object `student` từ bài 6 sang một object mới bằng cách sử dụng:
1. Spread operator.
2. `JSON.parse(JSON.stringify())`.

---

#### **10. Sắp xếp Object theo bảng chữ cái**
Cho object:
```javascript
const person = { z: 1, a: 2, m: 3 };
```
Sắp xếp các thuộc tính theo thứ tự bảng chữ cái và in ra object đã sắp xếp.

---

#### **11. Đếm số thuộc tính trong Object**
Cho object:
```javascript
const student = { name: "Alice", age: 22, grade: "A", major: "Computer Science" };
```
Viết hàm trả về số thuộc tính của object.

---

#### **12. Tìm giá trị lớn nhất**
Cho object:
```javascript
const scores = { Alice: 85, Bob: 92, Charlie: 78 };
```
Tìm học sinh có điểm cao nhất.

---

### **Bài Tập Về Date**

#### **1. Lấy ngày hiện tại**
In ra ngày, tháng, năm hiện tại dưới dạng `DD-MM-YYYY`.

---

#### **2. Hiển thị thời gian hiện tại**
In ra giờ, phút, giây hiện tại dưới dạng `HH:MM:SS`.

---

#### **3. Tính ngày mai**
Sử dụng `Date` để tính ngày mai từ ngày hiện tại và in ra dưới dạng `DD-MM-YYYY`.

---

#### **4. Tính khoảng cách giữa hai ngày**
Viết hàm nhận vào hai chuỗi ngày theo định dạng `YYYY-MM-DD`:
- `date1 = "2023-12-01"`, 
- `date2 = "2023-12-25"`.

Trả về số ngày giữa hai ngày.

---

#### **5. Kiểm tra ngày hợp lệ**
Viết hàm kiểm tra xem chuỗi `date = "2023-02-30"` có phải là ngày hợp lệ không.

---

#### **6. Tính tuổi từ ngày sinh**
Yêu cầu nhập ngày sinh `birthDate = "2000-05-15"`. Tính tuổi hiện tại của người đó.

---

#### **7. Cộng thêm ngày vào ngày hiện tại**
Viết hàm nhận vào số ngày `n = 30` và trả về ngày mới sau khi cộng `n` ngày vào ngày hiện tại.

---

#### **8. Kiểm tra năm nhuận**
Viết hàm kiểm tra xem năm `year = 2024` có phải là năm nhuận hay không.

---

#### **9. Chuyển đổi định dạng ngày**
Viết hàm chuyển đổi ngày `date = "2023-12-01"` sang định dạng `01/12/2023`.

---

#### **10. So sánh hai ngày**
Cho hai ngày:
- `date1 = "2023-12-01"`, 
- `date2 = "2023-11-30"`.

So sánh và in ra ngày nào sớm hơn.

---

#### **11. Ngày đầu tiên và cuối cùng của tháng**
Nhập ngày `date = "2023-12-15"`, trả về:
- Ngày đầu tiên: `01-12-2023`.
- Ngày cuối cùng: `31-12-2023`.

---

#### **12. Đếm số ngày trong tháng**
Cho tháng `month = 2` và năm `year = 2024`. Trả về số ngày trong tháng đó.

---

### **Bài Tập Về JSON**

#### **1. Chuyển Object sang JSON**
Cho object:
```javascript
const person = { name: "Alice", age: 25, city: "New York" };
```
Sử dụng `JSON.stringify` để chuyển đổi object này sang chuỗi JSON.

---

#### **2. Chuyển JSON sang Object**

Cho chuỗi JSON:
```json
'{"name":"Bob","age":30,"city":"Los Angeles"}'
```

- Thêm vào một thuộc tính mới: `email='bob@gmail.com`
- In ra kết quả

---

#### **3. Lọc dữ liệu từ JSON**
Cho mảng JSON:
```json
[
  { "name": "Alice", "age": 24 },
  { "name": "Bob", "age": 19 },
  { "name": "Charlie", "age": 21 }
]
```
Viết chương trình lọc ra các đối tượng có `age >= 21`. 

