# Chương 2. HỆ THỐNG QUY TRÌNH NGHIỆP VỤ FPT TELECOM

> 📂 **File nguồn DrawIO:** [kien_truc.drawio](kien_truc.drawio) — 12 trang, mở bằng DrawIO Desktop hoặc <https://app.diagrams.net>
>
> 🖼️ **File ảnh PNG:** đặt trong thư mục [images/kien_truc/](images/kien_truc/) — 12 file PNG tương ứng 12 sơ đồ.

---

## 2.1. Kiến trúc quy trình nghiệp vụ của FPT Telecom

Để đảm bảo hoạt động hiệu quả trong việc cung cấp dịch vụ viễn thông và Internet đến khách hàng, FPT Telecom xây dựng hệ thống quy trình nghiệp vụ chặt chẽ, bao gồm các hoạt động từ tiếp nhận nhu cầu, vận hành kỹ thuật đến chăm sóc sau bán hàng. Mô hình quản lý này giúp công ty tối ưu hóa trải nghiệm khách hàng, duy trì lợi thế cạnh tranh và phát triển bền vững. Các quy trình của FPT Telecom được phân thành ba nhóm chính: **Quản lý (Management)**, **Cốt lõi (Core)** và **Hỗ trợ (Support)**.

**Nhóm quy trình quản lý** là nhóm quy trình tập trung vào việc định hướng phát triển dài hạn, đảm bảo công ty có chiến lược kinh doanh và quản trị hiệu quả:

- **Quy trình hoạch định chiến lược kinh doanh:** Xây dựng kế hoạch phát triển thị trường, sản phẩm và chiến lược cạnh tranh.
- **Quy trình quản lý và mở rộng hạ tầng:** Quản lý hệ thống cáp quang, các cổng kết nối (Port) và mở rộng vùng phủ.
- **Quy trình đo lường chất lượng dịch vụ (NPS/KPI):** Khảo sát mức độ hài lòng khách hàng sau lắp đặt, đánh giá hiệu suất nhân viên Sales và Kỹ thuật viên.

**Nhóm quy trình cốt lõi** là nhóm quy trình quan trọng nhất, liên quan trực tiếp đến hoạt động cung cấp dịch vụ lắp đặt Internet cho khách hàng:

- **Quy trình tiếp nhận yêu cầu:** Khách hàng đăng ký qua Website, Hotline, Cửa hàng hoặc Nhân viên kinh doanh; Sales ghi nhận thông tin.
- **Quy trình tư vấn và ký hợp đồng:** Tư vấn gói cước, thu thập giấy tờ, ký hợp đồng điện tử hoặc giấy.
- **Quy trình khảo sát hạ tầng:** Kỹ thuật kiểm tra cáp quang, cổng kết nối (Port) để quyết định triển khai.
- **Quy trình tạo và phân bổ Work Order:** Hệ thống BPMS/CRM tự động tạo đơn lắp đặt, phân công đội kỹ thuật khu vực.
- **Quy trình thi công lắp đặt:** Kéo cáp quang, hàn nối, lắp Modem, cấu hình Wi-Fi và nghiệm thu.
- **Quy trình kích hoạt và chăm sóc sau bán hàng:** Kích hoạt tài khoản Internet, gửi SMS/Email xác nhận, khảo sát hài lòng.

**Nhóm quy trình hỗ trợ** giúp đảm bảo vận hành trơn tru, hỗ trợ các quy trình cốt lõi hoạt động hiệu quả:

- **Quy trình quản lý kho và vật tư:** Xuất nhập Modem/ONT, Router, dây cáp quang và phụ kiện lắp đặt.
- **Quy trình tài chính - kế toán:** Xử lý cước hòa mạng, phí lắp đặt, quản lý dòng tiền và doanh thu.
- **Quy trình Công nghệ Thông tin (CRM/BPMS):** Vận hành hệ thống quản trị quy trình, tự động hóa tạo đơn, kích hoạt dịch vụ.

---

## 2.2. Sơ đồ kiến trúc tổng quan

