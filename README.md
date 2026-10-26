# Góc Học Nhỏ — WDLab02

Website văn phòng phẩm mô phỏng: 5 trang HTML, 10 sản phẩm VP01–VP10, 3 nhóm hàng và 10 ảnh SVG cục bộ. Toàn bộ tên sản phẩm, hình minh họa, giá và chính sách là dữ liệu giả lập. Ảnh SVG được dựng riêng bằng các hình vector cơ bản, không dùng ảnh giày dép từ mẫu.

## Chạy

Chép thư mục này vào htdocs, bật Apache trong XAMPP và mở http://localhost/goc-hoc-nho/ . Không cần MySQL hoặc bước build. Cũng có thể mở index.html để xem nhanh, nhưng minh chứng bài yêu cầu localhost.

## Trang

- index.html: giới thiệu, danh mục 10 sản phẩm, chính sách demo.
- chi-tiet.html: các section #VP01 đến #VP10.
- bang-gia.html: 6 cột logic, gộp giá 3 cột và nhóm 4/3/3 hàng.
- dat-hang.html: form GET, thông tin giả lập, validation khai báo.
- xac-nhan.html: giải thích kết quả demo; không lưu đơn.

## Giới hạn

Chỉ HTML và các thuộc tính trình bày legacy được đề cho phép; không CSS/JS/framework/backend. Các thuộc tính bgcolor, align, font... có thể bị validator HTML hiện đại cảnh báo obsolete: chúng được giữ vì mục tiêu Lab02, không phải best practice hiện đại. Không đảm bảo bố cục tối ưu trên màn hình nhỏ.

Link đặt mẫu chỉ cuộn đến vùng chọn sản phẩm; người dùng tự chọn mã. Giá và tổng được ghi sẵn, không tính theo form. GET có thể làm dữ liệu xuất hiện trong URL, lịch sử và log: chỉ dùng dữ liệu giả lập. Trang xác nhận không chứng minh đã lưu đơn hoặc thanh toán.

Tổng mua 1 đơn vị của từng mã: gốc 435.000đ, bán 361.000đ, tiết kiệm 74.000đ.

## Kiểm tra

Đã kiểm tra source: 155 tham chiếu cục bộ, ID, nhãn form, bảng merge và dữ liệu. Cần kiểm thử trình duyệt và chụp minh chứng localhost/GitHub trên máy sinh viên. Báo cáo và hướng dẫn được cung cấp riêng, không đưa script tạo file vào website.

## Nguồn

Cấu trúc tham khảo WDLab02 Instruction và StepUp Shoes của giảng viên. Nội dung được thay bằng văn phòng phẩm. MDN: https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/form và https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/th .
