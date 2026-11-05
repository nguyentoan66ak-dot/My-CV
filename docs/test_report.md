# BÁO CÁO KIỂM THỬ PHẦN MỀM

## 1. Thông tin chung

| Thông tin | Chi tiết |
|---|---|
| Tên dự án | Portfolio CV - Nguyễn Huy Toàn |
| Phiên bản | v1.0 |
| Ngày kiểm thử | 05/11/2026 |
| Người thực hiện | QA/QC - rà soát mã nguồn và kiểm tra trực quan bằng trình duyệt |
| Phạm vi | Rà soát `index.html`, `assets/css/styles.css`, `README.md`, tài liệu phát hành và ảnh Responsive trong `docs/screenshots/` |
| Phương pháp | Rà soát mã nguồn/tài liệu và chụp trang trong trình duyệt ở ba viewport; chưa thực hiện kiểm thử đa trình duyệt hoặc môi trường Docker |

### Quy ước trạng thái

- **Đạt:** Có đủ căn cứ xác nhận hạng mục đáp ứng yêu cầu trong phạm vi đã kiểm tra.
- **Chưa đạt:** Đã phát hiện lỗi hoặc thiếu sót ảnh hưởng trực tiếp đến yêu cầu.
- **Cần cải thiện:** Chưa có đủ bằng chứng để kết luận, cần kiểm thử thêm hoặc còn rủi ro cần xử lý.

## 2. Bảng tổng quan trạng thái

| STT | Nhóm tiêu chí | Trạng thái | Tóm tắt |
|---:|---|---|---|
| 1 | Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng | **Chưa đạt** | Có mục liên hệ sai cấu trúc HTML; liên kết chi tiết dự án chưa dẫn đến nội dung thực. |
| 2 | Giao diện, trải nghiệm người dùng và khả năng tương thích | **Chưa đạt** | Ảnh chụp ở cả ba viewport cho thấy chip kỹ năng và lưới dự án tràn/cắt theo chiều ngang. |
| 3 | Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản | **Cần cải thiện** | Đã mở trang để chụp ảnh; chưa kiểm tra lỗi tải tài nguyên/Console hoặc đo hiệu năng. |
| 4 | Bảo mật, quản lý cấu hình và dữ liệu | **Cần cải thiện** | Không thấy cấu hình bí mật trong phạm vi rà soát; số điện thoại cá nhân được công khai và ảnh phụ thuộc nguồn ngoài. |
| 5 | Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao | **Chưa đạt** | Có lỗi đánh dấu HTML; cần làm rõ các mục dự án minh họa so với phạm vi website portfolio tĩnh. |
| 6 | Khả năng triển khai, kiểm thử và cung cấp minh chứng | **Cần cải thiện** | README có hướng dẫn chạy tĩnh/Docker nhưng chưa có bằng chứng các bước đã được thực thi thành công. |

## 3. Kết quả chi tiết

### 3.1. Tính đúng đắn và mức độ đáp ứng yêu cầu chức năng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Hiển thị các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ | Đạt | Các section và ID tương ứng có trong `index.html`; chỉ xác nhận qua mã nguồn, chưa kiểm tra trên trình duyệt. |
| Điều hướng đến các section trong trang | Đạt | Menu sử dụng liên kết `#about`, `#skills`, `#projects`, `#contact`, khớp ID trong tài liệu HTML. |
| Liên kết email | Đạt | Có liên kết `mailto:nguyentoan07ak@gmail.com` trong phần Liên hệ. |
| Hiển thị thông tin số điện thoại | Chưa đạt | Thẻ `span` có thuộc tính `class` thiếu dấu nháy đóng; thẻ liên kết dùng `mailto:` cho số điện thoại và thuộc tính `href` không hợp lệ. Cần sửa HTML và dùng `tel:` nếu cần gọi điện. |
| Liên kết xem chi tiết dự án | Chưa đạt | Các thẻ dự án đang dùng `href="#"`, không mở trang hoặc nội dung chi tiết. Cần thay bằng URL hợp lệ hoặc bỏ liên kết nếu dự án chưa có trang đích. |
| Nội dung mô tả phù hợp với chức năng thật | Cần cải thiện | Các thẻ Todo List/Weather có thể là dự án minh họa, không nhất thiết là tính năng của portfolio. Cần xác nhận trang đích/demo tương ứng và diễn đạt rõ phạm vi để tránh người xem hiểu nhầm. |

