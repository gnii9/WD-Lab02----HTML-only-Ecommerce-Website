# Hướng dẫn hoàn thiện và nộp WDLab02

Bộ bài gồm website Góc Học Nhỏ và báo cáo bản thảo. Website có 5 HTML, 10 ảnh SVG, dữ liệu văn phòng phẩm khác hoàn toàn mẫu giày dép. Không có CSS, JavaScript, framework, backend hay cơ sở dữ liệu.

**Chưa nộp ngay bản báo cáo hiện tại:** còn thiếu lớp, ảnh chụp thực tế, URL GitHub và minh chứng commit. Thông tin MSSV 22110033 và tên không dấu LeThiHongDang được điền theo bài Lab01; kiểm tra lại cả cách viết tên có dấu trước khi dùng.

## 1. Chạy website trên máy Windows

1. Giải nén `WDLab02_GocHocNho_Source.zip`.
2. Chép nguyên thư mục `goc-hoc-nho` vào `C:\xampp\htdocs\` (hoặc htdocs trong nơi bạn cài XAMPP).
3. Kiểm tra đường dẫn phải là `C:\xampp\htdocs\goc-hoc-nho\index.html`, tránh lồng thêm một tầng thư mục.
4. Mở XAMPP Control Panel, nhấn **Start** tại Apache. Không cần MySQL.
5. Mở trình duyệt tại `http://localhost/goc-hoc-nho/`.
6. Nếu Apache dùng cổng khác, thay bằng `http://localhost:CONG/goc-hoc-nho/` theo cổng thực tế. Nếu lỗi 404, kiểm tra tên thư mục. Nếu không kết nối được, kiểm tra Apache đã chạy và cổng đang dùng.
7. Mở VS Code → File → Open Folder → chọn đúng `goc-hoc-nho`.

Có thể nhấp đúp index.html để xem nhanh, nhưng ảnh minh chứng theo đề cần chạy localhost. Python HTTP server cũng chỉ là máy chủ file tĩnh, không phải backend lưu đơn; hướng dẫn chính ở đây dùng Apache như bài Lab01.

## 2. Thứ tự đọc để hiểu và trình bày với thầy

- **index.html:** tìm DOCTYPE, head, header, nav, main, section, article và footer. Xem card VP01: ảnh → tên → giá → link chi tiết.
- **chi-tiet.html:** tìm `id="VP01"`; đối chiếu với `href="chi-tiet.html#VP01"` ở trang chủ.
- **bang-gia.html:** đếm 6 cột: nhóm, tên, gốc, bán, tiết kiệm, thao tác. Tiêu đề giá dùng colspan=3; tên nhóm dùng rowspan=4/3/3. Một tbody tương ứng một nhóm hàng.
- **dat-hang.html:** phân biệt id/for/name; tìm action/method; thử validation. Link “Đặt mẫu” chỉ cuộn đến chọn sản phẩm, không tự chọn VP01.
- **xac-nhan.html:** đọc phần giải thích form demo. Trang không đọc query, không gửi email, không lưu đơn.

Đọc báo cáo mục 5–7 và thử diễn giải lại bằng lời của bạn. Đừng chỉ học thuộc tên thẻ: hãy mở đúng đoạn code và chỉ ra kết quả trên trình duyệt.

## 3. Test form từng bước

1. Mở Đặt hàng mẫu, bấm Gửi ngay khi chưa nhập: browser phải chặn.
2. Nhập tên `Nguyen Van A`, email `abc`: phải báo email chưa hợp lệ.
3. Đổi email thành `demo@example.com`; điện thoại có thể bỏ trống hoặc dùng `0900000000`.
4. Chọn `VP01`, thử số lượng `0`, `11`, `1.5`: đều ngoài ràng buộc. Sửa lại `2`.
5. Chọn đóng gói tiêu chuẩn, chọn Nhận tại cửa hàng.
6. Chưa tick đồng ý mà gửi: phải bị chặn; sau đó tick đồng ý demo.
7. Nhập ghi chú giả lập `Goi gon`, bấm Gửi yêu cầu mẫu.
8. Kiểm tra đến `xac-nhan.html?...`, có `maSanPham=VP01` và `soLuong=2` trên URL. Các khóa khác do name quyết định; khoảng trắng và dấu tiếng Việt có thể được mã hóa.
9. Quay lại, thử hai radio để thấy chỉ chọn được một. Nhấn Nhập lại để thấy reset khôi phục mặc định, số lượng là 1.
10. Mở xac-nhan.html trực tiếp: trang vẫn mở, vì nó là trang tĩnh, không phải bằng chứng đã nhận đơn.

