# Buổi 2: Khai báo biến và kiểu dữ liệu

**Mục tiêu:** Làm quen với cú pháp khai báo biến và kiểu dữ liệu của biến.

## 💛 Khai báo biến:

Có ba từ khóa để khai báo biến trong TypeScript là `var`, `let`, và `const`.

- `var`: Phạm vi hoạt động trong toàn bộ function hoặc toàn cục nếu khai báo ngoài function.
- `let`: Phạm vi hoạt động trong block `{}`, ví dụ như trong vòng lặp, câu lệnh điều kiện.
- `const`: Tương tự như `let` nhưng giá trị không thể thay đổi sau khi đã gán.

### 🔥 Ví dụ


```typescript
var name = "Nguyen Van A";
let age = 30;
const isStudent = true;
```

### 🔥 Gán lại giá trị cho biến

Khi sử dụng `var` hoặc `let`, bạn có thể gán lại giá trị cho biến:

```typescript
var name = "Nguyen Van A";
name = "Tran Van B"; // valid
let age = 30;
age = 35; // valid
```

Tuy nhiên, với `const`, bạn không thể gán lại giá trị cho biến sau khi nó đã được khởi tạo:

```typescript
const isStudent = true;
isStudent = false; // Error: Assignment to constant variable.
```

Biến khai báo với `const` cần được gán giá trị ngay tại thời điểm khai báo và không thể thay đổi giá trị đó sau này.



## 💛 Các kiểu dữ liệu cơ bản:

- `string`: Chuỗi ký tự.
- `number`: Số.
- `boolean`: Giá trị đúng/sai.
- `any`: Bất kỳ kiểu dữ liệu nào.
- `null`: Không có giá trị.
- `undefined`: Chưa được gán giá trị.

### 🔥Ví dụ


```typescript
let company: string = "ABC Corp";
let salary: number = 5000;
let isActive: boolean = false;
let data: any = { name: "XYZ" };
let user = null;
let score: number;
```

### 🔥 Kiểm tra kiểu dữ liệu của biến

Sử dụng `typeof` để kiểm tra kiều dử liệu của biến

```typescript
typeof "John"         // Returns string
typeof ("John"+"Doe") // Returns string
typeof 3.14           // Returns number
typeof 33             // Returns number
typeof (33 + 66)      // Returns number
typeof true           // Returns boolean
typeof false          // Returns boolean
typeof 1234n          // Returns bigint
typeof Symbol()       // Returns symbol
typeof x              // Returns undefined
```

## 💛 Một số lệnh cơ bản

### **`console`**
Phương thức **`console`** được sử dụng để ghi thông tin vào bảng điều khiển (console) của trình duyệt, thường dùng cho mục đích gỡ lỗi (debug) hoặc in thông tin.

#### **Các phương thức phổ biến của `console`:**

1. **`console.log(message)`**
   - In ra thông tin thông thường.
   - Ví dụ:
     ```javascript
     console.log("Hello, world!");
     console.log("Số 5:", 5);
     ```

2. **`console.warn(message)`**
   - In ra thông báo cảnh báo.
   - Ví dụ:
     ```javascript
     console.warn("Đây là cảnh báo!");
     ```

3. **`console.error(message)`**
   - In ra thông báo lỗi.
   - Ví dụ:
     ```javascript
     console.error("Đã xảy ra lỗi!");
     ```

4. **`console.table(data)`**
   - Hiển thị dữ liệu dạng bảng.
   - Ví dụ:
     ```javascript
     const users = [
         { id: 1, name: "John" },
         { id: 2, name: "Jane" }
     ];
     console.table(users);
     ```

5. **`console.group()` và `console.groupEnd()`**
   - Nhóm các thông điệp lại với nhau.
   - Ví dụ:
     ```javascript
     console.group("Nhóm Thông Tin");
     console.log("Thông tin A");
     console.log("Thông tin B");
     console.groupEnd();
     ```

---

