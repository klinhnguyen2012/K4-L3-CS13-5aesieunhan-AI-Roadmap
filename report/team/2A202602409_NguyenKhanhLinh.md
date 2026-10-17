# Báo cáo cá nhân — Nguyễn Khánh Linh (2A202602409)

## 1. Thông tin thành viên

- Họ tên: Nguyễn Khánh Linh
- MSSV: 2A202602409
- GitHub: `klinhnguyen2012`
- Nhóm và đề CS13: Nhóm 5 (5aesieunhan) · Đề 2: ChấmNhanh (chấm bài viết tiếng Anh)
- Vai trò: Mức tự động & Phân tích kinh tế · CP3

## 2. Phần việc phụ trách

- **CP3 (Nhiệm vụ 3 — Các mức tự động và cổng đánh giá)**:
  - Phân định ranh giới phối hợp giữa AI và con người qua từng mức tự động (từ Mức 0 đến Mức 3) tại sheet `2_Mức tự động` (B5:I8).
  - Thiết lập hệ số kỹ thuật cho hệ thống **Cổng đánh giá** (Quality Gates) định lượng bằng số (chỉ số, ngưỡng định lượng, cỡ mẫu tối thiểu theo quy tắc $3/n$, người xác nhận có thẩm quyền) cho các mức chuyển giao Mức 1, Mức 2 và Mức 3.
  - Xây dựng mô hình tài chính và kinh tế đơn vị (**Unit Economics**): tính toán chi phí gọi AI, hạ tầng, chi phí người duyệt, tính biên lợi nhuận gộp theo từng mức tự động, xác định ngưỡng hòa vốn biên gộp 60% (tỷ lệ duyệt trần 17,7%), và phân tích kịch bản xấu hết vốn ở tháng 17.
  - Phối hợp và khớp nối các mức tự động với danh sách công việc ưu tiên của CP1–CP2 (Việc 3, Việc 1, Việc 7, Việc 4) và chuyển giao thông số cho CP4 (Bảng lộ trình).

## 3. Đóng góp cụ thể

### 3.1. Phân định vai trò AI – Người và thiết kế Cổng đánh giá (`2_Mức tự động`)

Tôi đã nghiên cứu kỹ hồ sơ tình huống Đề 2 (ChấmNhanh) và xây dựng 4 mức tự động bám sát hiện trạng sản phẩm (bản 2 phát hành có giới hạn, tầng Khó bị tụt):

| Mức | Tên mức | AI làm gì | Người làm gì | Cổng đánh giá (Chỉ số + Ngưỡng + Cỡ mẫu + Người xác nhận) |
|:---:|---|---|---|---|
| **0** | **Gợi ý** *(Tuần 0 · Đang có)* | Máy chấm nháp 4 tiêu chí và viết nhận xét; chưa hiển thị trực tiếp cho học sinh | Giáo viên chấm lại và quyết định điểm 100% bài viết | Không cần cổng: đây là mức khởi đầu nội bộ, giáo viên chịu trách nhiệm 100% |
| **1** | **Hỗ trợ có duyệt** *(Tuần 1–6 · Bây giờ)* | Máy chấm bài thường và trả điểm; tự động chuyển bài vùng ranh giới 5,0–6,5 và bài tầng Khó cho giáo viên | Giáo viên chấm bài được chuyển sang; Cô Lan chấm đôi mẫu ngẫu nhiên 2% bài | **Chạy lại bộ đề 40 bài**: số tầng tụt = 0 (khắc phục điểm đỏ tầng Khó tụt 1); lỗi nghiêm trọng = 0/40 (bài lệch >1 điểm); tỷ lệ đạt quy về thực tế $\ge 80\%$ (hiện 82,6%); kappa $\ge 0,6$ (hiện 0,80); Cô Lan ký xác nhận |
| **2** | **Tự động một phần** *(Tháng 3–6 · Tiếp theo)* | Máy chấm và trả điểm cho bài thường; vùng chuyển giáo viên thu hẹp lại khi mô hình ổn định | Giáo viên duyệt khoảng 10% bài (vùng ranh giới hẹp + mẫu chấm đôi định kỳ) | **Chấm đôi $\ge 100$ bài thật**: 0 bài lệch >1 điểm (giới hạn trên theo quy tắc $3/n \approx 3/100 = 3\%$); $\ge 70\%$ bài lệch $\le 0,5$ điểm (phù hợp thực tế 2 giáo viên giỏi khớp nhau); số tầng tụt = 0; Cô Lan ký xác nhận |
| **3** | **Tự động có giám sát** *(Tháng 7–12 · Sau này)* | Máy chấm và trả điểm bài thường; chỉ chuyển giáo viên ở vùng ranh giới hẹp nhất | Giáo viên chấm mẫu khoảng 5% để giám sát hậu kiểm; học sinh có quyền gọi giáo viên phúc khảo | **Chấm đôi $\ge 200$ bài qua 2 đợt**: 0 bài lệch >1 điểm ($3/200 = 1,5\%$); $\ge 70\%$ bài lệch $\le 0,5$ điểm; tỷ lệ đạt quy về thực tế $\ge 80\%$; khiếu nại của phụ huynh $\le 2$ lần/quý; Ban lãnh đạo ký duyệt |

