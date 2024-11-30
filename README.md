# Node.js cơ bản với TypeScript

## Buổi 1: Giới thiệu và cài đặt môi trường

**Mục tiêu:** Làm quen với Node.js và TypeScript


  1. Node.js là gì? Tại sao dùng Node.js?
  2. Giới thiệu TypeScript:
     - TypeScript vs JavaScript.
     - Lợi ích của TypeScript.
  3. Cài đặt môi trường:
     - Cài đặt Node.js và npm.
     - Cài đặt TypeScript (sử dụng `npm install -g typescript`).
     - Giới thiệu `tsconfig.json` và tạo một project TypeScript cơ bản.
  4. Chạy file TypeScript với `tsc` và `node`.


---


## Buổi 2: Khai báo biến và kiểu dữ liệu

**Mục tiêu:** Làm quen với cú pháp khai báo biến và kiểu dữ liệu của biến.

  1. Khai báo biến: `var`, `let`, `const`.
  2. Các kiểu dữ liệu cơ bản:
     - `string`, `number`, `boolean`.
     - `any`, `null`, `undefined`.
  3. Khai báo kiểu tường minh và sử dụng `type inference`.
  4. Sử dụng `enum` trong TypeScript.
  5. Chuỗi và các phương thức xử lý Chuỗi.



## Buổi 3: Dữ liệu kiểu số và các loại toán tử

**Mục tiêu:** Làm quen với dữ liệu số và các loại toán tử cơ bản trong TypeScript.

1. **Dữ liệu kiểu số trong TypeScript**  
   - Số nguyên, số thực, và cách khai báo số (`number`).  
   - Khái niệm `NaN`, `Infinity`.  
   - Kiểu `BigInt` (khi nào dùng và cách sử dụng).  

2. **Toán tử số học**  
   - Các phép toán cơ bản: `+`, `-`, `*`, `/`, `%`, `**`.  
   - Tăng giảm giá trị: `++`, `--`.  
   - Các trường hợp đặc biệt: chia 0, modulo âm.  

3. **Toán tử so sánh**  
   - So sánh giá trị: `==`, `!=`.  
   - So sánh nghiêm ngặt: `===`, `!==`.  
   - Lớn hơn, nhỏ hơn: `>`, `<`, `>=`, `<=`.  

4. **Toán tử logic**  
   - AND (`&&`), OR (`||`), NOT (`!`).  
   - Kết hợp toán tử logic và toán tử so sánh trong điều kiện.  

---




## Buổi 4: Cấu trúc điều khiển

**Mục tiêu:** Hiểu và sử dụng các cấu trúc điều khiển rẽ nhánh để xử lý logic trong chương trình.  

1. **Giới thiệu cấu trúc điều khiển rẽ nhánh**  
   - Tầm quan trọng của điều kiện trong lập trình.  

2. **Cấu trúc `if`, `else if`, và `else`**  
   - Cách sử dụng cơ bản.  
   - Đặt điều kiện lồng nhau.  

3. **Cấu trúc `switch`**  
   - Khi nào nên dùng `switch`.  
   - So sánh hiệu quả giữa `switch` và `if-else`.  

4. **Toán tử điều kiện (ternary operator)**  
   - Cách viết điều kiện đơn giản hơn với `? :`.  

---

## Buổi 5: Mảng, Tuples và Vòng lặp

**Mục tiêu:** Hiểu cách làm việc với mảng và tuples, đồng thời sử dụng các vòng lặp để xử lý dữ liệu.


1. **Mảng trong TypeScript**  
   - Khai báo và khởi tạo mảng:  
     - Cú pháp `Array<T>` và `T[]`.  
   - Thao tác trên mảng:  
     - Thêm, sửa, xóa phần tử: `push`, `pop`, `splice`.  
   - Các phương thức quan trọng:  
     - Duyệt mảng: `forEach`.  
     - Biến đổi: `map`.  
     - Tìm kiếm và lọc: `find`, `filter`.  

2. **Tuples trong TypeScript**  
   - Định nghĩa và khai báo tuples.  
   - Sử dụng tuples để nhóm các giá trị khác kiểu.  
   - Thêm phần tử vào tuples với phương thức `push`.  