### 3.2. Giao diện, trải nghiệm người dùng và khả năng tương thích

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Bố cục responsive theo kích thước màn hình | Chưa đạt | Đã chụp mobile 390×844, tablet 768×1024 và desktop 1440×900. Chip kỹ năng và thẻ/lưới dự án vượt chiều rộng khả dụng, bị cắt ở mép viewport. Xem minh chứng bên dưới. |
| Điều hướng và thao tác bằng bàn phím | Cần cải thiện | Có quy tắc `:focus-visible`; cần chạy thử thứ tự Tab, độ rõ focus và khả năng truy cập các liên kết. |
| Khả năng đọc và tương phản màu sắc | Cần cải thiện | Màu chữ/nền được khai báo qua CSS variables nhưng chưa đo tương phản WCAG hoặc xác nhận trên giao diện thực. |
| Ảnh đại diện và ảnh dự án | Cần cải thiện | Ảnh dùng URL bên ngoài; chưa xác minh trạng thái HTTP, hiển thị khi mất mạng hoặc cách xử lý ảnh lỗi. |
| Tương thích Chrome, Edge, Firefox và Safari | Cần cải thiện | Chưa thực hiện kiểm thử đa trình duyệt. |

#### Minh chứng ảnh chụp Responsive

Ảnh được chụp trực tiếp từ trang hiện trạng bằng trình duyệt, không chỉnh sửa nội dung ảnh. Các ảnh ghi nhận bố cục tại viewport tương ứng và đồng thời thể hiện lỗi tràn/cắt ngang cần khắc phục.

| Thiết bị | Kích thước viewport | Minh chứng |
|---|---:|---|
| Mobile | 390 × 844 | [responsive-mobile.png](screenshots/responsive-mobile.png) |
| Tablet | 768 × 1024 | [responsive-tablet.png](screenshots/responsive-tablet.png) |
| Desktop | 1440 × 900 | [responsive-desktop.png](screenshots/responsive-desktop.png) |

### 3.3. Khả năng vận hành, xử lý lỗi và hiệu năng cơ bản

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Mở trang bằng file HTML hoặc máy chủ tĩnh | Cần cải thiện | README có hướng dẫn, nhưng chưa thực thi để xác nhận trang và CSS tải thành công. |
| Tải tài nguyên khi ảnh ngoài không truy cập được | Cần cải thiện | Chưa kiểm thử mất mạng/URL ảnh lỗi; các ảnh hiện phụ thuộc dịch vụ bên ngoài. |
| Không phát sinh lỗi HTML/CSS hoặc lỗi trình duyệt | Chưa đạt | Rà soát mã nguồn phát hiện khai báo đầu tài liệu không đúng dạng `<!DOCTYPE html>` và markup mục số điện thoại không hợp lệ; chưa chạy validator hoặc kiểm tra Console. |
| Hiệu năng tải trang cơ bản | Cần cải thiện | Chưa đo thời gian tải, kích thước ảnh hoặc chỉ số hiệu năng; ảnh ngoài chưa có cơ chế tải chậm được xác nhận. |

### 3.4. Bảo mật, quản lý cấu hình và dữ liệu

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Thông tin bí mật/khóa truy cập trong mã nguồn | Đạt | Không thấy thông tin xác thực hoặc khóa API trong các tệp được rà soát; phạm vi là website tĩnh và kiểm tra mã nguồn thủ công. |
| Quản lý cấu hình môi trường | Đạt | README xác nhận không cần `.env` hay biến môi trường cho phiên bản hiện tại. |
| Bảo vệ dữ liệu cá nhân được công khai | Cần cải thiện | README hiển thị số điện thoại cá nhân. Xác nhận chủ sở hữu đồng ý công khai trước khi bàn giao/phát hành. |
| Phụ thuộc tài nguyên bên ngoài | Cần cải thiện | Ảnh được tải từ domain bên ngoài; cần cân nhắc lưu ảnh trong `assets/img/` để giảm phụ thuộc và kiểm soát nguồn. |
| HTTPS và cấu hình máy chủ triển khai | Cần cải thiện | Chưa có cấu hình máy chủ/hosting thực tế để đánh giá HTTPS, header bảo mật hoặc chính sách triển khai. |

