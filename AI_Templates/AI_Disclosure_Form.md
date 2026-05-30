# [AI-03] AI Disclosure Form

**Biểu mẫu tuyên bố và minh bạch hóa mức độ can thiệp của công nghệ vào bài làm của sinh viên**

---

### 1. Khẳng định về việc tạo nháp bởi AI

Tôi xác nhận các thành phần dưới đây trong đồ án ban đầu được hỗ trợ tạo nháp, định dạng cấu trúc hoặc gợi ý ý tưởng bởi công cụ Trí tuệ nhân tạo (AI):

- **Công cụ AI sử dụng:** Gemini 3.1 Pro.
- **Các phần được tạo nháp bởi AI:**
  - **Sơ đồ tư duy (Mindmap):** Tạo ra hình ảnh tổng quan về phân nhiệm vai trò QA/QC trong phát triển phần mềm.
  - **Requirement 1:** Định dạng bảng mẫu Markdown để trình bày 10 tin tuyển dụng QA/QC.
  - **Requirement 2:** Định dạng bảng mẫu Markdown để trình bày 20 lỗi phần mềm. Tìm kiếm dữ liệu thô, tóm tắt thông tin từ các bài báo được tôi tìm kiếm để rút ra bối cảnh lịch sử và giải pháp kỹ thuật nền tảng cho 20 lỗi phần mềm giai đoạn 2022–2026.
  - **Requirement 3:** Định dạng bảng mẫu Markdown để trình bày rõ ràng, minh bạch mục Requirement 3. Tạo 15 kịch bản (sau đó 3 cái được thay thế bởi tôi) kiểm thử chức năng cơ bản (Bật/tắt, tăng giảm nhiệt độ, tốc độ quạt...) cho thiết bị máy lạnh treo tường.

---

### 2. Chi tiết các mục tiến hành rà soát và chỉnh sửa

Tôi đã thực hiện kiểm tra, đối chiếu kiến thức và trực tiếp chỉnh sửa các nội dung do AI sinh ra nhằm đảm bảo tính chính xác và tính thực tế của báo cáo:

- **Sửa lỗi sơ đồ tư duy:** Phát hiện và đính chính 3 sai sót của AI bao gồm: Nhầm lẫn việc sửa code (Rework/Fixes) thuộc QC, QA thiết lập yêu cầu (Requirements) ở đầu dự án, và QA cung cấp dữ liệu test cho QC.
- **Requirement 1 (QA/QC Job Market 2026+):** Tự truy cập thủ công tài khoản LinkedIn cá nhân để thu thập 10 tin tuyển dụng thực tế trong vòng 60 ngày, chụp ảnh minh chứng có tên tài khoản cá nhân ở góc màn hình, và tự viết vài câu phân tích tác động của AI (AI Impact Analysis) cho từng tin tuyển dụng.
- **Requirement 2 (20 Software Defects):** Kiểm tra lại tính xác thực của 20 lỗi, xem xét lại mức độ nghiêm trọng và hậu quả. Quyết định dừng thực hiện phần rà soát ảo giác AI (AI Hallucination/Bias Audit) cho các lỗi từ số 11 đến số 20 do nhận thấy nội dung này rời xa cốt lõi môn học, đồng thời tự trừ 5 điểm trong bảng tự chấm điểm (Nhận mức 15/20 điểm).
- **Requirement 3 (Test Design trong Excel):** Chỉnh sửa bảng 15 kịch bản kiểm thử, hoàn thiện cột Kết quả thực tế (Actual Result) và Kết luận (Verdict) sau khi chạy thử nghiệm trên máy lạnh Sharp.

---

### 3. Các phần được thực hiện hoàn toàn bằng con người

Tôi cam kết các phần nội dung dưới đây được thực hiện 100% bằng năng lực trí tuệ cá nhân, không có bất kỳ sự can thiệp, sao chép hay hỗ trợ nào từ AI:

- **Thiết kế 3 Edge Cases vật lý:** Tự tư duy và bổ sung 3 kịch bản kiểm thử biên hóc búa liên quan đến tương tác phần cứng thực tế mà AI bỏ sót:
  - _TC-07:_ Kiểm tra giới hạn biên nhiệt độ tối đa của hệ thống (30°C).
  - _TC-09:_ Kiểm tra tính năng tự động phục hồi trạng thái khi ngắt cầu dao điện vật lý đột ngột.
  - _TC-14:_ Kiểm tra hành vi bất đồng bộ lệnh giữa Remote và bo mạch dàn lạnh trong lúc mất điện.
- **Kịch bản và Video Thực thi kiểm thử:** Trực tiếp tiến hành thực thi các kịch bản, quay 5 video demo độc lập cho các kịch bản TC-01, TC-05, TC-07, TC-09, TC-15 và tự thuyết minh bằng giọng nói cá nhân để làm minh chứng chống gian lận.
- **Báo cáo lỗi (Bug Tracking trên GitHub Issues):** Trực tiếp phát hiện 5 lỗi thực tế trên thiết bị Sharp (Model: AH-X9XEW), tự thiết kế cấu trúc báo cáo lỗi theo mẫu gợi ý từ đề bài và tiến hành log thủ công thành 5 Issues trên kho lưu trữ GitHub cá nhân.
- **Phần viết AI Critique (Phê bình AI):** Tự viết toàn bộ đoạn văn luận 290 chữ phân tích thấu đáo về các điểm yếu cốt tử của AI như thiếu tư duy vật lý và chồng lấn trạng thái trong thực tế, ảo giác nhiễu thông tin, và rủi ro bị bẻ gãy rào cản đạo đức bằng kỹ thuật đóng vai.

---

### 4. Cam kết và Xác nhận

Tôi xin hoàn toàn chịu trách nhiệm trước Hội đồng Kỷ luật của Khoa và Nhà trường về tính trung thực, minh bạch của các thông tin khai báo trong biểu mẫu này.

- **Sinh viên thực hiện:** Nguyễn Hiếu Thuận
- **Mã số sinh viên:** 23127125
- **Ngày hoàn thành biểu mẫu:** 30/05/2026
