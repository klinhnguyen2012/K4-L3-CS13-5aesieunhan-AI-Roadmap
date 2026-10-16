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
