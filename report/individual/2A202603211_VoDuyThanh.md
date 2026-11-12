# Báo cáo thực hành Day 3 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên [LMS](https://aithucchien.vinuni.edu.vn). Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](../../reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202603211
- Ngày / CVAT local: 12/11/2026
- Công cụ đã dùng: CVAT local

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh [LMS](https://aithucchien.vinuni.edu.vn) đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task            | File ZIP đúng tên   | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
| --------------- | ------------------- | -----------------: | ---------------------------: |
| easy_semantic   | easy_semantic.zip   |              3 / 3 |                           20 |
| medium_instance | medium_instance.zip |              3 / 3 |                           32 |
| hard_panoptic   | hard_panoptic.zip   |              2 / 2 |                           30 |
| cp1_holes       | cp1_holes.zip       |              1 / 1 |                            3 |
| cp2_slice       | cp2_slice.zip       |              1 / 1 |                            3 |
| cp5_occlusion   | cp5_occlusion.zip   |              1 / 1 |                            3 |
| cp3_thin        | cp3_thin.zip        |              1 / 1 |                            3 |
| cp4_curb        | cp4_curb.zip        |              1 / 1 |                            3 |
| cp6_coverage    | cp6_coverage.zip    |              1 / 1 |                            3 |
| **Tổng tối đa** |                     |                    |                      **100** |

Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: Ảnh 1, xe mô tô có người phụ nữ đi trước che khuất một phần xe
- Class và quy tắc tôi dùng để chọn biên: motorcycle, gán 2 object như thể 2 phần cho cùng 1 chiếc xe
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: Không dùng, gán nhãn 2 object cho cùng 1 xe, 1 phần đầu xe và 1 phần thân xe do bị người phụ nữ che khuất phần giữa
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Tôi chưa tìm thấy và sửa lỗi nào trong bài

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí                                 | Hai cách hiểu có thể                    | Quy tắc/chứng cứ                                                       | Quyết định hoặc câu hỏi cho coach                     |
| ------------------------------------------ | --------------------------------------- | ---------------------------------------------------------------------- | ----------------------------------------------------- |
| cp1_holes: xe SUV                          | Xe SUV này liệt vào dạng car hay truck? | Hình dạng phương tiện là một chiếc xe SUV có thể chở cả người lẫn hàng | nên có một label riêng cho SUV?                       |
| các loại cây không có lá hoặc màu xanh lá  | phân vào label `vegetation` hoặc `pole` | các loại cây này không có màu xanh, dễ nhầm lẫn sang các cây cột       | phân vào `vegetation`                                 |
| cp6_coverage: Phần đường bên dưới building | thuộc `sidewalk` hoặc thuộc `building`  | phần đường nằm ngay dưới tòa nhà và nối liền sidewalk                  | chưa quyết định được nhưng có thể thêm vào `sidewalk` |