Chỉ dùng dữ liệu giả lập. GET hiện dữ liệu trên URL và có thể lưu trong lịch sử/log. Không có cơ sở dữ liệu đơn hàng không có nghĩa là dữ liệu biến mất khỏi mọi nơi.

## 4. Chụp hình đúng yêu cầu

Dùng Snipping Tool hoặc Win+Shift+S. Giữ chữ đủ lớn để đọc, không thu nhỏ toàn trang quá mức. Caption nằm dưới từng hình trong báo cáo.

| Mã | Cách chụp | Caption gợi ý |
|---|---|---|
| S1 | Trang chủ đầu trang; thấy localhost, thương hiệu, menu, banner và một phần catalog | Hình S1 – Trang chủ Góc Học Nhỏ chạy trên localhost |
| S2a | Nhóm Sổ và giấy; có thể chụp 2 ảnh nếu không đủ chiều cao | Hình S2a – Nhóm Sổ và giấy gồm VP01 đến VP04 |
| S2b | Nhóm Bút viết VP05–VP07 | Hình S2b – Ba sản phẩm thuộc nhóm Bút viết |
| S2c | Nhóm Dụng cụ VP08–VP10 | Hình S2c – Ba dụng cụ học tập |
| S3 | Từ trang chủ bấm VP01, chụp vùng chi tiết cùng URL #VP01 | Hình S3 – Liên kết fragment đến chi tiết VP01 |
| S4 | Bảng giá có 2 hàng header, 3 nhóm, 10 sản phẩm và footer | Hình S4 – Bảng giá sử dụng colspan và rowspan |
| S5a | Form, chia 2 ảnh nếu cần để thấy đủ trường | Hình S5a – Form đặt hàng mẫu |
| S5b | Bấm Gửi khi thiếu trường, chụp thông báo validation | Hình S5b – Trình duyệt kiểm tra trường bắt buộc |
| S6 | Gửi form hợp lệ, chụp trang kết quả và thanh địa chỉ có query | Hình S6 – Trang kết quả và dữ liệu GET trên URL |
| S7 | VS Code Explorer mở images/ cạnh trình duyệt đang chạy localhost | Hình S7 – Cấu trúc source và môi trường chạy |
| S8a | GitHub Code tab, rõ URL repo, 5 HTML và images/ | Hình S8a – Repository chứa source code |
| S8b | Mở danh sách commits trên GitHub, thấy commit thật | Hình S8b – Lịch sử commit của project |

Nếu một ảnh không chứa hết thì chia thành ảnh phụ, không bỏ sản phẩm. Báo cáo hiện có các vị trí [CHÈN ẢNH]; thay bằng hình thật, không dùng ảnh dựng lại hoặc ảnh source thay thế giao diện.

## 5. Đưa code lên GitHub

Tạo repo riêng cho Lab02, không ghi đè repo Lab01. Tên đề xuất: `WD-Lab02-HTML-Ecommerce`. Đây là tên gợi ý, chưa phải repository đã tạo.

Trên GitHub: New repository → nhập tên → chọn Public nếu phù hợp yêu cầu lớp (hoặc cấp quyền cho thầy) → để repo trống, không tạo thêm README/gitignore/license khi làm theo quy trình dưới → Create repository. Sao chép URL HTTPS thật.

Mở terminal VS Code tại thư mục goc-hoc-nho. Nếu đây là thư mục mới và chưa có repository:

```bash
git init
git branch -M main
git status
git add .
git commit -m "feat: complete WDLab02 stationery ecommerce"
git remote add origin URL_HTTPS_REPO_THUC_TE
git remote -v
git push -u origin main
git status
```

Thay `URL_HTTPS_REPO_THUC_TE` bằng URL sao chép từ GitHub, không gõ nguyên chữ placeholder. Nếu Git yêu cầu danh tính, dùng tên/email Git của chính bạn theo Lab01. Đăng nhập qua cơ chế GitHub trên máy; không dán mật khẩu/token vào báo cáo.

