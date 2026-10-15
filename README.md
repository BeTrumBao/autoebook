# AutoEbook

Userscript hỗ trợ tự động xử lý danh sách sách trên [Thư viện Sách](https://thcscaukieu.thuvienhcm.edu.vn/). Script thêm một bảng điều khiển vào trang để quét sách, chọn danh sách cần xử lý, theo dõi tiến độ và xem báo cáo.

## Tính năng

- Quét danh sách sách trên trang thư viện và lưu danh sách đã quét vào bộ nhớ trình duyệt để dùng lại.
- Có ba chế độ: xử lý sách chưa hoàn tất, xử lý theo số lượng, hoặc tự chọn sách từ danh sách.
- Trong danh sách chọn sách có nút **Chọn tất cả** và **Bỏ chọn tất cả**; số lượng `0` nghĩa là không giới hạn.
- Xử lý tuần tự từng cuốn, mở trình đọc sách/PDF và chờ trang đọc sẵn sàng.
- Kiểm tra tiến độ và trạng thái hoàn tất theo thông tin hiển thị trên trang; bỏ qua sách đã hoàn tất.
- Tự bấm tim khi cần để đáp ứng điều kiện hoàn tất mà trang thư viện hiển thị.
- Hiển thị tiến độ, thời gian ước tính, lý do sách bị bỏ qua và báo cáo kết quả sau khi quét.
- Có thể dừng quá trình đang chạy.

## Cách hoạt động

1. Khi mở trang thuộc `thcscaukieu.thuvienhcm.edu.vn`, script kiểm tra trạng thái đã lưu và thêm giao diện AutoEbook vào trang.
2. Khi bắt đầu, script lấy các liên kết sách từ danh sách thư viện. Danh sách, vị trí đang xử lý, lịch sử và một số tùy chọn được lưu bằng `localStorage` của trình duyệt.
3. Script lần lượt mở trang từng cuốn, chờ bộ đọc PDF tải và kiểm tra tiến độ/trạng thái tim theo giao diện của website.
4. Sách đã hoàn tất sẽ được bỏ qua. Sách cần đăng nhập, cần quyền giáo viên hoặc gặp lỗi truy cập được ghi nhận để hiển thị trong báo cáo; script không vượt qua các yêu cầu đăng nhập hay quyền truy cập.
5. Khi kết thúc, AutoEbook hiển thị tổng kết và danh sách kết quả.

## Cài đặt

1. Cài tiện ích Tampermonkey trên trình duyệt.
2. [Bấm vào đây để cài AutoEbook bằng Tampermonkey](https://raw.githubusercontent.com/BeTrumBao/autoebook/refs/heads/main/AutoEbook-installer.user.js). Repo cần có cả `AutoEbook-installer.user.js` và `script_v2.js` ở nhánh `main`.
3. Chọn **Install** trong trang cài đặt của Tampermonkey.
4. Đăng nhập vào trang thư viện rồi mở danh sách sách để sử dụng bảng điều khiển.

## Lưu ý

- Script chỉ chạy trên `thcscaukieu.thuvienhcm.edu.vn`.
- Cache, lịch sử và tiến độ của AutoEbook được lưu trong bộ nhớ trang của trình duyệt. Xóa dữ liệu trang có thể xóa các thông tin này.
- Giao diện website thay đổi có thể làm một số chức năng cần được cập nhật.
