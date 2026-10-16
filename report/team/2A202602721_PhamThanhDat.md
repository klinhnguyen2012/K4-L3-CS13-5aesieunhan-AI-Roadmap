# Báo cáo cá nhân — Phạm Thành Đạt (2A202602721)

## 1. Thông tin thành viên

- Họ tên: Phạm Thành Đạt
- MSSV: 2A202602721
- Nhóm và đề CS13: Nhóm 5 (5aesieunhan) · Đề 2: ChấmNhanh (chấm bài viết tiếng Anh)
- Vai trò: QA & tích hợp

## 2. Phần việc phụ trách

- Phụ trách toàn diện công tác QA & tích hợp sản phẩm cho nhóm 5aesieunhan:
  - **CP1**: Rà soát và đọc hồ sơ tình huống, đối chiếu các tham số kinh tế - kỹ thuật, điền trang `0_Đầu vào` (B5:E10), xác minh công thức `0_Đầu vào!B12` và cột O của `1_Danh sách việc`.
  - **CP2**: Kiểm tra chéo công thức tính điểm ưu tiên RICE kết hợp mức độ sẵn sàng và rủi ro bị nuốt, xác thực thứ tự ưu tiên và các quyết định Tự làm/Mua/Chờ/Không làm.
  - **CP3**: Kiểm tra bài toán kinh tế (chi phí, doanh thu, biên lợi nhuận theo các mức tự động), thẩm định tính khả thi của giờ chuyên gia và cổng kiểm soát chất lượng, sửa mâu thuẫn thời gian chấm đôi tại `2_Mức tự động!F7` và `3_Bảng lộ trình!C10`.
  - **CP4**: Kiểm tra sự nhất quán của bảng lộ trình `3_Bảng lộ trình`, khung rà soát `4_Rà soát`, kiểm tra checklist `6_Tự kiểm tra`, hoàn thiện hồ sơ nhóm trong `team/TEAM.md` và `README.md`.
  - **CP5**: Thẩm định 1 slide tóm tắt cho lãnh đạo tại `5_Slide lãnh đạo` và file slide thuyết trình `5aesieunhan_CS13_Slide.pptx`, đảm bảo chuẩn định dạng ≤60 chữ/ô và số liệu ăn khớp 100%.

## 3. Nhật ký QA theo checkpoint

### CP1 · Đọc hồ sơ và kiểm tra giả thuyết, chỉ số
- **Đọc và xác nhận hồ sơ tình huống**: Đã hoàn thành đọc và đối chiếu cả 6 mục trong hồ sơ tình huống Đề 2 (ChấmNhanh). Điền "Có" vào B5:B10 trên sheet `0_Đầu vào` kèm các ghi chú chi tiết tại E5:E10:
  - E5: Đã đối chiếu 9 dòng số liệu với trang 2 B12:B20; khớp hồ sơ.
  - E6: 1 việc = 1 bài viết được chấm điểm và có nhận xét; ~1.500 bài/tuần.
  - E7: Giữ 6 việc gợi ý, thêm việc 7 (báo cáo độ lệch cho đối tác).
  - E8: Phát hành có giới hạn; tầng Khó tụt 1 → sửa và chạy lại trước khi mở rộng.
  - E9: Cô Lan + thầy Khoa, 2 giờ/tuần mỗi người; 1 vòng 40 bài = 14,2 giờ.
  - E10: Người duyệt = giáo viên công ty trả tiền; hai giáo viên giỏi khớp ~70% trong 0,5 điểm.
- **Xác minh công thức trang `0_Đầu vào`**: Ô B12 (`=COUNTIF(B5:B10,"Có")`) đạt kết quả **6/6 mục**, sẵn sàng chuyển sang Nhiệm vụ 1.
- **Kiểm tra chéo trang `1_Danh sách việc`**:
  - Toàn bộ **7/7 việc** (cột O dòng 5 đến 11) đều đạt trạng thái `"Có"`.
  - Tất cả 7 việc đều có đầy đủ giả thuyết nghiệp vụ rõ ràng (cột D) cùng chỉ số thành công và ngưỡng định lượng có con số cụ thể (cột E).

