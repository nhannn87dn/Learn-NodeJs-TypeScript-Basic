# Buổi 3: Dữ liệu kiểu số và các loại toán tử


## 💛 **Dữ liệu kiểu số trong TypeScript**  

### 🔥 Số nguyên và số thực

Trong TypeScript, cả số nguyên và số thực đều được đại diện bởi kiểu number. Không có kiểu riêng biệt cho số nguyên.

```ts
let integer: number = 6;
let float: number = 6.02;
```
### 🔥 NaN và Infinity

`NaN` (Not a Number) là một giá trị đặc biệt được sử dụng để biểu diễn một kết quả không hợp lệ hoặc không xác định trong toán học. `Infinity` là một giá trị đặc biệt biểu diễn vô cực.

```ts
let result = 0 / 0; // NaN
let infiniteNumber = 1 / 0; // Infinity
```

### 🔥 BigInt

`BigInt` là một kiểu dữ liệu cho phép lưu trữ số nguyên lớn hơn giới hạn của kiểu `number`.

```ts
let bigNumber: bigint = 1234567890123456789012345678901234567890n;
```

---

## 💛 **Toán tử số học**  

### 🔥 **Toán tử số học là gì?**

Toán tử số học (Arithmetic Operators) trong JavaScript/TypeScript được sử dụng để thực hiện các phép toán cơ bản trên các giá trị số, như cộng, trừ, nhân, chia, và nhiều phép toán khác.

---

### 🔥**Danh sách các toán tử số học**

1. **Cộng (`+`)**
   - **Mô tả:** Cộng hai giá trị với nhau.
   - **Ví dụ:**
     ```javascript
     console.log(5 + 3); // Output: 8
     ```

2. **Trừ (`-`)**
   - **Mô tả:** Trừ giá trị thứ hai khỏi giá trị thứ nhất.
   - **Ví dụ:**
     ```javascript
     console.log(10 - 4); // Output: 6
     ```

3. **Nhân (`*`)**
   - **Mô tả:** Nhân hai giá trị.
   - **Ví dụ:**
     ```javascript
     console.log(6 * 7); // Output: 42
     ```

4. **Chia (`/`)**
   - **Mô tả:** Chia giá trị thứ nhất cho giá trị thứ hai.
   - **Ví dụ:**
     ```javascript
     console.log(20 / 4); // Output: 5
     ```

5. **Lấy phần dư (`%`)**
   - **Mô tả:** Trả về phần dư khi chia hai số.
   - **Ví dụ:**
     ```javascript
     console.log(10 % 3); // Output: 1
     ```

6. **Lũy thừa (`**`)**
   - **Mô tả:** Tính lũy thừa của một số.
   - **Ví dụ:**
     ```javascript
     console.log(2 ** 3); // Output: 8
     ```

7. **Âm một số (`-`)**
   - **Mô tả:** Biến một số thành giá trị âm.
   - **Ví dụ:**
     ```javascript
     console.log(-5); // Output: -5
     ```

---

### 🔥 **Toán tử tăng và giảm**

1. **Tăng (`++`)**
   - **Mô tả:** Tăng giá trị của biến lên 1.
   - **Cú pháp:**
     - **Tiền tố (`++x`)**: Tăng trước, rồi trả về giá trị sau khi tăng.
     - **Hậu tố (`x++`)**: Trả về giá trị trước khi tăng, rồi mới tăng.
   - **Ví dụ:**
     ```javascript
     let x = 5;
     console.log(++x); // Output: 6 (Tăng trước)
     console.log(x++); // Output: 6 (Trả về giá trị trước khi tăng)
     console.log(x);   // Output: 7
     ```

2. **Giảm (`--`)**
   - **Mô tả:** Giảm giá trị của biến đi 1.
   - **Cú pháp:**
     - **Tiền tố (`--x`)**: Giảm trước, rồi trả về giá trị sau khi giảm.
     - **Hậu tố (`x--`)**: Trả về giá trị trước khi giảm, rồi mới giảm.
   - **Ví dụ:**
     ```javascript
     let y = 5;
     console.log(--y); // Output: 4 (Giảm trước)
     console.log(y--); // Output: 4 (Trả về giá trị trước khi giảm)
     console.log(y);   // Output: 3
     ```

---

### 🔥 **Một số lưu ý khi sử dụng toán tử số học**

