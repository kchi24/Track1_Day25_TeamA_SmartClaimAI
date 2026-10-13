# Track 1 - Day 25 — AI Team Lab

- Team: Team HTK
- Thành viên (3–5 người):
  1. Nguyễn Minh Hoàng — AI Engineer & Model Optimization Lead
  2. Trần Anh Tuấn — Product Lead & Solution Architect (Trưởng nhóm)
  3. Lê Quốc Khánh — Data & Fullstack Backend Engineer
- Tên dự án: SmartClaim AI
- Link sản phẩm/demo (nếu có): https://github.com/TeamHTK/Track1_Day25_TeamHTK_SmartClaimAI

## Bài nộp

File: `Day25_AI-Team-Lab_TeamHTK.pdf`

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

---

## 📈 Phase 4 — Artefact 4: Đánh giá Team Health & Growth Plan 30 ngày (Trang 4 PDF)

### 1. Bảng tự chấm điểm Team Health cá nhân (Thang điểm 1–5)

| Khía cạnh đánh giá | Nguyễn Minh Hoàng<br>*(AI Engineer)* | Trần Anh Tuấn<br>*(Product Lead)* | Lê Quốc Khánh<br>*(Data & Backend)* | Điểm Trung Bình Team |
|:---|:---:|:---:|:---:|:---:|
| **1. Chất lượng AI** *(Output ổn định, ít ảo giác)* | **4 / 5** | **3 / 5** | **4 / 5** | **3.67 / 5** |
| **2. Tiến độ** *(Hoàn thành đúng cam kết sprint)* | **3 / 5** | **3 / 5** | **4 / 5** | **3.33 / 5** |
| **3. Tinh thần team** *(Minh bạch, dám nói thẳng, phối hợp)* | **5 / 5** | **5 / 5** | **4 / 5** | **4.67 / 5** |
| **4. Tốc độ ra sản phẩm** *(Thời gian từ ý tưởng/model đến demo)* | **3 / 5** | **2 / 5** | **3 / 5** | **2.67 / 5** *(Thấp nhất)* |

---

### 2. Phân tích so sánh điểm & Xác định vấn đề cốt lõi

* **Khía cạnh có điểm số thấp nhất**:  
  **Tốc độ ra sản phẩm (2.67 / 5)**. Thời gian từ lúc AI Engineer tinh chỉnh xong một prompt hoặc cập nhật model đến lúc có bản cập nhật chạy trên giao diện web cho Product Lead và thẩm định viên thử nghiệm còn quá chậm (thường mất từ 3–4 ngày tích hợp thủ công).
* **Khía cạnh chênh lệch điểm nhiều nhất**:  
  **Chất lượng AI (Hoàng chấm 4/5, Tuấn chấm 3/5 — lệch 1 điểm)**.
* **Lý do có sự chênh lệch**:  
  - *Nguyễn Minh Hoàng (AI Engineer)* nhìn nhận chất lượng qua các chỉ số benchmark trong phòng lab (F1-score 92.4% trên tập test sạch đã định dạng chuẩn).  
  - *Trần Anh Tuấn (Product Lead)* nhìn nhận dưới góc độ trải nghiệm của thẩm định viên thực tế: khi gặp các hóa đơn chụp xiên góc, bóng mờ hoặc toa thuốc viết tay có chữ ký đè lên tên thuốc, mô hình vẫn bỏ sót trường hoặc trả về kết quả rỗng, buộc con người phải can thiệp thủ công.
* **Vấn đề then chốt đe dọa trực tiếp milestone Pilot tiếp theo**:  
  **Thiếu hệ thống đánh giá tự động (Automated Evals Framework)**: Mỗi lần cập nhật thuật toán, team phải ngồi kiểm thử bằng mắt từng hồ sơ, vừa mất thời gian vừa không phát hiện kịp thời các lỗi hồi quy (regression bugs).

---

### 3. Nâng cấp khung năng lực (Competency Upgrade)

Dựa trên **Competency Framework (L1 — AI Literate, L2 — AI Practitioner, L3 — AI Builder)**:

* **Role lựa chọn**: **AI & Model Engineer (Nguyễn Minh Hoàng)**.
* **Cấp độ hiện tại**: **Gần L2 — AI Practitioner**  
  *(Đã thành thạo tích hợp Vision-Language Model, kỹ thuật RAG và Prompt Engineering nâng cao, nhưng quy trình kiểm định chất lượng mô hình vẫn phụ thuộc vào test thủ công cục bộ).*