### CP2 · Thẩm định điểm ưu tiên và quyết định lựa chọn
- **Tính toán lại toàn bộ điểm ưu tiên theo công thức M**:
  - Công thức tính điểm ưu tiên chuẩn hóa:
    $$\text{Điểm} = \text{RICE} \times (0{,}5 + 0{,}5 \times \text{sẵn sàng TB}) \times (1 - 0{,}5 \times \text{rủi ro bị nuốt})$$
    Trong đó:
    - $\text{RICE} = \frac{\text{Độ phủ (F)} \times \text{Tác động (G)} \times \text{Mức tự tin (H)}}{\text{Công sức (I)}}$
    - $\text{Sẵn sàng TB} = \frac{\text{Sẵn sàng dữ liệu (J)} + \text{Sẵn sàng đánh giá (K)}}{2}$
    - $\text{Rủi ro bị nuốt} = \text{Cột L}$
  - Kết quả tính toán lại độc lập cho từng việc:
    - **Việc 3** (Chuyển bài cho giáo viên đúng lúc): $\text{RICE} = 10{,}0$, sẵn sàng TB = 0,70, rủi ro = 0,1 $\rightarrow$ **Điểm = 8,07 (Hạng 1)**.
    - **Việc 1** (Chấm điểm 4 tiêu chí cho bài viết thường): $\text{RICE} = 6{,}67$, sẵn sàng TB = 0,80, rủi ro = 0,3 $\rightarrow$ **Điểm = 5,10 (Hạng 2)**.
    - **Việc 7** (Báo cáo độ lệch máy–giáo viên cho đối tác): $\text{RICE} = 6{,}00$, sẵn sàng TB = 0,70, rủi ro = 0,1 $\rightarrow$ **Điểm = 4,84 (Hạng 3)**.
    - **Việc 4** (Sửa ngữ pháp từng câu): $\text{RICE} = 10{,}0$, sẵn sàng TB = 0,90, rủi ro = 1,0 $\rightarrow$ **Điểm = 4,75 (Hạng 4)**.
    - **Việc 2** (Nhận xét có trích câu và gợi ý sửa): $\text{RICE} = 2{,}50$, sẵn sàng TB = 0,35, rủi ro = 0,5 $\rightarrow$ **Điểm = 1,27 (Hạng 5)**.
    - **Việc 6** (Tạo đề bài viết theo trình độ): $\text{RICE} = 2{,}40$, sẵn sàng TB = 0,65, rủi ro = 1,0 $\rightarrow$ **Điểm = 0,99 (Hạng 6)**.
    - **Việc 5** (Báo cáo tiến bộ cho phụ huynh): $\text{RICE} = 1{,}125$, sẵn sàng TB = 0,20, rủi ro = 0,4 $\rightarrow$ **Điểm = 0,54 (Hạng 7)**.
- **Khớp thứ tự trong Bảng lộ trình**:
  - Thứ tự ưu tiên qua tính toán độc lập ($3 \rightarrow 1 \rightarrow 7 \rightarrow 4$) khớp hoàn toàn với thứ tự việc triển khai ở tầng Bây giờ trong `3_Bảng lộ trình!B5`: Việc 3 (xếp 1) $\rightarrow$ Việc 1 $\rightarrow$ Việc 7 $\rightarrow$ Việc 4.
