# Buổi 8: Error handling và Tác vụ bất đồng bộ

**Mục tiêu:** Biết cách xử lý các lỗi xảy ra trong quá trình phát triển ứng dụng, hiểu và áp dụng được quy trình xử lý một tác vụ bất động bộ trong Javascript.   

## 💛 **Error Handling**


### 🔥 **Khái niệm**

Error Handling là quá trình dự đoán, phát hiện, và xử lý lỗi trong chương trình nhằm đảm bảo hệ thống hoạt động ổn định, tránh gián đoạn và cung cấp trải nghiệm tốt cho người dùng. Trong lập trình, lỗi có thể xảy ra bất cứ lúc nào, từ lỗi cú pháp, lỗi logic đến lỗi runtime.

Mục tiêu của Error Handling:

- Phát hiện lỗi nhanh chóng.
- Xử lý lỗi một cách hợp lý để chương trình tiếp tục hoạt động.
- Cung cấp thông tin rõ ràng về nguyên nhân lỗi.

### 🔥 **Các loại lỗi phổ biến**

#### 1. **Lỗi cú pháp (Syntax Errors):**
   - Xảy ra khi cú pháp của mã nguồn không hợp lệ.
   - Thường được phát hiện trong quá trình biên dịch hoặc trước khi thực thi chương trình.
   - **Ví dụ:**
     ```javascript
     console.log("Hello World // Thiếu dấu đóng ngoặc kép
     ```

#### 2. **Lỗi runtime (Runtime Errors):**
   - Xảy ra trong quá trình thực thi mã.
   - Do các vấn đề như tham chiếu biến không tồn tại, gọi hàm trên giá trị không hợp lệ, hoặc lỗi chia cho 0.
   - **Ví dụ:**
     ```javascript
     let x = undefined;
     console.log(x.y); // Cannot read properties of undefined
     ```

#### 3. **Lỗi logic (Logical Errors):**
   - Xảy ra khi mã chạy nhưng không mang lại kết quả mong muốn.
   - Loại lỗi này thường khó phát hiện vì chương trình không bị lỗi cú pháp hoặc runtime.
   - **Ví dụ:**
     ```javascript
     function add(a, b) {
       return a - b; // Sai logic
     }
     console.log(add(3, 2)); // Kết quả: 1 (sai)
     ```

---

### 🔥**Sử dụng `try...catch` và `finally`**

`try...catch` là một cấu trúc xử lý lỗi trong JavaScript, cho phép bạn:

- Phát hiện lỗi xảy ra trong một đoạn mã.
- Xử lý lỗi mà không làm gián đoạn luồng thực thi của chương trình.
- Tùy chọn thực hiện hành động sau khi xử lý lỗi (dùng `finally`).

**Cú pháp:**
```javascript
try {
  // Code có thể gây lỗi
} catch (error) {
  // Xử lý lỗi
} finally {
  // Thực thi dù lỗi xảy ra hay không
}
```

**Ví dụ:**
```javascript
try {
  let result = 10 / 0;
  console.log(result);
} catch (error) {
  console.error("An error occurred:", error.message);
} finally {
  console.log("Operation completed.");
}
```

---

### 🔥**Tạo và ném lỗi (`throw`)**

- Bạn có thể tạo lỗi tùy chỉnh và ném nó bằng từ khóa `throw`.

**Ví dụ:**
```javascript
function divide(a, b) {
  if (b === 0) {
    throw new Error("Cannot divide by zero");
  }
  return a / b;
}

try {
  console.log(divide(10, 0));
} catch (error) {
  console.error("Error:", error.message);
}
```

---

## 💛 **Xử lý bất đồng bộ**


### 🔥**1. Bất đồng bộ là gì?**

Bất đồng bộ (asynchronous) là cách xử lý các tác vụ không chặn luồng chính của chương trình. Điều này cho phép thực thi các tác vụ khác trong khi chờ tác vụ bất đồng bộ hoàn thành (ví dụ: tải dữ liệu từ API, đọc file).

**Ví dụ đồng bộ (synchronous):**
```javascript
console.log("Start");
let result = someSyncOperation();
console.log("Result:", result);
console.log("End");
```

**Ví dụ bất đồng bộ:**
```javascript
console.log("Start");
setTimeout(() => {
  console.log("Async operation completed");
}, 2000);
console.log("End");
```

---

### 🔥**2. Callback Hell**

Callback Hell xảy ra khi bạn sử dụng nhiều callback lồng nhau, khiến mã trở nên khó đọc và khó duy trì.

**Ví dụ Callback Hell:**
```javascript
setTimeout(() => {
  console.log("Step 1");
  setTimeout(() => {
    console.log("Step 2");
    setTimeout(() => {
      console.log("Step 3");
    }, 1000);
  }, 1000);
}, 1000);
```

**Cách giải quyết:**
- Sử dụng **Promises**.
- Sử dụng **async/await**.

---

### 🔥**3. Promise**

**Promise** là một cách hiện đại để xử lý bất đồng bộ, giúp giải quyết Callback Hell.  
Promise đại diện cho một giá trị sẽ có trong tương lai (resolved) hoặc một lỗi (rejected).

**Cú pháp cơ bản:**
```javascript
const myPromise = new Promise((resolve, reject) => {
  let success = true; // Giả lập kết quả
  if (success) {
    resolve("Promise fulfilled!"); // Kết quả khi thành công
  } else {
    reject("Promise rejected!"); // Kết quả khi thất bại
  }
});
```

**Sử dụng Promise**

```javascript
myPromise
  .then(result => {
    console.log(result); // In ra: "Promise fulfilled!"
  })
  .catch(error => {
    console.error(error);
  })
  .finally() {
    console.log("Finally completed.");
   }
```

---

### 🔥**4. Async/Await**

`async/await` là cú pháp hiện đại giúp viết mã bất đồng bộ trông như mã đồng bộ, dễ đọc và quản lý hơn.

- **`async`**: Được khai báo trước hàm, biến hàm đó thành hàm bất đồng bộ.
- **`await`**: Dừng thực thi hàm cho đến khi Promise được giải quyết (resolved/rejected).

**Ví dụ:**
```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("Data fetched successfully");
    }, 2000);
  });
}

async function getData() {
  try {
    let data = await fetchData();
    console.log(data);
  } catch (error) {
    console.error("Error:", error);
  }
}

getData();
```

---

### 🔥**5. Xử lý lỗi trong các hàm bất đồng bộ**

- **Sử dụng `try...catch` trong `async` function:**
```javascript
async function fetchData() {
  try {
    let response = await someAsyncFunction();
    console.log("Data:", response);
  } catch (error) {
    console.error("Error occurred:", error);
  }
}
```

- **Kết hợp `.catch()` với `await`:**
```javascript
async function fetchData() {
  await someAsyncFunction().catch(error => {
    console.error("Error occurred:", error);
  });
}
```

