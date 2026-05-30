# [AI-02] AI Audit Report

**Sinh viên:** Nguyen Hieu Thuan
**MSSV:** 23127125

---

### Artifact 1: Sơ đồ tư duy quy trình ISTQB về QA/QC Roles

- **(1) Prompt + tool:**
  - **Tool:** Gemini 3.1 Pro
  - **Timestamp:** 9:00 28/05/2026
  - **Prompt:** `draws a QA/QC role mindmap.`
- **(2) AI output:** AI sinh ra sơ đồ hoàn chỉnh phân chia các vai trò, trong đó gán nhiệm vụ "Perform rework/fixes" cho QC; khẳng định "QA sets requirements at start"; và cho rằng "QA provides test data to QC".
- **(3) Verdict:** INVALID
- **(4) Reasoning:** Hoạt động Kiểm thử (Testing) và Gỡ lỗi (Debugging/Fixing) là độc lập, việc sửa lỗi code là của Developer chứ không phải QC. Thêm vào đó, Khách hàng/BA/PO là người định nghĩa Yêu cầu (Requirements), QA chỉ kiểm toán quy trình. Cuối cùng, dữ liệu kiểm thử (Test Data) do QC tự chuẩn bị trong pha Test Implementation, không liên quan đến QA.
- **(5) Student fix:** Đã phát hiện và sửa lại 3 lỗi sai trong sơ đồ: Thay "Perform rework/fixes" thành "Retest fixed defects"; Thay "QA sets requirements" thành "BA/PO sets requirements"; Đổi "QA provides test data to QC" thành "QC prepares test data during Test Implementation phase".

---

### Artifact 2: 15 Kịch bản kiểm thử thiết bị máy lạnh (Requirement 3)

- **(1) Prompt + tool:**
  - **Tool:** Gemini 3.1 Pro
  - **Timestamp:** 20:00 27/05/2026
  - **Prompt:** `ok, bây giờ hãy tạo cho tôi 15 test cases cho máy lạnh treo tường với đúng format (Objective / Input / Steps / Expected / Actual / Verdict) để tôi copy được vào file excel nhé. Các trường Actual và Verdict thì để trống.`
- **(2) AI output:** AI sinh ra bảng 15 Test Cases, toàn bộ đều tập trung vào các luồng thao tác hoàn hảo (Happy Path) như: bật/tắt, tăng/giảm nhiệt độ, đổi chế độ, chỉnh tốc độ quạt.
- **(3) Verdict:** INCOMPLETE
- **(4) Reasoning:** AI thiếu hoàn toàn tư duy về môi trường vật lý thực tế. Nó không lường trước được các giới hạn về phần cứng và các rủi ro năng lượng ngoài môi trường thực tế (như mất điện đột ngột), cũng như đặc tính bất đồng bộ giữa giao thức hồng ngoại một chiều của Remote và bộ nhớ của bo mạch Dàn lạnh.
- **(5) Student fix:** Đã loại bỏ 3 kịch bản cơ bản dư thừa của AI (ở vị trí TC-07, TC-09, TC-14) và thay thế bằng 3 Edge Cases vật lý hóc búa do bản thân tự thiết kế: (1) Kiểm tra giới hạn biên nhiệt độ tối đa 30°C, (2) Kiểm tra tính năng Auto-Restart khi ngắt cầu dao điện đột ngột, (3) Kiểm tra xử lý bất đồng bộ trạng thái khi mất điện và bấm tắt trên remote.

---

### Artifact 3: Danh sách 20 Lỗi phần mềm 2022-2026 (Requirement 2)

- **(1) Prompt + tool:**
  - **Tool:** Gemini 3.1 Pro
  - **Timestamp:** 25/05/2026 - 30/05/2026 (Req 2 - Toàn bộ các Prompts)
  - **Prompt:** Phần này được tạo ra từ nhiều câu promt khác nhau, với cấu trúc cơ bản là "Dựa vào nội dung trong bài báo dưới đây, cho tôi biết thông tin có hợp lệ cho requirement 2 hay không? Nếu có hãy tóm tắt lại cho tôi theo format có sẵn, nội dung và link bài báo là..."
- **(2) AI output:** AI tổng hợp danh sách lỗi. Khi được yêu cầu tóm tắt và đưa ra nhận định chung dựa trên thông tin tìm kiếm, các kết quả trả về gần như khớp với thực tế và thông tin chính gốc. Tuy nhiên, khi được yêu cầu đóng vai (roleplay), AI có biểu hiện thiên kiến (Bias) và sinh ra các thông tin ảo giác (Hallucination) không có thật.
- **(3) Verdict:** INCOMPLETE
- **(4) Reasoning:** Mô hình LLM rất dễ bị bẻ gãy rào cản đạo đức (Jailbreak) thông qua kỹ thuật Prompt Roleplay, dẫn đến việc AI sẵn sàng tự bịa đặt các thuyết âm mưu hoặc đưa ra lời khuyên sai lệch chuẩn mực kỹ thuật phần mềm thay vì phân tích lỗi khách quan.
- **(5) Student fix:** Trực tiếp Fact-check toàn bộ 20 nguồn link để đảm bảo tính xác thực. Thực hiện bắt lỗi ảo giác/thiên kiến của AI cho các defect, sau đó chủ động dừng thao tác này ở 10 defect cuối để tập trung vào cốt lõi chuyên môn kiểm thử và chấp nhận tự trừ điểm trong khung Self-Assessment.

---

### Tổng kết và Kết luận

**1. Tỷ lệ chính xác của AI (AI Accuracy Ratio):**
Dựa trên các Artifacts trọng yếu đã kiểm toán:

- **VALID:** 0% (Không có Artifact nào dùng được ngay lập tức mà không cần sửa chữa).
- **INVALID:** ~33% (Sai kiến thức nền tảng ISTQB ở sơ đồ tư duy).
- **INCOMPLETE:** ~67% (Thiếu tư duy vật lý edge cases và bị ảo giác khi tìm nguồn/đóng vai).

**2. Kết luận:**
Qua quá trình hợp tác và kiểm toán công cụ Gemini 3.1 Pro, tôi rút ra nguyên tắc sử dụng AI trong công việc QA/QC như sau:

- **KHI NÀO NÊN DÙNG AI:** Sử dụng rất tốt cho việc tạo bộ khung (templates), định dạng văn bản Markdown/Excel, viết nháp các test cases cơ bản, và tìm kiếm khối lượng lớn dữ liệu thô ban đầu.
- **KHI NÀO KHÔNG NÊN DÙNG AI:** Không nên dùng AI để thay thế con người trong việc thiết kế Test Case biên (Edge cases) cho phần cứng vật lý, không dùng AI để xác nhận kiến thức chuyên môn cốt lõi (như ISTQB) mà không đối chiếu giáo trình, các đường link được AI cung cấp thường không có thật hoặc không thể truy cập, vì vậy nên kiểm tra thật kĩ. Đồng thời, luôn nhớ phải kiểm tra lại mọi thông tin mà AI đã sinh ra để đảm bảo tính hợp lệ và đúng yêu cầu đề ra.