3. **Vòng lặp trong TypeScript**  
   - Các loại vòng lặp:  
     - `for`, `while`, `do...while`.  
     - Vòng lặp nâng cao: `for...of` và `for...in`.  
   - Sử dụng vòng lặp để duyệt mảng và tuples. 

---

## Buổi 6: Objects

**Mục tiêu:** Hiểu và sử dụng kiểu dữ liệu object trong TypeScript để quản lý và thao tác với dữ liệu phức tạp.  


1. **Khái niệm object trong TypeScript**  
   - Cách khai báo object:  
     - Sử dụng kiểu tường minh và kiểu suy diễn.  
     - Khai báo với `type` và `interface`.  
   - Thuộc tính bắt buộc và thuộc tính tùy chọn (`?`).  

2. **Truy cập và thao tác với object**  
   - Truy cập thuộc tính bằng dấu chấm (`.`) và ngoặc vuông (`[]`).  
   - Thêm, sửa, xóa thuộc tính của object.  

3. **Lồng ghép object và các kiểu dữ liệu khác**  
   - Object chứa mảng và ngược lại.  
   - Object lồng nhau và cách truy cập.  

4. **Duyệt qua object**  
   - Sử dụng vòng lặp `for...in` để duyệt qua các thuộc tính.  
   - Sử dụng `Object.keys`, `Object.values`, và `Object.entries` để thao tác.  

5. **Kiểu dữ liệu thời gian `Date`** 

6. **JSON trong TypeScript và Node.js**  
   - **JSON là gì?**: Định dạng, cấu trúc, và cách sử dụng.  
   - **Chuyển đổi giữa JSON và object:**  
     - `JSON.stringify` (chuyển object sang chuỗi JSON).  
     - `JSON.parse` (chuyển chuỗi JSON sang object).  
   - Đọc và ghi dữ liệu JSON vào file.  

---
## Buổi 7: Functions và Modules

**Mục tiêu:** Làm quen với cách định nghĩa và sử dụng hàm (functions) trong TypeScript, đồng thời tổ chức code hiệu quả hơn với modules.  


1. **Hàm (Functions) trong TypeScript**  
   - **Cách khai báo hàm:**  
     - Hàm không trả về (`void`).  
     - Hàm có kiểu trả về (`string`, `number`, `boolean`,...).  
   - **Tham số của hàm:**  
     - Tham số bắt buộc và tùy chọn (`?`).  
     - Giá trị mặc định cho tham số.  
     - Sử dụng toán tử `rest` để gom nhóm tham số.  
   - **Hàm nặc danh và hàm mũi tên (arrow functions).**  

2. **Sử dụng hàm trong TypeScript**  
   - Định nghĩa hàm tường minh với kiểu dữ liệu tham số và kiểu trả về.  
   - Hàm lồng nhau và đệ quy (recursion).  

3. **Modules trong Node.js và TypeScript**  
   - **Giới thiệu modules:** Tổ chức mã nguồn với các file riêng biệt.  
   - **Cách xuất và nhập module:**  
     - `export` và `import`.  
     - Default export và named export.  
   - Sử dụng thư viện có sẵn (built-in modules) trong Node.js:  
     - Ví dụ: `fs`, `path`.  


---

## Buổi 8: JSON và Error handling

**Mục tiêu:** Làm quen với cách làm việc với JSON trong TypeScript và Node.js, đồng thời xử lý lỗi hiệu quả trong ứng dụng.  

1. **Error Handling trong TypeScript**  
   - **Các loại lỗi phổ biến:**  
     - Lỗi cú pháp, lỗi runtime, lỗi logic.  
   - **Sử dụng `try...catch` và `finally`:**  
     - Phát hiện và xử lý lỗi trong runtime.  
   - **Tạo và ném lỗi (`throw`):**  
     - Cách tự định nghĩa lỗi.  
2. **Promise và Async/Await:**  
   - Xử lý bất đồng bộ.  
   - Xử lý lỗi trong các hàm bất đồng bộ.  
