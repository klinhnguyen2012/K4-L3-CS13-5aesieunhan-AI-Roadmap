# CS13 — Lộ trình sản phẩm AI

## Bài làm của nhóm 5aesieunhan

- **Số nhóm**: Nhóm 5 (5aesieunhan)
- **Đề tài**: Đề 2 · ChấmNhanh — chấm bài viết tiếng Anh
- **Danh sách file nộp bài**:
  - File Excel lộ trình sản phẩm: [`5aesieunhan_CS13.xlsx`](5aesieunhan_CS13.xlsx)
  - File slide thuyết trình lãnh đạo (1 slide): [`5aesieunhan_CS13_Slide.pptx`](5aesieunhan_CS13_Slide.pptx)
  - Thông tin phân công và bằng chứng nhóm: [`team/TEAM.md`](team/TEAM.md)
  - Báo cáo cá nhân các thành viên:
    - Nguyễn Khánh Linh (Mức tự động · CP3): [`report/team/2A202602409_NguyenKhanhLinh.md`](report/team/2A202602409_NguyenKhanhLinh.md)
    - Bùi Thị Ngọc Trân (Lộ trình & slide · CP4 + CP5): [`report/team/2A202602529_BuiThiNgocTran.md`](report/team/2A202602529_BuiThiNgocTran.md)
    - Ngô Lê Thuỷ Tiên (Danh sách việc 1–3, 7 · CP1 + CP2): [`report/team/2A202602614_NgoLeThuyTien.md`](report/team/2A202602614_NgoLeThuyTien.md)
    - Đinh Thị Minh Tâm (Danh sách việc 4–6 · CP1 + CP2): [`report/team/2A202602433_DinhThiMinhTam.md`](report/team/2A202602433_DinhThiMinhTam.md)
    - Phạm Thành Đạt (QA & tích hợp · CP1 Nhiệm vụ 0 + kiểm tra chéo CP1–CP5): [`report/team/2A202602721_PhamThanhDat.md`](report/team/2A202602721_PhamThanhDat.md)

**AI in Action · Track 1 · Khóa 4 · Level 3 dùng chung · Chiều 16/10/2026**

Trong bài này, nhóm bạn lập lộ trình 12 tháng cho một sản phẩm AI: làm gì trước, dựa vào bằng chứng nào, khi nào tăng mức tự động và khi nào dừng. Sản phẩm cuối là **một file Excel của nhóm** và **một slide cho lãnh đạo**, lưu trong repo GitHub của nhóm. Mỗi thành viên nộp cùng link repo trên VLearn. Bạn không cần viết code, cài Python hay có API key.

## Bắt đầu từ đâu?

1. Xem [luật làm bài](RULES.md), rồi xác định đề của nhóm trong bảng dưới.
2. Tải [hồ sơ tình huống](docs/CS13_HoSoTinhHuong.pdf) và file Excel tương ứng về máy. Mở bằng Excel hoặc LibreOffice.
3. Lưu một bản làm bài tên `[Nhom]_CS13.xlsx`, thay `[Nhom]` bằng tên nhóm thực tế.
4. Tạo repo nhóm theo [SUBMISSION.md](SUBMISSION.md). Làm lần lượt CP1 → CP4 trong [CHECKPOINTS.md](CHECKPOINTS.md); CP5 làm ở nhà.

| Số nhóm | Đề | File Excel cần tải |
|---|---|---|
| 1, 4, 7, 10 và các nhóm cách nhau 3 số | 1 · SổSạch — đọc hóa đơn đầu vào | [CS13_Roadmap_De1.xlsx](src/CS13_Roadmap_De1.xlsx) |
| 2, 5, 8, 11 và các nhóm cách nhau 3 số | 2 · ChấmNhanh — chấm bài viết tiếng Anh | [CS13_Roadmap_De2.xlsx](src/CS13_Roadmap_De2.xlsx) |
| 3, 6, 9, 12 và các nhóm cách nhau 3 số | 3 · RaViện — soạn nháp tóm tắt ra viện | [CS13_Roadmap_De3.xlsx](src/CS13_Roadmap_De3.xlsx) |

Nếu chưa biết số nhóm, hỏi coach trước khi chọn file. Nhóm chỉ dùng **một** file đề. Có thể chọn một người giữ file và chia sẻ màn hình để cả nhóm cùng quyết định.

**Chỉ điền ô vàng.** Ô xanh là công thức đã khóa. Số liệu kinh tế đã có ở trang `2_Mức tự động`, dòng 12–20; không cần tìm file của buổi khác. Khi cần xem cách diễn đạt, mở [bản mẫu cho một sản phẩm khác](src/CS13_Roadmap_Mau.xlsx); đừng chép số của mẫu sang đề của nhóm.

## Cần hoàn thành gì trong 60 phút?

