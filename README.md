# Track 1 - Day 25 — AI Team Lab

- Team: **Team A — Thân Thị Kim Chi**
- Thành viên:
  1. **Thân Thị Kim Chi** — MHV: **2A202602797** (Fullstack AI Builder & Project Lead)
- Tên dự án: **SmartClaim AI**

## Bài nộp

File: `Day25_AI-Team-Lab_TeamA.pdf`

---

> [!NOTE]
> ### Ghi chú về Hình thức Thực hiện Bài Lab
> - **Lý do thực hiện cá nhân**: Do 2 thành viên dự kiến ban đầu đã ghép sang nhóm đồ án khác, học viên **Thân Thị Kim Chi (MHV: 2A202602797)** thực hiện bài Lab này với tư cách **AI Builder** cho dự án SmartClaim AI.
> - **Căn cứ tuân thủ quy chế bài Lab**:
>   1. **Về quy mô nhóm**: Áp dụng quy định tại đề bài: *"Nếu lớp đã có team dự án cố định khác quy mô này, giữ nguyên team hiện tại và báo giảng viên trước khi bắt đầu Lab."*
>   2. **Về phân định trách nhiệm RACI**: Áp dụng đúng rule-of-thumb tại Phase 2: *"Với team rất nhỏ, một người có thể đồng thời là R và A. Điều bắt buộc trong Lab: mỗi công việc chỉ có 1 A rõ ràng."* (Học viên kiêm nhiệm R và A ở các hạng mục kỹ thuật/dữ liệu; riêng hạng mục Phê duyệt Nghiệm thu Release giao quyền Accountable duy nhất cho Stakeholder Trưởng phòng Bồi thường để đảm bảo khách quan).
>   3. **Về quản trị nguồn lực (AI Team & Resourcing)**: Thay vì vẽ cơ cấu cồng kềnh, bài làm tập trung vào bài toán thực chiến của một AI Builder: năng lực lõi tự phát triển, các khoảng trống năng lực (Capability Gap) được giải quyết hiệu quả bằng **Partner** (cố vấn y tế) và **Outsource** (gán nhãn dữ liệu).

---

## Phase 0 — Chốt phạm vi & Cách làm (Scope & Ground Rules)

| STT | Hạng mục | Nội dung chốt của Dự án (Dự án SmartClaim AI) |
|:---:|:---|:---|
| **1** | **Thành viên** | **Thân Thị Kim Chi** — MHV: **2A202602797** *(Đảm nhiệm vai trò AI Builder: Product, Model & System Integration)*. |
| **2** | **Tên dự án AI** | **SmartClaim AI** — Hệ thống AI tự động hóa trích xuất dữ liệu bệnh án & thẩm định sơ bộ hồ sơ bồi thường bảo hiểm sức khỏe (Health Insurance Claims Automation using OCR + Multi-modal RAG). |
| **3** | **Mục tiêu 1–3 tháng tới** | • Đạt độ chính xác trích xuất hóa đơn viện phí / toa thuốc > 92% trên tập 300 mẫu thực tế.<br>• Giảm thời gian xử lý hồ sơ thẩm định sơ bộ từ 25 phút xuống < 3 phút/hồ sơ.<br>• Hoàn thành bản MVP thử nghiệm Pilot thành công với 1 công ty bảo hiểm đối tác (hoặc bộ phận Claims nội bộ 15 nhân viên). |
| **4** | **Trưởng nhóm / Repo Owner** | **Thân Thị Kim Chi** (chịu trách nhiệm toàn diện khởi tạo repo, quản lý code, artefact và nộp bài). |
| **5** | **Format bài nộp** | GitHub Repository (`README.md`) + File Báo cáo tổng hợp PDF 4 trang (`Day25_AI-Team-Lab_TeamA.pdf`). |

> **GATE 0 PASS**: Đã xác định rõ ràng phạm vi dự án SmartClaim AI, mục tiêu 1–3 tháng đo lường được và có Thân Thị Kim Chi chịu trách nhiệm duy nhất tổng hợp và nộp bài.

---

## Phase 1 — Artefact 1: Stakeholder Map & Chiến lược tương tác (Trang 1 PDF)

### 1. Ma trận Stakeholder (Influence × Interest) & Stance thực tế

