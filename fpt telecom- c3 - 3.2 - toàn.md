### 3.2.6. Mô hình hóa quy trình tương lai (Sơ đồ BPMN - To-Be)

#### 3.2.6.1. Mục tiêu của mô hình To-Be
Mô hình To-Be được xây dựng trên cơ sở giảm các điểm lãng phí đã nhận diện ở As-is, tăng mức độ tự động hóa và liên thông dữ liệu giữa khách hàng, Sales, CRM/BPMS, kho và kỹ thuật viên.

Các nguyên tắc chính:
* Tự động kiểm tra hạ tầng và port thông qua API khi có dữ liệu hệ thống.
* Ký hợp đồng điện tử và thanh toán trực tuyến trong cùng một luồng.
* Tự động tạo Work Order sau khi đơn đủ điều kiện.
* Đẩy lịch, tọa độ, thông tin khách hàng và vật tư cho kỹ thuật viên qua App Mobile.
* Tối ưu lộ trình kỹ thuật viên bằng Routing.
* Quản lý vật tư bằng QR/Barcode.
* Nghiệm thu điện tử trên Mobile App.
* Tự động kích hoạt dịch vụ sau khi nghiệm thu đạt.
* Tự động khảo sát CSAT sau bán hàng.

#### 3.2.6.2. Sơ đồ BPMN To-Be
> **Hình 3.3. Sơ đồ BPMN To-Be của quy trình thi công và lắp đặt mạng Wi-Fi**

