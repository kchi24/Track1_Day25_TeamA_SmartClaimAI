# Track 1 - Day 27 — AI Team Lab: Từ Stakeholder đến Team Health & Growth Plan
**Repository chính thức của Team HTK**  
*Thời gian thực hiện: 120 phút | Đội ngũ: Team HTK*

---

## 📌 Phase 0 — Chốt phạm vi & Cách làm (Scope & Ground Rules)

| STT | Hạng mục | Nội dung thống nhất của Team |
|:---:|:---|:---|
| **1** | **Thành viên team (3 thành viên)** | • **Nguyễn Minh Hoàng** — AI Engineer & Model Optimization Lead<br>• **Trần Anh Tuấn** — Product Lead & Solution Architect *(Trưởng nhóm)*<br>• **Lê Quốc Khánh** — Data & Fullstack Backend Engineer |
| **2** | **Tên dự án AI** | **SmartClaim AI** — Hệ thống AI tự động hóa trích xuất dữ liệu bệnh án & thẩm định sơ bộ hồ sơ bồi thường bảo hiểm sức khỏe (Health Insurance Claims Automation using OCR + Multi-modal RAG). |
| **3** | **Mục tiêu 1–3 tháng tới** | • Đạt độ chính xác trích xuất hóa đơn viện phí / toa thuốc > 92% trên tập 300 mẫu thực tế.<br>• Giảm thời gian xử lý hồ sơ thẩm định sơ bộ từ 25 phút xuống < 3 phút/hồ sơ.<br>• Hoàn thành bản MVP thử nghiệm Pilot thành công với 1 công ty bảo hiểm đối tác (hoặc bộ phận Claims nội bộ 15 nhân viên). |
| **4** | **Trưởng nhóm / Repo Owner** | **Trần Anh Tuấn** (chịu trách nhiệm khởi tạo repo, điều phối checklist, merge artefact và nộp link). |
| **5** | **Format bài nộp** | GitHub Repository (`README.md`) + File Báo cáo tổng hợp PDF 4 trang (tương ứng 4 Artefact). |

> **✅ GATE 0 PASS**: Toàn bộ thành viên đã chốt chung phạm vi dự án SmartClaim AI, chung mục tiêu 1–3 tháng và có Trưởng nhóm (Trần Anh Tuấn) phụ trách tổng hợp.

---

## 🗺️ Phase 1 — Artefact 1: Stakeholder Map & Chiến lược tương tác (Trang 1 PDF)

### 1. Ma trận Stakeholder (Influence × Interest) & Stance thực tế

Team xác định **7 stakeholder cụ thể** (không ghi chung chung) liên quan trực tiếp đến sự thành bại của SmartClaim AI:

```
                      [ INTEREST: MỨC ĐỘ QUAN TÂM ]
                THẤP (Low)                         CAO (High)
        +-----------------------------------+-----------------------------------+
        | [BLOCKER]                         | [CHAMPION]                        |
        | 2. Trưởng phòng Pháp chế &        | 1. Giám đốc Vận hành Bồi thường   |
        |    Bảo mật Dữ liệu (Compliance)   |    (Head of Claims Operations)    |
   C    |    * Stance: Chưa ủng hộ          |    * Stance: Ủng hộ               |
   A    |                                   |                                   |
   O    | 3. Giám đốc CNTT đối tác (CIO)    | 4. Tech Mentor / Giảng viên AI    |
        |    * Stance: Trung lập            |    * Stance: Ủng hộ               |
[INFLUENCE]---------------------------------+-----------------------------------|
        | [BYSTANDER]                       | [SUPPORTER]                       |
   T    | 7. Nhân viên Đại lý phân phối     | 5. Chuyên viên Thẩm định hồ sơ    |
   H    |    bảo hiểm (Agents)              |    cấp cao (Senior Claims Reviewer|
   Ấ    |    * Stance: Trung lập            |    * Stance: Ủng hộ               |
   P    |                                   |                                   |
        |                                   | 6. Bệnh nhân / Khách hàng gửi đơn |
        |                                   |    * Stance: Trung lập / Ủng hộ   |
        +-----------------------------------+-----------------------------------+
```

#### Chi tiết 7 Stakeholder và Phân loại:
1. **Ông Trần Hùng — Giám đốc Vận hành Bồi thường (Head of Claims)**
   - *Vùng*: Influence Cao × Interest Cao (`Champion`)
   - *Stance*: **Ủng hộ** (Muốn giảm tải áp lực cho nhân sự khi lượng claim tăng 40% dịp cuối năm).
2. **Bà Đỗ Thu Hà — Trưởng phòng Pháp chế & An toàn Thông tin (Compliance & Data Privacy Officer)**
   - *Vùng*: Influence Cao × Interest Thấp (`Blocker`)
   - *Stance*: **Chưa ủng hộ** (Lo ngại vi phạm Nghị định 13/2023/NĐ-CP về bảo vệ dữ liệu cá nhân nhạy cảm y tế khi dùng AI/LLM).
3. **Ông Lê Quang Minh — Giám đốc Công nghệ (CIO / Head of IT Core)**
   - *Vùng*: Influence Cao × Interest Thấp (`Blocker`)
   - *Stance*: **Trung lập** (E ngại hệ thống AI bên ngoài chọc trực tiếp vào Database Core Insurance cũ kỹ, tăng rủi ro downtime).
4. **TS. Nguyễn Việt Khoa — Tech Mentor / Giảng viên hướng dẫn AI**
   - *Vùng*: Influence Cao × Interest Cao (`Champion`)
   - *Stance*: **Ủng hộ** (Đánh giá cao tính ứng dụng và sẵn sàng kết nối dữ liệu mẫu ẩn danh).
