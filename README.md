# Track 1 - Day 25 — AI Team Lab

- Team: **Team A**
- Thành viên:
  1. **Thân Thị Kim Chi** — MHV: **2A202602797**

## Bài nộp

File: `Day25_AI-Team-Lab_TeamA.pdf`

---

> [!NOTE]
> **Báo cáo về Quy mô Nhóm & Căn cứ thực hiện theo Quy chế bài Lab:**
> - **Hoàn cảnh thực tế**: Ban đầu nhóm có 3 thành viên, nhưng do 2 bạn đã chuyển ghép sang nhóm đồ án khác theo phân bổ lớp, học viên **Thân Thị Kim Chi** đã báo cáo giảng viên/mentor và được chấp thuận bảo lưu đồ án thực tế **SmartClaim AI** để thực hiện độc lập với vai trò **AI Builder**.
> - **Căn cứ tuân thủ quy chế bài Lab**:
>   1. *Về quy mô team*: Áp dụng quy định tại đề bài: *"Nếu lớp đã có team dự án cố định khác quy mô này, giữ nguyên team hiện tại và báo giảng viên trước khi bắt đầu Lab."*
>   2. *Về phân định trách nhiệm RACI*: Áp dụng đúng quy tắc bài Lab cho team nhỏ: *"Với team rất nhỏ, một người có thể vừa R vừa A. Điều bắt buộc trong Lab: mỗi công việc chỉ có 1 A rõ ràng."* (Học viên kiêm nhiệm R và A các khâu kỹ thuật; khâu Quyết định Release vẫn giao quyền A duy nhất cho Stakeholder Bồi thường).
>   3. *Về khối lượng & Chuẩn đầu ra*: Hoàn thành đầy đủ 100% chuẩn đầu ra của tất cả 6 Gate (Gate 0 đến Gate 5) như một team hoàn chỉnh, xử lý các khoảng trống năng lực qua mô hình thực tế: **Partner** (cố vấn y tế) và **Outsource** (gán nhãn).

---

## Phase 0 — Chốt phạm vi & Cách làm (Scope & Ground Rules)

| STT | Hạng mục | Nội dung thống nhất |
|:---:|:---|:---|
| **1** | **Thành viên** | **Thân Thị Kim Chi** — MHV: **2A202602797** (AI Builder & Project Lead) |
| **2** | **Tên dự án** | **SmartClaim AI** — Hệ thống tự động trích xuất chứng từ & thẩm định sơ bộ hồ sơ bồi thường bảo hiểm |
| **3** | **Mục tiêu 1–3 tháng** | • Độ chính xác trích xuất hóa đơn/toa thuốc **> 92%**.<br>• Giảm thời gian xử lý từ **25 phút xuống < 3 phút/hồ sơ**.<br>• Hoàn thành thử nghiệm **Pilot nội bộ 200 hồ sơ claim**. |
| **4** | **Trưởng nhóm / Repo Owner** | **Thân Thị Kim Chi** (chịu trách nhiệm tạo repo, quản lý artefact và nộp bài) |
| **5** | **Format bài nộp** | GitHub Repository (`README.md`) + File PDF 4 trang (`Day25_AI-Team-Lab_TeamA.pdf`) |

---

## Phase 1 — Stakeholder Map & Chiến lược (Trang 1 PDF)

### 1. Ma trận Stakeholder (Influence × Interest) & Stance

```
                     [ INTEREST: MỨC ĐỘ QUAN TÂM ]
               THẤP                               CAO
       +----------------------------------+----------------------------------+
   C   | [BLOCKER]                        | [CHAMPION]                       |
   A   | • Compliance Officer (Chưa ủng hộ)| • Head of Claims (Ủng hộ mạnh)   |
   O   | • CIO / Core IT (Trung lập)      | • Tech Mentor (Ủng hộ)           |
[INFL]-+----------------------------------+----------------------------------+
   T   | [BYSTANDER]                      | [SUPPORTER]                      |
   H   | • Đại lý bảo hiểm (Trung lập)    | • Chuyên viên thẩm định (Ủng hộ) |
   Ấ   | • Đội ngũ CSKH (Trung lập)       | • Khách hàng nộp đơn (Ủng hộ)    |
   P   +----------------------------------+----------------------------------+
```

### 2. Bốn Stakeholder ưu tiên & Kế hoạch hành động