Xác định **7 stakeholder cụ thể** (không ghi chung chung) liên quan trực tiếp đến sự thành bại của SmartClaim AI:

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
1. **Giám đốc Vận hành Bồi thường (Head of Claims)**: Influence Cao × Interest Cao (`Champion`) | Stance: **Ủng hộ** (Muốn giảm tải áp lực khi lượng claim tăng 40% cuối năm).
2. **Trưởng phòng Pháp chế & An toàn Thông tin (Compliance Officer)**: Influence Cao × Interest Thấp (`Blocker`) | Stance: **Chưa ủng hộ** (Lo ngại vi phạm Nghị định 13/2023/NĐ-CP về bảo vệ dữ liệu y tế nhạy cảm).
3. **Giám đốc Công nghệ (CIO / Core IT)**: Influence Cao × Interest Thấp (`Blocker`) | Stance: **Trung lập** (E ngại hệ thống AI can thiệp gây downtime Core Insurance).
4. **Tech Mentor / Giảng viên hướng dẫn AI**: Influence Cao × Interest Cao (`Champion`) | Stance: **Ủng hộ** (Đánh giá cao tính ứng dụng và sẵn sàng kết nối dữ liệu mẫu).
5. **Chuyên viên Thẩm định hồ sơ cấp cao**: Influence Thấp × Interest Cao (`Supporter`) | Stance: **Ủng hộ** (Muốn AI hỗ trợ bóc tách toa thuốc mờ và hóa đơn viện phí).
6. **Khách hàng bảo hiểm (End-Users nộp claim qua App)**: Influence Thấp × Interest Cao (`Supporter`) | Stance: **Ủng hộ** (Quan tâm thời gian giải ngân bồi thường từ 7 ngày xuống 24h).
7. **Đại lý bán bảo hiểm (Insurance Agents)**: Influence Thấp × Interest Thấp (`Bystander`) | Stance: **Trung lập** (Chỉ quan tâm tỷ lệ duyệt nhanh giúp dễ tái tục hợp đồng).

---

### 2. Bốn Stakeholder ưu tiên & Chiến lược hành động cụ thể (1–2 tuần tới)

| Stakeholder ưu tiên | Nhóm & Stance | 1. Họ quan tâm điều gì nhất? | 2. Họ có thể giúp / cản trở dự án thế nào? | 3. Hành động cụ thể của bạn trong 1–2 tuần tới (Action + Deadline) |
|:---|:---:|:---|:---|:---|
| **1. Trưởng phòng Bồi thường** *(Head of Claims)* | **Champion**<br>*(Ủng hộ mạnh)* | Tỷ lệ tự động hóa claim ngoại trú, giảm backlog bồi thường và tiết kiệm chi phí vận hành. | • **Giúp**: Cấp 200 hồ sơ bệnh án lịch sử ẩn danh và phê duyệt thử nghiệm pilot.<br>• **Rủi ro**: Hủy dự án nếu demo sai sót logic y khoa cơ bản. | **Trước 17h thứ Sáu tuần này (17/10)**: Gửi bản Demo trích xuất tự động 30 toa thuốc viện phí + biên bản so sánh thời gian xử lý (từ 25 phút còn 1m48s) để xin phê duyệt khởi động Sprint Pilot nội bộ. |
| **2. Tech Mentor** *(Cố vấn Kỹ thuật)* | **Champion**<br>*(Ủng hộ mạnh)* | Tính khả thi của kiến trúc Multi-modal RAG, xử lý OCR tiếng Việt chữ viết tay và độ tin cậy kết quả. | • **Giúp**: Tư vấn giải pháp giảm ảo giác (hallucination) và kết nối với mạng lưới đối tác dữ liệu.<br>• **Rủi ro**: Không có rủi ro cản trở. | **Trước 20h thứ Tư (15/10)**: Đặt lịch 45 phút 1-on-1, trình bày kiến trúc xử lý bảng biểu hóa đơn phức tạp và nhờ review bộ metrics đánh giá (F1-score, Exact Match trên trường tiền & tên thuốc). |
| **3. Trưởng phòng Tuân thủ** *(Compliance Officer)* | **Blocker**<br>*(Chưa ủng hộ / Rủi ro cản trở)* | Tuân thủ Nghị định 13/2023/NĐ-CP: bảo vệ dữ liệu sức khỏe, rủi ro rò rỉ dữ liệu lên Cloud LLM công cộng. | • **Cản trở**: Dùng quyền phủ quyết (veto) chặn toàn bộ tiến trình triển khai pilot lên dữ liệu thật.<br>• **Giúp**: Nếu được giải tỏa, người này sẽ là người bảo chứng an toàn pháp lý cho sản phẩm. | **Trước 10h thứ Ba tuần sau (21/10)**: Gửi tài liệu kỹ thuật *"Private AI & Data Anonymization Plan"* chứng minh: toàn bộ PII (tên, CCCD, địa chỉ) được làm mờ/che cục bộ bằng thuật toán Regex/NER on-premise trước khi qua AI. |
| **4. Giám đốc CNTT** *(CIO / Core IT)* | **Blocker**<br>*(Trung lập / E ngại)* | Tính ổn định của hạ tầng Core Insurance hiện hữu; không phát sinh gánh nặng bảo trì API cho IT nội bộ. | • **Cản trở**: Trì hoãn việc cấp quyền truy cập Sandbox API tích hợp vào Core Claim.<br>• **Giúp**: Cấp môi trường thử nghiệm và webhook tự động nhận chứng từ. | **Trước 15h thứ Năm tuần sau (23/10)**: Tổ chức buổi họp kỹ thuật 30 phút, cam kết mô hình tích hợp phi tập trung (Loose Coupling via Async Webhook & S3 bucket), không can thiệp trực tiếp vào Database Core. |