### **`confirm`**
Phương thức **`confirm`** hiển thị một hộp thoại với câu hỏi xác nhận (Yes/No), và trả về giá trị **`true`** nếu người dùng nhấn "OK" và **`false`** nếu nhấn "Cancel".

#### **Cách sử dụng:**
```javascript
const isConfirmed = confirm("Bạn có chắc chắn muốn xóa?");
if (isConfirmed) {
    console.log("Người dùng chọn OK.");
} else {
    console.log("Người dùng chọn Cancel.");
}
```

#### **Ứng dụng:**
- Xác nhận trước khi thực hiện hành động quan trọng (xóa dữ liệu, gửi thông tin, v.v.).

---

### **`alert`**
Phương thức **`alert`** hiển thị một hộp thoại thông báo với nội dung và chỉ có một nút "OK". Hộp thoại này được dùng để hiển thị thông tin nhanh đến người dùng.

#### **Cách sử dụng:**
```javascript
alert("Hệ thống đã lưu thành công!");
```

#### **Lưu ý:**
- `alert` làm gián đoạn luồng thực thi cho đến khi người dùng nhấn "OK".
- Hạn chế sử dụng quá nhiều để tránh gây khó chịu cho người dùng.

---

### **`prompt`**
Phương thức **`prompt`** hiển thị một hộp thoại yêu cầu người dùng nhập dữ liệu. Nó trả về chuỗi mà người dùng nhập vào, hoặc **`null`** nếu người dùng nhấn "Cancel".

#### **Cách sử dụng:**
```javascript
const name = prompt("Nhập tên của bạn:");
if (name) {
    alert(`Chào mừng, ${name}!`);
} else {
    alert("Bạn chưa nhập tên.");
}
```

#### **Ứng dụng:**
- Thu thập thông tin nhanh từ người dùng mà không cần tạo giao diện nhập liệu phức tạp.

---

### **So sánh các phương thức:**

| Phương thức | Mục đích                                    | Tương tác          | Kết quả trả về          |
|-------------|---------------------------------------------|--------------------|-------------------------|
| `console`   | Ghi log để gỡ lỗi                          | Không              | Không có kết quả trực tiếp |
| `confirm`   | Yêu cầu xác nhận (Yes/No)                  | Có                | `true` hoặc `false`    |
| `alert`     | Hiển thị thông báo                         | Có                | Không trả về kết quả    |
| `prompt`    | Yêu cầu người dùng nhập dữ liệu            | Có                | Chuỗi hoặc `null`      |

---

### **Ví dụ thực tế với tất cả các phương thức:**
```javascript
console.log("Hệ thống khởi động...");

const isConfirmed = confirm("Bạn có muốn tiếp tục?");
if (isConfirmed) {
    const name = prompt("Hãy nhập tên của bạn:");
    if (name) {
        alert(`Chào mừng, ${name}!`);
        console.log(`Người dùng nhập tên: ${name}`);
    } else {
        alert("Bạn đã không nhập tên.");
    }
} else {
    alert("Bạn đã hủy thao tác.");
    console.warn("Người dùng chọn không tiếp tục.");
}
``` 


## 💛 Khai báo kiểu tường minh và sử dụng `type inference`

TypeScript hỗ trợ khai báo kiểu tường minh, nghĩa là bạn có thể chỉ định rõ ràng kiểu dữ liệu cho biến. Nếu không chỉ định, TypeScript sẽ sử dụng `type inference` để tự động xác định kiểu dữ liệu dựa trên giá trị được gán.

### 🔥Ví dụ


```typescript
let explicitString: string = "This is a string";
let inferredString = "This is also a string"; // type inferred as `string`
//Nếu bạn khai báo lại giá trị
explicitString = 12 // => Error
```

## 💛 Sử dụng `enum` trong TypeScript

`enum` cho phép định nghĩa một tập hợp các hằng số có tên.

### 🔥Ví dụ


```typescript
enum Color {
    Red,
    Green,
    Blue
}
let c: Color = Color.Green;
console.log(c.)
```

## 💛 Sử dụng `Union` trong TypeScript