- **Thẩm định quyết định (cột P) và lý do lựa chọn (cột Q)**:
  - **Tự làm (Việc 3, 1, 7)**:
    - *Việc 3 (Tự làm, hạng 1)*: Là điều kiện tiên quyết để giải quyết nút thắt lớn nhất trong hồ sơ (cổng phát hành đang báo 'Xem lại' vì tầng Khó tụt 1 tầng). Tự xây luật chuyển bài và can thiệp sửa tầng Khó để chặn lỗi nghiêm trọng.
    - *Việc 1 (Tự làm, hạng 2)*: Là năng lực cốt lõi mang lại giá trị kinh tế trực tiếp cho trung tâm, giúp giáo viên tiết kiệm 60% thời gian chấm bài thường.
    - *Việc 7 (Tự làm, hạng 3)*: Việc nhóm đề xuất thêm dựa trên nhận diện rủi ro sống còn từ hồ sơ: 55% doanh thu đến từ 25% trung tâm lớn nhất, và trung tâm đối tác lớn nhất đang đòi bằng chứng máy lệch giáo viên bao nhiêu. Việc 7 tận dụng ngay mẫu chấm đôi 2% có sẵn nên chi phí phát triển thấp, hiệu quả giữ chân khách hàng then chốt rất cao.
  - **Mua (Việc 4)**:
    - *Lưu ý quan trọng*: Việc 4 đạt điểm khá cao (4,75, xếp hạng 4) do công sức thấp (1) và độ sẵn sàng cao (0,90), nhưng nhóm quyết định **Mua** thay vì Tự làm vì **rủi ro bị nuốt bằng 1,0**. Hồ sơ ghi công cụ sửa ngữ pháp miễn phí đã làm rất tốt việc sửa từng câu; việc tự phát triển sẽ không tạo ra bất kỳ lợi thế cạnh tranh độc quyền nào mà lại lãng phí giờ chuyên gia và kỹ sư. Tích hợp công cụ sẵn có giúp bổ sung tính năng với chi phí gọi thêm 0 đồng.
  - **Chờ (Việc 2, 5)**:
    - *Việc 2 (Chờ, hạng 5)*: Chưa có bộ dữ liệu chuẩn hóa để đo lường việc học sinh sửa bài sau nhận xét; rủi ro bị nuốt ở mức 0,5 do các mô hình miễn phí viết nhận xét khá tốt. Quyết định chờ và xem xét lại tại mốc Ngày 90.
    - *Việc 5 (Chờ, hạng 7)*: Điểm số thấp nhất (0,54), dữ liệu điểm học sinh mới bắt đầu thu thập nên cần ít nhất 3 tháng mới có thể tạo báo cáo tiến bộ có ý nghĩa; chưa có cơ chế đo lường tỷ lệ phụ huynh gia hạn khóa học. Quyết định chờ và đưa vào xem xét tại mốc Ngày 90 (chuyển sang tầng Sau này).
  - **Không làm (Việc 6)**:
    - *Việc 6 (Không làm, hạng 6)*: Điểm thấp (0,99), rủi ro bị nuốt tối đa 1,0 vì các mô hình AI tạo sinh miễn phí đã làm tốt việc tạo đề bài viết. Đây không phải tính năng khiến các trung tâm sẵn sàng chi trả tiền cho ChấmNhanh. Quyết định dứt khoát không đưa vào lộ trình sản phẩm.

### CP3 · Thẩm định mức tự động, bài toán kinh tế và điều chỉnh mâu thuẫn chấm đôi
- **Xác minh độc lập bài toán kinh tế theo các mức tự động**:
  - *Doanh thu bình quân mỗi bài*: Khách hàng (trung tâm) trả trung bình $5{,}21$ triệu VNĐ/tháng (sau khi đã chia 20% cho đối tác), thực hiện trung bình $1.000$ bài/tháng $\rightarrow$ Doanh thu đơn vị = **5.210 đ/bài**.
  - *Chi phí đơn vị theo các mức*: Chi phí nền tảng cố định trên mỗi bài gồm gọi API AI ($769$ đ) + Hạ tầng/đánh giá/khác ($250$ đ) = **1.019 đ/bài**. Giáo viên duyệt bài hưởng mức thù lao $120.000$ đ/giờ, thời gian duyệt trung bình $3$ phút/bài $\rightarrow$ Chi phí duyệt nếu duyệt $100\%$ bài là $\frac{3 \times 120.000}{60} = \mathbf{6.000\text{ đ/bài}}$.
    - **Mức 0 (Duyệt 100%)**: $769 + 250 + 6.000 = \mathbf{7.019\text{ đ/bài}}$. Doanh thu thu về $5.210$ đ/bài $\rightarrow$ Biên lợi nhuận gộp âm ($-34{,}7\%$, lỗ $1.809$ đ/bài). Điều này chứng minh việc duy trì Mức 0 lâu dài là bất khả thi về mặt tài chính.
    - **Mức 1 (Hỗ trợ có duyệt, duyệt 15%)**: $769 + 250 + 0{,}15 \times 6.000 = 1.019 + 900 = \mathbf{1.919\text{ đ/bài}} \rightarrow$ Biên lợi nhuận gộp đạt **63,2%** ($\ge 60\%$, đạt mục tiêu tài chính).
    - **Mức 2 (Tự động một phần, duyệt 10%)**: $769 + 250 + 0{,}10 \times 6.000 = 1.019 + 600 = \mathbf{1.619\text{ đ/bài}} \rightarrow$ Biên lợi nhuận gộp đạt **68,9%**.
    - **Mức 3 (Tự động có giám sát, duyệt 5%)**: $769 + 250 + 0{,}05 \times 6.000 = 1.019 + 300 = \mathbf{1.319\text{ đ/bài}} \rightarrow$ Biên lợi nhuận gộp đạt **74,7%**.
  - *Tỷ lệ duyệt tối đa để đảm bảo biên lợi nhuận $\ge 60\%$*:
    $$\frac{5.210 - (1.019 + p \times 6.000)}{5.210} \ge 0{,}60 \iff 1.019 + p \times 6.000 \le 2.084 \iff p \le \frac{1.065}{6.000} \approx \mathbf{17{,}75\%}$$
    Nếu tỷ lệ bài chuyển sang giáo viên vượt quá $17{,}75\%$, biên lợi nhuận của Mức 1 sẽ rơi xuống dưới ngưỡng an toàn $60\%$.