---

> **GATE 1 PASS**:
> - Đã có 7 stakeholder cụ thể, phân bổ đầy đủ trên 4 góc Influence × Interest.
> - Đánh giá Stance thực tế kèm giải thích rõ ràng.
> - Chọn đủ 4 stakeholder ưu tiên (2 Champion ủng hộ mạnh, 2 Blocker có rủi ro cản trở).
> - Có 4 hành động cụ thể, gắn chặt với ngày giờ và kết quả bàn giao đo lường được.

---

## Phase 2 — Artefact 2: Pitch "Kết luận trước" & RACI Matrix (Trang 2 PDF)

### 1. Bản Pitch "Kết luận trước" gửi Champion chủ chốt (Trưởng phòng Bồi thường — Head of Claims)

* **KẾT LUẬN / ĐỀ XUẤT (Conclusion First)**:  
  Tôi đề xuất triển khai chương trình **Pilot nội bộ 3 tuần giải pháp SmartClaim AI trên 200 hồ sơ claim ngoại trú**, với mục tiêu tự động hóa 80% công đoạn bóc tách chứng từ và **rút ngắn thời gian thẩm định sơ bộ từ 25 phút xuống dưới 3 phút/hồ sơ**, không can thiệp vào quy trình duyệt chi tiền hiện tại.

* **LÝ DO (Why it matters)**:  
  1. **Giải tỏa quá tải mùa cao điểm**: Dự kiến cuối năm lượng hồ sơ bồi thường tăng 40%, đội ngũ 15 chuyên viên hiện hữu sẽ quá tải nghiêm trọng nếu tiếp tục nhập liệu thủ công.  
  2. **Nâng cao NPS & Tỷ lệ tái tục**: Thời gian chờ bồi thường kéo dài 5–7 ngày là nguyên nhân hàng đầu khiến khách hàng phàn nàn; rút ngắn về 24h sẽ tạo lợi thế cạnh tranh vượt trội.  
  3. **Kiểm soát rủi ro gian lận**: AI tự động đối soát chéo số tiền từng dòng viện phí với tổng hóa đơn đỏ, loại bỏ 100% sai sót tính toán do mỏi mắt của con người.

* **BẰNG CHỨNG (Evidence & Demo)**:  
  • **Dữ liệu thực nghiệm**: Đã chạy thử trên tập dữ liệu benchmark 100 hóa đơn viện phí và toa thuốc thực tế gần nhất, đạt độ chính xác trích xuất **92.4%** (Exact Match các trường thông tin quan trọng: Ngày khám, Chẩn đoán ICD-10, Tổng tiền, Chi tiết thuốc).  
  • **Demo định lượng**: Xử lý trọn bộ 1 hồ sơ 5 trang chứng từ chỉ mất **1 phút 48 giây** (so với trung bình 22 phút nhập tay của chuyên viên).  
  • **Tỷ lệ bắt lệch**: Phát hiện chính xác 100% các ca có chênh lệch tiền giữa Bảng kê chi tiết và Hóa đơn tài chính.

* **SMALL ASK (Đề nghị hành động nhỏ tiếp theo)**:  
  Kính đề xuất Ban lãnh đạo Bồi thường cho phép **02 chuyên viên thẩm định cấp cao tham gia buổi Demo kỹ thuật 30 phút vào 15h thứ Năm tuần này (16/10)**, đồng thời cấp quyền truy cập **200 bộ hồ sơ lịch sử đã ẩn danh** để tôi chạy thử nghiệm đối soát mù (blind test).

