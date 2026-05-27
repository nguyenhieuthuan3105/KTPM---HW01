## Requirement 3: Test cases for ONE physical product (40 pts)

**Tổng quan:**

- **Thiết bị kiểm thử:** Máy lạnh (Air Conditioner)
- **Tổng số Test Cases đã thiết kế:** 15 (Chi tiết xem trong file Excel đính kèm `[MãSV]_HW01_TestCases.xlsx`)
- **Tổng số Lỗi (Defects) tìm thấy:** 5 (Đã log trên GitHub Issues)
- **Tổng số Video thực thi:** 5 (YouTube Unlisted)

---

### 1. Thông tin thiết bị & Minh chứng (Device Information & Anti-cheat)

- **Thiết bị (Device):** Máy lạnh treo tường
- **Thương hiệu (Brand):** [Sharp]
- **Dòng máy (Model):** [AH-X9XEW]
- **Năm sản xuất/Mua (Year):** [2021]
- **Số Seri (Serial Number):** [102****37]

**Ảnh minh chứng thiết bị (Kèm Thẻ sinh viên):**
![Ảnh máy lạnh và Thẻ sinh viên](/images/ac_with_student_card.jpg)

---

### 2. Phân tích Edge Cases bị AI bỏ sót (AI Edge Cases Analysis)

Trong quá trình dùng AI (Claude 3.5 Sonnet / ChatGPT) để tạo 15 Test Cases, AI chủ yếu tập trung vào các chức năng cơ bản (Bật/tắt, tăng giảm nhiệt độ, chuyển mode). Dưới đây là **3 trường hợp kiểm thử biên (Edge Cases)** liên quan đến tương tác vật lý và môi trường mà AI đã hoàn toàn bỏ sót.

**Minh chứng AI bỏ sót:**
![Screenshot AI không tạo ra các Edge Cases này](/images/ai_missed_1.png)
![Screenshot AI không tạo ra các Edge Cases này](/images/ai_missed_2.png)
![Screenshot AI không tạo ra các Edge Cases này](/images/ai_missed_3.png)

**Chi tiết 3 Edge Cases do sinh viên tự bổ sung:**

- **Edge Case 1: Kiểm tra giới hạn nhiệt độ tối đa.**
  - _Lý do AI bỏ sót:_ Vì đối tượng kiểm thử là "máy lạnh", AI mặc định tập trung vào kiểm thử biên dưới (nhiệt độ tối thiểu 16°C) và các chế độ làm mát mà bỏ quên việc kiểm thử phân tích giá trị biên cho biên trên (nhiệt độ tối đa 30°C - 32°C) của dải vận hành hệ thống.

- **Edge Case 2: Máy lạnh đang chạy, tắt cầu dao, sau đó bật trở lại.**
  - _Lý do AI bỏ sót:_ AI hoạt động dựa trên giả định môi trường lý tưởng, nơi nguồn điện luôn ổn định và mọi luồng điều khiển đều qua Remote (Happy Path). AI thiếu tư duy về Kiểm thử khả năng phục hồi của phần cứng trước các sự cố vật lý ngoài môi trường thực tế (Mất điện đột ngột).

- **Edge Case 3: Máy lạnh đang chạy, tắt cầu dao, sau đó bấm lệnh tắt trên remote. Bật cầu dao trở lại.**
  - _Lý do AI bỏ sót:_ AI chỉ mô phỏng các chuỗi hành vi tuần tự. Nó không thể tự dự đoán được kịch bản Bất đồng bộ trạng thái giữa một giao thức không lưu trạng thái và trạng thái lưu trong bộ nhớ tĩnh của bo mạch dàn lạnh khi nguồn điện vật lý bị ngắt quãng.

---

### 3. Báo cáo Lỗi (Defect Tracking - GitHub Issues)

Trong quá trình thực thi kiểm thử trên thiết bị thực tế, tôi đã tìm ra 5 lỗi (defects/bugs) và tiến hành log lên hệ thống GitHub Issues.

- **Link GitHub Repository:** [Dán link repo của bạn vào đây, VD: https://github.com/username/QAQC-HW01-AirConditioner]

**Ảnh minh chứng GitHub Issues:**
![GitHub Issues Log](/images/github_issues_bugs.png)
_(Lưu ý: Ảnh chụp màn hình danh sách 5 bugs trên trang Issues, GÓC MÀN HÌNH PHẢI THẤY RÕ USERNAME GITHUB CỦA BẠN)_

**Danh sách tóm tắt 5 Bugs:**

1. [Bug 1: VD - Màn hình Remote bị mờ/mất nét khi nhìn nghiêng góc 45 độ]
2. [Bug 2: VD - Cánh đảo gió (Swing) phát ra tiếng kêu cọt kẹt khi bật chế độ Quiet]
3. [Bug 3: VD - Ứng dụng điều khiển qua Wi-Fi mất kết nối khi đổi sang mạng 5GHz]
4. [Bug 4: VD - Nhấn nút Sleep nhưng đèn LED trên dàn lạnh không tắt hoàn toàn]
5. [Bug 5: VD - Remote không gửi được tín hiệu nếu bị che khuất một phần mắt hồng ngoại]

---

### 4. Bằng chứng Thực thi (Test Execution Videos)

Dưới đây là 5 video thực thi kiểm thử trực tiếp trên máy lạnh.
_(Ghi chú: Tất cả video đều có giọng nói thuyết minh (voice narration) của sinh viên theo đúng yêu cầu Anti-cheat)._

| ID    | Tên Test Case (Test Scenario)                                           | Link Video (YouTube Unlisted)                      |
| :---- | :---------------------------------------------------------------------- | :------------------------------------------------- |
| TC-01 | Kiểm tra tính năng hẹn giờ tắt máy (Timer Off)                          | `[Dán link YouTube, VD: https://youtu.be/abcd123]` |
| TC-05 | Kiểm tra tính năng làm lạnh nhanh (Turbo/Powerful)                      | `[Dán link YouTube]`                               |
| TC-08 | Kiểm tra hành vi của máy khi mất tín hiệu Remote (Che hồng ngoại)       | `[Dán link YouTube]`                               |
| TC-12 | Kiểm tra phục hồi trạng thái sau khi rút phích cắm đột ngột (Edge Case) | `[Dán link YouTube]`                               |
| TC-15 | Kiểm tra phản hồi khi bấm loạn xạ các nút trên Remote (Edge Case)       | `[Dán link YouTube]`                               |

---
