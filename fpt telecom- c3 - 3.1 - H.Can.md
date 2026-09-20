## 3.1. Phương pháp thực hiện

Để xây dựng mô hình và phân tích hệ thống quy trình nghiệp vụ tại FPT Telecom một cách khách quan và chính xác, nhóm đã áp dụng kết hợp các phương pháp thu thập dữ liệu, tiêu chuẩn mô hình hóa và công cụ phần mềm chuyên dụng như sau:

### 3.1.1. Phương pháp thu thập dữ liệu (Process Discovery Methods)

Quá trình khám phá quy trình được thực hiện thông qua 3 phương pháp chính theo đúng vòng đời quản trị quy trình (BPM Lifecycle)[cite: 10]:

**Phương pháp dựa trên tài liệu/bằng chứng (Evidence/Document-based Discovery):**
Nhóm tiến hành thu thập và phân tích các tài liệu nội bộ, quy trình hướng dẫn lắp đặt chuẩn (SOP), cùng các biểu mẫu hợp đồng điện tử hiện hành và dữ liệu log từ hệ thống của FPT Telecom[cite: 1, 7, 10]. Phương pháp này giúp thiết lập khung quy trình chuẩn mực và phản ánh chính xác quy trình As-is mà không bị ảnh hưởng bởi nhận định cảm tính[cite: 17].

**Phương pháp phỏng vấn (Interview-based Discovery):**
Nhóm đã trao đổi và phỏng vấn trực tiếp nhân viên Kinh doanh (Sales) và Kỹ thuật viên (TNC) đang làm việc tại FPT[cite: 1, 5]. Phương pháp này giúp đối chiếu tài liệu với thực tế triển khai, từ đó hiểu rõ luồng công việc thực, nhận diện các "điểm nghẽn" và cách xử lý các tình huống ngoại lệ (ví dụ: khảo sát thấy hết cổng kết nối Port hoặc đứt cáp)[cite: 1, 5].

**Phương pháp quan sát (Observation):**
Thành viên trong nhóm trực tiếp đóng vai khách hàng và quan sát thực tế một ca triển khai lắp đặt mạng – trải dài từ giai đoạn tổng đài tiếp nhận yêu cầu cho đến khi khách hàng ký nghiệm thu hoàn tất[cite: 1, 5].

### 3.1.2. Phương pháp và Tiêu chuẩn mô hình hóa

Nhóm sử dụng ngôn ngữ mô hình hóa trực quan tiêu chuẩn mở BPMN 2.0 (Business Process Model and Notation) để vẽ lại sơ đồ quy trình hiện tại (Sơ đồ As-Is)[cite: 1, 5, 14].

Trong quá trình vẽ, nhóm áp dụng chặt chẽ các khía cạnh góc nhìn cốt lõi của BPMN nhằm tránh các lỗi ngữ nghĩa và logic hệ thống, bao gồm[cite: 5, 6]:

**Góc nhìn Tổ chức (Who):**
Sử dụng các Pools và Lanes để phân định rõ vai trò, trách nhiệm của từng chủ thể tham gia (Khách hàng, Nhân viên Sales, Kỹ thuật viên, Hệ thống BPMS)[cite: 1, 3, 5].

**Góc nhìn Chức năng (What):**
Sử dụng các Tasks/Activities để mô tả cụ thể từng hành động nghiệp vụ (tư vấn, kéo cáp, cấu hình thiết bị, ký hợp đồng)[cite: 1, 3, 5].

**Góc nhìn Luồng kiểm soát (When):**
Sử dụng các Cổng rẽ nhánh (Gateways) để xử lý các điều kiện kiểm tra hạ tầng và luồng công việc ngoại lệ[cite: 1, 3, 5].

### 3.1.3. Công cụ hỗ trợ (Tools)

**Công cụ thiết kế:**
Nhóm sử dụng phần mềm Camunda Modeler để thiết kế và số hóa các sơ đồ luồng quy trình chính và luồng ngoại lệ một cách chuyên nghiệp[cite: 1, 6].

**Công cụ quản lý:**
Nhóm sử dụng nền tảng GitHub để lưu trữ phiên bản các tệp định dạng .bpmn, .png và quản lý tiến độ làm việc chung của toàn dự án[cite: 1, 5].