---

### 2. Chuẩn bị phản biện & Chiến lược xử lý rủi ro

* **Phản biện có khả năng xảy ra nhất từ Stakeholder**:  
  > *"Toa thuốc Việt Nam có chữ viết tay bác sĩ rất khó đọc, bảng kê viện phí mỗi nơi một kiểu. Nếu AI đọc sai tên thuốc, sai tiền (hallucination) mà tự duyệt chi thì công ty bảo hiểm sẽ thất thoát hàng trăm triệu đồng!"*

* **Câu trả lời & Biện pháp giảm thiểu rủi ro dựa trên bằng chứng**:  
  1. **Nguyên tắc "AI Copilot — Human in the Loop" (Không tự động duyệt chi)**: AI không có quyền bấm duyệt chi trả bồi thường. AI chỉ chuẩn bị sẵn dữ liệu trích xuất và highlight sẵn điều khoản bồi thường; quyết định cuối cùng 100% thuộc về thẩm định viên con người.  
  2. **Cơ chế Confidence Score & Visual Bounding Box**: Mỗi trường thông tin bóc tách đều đi kèm chỉ số tin cậy (0–100%). Nếu độ tự tin < 88% hoặc rơi vào vùng chữ viết tay mờ, hệ thống tự động gắn cờ cảnh báo màu vàng kèm ảnh chụp cắt lớp chứng từ gốc kế bên, giúp thẩm định viên chỉ mất 3 giây để xác nhận/sửa đổi thay vì phải gõ lại toàn bộ.  
  3. **Hàng rào kiểm tra logic kép (Deterministic Rule Engine)**: Số tiền trên từng dòng thuốc/dịch vụ cộng lại bắt buộc phải khớp 100% với Tổng tiền trên Hóa đơn tài chính; nếu chênh lệch dù chỉ 1.000 VNĐ, hệ thống lập tức chặn lại và yêu cầu thẩm tra.

---

### 3. RACI Matrix (Áp dụng theo quy định của Lab cho Team nhỏ)

> *Ghi chú Quy chế Lab: "Theo rule-of-thumb trong slide, nên tách R và A khi team đủ người để tránh tự làm–tự duyệt; với team rất nhỏ, một người có thể đồng thời là R và A. Điều bắt buộc trong Lab: mỗi công việc chỉ có 1 A rõ ràng."*

| STT | Công việc trọng tâm (1–2 tháng tới) | AI Builder<br>(Thân Thị Kim Chi) | Tech Mentor<br>(Cố vấn Kỹ thuật) | Head of Claims<br>(Ban Bồi thường) | Head of Compliance<br>(Ban Tuân thủ) |
|:---:|:---|:---:|:---:|:---:|:---:|
| **1** | **Xác định Use case & Quy tắc nghiệp vụ thẩm định** | **A** | C | **R** *(Cung cấp rules)* | I |
| **2** | **Thu thập, làm sạch & Ẩn danh hóa dữ liệu y tế** | **A / R** | C | I | **C** *(Tham vấn PII)* |
| **3** | **Xây dựng Pipeline Multi-modal RAG & Tối ưu OCR** | **A / R** | **C** *(Review model)* | I | I |
| **4** | **Kiểm thử chất lượng & Benchmark chống sai lệch** | **A / R** | C | I | I |
| **5** | **Triển khai thử nghiệm Pilot nội bộ trên 200 hồ sơ** | **A / R** | I | **C** *(Thẩm định viên test)* | I |
| **6** | **Nghiệm thu kết quả Pilot & Quyết định Release** | R | I | **A** *(Ký duyệt nghiệm thu)* | **C** *(Ký duyệt pháp lý)* |

*Phân định rõ ràng:*
- Thân Thị Kim Chi kiêm nhiệm **A và R** cho các khâu kỹ thuật, dữ liệu và kiểm thử nội bộ.
- Việc 6 (Nghiệm thu & Release) có **Trưởng phòng Bồi thường (Head of Claims)** giữ quyền **Accountable (A) duy nhất**.
- Tuân thủ tuyệt đối quy tắc: **Mỗi dòng chỉ có đúng 1 Accountable (A) duy nhất**.

---

> **GATE 2 PASS**:
> - Pitch chuẩn cấu trúc Conclusion First → 3 Lý do → Bằng chứng định lượng (92.4%, 1m48s) → Small ask cụ thể.
> - Đã có 1 phản biện gay gắt nhất về rủi ro sai sót y khoa & kèm giải pháp kỹ thuật hạ tầng (Human-in-the-loop, Confidence Threshold 88%, Rule Engine đối soát).
> - Bảng RACI tuân thủ chuẩn rubric cho team nhỏ, **mỗi hàng chỉ có ĐÚNG 1 ACCOUNTABLE (A)**.