_Hình 2.1. Kiến trúc nghiệp vụ FPT Telecom — phân nhóm Quản lý / Cốt lõi / Hỗ trợ_

![Kiến trúc tổng quan](/assets/diagrams/kien_truc/kien-truc-tong-quan.png)

---

## 2.3. Quy trình quản lý (Management Process)

### 2.3.1. Quy trình hoạch định chiến lược kinh doanh

![Quy trình hoạch định chiến lược kinh doanh](/assets/diagrams/kien_truc/management/hoach-dinh-chien-luoc.png)

**Mô tả luồng:**

1. Phân tích thị trường để xác định cơ hội và thách thức.
2. Xây dựng kế hoạch kinh doanh dựa trên phân tích.
3. Hội đồng quản trị xem xét và phê duyệt. Nếu chưa duyệt → điều chỉnh và quay lại bước 2.
4. Triển khai chiến lược đã được phê duyệt.
5. Theo dõi và đánh giá hiệu quả triển khai.

### 2.3.2. Quy trình quản lý và mở rộng hạ tầng

![Quy trình quản lý và mở rộng hạ tầng](/assets/diagrams/kien_truc/management/quan-ly-va-mo-rong-ha-tang.png)

**Mô tả luồng:**

1. Khảo sát nhu cầu sử dụng dịch vụ theo vùng.
2. Đánh giá tình trạng cáp quang và Port hiện có.
3. Nếu không cần mở rộng → duy trì hiện trạng.
4. Nếu cần mở rộng → lập dự án đầu tư → triển khai thi công → nghiệm thu hạ tầng.

### 2.3.3. Quy trình đo lường chất lượng dịch vụ (NPS/KPI)

![Quy trình đo lường chất lượng dịch vụ](/assets/diagrams/kien_truc/management/do-luong-chat-luong-dich-vu.png)

**Mô tả luồng:**

1. Sau khi khách hàng hoàn tất lắp đặt, tổng đài gọi điện khảo sát.
2. Thu thập điểm NPS (Net Promoter Score).
3. Nếu không đạt ngưỡng → phân tích nguyên nhân → điều chỉnh quy trình.
4. Nếu đạt ngưỡng → tổng hợp báo cáo KPI.

---

## 2.4. Quy trình cốt lõi (Core Process)

### 2.4.1. Quy trình tiếp nhận yêu cầu

![Quy trình tiếp nhận yêu cầu](/assets/diagrams/kien_truc/core/tiep-nhan-yeu-cau.png)

**Mô tả luồng:**

1. Khách hàng có nhu cầu đăng ký dịch vụ Internet.
2. Khách hàng chọn 1 trong 4 kênh đăng ký: Website, Hotline, Cửa hàng FPT, hoặc Nhân viên Sales.
3. Nhân viên kinh doanh (Sales) liên hệ khách hàng để xác nhận thông tin.
4. Sales chuyển hồ sơ sang bước khảo sát hạ tầng.

### 2.4.2. Quy trình khảo sát hạ tầng

![Quy trình khảo sát hạ tầng](/assets/diagrams/kien_truc/core/khao-sat-ha-tang.png)

**Mô tả luồng:**

1. Kỹ thuật viên tiếp nhận yêu cầu từ hệ thống BPMS/CRM.
2. Kiểm tra tình trạng hạ tầng cáp quang tại khu vực lắp đặt.
3. Kiểm tra số lượng cổng kết nối (Port) còn khả dụng.
4. Nếu không đủ điều kiện → thông báo cho khách hàng và kết thúc.
5. Nếu đủ điều kiện → tư vấn gói cước và ký hợp đồng.

### 2.4.3. Quy trình tạo và phân bổ Work Order

![Quy trình tạo và phân bổ Work Order](/assets/diagrams/kien_truc/core/work-order.png)

**Mô tả luồng:**

1. Hợp đồng được khách hàng ký kết (điện tử hoặc giấy).
2. Hệ thống BPMS/CRM tiếp nhận dữ liệu hợp đồng.
3. Hệ thống tự động sinh Work Order (đơn lắp đặt).
4. Phân công Work Order cho đội kỹ thuật phụ trách khu vực.
5. Kho vật tư chuẩn bị thiết bị (Modem, cáp quang, phụ kiện).

