# Lab F3 - Đăng ký học phần (Flutter)

**Sinh viên:** Nguyễn Phạm Chí Thành
**MSSV:** 231A010308
**Lớp:** CNTT-LTDD
**Môn:** Lập trình trên các thiết bị di động

## Mô tả

Form đăng ký học phần dùng Flutter Form + validator, gồm đủ 7 loại control theo yêu cầu:
TextFormField, DropdownButtonFormField, RadioGroup + RadioListTile, CheckboxListTile,
Slider, SwitchListTile.

- Nhập Họ tên / MSSV / Email có validator kiểm tra hợp lệ ngay khi gõ (`AutovalidateMode.onUserInteraction`).
- MSSV chỉ cho gõ số, tối đa 10 ký tự (`inputFormatters`).
- Chọn Học phần bằng Dropdown, Hệ đào tạo bằng RadioGroup, Buổi học bằng Checkbox (lưu vào `Set`).
- Số tín chỉ chọn bằng Slider (10-24), Switch bật/tắt nhận thông báo qua email.
- Bấm ĐĂNG KÝ: kiểm tra toàn bộ Form + các control ngoài Form, nếu hợp lệ hiện hộp thoại tóm tắt dữ liệu.
- Bấm Làm lại: đưa form về trạng thái ban đầu.

## Bài nâng cao

**NC2 - Kiểm tra phụ thuộc giữa 2 control:**
Nếu người dùng chọn hệ đào tạo "Vừa làm vừa học" nhưng chưa tick buổi "Tối" trong
danh sách buổi học, bấm ĐĂNG KÝ sẽ không hiện hộp thoại mà hiện SnackBar báo
"Hệ Vừa làm vừa học bắt buộc phải chọn buổi Tối". Đây là ràng buộc nghiệp vụ giữa
RadioGroup và CheckboxListTile, nằm ngoài validator của Form nên phải tự viết `if`
kiểm tra trong hàm `_dangKy()`.

**NC3 - Đếm ký tự còn lại ô Họ tên:**
Thêm thuộc tính `maxLength: 50` vào TextFormField của ô Họ tên. Flutter tự động
hiển thị bộ đếm dạng `x/50` dưới ô nhập, cập nhật theo thời gian thực khi gõ,
không cần tự viết thêm code đếm ký tự.

## Công nghệ

- Flutter 3.47.3, Dart 3.13.3
- Material 3 (ColorScheme.fromSeed)
