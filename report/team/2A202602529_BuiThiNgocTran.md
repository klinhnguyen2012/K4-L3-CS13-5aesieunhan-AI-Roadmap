# Báo cáo cá nhân — Bùi Thị Ngọc Trân (2A202602529)

## 1. Thông tin thành viên

- Họ tên: Bùi Thị Ngọc Trân
- MSSV: 2A202602529
- Nhóm và đề CS13: Nhóm 5 (5aesieunhan) · Đề 2: ChấmNhanh (chấm bài viết tiếng Anh)
- Vai trò: Lộ trình và slide · CP4 + CP5

## 2. Phần việc phụ trách

- **CP4 (Nhiệm vụ 4 — Lộ trình sản phẩm & Lịch rà soát)**:
  - Thiết kế và hoàn thiện toàn diện `3_Bảng lộ trình` theo khung 3 tầng: Bây giờ (0–3 tháng), Tiếp theo (3–6 tháng), và Sau này (6–12 tháng) với đầy đủ 8 dòng tiêu chuẩn.
  - Xây dựng Khung lịch rà soát lộ trình tại `4_Rà soát`, thiết lập cơ chế đánh giá định kỳ ở các mốc Ngày 30 / Ngày 60 / Ngày 90 và quy trình kích hoạt rà soát theo sự kiện (mô hình mới/giá giảm, đối thủ ra tính năng tương tự, thay đổi pháp lý theo Luật AI).
- **CP5 (Nhiệm vụ 5 — Slide thuyết trình lãnh đạo)**:
  - Soạn thảo 5 ô nội dung tóm tắt cho lãnh đạo tại `5_Slide lãnh đạo` (B4:B8) theo nguyên tắc "Kết luận trước" (Bottom-line first), kiểm soát độ dài nghiêm ngặt dưới 60 chữ/ô (toàn bộ 5/5 ô đều đạt trạng thái "Đạt").
  - Trình bày và hoàn thiện file slide trình chiếu 1 trang [`5aesieunhan_CS13_Slide.pptx`](../../5aesieunhan_CS13_Slide.pptx) đồng bộ 100% về số liệu kinh tế - kỹ thuật và quyết định chiến lược với file Excel.

## 3. Đóng góp cụ thể

### 3.1. Thiết kế Bảng lộ trình 3 tầng (`3_Bảng lộ trình`)

Dựa trên hồ sơ tình huống Đề 2 và kết quả chốt từ CP1–CP3 của nhóm, tôi đã xây dựng đầy đủ 8 dòng cho tầng Bây giờ cùng định hướng cho 2 tầng tiếp theo:

