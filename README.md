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

---

## ⚡ Phase 2 — Artefact 2: Pitch "Kết luận trước" & RACI Matrix (Trang 2 PDF)

### 1. Bản Pitch nháp của Team gửi Champion chủ chốt (Ông Trần Hùng — Head of Claims)

* **KẾT LUẬN / ĐỀ XUẤT (Conclusion First)**:  
  Team đề xuất triển khai chương trình **Pilot nội bộ 3 tuần giải pháp SmartClaim AI trên 200 hồ sơ claim ngoại trú**, với mục tiêu tự động hóa 80% công đoạn bóc tách chứng từ và **rút ngắn thời gian thẩm định sơ bộ từ 25 phút xuống dưới 3 phút/hồ sơ**, không can thiệp vào quy trình duyệt chi tiền hiện tại.

* **LÝ DO (Why it matters)**:  
  1. **Giải tỏa quá tải mùa cao điểm**: Dự kiến cuối năm lượng hồ sơ bồi thường tăng 40%, đội ngũ 15 chuyên viên hiện hữu sẽ quá tải nghiêm trọng nếu tiếp tục nhập liệu thủ công.  
  2. **Nâng cao NPS & Tỷ lệ tái tục**: Thời gian chờ bồi thường kéo dài 5–7 ngày là nguyên nhân hàng đầu khiến khách hàng phàn nàn; rút ngắn về 24h sẽ tạo lợi thế cạnh tranh vượt trội cho công ty bảo hiểm.  
  3. **Kiểm soát rủi ro gian lận**: AI tự động đối soát chéo số tiền từng dòng viện phí với tổng hóa đơn đỏ, loại bỏ 100% sai sót tính toán do mỏi mắt của con người.

* **BẰNG CHỨNG (Evidence & Demo)**:  
  • **Dữ liệu thực nghiệm**: Đã chạy thử trên tập dữ liệu benchmark 100 hóa đơn viện phí và toa thuốc thực tế gần nhất, đạt độ chính xác trích xuất **92.4%** (Exact Match các trường thông tin quan trọng: Ngày khám, Chẩn đoán ICD-10, Tổng tiền, Chi tiết thuốc).  
  • **Demo định lượng**: Xử lý trọn bộ 1 hồ sơ 5 trang chứng từ (Hóa đơn GTGT + Bảng kê chi phí + Toa thuốc) chỉ mất **1 phút 48 giây** (so với trung bình 22 phút nhập tay của chuyên viên).  
  • **Tỷ lệ bắt lệch**: Phát hiện chính xác 100% các ca có chênh lệch tiền giữa Bảng kê chi tiết và Hóa đơn tài chính.

* **SMALL ASK (Đề nghị hành động nhỏ tiếp theo)**:  
  Kính đề xuất anh Hùng cho phép **02 chuyên viên thẩm định cấp cao tham gia buổi Demo kỹ thuật 30 phút vào 15h thứ Năm tuần này (16/10)**, đồng thời cấp quyền truy cập **200 bộ hồ sơ lịch sử đã ẩn danh** để team chạy thử nghiệm đối soát mù (blind test) đối chiếu với kết quả của chuyên viên.

---

### 2. Chuẩn bị phản biện & Chiến lược xử lý rủi ro

* **Phản biện có khả năng xảy ra nhất từ Stakeholder**:  
  > *"Toa thuốc Việt Nam có chữ viết tay bác sĩ rất khó đọc, bảng kê viện phí mỗi bệnh viện một định dạng khác nhau. Nếu AI đọc sai tên thuốc, sai liều lượng hoặc bịa số tiền (hallucination) mà hệ thống tự duyệt chi thì công ty bảo hiểm sẽ thất thoát hàng trăm triệu đồng!"*