Union là một tính năng cho phép một biến có thể lưu trữ nhiều kiểu dữ liệu khác nhau.

### 🔥 Ví dụ:


```typescript
let multiType: number | string;
multiType = 20; // valid
multiType = "twenty"; // valid
```

## 💛 Chuỗi và các phương thức xử lý Chuỗi

Các phương thức xử lý chuỗi trong TypeScript giúp bạn làm việc với chuỗi một cách dễ dàng hơn.

### 🔥 Ví dụ

Ví dụ 1:

```typescript
let carName1 = "Volvo XC60";  // Double quotes
let carName2 = 'Volvo XC60';  // Single quotes
```

Ví dụ 2

```typescript
let answer1 = "It's alright";
let answer2 = "He is called 'Johnny'";
let answer3 = 'He is called "Johnny"';
```

### 🔥 String Length

Lấy độ dài của một chuổi

```typescript
let text = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = text.length;
console.log('length',length);
```

### 🔥 Escape Characters

Trong TypeScript, các ký tự đặc biệt có thể được "thoát" bằng cách sử dụng dấu gạch chéo ngược (`\`). Điều này cho phép bạn sử dụng các ký tự đặc biệt trong chuỗi mà không gây ra lỗi cú pháp.

Ví dụ:

```typescript
let example1 = "Dòng này chứa \"dấu ngoặc kép\"";
let example2 = 'Đây là cách sử dụng dấu gạch chéo ngược: \\';
let example3 = "Xuống dòng mới\nDòng mới";
```

Danh sách một số kí tự `thoát`

| **Code** | **Result**               | **Giải thích (Tiếng Việt)**                              |
|----------|--------------------------|----------------------------------------------------------|
| `\b`     | Backspace                | Xóa ký tự đứng trước con trỏ                              |
| `\f`     | Form Feed                | Chuyển sang trang mới trong máy in (ít được sử dụng)     |
| `\n`     | New Line                 | Xuống dòng mới                                           |
| `\r`     | Carriage Return          | Đưa con trỏ về đầu dòng nhưng không xuống dòng mới        |
| `\t`     | Horizontal Tabulator     | Tab ngang, thường để căn chỉnh khoảng cách               |
| `\v`     | Vertical Tabulator       | Tab dọc, ít được sử dụng                                 |


Ví dụ áp dụng:

```js
console.log("Hello\b World!"); // Sử dụng \b (Backspace)
console.log("Hello\fWorld!");  // Sử dụng \f (Form Feed)
console.log("Hello\nWorld!");  // Sử dụng \n (New Line)
console.log("Hello\rWorld!");  // Sử dụng \r (Carriage Return)
console.log("Hello\tWorld!");  // Sử dụng \t (Horizontal Tabulator)
console.log("Hello\vWorld!");  // Sử dụng \v (Vertical Tabulator)

console.log("Error: Something went wrong!\nPlease try again later.");
console.log("Name\tAge\tCity");
console.log("John\t25\tNew York");
console.log("Anna\t30\tLondon");

```


### 🔥 Template Strings

Template strings (còn được gọi là template literals) trong TypeScript cung cấp cách thức thuận tiện để tạo chuỗi. Chúng cho phép bạn kết hợp các biến, biểu thức và xuống dòng một cách trực tiếp trong chuỗi.

Cú pháp sử dụng dấu backtick (` ` `) thay vì dấu ngoặc đơn hoặc kép:

```typescript
let firstName = "Nguyen";
let lastName = "Van A";
let fullName = `Tên đầy đủ: ${firstName} ${lastName}`;
let multiLineString = `Dòng đầu tiên
Dòng thứ hai
Dòng thứ ba`;
```

Template strings rất hữu ích khi bạn cần tạo chuỗi phức tạp mà không muốn sử dụng phép nối chuỗi truyền thống.

### 🔥 Các phương thức xử lý chuỗi

Tham khảo đầy đủ tại: https://www.w3schools.com/js/js_string_methods.asp


Dưới đây là danh sách một số phương thức chuỗi thường được sử dụng trong JavaScript:

---

