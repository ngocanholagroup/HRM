# Hệ Thống Quản Lý Nhân Sự Hola Group (HRM)

> **Mô tả:** Giải pháp quản lý nhân sự chuyên sâu được thiết kế riêng cho hệ sinh thái của Hola Group, hỗ trợ quản lý vận hành sản xuất và tích hợp công nghệ chấm công thông minh qua mã QR Code.

## 🌐 Liên kết dự án
* **Hệ thống thực tế (Live Demo):** [https://erpmini.cloud](https://erpmini.cloud)
* **Theo dõi tiến độ dự án:** [Google Spreadsheet](https://docs.google.com/spreadsheets/d/1Ouz-jxjV6gg4vwenk94TxB3wv66ZlYrlJ33Hpq8s_h8/edit?gid=0#gid=0)

---

## 👥 Đơn vị vận hành và Phát triển

| Tổ chức | Vai trò | Trách nhiệm |
| :--- | :--- | :--- |
| **Hola Group** | Đơn vị chủ quản | Định hướng và vận hành hệ thống |
| **HRM Technical Team** | Đội ngũ kỹ thuật | Phát triển Fullstack (Angular & Spring Boot) |

---

## 🔐 Tài khoản truy cập hệ thống (Demo)

| Quyền hạn | Tên đăng nhập | Mật khẩu |
| :--- | :--- | :--- |
| **Quản trị viên (Admin)** | `admin` | `admin123` |
| **Quản lý nhân sự (HR)** | `hr_manager` | `hr123` |
| **Quản lý bộ phận (Lead)** | `inan_lead` | `ql123` |
| **Nhân viên** | `000050` | `123123` |

---

## ⚙️ Quy trình cài đặt và Triển khai

### Bước 1: Đóng gói Giao diện (Frontend - Angular)
1.  Truy cập vào thư mục `frontend`, mở terminal và thực hiện:
    ```bash
    npm i
    ng build
    ```
2.  Sau khi quá trình build hoàn tất, truy cập thư mục `/dist/Fe_luanvan`.
3.  Sao chép toàn bộ nội dung trong thư mục con `/browser` ra thư mục gốc của bản build.
4.  Chuyển toàn bộ dữ liệu này vào thư mục tài nguyên của Backend tại:
    `\backend\src\main\resources\static`

### Bước 2: Cấu hình Hệ thống (Backend - Spring Boot)
Chỉnh sửa tệp `application.properties` tại đường dẫn:
`\backend\src\main\resources\application.properties`

Cập nhật các thông số môi trường sau:

```properties
# Cấu hình Server
server.port=8080
server.address=0.0.0.0

# Cấu hình Cơ sở dữ liệu (MySQL)
spring.datasource.url=jdbc:mysql://localhost:3306/manaplastic_hr
spring.datasource.username=root
spring.datasource.password=your_password_here

# Cấu hình hệ thống gửi Email (SMTP)
spring.mail.username=contact@holagroup.com
spring.mail.password=your_app_password