### 2.4.4. Quy trình thi công lắp đặt

![Quy trình thi công lắp đặt](/assets/diagrams/kien_truc/core/thi-cong.png)

**Mô tả luồng:**

1. Kỹ thuật viên liên hệ khách hàng để xác nhận lịch lắp đặt.
2. Kỹ thuật viên di chuyển đến địa điểm lắp đặt.
3. Kéo cáp quang từ hộp phối đến vị trí lắp đặt.
4. Hàn nối cáp quang với Modem/ONT.
5. Lắp đặt Modem/ONT tại vị trí khách hàng.
6. Cấu hình Wi-Fi và kiểm tra tín hiệu Internet.
7. Nếu nghiệm thu chưa đạt → khắc phục sự cố rồi kiểm tra lại.
8. Nếu nghiệm thu đạt → thu phí lắp đặt (nếu chưa thanh toán) và khách hàng ký xác nhận hoàn tất.

### 2.4.5. Quy trình kích hoạt và hậu mãi

![Quy trình kích hoạt và hậu mãi](/assets/diagrams/kien_truc/core/kich-hoat-va-hau-mai.png)

**Mô tả luồng:**

1. Kỹ thuật viên cập nhật trạng thái Work Order trên hệ thống.
2. Hệ thống BPMS/CRM tự động kích hoạt tài khoản Internet cho khách hàng.
3. Hệ thống gửi SMS/Email xác nhận dịch vụ cho khách hàng.
4. Khách hàng xác nhận và bắt đầu sử dụng dịch vụ.
5. Tổng đài gọi điện khảo sát mức độ hài lòng (NPS).
6. Hỗ trợ kỹ thuật khi khách hàng có yêu cầu phát sinh.

---

## 2.5. Quy trình hỗ trợ (Support Process)

### 2.5.1. Quy trình quản lý kho và vật tư

![Quy trình quản lý kho và vật tư](/assets/diagrams/kien_truc/support/kho-va-vat-tu.png)

**Mô tả luồng:**

1. Kho thực hiện kiểm kê định kỳ.
2. Nếu tồn kho không đủ → đặt hàng nhà cung cấp (NCC) → nhập kho thiết bị mới.
3. Kho tiếp nhận yêu cầu xuất thiết bị từ đội kỹ thuật.
4. Xuất Modem, Router, cáp quang, phụ kiện theo yêu cầu.
5. Bàn giao thiết bị cho đội kỹ thuật để triển khai lắp đặt.

### 2.5.2. Quy trình tài chính - kế toán

![Quy trình tài chính - kế toán](/assets/diagrams/kien_truc/support/tai-chinh-ke-toan.png)

**Mô tả luồng:**

1. Bộ phận kế toán tiếp nhận thông tin hợp đồng từ hệ thống CRM.
2. Xuất hóa đơn phí lắp đặt ban đầu cho khách hàng.
3. Theo dõi thu phí lắp đặt.
4. Theo dõi thanh toán cước hàng tháng của khách hàng.
5. Nếu khách hàng thanh toán quá hạn → nhắc nợ và xử lý theo quy trình.
6. Cuối kỳ, tổng hợp báo cáo doanh thu cho Ban lãnh đạo.

### 2.5.3. Quy trình Công nghệ Thông tin (CRM/BPMS)

![Quy trình Công nghệ Thông tin](/assets/diagrams/kien_truc/support/cong-nghe-thong-tin.png)

**Mô tả luồng:**

1. Vận hành và bảo trì hệ thống CRM (Quản lý quan hệ khách hàng).
2. Vận hành và bảo trì hệ thống BPMS (Quản lý quy trình nghiệp vụ).
3. Tự động hóa việc tạo Work Order khi có hợp đồng mới.
4. Tự động kích hoạt dịch vụ khi Work Order hoàn tất.
5. Xử lý sự cố kỹ thuật CNTT khi phát sinh.
6. Sao lưu dữ liệu định kỳ và đảm bảo an toàn bảo mật.
