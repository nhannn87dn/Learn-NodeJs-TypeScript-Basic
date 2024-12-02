# Buổi 7: Functions và Modules

**Mục tiêu:** Làm quen với cách định nghĩa và sử dụng hàm (functions) trong TypeScript, đồng thời tổ chức code hiệu quả hơn với modules.  


## 💛 **HÀM TRONG TYPESCRIPT**


### 🔥 **Hàm trong JavaScript là gì?**

Hàm (Function) trong JavaScript là một khối mã được thiết kế để thực hiện một nhiệm vụ cụ thể. Hàm có thể được gọi (hoặc "chạy") bất cứ khi nào cần, giúp giảm thiểu việc lặp lại mã và cải thiện khả năng tái sử dụng.

---

### 🔥 **Tại sao cần sử dụng hàm trong JavaScript?**

1. **Tái sử dụng mã**: Một hàm có thể được gọi nhiều lần mà không cần phải viết lại mã.
2. **Tổ chức mã**: Giúp mã nguồn dễ đọc, dễ quản lý.
3. **Giảm lỗi**: Việc chia nhỏ logic thành các hàm nhỏ giúp phát hiện và sửa lỗi dễ dàng hơn.
4. **Hỗ trợ xử lý tác vụ phức tạp**: Tích hợp các logic phức tạp vào một hàm đơn giản.

---

### 🔥 **Cách khai báo hàm trong JavaScript**


#### **0. Cấu trúc của một hàm**

```javascript
function functionName(parameters) {
  // Khối mã thực thi
  return value; // (tùy chọn) Giá trị trả về
}
```

- **`functionName`**: Tên của hàm.
- **`parameters`**: Các tham số truyền vào (có thể có nhiều tham số, phân cách bởi dấu phẩy `,`).
- **`return`**: Dùng để trả về kết quả (tùy chọn).


#### **1. Hàm có tên (Named Function)**
Đây là cách khai báo hàm phổ biến nhất, với một tên rõ ràng.
```javascript
function greet() {
   console.log(`Hello`);
}
// Gọi hàm = Chạy hàm
greet(); // Hello
```

#### **2. Hàm nặc danh (Anonymous Function)**
Hàm không có tên, thường được gán vào một biến hoặc được sử dụng làm tham số.
```javascript
const anonymous = function () {
  console.log(`Hello`);
};
// Gọi hàm = Chạy hàm
anonymous(); // Hello
```

#### **3. Hàm mũi tên (Arrow Function)**
Cách viết ngắn gọn hơn của hàm nặc danh, được giới thiệu từ ES6.

```javascript
const arrowFunc =  () => {
  console.log(`Hello`);
};
// Gọi hàm = Chạy hàm
arrowFunc(); // Hello
```

---

### 🔥 **Tham số và đối số trong hàm**


#### **1. Tham số (Parameters)**

- **Định nghĩa**: Tham số là các biến được định nghĩa trong phần khai báo của hàm. Chúng đóng vai trò là "đầu vào" mà hàm mong đợi khi được gọi.  
- **Mục đích**: Tham số giúp hàm nhận dữ liệu từ bên ngoài để thực hiện các nhiệm vụ cụ thể.

**Ví dụ**:
```javascript
function greet(name) { // 'name' là tham số
  console.log(`Hello, ${name}!`);
}
```

---

#### **2. Đối số (Arguments)**

- **Định nghĩa**: Đối số là giá trị thực tế được truyền vào khi gọi hàm.  
- **Mục đích**: Đối số cung cấp giá trị cụ thể cho tham số của hàm khi hàm được gọi.

**Ví dụ**:
```javascript
greet("Alice"); // 'Alice' là đối số
```

---

##### **Mối quan hệ giữa tham số và đối số**

- **Tham số** là một placeholder (chỗ giữ chỗ) được định nghĩa trong hàm.  
- **Đối số** là giá trị thực tế mà bạn truyền cho tham số khi gọi hàm.  