* **Câu trả lời & Biện pháp giảm thiểu rủi ro dựa trên bằng chứng**:  
  1. **Nguyên tắc "AI Copilot — Human in the Loop" (Không tự động duyệt chi)**: AI không có quyền bấm duyệt chi trả bồi thường. AI chỉ chuẩn bị sẵn dữ liệu trích xuất và highlight sẵn điều khoản bồi thường; quyết định cuối cùng 100% thuộc về thẩm định viên.  
  2. **Cơ chế Confidence Score & Visual Bounding Box**: Mỗi trường thông tin bóc tách đều đi kèm chỉ số tin cậy (0–100%). Nếu độ tự tin < 88% hoặc rơi vào vùng chữ viết tay mờ, hệ thống tự động gắn cờ cảnh báo màu vàng kèm ảnh chụp cắt lớp chứng từ gốc kế bên, giúp thẩm định viên chỉ mất 3 giây để xác nhận/sửa đổi thay vì phải gõ lại toàn bộ.  
  3. **Hàng rào kiểm tra logic kép (Deterministic Rule Engine)**: Số tiền trên từng dòng thuốc/dịch vụ cộng lại bắt buộc phải khớp 100% với Tổng tiền trên Hóa đơn tài chính; nếu chênh lệch dù chỉ 1.000 VNĐ, hệ thống lập tức chặn lại và yêu cầu thẩm tra.

---

### 3. Cá nhân viết lại Pitch & Team tổng hợp

* **Nguyễn Minh Hoàng (AI Engineer)**:  
  *Góc nhìn kỹ thuật & độ tin cậy:* "Chúng tôi đề xuất thử nghiệm mô hình Multi-modal RAG kết hợp OCR chuyên dụng cho y tế trên 200 hồ sơ. Hệ thống đã đạt 92.4% Exact Match và được trang bị Guardrails chống Hallucination đa tầng với Confidence Threshold 88%. Đề xuất anh Hùng phê duyệt buổi Test kỹ thuật 30 phút vào thứ Năm để kiểm chứng độ chính xác trực tiếp trên dữ liệu mẫu."
* **Trần Anh Tuấn (Product Lead)**:  
  *Góc nhìn giá trị kinh doanh & vận hành:* "Để chuẩn bị cho đợt tăng tải 40% hồ sơ cuối năm mà không cần tuyển ồ ạt nhân sự thời vụ, chúng tôi đề xuất Pilot SmartClaim AI trong 3 tuần giúp giảm 80% thời gian nhập liệu thủ công. Kết quả demo cho thấy tốc độ xử lý nhanh hơn 10 lần. Mong anh Hùng đồng ý cho 2 thẩm định viên tham gia buổi Demo 30 phút tuần này để kiểm nghiệm thực tế."
* **Lê Quốc Khánh (Data & Backend Engineer)**:  
  *Góc nhìn tích hợp & an toàn dữ liệu:* "Hệ thống SmartClaim AI đã sẵn sàng hoạt động độc lập qua cổng Web Portal bảo mật, không đụng chạm đến Core IT. Dữ liệu bệnh án được ẩn danh hóa PII 100% tại máy chủ cục bộ. Đề xuất anh Hùng phê duyệt bộ 200 hồ sơ lịch sử ẩn danh để chúng tôi đối soát tự động song song với kết quả thẩm định cũ."
* 👉 **Team thống nhất**: Sử dụng phiên bản tổng hợp ở Mục 1 — kết hợp bài toán nhức nhối về năng suất của vận hành, bằng chứng thời gian/độ chính xác cụ thể và Small Ask rõ ràng, không gây áp lực cam kết lớn.

---

### 4. RACI Matrix (Bảng phân định trách nhiệm 6 công việc then chốt)

*Nguyên tắc tuân thủ: Mỗi công việc có **đúng 1 Accountable (A) duy nhất**. Tách biệt rõ giữa người làm (R) và người chịu trách nhiệm cuối (A).*