| Dòng | Tầng Bây giờ (0–3 tháng) · Cam kết | Tầng Tiếp theo (3–6 tháng) · Định hướng | Tầng Sau này (6–12 tháng) · Khám phá |
|---|---|---|---|
| **5. Việc chính** | Tích hợp 4 việc được chọn: Việc 3 (Hạng 1: Chuyển bài cho giáo viên đúng lúc & sửa tầng Khó), Việc 1 (Hạng 2: Chấm 4 tiêu chí cho bài thường), Việc 7 (Hạng 3: Báo cáo độ lệch máy–giáo viên cho đối tác lớn), Việc 4 (Hạng 4: Mua/tích hợp công cụ ngữ pháp có sẵn). | Việc 2: Nhận xét có trích câu và gợi ý sửa khi đã có cách đo "học sinh sửa được bài sau". Mở rộng thêm trung tâm nếu qua cổng Mức 2. | Việc 5: Báo cáo tiến bộ cho phụ huynh (sau khi đủ khoảng 3 tháng dữ liệu điểm). Việc 6 (Tạo đề bài): Không làm, chỉ xem lại nếu khách hàng đòi hỏi. |
| **6. Giả thuyết** | Chuyển đúng bài vùng 5,0–6,5 và bài tầng Khó cho giáo viên sẽ giúp máy chấm bài thường, giáo viên bớt 60% giờ chấm mà không bài khó nào bị lệch quá 1 điểm. | Nhận xét có trích câu giúp học sinh sửa được bài ở lần nộp sau. | Báo cáo tiến bộ giúp phụ huynh tin tưởng và tăng tỷ lệ gia hạn khoá học. |
| **7. Chỉ số & ngưỡng** | - Số tầng tụt giảm từ 1 về 0 trên bộ đề 40 bài.<br>- 0 bài lệch >1 điểm trong mẫu chấm đôi 2%.<br>- ≥70% bài lệch ≤0,5 điểm.<br>- Giáo viên bớt ≥60% giờ chấm bài thường.<br>- Tỷ lệ đạt quy về thực tế ≥80%. | Tỷ lệ học sinh nộp bản sửa có điểm cao hơn bản đầu; ngưỡng cụ thể chốt sau 4 tuần đo cơ sở. | Tỷ lệ gia hạn khoá học của phụ huynh nhận báo cáo so với nhóm không nhận; ngưỡng chốt khi tích lũy đủ ~3 tháng dữ liệu. |
| **8. Mức tự động** | **Mức 1 (Hỗ trợ có duyệt)**: Máy chấm bài thường, giáo viên duyệt ~15% bài (vùng 5,0–6,5 + mẫu ngẫu nhiên 2%). | **Mức 2 (Tự động một phần)**: Giáo viên duyệt ~10% bài, chỉ kích hoạt khi vượt qua cổng đánh giá. | **Mức 3 (Tự động có giám sát)**: Giáo viên chấm mẫu ~5%; chỉ mang tính thăm dò, không cam kết trước. |
| **9. Cổng đánh giá** | **Cổng lên Mức 1**: Chạy lại bộ đề 40 bài; số tầng tụt = 0 (hiện tại là 1 ở tầng Khó); lỗi nghiêm trọng 0/40; tỷ lệ đạt quy về thực tế ≥80% (hiện 82,6%); kappa ≥0,6 (hiện 0,80); Cô Lan ký xác nhận. | **Cổng lên Mức 2**: Chấm đôi ≥100 bài thật; 0 bài lệch >1 điểm (giới hạn trên theo quy tắc 3/n ≈ 3/100 = 3%); ≥70% bài lệch ≤0,5 điểm; số tầng tụt = 0; Cô Lan xác nhận. | **Cổng lên Mức 3**: Chấm đôi ≥200 bài qua 2 đợt liên tiếp; 0 bài lệch >1 điểm (3/200 = 1,5%); khiếu nại của phụ huynh vì lệch điểm ≤2 lần/quý; Ban lãnh đạo phê duyệt. |
| **10. Điều kiện cần** | - Giờ chuyên gia: Cô Lan và Thầy Khoa mỗi người 2 giờ/tuần (tổng 4 giờ/tuần). 1 vòng chạy lại 40 bài tốn 14,2 giờ ≈ 3,5 tuần → trong 12 tuần chỉ chạy được tối đa 1–2 vòng.<br>- Mẫu chấm đôi 2% chỉ khả thi với quy mô ≤550 bài thử nghiệm/tuần (ước tính 2 giờ ≈ 11 bài).<br>- Dữ liệu: Cần gắn nhãn bài vùng ranh giới 5,0–6,5.<br>- Tuân thủ: Gắn thông báo bài do AI chấm theo Luật AI 134/2025/QH15. | Cần ≥100 bài chấm đôi (giáo viên duyệt của công ty chấm ~30 bài/tuần trong 4 tuần; chuyên gia chỉ xác nhận); Báo cáo độ lệch cho đối tác; Dữ liệu điểm tích lũy đủ sau ~3 tháng. | Quy trình khiếu nại và gọi lại giáo viên; Dữ liệu điểm học sinh đủ lớn cho báo cáo tiến bộ; Rà soát phân loại mức độ rủi ro theo luật định. |
| **11. Căn cứ kinh tế** | - Doanh thu sau chia 20%: 5,21 triệu/trung tâm/tháng (1.000 bài) → 5.210 đ/bài.<br>- Chi phí Mức 1 (duyệt 15%): 769đ (AI) + 250đ (hạ tầng) + 0,15 × 3 phút × 120.000đ/60 = 1.919 đ/bài.<br>- Biên gộp Mức 1: **63,2%** (đạt yêu cầu ≥60%).<br>- Điểm an toàn: Duyệt quá 17,7% thì biên gộp rơi xuống dưới 60%. (Mức 0 duyệt 100% tốn 7.019 đ/bài, bị lỗ). | Mức 2 (duyệt 10%): Chi phí 1.619 đ/bài, biên gộp 68,9%. Nhận thức kịch bản xấu: hết tiền ở tháng 17 nếu mở rộng vội vã. | Mức 3 (duyệt 5%): Chi phí 1.319 đ/bài, biên gộp 74,7%. Biến số nguy hiểm nhất: Doanh thu bình quân (55% doanh thu đến từ 25% trung tâm lớn nhất). |
| **12. Điều kiện dừng** | **NẾU** sau khi chạy lại bộ đề 40 bài (tuần 6) số tầng tụt vẫn ≥1, hoặc mẫu chấm đôi ngày 60 có ≥1 bài lệch >1 điểm, **THÌ** lùi về Mức 0, không mở thêm trung tâm mới.<br>**NẾU** doanh thu bình quân sau chia <3,95 triệu/trung tâm 2 tháng liên tiếp trên ≥15 trung tâm **THÌ** dừng hoàn toàn việc mở rộng. | **NẾU** có 1 trung tâm lớn rút lui hoặc doanh thu bình quân giảm >10% so với 5,21 triệu **THÌ** xem xét lại chính sách giá và mức tự động. | **NẾU** tỷ lệ gia hạn khoá học không tăng sau 3 tháng thử nghiệm báo cáo tiến bộ **THÌ** dừng vĩnh viễn Việc 5. |