**Ví dụ minh họa**:
```javascript
function add(a, b) { // 'a' và 'b' là tham số
  return a + b;
}

console.log(add(3, 5)); // 3 và 5 là đối số
```

---

##### **Các trường hợp sử dụng tham số và đối số**

**1. Tham số mặc định**
Bạn có thể gán giá trị mặc định cho tham số. Nếu không có đối số nào được truyền vào, tham số sẽ sử dụng giá trị mặc định.
```javascript
function greet(name = "Guest") {
  console.log(`Hello, ${name}!`);
}
greet();            // Hello, Guest!
greet("Alice");     // Hello, Alice!
```

---

**2. Tham số tùy chọn**
Trong TypeScript, bạn có thể đánh dấu tham số là tùy chọn bằng cách sử dụng dấu `?`.
```typescript
function introduce(name: string, age?: number): string {
  return age ? `${name} is ${age} years old.` : `${name}'s age is unknown.`;
}
console.log(introduce("Alice"));       // Alice's age is unknown.
console.log(introduce("Bob", 30));     // Bob is 30 years old.
```

---

**3. Sử dụng toán tử `rest`**
Bạn có thể sử dụng toán tử `rest` (`...`) để gom nhóm các đối số vào một mảng.
```javascript
function sum(...numbers) { // 'numbers' là một mảng chứa các đối số
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4)); // 10
```

---

**4. Đối số dạng mảng (`spread`)**
Bạn có thể sử dụng toán tử `spread` (`...`) để truyền một mảng làm các đối số riêng lẻ cho hàm.
```javascript
function multiply(a, b, c) {
  return a * b * c;
}
const nums = [2, 3, 4];
console.log(multiply(...nums)); // 24
```

---


| **Thuật ngữ**  | **Tham số (Parameters)**         | **Đối số (Arguments)**           |
|-----------------|----------------------------------|-----------------------------------|
| **Khai báo tại**| Trong phần định nghĩa của hàm.   | Khi gọi hàm.                     |
| **Là gì?**      | Biến placeholder (chỗ giữ chỗ). | Giá trị thực tế được truyền vào. |
| **Ví dụ**       | `function add(a, b)`            | `add(3, 5)`                      |

---

**Lưu ý**

1. Số lượng đối số khi gọi hàm không nhất thiết phải khớp với số lượng tham số:
   - Nếu thừa đối số, chúng bị bỏ qua.
   - Nếu thiếu đối số, tham số không được gán giá trị sẽ là `undefined`.
```javascript
function example(a, b) {
  console.log(a, b);
}
example(1);       // 1 undefined
example(1, 2, 3); // 1 2
```

2. Bạn có thể kiểm tra đối số được truyền vào bằng `arguments` (trong hàm thường, không áp dụng cho hàm mũi tên):
```javascript
function showArguments() {
  console.log(arguments); // [1, 2, 3]
}
showArguments(1, 2, 3);
```

---

### 🔥 **Hàm có `return`**

Hàm có `return` trong JavaScript là một hàm trả về một giá trị cụ thể khi nó được gọi. Lệnh `return` được sử dụng để kết thúc hàm và trả giá trị từ hàm đó về nơi nó được gọi.

---

#### **Cú pháp**

```javascript
function functionName(parameters) {
  // Khối mã thực thi
  return value; // Giá trị được trả về
}
```

- **`value`**: Là giá trị mà hàm trả về (có thể là bất kỳ kiểu dữ liệu nào như số, chuỗi, mảng, object, hoặc một hàm khác).
- Khi hàm gặp lệnh `return`, nó sẽ dừng thực thi ngay lập tức.

---

#### **Tại sao sử dụng `return`?**

1. **Trả giá trị cho nơi gọi hàm**: Giúp bạn nhận kết quả của một phép tính hoặc logic.
2. **Kết thúc hàm sớm**: Lệnh `return` có thể được sử dụng để kết thúc hàm trước khi toàn bộ mã được thực thi.
3. **Tái sử dụng logic**: Các giá trị trả về từ hàm có thể được sử dụng nhiều lần hoặc trong các hàm khác.

---

#### **Ví dụ**

**1. Hàm trả về số**
```javascript
function add(a, b) {
  return a + b;
}
const result = add(5, 3); // Lưu giá trị trả về vào biến
console.log(result); // 8
```

**2. Hàm trả về chuỗi**
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}
console.log(greet("Alice")); // Hello, Alice!
```