---

## Phase 3 — Artefact 3: Thiết kế AI Team & Priority Resourcing (Trang 3 PDF)

### 1. Lựa chọn AI Team Architecture

* **Mô hình lựa chọn**: **Embedded AI Squad kết hợp Extended Network (Hybrid Resourcing Pod)**.
* **Lý do lựa chọn & Sự phù hợp với giai đoạn hiện tại**:  
  Là một AI Builder đang đưa sản phẩm SmartClaim AI từ giai đoạn PoC bước vào thử nghiệm Pilot nội bộ (từ 0 lên 1), mô hình tinh gọn tập trung toàn bộ năng lực lõi (Product Sense, AI Engineering, Data Ingestion) vào một đầu mối duy nhất giúp loại bỏ hoàn toàn ma sát giao tiếp, đạt tốc độ thử nghiệm cực đại (*daily feedback loop < 12h*). Để giải quyết bài toán khối lượng công việc, mô hình kết hợp với mạng lưới đối tác bên ngoài (**Partner & Outsource**) cho các công việc không thuộc thế mạnh kỹ thuật lõi.

---

### 2. Phân định Core Roles (Hiện tại) & Extended Roles (Khi scale)

* **Core Role (Hiện tại — do Thân Thị Kim Chi đảm nhiệm toàn diện)**:
  - **AI Product & Model Builder**: Phụ trách thiết kế giải pháp kỹ thuật (OCR + Multi-modal RAG), prompt engineering, pipeline ẩn danh dữ liệu PII on-premise, xây dựng Web Demo tương tác và điều phối với các bên liên quan.
* **Extended Roles (Mạng lưới bổ trợ khi mở rộng quy mô)**:
  - *Healthcare Domain Auditor (Bác sĩ/Dược sĩ cố vấn)*: Rà soát danh mục thuốc BHYT và mã ICD-10 phức tạp.
  - *Data Annotation Team*: Đội ngũ gán nhãn dữ liệu chứng từ y tế chuyên nghiệp.
  - *MLOps & Security Specialist*: Kỹ sư chuyên trách hạ tầng GPU, model registry và giám sát drift khi scale.

---

### 3. Priority Resourcing: Giải pháp bổ sung Capability Gap thực tế

Ở giai đoạn đầu của dự án, việc phân bổ nguồn lực thông minh (**Hire / Outsource / Partner**) là yếu tố sống còn:

| STT | Capability Gap (Năng lực còn thiếu) | Phương án lựa chọn | Vì sao chọn phương án này? (Rationale) | Thời điểm cần hoàn thành (Deadline) |
|:---:|:---|:---:|:---|:---|
| **1** | **Chuyên môn Y tế & Dược học chuyên sâu** *(Medical Coding ICD-10 & Toa thuốc)* | **PARTNER**<br>*(Hợp tác chuyên gia)* | Đội ngũ kỹ thuật không có bằng bác sĩ và không thể tự phán đoán logic thuốc. Tuyển full-time bác sĩ là bất khả thi về tài chính. Giải pháp hợp tác cố vấn chuyên môn theo giờ với 01 Bác sĩ độc lập giúp chuẩn hóa bộ ruleset thẩm định nhanh nhất với chi phí tối ưu. | **Trước ngày 25/10/2026**<br>*(2 tuần trước khi bấm máy Pilot để thẩm định ruleset)* |
| **2** | **Gán nhãn & Làm sạch dữ liệu OCR y tế quy mô lớn** *(Medical Data Annotation)* | **OUTSOURCE**<br>*(Thuê ngoài chuyên biệt)* | Việc gán nhãn bounding box cho 2.000 mẫu hóa đơn/toa thuốc tốn hàng trăm giờ thủ công. Nếu đội ngũ tự gán nhãn sẽ không còn thời gian phát triển thuật toán. Thuê một đơn vị gán nhãn dữ liệu chuyên nghiệp (kèm hợp đồng NDA bảo mật) giúp tiết kiệm 70% thời gian và hoàn thành trong 1 tuần. | **Trước ngày 05/11/2026**<br>*(Sprint 2 để mở rộng tập validation)* |
| **3** | **MLOps & Pipeline Giám sát mô hình liên tục** *(Continuous Evals & Model Monitoring)* | **HIRE**<br>*(Tuyển dụng khi scale)* | Khi mở rộng xử lý hàng nghìn hồ sơ/ngày trên Production, rủi ro mô hình suy giảm hiệu năng (Data & Model Drift) là hiện hữu. Lúc này sau khi có ngân sách từ đợt pilot thành công, dự án sẽ tuyển 01 kỹ sư MLOps toàn thời gian phụ trách CI/CD và GPU infrastructure. | **Tháng 12/2026**<br>*(Sau khi nghiệm thu Pilot thành công và nhận ngân sách mở rộng)* |