```mermaid
flowchart LR

  subgraph KH["KHÁCH HÀNG"]
    A((Bắt đầu))
    B["Đăng ký dịch vụ\nWebsite / App / Hotline"]
    C["Cung cấp thông tin & vị trí"]
    D["Ký hợp đồng điện tử"]
    E["Thanh toán trực tuyến\n(nếu có)"]
    F["Xác nhận lịch lắp đặt"]
    G["Nghiệm thu điện tử"]
    H["Nhận thông báo kích hoạt"]
    I["Sử dụng dịch vụ"]
    J((Kết thúc))
    A --> B --> C
  end

  subgraph SALES["SALES"]
    S1["Tiếp nhận / tư vấn\ntrên CRM"]
    S2["Xác nhận gói cước\nvà thông tin đơn"]
  end

  subgraph TECH["KỸ THUẬT KHẢO SÁT"]
    T1["API tự động kiểm tra\nhạ tầng + port"]
    X1{"Đủ điều kiện?"}
    T2["Thông báo không thể lắp đặt\n& đề xuất phương án khác"]
  end

  subgraph CRM["CRM / BPMS"]
    R1["Tự động tạo Work Order"]
    R2["Phân công kỹ thuật viên\n+ lịch + tọa độ"]
    R3["Đồng bộ App Mobile"]
    R4["Nhận kết quả thi công\n& nghiệm thu"]
    X4{"Thi công đạt?"}
    R5["Tự động kích hoạt dịch vụ"]
    R6["Tự động gửi SMS/Email/App"]
  end

  subgraph WH["KHO & VẬT TƯ"]
    W1["Quét QR/Barcode\nxác nhận vật tư"]
    W2["Đóng gói & bàn giao\ntheo Work Order"]
  end

  subgraph TNC["KỸ THUẬT VIÊN LẮP ĐẶT"]
    N1["Nhận Work Order trên App"]
    N2["Tối ưu lộ trình Routing"]
    N3["Liên hệ / xác nhận lịch"]
    N4["Đến hiện trường"]
    N5["Kéo cáp + hàn nối"]
    N6["Lắp modem/ONT + Router"]
    N7["Cấu hình Wi-Fi + đo tín hiệu"]
    N8["Checklist điện tử\n+ ảnh hiện trường"]
    N9["Gửi kết quả lên App"]
  end

  subgraph ACCOUNT["KẾ TOÁN"]
    K1["Đối soát thanh toán tự động"]
    K2["Xuất hóa đơn điện tử"]
  end

  subgraph CSKH["CSKH / TỔNG ĐÀI"]
    C1["Khảo sát CSAT tự động"]
    C2["Chatbot / Ticket hỗ trợ\nkhi cần"]
  end

  C --> S1 --> S2 --> T1 --> X1
  X1 -- "Không" --> T2 --> J
  X1 -- "Có" --> D --> E --> K1 --> R1
  R1 --> R2 --> R3 --> W1 --> W2 --> N1
  N1 --> N2 --> N3 --> F --> N4 --> N5 --> N6 --> N7 --> N8 --> N9 --> R4 --> X4
  X4 -- "Không" --> N7
  X4 -- "Có" --> G --> R5 --> R6 --> H --> I --> C1 --> C2 --> J
  K1 --> K2
### 3.2.6.3. So sánh luồng As-is và To-Be

| Nội dung | As-is | To-Be đề xuất |
| :--- | :--- | :--- |
| **Kiểm tra hạ tầng/port** | Kiểm tra thủ công/qua nhân sự kỹ thuật | API tự động kiểm tra từ CRM |
| **Nhập thông tin** | Có khả năng nhập lặp | Một nguồn dữ liệu dùng chung |
| **Hợp đồng** | Điện tử hoặc giấy | Ưu tiên e-Contract |
| **Thanh toán** | Có thể phát sinh xử lý riêng | Tích hợp Payment Gateway |
| **Tạo Work Order** | CRM/BPMS tạo và phân công | Tự động tạo và phân công |
| **Lịch hẹn** | Gọi/xác nhận thủ công | Xác nhận qua App/SMS |
| **Vật tư** | Chuẩn bị/xuất kho thủ công | QR/Barcode + Work Order |
| **Điều phối kỹ thuật** | Phân công theo lịch | Routing tối ưu |
| **Liên hệ khách hàng** | Kỹ thuật viên gọi thủ công | Thông báo và App |
| **Thi công** | Ghi nhận thủ công | Mobile App + checklist + ảnh |
| **Nghiệm thu** | Giấy/tờ hoặc biên bản | Nghiệm thu điện tử |
| **Kích hoạt** | Cập nhật trạng thái rồi kích hoạt | Tự động kích hoạt |
| **CSKH** | Gọi khảo sát | CSAT tự động + Chatbot/Ticket |

---

### 3.2.7. Đề xuất giải pháp cải tiến quy trình (Improvement Solutions)

#### 3.2.7.1. Ma trận giải pháp theo Issue Register

| Mã vấn đề | Vấn đề | Giải pháp cải tiến | Công nghệ/Phương pháp | Lợi ích kỳ vọng |
| :--- | :--- | :--- | :--- | :--- |
| **IR-01** | Không đủ hạ tầng/port | Tự động kiểm tra hạ tầng và port trước khi chốt đơn | API Hạ tầng – CRM/BPMS | Giảm đơn lỗi, giảm thời gian khảo sát |
| **IR-02** | Chờ xác nhận lịch | Cho khách hàng chọn/đổi lịch trực tuyến; tự động nhắc lịch | Web/App, SMS, Mobile App | Giảm thời gian chờ, tăng tỷ lệ đúng hẹn |
| **IR-03** | Thiếu vật tư | Liên kết Work Order với kho; quét QR/Barcode khi xuất vật tư | WMS + QR/Barcode | Giảm thiếu vật tư và chuyến đi bổ sung |
| **IR-04** | Sai/thừa thông tin | Dùng một nguồn dữ liệu khách hàng, tự động đồng bộ giữa Sales–CRM–Kỹ thuật | CRM/BPMS, Integration Platform | Giảm nhập liệu lặp và Human Error |
| **IR-05** | Thi công không đạt | Checklist kỹ thuật số, ảnh hiện trường và kiểm tra tín hiệu bắt buộc | Mobile App, Digital Checklist | Giảm Rework, tăng chất lượng |
| **IR-06** | Khách hàng không nghiệm thu | Nghiệm thu điện tử và xác nhận trên App | Mobile App, E-Signature | Giảm tranh chấp, tăng tốc đóng đơn |
| **IR-07** | Chậm kích hoạt | Tự động kích hoạt khi CRM nhận trạng thái nghiệm thu đạt | BPMS Automation | Rút ngắn thời gian từ nghiệm thu đến sử dụng |
| **IR-08** | Phản hồi sau lắp đặt | Gửi CSAT tự động, phân loại phản hồi và tạo ticket | Chatbot, AI, QoE Monitoring | Tăng tốc xử lý phản hồi |
| **IR-09** | Vướng mắc phí/thanh toán | Tích hợp Payment Gateway ngay sau e-Contract; đối soát tự động | Payment Gateway, E-Invoice | Giảm chờ thanh toán và tải cho Kế toán |

#### 3.2.7.2. Ưu tiên giải pháp

**Ưu tiên 1 – Tác động cao**
* API kiểm tra hạ tầng/port.
* Tự động tạo và phân công Work Order.
* Mobile App cho kỹ thuật viên.
* Tích hợp thanh toán trực tuyến.
* Nghiệm thu điện tử.

**Ưu tiên 2 – Tối ưu vận hành**
* QR/Barcode quản lý vật tư.
* Routing tối ưu.
* Dashboard KPI.
* Tự động khảo sát CSAT.

**Ưu tiên 3 – Nâng cao**
* Chatbot/AI hỗ trợ.
* Phân tích dự báo nhu cầu vật tư.
* Phân tích chất lượng mạng sau lắp đặt.
* Tối ưu điều phối theo dữ liệu lịch sử.

---

### 3.2.8. Kế hoạch chuyển đổi & Lộ trình thực thi (Implementation Plan)

#### 3.2.8.1. Mục tiêu chuyển đổi
Mục tiêu là chuyển từ quy trình As-is phụ thuộc nhiều vào thao tác thủ công và thời gian chờ sang To-Be có mức độ tự động hóa, tích hợp dữ liệu và điều phối theo thời gian thực cao hơn.

#### 3.2.8.2. Roadmap triển khai

| Giai đoạn | Thời gian tham chiếu | Mục tiêu | Nhiệm vụ chính | Kết quả/KPI |
| :--- | :--- | :--- | :--- | :--- |
| **GĐ 0 – Khảo sát & chuẩn hóa** | Tuần 0–2 | Chuẩn hóa dữ liệu và baseline | Xác nhận SOP, dữ liệu khách hàng, API hạ tầng, KPI baseline | Baseline KPI được phê duyệt |
| **GĐ 1 – Tự động hóa lõi** | Tuần 3–6 | Giảm thao tác thủ công | API port, e-Contract, Payment Gateway, auto Work Order | 100% đơn đủ điều kiện được tạo WO tự động |
| **GĐ 2 – Số hóa hiện trường** | Tuần 7–12 | Giảm Wait/Transportation/Rework | Mobile App, GPS, Routing, QR/Barcode, checklist | Wait Time giảm ≥ 50% |
| **GĐ 3 – Tự động hóa đầu cuối** | Từ tuần 13 | Tối ưu toàn bộ vòng đời | Auto activation, e-Invoice, CSAT tự động, Dashboard | Lead Time ≤ 360 phút, On-time ≥ 95% |
| **GĐ 4 – Tối ưu liên tục** | Sau triển khai | Cải tiến theo dữ liệu | KPI review, AI/Chatbot, predictive analytics | Cải tiến định kỳ |

#### 3.2.8.3. Kế hoạch hành động
1. Khảo sát As-is và xác nhận baseline trong 1–2 tuần.
2. Chuẩn hóa dữ liệu CRM/BPMS và thiết kế API hạ tầng trong 1–2 tuần.
3. Triển khai e-Contract + Payment Gateway + tự động tạo Work Order trong 2–3 tuần.
4. Phát triển Mobile App cho kỹ thuật viên trong 2–3 tuần.
5. Tích hợp WMS/QR/Barcode và Routing trong 2–3 tuần.
6. Triển khai nghiệm thu điện tử và Auto Activation trong 1–2 tuần.
7. Thiết lập Dashboard KPI và CSAT tự động trong 1–2 tuần.
8. Đào tạo Sales, Kỹ thuật, Kho, CSKH và Kế toán trước khi pilot.
9. Pilot tại một khu vực, đo KPI trước và sau.
10. Mở rộng triển khai sau khi kết quả pilot đạt KPI mục tiêu.

#### 3.2.8.4. Quản trị thay đổi

| Nhóm | Nội dung cần đào tạo | Hình thức |
| :--- | :--- | :--- |
| **Sales** | e-Contract, CRM, quản lý đơn | Đào tạo + SOP |
| **Kỹ thuật khảo sát** | API hạ tầng, xử lý ngoại lệ | Workshop |
| **Kỹ thuật viên** | Mobile App, GPS, Routing, checklist | Thực hành |
| **Kho & Vật tư** | QR/Barcode, WMS | Thực hành |
| **CSKH** | CSAT, Chatbot/Ticket | Đào tạo hệ thống |
| **Kế toán** | Payment Gateway, đối soát, e-Invoice | Đào tạo hệ thống |

#### 3.2.8.5. Rủi ro triển khai và biện pháp giảm thiểu

| Rủi ro | Tác động | Biện pháp |
| :--- | :--- | :--- |
| API hạ tầng không ổn định | Chậm kiểm tra điều kiện | Fallback sang kiểm tra thủ công |
| Nhân viên chưa quen hệ thống | Giảm năng suất giai đoạn đầu | Đào tạo + pilot + hỗ trợ tại chỗ |
| Dữ liệu CRM không đồng nhất | Lỗi Work Order | Chuẩn hóa master data |
| Người dùng không sử dụng App đầy đủ | Mất dữ liệu hiện trường | KPI sử dụng App + kiểm tra bắt buộc |
| Thanh toán lỗi | Đơn bị treo | Retry + đối soát + fallback |
| Routing chưa phù hợp thực tế | Tăng thời gian di chuyển | Pilot và hiệu chỉnh thuật toán |

---

### 3.2.9. Đánh giá tác động của chuyển đổi

#### 3.2.9.1. Tác động đến thời gian
Theo bộ số liệu tham chiếu, việc tự động hóa các điểm chờ có thể đưa Lead Time từ 620 phút xuống mục tiêu 360 phút, tương đương mức giảm khoảng 41,9%.

#### 3.2.9.2. Tác động đến chi phí
Chi phí tham chiếu cho một đơn giảm từ khoảng 1.592.300 VNĐ xuống 1.350.000 VNĐ, tương đương giảm khoảng 15,2%.
Phần tiết kiệm chủ yếu đến từ:
* Giảm thời gian chờ và nhân công điều phối.
* Giảm quãng đường di chuyển nhờ Routing.
* Giảm chuyến đi bổ sung vật tư.
* Giảm chi phí rework.
* Giảm thao tác nhập liệu thủ công.

#### 3.2.9.3. Tác động đến chất lượng dịch vụ
To-Be đặt mục tiêu:
* Rework Rate giảm từ 12% xuống 4%.
* On-time Rate tăng từ 78% lên 96%.
* CSAT tăng từ 88% lên 95%.

*Đây là mục tiêu tham chiếu cần được kiểm chứng bằng dữ liệu pilot.*

---

### 3.2.10. Kết luận sau cải tiến
Quy trình To-Be giữ lại các checkpoint nghiệp vụ cần thiết của As-is nhưng chuyển cách thức thực hiện theo hướng số hóa, tự động hóa và tích hợp dữ liệu.

Trọng tâm cải tiến là giảm thời gian chờ, giảm di chuyển không tạo giá trị, hạn chế nhập liệu lặp và giảm Rework. Các giải pháp trọng tâm gồm:
* Tự động kiểm tra hạ tầng/port bằng API.
* Tự động tạo và phân công Work Order.
* Điều phối kỹ thuật viên qua Mobile App và Routing.
* Quản lý vật tư bằng QR/Barcode.
* Thanh toán trực tuyến.
* Nghiệm thu điện tử.
* Tự động kích hoạt dịch vụ.
* CSAT và hỗ trợ sau bán hàng tự động.

Theo bộ số liệu giả định tham chiếu, Lead Time có thể giảm 41,9%, Wait Time giảm 69,0% và Cost/Order giảm khoảng 15,2%.
Các kết quả này là mục tiêu thiết kế/ước tính, không phải số liệu nội bộ đã được xác minh của FPT Telecom. Nhóm cần thay thế bằng dữ liệu khảo sát hoặc dữ liệu vận hành thực tế nếu có.

---

### Nguồn và phạm vi dữ liệu
* `fpt_telecom_3_2_toan_review.md`: nguồn chính cho cấu trúc quy trình, actor, 11 bước, Gateway và Issue Register.
* `Tổng Quan Quy trình lắp đặt mạng Wi-Fi của FPT Telecom`: nguồn đối chiếu cho vai trò bộ phận, các checkpoint và hoạt động CRM/BPMS.
* Các số liệu thời gian, chi phí và KPI mục tiêu trong mục 3.2.4 và 3.2.7 là giả định tham chiếu phục vụ phân tích, không được trình bày như dữ liệu nội bộ đã xác minh của FPT Telecom.