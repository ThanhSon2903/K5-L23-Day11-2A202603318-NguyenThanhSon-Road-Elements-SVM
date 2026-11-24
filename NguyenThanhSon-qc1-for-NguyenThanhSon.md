
# Phiếu QC 1 — Road v1.0

**Lô được kiểm (học viên):** Nguyễn Thanh Sơn  
**Người kiểm (học viên):** Nguyễn Thanh Sơn  
**Ngày:** 21/11/2026  
**Phiên bản guideline:** Road v1.0  
**File được kiểm (tên + `revision` trong manifest):**
- `NguyenThanhSon-front.zip`
- `NguyenThanhSon-fisheye.zip`
- `NguyenThanhSon-manifest.json` — revision 1

**Số ảnh kiểm:** 34 ảnh (6 ảnh mẫu + 28 ảnh thêm).  
**Số nhãn đã kiểm (shape + tag):** Chưa thống kê riêng.

## Tổng hợp theo mã

| Mã | Loại lỗi | Số mục kiểm | Số lỗi/cảnh báo lint | Mức |
|---|---|---:|---:|---|
| QC1-01 | Tag camera | — | 0 | Nặng |
| QC1-02 | Đủ L1, R1 | — | 2 | Nặng |
| QC1-03 | Position | — | 0 | Nặng |
| QC1-04 | Tâm vạch, chiều, điểm dừng | — | 0 | Chính |
| QC1-05 | Vạch đứt, che | — | 0 | Chính |
| QC1-06 | Style, color, kind | — | 0 | Chính |
| QC1-07 | Vùng lái | — | 0 | Chính |
| QC1-08 | Đèn, màu | — | 1 | Nhẹ |
| QC1-09 | Facing, type, group, biển phụ | — | 0 | Chính |
| QC1-10 | Hình in, đủ biển | — | 8 | Nhẹ |
| QC1-11 | Fisheye | — | 8 | Chính |
| QC1-12 | File | — | 12 | Nhẹ |
| **Tổng** | | | **31** | |

*Lưu ý: Đây là số cảnh báo do lint phát hiện, chưa phải số lỗi thực tế đã được người kiểm xác nhận.*

## Danh sách lỗi (mỗi lỗi một dòng)

| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
|---:|---|---|---|---|---|
| 1 | QC1-12 | B01 | File export | Nhẹ | Ảnh xuất hiện 2 lần trong export; kiểm tra upload trùng hoặc export cấp project. Giữ bản có nhiều nhãn nhất, xóa bản thừa và export lại từ task. |
| 2 | QC1-12 | B02 | File export | Nhẹ | Ảnh xuất hiện 2 lần trong export; kiểm tra upload trùng hoặc export cấp project. |
| 3 | QC1-12 | B03 | File export | Nhẹ | Ảnh xuất hiện 2 lần trong export; kiểm tra upload trùng hoặc export cấp project. |
| 4 | QC1-12 | B04 | File export | Nhẹ | Ảnh xuất hiện 2 lần trong export; kiểm tra upload trùng hoặc export cấp project. |
| 5 | QC1-12 | B05 | File export | Nhẹ | Ảnh xuất hiện 2 lần trong export; kiểm tra upload trùng hoặc export cấp project. |
| 6 | QC1-12 | B06 | File export | Nhẹ | Ảnh xuất hiện 2 lần trong export; kiểm tra upload trùng hoặc export cấp project. |
| 7 | QC1-10 | A04 | traffic_sign #0 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 8 | QC1-10 | A04 | traffic_sign #6 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 9 | QC1-10 | A04 | traffic_sign #9 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 10 | QC1-08 | A04 | traffic_light #10 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 11 | QC1-12 | A05 | drivable #0 | Nhẹ | Có 1 điểm lặp liền nhau, cần xóa điểm thừa. |
| 12 | QC1-02 | A05 | lane | Nặng | Chưa có L1; bỏ qua nếu thực sự không thấy vạch. |
| 13 | QC1-02 | A05 | lane | Nặng | Chưa có R1; bỏ qua nếu thực sự không thấy vạch. |
| 14 | QC1-12 | A10 | drivable #20 | Nhẹ | Có 1 điểm lặp liền nhau, cần xóa điểm thừa. |
| 15 | QC1-10 | A10 | traffic_sign #2 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 16 | QC1-10 | A10 | traffic_sign #5 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 17 | QC1-10 | A10 | traffic_sign #6 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 18 | QC1-12 | B01 | road_curb #5 | Nhẹ | Có 1 điểm lặp liền nhau, cần xóa điểm thừa. |
| 19 | QC1-12 | B01 | road_curb #4 | Nhẹ | Có 1 điểm lặp liền nhau, cần xóa điểm thừa. |
| 20 | QC1-11 | B02 | traffic_light #3 | Chính | Gợi ý edge_zone = bật (tâm box ngoài 80% bán kính; tự kiểm lại). |
| 21 | QC1-11 | B02 | traffic_light #4 | Chính | Gợi ý edge_zone = bật (tâm box ngoài 80% bán kính; tự kiểm lại). |
| 22 | QC1-11 | B02 | traffic_light #0 | Chính | Gợi ý edge_zone = bật (tâm box ngoài 80% bán kính; tự kiểm lại). |
| 23 | QC1-11 | B02 | traffic_light #6 | Chính | Gợi ý edge_zone = bật (tâm box ngoài 80% bán kính; tự kiểm lại). |
| 24 | QC1-10 | B03 | traffic_sign #2 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 25 | QC1-10 | B03 | traffic_sign #7 | Nhẹ | Box thấp hơn 8 px, không bắt buộc. |
| 26 | QC1-11 | B04 | traffic_sign #0 | Chính | Gợi ý edge_zone = bật (tâm box ngoài 80% bán kính; tự kiểm lại). |
| 27 | QC1-11 | B04 | traffic_sign #2 | Chính | Gợi ý edge_zone = bật (tâm box ngoài 80% bán kính; tự kiểm lại). |
| 28 | QC1-11 | B07 | lane #6 | Chính | Chỉ 3 điểm: trên fisheye hãy đặt điểm theo cung. |
| 29 | QC1-12 | B09 | crosswalk #2 | Nhẹ | Có 1 điểm lặp liền nhau, cần xóa điểm thừa. |
| 30 | QC1-12 | B10 | drivable #2 | Nhẹ | Có 3 điểm lặp liền nhau, cần xóa điểm thừa. |
| 31 | QC1-11 | B10 | traffic_sign #1 | Chính | Gợi ý edge_zone = bật (tâm box ngoài 80% bán kính; tự kiểm lại). |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
|---|---|---|
| A05 | Nếu thực sự không thấy vạch L1 và R1 thì có được bỏ qua không? | Chưa có |
| B02, B04, B10 | Các đối tượng nằm sát rìa ảnh fisheye có cần bật edge_zone không? | Chưa có |
| B07 | Đường lane trên fisheye cần đặt bao nhiêu điểm để thể hiện đúng độ cong? | Chưa có |

## Quyết định

- **Lỗi nặng:** 2 cảnh báo.
- **Lỗi chính:** 8 cảnh báo.
- **Lỗi nhẹ:** 21 cảnh báo.
- **Ca chờ lead:** 3 nhóm vấn đề.
- **Tổng:** 31 cảnh báo lint.

**Quyết định: HOLD (tạm giữ để kiểm tra và sửa).**

**Lý do:**
1. Kiểm tra lại hai cảnh báo thiếu L1 và R1 tại A05. Nếu thực sự không thấy vạch thì có thể bỏ qua theo guideline.
2. Kiểm tra thuộc tính edge_zone tại B02, B04 và B10.
3. Chỉnh các polygon có điểm lặp và kiểm tra đường lane tại B07.
4. Xử lý ảnh bị trùng trong export B01–B06.
5. Các cảnh báo box thấp hơn 8 px không bắt buộc chỉnh sửa, cần đối chiếu guideline trước khi quyết định.

**Ghi chú:** Lint chỉ mang tính gợi ý. GT và người kiểm mới quyết định lỗi thực tế. Chỉ chuyển sang Release sau khi hoàn thành kiểm tra và xử lý các vấn đề cần thiết.