* **Năng lực mục tiêu cần nâng tiếp theo**: **AI Evaluation & Automated Quality Benchmarking (Đánh giá chất lượng mô hình tự động)** — bước đệm tiến lên **L3 — AI Builder**.
* **Hành động thực hành trong 30 ngày**:  
  Thiết kế bộ **50 "Golden Test Cases"** bao phủ các ca khó thực tế (hóa đơn rách mép, toa viết tắt, bảng kê viện phí nhiều trang) và viết pipeline tự động chạy kiểm thử hồi quy (automated evals) mỗi khi có thay đổi code/prompt trước khi đưa lên môi trường test.

---

### 4. Kế hoạch phát triển Team trong 30 ngày (Team Growth Plan)

Team thống nhất **3 hành động cụ thể, có chủ sở hữu (Owner), hạn chót (Deadline) và tiêu chí hoàn thành đo lường được**:

| STT | Vấn đề cần giải quyết | Hành động cụ thể trong 30 ngày | Owner (Người phụ trách) | Deadline (Hạn chót) | Dấu hiệu hoàn thành (Acceptance Criteria) |
|:---:|:---|:---|:---:|:---:|:---|
| **1** | **Chất lượng AI & Thiếu bộ đo tự động** *(Eval Gap)* | Xây dựng bộ **50 Golden Cases** (chuẩn hóa dữ liệu ground-truth y tế); tích hợp script đo lường tự động (F1-score, Field Accuracy, Token Cost). | **Nguyễn Minh Hoàng**<br>*(AI Engineer)* | **28/10/2026** | Script `eval_pipeline.py` chạy tự động < 5 phút, xuất báo cáo so sánh chi tiết độ chính xác từng trường, tự động cảnh báo nếu tỷ lệ trích xuất tụt dưới 90%. |
| **2** | **Tốc độ ra sản phẩm chậm** *(Deployment Bottleneck)* | Xây dựng môi trường **Staging Web Sandbox nội bộ** với tính năng *"Drag-and-Drop & Instant Inspection"* (kéo thả ảnh chụp chứng từ -> hiển thị kết quả trích xuất và bounding box trong 3 giây). | **Lê Quốc Khánh**<br>*(Backend/Data)* | **05/11/2026** | Triển khai thành công Web Sandbox nội bộ; Product Lead và 2 thẩm định viên có thể tự truy cập upload thử nghiệm bất cứ lúc nào mà không cần hỗ trợ kỹ thuật. |
| **3** | **Tiến độ & Phối hợp giải quyết Blocker** *(Alignment Gap)* | Thiết lập cơ chế họp cố định **"Weekly Sprint Review & Blocker Clearing" 25 phút vào 16h30 thứ Sáu hàng tuần**; trực tiếp cập nhật tiến độ tương tác với 4 stakeholder ưu tiên. | **Trần Anh Tuấn**<br>*(Product Lead)* | **Bắt đầu 17/10/2026**<br>*(Duy trì liên tục 4 tuần)* | 100% các buổi họp có Action Log gắn hạn hoàn thành cụ thể; tỷ lệ hoàn thành đúng hạn các cam kết trong Sprint tăng từ 70% lên trên 90%. |

---

> **✅ GATE 4 PASS**:
> - Đã chấm đầy đủ 4 khía cạnh sức khỏe team cho cả 3 thành viên với bảng số liệu rõ ràng.
> - Đã phân tích thấu đáo điểm thấp nhất (Tốc độ ra sản phẩm 2.67/5) và điểm chênh lệch (Chất lượng AI), chỉ đúng điểm nghẽn eval.
> - Đã nâng cấp năng lực cho AI Engineer theo khung L1/L2/L3 (từ L2 lên L3 ở mảng AI Evaluation).
> - Growth Plan 30 ngày gồm đúng 3 hành động thực thi, có **Owner cụ thể, Deadline chính xác và Tiêu chí nghiệm thu định lượng**.

---

## 🔍 Phase 5 — Tự soi lỗi, Tính nhất quán & Hoàn thiện bài nộp (Trang tổng kết)

### 1. Bảng kiểm tra tự soi lỗi 4 Artefact (Self-Audit Checklist)