1. **Phép chia cho 0**
   - Trong JavaScript, chia cho `0` không gây lỗi nhưng sẽ trả về `Infinity` hoặc `-Infinity`.
   - **Ví dụ:**
     ```javascript
     console.log(5 / 0);  // Output: Infinity
     console.log(-5 / 0); // Output: -Infinity
     ```

2. **Sử dụng với chuỗi**
   - Khi sử dụng toán tử `+` với chuỗi, nó sẽ thực hiện phép **nối chuỗi** thay vì cộng số.
   - **Ví dụ:**
     ```javascript
     console.log("5" + 3); // Output: "53" (Nối chuỗi)
     console.log(5 + "3"); // Output: "53" (Nối chuỗi)
     console.log(5 - "3"); // Output: 2 (Ép chuỗi thành số)
     ```

3. **Số âm trong phép lũy thừa**
   - Nếu số âm được nâng lên lũy thừa, phải đặt trong ngoặc.
   - **Ví dụ:**
     ```javascript
     console.log((-2) ** 3); // Output: -8
     console.log(-2 ** 3);   // Lỗi cú pháp
     ```

---

### **Ứng dụng của toán tử số học**

1. **Tính chu vi và diện tích hình chữ nhật:**
   ```javascript
   const length = 10;
   const width = 5;
   const perimeter = 2 * (length + width);
   const area = length * width;

   console.log("Chu vi:", perimeter); // Output: Chu vi: 30
   console.log("Diện tích:", area);  // Output: Diện tích: 50
   ```

2. **Kiểm tra số chẵn hay lẻ:**
   ```javascript
   const number = 7;
   if (number % 2 === 0) {
     console.log("Số chẵn");
   } else {
     console.log("Số lẻ");
   }
   ```

3. **Tính số mũ:**
   ```javascript
   const base = 2;
   const exponent = 4;
   console.log(base ** exponent); // Output: 16
   ```


---

## 💛 **Toán tử so sánh**  

### 🔥 Khái niệm

Toán tử so sánh (Comparison Operators) trong JavaScript được sử dụng để **so sánh hai giá trị** và trả về một giá trị Boolean (`true` hoặc `false`) tùy thuộc vào kết quả của phép so sánh. 


### 🔥 **Danh sách các toán tử so sánh**

1. **So sánh bằng (`==`)**
   - **Mô tả:** So sánh giá trị của hai biến, **không kiểm tra kiểu dữ liệu**.
   - **Ví dụ:**
     ```javascript
     console.log(5 == "5");  // Output: true (Không kiểm tra kiểu dữ liệu)
     console.log(5 == 5);    // Output: true
     ```

2. **So sánh không bằng (`!=`)**
   - **Mô tả:** Kiểm tra hai giá trị **không bằng nhau**, **không kiểm tra kiểu dữ liệu**.
   - **Ví dụ:**
     ```javascript
     console.log(5 != "5");  // Output: false (Vì giá trị giống nhau)
     console.log(5 != 6);    // Output: true
     ```

3. **So sánh bằng chặt (`===`)**
   - **Mô tả:** So sánh cả giá trị **và kiểu dữ liệu** của hai biến.
   - **Ví dụ:**
     ```javascript
     console.log(5 === "5"); // Output: false (Kiểu dữ liệu khác nhau)
     console.log(5 === 5);   // Output: true
     ```

4. **So sánh không bằng chặt (`!==`)**
   - **Mô tả:** Kiểm tra hai giá trị **không bằng nhau** hoặc kiểu dữ liệu **khác nhau**.
   - **Ví dụ:**
     ```javascript
     console.log(5 !== "5"); // Output: true (Kiểu dữ liệu khác nhau)
     console.log(5 !== 5);   // Output: false
     ```

5. **Lớn hơn (`>`)**
   - **Mô tả:** Trả về `true` nếu giá trị bên trái **lớn hơn** giá trị bên phải.
   - **Ví dụ:**
     ```javascript
     console.log(10 > 5); // Output: true
     console.log(5 > 10); // Output: false
     ```

6. **Nhỏ hơn (`<`)**
   - **Mô tả:** Trả về `true` nếu giá trị bên trái **nhỏ hơn** giá trị bên phải.
   - **Ví dụ:**
     ```javascript
     console.log(3 < 8); // Output: true
     console.log(8 < 3); // Output: false
     ```

7. **Lớn hơn hoặc bằng (`>=`)**
   - **Mô tả:** Trả về `true` nếu giá trị bên trái **lớn hơn hoặc bằng** giá trị bên phải.
   - **Ví dụ:**
     ```javascript
     console.log(10 >= 10); // Output: true
     console.log(9 >= 10);  // Output: false
     ```

