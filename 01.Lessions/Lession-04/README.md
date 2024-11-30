# Buổi 4: Cấu trúc điều khiển


## 💛 **Giới thiệu cấu trúc điều khiển rẽ nhánh**  

### 🔥**Tầm quan trọng của điều kiện trong lập trình**
- Điều kiện là một trong những khái niệm cơ bản và quan trọng trong lập trình, cho phép chương trình quyết định hành động tiếp theo dựa trên các giá trị đầu vào hoặc các điều kiện cụ thể.
- Các cấu trúc điều kiện giúp lập trình viên điều khiển luồng thực thi của chương trình, từ đó xây dựng logic phức tạp cho các ứng dụng.
- Điều kiện trong lập trình giúp:
  - **Quyết định hành động:** Dựa trên giá trị của biến hoặc biểu thức, chương trình có thể thực hiện các hành động khác nhau.
  - **Xử lý các tình huống khác nhau:** Giúp xử lý các trường hợp ngoại lệ hoặc các tình huống bất ngờ.
  - **Tăng tính tương tác:** Tạo ra các chương trình có thể phản hồi và tương tác với người dùng, hoặc các yếu tố bên ngoài khác.

---

## 💛 **Cấu trúc `if`, `else if`, và `else`**

### 🔥 **Cách sử dụng cơ bản**
Cấu trúc `if`, `else if`, và `else` là cách phổ biến để kiểm tra các điều kiện và thực hiện các hành động tùy thuộc vào kết quả của điều kiện đó.

- **`if`:** Kiểm tra một điều kiện. Nếu điều kiện đúng, sẽ thực thi mã trong khối `if`.
- **`else if`:** Sử dụng để kiểm tra thêm các điều kiện khác nếu điều kiện trước đó không đúng.
- **`else`:** Thực thi mã khi tất cả các điều kiện trước đó không đúng.

Dưới đây là cách sử dụng cơ bản của các cấu trúc điều kiện `if`, `else if`, và `else` trong JavaScript, cùng với giải thích chi tiết và ví dụ cụ thể cho từng loại.

---

#### **1. Cấu trúc `if`**

Cấu trúc `if` dùng để kiểm tra một điều kiện, và nếu điều kiện đó đúng (true), thì mã trong khối `if` sẽ được thực thi.

**Cú pháp:**
```javascript
if (condition) {
    // Mã sẽ thực thi nếu điều kiện đúng (true)
}
```

**Khi nào thì sử dụng `if` đơn:**

1. **Chỉ cần kiểm tra một điều kiện duy nhất:**
   - Khi bạn chỉ muốn thực hiện hành động nếu điều kiện duy nhất là đúng và không cần xử lý thêm các trường hợp khác.

2. **Không cần thực hiện hành động gì khi điều kiện sai:**
   - Nếu bạn chỉ muốn thực thi một đoạn mã khi điều kiện thỏa mãn và không cần có hành động nào khi điều kiện sai, không cần phải sử dụng `else` hoặc `else if`.

3. **Khi không cần xử lý các tình huống thay thế:**
   - Nếu bạn không quan tâm đến các tình huống khi điều kiện không thỏa mãn, bạn có thể chỉ dùng `if` mà không cần phải xử lý thêm điều kiện sai.


**Ví dụ:**
```javascript
let age = 18;

if (age >= 18) {
    console.log("Bạn đủ tuổi trưởng thành.");
}
```

**Giải thích:**
- Ở đây, điều kiện `age >= 18` sẽ được kiểm tra. Nếu đúng, chương trình sẽ in ra "Bạn đủ tuổi trưởng thành."
- Nếu `age` nhỏ hơn 18, mã trong khối `if` sẽ không thực thi, và không có gì được in ra.



Ví dụ: Giả sử bạn chỉ muốn in ra một thông báo khi một số là số chẵn, không cần thực hiện hành động nào nếu số đó là số lẻ.

   ```javascript
   let number = 4;

   if (number % 2 === 0) {
       console.log("Số chẵn");
   }
   ```

   **Giải thích:**
   - Ở đây, chỉ khi số là số chẵn (`number % 2 === 0`), chương trình mới in ra "Số chẵn".
   - Nếu số là lẻ, không có hành động nào được thực thi.