**3. Hàm trả về mảng**
```javascript
function getEvenNumbers(arr) {
  return arr.filter((num) => num % 2 === 0);
}
console.log(getEvenNumbers([1, 2, 3, 4, 5])); // [2, 4]
```

**4. Hàm trả về object**
```javascript
function createUser(name, age) {
  return { name: name, age: age };
}
console.log(createUser("Alice", 25)); // { name: "Alice", age: 25 }
```


#### **Sử dụng `return` để kết thúc hàm sớm**

Hàm sẽ dừng thực thi ngay khi gặp lệnh `return`.  
Điều này hữu ích trong các trường hợp cần thoát sớm khi gặp điều kiện cụ thể.

**Ví dụ**:
```javascript
function checkAge(age) {
  if (age < 18) {
    return "You are not allowed.";
  }
  return "Welcome!";
}
console.log(checkAge(16)); // You are not allowed.
console.log(checkAge(20)); // Welcome!
```

---

#### **Hàm trả về hàm khác**

Trong JavaScript, hàm có thể trả về một hàm khác (Higher-Order Function):
```javascript
function multiplier(factor) {
  return function (num) {
    return num * factor;
  };
}
const double = multiplier(2); // Hàm nhân đôi
console.log(double(5)); // 10
```

---

#### **Kết hợp `return` với các loại dữ liệu**

**Trả về kết quả của các phép tính**
```javascript
function calculateArea(width, height) {
  return width * height;
}
console.log(calculateArea(5, 10)); // 50
```

**Trả về giá trị boolean**
```javascript
function isEven(number) {
  return number % 2 === 0;
}
console.log(isEven(4)); // true
console.log(isEven(5)); // false
```

**Trả về giá trị từ mảng hoặc object**
```javascript
function getFirstElement(arr) {
  return arr[0];
}
console.log(getFirstElement([10, 20, 30])); // 10
```

---

### 🔥 **Hàm lồng nhau (Nested Function)**

Hàm được định nghĩa bên trong một hàm khác.

```javascript
function outerFunction(outerVariable) {
  function innerFunction(innerVariable) {
    console.log(`Outer: ${outerVariable}, Inner: ${innerVariable}`);
  }
  innerFunction("Inner Value");
}
outerFunction("Outer Value");
// Outer: Outer Value, Inner: Inner Value
```

### 🔥 **Hàm đệ quy (Recursive Function)**


Hàm đệ quy (Recursive Function) là một hàm trong lập trình tự gọi lại chính nó trong quá trình thực thi. Hàm này thường được sử dụng để giải quyết các bài toán có cấu trúc lặp đi lặp lại hoặc có thể chia nhỏ thành các bài toán con giống với bài toán ban đầu.

---

#### **Đặc điểm của hàm đệ quy**

1. **Điểm dừng (Base Case)**: Mỗi hàm đệ quy cần có một điều kiện dừng để tránh lặp vô hạn. Khi điều kiện này được thỏa mãn, hàm sẽ ngừng tự gọi lại.
2. **Quy luật đệ quy (Recursive Rule)**: Phần logic của hàm cần gọi lại chính nó để xử lý bài toán con.

---

####  **Cú pháp cơ bản**

```javascript
function recursiveFunction(parameters) {
  if (baseCondition) {
    // Điều kiện dừng
    return result;
  } else {
    // Gọi lại chính hàm với dữ liệu mới
    return recursiveFunction(modifiedParameters);
  }
}
```

