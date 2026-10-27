# CV Portfolio cá nhân

Trang portfolio/CV cá nhân giới thiệu Trần Quốc Đạt, định hướng Frontend Developer. Dự án được xây dựng dưới dạng website tĩnh bằng HTML và CSS, có thể mở trực tiếp bằng trình duyệt hoặc phục vụ qua một web server tĩnh.

## Chức năng

- Giới thiệu cá nhân và định hướng nghề nghiệp.
- Hiển thị các kỹ năng dưới dạng thẻ.
- Trình bày một số dự án mẫu: Landing Page Sản Phẩm, Todo List, Weather Dashboard và Blog Cá Nhân.
- Cung cấp khu vực liên hệ và điều hướng nhanh tới từng phần trên trang.
- Bố cục responsive theo hướng mobile-first, sử dụng một cột trên màn hình nhỏ, hai cột trên tablet và ba cột trên desktop.
- Hỗ trợ điều hướng bằng bàn phím, trạng thái focus dễ nhận biết và tùy chọn giảm chuyển động của hệ điều hành.

> Đây là trang portfolio tĩnh. Các thẻ dự án hiện dùng nội dung minh họa; dự án này chưa tích hợp ứng dụng Todo, API thời tiết, biểu mẫu gửi liên hệ hay trang chi tiết dự án.

## Công nghệ

- HTML5: cấu trúc nội dung có ngữ nghĩa và metadata.
- CSS3: giao diện, custom properties, Flexbox, CSS Grid, media queries và responsive design.
- Không sử dụng framework, thư viện JavaScript, backend hoặc cơ sở dữ liệu.

## Cấu trúc thư mục

```text
.
├── index.html
├── REDME.md
└── assets/
    ├── css/
    │   └── styles.css
    └── img/
        └── ... ảnh đại diện và ảnh minh họa ...
```

## Yêu cầu môi trường

### Chạy trực tiếp

- Windows, macOS hoặc Linux.
- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.
- Không cần cài Node.js, npm hay bất kỳ thư viện dự án nào.

### Chạy qua web server

- Python 3 (để dùng máy chủ HTTP tích hợp sẵn) **hoặc** Docker Engine/Desktop.
- Kết nối Internet chỉ cần thiết lần đầu chạy Docker nếu máy chưa có image `nginx:alpine`.

## Cài đặt

Tải hoặc clone mã nguồn về máy, sau đó mở terminal tại thư mục dự án — thư mục có `index.html`.

```bash
git clone https://github.com/dattq-dnu/CV.git
cd CV
```

Nếu đã có mã nguồn, bỏ qua bước clone và chuyển terminal tới đúng thư mục chứa `index.html`. Không cần cài đặt dependency.

## Cấu hình và tùy chỉnh

Dự án không có file cấu hình môi trường, biến `.env` hay bước build.

- Sửa nội dung, thông tin cá nhân, kỹ năng, dự án và liên hệ trong `index.html`.
- Sửa màu sắc, kiểu chữ, khoảng cách và breakpoint responsive trong `assets/css/styles.css`.
- Thay ảnh trong `assets/img/`; cập nhật các đường dẫn tương ứng trong `index.html` khi đổi tên hoặc vị trí ảnh.
- Trước khi công khai website, hãy thay email mẫu `tranquocdat@example.com` và kiểm tra/cập nhật các đường dẫn liên hệ, dự án theo thông tin thực tế.
- Các liên kết “Xem chi tiết” hiện là liên kết giữ chỗ (`#`); hãy thay bằng URL dự án thật nếu có.

## Chạy thử

### Windows

**Cách 1 — mở trực tiếp:** dùng File Explorer mở `index.html` bằng trình duyệt.

**Cách 2 — chạy web server bằng Python:** mở PowerShell tại thư mục dự án:

```powershell
py -m http.server 8000
```

Nếu lệnh `py` không có trên máy, thử:

```powershell
python -m http.server 8000
```

Mở [http://localhost:8000](http://localhost:8000). Nhấn `Ctrl+C` trong PowerShell để dừng server.

### macOS

Mở Terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

Truy cập [http://localhost:8000](http://localhost:8000). Nhấn `Ctrl+C` để dừng server.

### Linux

Mở terminal tại thư mục dự án và chạy:

```bash
python3 -m http.server 8000
```

Truy cập [http://localhost:8000](http://localhost:8000). Nhấn `Ctrl+C` để dừng server.

> Nếu cổng `8000` đang được sử dụng, thay `8000` trong lệnh bằng một cổng khác, ví dụ `8080`, rồi truy cập đúng cổng đó.

## Chạy bằng Docker

Yêu cầu đã cài Docker Desktop (Windows/macOS) hoặc Docker Engine (Linux) và Docker daemon đang hoạt động. Không cần Dockerfile: container Nginx sẽ phục vụ trực tiếp các file hiện có trong thư mục dự án.

### Windows PowerShell

Chạy tại thư mục dự án:

```powershell
docker run --rm -d --name cv-portfolio -p 8080:80 --mount "type=bind,source=$($PWD.Path),target=/usr/share/nginx/html,readonly" nginx:alpine
```

### macOS và Linux

Chạy tại thư mục dự án:

```bash
docker run --rm -d --name cv-portfolio -p 8080:80 --mount "type=bind,source=$(pwd),target=/usr/share/nginx/html,readonly" nginx:alpine
```

Sau khi container khởi động, mở [http://localhost:8080](http://localhost:8080). Khi chỉnh sửa file trong dự án, tải lại trang để xem thay đổi. Dừng container bằng:

```bash
docker stop cv-portfolio
```

Nếu cổng `8080` đã được sử dụng, đổi phần `8080:80` thành cổng trống khác, chẳng hạn `8081:80`, rồi mở cổng tương ứng trên trình duyệt.

## Thông tin liên hệ

Thông tin đang được hiển thị trong trang:

- **Tên:** Trần Quốc Đạt
- **Email:** tranquocdat@example.com (địa chỉ mẫu, cần xác nhận/cập nhật trước khi sử dụng)
- **GitHub:** [github.com/dattq-dnu](https://github.com/dattq-dnu)
- **TikTok:** [@tqd_66208](https://www.tiktok.com/@tqd_66208)

Để cập nhật thông tin liên hệ trên website, chỉnh sửa các mục tương ứng trong phần `Liên hệ` của `index.html`.