| STT | Công việc trọng tâm (1–2 tháng tới) | Product Lead<br>(Trần Anh Tuấn) | AI Engineer<br>(Nguyễn Minh Hoàng) | Backend/Data<br>(Lê Quốc Khánh) | Stakeholder chính<br>(Head of Claims / Compliance) |
|:---:|:---|:---:|:---:|:---:|:---:|
| **1** | **Xác định Use case & Quy tắc nghiệp vụ thẩm định** *(Claims Business Rules)* | **A** | C | C | **R** *(Trần Hùng - Head of Claims)* |
| **2** | **Thu thập, làm sạch & Ẩn danh hóa dữ liệu y tế** *(PII Masking & Pipeline)* | C | C | **A / R** | **C** *(Đỗ Thu Hà - Compliance Officer)* |
| **3** | **Xây dựng Pipeline Multi-modal RAG & Tối ưu OCR** *(AI Model Development)* | C | **A / R** | R | I |
| **4** | **Kiểm thử chất lượng & Benchmark chống sai lệch** *(AI QA & Guardrails)* | **A** | R | R | I |
| **5** | **Triển khai thử nghiệm Pilot nội bộ trên 200 hồ sơ** *(Internal Pilot Run)* | **A** | R | R | **C** *(2 Chuyên viên thẩm định)* |
| **6** | **Nghiệm thu kết quả Pilot & Quyết định Release** *(Go/No-Go Decision)* | R | I | I | **A** *(Trần Hùng - Head of Claims)* |

*Chú giải phân định RACI:*
- **Việc 1**: *Trần Anh Tuấn (Product Lead)* chịu trách nhiệm cuối (**A**) việc chuyển hóa nghiệp vụ thành tài liệu đặc tả; *Trần Hùng (Stakeholder)* là người trực tiếp định nghĩa và cung cấp quy tắc (**R**).
- **Việc 2**: *Lê Quốc Khánh* chịu trách nhiệm chính (**A/R**) việc pipeline dữ liệu bảo mật; *Bà Đỗ Thu Hà* được tham vấn (**C**) để chuẩn hóa phương án tuân thủ Nghị định 13.
- **Việc 3**: *Nguyễn Minh Hoàng* chịu trách nhiệm toàn diện (**A/R**) về chất lượng mô hình AI và độ chính xác OCR.
- **Việc 4**: *Trần Anh Tuấn* chịu trách nhiệm cuối (**A**) về tiêu chí đánh giá nghiệp vụ đạt chuẩn; Hoàng và Khánh phối hợp thực hiện (**R**).
- **Việc 5**: *Trần Anh Tuấn* điều phối và chịu trách nhiệm toàn bộ đợt Pilot (**A**); Hoàng & Khánh hỗ trợ kỹ thuật (**R**); các thẩm định viên tham gia đóng góp ý kiến đánh giá (**C**).
- **Việc 6**: *Trần Hùng (Stakeholder - Head of Claims)* là người duy nhất nắm quyền phê duyệt ký nghiệm thu và quyết định Go/No-Go (**A**).

---

> **✅ GATE 2 PASS**:
> - Pitch chuẩn cấu trúc Conclusion First (Kết luận trước) → 3 Lý do → Bằng chứng định lượng (92.4%, 1m48s) → Small ask cụ thể (Demo 30 phút, 200 hồ sơ).
> - Đã có 1 phản biện gay gắt nhất về rủi ro sai sót y khoa & kèm giải pháp kỹ thuật hạ tầng (Human-in-the-loop, Confidence Threshold 88%, Rule Engine đối soát).
> - Hoàn thành phần viết lại cá nhân của 3 thành viên và tổng hợp thống nhất.
> - Bảng RACI gồm 6 công việc trọng tâm, **mỗi hàng chỉ có ĐÚNG 1 ACCOUNTABLE (A)**, tách biệt vai trò rõ ràng.

---

## 👥 Phase 3 — Artefact 3: Thiết kế AI Team & Priority Resourcing (Trang 3 PDF)

### 1. Lựa chọn AI Team Architecture

