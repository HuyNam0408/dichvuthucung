
# Pet Care (PHP + MySQL)

## Cài đặt nhanh (XAMPP / WAMP)
1. Tạo DB:
   - Mở phpMyAdmin → tab SQL → dán nội dung `schema.sql`.
2. Copy toàn bộ thư mục `petcare_php` vào `htdocs` (XAMPP) hoặc `www` (WAMP).
3. Mở `includes/db.php` và sửa user/pass/host nếu cần.
4. Đặt ảnh hero vào `assets/img/hero-dog.jpg` (tuỳ ý).
5. Truy cập `http://localhost/petcare_php/`

**Tài khoản demo**: `demo@petcare.local` / `123456`

## Cấu trúc
- index.php — trang chủ kiểu "Pet Care"
- login.php, register.php, logout.php — đăng nhập hiện đại (password_hash + prepared statements)
- schedule.php — đặt lịch (chỉ khi đã đăng nhập)
- dashboard.php — xem lịch hẹn của bạn
- includes/db.php — kết nối MySQL
- includes/auth.php — session + guard
- assets/css/style.css — giao diện
- schema.sql — lệnh tạo bảng + dữ liệu mẫu

## Bảo mật
- Mọi truy vấn SQL đều dùng `prepare/bind`.
- Mật khẩu lưu bằng `password_hash()` và kiểm tra `password_verify()`.
- Session được khởi tạo sớm trong `auth.php`.
