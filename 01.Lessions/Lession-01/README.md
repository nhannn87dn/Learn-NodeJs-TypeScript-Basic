# Buổi 1: Giới thiệu và cài đặt môi trường

**Mục tiêu:** Làm quen với Node.js và TypeScript

## 💛 1. Node.js là gì? 

### 🔥 Tìm hiểu khái niệm

Node.js là một nền tảng phát triển phía server dựa trên JavaScript Engine của Chrome (V8 Engine). Nó cho phép chạy JavaScript trên server, không chỉ trên trình duyệt. Node.js được sử dụng rộng rãi vì nó hỗ trợ xử lý bất đồng bộ, giúp xử lý nhiều kết nối cùng một lúc mà không bị chặn.

![node](img/node-intro.png)

Node.js đã trở thành một trong những công nghệ nổi bật nhất trong lĩnh vực phát triển web và được sử dụng rộng rãi để xây dựng các ứng dụng web như các trang web động (dynamic web pages), các ứng dụng real-time và các ứng dụng web theo mô hình client-server.

Sau khi được phát hành lần đầu tiên vào năm 2009, Node.js nhanh chóng thu hút sự quan tâm và phát triển đáng kể. Các cập nhật liên tục đã được phát hành, bao gồm việc thêm các tính năng mới và cải tiến hiệu suất. Hiện nay, Node.js được sử dụng rộng rãi trên toàn cầu và là một trong những công nghệ phổ biến nhất trong lĩnh vực phát triển web.


### 🔶 Node.js hoạt động như thế nào?

Ý tưởng chính của Node js là sử dụng non-blocking, hướng sự vào ra dữ liệu thông qua các tác vụ thời gian thực một cách nhanh chóng. Bởi vì, Node js có khả năng mở rộng nhanh chóng, khả năng xử lý một số lượng lớn các kết nối đồng thời bằng thông lượng cao.

Nếu như các ứng dụng web truyền thống, các request tạo ra một luồng xử lý yêu cầu mới và chiếm RAM của hệ thống thì việc tài nguyên của hệ thống sẽ được sử dụng không hiệu quả. Chính vì lẽ đó giải pháp mà Node js đưa ra là sử dụng luồng đơn (Single-Threaded), kết hợp với non-blocking I/O để thực thi các request, cho phép hỗ trợ hàng chục ngàn kết nối đồng thời.

![nodejs](img/node-proceess.bmp)

### 🔥 Giới thiệu về Event Loop

**Event Loop** là một trong những khái niệm quan trọng nhất trong Node.js, vì nó giải thích cách Node.js xử lý các tác vụ đồng thời mặc dù nó chỉ chạy trên một luồng duy nhất (single-threaded). Node.js sử dụng event loop để quản lý các tác vụ bất đồng bộ như đọc/ghi file, yêu cầu HTTP, hoặc truy vấn cơ sở dữ liệu mà không chặn (blocking) luồng chính.

Trong Node.js, mã JavaScript chạy trong một luồng duy nhất, còn được gọi là luồng chính (main thread). Tuy nhiên, để xử lý các yêu cầu I/O không đồng bộ, như đọc và ghi vào tệp, gọi API mạng hoặc truy vấn cơ sở dữ liệu, Node.js sử dụng mô hình sự kiện và non-blocking I/O.

Client gửi các REQUEST đến SERVER để tương tác với ứng dụng web. Các REQUESTs này có thể là Blocking hoặc Non-Blocking

- Truy vấn dữ liệu
- Xóa dữ liệu
- Cập nhật dữ liệu

Node.JS tiếp nhận các Request gửi đến và thêm chúng vào hàng đợi `Event Queue`

Sau đó các yêu cầu `Request` này được xử lý lần lượt thông qua `Event Loop`.

![node-flow](img/node-flow.png)

Cơ chế hoạt động của **Event Loop**:

1. **Requests (Yêu cầu)**: Các yêu cầu từ người dùng được đưa vào **Hàng đợi sự kiện (Event Queue)**. Đây là nơi lưu trữ các sự kiện cần được xử lý.