* **Mô hình lựa chọn**: **Embedded AI Team (Cross-functional Product Pod)**.
* **Lý do lựa chọn & Sự phù hợp với giai đoạn hiện tại**:  
  Đội ngũ hiện có quy mô tinh gọn 3 thành viên đang phát triển sản phẩm SmartClaim AI từ giai đoạn PoC bước vào thử nghiệm Pilot nội bộ (từ 0 lên 1). Mô hình **Embedded** tích hợp chặt chẽ toàn bộ các năng lực then chốt (AI, Data, Backend, Product) vào trong cùng một squad duy nhất. Mô hình này giúp loại bỏ hoàn toàn rào cản hành chính giữa các phòng ban, tạo ra vòng lặp phản hồi siêu ngắn (*daily feedback loop < 24h*) giữa kỹ thuật mô hình và yêu cầu nghiệp vụ thẩm định, không gây lãng phí chi phí vận hành cồng kềnh như mô hình Centralized hay phân tán phức tạp như Hybrid của các tập đoàn lớn.

---

### 2. Phân định Core Roles (Cần ngay) & Extended Roles (Cần khi scale)

```
+---------------------------------------------------------------------------------------+
|                                    SQUAD SMARTCLAIM AI                                |
|                                                                                       |
|   [CORE ROLES - GIAI ĐOẠN HIỆN TẠI (3 THÀNH VIÊN)]                                    |
|   +--------------------------+  +--------------------------+  +-------------------+   |
|   | AI Product & Solution    |  | AI & Model Engineer      |  | Data & Backend    |   |
|   | Lead (Trần Anh Tuấn)     |  | (Nguyễn Minh Hoàng)      |  | Engineer (Lê Quốc |   |
|   | • Nghiệp vụ & User Flow  |  | • Multi-modal OCR & RAG  |  |   Khánh)          |   |
|   | • Human-in-the-Loop Spec |  | • Prompting & Guardrails |  | • PII Anonymizer  |   |
|   | • Stakeholder Management |  | • Evaluation Metrics     |  | • API Ingestion   |   |
|   +--------------------------+  +--------------------------+  +-------------------+   |
|                                                                                       |
|   [EXTENDED ROLES - BỔ SUNG KHI SCALE (3-6 THÁNG TỚI)]                                |
|   • MLOps & Evals Engineer (Tự động hóa CI/CD, Model Monitoring, Drift Detection)     |
|   • Healthcare Domain Auditor (Bác sĩ cố vấn danh mục thuốc BHYT & mã ICD-10)         |
|   • AI Governance & Security Specialist (Chứng chỉ ISO 27001, HIPAA & Pháp lý)        |
+---------------------------------------------------------------------------------------+
```

#### Bảng chi tiết trách nhiệm các vai trò cốt lõi (Core Roles):
1. **AI Product & Solution Lead (Trần Anh Tuấn — Core, hiện tại)**:
   - Sở hữu Product Vision, Roadmap và tiêu chí thành công của đợt Pilot.
   - Chuyển dịch nghiệp vụ thẩm định bảo hiểm phức tạp thành bài toán kỹ thuật; thiết kế giao diện tương tác thẩm định viên (Human-in-the-Loop UX).
   - Đo lường Business Metrics: Thời gian thẩm định trung bình, tỷ lệ can thiệp của con người (Touch Rate).
2. **AI & Model Engineer (Nguyễn Minh Hoàng — Core, hiện tại)**:
   - Xây dựng pipeline tích hợp Multi-modal OCR chuyên dụng cho tài liệu y khoa tiếng Việt và Vision-Language Models (VLM).
   - Thiết kế kiến trúc Multi-modal RAG trích xuất thông tin cấu trúc (JSON Schema) chuẩn xác.
   - Thiết lập Guardrails kiểm soát ảo giác và hệ thống tính điểm tự tin (Confidence Scoring Engine).
3. **Data & Backend Engineer (Lê Quốc Khánh — Core, hiện tại)**:
   - Xây dựng module làm sạch và ẩn danh hóa dữ liệu PII on-premise tuân thủ Nghị định 13/2023/NĐ-CP.
   - Thiết kế hệ thống RESTful API / Async Webhook tốc độ cao kết nối với cổng Portal thẩm định.
   - Đảm bảo an toàn hạ tầng Sandbox, quản lý cơ sở dữ liệu Vector DB và PostgreSQL.

---

### 3. Priority Resourcing: Giải pháp bổ sung Capability Gap