| Stakeholder | Nhóm & Stance | Mối quan tâm chính | Hành động cụ thể (Action + Deadline) |
|:---|:---:|:---|:---|
| **Head of Claims** | **Champion**<br>*(Ủng hộ mạnh)* | Giảm quá tải (+40% đơn), cắt thời gian duyệt, chống thất thoát. | **Trước 17h thứ Sáu (16/10)**: Gửi bản Demo 30 toa thuốc + biên bản so sánh thời gian (25p ➔ 1m48s). |
| **Compliance Officer** | **Blocker**<br>*(Chưa ủng hộ)* | Rò rỉ dữ liệu y tế PII, tuân thủ Nghị định 13/2023/NĐ-CP. | **Trước 10h thứ Ba (20/10)**: Gửi đề án Local Masking PII (Regex/NER on-premise) trước khi qua AI. |
| **Tech Mentor** | **Champion**<br>*(Ủng hộ)* | Kiến trúc Multi-modal RAG chống ảo giác, benchmark chuẩn hóa. | **Trước 20h thứ Năm (15/10)**: Họp 1-on-1 45p trình bày kiến trúc xử lý bảng biểu & review bộ evals. |
| **CIO / Core IT** | **Blocker**<br>*(Trung lập)* | Độ ổn định hệ thống Core Insurance, không gây quá tải API nội bộ. | **Trước 15h thứ Năm (22/10)**: Họp kỹ thuật cam kết tích hợp Loose Coupling (Async Webhook & S3). |

---

## Phase 2 — Pitch "Kết luận trước" & RACI Matrix (Trang 2 PDF)

### 1. Bản Pitch gửi Head of Claims
- **KẾT LUẬN / ĐỀ XUẤT**: Triển khai Pilot nội bộ 3 tuần trên 200 hồ sơ claim ngoại trú, tự động hóa 80% bóc tách, rút ngắn từ 25 phút còn < 3 phút/hồ sơ.
- **LÝ DO CHÍNH**: (1) Giải tỏa quá tải cuối năm (+40% claim); (2) Rút ngắn giải ngân về 24h tăng NPS; (3) Tự động đối soát chéo từng dòng viện phí triệt tiêu 100% lỗi tính toán.
- **BẰNG CHỨNG**: Benchmark 100 hồ sơ đạt **92.4% Exact Match**; Demo xử lý 5 trang chứng từ chỉ mất **1 phút 48 giây**; tỷ lệ bắt lệch hóa đơn đạt **100%**.
- **SMALL ASK**: Xin cử 02 chuyên viên thẩm định dự Demo 30 phút vào **15h thứ Năm (15/10)** và cấp 200 hồ sơ lịch sử ẩn danh để test mù.

### 2. Xử lý phản biện gay gắt
- **Phản biện**: *"Toa thuốc chữ khó đọc, AI ảo giác đọc sai tiền làm thất thoát bồi thường!"*
- **Giải pháp**: 
  1. *Human-in-the-Loop*: AI chỉ hỗ trợ trích xuất, quyền duyệt chi tiền 100% thuộc thẩm định viên.
  2. *Confidence Score & Bounding Box*: Độ tự tin < 88% tự động gắn cờ vàng kèm ảnh cắt lớp gốc đối soát trong 3s.
  3. *Deterministic Rule Engine*: Đối soát chéo tổng tiền từng dòng thuốc khớp 100% với hóa đơn đỏ.

### 3. RACI Matrix (6 Công việc trọng tâm)

| STT | Công việc quan trọng (1–2 tháng tới) | AI Builder (Kim Chi) | Tech Mentor | Head of Claims | Compliance |
|:---:|:---|:---:|:---:|:---:|:---:|
| 1 | Xác định Use case & Quy tắc nghiệp vụ thẩm định | **A** | C | **R** | I |
| 2 | Thu thập, làm sạch & Ẩn danh hóa dữ liệu PII y tế | **A / R** | C | I | **C** |
| 3 | Xây dựng Pipeline Multi-modal RAG & Tối ưu OCR | **A / R** | **C** | I | I |
| 4 | Kiểm thử chất lượng & Benchmark chống sai lệch | **A / R** | C | I | I |
| 5 | Triển khai thử nghiệm Pilot nội bộ trên 200 hồ sơ | **A / R** | I | **C** | I |
| 6 | Nghiệm thu kết quả Pilot & Quyết định Release | R | I | **A** | **C** |

*(Quy tắc bài lab: Mỗi công việc chỉ có đúng 1 Accountable duy nhất).*

---

## Phase 3 — Thiết kế AI Team & Priority Resourcing (Trang 3 PDF)

