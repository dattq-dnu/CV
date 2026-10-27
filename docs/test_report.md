# Báo cáo kiểm thử

## 1. Thông tin chung

- **Dự án:** CV Portfolio cá nhân — Trần Quốc Đạt.
- **Ngày kiểm thử:** 27/10/2026.
- **Phạm vi:** Kiểm tra trang `index.html`, stylesheet, điều hướng, nội dung, ảnh và khả năng triển khai của website tĩnh.
- **Môi trường kiểm thử:** Windows; mở trang cục bộ bằng trình duyệt tích hợp; không cần cài dependency.
- **Cách kiểm thử:** Mở trang thực tế, quan sát giao diện, kiểm tra DOM và trạng thái tải của tài nguyên bằng trình duyệt; đối chiếu cấu trúc HTML/CSS và hướng dẫn chạy trong README.
- **Ngoài phạm vi:** Không kiểm thử xâm nhập, không chạy kiểm thử tải, không đánh giá trên mọi trình duyệt/thiết bị; Docker và triển khai lên hosting chưa được chạy thực tế trong lần kiểm thử này.

## 2. Kết quả theo tiêu chí

### 2.1. Tính đúng đắn — Đạt có điều kiện

- Trang mở được và hiển thị đúng tiêu đề **“Trần Quốc Đạt · Frontend Developer”**.
- Các khu vực Giới thiệu, Kỹ năng, Dự án và Liên hệ có mặt trong trang; điều hướng nội bộ trỏ tới các ID tương ứng.
- Bốn thẻ dự án được hiển thị. Cả stylesheet và năm ảnh được tham chiếu đều tải thành công trong lần kiểm tra trên trình duyệt.
- Các thẻ dự án hiện là nội dung giới thiệu; Todo List và Weather Dashboard chưa phải ứng dụng có thể tương tác.
- **Minh chứng:** [Ảnh toàn trang trên desktop](screenshots/01-desktop-full.png).

### 2.2. UI/UX — Đạt có điều kiện

- Nội dung có phân cấp tiêu đề, thanh điều hướng, thẻ kỹ năng/dự án và khu vực liên hệ; header được giữ ở đầu trang khi cuộn.
- CSS có bố cục mobile-first, breakpoint tablet từ 768px và desktop từ 1280px; có trạng thái focus cho bàn phím và hỗ trợ `prefers-reduced-motion`.
- Ảnh chụp toàn trang cho thấy bố cục dự án hai cột tại kích thước viewport trình duyệt được ghi nhận là 1006 × 410 CSS px.
- Chưa xác nhận trực quan trên thiết bị thật hoặc viewport mobile CSS; không xem ảnh bị thu nhỏ/cắt là kết quả kiểm thử mobile.
- **Minh chứng:** [Ảnh toàn trang trên desktop](screenshots/01-desktop-full.png).

### 2.3. Khả năng vận hành — xử lý lỗi — Đạt có điều kiện

- Trang tĩnh mở được trực tiếp từ file cục bộ; không cần backend hoặc bước build để hiển thị nội dung.
- Các ảnh và stylesheet tải thành công trong lần chạy thử; trang có thể phục vụ bằng web server tĩnh theo hướng dẫn trong README.
- Dự án không có luồng gọi API, biểu mẫu gửi dữ liệu hoặc logic backend để kiểm thử tình huống lỗi nghiệp vụ. Chưa có cơ chế hiển thị thông báo thay thế khi ảnh không tải được.
- **Minh chứng:** [Ảnh toàn trang trên desktop](screenshots/01-desktop-full.png) và [ảnh khu vực liên hệ](screenshots/02-contact-section.png).

### 2.4. Bảo mật — Phù hợp với phạm vi trang tĩnh; chưa kiểm thử bảo mật chuyên sâu

- Trong phạm vi mã nguồn đã xem, trang chỉ gồm HTML/CSS tĩnh; không thấy JavaScript, endpoint backend, xử lý dữ liệu nhập, tài khoản hay bí mật cấu hình.
- Không có form nhập liệu hoặc chức năng xác thực để đánh giá kiểm thử đầu vào.
- Chưa chạy công cụ quét lỗ hổng, kiểm thử HTTP headers, cấu hình máy chủ triển khai hoặc rà soát bảo mật chuyên sâu. Kết quả này không phải chứng nhận website an toàn.
- Email hiển thị là địa chỉ mẫu; cần thay bằng thông tin đã được xác nhận trước khi công khai.

### 2.5. Chất lượng mã nguồn — Đạt

- HTML tách khỏi CSS; trang sử dụng phần tử có ngữ nghĩa, khai báo ngôn ngữ, metadata, nhãn thay thế ảnh và nhãn điều hướng.
- CSS sử dụng custom properties, Flexbox, CSS Grid, quy tắc mobile-first và media queries; không cần thư viện ngoài.
- Chưa có bộ test tự động, cấu hình lint/format hoặc quy trình CI trong phạm vi được kiểm tra.

### 2.6. Khả năng triển khai — Đạt có điều kiện

- Đây là website tĩnh, có thể phân phối các file HTML, CSS và ảnh qua hosting tĩnh hoặc web server như Nginx.
- README có hướng dẫn chạy cục bộ trên Windows, macOS, Linux và hướng dẫn Docker dùng image Nginx.
- Chưa thực hiện build, chạy container Docker hoặc triển khai lên hosting trong lần kiểm thử này; các thao tác đó cần được xác nhận riêng trước khi phát hành.
- Cần cập nhật email mẫu và các URL giữ chỗ trước khi đưa website lên môi trường công khai.

## 3. Hạn chế và khuyến nghị

1. Thay email mẫu và thay các liên kết `#` của dự án, GitHub, TikTok bằng URL thực tế.
2. Nếu dự án Todo List hoặc Weather Dashboard được mô tả như chức năng đã hoàn thiện, bổ sung ứng dụng tương tác tương ứng; hiện tại các mục này chỉ là thẻ giới thiệu.
3. Kiểm tra giao diện bằng viewport mobile CSS thực và trên trình duyệt/thiết bị mục tiêu trước khi nghiệm thu.
4. Chạy thử quy trình Docker hoặc hosting thực tế trước khi xác nhận khả năng triển khai đầu-cuối.
5. Nếu website được mở rộng với backend, API hoặc biểu mẫu, bổ sung kiểm thử chức năng và bảo mật phù hợp với các luồng mới.

## 4. Kết luận

Website đạt yêu cầu cơ bản của một portfolio tĩnh trong lần kiểm thử cục bộ: trang mở được, nội dung chính và tài nguyên hiển thị. UI responsive được hỗ trợ trong mã CSS nhưng chưa được xác nhận bằng kiểm thử viewport mobile thực. Chưa đủ cơ sở để kết luận về triển khai Docker/hosting hoặc bảo mật chuyên sâu. Có thể dùng cho mục đích trình diễn sau khi cập nhật thông tin liên hệ và các URL giữ chỗ.
