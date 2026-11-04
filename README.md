# Bài 1 : Xử lý cảnh báo đăng nhập giả mạo GitHub
## 1. Xác định ký tự lạ trong URL
URL được cung cấp: `https://githúb.com/login`

Ký tự đáng ngờ là chữ `ú` trong từ `githúb`.
- URL GitHub chính thức: `https://github.com/login`
- URL giả mạo: `https://githúb.com/login`

**Giải thích:**

Chữ `ú` là ký tự Unicode, khác với chữ `u` thông thường trong bảng chữ cái Latin ASCII.

Kẻ tấn công lợi dụng sự tương đồng về hình thức giữa các ký tự để tạo ra tên miền giả có giao diện gần giống trang web thật. Người dùng có thể nhìn lướt qua và nhầm tưởng mình đang truy cập GitHub chính thức.

Đây là hình thức tấn công giả mạo tên miền bằng ký tự tương đồng, thường được gọi là Homograph Attack. Mục đích có thể là đánh cắp tài khoản và mật khẩu đăng nhập.
## 2. Quy trình kiểm tra URL trước khi nhập Master Password
### Bước 1: Kiểm tra bằng mắt thường
- Đọc kỹ từng ký tự trong tên miền.
- Chú ý những ký tự Unicode bất thường như  `ú`, `а`, `е` hoặc những ký tự trông giống chữ cái thông thường.
- Kiểm tra chính xác tên miền, không chỉ nhìn vào logo hoặc giao diện trang web.
- Không đăng nhập nếu URL có dấu hiệu đáng ngờ.
### Bước 2: Kiểm tra tên miền chính thức
- GitHub chính thức sử dụng tên miền `github.com`.
- Không đăng nhập thông qua đường link được gửi bất ngờ trong email hoặc tin nhắn.
- Tự nhập địa chỉ website chính thức vào trình duyệt để truy cập.
### Bước 3: Sử dụng công cụ hỗ trợ
**Có thể sử dụng:**
- Punycode: Kiểm tra tên miền Unicode đã được chuyển đổi sang dạng ASCII. Tên miền đáng ngờ có thể hiển thị dưới dạng bắt đầu bằng `xn--`.
- Google Safe Browsing: Kiểm tra cảnh báo về website có dấu hiệu lừa đảo hoặc không an toàn.
- Trình duyệt Chrome: Chú ý cảnh báo bảo mật và cách trình duyệt hiển thị tên miền quốc tế hóa (IDN). 
### Bước 4: Đưa ra quyết định
- Nếu tên miền không chính xác hoặc có ký tự bất thường: Không đăng nhập.
- Nếu nhận được yêu cầu xác minh tài khoản bất ngờ: Không vội làm theo.
- Chỉ nhập Master Password khi đã xác minh chắc chắn website là trang chính thức.