- **AI Team Architecture**: **Embedded AI Squad kết hợp Extended Network** (tập trung năng lực lõi vào 1 đầu mối kỹ thuật để duy trì *feedback loop < 12h*, kết hợp Partner & Outsource bên ngoài).
- **Phân định vai trò**:
  - *Core Role (Hiện tại)*: AI Product & Model Builder (Thân Thị Kim Chi phụ trách model, data, demo, điều phối).
  - *Extended Roles (Khi scale)*: Healthcare Domain Auditor (Bác sĩ cố vấn), Data Annotation Team, MLOps Specialist.
- **Priority Resourcing (Bổ sung năng lực)**:
  1. **Chuyên môn Y tế & Toa thuốc** ➔ **PARTNER** (Hợp tác cố vấn theo giờ với Bác sĩ để chuẩn hóa ruleset; hạn chót: *25/10/2026*).
  2. **Gán nhãn 2.000 mẫu hóa đơn** ➔ **OUTSOURCE** (Thuê đơn vị chuyên nghiệp có NDA, tiết kiệm 70% thời gian; hạn chót: *05/11/2026*).
  3. **MLOps & Continuous Evals** ➔ **HIRE** (Tuyển kỹ sư MLOps khi hệ thống scale sau đợt pilot; hạn chót: *Tháng 12/2026*).
- **Squad Goal**: *"Dự án SmartClaim AI sở hữu giải pháp xử lý chứng từ bảo hiểm tự động và chịu trách nhiệm đưa tỷ lệ trích xuất từ 92.4% lên > 95%, giảm thời gian xử lý từ 25 phút còn < 3 phút/hồ sơ trong 60 ngày tới."*


## Phase 4 — Team Health & Growth Plan 30 ngày (Trang 4 PDF)

### 1. Đánh giá Team Health (Thang điểm 1–5)
- **Chất lượng AI**: 3.5 / 5 | Model đạt 92.4% nhưng gặp khó khi hóa đơn mờ hoặc chữ ký đè chữ.
- **Tiến độ**: 3.5 / 5 | Khối lượng việc lớn, cần quản trị thời gian chặt chẽ.
- **Tinh thần team**: 4.5 / 5 | Tự chủ cao, quyết đoán, không ma sát nội bộ.
- **Tốc độ ra sản phẩm**: **2.5 / 5** *(Thấp nhất - Điểm nghẽn)* | Thiếu hệ thống đánh giá tự động (Automated Evals) khiến mỗi lần chỉnh prompt phải test tay mất nhiều giờ.

### 2. Nâng cấp năng lực (Competency Framework)
- **Đối tượng**: Thân Thị Kim Chi (AI Builder) | Hiện tại: **Gần L2 (AI Practitioner)**.
- **Năng lực cần nâng**: **AI Evaluation & Automated Benchmarking** (hướng tới L3 — AI Builder).
- **Hành động 30 ngày**: Xây dựng 50 Golden Test Cases y tế và tích hợp pipeline tự động test hồi quy mỗi commit.

### 3. Kế hoạch hành động 30 ngày (Growth Plan)

| STT | Vấn đề ưu tiên | Hành động cụ thể trong 30 ngày | Owner | Deadline | Dấu hiệu hoàn thành |
|:---:|:---|:---|:---:|:---:|:---|
| 1 | **Chất lượng AI & Evals** | Xây bộ 50 Golden Cases + script đo F1-score tự động. | Kim Chi | 28/10/2026 | Script `eval_pipeline.py` chạy < 5p; cảnh báo nếu accuracy < 90%. |
| 2 | **Tốc độ ra sản phẩm** | Dựng Staging Web Sandbox kéo-thả kiểm tra chứng từ 3s. | Kim Chi | 05/11/2026 | Web Sandbox online; thẩm định viên tự upload test được ngay. |
| 3 | **Tiến độ & Stakeholder** | Họp Weekly Review 30 phút vào chiều thứ Sáu hàng tuần. | Kim Chi | 16/10/2026 | 100% các tuần có Action Log gỡ khó dứt điểm cho Blocker. |

---

## Phase 5 — Thông tin bàn giao & Nộp bài

- **Repository**: `Track1_Day25_TeamA_SmartClaimAI`
- **File Báo cáo PDF**: [`Day25_AI-Team-Lab_TeamA.pdf`](Day25_AI-Team-Lab_TeamA.pdf) (Tối đa đúng 4 trang A4)
  - Trang 1: Stakeholder Map & 4 Chiến lược ưu tiên
  - Trang 2: Pitch "Kết luận trước", Xử lý phản biện & RACI Matrix
  - Trang 3: Thiết kế AI Team & Priority Resourcing (Hire/Outsource/Partner)
  - Trang 4: Team Health & Growth Plan 30 ngày