### 3.2. Mô hình hóa bài toán kinh tế đơn vị (Unit Economics)

Dựa trên số liệu đề bài (dòng 12–20 sheet `2_Mức tự động`), tôi đã thiết lập công thức và phân tích cấu trúc chi phí:

1. **Các tham số đầu vào cố định**:
   - Chi phí gọi AI mỗi bài (đã tính gọi lại): $769\text{ đồng}$
   - Chi phí hạ tầng + đánh giá + khác: $250\text{ đồng}$
   - Thời gian người duyệt: $3\text{ phút/bài}$
   - Chi phí 1 giờ người duyệt công ty: $120.000\text{ đồng}$ ($\rightarrow \frac{120.000 \times 3}{60} = 6.000\text{ đ/bài}$ nếu duyệt 100%)
   - Doanh thu bình quân sau chia 20%: $5.210.000\text{ đ/trung tâm/tháng}$ cho $1.000\text{ bài}$ $\rightarrow 5.210\text{ đ/bài}$.

2. **Kết quả tính toán theo từng mức**:
   - **Mức 0 (Duyệt 100%)**:
     $$\text{Chi phí} = 769 + 250 + 1{,}00 \times 6.000 = 7.019\text{ đ/bài}$$
     $$\text{Biên gộp} = \frac{5.210 - 7.019}{5.210} = -34{,}7\% \quad (\text{Lỗ nặng})$$
   - **Mức 1 (Duyệt 15%)**:
     $$\text{Chi phí} = 769 + 250 + 0{,}15 \times 6.000 = 1.919\text{ đ/bài}$$
     $$\text{Biên gộp} = \frac{5.210 - 1.919}{5.210} = \mathbf{63{,}2\%} \quad (\ge 60\% \rightarrow \mathbf{Đạt})$$
   - **Mức 2 (Duyệt 10%)**:
     $$\text{Chi phí} = 769 + 250 + 0{,}10 \times 6.000 = 1.619\text{ đ/bài}$$
     $$\text{Biên gộp} = \frac{5.210 - 1.619}{5.210} = \mathbf{68{,}9\%} \quad (\ge 60\% \rightarrow \mathbf{Đạt})$$
   - **Mức 3 (Duyệt 5%)**:
     $$\text{Chi phí} = 769 + 250 + 0{,}05 \times 6.000 = 1.319\text{ đ/bài}$$
     $$\text{Biên gộp} = \frac{5.210 - 1.319}{5.210} = \mathbf{74{,}7\%} \quad (\ge 60\% \rightarrow \mathbf{Đạt})$$

3. **Phát hiện kinh tế sống còn**:
   - **Điểm hòa vốn biên 60%**: Đặt phương trình $\frac{5.210 - (1.019 + H \times 6.000)}{5.210} \ge 0{,}60 \iff H \le \frac{5.210 \times 0{,}40 - 1.019}{6.000} \approx \mathbf{17{,}7\%}$. Nếu tỷ lệ bài phải duyệt vượt quá 17,7%, biên lợi nhuận gộp sẽ rơi xuống dưới 60%, vi phạm mục tiêu tài chính của công ty.
   - **Quản trị rủi ro dòng tiền**: Kịch bản xấu của đề chỉ ra công ty sẽ cạn tiền ở **tháng 17** nếu đốt tiền mở rộng trước khi kiểm soát được tỷ lệ duyệt. Do đó, việc duy trì Mức 1 ở tỷ lệ 15% là ranh giới bắt buộc trước khi mở rộng mạng lưới trung tâm.