8. **Nhỏ hơn hoặc bằng (`<=`)**
   - **Mô tả:** Trả về `true` nếu giá trị bên trái **nhỏ hơn hoặc bằng** giá trị bên phải.
   - **Ví dụ:**
     ```javascript
     console.log(5 <= 10); // Output: true
     console.log(11 <= 10); // Output: false
     ```


### 🔥 **Một số lưu ý khi sử dụng toán tử so sánh**

1. **So sánh giá trị với kiểu dữ liệu khác nhau:**
   - **Toán tử `==`**:
     - Chuyển đổi kiểu dữ liệu trước khi so sánh.
     - **Ví dụ:**
       ```javascript
       console.log(5 == "5");  // Output: true
       console.log(true == 1); // Output: true
       ```
   - **Toán tử `===`**:
     - Không chuyển đổi kiểu dữ liệu.
     - **Ví dụ:**
       ```javascript
       console.log(5 === "5"); // Output: false
       console.log(true === 1); // Output: false
       ```

2. **So sánh với `NaN`:**
   - `NaN` không bao giờ bằng chính nó.
   - **Ví dụ:**
     ```javascript
     console.log(NaN == NaN);  // Output: false
     console.log(NaN === NaN); // Output: false
     ```

3. **So sánh chuỗi:**
   - Chuỗi được so sánh theo thứ tự bảng mã Unicode.
   - **Ví dụ:**
     ```javascript
     console.log("a" > "b"); // Output: false
     console.log("apple" > "app"); // Output: true
     ```

---

### 🔥 **Ứng dụng thực tế của toán tử so sánh**

1. **Kiểm tra điều kiện:**
   - Kiểm tra người dùng đã đủ tuổi để đăng ký:
     ```javascript
     const age = 20;
     if (age >= 18) {
       console.log("Bạn đủ tuổi để đăng ký.");
     } else {
       console.log("Bạn chưa đủ tuổi.");
     }
     ```

2. **So sánh dữ liệu nhập vào:**
   - Xác minh mật khẩu:
     ```javascript
     const inputPassword = "12345";
     const savedPassword = "12345";
     if (inputPassword === savedPassword) {
       console.log("Mật khẩu đúng!");
     } else {
       console.log("Mật khẩu sai!");
     }
     ```

3. **Sắp xếp dữ liệu:**
   - Sử dụng toán tử so sánh trong thuật toán sắp xếp:
     ```javascript
     const numbers = [5, 3, 8, 1];
     numbers.sort((a, b) => a - b);
     console.log(numbers); // Output: [1, 3, 5, 8]
     ```

---

## 💛 **Toán tử logic**  


### 🔥 **Toán tử logic trong JavaScript là gì?**

Toán tử logic (logical operators) trong JavaScript được sử dụng để thực hiện các phép toán logic trên các giá trị Boolean (true/false). Chúng giúp kiểm tra các điều kiện và đưa ra kết quả logic (true hoặc false).

---

### 🔥 **Các loại toán tử logic phổ biến**

1. **Toán tử AND (`&&`)**
   - **Mô tả:** Trả về `true` nếu **tất cả** các biểu thức đều là `true`. 
   - **Cách hoạt động:**
     - Nếu gặp giá trị `false`, toán tử trả về giá trị đó và dừng kiểm tra các giá trị còn lại.
     - Nếu không gặp `false`, toán tử trả về giá trị cuối cùng.
   - **Cú pháp:** 
     ```javascript
     expr1 && expr2
     ```
   - **Ví dụ:**
     ```javascript
     console.log(true && true);   // Output: true
     console.log(true && false);  // Output: false
     console.log(false && false); // Output: false
     console.log(5 > 3 && 10 > 2); // Output: true
     ```

2. **Toán tử OR (`||`)**
   - **Mô tả:** Trả về `true` nếu **ít nhất một** biểu thức là `true`. 
   - **Cách hoạt động:**
     - Nếu gặp giá trị `true`, toán tử trả về giá trị đó và dừng kiểm tra các giá trị còn lại.
     - Nếu không gặp `true`, toán tử trả về giá trị cuối cùng.
   - **Cú pháp:** 
     ```javascript
     expr1 || expr2
     ```
   - **Ví dụ:**
     ```javascript
     console.log(true || false);  // Output: true
     console.log(false || false); // Output: false
     console.log(5 > 3 || 10 < 2); // Output: true
     ```