### 3.5. Chất lượng mã nguồn, cấu trúc repository và tài liệu bàn giao

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Cấu trúc HTML và khả năng phân tích cú pháp | Chưa đạt | `index.html` bắt đầu bằng `DOCTYPE html>` thay vì `<!DOCTYPE html>`; khu vực số điện thoại có dấu nháy/thuộc tính không hợp lệ. |
| Tổ chức CSS và bố cục responsive | Đạt | CSS tách riêng tại `assets/css/styles.css`, sử dụng custom properties, Flexbox/Grid và media queries; chưa đánh giá chất lượng hiển thị runtime. |
| Tính nhất quán giữa nội dung và tài liệu | Cần cải thiện | README mô tả portfolio là trang tĩnh không dùng JavaScript; phần Kỹ năng và các thẻ dự án nhắc đến JavaScript/API. Cần xác nhận đây là kỹ năng/dự án minh họa và bổ sung liên kết demo hoặc ghi chú phù hợp. |
| Hướng dẫn cài đặt và chạy | Đạt | README có hướng dẫn mở trực tiếp, máy chủ Python và Docker/Nginx; chưa xác minh lệnh chạy trong môi trường sạch. |
| Tài liệu release note và nhật ký thay đổi | Đạt | Có `docs/RELEASENOTE.md` và `docs/AI_LOG.md`; trạng thái nội dung được ghi nhận theo tài liệu hiện có. |

### 3.6. Khả năng triển khai, kiểm thử và cung cấp minh chứng

| Hạng mục kiểm tra | Trạng thái | Ghi chú/Minh chứng |
|---|---|---|
| Triển khai bằng máy chủ HTTP tĩnh | Cần cải thiện | Có lệnh chạy trong README; chưa có log hoặc ảnh chụp chứng minh trang hoạt động. |
| Triển khai bằng Docker/Nginx | Cần cải thiện | README hướng dẫn bind mount thư mục vào Nginx; chưa xác nhận Docker khởi động, cổng truy cập hoặc khả năng phục vụ CSS/ảnh. |
| Bộ kiểm thử hồi quy và kết quả thực thi | Cần cải thiện | Chưa có test tự động hoặc biên bản chạy test trong phạm vi kiểm thử này. |
| Minh chứng kiểm thử bàn giao | Cần cải thiện | Đã có ba ảnh chụp Responsive liên kết ở mục 3.2; cần bổ sung kết quả đa trình duyệt, kiểm tra Console và log/ảnh triển khai sau khi chạy thực tế. |

## 4. Đánh giá tổng kết và đề xuất

### Nhận định chung

**Chưa khuyến nghị bàn giao như một bản phát hành đã được nghiệm thu.** Rà soát tĩnh xác nhận một số lỗi HTML ở khai báo DOCTYPE và mục số điện thoại, cùng các liên kết chi tiết dự án chưa có đích thực. Ngoài ra, chưa có kết quả kiểm thử trực tiếp trên trình duyệt, thiết bị hoặc Docker; do đó chưa thể kết luận về giao diện runtime, tương thích và khả năng triển khai.

### Vấn đề cần xử lý trước khi bàn giao

1. Sửa khai báo DOCTYPE và markup/liên kết số điện thoại trong `index.html`; chạy HTML validator sau khi sửa.
2. Thay các liên kết `href="#"` bằng trang đích thật hoặc trình bày nội dung dự án không như liên kết.
3. Đồng bộ nội dung kỹ năng và mô tả dự án với chức năng thực tế, đặc biệt là các nội dung JavaScript, Todo List và Weather API.
4. Chạy kiểm thử thủ công trên các viewport di động, máy tính bảng và desktop; kiểm tra điều hướng bàn phím, tương phản, ảnh lỗi và Console trình duyệt.
5. Chạy thử ít nhất một phương thức triển khai (máy chủ tĩnh hoặc Docker/Nginx), lưu lại URL/kết quả và ảnh chụp làm minh chứng.
6. Xác nhận việc công khai số điện thoại; cân nhắc chuyển ảnh ngoài vào `assets/img/` nếu cần hoạt động ổn định khi nguồn ảnh bên ngoài không khả dụng.

### Điều kiện đề xuất để nghiệm thu lại

- Các lỗi được đánh dấu **Chưa đạt** đã được xử lý và kiểm tra lại.
- Hoàn tất kiểm thử trình duyệt/viewport và xác nhận các liên kết, tài nguyên hoạt động.
- Có bằng chứng triển khai thành công và cập nhật trạng thái kiểm thử dựa trên kết quả thực thi.

## 5. Giới hạn của báo cáo

Báo cáo được lập từ rà soát mã nguồn và tài liệu tại ngày kiểm thử. Không bao gồm kiểm thử runtime, kiểm thử tải, kiểm thử bảo mật chuyên sâu, xác minh nội dung cá nhân hoặc xác nhận Docker/hosting. Các mục chưa có bằng chứng thực thi được đánh dấu **Cần cải thiện**, không được xem là đã đạt.