### 3.3. Phân biệt rõ vai trò Chuyên gia và Người duyệt

Một đóng góp quan trọng trong phân tích CP3 là làm rõ sự tách biệt giữa:
- **Người duyệt của công ty (I5:I8 = "Người của mình")**: Là các giáo viên chấm bài được công ty trả lương theo giờ (120.000 đ/h) để xử lý các bài được chuyển sang và thực hiện chấm đôi 2% trong vận hành hàng ngày (chi phí được hạch toán đầy đủ vào cột J).
- **Chuyên gia chuyên môn (Cô Lan, Thầy Khoa)**: Chỉ có quỹ thời gian hạn hẹp là $2\text{ giờ/tuần/người}$ (tổng 4 giờ/tuần). Quỹ giờ này chỉ dùng để đánh giá bộ đề chuẩn 40 bài (mất 14,2 giờ/vòng ≈ 3,5 tuần) và ký xác nhận các cổng đánh giá chất lượng; tuyệt đối không dùng giờ chuyên gia vào việc chấm duyệt vận hành để tránh nghẽn cổ chai tiến độ.

## 4. Bằng chứng đóng góp

- **File Excel nhóm**: [`5aesieunhan_CS13.xlsx`](../../5aesieunhan_CS13.xlsx)
  - Trang `2_Mức tự động`: Toàn bộ các ô B5:I8 và các công thức J5:M8.
  - Trang `2_Mức tự động` B12:B20: Đối chiếu số liệu kinh tế chuẩn xác từ hồ sơ.
  - Trang `6_Tự kiểm tra`:
    - R7: Số mức tự động có cổng đánh giá kèm con số = **3 mức** (yêu cầu $\ge 2$) $\rightarrow$ **Đạt**.
    - R12: Số mức tự động có biên lợi nhuận $\ge 60\%$ = **3 mức** (yêu cầu $\ge 1$) $\rightarrow$ **Đạt**.
- **Tính nhất quán giữa các trang**:
  - Dữ liệu chi phí 1.919 đ/bài, biên gộp 63,2%, điều kiện cổng Mức 1, 2, 3 được chuyển giao nguyên vẹn sang `3_Bảng lộ trình` (dòng 8, 9, 11) và `5_Slide lãnh đạo` (ô B4, B6).

## 5. Tự đánh giá

- **Điều hiểu rõ**:
  - Tự động hóa sản phẩm AI là một thang đo liên tục, không phải công tắc bật/tắt (on/off). Việc phân cấp từ Gợi ý (Mức 0) $\rightarrow$ Hỗ trợ có duyệt (Mức 1) $\rightarrow$ Tự động một phần (Mức 2) $\rightarrow$ Tự động có giám sát (Mức 3) cho phép vừa kiểm soát rủi ro chất lượng, vừa giải phóng dần nhân lực giáo viên.
  - Cổng đánh giá phải dựa trên thống kê với cỡ mẫu tin cậy (như quy tắc $3/n$ cho tỷ lệ lỗi cực đại khi thấy 0 lỗi) kết hợp các chỉ số tương đồng (kappa $\ge 0,6$, tỷ lệ đạt $\ge 80\%$).
  - Biên lợi nhuận gộp là lằn ranh quyết định sự sống còn của doanh nghiệp: nếu không có cơ chế lọc bài (routing) hiệu quả để hạ tỷ lệ duyệt xuống dưới 17,7%, công ty sẽ bị lỗ trên từng bài viết bán ra.
- **Giả định còn cần kiểm chứng**:
  - Giả định tỷ lệ duyệt 15% ở Mức 1 bao gồm toàn bộ bài vùng 5,0–6,5 và bài tầng Khó là đủ để giữ tỷ lệ bài lệch >1 điểm thực tế bằng 0.
  - Giả định giáo viên công ty có thể xử lý việc đọc duyệt và sửa nhận xét trong vòng trung bình đúng 3 phút/bài mà không bị vượt quá định mức chi phí.