3. **Toán tử NOT (`!`)**
   - **Mô tả:** Đảo ngược giá trị logic. Nếu là `true` thì chuyển thành `false`, ngược lại.
   - **Cú pháp:** 
     ```javascript
     !expr
     ```
   - **Ví dụ:**
     ```javascript
     console.log(!true);  // Output: false
     console.log(!false); // Output: true
     console.log(!(5 > 3)); // Output: false
     ```

---

### 🔥 **Đặc điểm nâng cao**

#### **Short-Circuit Evaluation (Đánh giá ngắn mạch)**
- **Toán tử AND (`&&`)**:
  - Dừng kiểm tra khi gặp giá trị `false`.
  ```javascript
  console.log(false && console.log("Không được in")); // Không in gì, dừng tại `false`
  ```
- **Toán tử OR (`||`)**:
  - Dừng kiểm tra khi gặp giá trị `true`.
  ```javascript
  console.log(true || console.log("Không được in")); // Không in gì, dừng tại `true`
  ```

#### **Kết hợp nhiều toán tử logic**

- Khi kết hợp nhiều toán tử, **độ ưu tiên** như sau:
  1. `!` (NOT) thực hiện trước.
  2. `&&` (AND) thực hiện sau.
  3. `||` (OR) thực hiện cuối cùng.
- **Ví dụ:**
  ```javascript
  console.log(true || false && !false); // Output: true
  ```

---

### 🔥 **Ứng dụng thực tế của toán tử logic**

1. **Kiểm tra nhiều điều kiện:**

   ```javascript
   const age = 20;
   const hasID = true;
   console.log(age >= 18 && hasID); // Output: true
   ```

2. **Gán giá trị mặc định (Toán tử OR):**
   ```javascript
   const username = null;
   const displayName = username || "Guest";
   console.log(displayName); // Output: "Guest"
   ```

3. **Đảo ngược điều kiện (Toán tử NOT):**
   ```javascript
   const isLoggedIn = false;
   if (!isLoggedIn) {
     console.log("Vui lòng đăng nhập!"); // Output: "Vui lòng đăng nhập!"
   }
   ```

4. **Kiểm tra chuỗi hợp lệ:**
   ```javascript
   const str = "Hello";
   if (str && str.length > 0) {
     console.log("Chuỗi hợp lệ!"); // Output: "Chuỗi hợp lệ!"
   }
   ```

---


## 💛**Các phương thức xử lý số**


### 🔥 **Các phương thức xử lý số**

JavaScript cung cấp nhiều phương thức xử lý số để thao tác và làm việc với dữ liệu kiểu số. Dưới đây là danh sách các phương thức phổ biến từ lớp `Number` và đối tượng `Math`.

---

### 🔥 **1. Phương thức từ đối tượng `Number`**

#### **1.1 `Number.parseInt()`**
- **Mô tả:** Chuyển đổi chuỗi thành số nguyên.
- **Cú pháp:** 
  ```javascript
  Number.parseInt(string, radix);
  ```
- **Ví dụ:**
  ```javascript
  console.log(Number.parseInt("123"));    // Output: 123
  console.log(Number.parseInt("123.45")); // Output: 123
  console.log(Number.parseInt("abc"));    // Output: NaN
  ```

#### **1.2 `Number.parseFloat()`**
- **Mô tả:** Chuyển đổi chuỗi thành số thập phân (float).
- **Ví dụ:**
  ```javascript
  console.log(Number.parseFloat("123.45")); // Output: 123.45
  console.log(Number.parseFloat("123abc")); // Output: 123
  ```

#### **1.3 `Number.isFinite()`**
- **Mô tả:** Kiểm tra xem giá trị có phải là số hữu hạn.
- **Ví dụ:**
  ```javascript
  console.log(Number.isFinite(123));       // Output: true
  console.log(Number.isFinite(Infinity)); // Output: false
  ```

#### **1.4 `Number.isInteger()`**
- **Mô tả:** Kiểm tra xem giá trị có phải là số nguyên.
- **Ví dụ:**
  ```javascript
  console.log(Number.isInteger(123));    // Output: true
  console.log(Number.isInteger(123.45)); // Output: false
  ```