---

#### **2. Cấu trúc `else if`**

Cấu trúc `else if` được sử dụng khi bạn muốn kiểm tra thêm nhiều điều kiện khác sau khi điều kiện đầu tiên trong `if` không thỏa mãn. Bạn có thể có nhiều `else if` trong một câu lệnh.

**Cú pháp:**
```javascript
if (condition1) {
    // Mã thực thi nếu điều kiện1 đúng
} else if (condition2) {
    // Mã thực thi nếu điều kiện1 sai và điều kiện2 đúng
} else if (condition3) {
    // Mã thực thi nếu điều kiện1 và điều kiện2 sai và điều kiện3 đúng
}
```


**Khi nào thì sử dụng `else if`:**
- Khi có **nhiều điều kiện** cần kiểm tra, và mỗi điều kiện có hành động riêng.
- Khi muốn **tổ chức các điều kiện** theo thứ tự ưu tiên hoặc thứ tự logic.
- Khi bạn không muốn thực thi hành động mặc định cho tất cả các trường hợp không thỏa mãn điều kiện. 

**Ví dụ:**
```javascript
let score = 85;

if (score >= 90) {
    console.log("Điểm xuất sắc");
} else if (score >= 75) {
    console.log("Điểm khá");
} else if (score >= 50) {
    console.log("Điểm trung bình");
} else {
    console.log("Điểm yếu");
}
```

**Giải thích:**
- Nếu `score >= 90`, chương trình sẽ in ra "Điểm xuất sắc."
- Nếu không, nhưng `score >= 75`, chương trình sẽ in ra "Điểm khá."
- Nếu cả hai điều kiện trên đều không thỏa mãn, nhưng `score >= 50`, chương trình sẽ in "Điểm trung bình."
- Nếu không có điều kiện nào thỏa mãn, `else` sẽ in "Điểm yếu."

---

#### **3. Cấu trúc `else`**

Cấu trúc `else` được sử dụng để thực thi một hành động khi tất cả các điều kiện trước đó đều không đúng. Đây là phần mặc định sẽ chạy nếu các điều kiện `if` và `else if` không thỏa mãn.

**Cú pháp:**
```javascript
if (condition1) {
    // Mã thực thi nếu điều kiện1 đúng
} else {
    // Mã thực thi nếu điều kiện1 sai
}
```

**Khi nào thì cần dùng Cấu trúc `else`**

Cấu trúc `else` cần sử dụng khi bạn muốn thực hiện một hành động **mặc định** khi tất cả các điều kiện trước đó không thỏa mãn (tức là khi điều kiện trong `if` hoặc `else if` không đúng). Bạn sẽ sử dụng `else` khi có hai khả năng:

1. **Khi bạn cần thực hiện hành động trong trường hợp điều kiện sai:**
   - Nếu không có hành động nào được thực hiện khi điều kiện sai, bạn sử dụng `else` để đảm bảo rằng một hành động khác sẽ được thực thi.

2. **Khi chỉ có hai lựa chọn cần xử lý:**
   - Khi bạn muốn xử lý một hành động nếu điều kiện đúng, và một hành động khác nếu điều kiện sai. Trong trường hợp này, `else` là lựa chọn phù hợp để xử lý trường hợp ngược lại.

3. **Khi bạn muốn thay thế các điều kiện bổ sung bằng một hành động mặc định:**
   - Nếu không cần kiểm tra thêm nhiều điều kiện khác (không cần `else if`), bạn có thể sử dụng `else` để thực hiện hành động mặc định khi tất cả các điều kiện trước đó không thỏa mãn.


**Ví dụ:**
```javascript
let number = 7;

if (number % 2 === 0) {
    console.log("Số chẵn");
} else {
    console.log("Số lẻ");
}
```

**Giải thích:**
- Nếu `number` chia hết cho 2 (`number % 2 === 0`), chương trình sẽ in "Số chẵn."
- Nếu điều kiện trên không đúng (tức là số lẻ), mã trong phần `else` sẽ thực thi và in "Số lẻ."