2. **Event Loop (Vòng lặp sự kiện)**: Event Loop liên tục kiểm tra hàng đợi sự kiện để xem có sự kiện nào cần được xử lý hay không. Nếu có, nó sẽ lấy sự kiện ra khỏi hàng đợi và chuyển nó tới **Thread Pool** để xử lý. Các hoạt động không chặn (non-blocking operations) sẽ được xử lý trực tiếp, trong khi các hoạt động chặn (blocking operations) sẽ được gửi tới các nguồn tài nguyên bên ngoài như cơ sở dữ liệu, hệ thống tệp, v.v.

3. **Thread Pool (Nhóm luồng)**: Thread Pool xử lý các hoạt động chặn. Nó sẽ tạo ra các luồng riêng biệt để xử lý các tác vụ này.

4. **I/O Polling (Kiểm tra I/O)**: Có một hộp "I/O Polling" kết nối với Thread Pool, đại diện cho các cơ chế kiểm tra I/O như epoll, kqueue, v.v.

5. **External Resources (Nguồn tài nguyên bên ngoài)**: Khi công việc đã được hoàn thành, kết quả sau cùng sẽ được trả lại thông qua Event Loop và gửi lại cho người dùng.

Cơ chế này giúp Node.js xử lý nhiều yêu cầu một cách hiệu quả, đồng thời duy trì tính không chặn của ứng dụng.



### 🔥 Những ứng dụng nên viết bằng Node.JS ?

NodeJS được sử dụng để xây dựng rất nhiều loại ứng dụng khác nhau, trong đó phổ biến nhất gồm có:

- Ứng dụng trò chuyện trong thời gian thực: Nhờ vào cấu trúc không đồng bộ đơn luồng, Node.JS rất thích hợp cho mục đích xử lý giao tiếp trong thời gian thực. Nền tảng này có thể dễ dàng mở rộng quy mô và thường dùng để tạo ra các chatbot. Bên cạnh đó, các tính năng liên quan đến ứng dụng trò chuyện như: chat nhiều người, thông báo đẩy,… cũng có thể dễ dàng được bổ sung nhờ NodeJS.

- Internet of Things (IoT): Các ứng dụng IoT thường bao gồm nhiều bộ cảm biến phức tạp để gửi những phần dữ liệu nhỏ. Node.JS là một lựa chọn lý tưởng để xử lý các yêu cầu đồng thời này với tốc độ cực nhanh.

- Truyền dữ liệu: Netflix là một trong số những công ty lớn trên thế giới chuyên sử dụng Node.JS cho mục đích truyền dữ liệu. Sở dĩ vì đây là một nền tảng nhẹ và cực nhanh, đồng thời còn cung cấp một API chuyên dùng để stream.

- Các SPA (Single-page application) phức tạp: Trong SPA, toàn bộ ứng dụng được load vào trong một trang duy nhất, do đó sẽ có một số request được thực hiện trong nền. Vòng lặp sự kiện (event loop) của Node.JS cho phép xử lý các request theo hướng non-blocking.

- Các ứng dụng REST dựa trên API: JavaScript được sử dụng trong cả frontend lẫn backend của trang. Do đó một server có thể dễ dàng giao tiếp với frontend qua REST API bằng Node.js. Bên cạnh đó, Node.JS còn cung cấp nhiều package như Express.js hay Koa để việc xây dựng ứng dụng web trở nên dễ dàng hơn bao giờ hết.

### 🔥 Ưu điểm NodeJS

- IO hướng sự kiện không đồng bộ, cho phép xử lý nhiều yêu cầu đồng thời.
- Sử dụng JavaScript – một ngôn ngữ lập trình dễ học.
- Chia sẻ cùng code ở cả phía client và server.
- NPM(Node Package Manager) và module Node đang ngày càng phát triển mạnh mẽ.
- Cộng đồng hỗ trợ tích cực.
- Cho phép stream các file có kích thước lớn.

### 🔥 Nhược điểm NodeJS

