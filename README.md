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


Dịch vụ Xác thực bằng Cookie
Cài đặt
lone repository

Cài đặt các dependencies: npm install
Đảm bảo MongoDB đang chạy trên mongodb://127.0.0.1:27017

Khởi động server:node cookie_auth.js
Server sẽ chạy trên http://localhost:3001
1. Đăng nhập
POST http://localhost:3001/login

Body (JSON):
{
  "username": "admin",
  "password": "12345"
}
![alt text](public/img/cookie.png)
![alt text](public/img/cookie1.png)
2. Trang hồ sơ (bảo mật)
GET http://localhost:3001/profile

Yêu cầu: Phải có cookie xác thực hợp lệ từ đăng nhập

![alt text](public/img/cookie2.png)

Bước 3: Đăng xuất
ạo request mới, phương thức POST

URL: http://localhost:3001/logout
![alt text](public/img/cookie3.png)


![alt text](public/img/cookie4.png)