5. **Chị Vũ Mai Phương — Chuyên viên Thẩm định hồ sơ cấp cao (Senior Claims Reviewer)**
   - *Vùng*: Influence Thấp × Interest Cao (`Supporter`)
   - *Stance*: **Ủng hộ** (Mệt mỏi vì phải nhập tay chứng từ và đọc toa thuốc mờ, muốn AI hỗ trợ tiền kiểm tra).
6. **Khách hàng bảo hiểm (End-Users nộp claim qua App)**
   - *Vùng*: Influence Thấp × Interest Cao (`Supporter`)
   - *Stance*: **Ủng hộ** (Quan tâm thời gian giải ngân bồi thường từ 7 ngày xuống còn 24h).
7. **Đại lý bán bảo hiểm (Insurance Agents)**
   - *Vùng*: Influence Thấp × Interest Thấp (`Bystander`)
   - *Stance*: **Trung lập** (Chỉ quan tâm tỷ lệ bồi thường nhanh giúp họ dễ tái tục hợp đồng với khách).

---

### 2. Bốn Stakeholder ưu tiên & Chiến lược hành động cụ thể (1–2 tuần tới)

| Stakeholder ưu tiên | Nhóm & Stance | 1. Họ quan tâm điều gì nhất? | 2. Họ có thể giúp / cản trở dự án thế nào? | 3. Hành động cụ thể của team trong 1–2 tuần tới (Action + Deadline) |
|:---|:---:|:---|:---|:---|
| **1. Ông Trần Hùng** *(Head of Claims)* | **Champion**<br>*(Ủng hộ mạnh)* | Tỷ lệ tự động hóa hồ sơ đạt chuẩn, giảm backlog bồi thường và tiết kiệm chi phí vận hành. | • **Giúp**: Cung cấp 500 ca bệnh án lịch sử để kiểm thử và tài trợ phòng lab pilot.<br>• **Rủi ro**: Hủy dự án nếu kết quả demo sai sót logic y khoa cơ bản. | **Trước 17h thứ Sáu tuần này (17/10)**: Gửi bản Demo tương tác trích xuất tự động 30 toa thuốc viện phí + biên bản so sánh thời gian xử lý (từ 25 phút còn 2 phút 15 giây) để xin phê duyệt khởi động Sprint Pilot nội bộ. |
| **2. TS. Nguyễn Việt Khoa** *(Tech Mentor)* | **Champion**<br>*(Ủng hộ mạnh)* | Tính khả thi của kiến trúc Multi-modal RAG, xử lý OCR tiếng Việt chữ viết tay bác sĩ và độ tin cậy kết quả. | • **Giúp**: Tư vấn giải pháp giảm ảo giác (hallucination) và kết nối với mạng lưới đối tác dữ liệu.<br>• **Rủi ro**: Không có rủi ro cản trở. | **Trước 20h thứ Tư (15/10)**: Đặt lịch 45 phút 1-on-1, trình bày kiến trúc xử lý bảng biểu hóa đơn phức tạp và nhờ review bộ metrics đánh giá (F1-score, Exact Match trên trường tiền & tên thuốc). |
| **3. Bà Đỗ Thu Hà** *(Trưởng phòng Pháp chế & An toàn thông tin)* | **Blocker**<br>*(Chưa ủng hộ / Rủi ro cản trở)* | Tuân thủ Nghị định 13/2023/NĐ-CP: bảo vệ dữ liệu sức khỏe, rủi ro rò rỉ dữ liệu lên Cloud LLM công cộng (OpenAI). | • **Cản trở**: Dùng quyền phủ quyết (veto) chặn toàn bộ tiến trình triển khai pilot lên dữ liệu thật.<br>• **Giúp**: Nếu được giải tỏa, bà sẽ là người bảo chứng an toàn pháp lý cho sản phẩm. | **Trước 10h thứ Ba tuần sau (21/10)**: Gửi tài liệu kiến trúc kỹ thuật *"Private AI & Data Anonymization Plan"* chứng minh: toàn bộ PII (tên, CCCD, địa chỉ) được làm mờ/che cục bộ bằng thuật toán Regex/NER on-premise trước khi đưa vào pipeline OCR. |
| **4. Ông Lê Quang Minh** *(Giám đốc CNTT / CIO)* | **Blocker**<br>*(Trung lập / E ngại)* | Tính ổn định của hạ tầng Core Insurance hiện hữu; không phát sinh gánh nặng bảo trì API cho team IT nội bộ. | • **Cản trở**: Trì hoãn việc cấp quyền truy cập Sandbox API tích hợp vào Core Claim.<br>• **Giúp**: Cấp môi trường thử nghiệm và webhook tự động nhận chứng từ. | **Trước 15h thứ Năm tuần sau (23/10)**: Tổ chức buổi họp kỹ thuật 30 phút, cam kết mô hình tích hợp phi tập trung (Loose Coupling via Async Webhook & S3 bucket), không can thiệp trực tiếp vào Database Core. |

---

> **✅ GATE 1 PASS**:
> - Đã có 7 stakeholder cụ thể, phân bổ đầy đủ trên 4 góc Influence × Interest.
> - Đã đánh giá Stance thực tế kèm giải thích rõ ràng.
> - Đã chọn đủ 4 stakeholder ưu tiên (2 Champion ủng hộ mạnh, 2 Blocker có rủi ro cản trở).
> - Có 4 hành động cụ thể, gắn chặt với ngày giờ và kết quả bàn giao đo lường được (không viết chung chung).
