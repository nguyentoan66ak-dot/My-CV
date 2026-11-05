# Portfolio CV - Nguyễn Huy Toàn

## 1. Giới thiệu

Website portfolio cá nhân giới thiệu Nguyễn Huy Toàn, định hướng Công nghệ thông tin và Frontend. Dự án được xây dựng dưới dạng trang web tĩnh để trình bày thông tin cá nhân, kỹ năng, các dự án tiêu biểu và cách liên hệ.

## 2. Chức năng

- Hiển thị phần giới thiệu và ảnh đại diện.
- Trình bày danh sách kỹ năng và các dự án mẫu.
- Điều hướng nhanh đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Cung cấp liên kết email để liên hệ.
- Bố cục responsive cho màn hình điện thoại, máy tính bảng và máy tính.
- Sử dụng ảnh minh họa được tải từ các địa chỉ bên ngoài; cần kết nối Internet để tải các ảnh này.

## 3. Công nghệ sử dụng

- HTML5: cấu trúc và nội dung trang.
- CSS3: giao diện, responsive, Flexbox và CSS Grid.
- Trình duyệt web hiện đại để xem trang.
- Docker và Nginx (tùy chọn) để phục vụ trang web trong container.

Dự án hiện không sử dụng JavaScript, framework frontend, cơ sở dữ liệu hoặc công cụ build.

## 4. Cấu trúc thư mục

```text
.
├── index.html
├── README.md
└── assets/
	├── css/
	│   └── styles.css
	└── img/
```

## 5. Yêu cầu môi trường

### Chạy trực tiếp hoặc dùng máy chủ tĩnh

- Windows, macOS hoặc Linux.
- Trình duyệt hiện đại như Chrome, Edge, Firefox hoặc Safari.
- Không cần cài Node.js hay gói phụ thuộc.
- Python 3 chỉ cần thiết nếu muốn chạy máy chủ HTTP cục bộ thay vì mở trực tiếp file HTML.

### Chạy bằng Docker

- Docker Engine trên Linux, hoặc Docker Desktop trên Windows/macOS.
- Kết nối Internet lần đầu để tải image `nginx:alpine`.

## 6. Cài đặt mã nguồn

Đặt các tệp của dự án vào cùng một thư mục, giữ nguyên cấu trúc `assets/css/styles.css` như ở trên. Nếu dự án được lấy từ Git, mở Terminal tại thư mục muốn lưu và chạy:

```bash
git clone <URL_REPOSITORY>
cd <TEN_THU_MUC_DU_AN>
```

Thay `<URL_REPOSITORY>` và `<TEN_THU_MUC_DU_AN>` bằng địa chỉ repository và tên thư mục thực tế. Nếu bạn đã có thư mục dự án, chỉ cần mở Terminal hoặc PowerShell tại thư mục đó.

## 7. Cấu hình

Không cần tạo file `.env` hay thiết lập biến môi trường.

- Nội dung, tiêu đề trang, mô tả và thông tin liên hệ: chỉnh sửa trong `index.html`.
- Màu sắc, kiểu chữ và bố cục: chỉnh sửa các biến CSS trong `:root` và các quy tắc trong `assets/css/styles.css`.
- Ảnh đại diện và ảnh dự án hiện tham chiếu đến URL bên ngoài. Có thể thay URL trong `index.html` bằng ảnh của bạn; thư mục `assets/img/` có thể dùng để lưu ảnh cục bộ.
- Khi đổi đường dẫn ảnh hoặc CSS, giữ đường dẫn tương đối hợp lệ để trang hoạt động khi chạy bằng file, máy chủ tĩnh hoặc Docker.

## 8. Chạy thử

### Windows

**Mở trực tiếp:** dùng File Explorer mở `index.html`, hoặc chạy lệnh PowerShell sau tại thư mục dự án:

```powershell
Start-Process .\index.html
```

**Chạy máy chủ HTTP bằng Python:**

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có, thử `python -m http.server 8000`. Mở [http://localhost:8000](http://localhost:8000) trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở Terminal tại thư mục dự án và chạy:

```bash
open index.html
```

Hoặc chạy máy chủ HTTP:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở Terminal tại thư mục dự án và chạy:

```bash
xdg-open index.html
```

Hoặc chạy máy chủ HTTP:

```bash
python3 -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Dừng máy chủ bằng `Ctrl+C`.

### Docker

Các lệnh sau chạy Nginx và gắn thư mục dự án vào thư mục phục vụ web. Không cần tạo Dockerfile.

**Windows PowerShell** (chạy tại thư mục dự án):

```powershell
docker run --rm -d --name portfolio -p 8080:80 --mount "type=bind,source=$((Get-Location).Path),target=/usr/share/nginx/html,readonly" nginx:alpine
```

**Windows Command Prompt** (chạy tại thư mục dự án):

```bat
docker run --rm -d --name portfolio -p 8080:80 -v "%cd%:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS hoặc Linux** (chạy tại thư mục dự án):

```bash
docker run --rm -d --name portfolio -p 8080:80 --mount "type=bind,source=$(pwd),target=/usr/share/nginx/html,readonly" nginx:alpine
```

Sau khi container khởi động, mở [http://localhost:8080](http://localhost:8080). Dừng container bằng:

```bash
docker stop portfolio
```

Nếu cổng `8080` đang được sử dụng, đổi phần `-p 8080:80` thành một cổng trống khác, ví dụ `-p 8081:80`, rồi truy cập cổng tương ứng. Đảm bảo Docker đang chạy và container có quyền đọc thư mục dự án.

## 9. Thông tin liên hệ

- **Tác giả:** Nguyễn Huy Toàn
- **Email:** [nguyentoan07ak@gmail.com](mailto:nguyentoan07ak@gmail.com)
- **Số điện thoại:** 0335171585
