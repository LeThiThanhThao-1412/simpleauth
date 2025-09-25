Yêu cầu hệ thống
Đã cài đặt Node.js

Postman để kiểm thử API

Cài đặt
Clone repository này

Cài đặt dependencies: npm install
Chạy Máy chủ: node basic_auth.js
Máy chủ sẽ chạy trên: http://localhost:3000
Kiểm thử Route Công khai
Mở Postman

Tạo request GET mới đến: http://localhost:3000/
![alt text](<public/img/Ảnh chụp màn hình 2025-09-25 190922.png>)
Kiểm thử Route Được bảo vệ với Basic Auth
Phương pháp 1: Sử dụng Tab Auth của Postman
Tạo request GET mới đến: http://localhost:3000/secure
![alt text](<public/img/Ảnh chụp màn hình 2025-09-25 191025.png>)
Tạo request GET mới đến: http://localhost:3000/secure

Chuyển đến tab Headers

Thêm header mới:

Key: Authorization

Value: Basic YWRtaW46MTIzNDU= (đây là phiên bản được mã hóa base64 của admin:12345)

Gửi request

![alt text](public/img/image.png)


Không có Header Xác thực (401 Unauthorized)


![alt text](public/img/image-1.png)

Thông tin Đăng nhập Không hợp lệ (403 Forbidden)
![alt text](public/img/image-2.png)