---

####  **Ví dụ minh họa**

**1. Tính giai thừa (Factorial)**

Giai thừa của một số nguyên dương `n` được định nghĩa là:
- `n! = n * (n-1) * (n-2) * ... * 1`
- Điều kiện dừng: `0! = 1`

Hàm đệ quy tính giai thừa:
```javascript
function factorial(n) {
  if (n === 0) {
    return 1; // Điều kiện dừng
  }
  return n * factorial(n - 1); // Gọi lại chính hàm với n-1
}
console.log(factorial(5)); // Output: 120
```

---

####  **Ưu điểm của hàm đệ quy**

1. **Giải quyết bài toán lặp một cách tự nhiên**: Các bài toán như tìm kiếm, chia để trị, hoặc xử lý cây rất phù hợp với đệ quy.
2. **Mã ngắn gọn, dễ đọc**: Thay vì viết các vòng lặp phức tạp, đệ quy cung cấp cách tiếp cận trực quan hơn.

---

####  **Nhược điểm của hàm đệ quy**

1. **Hiệu suất thấp hơn so với vòng lặp**: Mỗi lần gọi hàm đệ quy sẽ tạo một khung (stack frame) mới trong bộ nhớ, dễ dẫn đến "tràn ngăn xếp" (stack overflow) nếu không có điều kiện dừng chính xác.
2. **Khó theo dõi lỗi**: Với các bài toán phức tạp, việc hiểu và sửa lỗi hàm đệ quy có thể khó khăn hơn.

**Ví dụ lỗi do thiếu điều kiện dừng**:
```javascript
function infiniteRecursion() {
  return infiniteRecursion(); // Không có điều kiện dừng
}
infiniteRecursion(); // Sẽ gây lỗi: Maximum call stack size exceeded
```

---

####  **Khi nào nên sử dụng hàm đệ quy?**

1. **Bài toán chia để trị (Divide and Conquer)**:
   - Ví dụ: Tìm kiếm nhị phân (Binary Search), sắp xếp nhanh (Quick Sort), sắp xếp trộn (Merge Sort).
   
2. **Xử lý cấu trúc cây hoặc đồ thị**:
   - Ví dụ: Duyệt cây (Tree Traversal), tìm đường trong đồ thị (Graph Traversal).

3. **Bài toán lặp dựa trên quan hệ đệ quy**:
   - Ví dụ: Dãy Fibonacci, giai thừa, và các chuỗi toán học.

---

### 🔥 **Callback Function**


**Callback Function** là một hàm được truyền làm tham số vào một hàm khác và được gọi lại (executed) bên trong hàm đó để hoàn thành một nhiệm vụ hoặc xử lý logic sau khi một sự kiện hoặc hành động xảy ra.  

Callback giúp bạn xử lý các tác vụ bất đồng bộ (asynchronous) như gọi API, đọc/ghi file, hoặc chờ thời gian mà không cần dừng toàn bộ chương trình.



####  **Cách hoạt động của Callback**

1. Hàm **A** nhận một hàm khác (Callback Function) làm tham số.  
2. Khi **A** hoàn thành một tác vụ nào đó, nó sẽ gọi lại hàm Callback đã được truyền vào.  
3. Hàm Callback sẽ thực hiện công việc cụ thể được chỉ định.

####  **Ví dụ minh họa**:
```javascript
function processUserInput(callback) {
  const name = "Alice";
  callback(name); // Gọi lại hàm callback với dữ liệu
}

function greetUser(userName) {
  console.log(`Hello, ${userName}!`);
}

processUserInput(greetUser); // Output: Hello, Alice!
```

---

####  **Tại sao sử dụng Callback Function?**

- **Xử lý bất đồng bộ**: Callback là cách phổ biến trong JavaScript để xử lý các tác vụ không đồng bộ, như:
  - Gọi API (fetch data).
  - Đọc/ghi file.
  - Chờ một hành động hoàn thành (timer, animation).