- **Thẩm định 3 cổng đánh giá (Mức 1 $\rightarrow$ Mức 3)**:
  - Cả 3 cổng đánh giá đều xác định rõ 4 thành tố: **chỉ số đo lường**, **ngưỡng định lượng**, **cỡ mẫu tối thiểu** và **chủ thể chịu trách nhiệm xác nhận**.
  - *Cổng Mức 2 và Mức 3 áp dụng chuẩn xác quy tắc $3/n$*:
    - Với cỡ mẫu $n = 100$ bài thật, nếu quan sát thấy $0$ lỗi nghiêm trọng (lệch $>1$ điểm), cận trên khoảng tin cậy 95% của tỷ lệ lỗi nghiêm trọng trong quần thể được giới hạn ở mức $\approx 3/100 = \mathbf{3\%}$.
    - Với cỡ mẫu $n = 200$ bài thật (2 đợt liên tiếp ở Mức 3), tỷ lệ lỗi nghiêm trọng được bảo đảm dưới $\approx 3/200 = \mathbf{1{,}5\%}$.
  - *Ngưỡng $\ge 70\%$ bài lệch $\le 0{,}5$ điểm*: Ngưỡng này được đối chiếu chính xác với hồ sơ, trong đó hai giáo viên giỏi chấm độc lập chỉ khớp nhau khoảng $70\%$ trong phạm vi $0{,}5$ điểm. Cổng không đặt cao hơn mức này để tránh đặt kỳ vọng phi lý đối với mô hình AI khi bản thân con người cũng có độ phân kỳ tự nhiên.
- **Phát hiện và xử lý mâu thuẫn then chốt về tiến độ chấm đôi và quỹ giờ chuyên gia**:
  - *Mâu thuẫn phát hiện*: Bản thảo ban đầu ghi nhận chuyên gia (cô Lan và thầy Khoa) sẽ thực hiện chấm đôi 100 bài trong 5 tuần (khoảng 20 bài/tuần). Tuy nhiên, hồ sơ tình huống chỉ rõ hai chuyên gia chỉ có **tổng cộng 4 giờ/tuần** (mỗi người 2 giờ/tuần). Với tốc độ chấm đôi cẩn thận, 2 giờ chỉ chấm được khoảng 11 bài. Đặc biệt, từ tuần 3 đến tuần 6, toàn bộ thời gian của hai chuyên gia phải dành trọn cho việc đánh giá lại bộ đề 40 bài chuẩn hóa ($14{,}2$ giờ $\approx 3{,}5$ tuần làm việc) để sửa tầng Khó. Do đó, việc yêu cầu chuyên gia vừa chạy lại bộ đề 40 bài vừa chấm đôi 100 bài trong 5 tuần là hoàn toàn phi thực tế và gây quá tải nguồn lực.
  - *Giải pháp điều chỉnh và chuẩn hóa*:
    - Nhóm đã thống nhất chuyển công tác chấm đôi sang cho **giáo viên duyệt của công ty** đảm nhiệm (chi phí duyệt đã nằm trong chi phí biến đổi 3 phút/bài = $6.000$ đ/bài).
    - Với lưu lượng hiện tại khoảng $1.500$ bài/tuần, tỷ lệ mẫu $2\%$ tương ứng với khoảng $\approx 30$ bài/tuần. Như vậy, chỉ cần khoảng **4 tuần** là tích lũy đủ 100 bài chấm đôi từ thực tế.
    - Chuyên gia (cô Lan) chỉ đóng vai trò rà soát các ca có phân kỳ/lệch điểm và ký xác nhận cổng đánh giá, hoàn toàn tương thích với quỹ thời gian 4 giờ/tuần.
  - *Thực hiện cập nhật trực tiếp vào file Excel*:
    - Ô `2_Mức tự động!F7`: Cập nhật thành: *"Đã có mẫu chấm đôi đủ 100 bài thật: giáo viên duyệt của công ty chấm đôi (3 phút/bài, đã tính trong chi phí), chuyên gia chỉ rà bài lệch và xác nhận cổng; 2% × 1.500 bài/tuần ≈ 30 bài/tuần → khoảng 4 tuần; báo cáo độ lệch gửi được cho đối tác; nhật ký bài chuyển giáo viên"*.
    - Ô `3_Bảng lộ trình!C10`: Cập nhật cụm từ `(khoảng 5 tuần)` thành: `(giáo viên duyệt của công ty chấm đôi ~30 bài/tuần, khoảng 4 tuần; chuyên gia chỉ xác nhận)`, giữ nguyên toàn bộ nội dung còn lại.