### 3.2. Thiết lập Khung rà soát lộ trình (`4_Rà soát`)

- **3 mốc thời gian cố định**:
  - **Ngày 30**: Quan sát số bài lệch >1 điểm trong mẫu chấm đôi 2%; tiến độ kỹ sư sửa tầng Khó; tỷ lệ bài chuyển cho giáo viên. Quyết định: Đi tiếp, sửa, hoặc lùi về Mức 0 nếu xuất hiện ≥1 bài lệch >1 điểm. Thẩm quyền: Cô Lan (tổ trưởng) cùng kỹ sư phụ trách.
  - **Ngày 60**: Đánh giá kết quả kiểm thử lại trên bộ đề 40 bài (số tầng tụt, chỉ số kappa, tỷ lệ đạt quy về thực tế); số giờ giáo viên thực tế tiết kiệm được. Quyết định: Đi tiếp, sửa hoặc đổi hướng; chỉ cho phép mở Mức 2 khi vượt qua toàn bộ tiêu chí cổng. Thẩm quyền: Cô Lan và Trưởng sản phẩm.
  - **Ngày 90**: Đánh giá doanh thu bình quân/trung tâm (theo dõi 2 tháng liên tiếp trên ≥15 trung tâm) và bằng chứng độ lệch máy–giáo viên cho đối tác; ghi nhận lưu ý chưa dùng chỉ số giá trị vòng đời (LTV) do khách hàng mới sử dụng 3 tháng. Quyết định: Đi tiếp, sửa, đổi hướng hoặc dừng mở rộng. Thẩm quyền: Ban lãnh đạo.
- **3 sự kiện bất thường ngoài lịch**:
  - *Mô hình mới xuất hiện / chi phí API giảm sâu*: Đối chiếu chi phí (hiện 769 đ/bài) và chạy thử nghiệm lại bộ đề 40 bài; chỉ đổi mô hình nếu tỷ lệ đạt ≥80% và 0 tầng bị tụt; người duyệt: Kỹ sư trưởng và Cô Lan.
  - *Nền tảng / đối thủ ra tính năng tương tự*: So sánh tính năng miễn phí trên bộ đề 40 bài xem có chấm đúng tiêu chí không; nếu đối thủ làm tốt, chuyển trọng tâm sang báo cáo độ lệch máy-giáo viên và tích hợp sâu; người duyệt: Trưởng sản phẩm và Ban lãnh đạo.
  - *Quy định pháp lý thay đổi (Luật AI 134/2025/QH15)*: Rà soát phân loại rủi ro của hệ thống chấm điểm; tăng tỷ lệ duyệt người, lùi mức tự động hoặc bổ sung cơ chế minh bạch/khiếu nại; người duyệt: Ban lãnh đạo và phụ trách pháp lý.

### 3.3. Soạn thảo Slide lãnh đạo & Trình chiếu (`5_Slide lãnh đạo` & `5aesieunhan_CS13_Slide.pptx`)

Thực hiện phương châm "Kết luận trước" (Bottom-line first) với cấu trúc 5 ô, độ dài chuẩn xác:
1. **Kết luận (1 câu)** (34 chữ — Đạt):
   > "Làm trước việc chuyển bài khó cho giáo viên và sửa tầng Khó; chỉ tăng mức tự động khi qua cổng đo bằng số. Mức 1: duyệt 15% bài, 1.919 đ/bài, biên gộp 63,2%."
2. **3 việc chính** (52 chữ — Đạt):
   > "1) Chuyển bài cho giáo viên đúng lúc, sửa tầng Khó đang tụt (tuần 1–2; chạy lại 40 bài tuần 3–6). 2) Chấm 4 tiêu chí cho bài thường, giáo viên bớt 60% giờ chấm. 3) Báo cáo độ lệch máy–giáo viên cho đối tác lớn nhất (≥70% bài lệch ≤0,5 điểm)."