Nếu repo đã có sẵn, chạy git status và git remote -v trước; không chạy lại remote add nếu origin đã tồn tại. Nếu remote có commit khác, fetch/pull và xử lý theo trạng thái thực tế; không dùng force push để ghi đè. Không tạo commit giả theo ngày để làm bằng chứng. Một commit thật của source hiện tại có giá trị hơn lịch sử giả; những lần sửa tiếp theo có thể tạo commit thật mới.

Sau khi push: mở repo bằng trình duyệt, kiểm tra file và ảnh có mặt; mở mục commits để chụp S8b. Repo private phải cấp quyền thầy; không chỉ gửi link không truy cập được.

## 6. Hoàn thiện báo cáo

1. Mở DOCX bản thảo bằng Word.
2. Kiểm tra tên, MSSV, điền lớp và URL GitHub thật.
3. Chèn S1–S8 và caption vào mục thiết kế/minh chứng; thêm trang nếu cần để ảnh rõ.
4. Chạy các ca test ở mục 8, ghi kết quả thật. Sửa mọi lỗi phát hiện trong code, ảnh và report cùng nhau.
5. Cập nhật tự đánh giá: chỉ ghi đã hoàn thành những gì thực sự hoàn thành.
6. Tìm toàn văn các chuỗi `[`, `BỔ SUNG`, `CHÈN`, `DÁN`, `chưa` và sửa các placeholder/trạng thái còn dang dở. Không xóa các mô tả giới hạn thật của HTML-only.
7. File → Export/Save As → PDF. Tên cuối theo đề: `22110033_LeThiHongDang_WD-Lab02.pdf` (đổi nếu thông tin sinh viên khác).
8. Mở PDF kiểm tra font tiếng Việt, hình không mờ, không vỡ bảng, link repo bấm được. PDF bản thảo đính kèm chỉ dùng xem trước, không phải bản đủ minh chứng để nộp.

## 7. Email nộp bài

Theo đề: gửi `tuantran261083course@gmail.com`; deadline **27/10/2026**, không thấy quy định giờ cụ thể. Chưa gửi email trong phiên làm việc này.

**Chỉ dùng nội dung sau khi đã thực sự hoàn tất ảnh, GitHub và PDF:**

Tiêu đề: `22110033_LeThiHongDang_WD-Lab02`

Kính gửi thầy,

Em là Lê Thị Hồng Đăng, MSSV 22110033, lớp [LỚP]. Em gửi thầy báo cáo bài WD-Lab02 đính kèm.

Bài làm là website văn phòng phẩm Góc Học Nhỏ, gồm 5 trang HTML, 10 sản phẩm, bảng giá có gộp ô và form đặt hàng mẫu. Em đã bổ sung giải thích code, hình chụp kết quả và phần trả lời câu hỏi theo yêu cầu. Phần bổ sung gồm chia nhóm sản phẩm và liên kết từ chi tiết đến dòng tương ứng trong bảng giá.

Source code và lịch sử commit: [URL GITHUB THỰC TẾ].

Website chỉ mô phỏng bằng HTML, không lưu đơn hoặc xử lý thanh toán. [Nếu còn thiếu phần nào, ghi rõ tại đây; nếu nộp trễ, bổ sung lý do thực tế.]

Em cảm ơn thầy.

Lê Thị Hồng Đăng

## 8. Kiểm tra cuối

- Đúng ngành hàng khác giày dép; 10 mã, 10 ảnh và 5 trang chạy được.
- Giá, tên và thông số nhất quán giữa các trang.
- 10 link chi tiết đúng, không thiếu ảnh; bảng đúng merge.
- Form validation và GET đã thử trên trình duyệt.
- Không style, script, CSS/JS hoặc backend.
- PDF có đủ ảnh, 10 đoạn code, 20 câu lý thuyết, 5 sửa lỗi và tự đánh giá thật.
- GitHub xem được, source đầy đủ, link repo có trong PDF và email.
- Đính kèm PDF cuối; không cần gửi ZIP source qua email nếu thầy không yêu cầu.

## Tài liệu đối chiếu

Yêu cầu và hướng dẫn WDLab02 do giảng viên cung cấp là căn cứ chấm bài chính. Tra cứu thêm MDN ngày 26/10/2026:
- https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/form
- https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/th