### CP4 · Kiểm tra lộ trình sản phẩm, điều kiện dừng và lịch rà soát
- **Kiểm tra tầng "Bây giờ" trên `3_Bảng lộ trình`**:
  - Toàn bộ các ô từ **B5 đến B12 đạt đủ 8/8 dòng** theo đúng chuẩn cấu trúc:
    1. *B5 (Việc chính)*: Liệt kê đúng 4 việc ưu tiên theo kết quả CP2 (Việc 3 xếp 1, Việc 1, Việc 7, Việc 4).
    2. *B6 (Giả thuyết)*: Giả thuyết rõ ràng về việc chuyển bài khó giúp máy chấm bài thường và giáo viên giảm 60% thời gian chấm.
    3. *B7 (Chỉ số & ngưỡng)*: Đầy đủ 5 chỉ số có ngưỡng định lượng (tầng tụt về 0, 0 bài lệch >1 điểm, $\ge 70\%$ bài lệch $\le 0{,}5$ điểm, giảm $\ge 60\%$ giờ chấm, tỷ lệ đạt $\ge 80\%$).
    4. *B8 (Mức tự động)*: Xác định Mức 1 (Hỗ trợ có duyệt, duyệt 15%).
    5. *B9 (Cổng đánh giá)*: Cổng lên Mức 1 dựa trên chạy lại bộ đề 40 bài do cô Lan xác nhận.
    6. *B10 (Điều kiện cần)*: Nêu chi tiết giờ chuyên gia (4 giờ/tuần), thời gian chạy lại 40 bài (14,2 giờ $\approx 3{,}5$ tuần), nhãn bài vùng 5,0–6,5 và tuân thủ Luật AI 134/2025/QH15.
    7. *B11 (Căn cứ kinh tế)*: Dẫn số liệu doanh thu 5.210 đ/bài, chi phí 1.919 đ/bài, biên gộp 63,2%, ngưỡng duyệt tối đa 17,75%.
    8. *B12 (Điều kiện dừng/đổi hướng)*: Đầy đủ số liệu và tuân thủ chặt chẽ cấu trúc khung **NẾU…THÌ**:
       - *"NẾU sau khi chạy lại bộ đề 40 bài (tuần 6) số tầng tụt vẫn ≥1, hoặc mẫu chấm đôi ngày 60 có ≥1 bài lệch >1 điểm, THÌ lùi về Mức 0, không mở thêm trung tâm."*
       - *"NẾU doanh thu bình quân sau chia <3,95 triệu/trung tâm 2 tháng liên tiếp trên ≥15 trung tâm THÌ dừng mở rộng."*
- **Thẩm định khung rà soát tại `4_Rà soát`**:
  - *3 mốc thời gian cố định*:
    - **Ngày 30**: Cô Lan (tổ trưởng) cùng kỹ sư rà soát số bài lệch >1 điểm trong mẫu chấm đôi 2%, tiến độ sửa tầng Khó, tỷ lệ chuyển giáo viên. Quyết định: đi tiếp, sửa hoặc lùi về Mức 0.
    - **Ngày 60**: Cô Lan và trưởng sản phẩm đánh giá kết quả chạy lại bộ đề 40 bài (số tầng tụt, kappa, tỷ lệ đạt quy về thực tế, số giờ giáo viên tiết kiệm thực tế). Quyết định: mở Mức 2 khi qua cổng.
    - **Ngày 90**: Ban lãnh đạo đánh giá doanh thu bình quân/trung tâm (2 tháng liên tiếp trên $\ge 15$ trung tâm) và độ lệch máy–giáo viên; chưa vội dùng chỉ số giá trị vòng đời (LTV) vì mới hoạt động 3 tháng.
  - *3 sự kiện kích hoạt ngoài lịch*:
    - Có mô hình mới hoặc giá API AI giảm mạnh (rà soát chi phí đơn vị và tỷ lệ đạt trên bộ đề 40 bài).
    - Nền tảng hoặc đối thủ cạnh tranh ra tính năng tương tự (so sánh chất lượng trên 40 bài và số trung tâm yêu cầu).
    - Quy định pháp lý thay đổi (Luật AI 134/2025/QH15 và các văn bản hướng dẫn thi hành).