- **Tái sử dụng mã nguồn**: Giúp bạn tách biệt logic chung và hành động cụ thể.
- **Đơn giản hóa luồng xử lý**: Mã nguồn dễ dàng được tổ chức hơn khi các hành động được thực thi theo thứ tự mong muốn.

---

#### **Cú pháp cơ bản**

```javascript
function mainFunction(callback) {
  console.log("Executing main function...");
  callback(); // Gọi lại hàm callback
}

function myCallback() {
  console.log("Callback function executed!");
}

mainFunction(myCallback);
```

---

####   **Ví dụ cụ thể**

**1. Xử lý bất đồng bộ với `setTimeout`**
`setTimeout` là một ví dụ phổ biến về việc sử dụng Callback trong JavaScript:
```javascript
console.log("Start");

setTimeout(() => {
  console.log("This runs after 2 seconds.");
}, 2000); // Hàm callback được thực thi sau 2 giây

console.log("End");
```

**Kết quả in ra**:
```
Start
End
This runs after 2 seconds.
```


####  **Callback Hell**

Callback Hell xảy ra khi bạn sử dụng nhiều Callback lồng nhau, khiến mã nguồn khó đọc và duy trì.

**Ví dụ Callback Hell**:
```javascript
setTimeout(() => {
  console.log("Task 1");
  setTimeout(() => {
    console.log("Task 2");
    setTimeout(() => {
      console.log("Task 3");
    }, 1000);
  }, 1000);
}, 1000);
```

---

## 💛 **MODULES TRONG NODE.JS**

---

### 🔥 **1. Giới thiệu về modules**

**Module** là cách để tổ chức mã nguồn thành các tệp nhỏ, dễ quản lý và tái sử dụng. Trong Node.js, mỗi tệp `.js` hoặc `.ts` là một module. 

- **Lợi ích của modules**:
  - Tách biệt mã nguồn, tránh xung đột.
  - Tăng khả năng tái sử dụng.
  - Dễ dàng bảo trì và kiểm tra.

---

### 🔥 **2. Cách xuất và nhập modules**

**2.1. Sử dụng `export` và `import`**  
- **Default export**:
  ```typescript
  // math.ts
  export default function add(a: number, b: number): number {
    return a + b;
  }

  // main.ts
  import add from "./math";
  console.log(add(2, 3)); // 5
  ```

- **Named export**:
  ```typescript
  // math.ts
  export const multiply = (a: number, b: number): number => a * b;
  export const divide = (a: number, b: number): number => a / b;

  // main.ts
  import { multiply, divide } from "./math";
  console.log(multiply(4, 5)); // 20
  console.log(divide(10, 2));  // 5
  ```

**2.2. Import tất cả từ module**:
```typescript
import * as math from "./math";
console.log(math.multiply(3, 3)); // 9
```

---

### 🔥 **3. Sử dụng thư viện có sẵn (built-in modules)**

Node.js cung cấp nhiều module tích hợp sẵn giúp xử lý các tác vụ phổ biến.  

- **`fs`** (File System): Quản lý tệp.
  ```typescript
  import * as fs from "fs";
  fs.writeFileSync("example.txt", "Hello, world!");
  const content = fs.readFileSync("example.txt", "utf-8");
  console.log(content); // Hello, world!
  ```

- **`path`**: Làm việc với đường dẫn tệp.
  ```typescript
  import * as path from "path";
  const fullPath = path.join(__dirname, "example.txt");
  console.log(fullPath); // /path/to/example.txt
  ```

- **`url`**: Phân tích và xử lý URL.
  ```typescript
  import { URL } from "url";
  const myUrl = new URL("https://example.com/path?name=Alice");
  console.log(myUrl.hostname); // example.com
  console.log(myUrl.searchParams.get("name")); // Alice
  ```

---
