# Bài tập Buổi 7: Functions và Modules

## **Bài Tập Về Hàm**

### **1. Hàm không trả về**
Viết một hàm `greet()` không có tham số, không trả về giá trị, chỉ in ra màn hình câu chào `Hello, world!`.

---

### **2. Hàm có tham số**
Viết một hàm `sum(a, b)` nhận vào hai tham số `a` và `b`, và trả về tổng của chúng.

---

### **3. Hàm với giá trị mặc định**
Viết hàm `greetUser(name = "Guest")` nhận tham số `name` với giá trị mặc định là `"Guest"`, và in ra câu chào `Hello, <name>!`.

---

### **4. Hàm với toán tử Rest**
Viết hàm `sumAll(...numbers)` nhận vào một dãy số và trả về tổng của chúng.

---

### **5. Hàm trả về một giá trị**
Viết hàm `multiply(a, b)` nhận vào hai tham số `a` và `b`, và trả về tích của chúng.

---

### **6. Hàm nặc danh (Anonymous Function)**
Viết một hàm nặc danh gán vào biến `subtract` thực hiện phép trừ giữa hai số và trả về kết quả. Ví dụ: `subtract(10, 5)` sẽ trả về `5`.

---

### **7. Hàm mũi tên (Arrow Function)**
Viết một hàm mũi tên `isEven(num)` nhận vào một số `num` và trả về `true` nếu số đó là chẵn, và `false` nếu không.

---

### **8. Hàm đệ quy**
Viết hàm đệ quy `factorial(n)` tính giai thừa của một số nguyên dương `n`.

---

### **9. Hàm callback**
Viết một hàm `processNumbers(arr, callback)` nhận vào một mảng các số và một hàm `callback` để thực hiện một phép toán (ví dụ: nhân mỗi phần tử trong mảng với 2).

---

### **10. Hàm trả về hàm (Function Returning Function)**
Viết hàm `createMultiplier(factor)` nhận vào một tham số `factor` và trả về một hàm mới, hàm này nhận vào một tham số `num` và trả về kết quả `num * factor`.

---

## **Bài Tập Về Module (TypeScript)**

### **1. Giới thiệu về Module**
Tạo một file `math.ts` chứa các hàm:
- `add(a: number, b: number): number`
- `subtract(a: number, b: number): number`

Sau đó, tạo một file `main.ts`, import các hàm từ `math.ts` và sử dụng chúng để tính tổng và hiệu của hai số.

**math.ts:**
```typescript
export function add(a: number, b: number): number {
    return a + b;
}

export function subtract(a: number, b: number): number {
    return a - b;
}
```

**main.ts:**
```typescript
import { add, subtract } from './math';

const sum = add(5, 3);
const difference = subtract(10, 4);

console.log(`Sum: ${sum}`);
console.log(`Difference: ${difference}`);
```

---

### **2. Export và Import Named**

Tạo file `utils.ts` chứa một hàm `greet(name: string): void` in ra câu chào `Hello, <name>!`. Sau đó, import hàm này vào file `app.ts` và gọi hàm với tham số tên người dùng.

**utils.ts:**
```typescript
export function greet(name: string): void {
    console.log(`Hello, ${name}!`);
}
```

**app.ts:**
```typescript
import { greet } from './utils';

greet("Alice");
```

---

### **3. Export Default và Import Default**

Tạo file `user.ts` với một đối tượng `user` có các thuộc tính `name` và `age`. Sử dụng `export default` để xuất đối tượng `user`, sau đó import đối tượng này vào một file khác và in ra các thuộc tính của `user`.

**user.ts:**
```typescript
const user = {
    name: "John",
    age: 30
};

export default user;
```

**app.ts:**
```typescript
import user from './user';

console.log(`Name: ${user.name}`);
console.log(`Age: ${user.age}`);
```

---

### **4. Sử dụng Built-in Module (fs)**

Viết một chương trình Node.js sử dụng module `fs` để đọc nội dung của một file `text.txt` và in ra màn hình.

**readFile.ts:**
```typescript
import * as fs from 'fs';

fs.readFile('text.txt', 'utf-8', (err, data) => {
    if (err) {
        console.error('Error reading file:', err);
    } else {
        console.log('File content:', data);
    }
});
```

**Lưu ý:** Đảm bảo rằng file `text.txt` tồn tại trong cùng thư mục với file `readFile.ts`.

---