- **Kiểm tra bảng tự đánh giá tại `6_Tự kiểm tra`**:
  - Cả **8/8 tiêu chí kiểm tra tự động đều đạt trạng thái "Đạt"** (B5 $\ge 5$; B6 = 0; B7 $\ge 2$; B8 = 8; B9 = "Có"; B10 = "Có"; B11 = 5; B12 $\ge 1$). Toàn bộ workbook đạt độ nhất quán và hoàn thiện cao nhất.

### CP5 · Thẩm định slide lãnh đạo và đối chiếu workbook
- **Kiểm tra giới hạn từ tại `5_Slide lãnh đạo`**:
  - Thực hiện kiểm tra độ dài văn bản độc lập cho từng khối nội dung (sử dụng công thức đếm số từ chuẩn Excel `=IF(TRIM(Bx)="",0,LEN(TRIM(Bx))-LEN(SUBSTITUTE(TRIM(Bx)," ",""))+1)`):
    - **Ô B4 (Kết luận 1 câu)**: **34 chữ** ($\le 60$ chữ, ô D4 = `"Đạt"`).
    - **Ô B5 (3 việc chính)**: **52 chữ** ($\le 60$ chữ, ô D5 = `"Đạt"`).
    - **Ô B6 (Cần gì: người, tiền, dữ liệu)**: **53 chữ** ($\le 60$ chữ, ô D6 = `"Đạt"`).
    - **Ô B7 (Rủi ro lớn nhất & cách xử lý)**: **58 chữ** ($\le 60$ chữ, ô D7 = `"Đạt"`).
    - **Ô B8 (Khi nào xem lại)**: **47 chữ** ($\le 60$ chữ, ô D8 = `"Đạt"`).
  - Cả **5/5 ô nội dung đều đạt chuẩn** (D4:D8 hiển thị `"Đạt"`), đáp ứng nghiêm ngặt tiêu chí súc tích, đi thẳng vào kết luận và số liệu đo lường.
- **Thẩm định tính toàn vẹn của file slide `5aesieunhan_CS13_Slide.pptx`**:
  - File slide bao gồm đúng **1 slide duy nhất**, bố cục chuyên nghiệp, trực quan theo chuẩn slide báo cáo lãnh đạo.
  - Nội dung text trên từng phân khu của slide khớp chính xác $100\%$ từng câu chữ với các ô tương ứng từ **B4 đến B8** trên trang `5_Slide lãnh đạo`.
- **Đối chiếu số liệu then chốt giữa slide và workbook**:
  - Toàn bộ các con số định lượng xuất hiện trên slide đều ăn khớp hoàn toàn với các bảng tính chi tiết tại trang 2 (`2_Mức tự động`) và trang 3 (`3_Bảng lộ trình`):
    - **15%**: Tỷ lệ việc có giáo viên duyệt ở Mức 1 (khớp `2_Mức tự động!H6` và `3_Bảng lộ trình!B8`).
    - **1.919 đ**: Chi phí mỗi việc ở Mức 1 sau khi tối ưu (khớp `2_Mức tự động!J6` và `3_Bảng lộ trình!B11`).
    - **63,2%**: Biên lợi nhuận gộp ở Mức 1 (khớp `2_Mức tự động!K6` và `3_Bảng lộ trình!B11`).
    - **14,2 giờ**: Tổng thời gian cô Lan và thầy Khoa chạy lại bộ đề 40 bài (khớp hồ sơ và `3_Bảng lộ trình!B10`).
    - **tháng 17**: Mốc thời gian cạn vốn trong kịch bản xấu của đề (khớp `2_Mức tự động!B20` và `3_Bảng lộ trình!C11`).
    - **3,95 triệu**: Mức sàn doanh thu bình quân/trung tâm để kích hoạt dừng mở rộng (khớp `2_Mức tự động!B19` và `3_Bảng lộ trình!B12`).
    - **≥15 trung tâm**: Quy mô cỡ mẫu trung tâm tối thiểu nhằm đảm bảo tính tin cậy của điều kiện dừng (khớp `2_Mức tự động!B19` và `3_Bảng lộ trình!B12`).

## 4. Đóng góp cụ thể

