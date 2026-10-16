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