---

#### **Kết hợp `if`, `else if`, và `else`**

Cấu trúc **kết hợp `if`, `else if`, và `else`** được sử dụng khi bạn cần kiểm tra **nhiều điều kiện khác nhau** và thực hiện các hành động **khác nhau** cho từng điều kiện đó. Bạn kết hợp các phần này khi bạn cần xử lý nhiều tình huống và chỉ muốn thực thi một hành động cho một trong các điều kiện, và thực hiện một hành động mặc định nếu tất cả các điều kiện đều không thỏa mãn.


1. **Khi có nhiều điều kiện cần kiểm tra:**
   - Nếu bạn có nhiều điều kiện cần phải kiểm tra và mỗi điều kiện có hành động khác nhau, bạn sẽ sử dụng `if` cho điều kiện đầu tiên, rồi dùng `else if` để kiểm tra thêm các điều kiện tiếp theo, và cuối cùng dùng `else` để xử lý trường hợp mặc định khi tất cả các điều kiện đều không thỏa mãn.

2. **Khi các điều kiện có tính chất loại trừ lẫn nhau:**
   - Các điều kiện có thể loại trừ nhau, ví dụ: nếu điều kiện đầu tiên đúng thì không cần kiểm tra các điều kiện tiếp theo, và ngược lại. Cấu trúc này giúp bạn tổ chức mã theo cách hợp lý hơn khi các điều kiện không thể cùng đúng một lúc.

3. **Khi bạn cần hành động mặc định khi không có điều kiện nào thỏa mãn:**
   - `else` sẽ giúp bạn xử lý các trường hợp khi tất cả các điều kiện `if` và `else if` đều không thỏa mãn.

### **Ví dụ về kết hợp `if`, `else if`, và `else`:**
```javascript
let score = 85;

if (score >= 90) {
    console.log("Điểm xuất sắc");
} else if (score >= 75) {
    console.log("Điểm khá");
} else if (score >= 50) {
    console.log("Điểm trung bình");
} else {
    console.log("Điểm yếu");
}
```

### **Giải thích:**
- **`if (score >= 90)`**: Kiểm tra nếu điểm >= 90, in ra "Điểm xuất sắc".
- **`else if (score >= 75)`**: Nếu không thỏa mãn điều kiện trên, kiểm tra nếu điểm >= 75, in ra "Điểm khá".
- **`else if (score >= 50)`**: Nếu không thỏa mãn các điều kiện trên, kiểm tra nếu điểm >= 50, in ra "Điểm trung bình".
- **`else`**: Nếu không thỏa mãn tất cả các điều kiện trên (tức là điểm < 50), in ra "Điểm yếu".


### **Ví dụ về kết hợp `if`, `else if`, và `else`:**

```javascript
let temperature = 25;

if (temperature > 30) {
    console.log("Nóng quá!");
} else if (temperature >= 20 && temperature <= 30) {
    console.log("Thời tiết dễ chịu.");
} else if (temperature >= 10 && temperature < 20) {
    console.log("Khá lạnh.");
} else {
    console.log("Rất lạnh.");
}
```

**Giải thích:**
- Nếu nhiệt độ trên 30, in ra "Nóng quá!"
- Nếu nhiệt độ trong khoảng từ 20 đến 30, in ra "Thời tiết dễ chịu."
- Nếu nhiệt độ từ 10 đến 20, in ra "Khá lạnh."
- Nếu tất cả các điều kiện trên đều sai (tức là nhiệt độ dưới 10), phần `else` sẽ in ra "Rất lạnh."

---


### 🔥 **Đặt điều kiện lồng nhau**
Bạn có thể lồng các cấu trúc `if` bên trong các cấu trúc `if`, `else if`, và `else` để kiểm tra nhiều điều kiện phức tạp hơn.

**Ví dụ lồng điều kiện:**
```javascript
let age = 20;
let hasLicense = true;

if (age >= 18) {
    if (hasLicense) {
        console.log("Bạn đủ tuổi và có giấy phép lái xe.");
    } else {
        console.log("Bạn đủ tuổi nhưng không có giấy phép lái xe.");
    }
} else {
    console.log("Bạn chưa đủ tuổi để lái xe.");
}
```

