# 3.3. Quy trình quản lý 2: Quản lý và mở rộng hạ tầng viễn thông (Cáp quang & Port)

## 3.3.1. Mô tả quy trình
- **Tác nhân tham gia (Actor):** Bộ phận Kế hoạch & Đầu tư, Quản lý kỹ thuật hạ tầng (INF), Đối tác thi công/Kỹ thuật viên, Ban Giám đốc[cite: 1, 3].
- **Khách hàng mục tiêu (Customer):** Khách hàng nội bộ (Bộ phận Kinh doanh - Sales, Bộ phận Kỹ thuật triển khai - TNC) và Khách hàng ngoại bộ (Người dùng Internet tại khu vực hết port)[cite: 3, 11].
- **Luồng các bước thực hiện (Workflow):** Hệ thống ghi nhận cảnh báo thiếu hụt Port/vượt ngưỡng lưu lượng -> Khảo sát năng lực hạ tầng khu vực -> Lập phương án đầu tư và dự toán chi phí -> Trình duyệt ngân sách lên Ban Giám đốc -> Triển khai thi công (kéo cáp, lắp tủ ODF mới) -> Nghiệm thu chất lượng và cập nhật số lượng Port mới lên hệ thống bản đồ GIS[cite: 1, 8].
- **Kịch bản thành công/thất bại:**
  - *Kết quả tích cực (Positive Outcome):* Hạ tầng cáp quang và Port được mở rộng đúng tiến độ; hệ thống GIS cập nhật chính xác số lượng Port khả dụng, giải quyết triệt để lỗi thiếu Port (ISS-01) cho Đội thi công[cite: 1, 3, 11].
  - *Kết quả tiêu cực (Negative Outcome):* Dự án bị từ chối do quá ngân sách; thi công chậm trễ do vướng giấy phép ngầm hóa/treo cáp điện lực; cập nhật sai lệch dữ liệu Port lên GIS gây lỗi điều phối[cite: 1, 11].

## 3.3.2. Mô hình hóa quy trình hiện tại (Sơ đồ BPMN - As-is)
*(Ghi chú cho nhóm: Chèn hình ảnh sơ đồ BPMN chi tiết tại đây. Nhớ thiết kế >7 Gateways, ví dụ: Gateway duyệt ngân sách, Gateway kiểm tra giấy phép thi công, Gateway kết quả nghiệm thu)*[cite: 3, 12].

## 3.3.3. Phân tích định tính
### 3.3.3.1. Phân tích giá trị gia tăng (VA, BVA, NVA)
- **Value-Adding (VA):** Thi công kéo cáp quang dã chiến/ngầm, Lắp đặt và hàn nối hộp ODF[cite: 3].
- **Business Value-Adding (BVA):** Khảo sát hiện trạng, Lập dự toán vật tư, Trình duyệt hồ sơ, Nghiệm thu hạ tầng[cite: 3].
- **Non-Value Adding (NVA):** Thời gian chờ đợi phê duyệt nhiều cấp, Thời gian chờ giấy phép thi công từ cơ quan nhà nước, Di chuyển qua lại giữa kho và hiện trường để bù vật tư thiếu[cite: 3].

### 3.3.3.2. Phân tích lãng phí (Lean 7 Wastes)
- **Thời gian chờ/Hold:** NVA lớn nhất nằm ở độ trễ từ lúc nhận ticket báo hết Port đến lúc có quyết định duyệt ngân sách đầu tư[cite: 3, 4].
- **Sự vận chuyển (Transportation):** Chuyển vật tư (cáp, bộ chia, tủ ODF) từ kho trung tâm đến các tuyến đường thi công xa[cite: 3].
- **Làm lỗi/Làm lại (Defects/Rework):** Khảo sát sai lệch vị trí dẫn đến thiết kế dự toán sai, thi công không đạt chuẩn suy hao quang phải hàn lại[cite: 3, 4].

### 3.3.3.3. Phân tích các bên liên quan (Stakeholder Analysis) và Sổ đăng ký vấn đề (Issue Register)
- **Sổ đăng ký vấn đề (Issue Register):**
  - *ISS-01:* Độ trễ cập nhật dữ liệu Port khả dụng lên GIS sau khi thi công xong (Nguyên nhân gốc rễ gây ra khảo sát ảo ở quy trình Core)[cite: 3, 4].
  - *ISS-02:* Hao hụt vật tư cáp dã chiến trong quá trình kéo cáp không sát với dự toán[cite: 4, 8].
  - *ISS-03:* Khó khăn trong việc xin phép hạ tầng cột điện của điện lực địa phương[cite: 8].

## 3.3.4. Phân tích định lượng
### 3.3.4.1. Định lượng Thời gian (Cycle time, Wait time)
- Phân tích và đo lường khoảng biến thiên thời gian thực hiện (Process Time) của tác vụ thi công và Thời gian chờ (Wait Time) khi duyệt hồ sơ. Tính tổng thời gian chu kỳ (Cycle Time) hoàn thành 1 dự án mở rộng trạm/port[cite: 3, 4].
### 3.3.4.2. Định lượng Chi phí
- Ước tính các thành phần chi phí: Chi phí vật tư cố định (Cáp, tủ ODF, Splitter), Chi phí nhân công (công thợ kéo cáp/hàn nối quang), và Tổn thất cơ hội/doanh thu (chi phí mất khách hàng do không có mạng/port để lắp đặt)[cite: 3, 4].