| Artefact | Tiêu chí kiểm tra theo bài giảng | Kết quả tự đánh giá | Minh chứng trong bài làm |
|:---|:---|:---:|:---|
| **Trang 1: Stakeholder Map & Chiến lược** | • Có ít nhất 6 stakeholder cụ thể (không ghi chung chung)?<br>• Đã map chuẩn theo trục Influence × Interest?<br>• Dùng đúng 4 quadrant (Champion/Blocker/Supporter/Bystander) và kiểm tra Stance thực tế?<br>• Đủ 4 hành động cụ thể cho 4 stakeholder ưu tiên? | **ĐẠT (PASS)** | • Xác định **7 stakeholder thực tế** kèm chức danh cụ thể.<br>• Phân bổ rõ ràng trên ma trận 2 trục.<br>• Ghi rõ Stance (Ủng hộ / Trung lập / Chưa ủng hộ) kèm lý giải.<br>• 4 hành động có **deadline, giờ giấc và sản phẩm bàn giao định lượng**. |
| **Trang 2: Pitch & RACI Matrix** | • Pitch áp dụng cấu trúc Conclusion First (Kết luận trước)?<br>• Có số liệu/bằng chứng hỗ trợ thay vì hứa suông?<br>• Có Small Ask cụ thể, khả thi?<br>• Có 1 phản biện xác đáng nhất và giải pháp hạ tầng?<br>• Mỗi dòng trong RACI chỉ có **đúng 1 Accountable (A)**? | **ĐẠT (PASS)** | • Mở đầu bằng đề xuất Pilot 3 tuần trên 200 hồ sơ.<br>• Bằng chứng: **92.4% Exact Match, 1m48s/hồ sơ, 100% bắt lệch**.<br>• Small Ask: Demo 30 phút thứ Năm + 200 hồ sơ ẩn danh test mù.<br>• Phản biện về sai sót y khoa được giải quyết bằng Human-in-the-Loop, Confidence 88% và Rule Engine.<br>• Bảng 6 việc: **Mỗi hàng đúng 1 A duy nhất**, tách biệt R và A. |
| **Trang 3: AI Team Architecture & Resourcing** | • Kiến trúc AI Team có giải thích vì sao phù hợp quy mô?<br>• Phân định rõ Core Roles (cần ngay) & Extended Roles?<br>• Có nhận diện Capability Gap rõ ràng?<br>• Priority Resourcing phân bổ đúng Hire / Outsource / Partner? | **ĐẠT (PASS)** | • Chọn **Embedded AI Team** (phù hợp team 3 người, feedback loop < 24h).<br>• Core: Product Lead, AI Engineer, Backend/Data; Extended: MLOps, Medical Auditor, AI Governance.<br>• 3 Gap: Y tế ➔ **Partner**; Gán nhãn ➔ **Outsource**; MLOps ➔ **Hire** khi scale. |
| **Trang 4: Team Health & Growth Plan** | • Đủ 4 khía cạnh sức khỏe team (Chất lượng, Tiến độ, Tinh thần, Tốc độ)?<br>• Phân tích điểm thấp nhất và điểm chênh lệch?<br>• Chọn 1 competency nâng cấp theo L1/L2/L3?<br>• Kế hoạch 30 ngày có tối đa 3 hành động có Owner + Deadline + Tiêu chí? | **ĐẠT (PASS)** | • Đủ 4 khía cạnh với điểm trung bình của 3 thành viên.<br>• Chỉ ra điểm nghẽn: Tốc độ ra sản phẩm (2.67/5) và chênh lệch Chất lượng AI.<br>• Nâng cấp AI Engineer từ gần L2 lên L3 ở mảng AI Evaluation.<br>• Đúng 3 hành động: **Hoàng (Eval), Khánh (Sandbox), Tuấn (Sprint Review)** có deadline và acceptance criteria. |

---

### 2. Kiểm tra tính nhất quán liên kết (Cross-Artefact Consistency Check)

1. **Tính nhất quán Stakeholder ➔ Pitch & RACI**:
   - Stakeholder quyền lực nhất ở Trang 1 là **Ông Trần Hùng (Head of Claims - Champion)** và **Bà Đỗ Thu Hà (Compliance - Blocker)** được đặt làm đối tượng trọng tâm trong bản Pitch "Kết luận trước" và giữ vai trò Accountable (A) cho việc nghiệm thu / Consulted (C) cho bảo mật trong bảng RACI Trang 2.
2. **Tính nhất quán Capability Gap ➔ Team Health & Growth Plan**:
   - Khoảng trống về năng lực kiểm thử mô hình và MLOps ở Trang 3 kết nối trực tiếp với điểm số thấp về "Tốc độ ra sản phẩm" và vấn đề "Thiếu bộ Automated Evals" ở Trang 4.
3. **Tính nhất quán RACI ➔ Growth Plan Owners**:
   - Trong RACI, *Nguyễn Minh Hoàng* chịu trách nhiệm mô hình AI ➔ Trong Growth Plan phụ trách Xây dựng bộ 50 Golden Cases & Script Eval.
   - *Lê Quốc Khánh* chịu trách nhiệm Ingestion & Hạ tầng ➔ Trong Growth Plan phụ trách Dựng Staging Web Sandbox nội bộ.
   - *Trần Anh Tuấn* chịu trách nhiệm điều phối Pilot và Stakeholders ➔ Trong Growth Plan làm Owner của Weekly Sprint Review & Blocker Clearing.

---

### 3. Thông tin bàn giao Repository & File Báo cáo Nộp bài

