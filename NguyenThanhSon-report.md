
# Báo cáo cá nhân — Ngày 11

**Họ tên:** Nguyễn Thanh Sơn  
**Mã học viên:** 2A202603318  
**Phiên bản CVAT (Help → About):** Chưa ghi nhận  
**Guideline:** Road v1.0  
**Lần nộp (`revision` trong manifest):** 1  
**Thời điểm export (ngày giờ trên CVAT):** 24/11/2026  
**Số lần nộp lại sau Rework:** 0 (chưa xác nhận có Rework)

## 1. Kiểm project

| Mục | Đúng như guideline Road v1.0? | Ghi chú |
|---|---|---|
| 6 label, đúng kiểu | Có | Sử dụng 6 label: lane, road_curb, crosswalk, drivable, traffic_light, traffic_sign |
| Thuộc tính và giá trị | Đã kiểm tra, cần QC lại | Đối chiếu các thuộc tính và giá trị theo guideline |
| 4 tag ảnh | Đã thiết lập, cần QC lại | Kiểm tra tag camera và các thuộc tính ảnh |

**Cách kết thúc polyline trên bản CVAT này:** Sử dụng thao tác kết thúc polyline trên giao diện CVAT sau khi đặt đủ các điểm theo hình dạng đối tượng, tránh đặt các điểm trùng nhau.

**Cách đặt tag ảnh trên bản CVAT này:** Chọn ảnh cần gán nhãn, thiết lập các tag ảnh theo guideline Road v1.0 và kiểm tra lại giá trị trước khi chuyển sang ảnh tiếp theo.

## 2. Số lượng đã gán

| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
|---|---:|---:|---:|---:|---:|---:|---:|
| front | 12 | Chưa thống kê | Chưa thống kê | Chưa thống kê | Chưa thống kê | Chưa thống kê | Chưa thống kê |
| front-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| fisheye | 8 | Chưa thống kê | Chưa thống kê | Chưa thống kê | Chưa thống kê | Chưa thống kê | Chưa thống kê |
| fisheye-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

## 3. Bảng ca khó

| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
|---|---|---|---|---|
| A05 | lane | Có cần gán L1 và R1 hay không | Kiểm tra lại ảnh gốc | Chỉ gán khi thực sự quan sát được vạch |
| B02 | traffic_light | Bật hoặc không bật edge_zone | Kiểm tra lại | Đối tượng nằm sát rìa ảnh fisheye |
| B04 | traffic_sign | Bật hoặc không bật edge_zone | Kiểm tra lại | Tâm box nằm ngoài 80% bán kính |
| B07 | lane | Đường cong và số lượng điểm | Bổ sung điểm theo cung | Polyline trên ảnh fisheye cần thể hiện đúng độ cong |
| B10 | traffic_sign | Bật hoặc không bật edge_zone | Kiểm tra lại | Đối tượng nằm sát rìa ảnh fisheye |

## 4. Phiếu QC 1 nhận được

**Bạn kiểm lô của tôi:** Tự kiểm tra bằng công cụ lint Road Lab.  
**Quyết định nhận được:** HOLD (tạm giữ để kiểm tra và sửa).

| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
|---|---:|---|---|
| QC1-02 | 2 | Cần đối chiếu ảnh A05 | Chưa |
| QC1-08 | 1 | Cần kiểm tra box traffic_light | Chưa |
| QC1-10 | 8 | Cần kiểm tra, box thấp hơn 8 px không bắt buộc | Chưa |
| QC1-11 | 8 | Cần kiểm tra edge_zone và polyline fisheye | Chưa |
| QC1-12 | 12 | Đồng ý cần kiểm tra ảnh trùng và điểm lặp | Chưa |
| **Tổng** | **31** | | |

**Kết quả lint:** 34 ảnh, 31 cảnh báo.

## 5. Kiểm file export

| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
|---|---|---|---|---|
| NguyenThanhSon-front.zip | Có, lint đọc được | Chưa thống kê | Chưa thống kê | Chưa kiểm tra |
| NguyenThanhSon-fisheye.zip | Có, lint đọc được | Chưa thống kê | Chưa thống kê | Chưa kiểm tra |

**Manifest:** `NguyenThanhSon-manifest.json`  
**Revision:** 1

## 6. Ảnh chụp màn hình

1. [ ] Tab Labels của project.
2. [ ] Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển).
3. [ ] Một ảnh fisheye đã gán, phóng to đoạn polyline cong.
4. [ ] Một đoạn XML có `<polyline label="lane">`.

## 7. Tự đánh giá

**Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20:**

Lỗi có nhiều cảnh báo nhất của em là QC1-12 với 12 cảnh báo. Các vấn đề chủ yếu liên quan đến ảnh xuất hiện trùng trong file export và các điểm polygon bị lặp liên tiếp.

Nguyên nhân có thể do thao tác click hai lần tại cùng một vị trí hoặc chưa kiểm tra kỹ dữ liệu sau khi gán nhãn.

Để tránh lặp lại lỗi ở Ngày 20, em sẽ chú ý hơn khi đặt các điểm polygon, kiểm tra lại các điểm trùng và đối chiếu số lượng ảnh trong file export với task trên CVAT trước khi nộp.

**Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào:**

Nhãn được sử dụng làm dữ liệu huấn luyện để model học cách nhận diện đối tượng, xác định vị trí và hình dạng của chúng trong ảnh.

Ví dụ, với nhãn `drivable`, nếu polygon có các điểm trùng hoặc đường biên không chính xác thì vùng đường có thể di chuyển được mô tả sai. Model sẽ học theo vùng dữ liệu không chính xác đó, dẫn đến dự đoán sai phạm vi mặt đường khi gặp ảnh mới.

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor

| y | 720 | 680 | 640 | 600 | 560 |
|---|---:|---:|---:|---:|---:|
| x của chúng tôi | Chưa đo | Chưa đo | Chưa đo | Chưa đo | Chưa đo |
| x của bạn kia | Chưa đo | Chưa đo | Chưa đo | Chưa đo | Chưa đo |

**1. Nếu bạn dừng polyline sớm 40 px, hàng nào đổi thành "không có làn"?**

Nếu polyline dừng sớm 40 px thì các hàng lấy mẫu nằm ngoài đoạn polyline sẽ không có tọa độ x tương ứng. Những hàng đó có thể bị đánh dấu là không có làn. Cần căn cứ vào vị trí điểm cuối và các hàng lấy mẫu thực tế để xác định chính xác hàng bị ảnh hưởng.

**2. So với bạn được kiểm (cùng ảnh): ở hàng 720 và hàng 560, hai bạn lệch nhau bao nhiêu pixel? Lệch ở hàng nào ảnh hưởng LKA nhiều hơn?**

Độ lệch được tính bằng giá trị tuyệt đối của hiệu hai tọa độ x tại cùng một hàng:

- Hàng 720: |x của chúng tôi - x của bạn kia|.
- Hàng 560: |x của chúng tôi - x của bạn kia|.

Sai lệch ở hàng 720 thường ảnh hưởng đáng kể đến việc xác định vị trí làn đường ở vùng gần xe, trong khi sai lệch ở hàng 560 ảnh hưởng đến việc xác định hướng và hình dạng làn đường ở vùng xa. Cần đối chiếu slide 25 để kết luận theo yêu cầu bài học.

**3. Nếu polyline vẽ từ xa về gần (ngược quy tắc 2), cách tính trên có đổi không? Script nào sẽ gặp khó?**

Về mặt toán học, cách tính tọa độ x tại từng hàng y không thay đổi. Tuy nhiên, nếu thứ tự các điểm bị đảo ngược thì script giả định polyline luôn được vẽ theo một chiều cố định có thể xử lý sai hoặc không nội suy đúng.

Do đó, script chuyển polyline thành row-anchor cần kiểm tra và chuẩn hóa thứ tự các điểm trước khi nội suy tọa độ.