| Giờ ngày 16/10/2026 | Checkpoint | Kết quả cần có |
|---|---|---|
| 17:00–17:17 | CP1 · Đọc hồ sơ, viết giả thuyết | Đọc đủ 6 mục; ít nhất 5 việc có giả thuyết, chỉ số và ngưỡng |
| 17:17–17:30 | CP2 · Chấm điểm ưu tiên | Ít nhất 5 việc có điểm; có lựa chọn và lý do |
| 17:30–17:43 | CP3 · Mức tự động và cổng | Ít nhất 2 mức có cổng; có vai trò người duyệt và căn cứ kinh tế |
| 17:43–17:55 | CP4 · Bảng lộ trình, rà soát | Tầng Bây giờ đủ 8 dòng; có điều kiện dừng và lịch rà soát |
| 17:55–18:00 | Kiểm tra và nộp | Tải Excel lên repo nhóm; mỗi người nộp link repo trên VLearn |
| Ở nhà, trước 23:59 ngày 19/10/2026 | CP5 · Slide lãnh đạo | Điền trang 5 và tạo 1 slide từ 5 ô nội dung |

Tất cả mốc giờ dùng giờ Việt Nam. Phần lý thuyết diễn ra 14:00–17:00; lịch trên chỉ dành cho thực hành. Bản chuẩn không có phần thuyết trình trên lớp.

## Phân công song song

Mỗi người đọc hồ sơ của đúng đề và làm độc lập phần được giao. Dùng cùng đơn vị “1 việc”, cùng thang điểm trong [CHECKPOINTS.md](CHECKPOINTS.md), và chỉ sửa các ô vàng trong Excel. Không chờ một người hoàn thành toàn bộ checkpoint rồi mới bắt đầu phần khác.

| Thành viên | Mã số sinh viên | Phần phụ trách | Phạm vi làm độc lập |
|---|---|---|---|
| Ngô Lê Thuỷ Tiên | 2A202602614 | Danh sách việc 1–3, 7 · CP1 + CP2 | Với 3 việc đầu trong danh sách đề và việc 7: điền giả thuyết, chỉ số/ngưỡng và các điểm F–L; đề xuất quyết định P cùng lý do Q. |
| Định Thị Minh Tâm | 2A202602433 | Danh sách việc 4–6 · CP1 + CP2 | Với 3 việc còn lại trong danh sách đề: điền giả thuyết, chỉ số/ngưỡng và các điểm F–L; đề xuất quyết định P cùng lý do Q. |
| Nguyễn Khánh Linh | 2A202602409 | Mức tự động · CP3 | Điền vai trò AI/người, điều kiện và cổng đánh giá ở trang 2; phân tích chi phí, biên lợi nhuận và người duyệt. Có thể đề xuất các mức cho những việc dự kiến ưu tiên; đánh dấu phần cần khớp lại sau khi nhóm chốt lựa chọn. |
| Bùi Thị Ngọc Trân | 2A202602529 | Lộ trình và slide · CP4 + CP5 | Dựa trên hồ sơ, soạn nháp tầng Bây giờ/Tiếp theo/Sau này, lịch rà soát và 5 ý cho slide. Đánh dấu chỗ phụ thuộc vào việc được chọn, cổng và số kinh tế để cập nhật khi tích hợp. |
| Phạm Thành Đạt | 2A202602721 | QA & tích hợp · CP1 Nhiệm vụ 0 + kiểm tra chéo CP1–CP5 | Điền 0_Đầu vào; tính lại điểm, chi phí, biên; đối chiếu số liệu trang 1–5 với hồ sơ; kiểm tra slide ≤60 chữ; điền TEAM.md và README nhóm. |

### Ghép kết quả

1. Tiên và Tâm nhập kết quả vào các dòng riêng trên `1_Danh sách việc`; không sửa dòng của nhau. Hai bạn cùng kiểm tra đủ ít nhất 5 việc có giả thuyết, chỉ số, ngưỡng và quyết định.
2. Linh đối chiếu lựa chọn ưu tiên với các mức tự động và cổng. Nhóm chốt ít nhất 2 cổng có chỉ số, ngưỡng, cỡ mẫu và người xác nhận; xử lý đúng trạng thái phát hành của đề.
3. Trân thay phần đánh dấu trong lộ trình/slide bằng các quyết định, cổng và số kinh tế đã chốt. Nhóm cùng rà sự nhất quán giữa trang 1–5, điều kiện dừng và nội dung slide.

Các phần có thể được soạn đồng thời; bước ghép cuối cần chờ để CP3 khớp với việc được chọn và CP4/CP5 khớp với toàn bộ quyết định. Rubric chấm theo tiêu chí, không chia đều điểm cho từng người. Mỗi thành viên cùng đọc hồ sơ và xác nhận nội dung cuối trước khi nộp.

## Đọc thêm ở đâu?

- [CHECKPOINTS.md](CHECKPOINTS.md): từng bước điền, cách hiểu và tự kiểm tra.
- [src/README.md](src/README.md): bản đồ các trang Excel và lỗi thường gặp.
- [RUBRIC.md](RUBRIC.md): thang chấm chính thức 100 điểm.
- [SUBMISSION.md](SUBMISSION.md): hai lần nộp và checklist.
- [docs/README.md](docs/README.md): hồ sơ và slide bài giảng gốc.

Điền [team/TEAM.md](team/TEAM.md) để người chấm biết thành viên và đóng góp. Các mẫu trong `report/team/` dùng để ghi chép thêm nếu cần; bài làm chính là Excel và slide trong repo nhóm. Xem cách tạo repo, tải file và nộp link tại [SUBMISSION.md](SUBMISSION.md).