---

## 💛 **Cấu trúc `switch`**

### 🔥 **Khi nào nên dùng `switch`**
Cấu trúc `switch` là một cách kiểm tra nhiều điều kiện trong JavaScript. Nó thường được sử dụng khi bạn có nhiều điều kiện mà bạn cần kiểm tra một cách rõ ràng và dễ đọc, đặc biệt khi các điều kiện này là **giá trị rời rạc**.

- **Ưu điểm:** Dễ đọc và dễ bảo trì khi có nhiều lựa chọn.
- **Nhược điểm:** Chỉ hoạt động tốt khi bạn so sánh các giá trị cụ thể, không thể sử dụng cho các điều kiện phức tạp hoặc điều kiện dạng biểu thức.

**Cú pháp cơ bản:**
```javascript
switch (expression) {
    case value1:
        // Đoạn mã sẽ thực thi nếu expression === value1
        break;
    case value2:
        // Đoạn mã sẽ thực thi nếu expression === value2
        break;
    default:
        // Đoạn mã sẽ thực thi nếu không có case nào khớp
}
```

**Ví dụ:**
```javascript
let day = 3;

switch (day) {
    case 1:
        console.log("Thứ 2");
        break;
    case 2:
        console.log("Thứ 3");
        break;
    case 3:
        console.log("Thứ 4");
        break;
    default:
        console.log("Ngày không hợp lệ");
}
```

### 🔥 **So sánh hiệu quả giữa `switch` và `if-else`**
- **Switch:** Dễ đọc và dễ duy trì khi bạn cần so sánh nhiều giá trị của một biến. Thích hợp cho các tình huống với số lượng lựa chọn cố định.
- **If-else:** Linh hoạt hơn và có thể sử dụng để kiểm tra các điều kiện phức tạp, chẳng hạn như so sánh các biểu thức, kết hợp các toán tử logic, v.v.

**Ví dụ so sánh:**
- **Sử dụng `switch`:**
```javascript
let color = "red";

switch (color) {
    case "red":
        console.log("Màu đỏ");
        break;
    case "blue":
        console.log("Màu xanh");
        break;
    default:
        console.log("Màu khác");
}
```

- **Sử dụng `if-else`:**
```javascript
let color = "red";

if (color === "red") {
    console.log("Màu đỏ");
} else if (color === "blue") {
    console.log("Màu xanh");
} else {
    console.log("Màu khác");
}
```

---

## 💛 **Toán tử điều kiện (ternary operator)**

### 🔥 **Cách viết điều kiện đơn giản hơn với `? :`**
Toán tử điều kiện (ternary operator) là một cách viết ngắn gọn cho cấu trúc `if-else`. Cú pháp của nó là:

```javascript
condition ? expr1 : expr2;
```

- Nếu `condition` là `true`, thì `expr1` sẽ được thực thi.
- Nếu `condition` là `false`, thì `expr2` sẽ được thực thi.

**Ví dụ:**
```javascript
let age = 20;
let message = age >= 18 ? "Bạn đủ tuổi trưởng thành." : "Bạn chưa đủ tuổi trưởng thành.";
console.log(message);
```

### 🔥 **Ưu điểm của toán tử điều kiện:**
- Giúp mã ngắn gọn và dễ đọc trong các trường hợp đơn giản.
- Có thể sử dụng trong biểu thức, ví dụ như gán giá trị cho biến hoặc trong các biểu thức khác.

**Ví dụ khác:**
```javascript
let result = (score >= 50) ? "Pass" : "Fail";
console.log(result);  // Output: "Pass" nếu score >= 50
```

---


## 💛 Regular Expressions


**Regular Expression (Biểu thức chính quy)** là một công cụ mạnh mẽ trong lập trình, dùng để tìm kiếm, kiểm tra và thay thế chuỗi theo các mẫu (pattern) xác định trước. Biểu thức chính quy giúp bạn xử lý và phân tích chuỗi một cách hiệu quả, đặc biệt là trong các bài toán như kiểm tra định dạng dữ liệu, tìm kiếm và thay thế trong văn bản.