Với vai trò **QA & tích hợp** cho toàn bộ dự án nhóm 5aesieunhan, tôi (Phạm Thành Đạt — MSSV 2A202602721) đã thực hiện các đóng góp cốt lõi:
1. **Thiết lập nền tảng kiểm định và đối chiếu hồ sơ (CP1)**: Đọc độc lập 6 phần hồ sơ tình huống Đề 2 (ChấmNhanh); điền đầy đủ và chính xác ô B5:B10 kèm 6 ghi chú chi tiết E5:E10 tại trang `0_Đầu vào`; kích hoạt công thức B12 đạt 6/6; kiểm tra chéo toàn bộ 7 việc tại `1_Danh sách việc` đạt 7/7 "Có" về giả thuyết và chỉ số có ngưỡng định lượng.
2. **Thẩm định công thức xếp hạng ưu tiên và quyết định triển khai (CP2)**: Tái tính toán độc lập điểm số theo công thức RICE kết hợp mức sẵn sàng dữ liệu/đánh giá và rủi ro bị nuốt; bảo vệ tính đúng đắn của việc chọn Mua cho Việc 4 (rủi ro bị nuốt 1,0 do thị trường đã có công cụ miễn phí làm tốt) và tập trung Tự làm cho Việc 3, 1, 7.
3. **Phát hiện mâu thuẫn nguồn lực chuyên gia và chuẩn hóa kinh tế (CP3)**:
   - Tính toán biên lợi nhuận gộp từng mức tự động, chứng minh Mức 0 chịu lỗ âm (-34,7%) và tìm ra tỷ lệ duyệt trần 17,75% để giữ biên gộp Mức 1 trên 60%.
   - Thẩm định 3 cổng đánh giá theo quy tắc $3/n$ ($n=100 \rightarrow 3\%$, $n=200 \rightarrow 1{,}5\%$) và ngưỡng 70% khớp thực tế giữa hai giáo viên giỏi.
   - Phát hiện điểm mâu thuẫn nghiêm trọng trong kế hoạch ban đầu: chuyên gia chỉ có 4 giờ/tuần nhưng lại phải gánh 14,2 giờ chạy lại bộ đề 40 bài (tuần 3–6) cộng với 100 bài chấm đôi trong 5 tuần (khoảng 20 bài/tuần). Trực tiếp đề xuất và thực hiện giải pháp chuyển việc chấm đôi sang giáo viên duyệt công ty (đã bao hàm trong chi phí 3 phút/bài), rút ngắn tiến độ tích lũy 100 bài xuống 4 tuần (~30 bài/tuần) và giải phóng chuyên gia chỉ tập trung xác nhận cổng. Cập nhật trực tiếp vào file Excel tại `2_Mức tự động!F7` và `3_Bảng lộ trình!C10`.
4. **Kiểm soát tính nhất quán và hoàn thiện hồ sơ dự án (CP4)**: Kiểm định 8/8 dòng tầng Bây giờ tại `3_Bảng lộ trình`, định dạng điều kiện dừng theo chuẩn NẾU…THÌ, thẩm định lịch rà soát 3 mốc thời gian và 3 sự kiện kích hoạt tại `4_Rà soát`, đối chiếu 8/8 tiêu chí Đạt tại `6_Tự kiểm tra`; cập nhật thông tin nhóm tại `team/TEAM.md` và `README.md`.
5. **Đảm bảo chất lượng sản phẩm bàn giao lãnh đạo (CP5)**: Đếm và kiểm soát độ dài các ô văn bản tại `5_Slide lãnh đạo` (34, 52, 53, 58, 47 chữ, tất cả $\le 60$ chữ); thẩm định file slide `5aesieunhan_CS13_Slide.pptx` đạt độ chuẩn xác 100% so với dữ liệu mô hình trong bảng tính.

## 5. Bằng chứng

Toàn bộ đóng góp được minh chứng rõ ràng thông qua 5 commits tuần tự và các vị trí ô/file trong repository:
- **Commit 1 (`feat(cp1): mark case file sections read in 0_Đầu vào`)**:
  - Ô `0_Đầu vào!B5:B10` = "Có", `0_Đầu vào!E5:E10` (6 ghi chú đối chiếu hồ sơ).
  - Ô `0_Đầu vào!B12` hiển thị `6/6` (công thức `=COUNTIF(B5:B10,"Có")`).
  - Cột `1_Danh sách việc!O5:O11` hiển thị "Có" cho toàn bộ 7/7 việc.
- **Commit 2 (`docs(cp2): verify priority scores and decisions`)**:
  - Báo cáo thẩm định điểm ưu tiên tại `report/team/2A202602721_PhamThanhDat.md#cp2`.
  - Ô `1_Danh sách việc!M5:M11` (8,07; 5,10; 4,84; 4,75; 1,27; 0,99; 0,54) và thứ tự việc chính tại `3_Bảng lộ trình!B5`.