- Không có khả năng mở rộng, vì vậy không thể tận dụng lợi thế mô hình đa lõi trong các phần cứng cấp server hiện nay.
- Khó thao tác với cơ sử dữ liệu quan hệ.
- Mỗi callback sẽ đi kèm với rất nhiều callback lồng nhau khác.
- Cần có kiến thức tốt về JavaScript.
- Không phù hợp với các tác vụ đòi hỏi nhiều CPU.

### 🔥 Một số lý do nên sử dụng NodeJS là gì?

Node.JS là một trong những nền tảng phổ biến nhất hiện nay cho mục đích phát triển ứng dụng mạng phía server. Vậy lý do nên sử dụng NodeJS là gì? Hãy cùng tìm hiểu những đặc điểm khiến Node.JS là lựa chọn hàng đầu cho các developer hiện nay:

- Tốc độ cực nhanh: Được xây dựng dựa trên engine JavaScript V8 của Google Chrome, do đó các thư viện của nó có khả năng thực thi code chỉ rất nhanh.
- NPM: Với hơn 50,000 package khác nhau, các developer có thể dễ dàng lựa chọn bất kỳ tính năng nào để xây dựng cho ứng dụng của mình.
- Lập trình không đồng bộ: Mọi API của Node.JS đều có tính không đồng bộ (non-blocking), do đó một server dựa trên Node.JS không cần phải đợi API trả về dữ liệu.
- Không có buffering: Node.JS giúp tiết kiệm thời gian xử lý file khi cần upload âm thanh hoặc video vì các ứng dụng này không bao giờ buffer dữ liệu mà chỉ xuất dữ liệu theo từng phần (chunk).
- Đơn luồng: Node.JS sử dụng mô hình đơn luồng với vòng lặp sự kiện. Do đó các ứng dụng có thể xử lý số lượng request lớn hơn rất nhiều so với các server truyền thống như Apache HTTP Server.

### 🔥 Những công ty lớn nào đang sử dụng NodeJS

NodeJS hiện đang được sử dụng bởi rất nhiều gã khổng lồ trên khắp thế giới, nhanh chóng vượt ngưỡng 1 tỉ lượt download từ năm 2018 và hỗ trợ đến khoảng 1.2% tổng số website trên Internet, tương đương với 20 triệu trang.

Một số công ty lớn sử dụng nền tảng này gồm có:

- Netflix: Netflix là một trong những nền tảng giải trí trực tuyến lớn nhất thế giới với hơn 167 triệu người dùng. Nhờ vào khả năng mở rộng và cho phép xây dựng các ứng dụng có yêu cầu sử dụng dữ liệu cao, NodeJS luôn là lựa chọn hàng đầu cho nền tảng này.
- Walmart: Đây là công ty có doanh thu lớn nhất thế giới với tổng 559 tỷ USD vào năm 2020 (theo Forbest). Walmart lựa chọn NodeJS bởi tính năng I/O không đồng bộ và khả năng xử lý nhiều request đồng thời.
- Uber: Là một công ty đặt xe có quy mô đa quốc gia, Uber lựa chọn NodeJS làm nền tảng xây dựng ứng dụng bởi I/O không đồng bộ và cộng đồng lớn mạnh.
- NASA: Đây là một cơ quan độc lập của Chính phủ Liên bang Hoa Kỳ, chịu trách nhiệm về chương trình không gian dân sự và nghiên cứu hàng không, vũ trụ. NASA lựa chọn nền tảng này để hạn chế thời gian truy cập và xử lý các tác vụ có yêu cầu dữ liệu cao để giữ cho server hoạt động 24/7.
- Paypal: Với thời gian xây dựng cực nhanh và khả năng xử lý dữ liệu lớn, NodeJS là một nền tảng lý tưởng cho một hệ thống thanh toán trực tuyến toàn cầu như PayPal.
- Medium: Medium là một nền tảng xuất bản trực tuyến vô cùng phổ biến, đồng thời cũng lựa chọn NodeJS để xây dựng ứng dụng hướng dữ liệu và đơn giản hoá quá trình bảo trì server.
  Ngoài ra còn rất nhiều nền tảng lớn khác như: Twitter, Spotify, eBay, Reddit, Linkedin,…

