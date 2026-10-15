# 🌐 AutoEbook

*AutoEbook hỗ trợ tự động xử lý danh sách sách trên [Thư viện Sách](https://thcscaukieu.thuvienhcm.edu.vn/). Chọn sách cần đọc, theo dõi tiến độ và xem báo cáo ngay trên trang thư viện.*

**Phiên bản:** `2026.1.5` · **Trình quản lý:** [Tampermonkey](https://www.tampermonkey.net/)

<details>
<summary>▶ Cách AutoEbook hoạt động</summary>

AutoEbook quét danh sách tài liệu, rồi xử lý từng sách theo thứ tự. Script chờ trình đọc tải, theo dõi trạng thái và tiến độ mà trang thư viện cung cấp, sau đó tổng hợp kết quả. Sách cần quyền truy cập phù hợp hoặc gặp lỗi sẽ được ghi nhận để người dùng xem lại.

</details>

---

## ⚙️ Cách cài đặt

1. Cài và bật trình quản lý userscript [Tampermonkey](https://www.tampermonkey.net/).
   - [Trang hướng dẫn Tampermonkey](https://www.tampermonkey.net/faq.php)
2. Nhấn nút bên dưới để cài hoặc cập nhật AutoEbook:

<p>
  <a href="https://raw.githubusercontent.com/BeTrumBao/autoebook/refs/heads/main/AutoEbook-installer.user.js"><img alt="INSTALL / UPDATE" src="https://img.shields.io/badge/INSTALL%20%2F%20UPDATE-444444?style=for-the-badge"></a>
  <a href="https://raw.githubusercontent.com/BeTrumBao/autoebook/refs/heads/main/AutoEbook-installer.user.js"><img alt="AUTOEBOOK" src="https://img.shields.io/badge/AUTOEBOOK-1677E8?style=for-the-badge"></a>
</p>

<details>
<summary>Hoặc mở liên kết cài đặt</summary>

[Cài AutoEbook bằng Tampermonkey](https://raw.githubusercontent.com/BeTrumBao/autoebook/refs/heads/main/AutoEbook-installer.user.js)

</details>

3. Trong tab Tampermonkey vừa mở, nhấn **Install**; nếu đang cập nhật, chọn **Update** hoặc **Overwrite**.
4. Đăng nhập Thư viện Sách, mở trang danh sách tài liệu và tải lại trang. Bảng điều khiển AutoEbook sẽ xuất hiện trên trang.

---

## 📖 Tính năng

### Tính năng cơ bản

- Quét danh sách sách và lưu bộ nhớ đệm để dùng lại.
- Chọn một trong ba chế độ: đọc sách chưa hoàn tất, đọc theo số lượng hoặc chọn thủ công.
- Trong hộp chọn sách, dùng **Chọn tất cả** hoặc **Bỏ chọn tất cả**; số lượng `0` nghĩa là không giới hạn.
- Xử lý tuần tự, chờ trình đọc sách/PDF tải và theo dõi trạng thái hoàn tất.
- Bỏ qua sách đã hoàn tất. Ở chế độ số lượng, thử thay sách không xử lý được bằng sách dự phòng phù hợp nếu còn.
- Hiển thị tiến độ, thời gian ước tính, lý do bỏ qua và báo cáo cuối quá trình.
- Cho phép dừng quá trình đang chạy.

### Lưu ý khi sử dụng

- AutoEbook sử dụng phiên đăng nhập hiện có trên trang thư viện; bảng điều khiển không yêu cầu nhập mật khẩu.
- Một số sách yêu cầu quyền giáo viên hoặc quyền truy cập khác. AutoEbook không cấp quyền và không vượt qua giới hạn của tài khoản.
- Kết quả cuối cùng dựa trên trạng thái hiển thị trên trang thư viện; hãy kiểm tra báo cáo sau khi chạy.

---

## 💾 Dữ liệu và quyền riêng tư

- Script chỉ chạy trên `thcscaukieu.thuvienhcm.edu.vn` theo metadata `@match`.
- Danh sách đã quét, tiến độ, lịch sử đọc và tùy chọn được lưu trong `localStorage` của trình duyệt trên trang thư viện.
- Dữ liệu cục bộ không tự đồng bộ giữa các trình duyệt. Xóa dữ liệu trang có thể xóa trạng thái AutoEbook.
- Mã được tải và chạy trong trình duyệt của người dùng. Chỉ cài userscript từ repository chính thức.

---

## 🔄 Cập nhật và phát hành

- File cài production là [`AutoEbook-installer.user.js`](AutoEbook-installer.user.js); file này chứa metadata Tampermonkey và mã chạy.
- Tampermonkey kiểm tra và tải cập nhật từ `@updateURL` / `@downloadURL` trỏ tới file production trên nhánh `main`.
- Khi phát hành bản mới, tăng `@version`, tạo lại artifact production từ mã nguồn hiện hành và cập nhật file trên GitHub.
- Giữ `@updateURL` và `@downloadURL` trỏ đến URL raw. Không dùng URL dạng `github.com/.../blob/...` để cài đặt.

### Các file trong repository

| File | Vai trò |
| --- | --- |
| `AutoEbook-installer.user.js` | Bản production để cài và cập nhật bằng Tampermonkey |
| `script.js` | Mã nguồn phát triển |
| `script_v2.js` | Artifact riêng, không nằm trong luồng cài production hiện tại; metadata hiện ghi phiên bản `2026.1.2` |
| `logo.png` | Biểu tượng userscript |

---

## 🛠 Khắc phục sự cố

- **Không thấy bảng điều khiển:** kiểm tra Tampermonkey và AutoEbook đang bật, địa chỉ đang mở thuộc đúng tên miền, rồi tải lại trang.
- **Không quét hoặc đọc được sách:** đăng nhập lại, mở trang danh sách tài liệu và quét lại. Website tải chậm hoặc thay đổi giao diện có thể ảnh hưởng quá trình.
- **Một số sách bị bỏ qua:** xem lý do trong báo cáo; sách đã hoàn tất, cần quyền khác hoặc không truy cập được có thể không xử lý bằng tài khoản hiện tại.
- **Không thấy bản cập nhật:** mở bảng điều khiển Tampermonkey và chạy kiểm tra cập nhật cho AutoEbook.

## Tác giả

**Made by Em Wizi With Love <3**