#### **1.5 `Number.isNaN()`**
- **Mô tả:** Kiểm tra xem giá trị có phải là `NaN` (Not-a-Number).
- **Ví dụ:**
  ```javascript
  console.log(Number.isNaN(NaN));        // Output: true
  console.log(Number.isNaN("123"));      // Output: false
  console.log(Number.isNaN(Number("x"))); // Output: true
  ```

#### **1.6 `Number.toFixed()`**
- **Mô tả:** Làm tròn số đến số chữ số thập phân cụ thể.
- **Ví dụ:**
  ```javascript
  let num = 123.456;
  console.log(num.toFixed(2)); // Output: "123.46"
  ```

#### **1.7 `Number.toString()`**
- **Mô tả:** Chuyển đổi số thành chuỗi.
- **Ví dụ:**
  ```javascript
  let num = 123;
  console.log(num.toString()); // Output: "123"
  ```

#### **1.8 `Number.valueOf()`**
- **Mô tả:** Trả về giá trị nguyên thủy của đối tượng số.
- **Ví dụ:**
  ```javascript
  let num = new Number(123);
  console.log(num.valueOf()); // Output: 123
  ```

---

### 🔥 **2. Phương thức từ đối tượng `Math`**

#### **2.1 `Math.abs()`**
- **Mô tả:** Trả về giá trị tuyệt đối.
- **Ví dụ:**
  ```javascript
  console.log(Math.abs(-5)); // Output: 5
  ```

#### **2.2 `Math.ceil()`**
- **Mô tả:** Làm tròn lên số nguyên gần nhất.
- **Ví dụ:**
  ```javascript
  console.log(Math.ceil(4.2)); // Output: 5
  ```

#### **2.3 `Math.floor()`**
- **Mô tả:** Làm tròn xuống số nguyên gần nhất.
- **Ví dụ:**
  ```javascript
  console.log(Math.floor(4.8)); // Output: 4
  ```

#### **2.4 `Math.round()`**
- **Mô tả:** Làm tròn số đến số nguyên gần nhất.
- **Ví dụ:**
  ```javascript
  console.log(Math.round(4.5)); // Output: 5
  console.log(Math.round(4.4)); // Output: 4
  ```

#### **2.5 `Math.max()` và `Math.min()`**
- **Mô tả:** Tìm số lớn nhất (`Math.max`) hoặc nhỏ nhất (`Math.min`) trong một danh sách.
- **Ví dụ:**
  ```javascript
  console.log(Math.max(1, 5, 3, 9)); // Output: 9
  console.log(Math.min(1, 5, 3, 9)); // Output: 1
  ```

#### **2.6 `Math.pow()`**
- **Mô tả:** Tính lũy thừa.
- **Ví dụ:**
  ```javascript
  console.log(Math.pow(2, 3)); // Output: 8
  ```

#### **2.7 `Math.sqrt()`**
- **Mô tả:** Tính căn bậc hai.
- **Ví dụ:**
  ```javascript
  console.log(Math.sqrt(16)); // Output: 4
  ```

#### **2.8 `Math.random()`**
- **Mô tả:** Trả về số ngẫu nhiên trong khoảng `[0, 1)`.
- **Ví dụ:**
  ```javascript
  console.log(Math.random()); // Output: Một số ngẫu nhiên, ví dụ: 0.245
  ```

#### **2.9 `Math.trunc()`**
- **Mô tả:** Bỏ phần thập phân của số (chỉ giữ phần nguyên).
- **Ví dụ:**
  ```javascript
  console.log(Math.trunc(4.9)); // Output: 4
  console.log(Math.trunc(-4.9)); // Output: -4
  ```
---

### 🔥 **3. Một số ví dụ ứng dụng thực tế**

#### **Tính số ngẫu nhiên trong khoảng [a, b]:**
```javascript
function randomInRange(a, b) {
  return Math.floor(Math.random() * (b - a + 1)) + a;
}
console.log(randomInRange(1, 10)); // Output: Một số ngẫu nhiên từ 1 đến 10
```

#### **Làm tròn số đến n chữ số thập phân:**
```javascript
function roundToDecimals(num, decimals) {
  return Number(num.toFixed(decimals));
}
console.log(roundToDecimals(1.234567, 3)); // Output: 1.235
```

#### **Kiểm tra số nguyên:**
```javascript
let num = 15.5;
console.log(Number.isInteger(num)); // Output: false
```

#### **Tìm số lớn nhất trong một mảng:**
```javascript
const numbers = [5, 8, 12, 3, 7];
console.log(Math.max(...numbers)); // Output: 12
```