![nodejs](img/nhung-ung-dung-cua-nodejs.webp)


## 💛 2. Giới thiệu TypeScript

### 🔥 TypeScript là gì

TypeScript là một ngôn ngữ lập trình mã nguồn mở do Microsoft phát triển, được xây dựng dựa trên JavaScript. Điểm nổi bật của TypeScript là nó thêm kiểu tĩnh (static typing) vào JavaScript, giúp các nhà phát triển viết mã rõ ràng và dễ bảo trì hơn.

Tài liệu chính thức: https://www.typescriptlang.org/

### 🔥 Lợi ích của TypeScript

TypeScript cung cấp kiểm tra kiểu tại thời điểm biên dịch, giúp phát hiện lỗi sớm và cải thiện chất lượng mã. Nó cũng hỗ trợ các tính năng lập trình hướng đối tượng như class, interface, và module một cách mạnh mẽ hơn JavaScript.

## 💛 3. Cài đặt môi trường

### 🔥 Cài đặt Node.js và npm

Truy cập vào trang web chính thức của Node.js (https://nodejs.org/) và tải xuống phiên bản phù hợp với hệ điều hành của bạn. Cài đặt Node.js cũng sẽ cài đặt npm, là trình quản lý gói cho JavaScript.

### 🔥 Cài đặt Công cụ biên tập Code

Có rất nhiều công cụ giúp bạn code với Nodejs

- Visual Studio Code (Khuyến nghị)
- Sublime Text

### 🔥 Tạo một dự án mới với Nodejs

#### 1. Tạo file `package.json`

Chạy lệnh 

```shell
npm init
# Hoặc để bỏ qua những thiết lập
ipm init -y
```


#### 2. Cài đặt TypeScript

Nhập lệnh

```shell
npm install typescript
```

Mở terminal và chạy lệnh trên để cài đặt TypeScript toàn cục trên máy tính của bạn. Điều này cho phép bạn sử dụng trình biên dịch TypeScript (`tsc`) từ bất kỳ nơi nào trong hệ thống của bạn.

#### Cấu hình biên dịch Typescript

TypeScript không thể thực thi trên môi trường trình duyệt do vậy bạn cần phải biên dịch thành Javascript thuần.

Để làm được vậy bạn cần cấu hình một số thông số nhất định để trình biên dịch hoạt động đúng.

Chạy lệnh sau để tạo file `tsconfig.json`

```shell
npx tsc --init
 ```
Hoặc bạn tạo file `tsconfig.json` ngay thư mục gốc với nội dung như sau:

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "rootDir": "./src",
    "outDir": "./dist",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}
```


## 4. Chạy file TypeScript

Tạo một file theo đường dẫn `src/index.ts`

với code như sau

```ts
console.log('Hello TypeScript');
```

Biên dịch mã TypeScript thành JavaScript bằng cách chạy lệnh sau:

```shell
npx tsc
```

Lệnh này sẽ tạo thư mục `dist` chứa các file JavaScript tương ứng với các file TypeScript trong thư mục `src`.

Chạy file `dist/index.js` bằng Node.js:

```shell
node dist/index.js
```

Bạn sẽ thấy trong cửa sổ  lệnh Termial:

```shell
Hello Typescript
```

Ví dụ về dùng Nodejs để khởi tạo một server

```ts
import http from 'node:http'

//create a server object:
http.createServer(function (req, res) {
  res.write('Hello World!'); //write a response to the client
  res.end(); //end the response
}).listen(8080); //the server object listens on port 8080
```

Khi đó bạn nhập vào trình duyệt `http://localhost:8080`. Bạn sẽ thấy dòng chữ: **Hello World!** xuất hiện.


## 💛 5. Guided for exercises

### Sử dụng `codesandbox.io`

Link: https://codesandbox.io

### Sử dụng các cộng cụ chat AI cho học code `ChatGPT`, `Copilot`

- https://chatgpt.com
- https://copilot.microsoft.com