Team xác định **3 khoảng trống năng lực (Capability Gap)** quan trọng nhất và đưa ra chiến lược bổ sung tối ưu nguồn lực thực tế (**Hire / Outsource / Partner**):

| STT | Capability Gap (Năng lực còn thiếu) | Phương án lựa chọn | Vì sao chọn phương án này? (Rationale) | Thời điểm cần hoàn thành (Deadline) |
|:---:|:---|:---:|:---|:---|
| **1** | **Chuyên môn Y tế & Dược học chuyên sâu** *(Medical Coding ICD-10 & Toa thuốc)* | **PARTNER**<br>*(Hợp tác chuyên gia)* | Ở giai đoạn MVP/Pilot, việc tuyển một bác sĩ hay dược sĩ toàn thời gian (Full-time Hire) là vô cùng tốn kém và lãng phí. Team chỉ cần sự tư vấn chuyên môn theo giờ để chuẩn hóa bộ quy tắc loại trừ quyền lợi và giải thích các toa thuốc khó. Do đó, hợp tác cố vấn với 01 Bác sĩ độc lập là giải pháp kinh tế và nhanh nhất. | **Trước ngày 25/10/2026**<br>*(2 tuần trước khi bấm máy Pilot để thẩm định bộ ruleset)* |
| **2** | **Gán nhãn & Làm sạch dữ liệu OCR y tế quy mô lớn** *(Medical Data Annotation)* | **OUTSOURCE**<br>*(Thuê ngoài chuyên biệt)* | Việc gán nhãn bounding box và key-value pairs cho 2.000 hóa đơn/toa thuốc lịch sử tốn hàng trăm giờ lao động chân tay. Nếu để kỹ sư AI tự làm sẽ lãng phí năng lực nghiên cứu thuật toán. Thuê một đơn vị gán nhãn dữ liệu chuyên nghiệp (kèm hợp đồng bảo mật NDA chặt chẽ) vừa tiết kiệm 70% chi phí vừa bàn giao nhanh trong 1 tuần. | **Trước ngày 05/11/2026**<br>*(Sprint 2 để mở rộng tập validation)* |
| **3** | **MLOps & Pipeline Giám sát mô hình liên tục** *(Continuous Evals & Model Monitoring)* | **HIRE**<br>*(Tuyển dụng khi scale)* | Khi mở rộng xử lý hàng nghìn hồ sơ/ngày trên môi trường Production thật, rủi ro mô hình suy giảm hiệu năng (Data & Model Drift) là hiện hữu. Team cần 01 kỹ sư MLOps chuyên trách quản lý CI/CD cho model, tự động hóa regression testing và tối ưu chi phí hạ tầng GPU. | **Tháng 12/2026**<br>*(Sau khi nghiệm thu Pilot thành công và nhận ngân sách mở rộng)* |

---

### 4. Squad Goal

> **"Squad của chúng tôi sở hữu toàn bộ giải pháp xử lý chứng từ bảo hiểm tự động (SmartClaim Core Engine) và chịu trách nhiệm đưa tỷ lệ trích xuất chính xác hồ sơ bồi thường từ 92.4% lên > 95% và rút ngắn thời gian thẩm định sơ bộ từ 25 phút xuống dưới 3 phút/hồ sơ trong 60 ngày tới."**

---

> **✅ GATE 3 PASS**:
> - Đã chọn mô hình **Embedded AI Team** và giải thích rõ ràng lý do phù hợp với giai đoạn PoC -> Pilot của team 3 người.
> - Đã phân định rõ Core Roles (hiện tại) và Extended Roles (khi scale).
> - Đã xác định đủ 3 Capability Gap và đưa ra chiến lược Resourcing đa dạng, đúng bản chất: **Partner** (bác sĩ cố vấn), **Outsource** (gán nhãn dữ liệu), **Hire** (kỹ sư MLOps khi scale) kèm lý do thuyết phục và deadline cụ thể.
> - Squad Goal được xây dựng đúng cấu trúc chuẩn chỉnh, sở hữu phạm vi và cam kết kết quả đo lường được.