### 🔥 **Cấu trúc cơ bản của Regular Expression:**

Biểu thức chính quy là một chuỗi ký tự mô tả mẫu chuỗi mà bạn muốn tìm kiếm. Các thành phần cơ bản của một Regular Expression bao gồm:

1. **Ký tự đặc biệt:**
   - `.` : Đại diện cho bất kỳ ký tự nào (trừ ký tự xuống dòng).
   - `^` : Đại diện cho bắt đầu chuỗi.
   - `$` : Đại diện cho kết thúc chuỗi.
   - `[]` : Đại diện cho tập hợp các ký tự. Ví dụ: `[a-z]` sẽ khớp với bất kỳ ký tự nào trong phạm vi từ `a` đến `z`.
   - `|` : Đại diện cho phép lựa chọn giữa các mẫu. Ví dụ: `abc|def` sẽ khớp với "abc" hoặc "def".
   - `()` : Dùng để nhóm các phần tử lại với nhau, ví dụ `(abc|def)`.

2. **Ký tự số lượng:**
   - `*` : Khớp với 0 hoặc nhiều lần xuất hiện của ký tự trước.
   - `+` : Khớp với 1 hoặc nhiều lần xuất hiện của ký tự trước.
   - `?` : Khớp với 0 hoặc 1 lần xuất hiện của ký tự trước.
   - `{n}` : Khớp với đúng n lần xuất hiện của ký tự trước.
   - `{n,}` : Khớp với ít nhất n lần xuất hiện.
   - `{n,m}` : Khớp với ít nhất n và tối đa m lần xuất hiện.

3. **Các ký tự đặc biệt khác:**
   - `\d` : Đại diện cho bất kỳ chữ số nào (tương đương với `[0-9]`).
   - `\w` : Đại diện cho bất kỳ ký tự từ a-z, A-Z, 0-9 hoặc dấu gạch dưới `_` (tương đương với `[a-zA-Z0-9_]`).
   - `\s` : Đại diện cho bất kỳ khoảng trắng nào (bao gồm dấu cách, tab, xuống dòng).
   - `\b` : Đại diện cho ranh giới của một từ.

4. **Phạm vi và ký tự đặc biệt:**
   - `[a-z]` : Khớp với bất kỳ ký tự nào trong phạm vi từ `a` đến `z`.
   - `[^a-z]` : Khớp với bất kỳ ký tự nào **không phải** từ `a` đến `z`.

### 🔥 **Ví dụ về Regular Expression:**

1. **Kiểm tra xem chuỗi có phải là một email hợp lệ không:**
   ```javascript
   const emailRegex = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
   const email = "example@domain.com";
   console.log(emailRegex.test(email));  // true
   ```

2. **Tìm kiếm số điện thoại theo định dạng `(xxx) xxx-xxxx`:**
   ```javascript
   const phoneRegex = /^\(\d{3}\) \d{3}-\d{4}$/;
   const phone = "(123) 456-7890";
   console.log(phoneRegex.test(phone));  // true
   ```

3. **Tìm tất cả các số trong một chuỗi:**
   ```javascript
   const numbersRegex = /\d+/g;
   const text = "I have 2 apples and 3 oranges.";
   console.log(text.match(numbersRegex));  // ["2", "3"]
   ```

4. **Thay thế tất cả các dấu cách bằng dấu gạch dưới trong chuỗi:**
   ```javascript
   const spaceRegex = /\s+/g;
   const text = "Hello World";
   console.log(text.replace(spaceRegex, "_"));  // "Hello_World"
   ```

### 🔥 **Ứng dụng của Regular Expression:**
- **Kiểm tra định dạng:** Email, số điện thoại, ngày tháng, mã zip, v.v.
- **Tìm kiếm và thay thế chuỗi:** Thay thế tất cả các từ, tìm kiếm trong các văn bản dài.
- **Phân tích văn bản:** Trích xuất dữ liệu từ chuỗi (ví dụ: trích xuất tên miền từ URL).
- **Lọc dữ liệu:** Loại bỏ hoặc giữ lại các chuỗi thỏa mãn điều kiện nhất định.