- **Commit 3 (`fix(cp3): align double-grading timeline with expert hours`)**:
  - Ô `2_Mức tự động!F7`: cập nhật mô tả giáo viên công ty chấm đôi ~30 bài/tuần trong 4 tuần, chuyên gia rà bài lệch và xác nhận cổng.
  - Ô `3_Bảng lộ trình!C10`: cập nhật cụm từ `(giáo viên duyệt của công ty chấm đôi ~30 bài/tuần, khoảng 4 tuần; chuyên gia chỉ xác nhận)`.
  - Báo cáo phân tích kinh tế, ngưỡng duyệt trần 17,75% và quy tắc $3/n$ tại `report/team/2A202602721_PhamThanhDat.md#cp3`.
- **Commit 4 (`docs(cp4): fill team info and submission README`)**:
  - File `team/TEAM.md`: bảng phân công 5 thành viên với MSSV và phân định bằng chứng rõ ràng.
  - File `README.md`: mục nộp bài nhóm 5aesieunhan ở đầu file và cập nhật bảng phân công song song.
  - Trang tính `3_Bảng lộ trình!B5:B12` (8/8 ô), `4_Rà soát!A5:D10`, và `6_Tự kiểm tra!C5:C12` (8/8 Đạt).
- **Commit 5 (`docs(cp5): verify leadership slide against workbook`)**:
  - Ô `5_Slide lãnh đạo!B4:B8` có số từ lần lượt 34, 52, 53, 58, 47 chữ (ô D4:D8 đều "Đạt").
  - File `5aesieunhan_CS13_Slide.pptx`: 1 slide duy nhất khớp nội dung B4:B8 và 7 số liệu kỹ thuật - kinh tế.
  - Báo cáo hoàn chỉnh tại `report/team/2A202602721_PhamThanhDat.md`.

## 6. Tự đánh giá

- **Điều hiểu rõ**:
  - *Quy tắc xác suất $3/n$ trong đánh giá chất lượng mô hình AI*: Khi kiểm định trên mẫu ngẫu nhiên gồm $n$ bài viết và quan sát thấy $0$ lỗi nghiêm trọng (bài lệch $>1$ điểm), cận trên của khoảng tin cậy 95% cho tỷ lệ lỗi thực tế trong toàn bộ quần thể là xấp xỉ $3/n$. Với $n = 100$ bài thật, ta bảo đảm được tỷ lệ lỗi nghiêm trọng không vượt quá $\approx 3/100 = 3\%$; với $n = 200$ bài (qua 2 đợt liên tiếp tại Mức 3), tỷ lệ lỗi được bảo đảm dưới $\approx 3/200 = 1{,}5\%$. Đây là cơ sở thống kê vững chắc giúp nhóm tự tin thiết kế cổng lên mức tự động mà không cần tốn chi phí kiểm tra toàn diện $100\%$ bài viết.
  - *Tính thực tế trong quản trị sản phẩm AI*: Không chạy theo các con số ảo tưởng hay kỳ vọng quá mức; nhận thức rõ giới hạn con người (hai giáo viên giỏi cũng chỉ khớp nhau ~70% trong 0,5 điểm) để thiết lập cổng đánh giá máy phù hợp, tránh over-engineering.
- **Giả định còn cần kiểm chứng**:
  - Giả định rằng **tỷ lệ bài thực tế rơi vào vùng ranh giới 5,0–6,5 và bài thuộc tầng Khó chỉ chiếm khoảng 15%** (Mức 1). Hiện tại, con số 15% này là giả định của nhóm (vùng 5,0–6,5 + tầng Khó + mẫu chấm đôi 2%), chưa được kiểm chứng trên tập dữ liệu bài viết thật quy mô lớn tại các trung tâm đối tác.
  - *Rủi ro vận hành*: Nếu khi triển khai diện rộng, tỷ lệ bài viết phân bố vào tầng Khó hoặc vùng ranh giới vượt quá **17,75%**, chi phí duyệt bài (với giá 6.000 đ/lần duyệt) sẽ ăn mòn lợi nhuận và kéo biên lợi nhuận gộp của Mức 1 xuống dưới ngưỡng sống còn $60\%$. Do đó, chỉ số phân bố độ khó thực tế của bài viết học sinh là biến số quan trọng nhất cần được đo lường và thẩm định nghiêm ngặt tại đợt rà soát Ngày 30.