* **Tên Repository chính thức**: `Track1_Day25_TeamHTK_` (hoặc `https://github.com/TeamHTK/Track1_Day25_TeamHTK_`)
* **Trưởng nhóm phụ trách nộp**: **Trần Anh Tuấn** (Product Lead)
* **Thành viên tham gia**: Nguyễn Minh Hoàng, Trần Anh Tuấn, Lê Quốc Khánh
* **File báo cáo xuất xưởng PDF (Tối đa đúng 4 trang)**: [`Day25_AI-Team-Lab_TeamHTK.pdf`](file:///d:/Track1_Day25_TeamHTK_/Day25_AI-Team-Lab_TeamHTK.pdf)
  - *Trang 1*: Stakeholder Map & 4 Chiến lược hành động ưu tiên
  - *Trang 2*: Pitch "Kết luận trước", Xử lý phản biện & RACI Matrix
  - *Trang 3*: Thiết kế Embedded AI Team & Priority Resourcing (Hire/Outsource/Partner)
  - *Trang 4*: Đánh giá Team Health & Growth Plan 30 ngày (Action, Owner, Deadline)

---

> **✅ GATE 5 PASS — REPOSITORY & BÁO CÁO ĐÃ SẴN SÀNG NỘP**:
> - Repository có đầy đủ cấu trúc chuẩn chỉnh trong `README.md`.
> - Đã xuất thành công file PDF báo cáo tối đa 4 trang `Day25_AI-Team-Lab_TeamHTK.pdf` ngay tại thư mục gốc.
> - Toàn bộ 4 Artefact có tính nhất quán cao, đáp ứng 100% tiêu chí của tất cả các Gate (Gate 0 đến Gate 5).

---

## 🛡️ Tuyên bố Tuân thủ Quy tắc dùng AI trong Lab (AI Ethics & Compliance)

Đội ngũ **Team HTK** cam kết tuân thủ nghiêm túc 100% quy tắc sử dụng AI theo hướng dẫn của giảng viên:

### 1. Phạm vi ứng dụng AI hỗ trợ hợp lệ (What was leveraged):
* ✅ **Mở rộng góc nhìn Stakeholder**: Dùng AI để rà soát các bên liên quan dễ bị bỏ sót trong chuỗi giá trị bảo hiểm y tế (bổ sung vị trí *Head of Compliance* để xử lý bài toán Nghị định 13/2023/NĐ-CP và *CIO* để giải tỏa rủi ro Core Insurance).
* ✅ **Tối ưu cấu trúc Pitch "Conclusion First"**: Tinh chỉnh thông điệp ngắn gọn, trực diện, loại bỏ văn phong dài dòng, tập trung vào kết luận và Small Ask.
* ✅ **Kiểm định tính chặt chẽ của RACI**: Rà soát tính logic, đảm bảo nguyên tắc vàng **"Mỗi hàng chỉ có đúng 1 Accountable (A) duy nhất"** và tách bạch rõ vai trò R và A.
* ✅ **Tư vấn cấu trúc AI Team & Nguồn lực**: Tham chiếu mô hình *Embedded AI Pod* phù hợp với quy mô nhóm 3 thành viên, tư vấn giải pháp *Priority Resourcing* thông minh (Partner/Outsource/Hire) thay vì rập khuôn tuyển dụng.
* ✅ **Chuyển hóa Team Health thành Actionable Plan**: Biến các nhận định trừu tượng về sức khỏe nhóm thành các hành động đo lường được kèm deadline cụ thể.

### 2. Cam kết tuyệt đối không vi phạm (What was strictly avoided):
* 🚫 **Không bịa stakeholder ảo**: Toàn bộ 7 stakeholder đều tương ứng với các vị trí vận hành và thẩm định có thật trong quy trình xử lý hồ sơ bồi thường bảo hiểm.
* 🚫 **Không bịa số liệu quá đà / hứa hẹn viển vông**: Mọi cam kết hiệu năng (92.4% Exact Match, 1m48s/hồ sơ) đều đi kèm giải pháp kỹ thuật phòng vệ *Human-in-the-Loop* và *Confidence Threshold 88%*, không cam kết tự động hóa 100% vô căn cứ.
* 🚫 **Không vẽ cơ cấu tổ chức "đẹp trên giấy"**: Không sao chép mô hình phòng ban đồ sộ của tập đoàn lớn; toàn bộ trách nhiệm gắn chặt vào năng lực thực tế của 3 thành viên Hoàng, Tuấn, Khánh.
* 🚫 **Không viết Growth Plan chung chung**: Loại bỏ hoàn toàn các khẩu hiệu sáo rỗng như "cần cố gắng hơn", thay bằng các deliverables kỹ thuật có thể verify được (Script `eval_pipeline.py`, Staging Web Sandbox, Weekly Review 25 phút).