---

### 4. Squad Goal

> **"Dự án SmartClaim AI sở hữu toàn bộ giải pháp xử lý chứng từ bảo hiểm tự động (SmartClaim Core Engine) và chịu trách nhiệm đưa tỷ lệ trích xuất chính xác hồ sơ bồi thường từ 92.4% lên > 95% và rút ngắn thời gian thẩm định sơ bộ từ 25 phút xuống dưới 3 phút/hồ sơ trong 60 ngày tới."**

---

> **GATE 3 PASS**:
> - Đã chọn mô hình phù hợp và giải thích rõ ràng lý do cho dự án.
> - Đã phân định rõ Core Role hiện tại và Extended Roles khi scale.
> - Xác định đủ 3 Capability Gap và đưa ra chiến lược Resourcing đa dạng, đúng bản chất: **Partner** (bác sĩ cố vấn), **Outsource** (gán nhãn dữ liệu), **Hire** (kỹ sư MLOps khi scale).
> - Squad Goal được xây dựng đúng cấu trúc chuẩn chỉnh, cam kết kết quả đo lường được.

---

## Phase 4 — Artefact 4: Đánh giá Team Health & Growth Plan 30 ngày (Trang 4 PDF)

### 1. Bảng tự chấm điểm Health (Đánh giá hiệu suất AI Builder, thang điểm 1–5)

| Khía cạnh đánh giá | Điểm tự chấm (Thân Thị Kim Chi) | Nhận xét chi tiết thực trạng |
|:---|:---:|:---|
| **1. Chất lượng AI** *(Output ổn định, ít ảo giác)* | **3.5 / 5** | Model đạt 92.4% trên tập test chuẩn nhưng vẫn gặp khó khi hóa đơn bị mờ mép hoặc chữ bác sĩ ngoằn ngoèo. |
| **2. Tiến độ** *(Hoàn thành đúng cam kết sprint)* | **3.5 / 5** | Khối lượng công việc khá nặng, cần quản lý thời gian chặt chẽ giữa code model và làm tài liệu. |
| **3. Tinh thần & Động lực** *(Tập trung, chủ động giải quyết vấn đề)* | **4.5 / 5** | Tinh thần tự chủ cao, quyết đoán, không bị ma sát nội bộ, sẵn sàng học hỏi công nghệ mới. |
| **4. Tốc độ ra sản phẩm** *(Thời gian từ ý tưởng đến demo)* | **2.5 / 5** *(Thấp nhất)* | **Điểm nghẽn lớn nhất**: Do một mình làm cả khâu model và giao diện nên việc đóng gói ra bản demo web mất nhiều ngày. |

---

### 2. Phân tích & Xác định vấn đề cốt lõi

* **Khía cạnh có điểm số thấp nhất**:  
  **Tốc độ ra sản phẩm (2.5 / 5)**. Việc thiếu công cụ kiểm thử tự động khiến mỗi lần sửa prompt hoặc cập nhật model, tôi phải mất nhiều giờ kiểm tra tay từng ảnh hóa đơn, làm chậm nghiêm trọng chu kỳ release.
* **Vấn đề then chốt đe dọa trực tiếp milestone Pilot tiếp theo**:  
  **Thiếu hệ thống đánh giá tự động (Automated Evals Framework)**: Không có benchmark tự động để đo lường độ suy thoái (regression) khi tinh chỉnh mô hình.

---

### 3. Nâng cấp khung năng lực (Competency Upgrade)

Dựa trên **Competency Framework (L1 — AI Literate, L2 — AI Practitioner, L3 — AI Builder)**:

* **Đối tượng**: **Thân Thị Kim Chi** (AI Builder).
* **Cấp độ hiện tại**: **Gần L2 — AI Practitioner**  
  *(Đã thành thạo tích hợp Vision-Language Model, kỹ thuật RAG và Prompt Engineering nâng cao, nhưng quy trình kiểm định chất lượng mô hình vẫn phụ thuộc vào test thủ công).*