3. **Cần gì (người, tiền, dữ liệu)** (53 chữ — Đạt):
   > "Chuyên gia: cô Lan và thầy Khoa, mỗi người 2 giờ/tuần (1 vòng chạy lại 40 bài tốn 14,2 giờ). Kỹ sư: sửa tầng Khó. Dữ liệu: thêm ca Khó, gắn nhãn bài vùng 5,0–6,5. Tiền: kịch bản xấu hết ở tháng 17, nên chưa mở rộng trước khi qua cổng Mức 1."
4. **Rủi ro lớn nhất & cách xử lý** (58 chữ — Đạt):
   > "Doanh thu bình quân: 55% đến từ 25% trung tâm lớn. Xử lý: gửi đối tác lớn nhất báo cáo độ lệch. Nếu doanh thu sau chia dưới 3,95 triệu/trung tâm 2 tháng liên tiếp trên ≥15 trung tâm thì dừng mở rộng; nếu ngày 60 có 1 bài lệch quá 1 điểm thì lùi về Mức 0."
5. **Khi nào xem lại** (47 chữ — Đạt):
   > "Ngày 30: tầng Khó đã sửa, mẫu chấm đôi. Ngày 60: kết quả chạy lại 40 bài, quyết định mở Mức 2. Ngày 90: doanh thu bình quân và độ lệch máy–giáo viên. Ngoài lịch: đổi mô hình, đối thủ ra tính năng tương tự, luật đổi."

File trình chiếu [`5aesieunhan_CS13_Slide.pptx`](../../5aesieunhan_CS13_Slide.pptx) được hoàn thiện với giao diện 1 slide trực quan, bố cục chia khối khoa học, kết luận nổi bật ở banner phía trên và 4 khối thẻ bên dưới.

## 4. Bằng chứng đóng góp

- **File Excel nhóm**: [`5aesieunhan_CS13.xlsx`](../../5aesieunhan_CS13.xlsx)
  - Sheet `3_Bảng lộ trình`: Toàn bộ các dòng từ B5 đến D12 được hoàn thành trọn vẹn, tính nhất quán cao.
  - Sheet `4_Rà soát`: Bảng lịch rà soát A4:D10 với đầy đủ mốc kiểm tra và kịch bản ứng phó sự kiện.
  - Sheet `5_Slide lãnh đạo`: Các ô B4:B8 chuẩn ≤60 chữ, cột C đếm chính xác và cột D đều đạt chữ "Đạt".
  - Sheet `6_Tự kiểm tra`: Toàn bộ 8/8 mục kiểm tra đều đạt trạng thái **"Đạt"**.
- **File Slide thuyết trình**: [`5aesieunhan_CS13_Slide.pptx`](../../5aesieunhan_CS13_Slide.pptx) hiển thị trọn vẹn 5 khối nội dung.

## 5. Tự đánh giá

- **Điều hiểu rõ**:
  - Lộ trình sản phẩm AI khác với lộ trình phần mềm truyền thống ở chỗ nó không chỉ lên lịch theo thời gian mà phải đi kèm **Cổng chất lượng đo bằng số** (Quality Gate) và **Điều kiện dừng** (Kill Switch). Một tính năng không thể tự động nâng mức chỉ vì đã đến ngày quy định nếu chưa vượt qua kiểm định định lượng trên cỡ mẫu đủ lớn.
  - Ràng buộc nguồn lực chuyên gia là yếu tố then chốt giới hạn tốc độ sản phẩm: với tổng cộng 4 giờ chuyên gia/tuần và mỗi vòng chạy lại mất 14,2 giờ, nhóm bắt buộc phải tính toán số vòng kiểm thử cẩn trọng để không làm vỡ tiến độ.
  - Tư duy kinh tế đơn vị (Unit Economics): Việc khống chế tỷ lệ bài duyệt của giáo viên ở mức ≤17,7% là lằn ranh đỏ để duy trì biên gộp trên 60%, bảo đảm công ty không rơi vào kịch bản cạn tiền ở tháng thứ 17.
- **Giả định còn cần kiểm chứng**:
  - Giả định bộ lọc định tuyến bài (routing) có thể phân loại chính xác các bài viết khó và bài trong vùng điểm nhạy cảm 5,0–6,5 để đẩy cho giáo viên duyệt kịp thời, không để lọt lỗi lệch điểm nghiêm trọng ra phụ huynh.
  - Giả định báo cáo độ lệch máy–giáo viên ở Việc 7 đủ thuyết phục để giữ chân 25% nhóm trung tâm lớn nhất (chiếm 55% doanh thu) tiếp tục gia hạn hợp đồng.