**1. `length`**
- **Mô tả:** Trả về độ dài của chuỗi.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.length); // Output: 13
  ```

---

**2. `toUpperCase()`**
- **Mô tả:** Chuyển tất cả các ký tự trong chuỗi thành chữ hoa.
- **Ví dụ:**
  ```javascript
  const str = "hello";
  console.log(str.toUpperCase()); // Output: "HELLO"
  ```

---

**3. `toLowerCase()`**
- **Mô tả:** Chuyển tất cả các ký tự trong chuỗi thành chữ thường.
- **Ví dụ:**
  ```javascript
  const str = "HELLO";
  console.log(str.toLowerCase()); // Output: "hello"
  ```

---

**4. `indexOf()`**
- **Mô tả:** Tìm vị trí đầu tiên của một chuỗi con trong chuỗi. Trả về `-1` nếu không tìm thấy.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.indexOf("World")); // Output: 7
  console.log(str.indexOf("JavaScript")); // Output: -1
  ```

---

**5. `includes()`**
- **Mô tả:** Kiểm tra chuỗi có chứa chuỗi con hay không. Trả về `true` hoặc `false`.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.includes("World")); // Output: true
  console.log(str.includes("JavaScript")); // Output: false
  ```

---

**6. `slice(start, end)`**
- **Mô tả:** Trích xuất một phần của chuỗi từ vị trí `start` đến `end` (không bao gồm `end`).
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.slice(7, 12)); // Output: "World"
  console.log(str.slice(7));     // Output: "World!"
  ```

---

**7. `substring(start, end)`**
- **Mô tả:** Tương tự `slice`, nhưng không hỗ trợ chỉ số âm.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.substring(7, 12)); // Output: "World"
  console.log(str.substring(7));     // Output: "World!"
  ```

---

**8. `replace(searchValue, newValue)`**
- **Mô tả:** Thay thế giá trị đầu tiên tìm thấy bằng giá trị mới.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.replace("World", "JavaScript")); // Output: "Hello, JavaScript!"
  ```

---

**9. `split(separator)`**
- **Mô tả:** Chia chuỗi thành một mảng các chuỗi con dựa trên ký tự phân tách (`separator`).
- **Ví dụ:**
  ```javascript
  const str = "apple,banana,cherry";
  console.log(str.split(",")); // Output: ["apple", "banana", "cherry"]
  ```

---

**10. `trim()`**
- **Mô tả:** Loại bỏ khoảng trắng ở đầu và cuối chuỗi.
- **Ví dụ:**
  ```javascript
  const str = "   Hello, World!   ";
  console.log(str.trim()); // Output: "Hello, World!"
  ```

---

**11. `concat()`**
- **Mô tả:** Nối hai hoặc nhiều chuỗi lại với nhau.
- **Ví dụ:**
  ```javascript
  const str1 = "Hello";
  const str2 = "World";
  console.log(str1.concat(", ", str2, "!")); // Output: "Hello, World!"
  ```

---

**12. `charAt(index)`**
- **Mô tả:** Trả về ký tự tại vị trí `index` trong chuỗi.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.charAt(7)); // Output: "W"
  ```

---

**13. `startsWith()`**
- **Mô tả:** Kiểm tra chuỗi có bắt đầu bằng một chuỗi con cụ thể hay không.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.startsWith("Hello")); // Output: true
  console.log(str.startsWith("World")); // Output: false
  ```

---

**14. `endsWith()`**
- **Mô tả:** Kiểm tra chuỗi có kết thúc bằng một chuỗi con cụ thể hay không.
- **Ví dụ:**
  ```javascript
  const str = "Hello, World!";
  console.log(str.endsWith("World!")); // Output: true
  console.log(str.endsWith("Hello"));  // Output: false
  ```

---

**15. `repeat(count)`**
- **Mô tả:** Lặp lại chuỗi một số lần chỉ định.
- **Ví dụ:**
  ```javascript
  const str = "Hello! ";
  console.log(str.repeat(3)); // Output: "Hello! Hello! Hello! "
  ```

---