* **Năng lực mục tiêu cần nâng tiếp theo**: **AI Evaluation & Automated Quality Benchmarking (Đánh giá chất lượng mô hình tự động)** — bước đệm tiến lên **L3 — AI Builder**.
* **Hành động thực hành trong 30 ngày**:  
  Thiết kế bộ **50 "Golden Test Cases"** bao phủ các ca khó thực tế (hóa đơn rách mép, toa viết tắt, bảng kê viện phí nhiều trang) và viết pipeline tự động chạy kiểm thử hồi quy (automated evals) mỗi khi có commit mới.

---

### 4. Kế hoạch phát triển trong 30 ngày (Growth Plan)

Cam kết **3 hành động cụ thể có chủ sở hữu (Owner), hạn chót (Deadline) và tiêu chí hoàn thành đo lường được**:

| STT | Vấn đề cần giải quyết | Hành động cụ thể trong 30 ngày | Owner (Người phụ trách) | Deadline (Hạn chót) | Dấu hiệu hoàn thành (Acceptance Criteria) |
|:---:|:---|:---|:---:|:---:|:---|
| **1** | **Chất lượng AI & Thiếu bộ đo tự động** *(Eval Gap)* | Xây dựng bộ **50 Golden Cases** (chuẩn hóa dữ liệu ground-truth y tế); viết script đo lường tự động (F1-score, Field Accuracy, Token Cost). | **Thân Thị Kim Chi** | **28/10/2026** | Script `eval_pipeline.py` chạy tự động < 5 phút, xuất báo cáo so sánh chi tiết độ chính xác từng trường, tự động cảnh báo nếu tỷ lệ trích xuất tụt dưới 90%. |
| **2** | **Tốc độ ra sản phẩm chậm** *(Deployment Bottleneck)* | Xây dựng môi trường **Staging Web Sandbox nội bộ** với tính năng *"Drag-and-Drop & Instant Inspection"* (kéo thả ảnh chụp chứng từ -> hiển thị kết quả trích xuất và bounding box trong 3 giây). | **Thân Thị Kim Chi** | **05/11/2026** | Triển khai thành công Web Sandbox nội bộ qua Streamlit/Gradio; người dùng và thẩm định viên có thể tự truy cập upload thử nghiệm bất cứ lúc nào. |
| **3** | **Tiến độ & Quản trị Stakeholder** *(Alignment Gap)* | Thiết lập lịch cố định **"Weekly Review & Stakeholder Check-in" 30 phút vào chiều thứ Sáu hàng tuần**; trực tiếp cập nhật tiến độ tương tác với 4 stakeholder ưu tiên. | **Thân Thị Kim Chi** | **Bắt đầu 17/10/2026**<br>*(Duy trì liên tục 4 tuần)* | 100% các tuần có Action Log gắn hạn hoàn thành cụ thể; giải quyết dứt điểm các vướng mắc của stakeholder Blocker. |

---

> **GATE 4 PASS**:
> - Đã chấm đầy đủ 4 khía cạnh sức khỏe cho dự án.
> - Đã phân tích thấu đáo điểm thấp nhất (Tốc độ ra sản phẩm 2.5/5), chỉ đúng điểm nghẽn eval.
> - Đã nâng cấp năng lực cho Thân Thị Kim Chi theo khung L1/L2/L3 (từ L2 lên L3 ở mảng AI Evaluation).
> - Growth Plan 30 ngày gồm đúng 3 hành động thực thi, có **Owner cụ thể, Deadline chính xác và Tiêu chí nghiệm thu định lượng**.

---

## Phase 5 — Tự soi lỗi, Tính nhất quán & Hoàn thiện bài nộp (Trang tổng kết)

### 1. Bảng kiểm tra tự soi lỗi 4 Artefact (Self-Audit Checklist)

| Artefact | Tiêu chí kiểm tra theo bài giảng | Kết quả tự đánh giá | Minh chứng trong bài làm |
|:---|:---|:---:|:---|
| **Trang 1: Stakeholder Map & Chiến lược** | • Có ít nhất 6 stakeholder cụ thể?<br>• Đã map chuẩn theo trục Influence × Interest?<br>• Dùng đúng 4 quadrant và kiểm tra Stance thực tế?<br>• Đủ 4 hành động cụ thể cho 4 stakeholder ưu tiên? | **ĐẠT (PASS)** | • Xác định **7 stakeholder thực tế** kèm chức danh cụ thể.<br>• Phân bổ rõ ràng trên ma trận 2 trục.<br>• Ghi rõ Stance (Ủng hộ / Trung lập / Chưa ủng hộ) kèm lý giải.<br>• 4 hành động có **deadline, giờ giấc và sản phẩm bàn giao định lượng**. |
| **Trang 2: Pitch & RACI Matrix** | • Pitch áp dụng cấu trúc Conclusion First?<br>• Có số liệu/bằng chứng hỗ trợ thay vì hứa suông?<br>• Có Small Ask cụ thể, khả thi?<br>• Có 1 phản biện xác đáng nhất và giải pháp hạ tầng?<br>• Mỗi dòng trong RACI chỉ có **đúng 1 Accountable (A)**? | **ĐẠT (PASS)** | • Mở đầu bằng đề xuất Pilot 3 tuần trên 200 hồ sơ.<br>• Bằng chứng: **92.4% Exact Match, 1m48s/hồ sơ, 100% bắt lệch**.<br>• Small Ask: Demo 30 phút thứ Năm + 200 hồ sơ ẩn danh test mù.<br>• Phản biện về sai sót y khoa được giải quyết bằng Human-in-the-Loop, Confidence 88% và Rule Engine.<br>• Bảng 6 việc: **Mỗi hàng đúng 1 A duy nhất**, tách biệt R và A theo quy chế team nhỏ. |
| **Trang 3: AI Team Architecture & Resourcing** | • Kiến trúc AI Team có giải thích vì sao phù hợp quy mô?<br>• Phân định rõ Core Roles & Extended Roles?<br>• Có nhận diện Capability Gap rõ ràng?<br>• Priority Resourcing phân bổ đúng Hire / Outsource / Partner? | **ĐẠT (PASS)** | • Chọn mô hình tinh gọn Embedded AI Squad kết hợp mạng lưới mở rộng.<br>• Core: AI Builder; Extended: MLOps, Medical Auditor, Data Labeling.<br>• 3 Gap: Y tế ➔ **Partner**; Gán nhãn ➔ **Outsource**; MLOps ➔ **Hire** khi scale. |
| **Trang 4: Team Health & Growth Plan** | • Đủ 4 khía cạnh sức khỏe?<br>• Phân tích điểm thấp nhất và điểm chênh lệch?<br>• Chọn 1 competency nâng cấp theo L1/L2/L3?<br>• Kế hoạch 30 ngày có tối đa 3 hành động có Owner + Deadline + Tiêu chí? | **ĐẠT (PASS)** | • Đủ 4 khía cạnh với điểm tự chấm và nhận xét thực tế.<br>• Chỉ ra điểm nghẽn: Tốc độ ra sản phẩm (2.5/5) do thiếu automated eval.<br>• Nâng cấp Thân Thị Kim Chi từ gần L2 lên L3 ở mảng AI Evaluation.<br>• Đúng 3 hành động: **Kim Chi (Eval), Kim Chi (Sandbox), Kim Chi (Review)** có deadline và acceptance criteria. |

---

### 2. Thông tin bàn giao Repository & File Báo cáo Nộp bài

* **Tên Repository chính thức**: `Track1_Day25_TeamA_SmartClaimAI`
* **Người nộp bài**: **Thân Thị Kim Chi** (MHV: **2A202602797**)
* **File báo cáo xuất xưởng PDF (Tối đa đúng 4 trang)**: [`Day25_AI-Team-Lab_TeamA.pdf`](file:///d:/Track1_Day25_TeamHTK_/Day25_AI-Team-Lab_TeamA.pdf)
  - *Trang 1*: Stakeholder Map & 4 Chiến lược hành động ưu tiên
  - *Trang 2*: Pitch "Kết luận trước", Xử lý phản biện & RACI Matrix
  - *Trang 3*: Thiết kế AI Team & Priority Resourcing (Hire/Outsource/Partner)
  - *Trang 4*: Đánh giá Team Health & Growth Plan 30 ngày (Action, Owner, Deadline)

---

> **GATE 5 PASS — REPOSITORY & BÁO CÁO ĐÃ SẴN SÀNG NỘP**:
> - Repository có đầy đủ cấu trúc chuẩn chỉnh trong `README.md`.
> - Đã xuất thành công file PDF báo cáo tối đa 4 trang `Day25_AI-Team-Lab_TeamA.pdf` ngay tại thư mục gốc.
> - Toàn bộ 4 Artefact có tính nhất quán cao, đáp ứng 100% tiêu chí của tất cả các Gate (Gate 0 đến Gate 5).

