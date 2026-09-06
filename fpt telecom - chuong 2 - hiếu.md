# CHƯƠNG 2: HỆ THỐNG QUY TRÌNH NGHIỆP VỤ FPT TELECOM

---

## 2.1. Kiến trúc quy trình nghiệp vụ của FPT Telecom

Để đảm bảo hoạt động hiệu quả trong việc cung cấp dịch vụ viễn thông và Internet chất lượng cao đến khách hàng, **FPT Telecom** xây dựng một hệ thống quy trình nghiệp vụ chặt chẽ, xuyên suốt từ định hướng chiến lược, vận hành cốt lõi đến các hoạt động hỗ trợ. Mô hình quản trị này giúp công ty:

- **Tối ưu hóa trải nghiệm khách hàng** ở mọi điểm chạm (_Touchpoint_).
- **Duy trì lợi thế cạnh tranh** trên thị trường viễn thông.
- **Phát triển bền vững** và nâng cao năng lực vận hành số hóa.

Hệ thống quy trình của FPT Telecom được phân định rõ ràng thành **3 nhóm chính**:

1. **Nhóm quy trình quản lý (Management Processes)**
2. **Nhóm quy trình cốt lõi (Core Processes)**
3. **Nhóm quy trình hỗ trợ (Support Processes)**

---

### 1. Nhóm quy trình quản lý (Management Processes)

**Đặc điểm:** Tập trung vào việc định hướng phát triển dài hạn, hoạch định chính sách, đo lường hiệu quả vận hành và đảm bảo công ty có chiến lược kinh doanh cũng như quản trị tối ưu.

- **Quy trình hoạch định chiến lược kinh doanh:**
  - _Nội dung:_ Phân tích biến động thị trường viễn thông, đánh giá đối thủ cạnh tranh, xây dựng kế hoạch kinh doanh trung và dài hạn; trình Hội đồng Quản trị phê duyệt và phân bổ chỉ tiêu xuống các Khối/Chi nhánh.
- **Quy trình quản lý và mở rộng hạ tầng:**
  - _Nội dung:_ Khảo sát nhu cầu sử dụng dịch vụ Internet/Truyền hình theo từng khu vực địa lý, đánh giá hiện trạng độ phủ cáp quang và số lượng cổng kết nối (Port) khả dụng để ra quyết định đầu tư, mở rộng vùng phủ hạ tầng mạng.
- **Quy trình đo lường chất lượng dịch vụ (NPS / KPI):**
  - _Nội dung:_ Thực hiện khảo sát mức độ hài lòng của khách hàng (Net Promoter Score – NPS) sau khi hoàn tất lắp đặt/bảo trì; tổng hợp, phân tích dữ liệu và báo cáo chỉ số KPI định kỳ của các bộ phận (Kinh doanh, Kỹ thuật, CSKH).

---

### 2. Nhóm quy trình cốt lõi (Core Processes)

**Đặc điểm:** Là chuỗi hoạt động quan trọng nhất, trực tiếp tạo ra giá trị gia tăng xuyên suốt hành trình trải nghiệm dịch vụ lắp đặt Internet của khách hàng từ lúc phát sinh nhu cầu đến khi sử dụng và chăm sóc sau bán hàng:

- **Quy trình tiếp nhận yêu cầu:**
  - _Nội dung:_ Tiếp nhận thông tin đăng ký dịch vụ của khách hàng qua đa kênh (Website fpt.vn, ứng dụng Hi FPT, Tổng đài 19006600, Quầy giao dịch hoặc nhân viên Sales D2D); ghi nhận thông tin địa chỉ lắp đặt và nhu cầu sử dụng lên hệ thống CRM/Mobisale.
- **Quy trình khảo sát hạ tầng:**
  - _Nội dung:_ Bộ phận Kỹ thuật kiểm tra bản đồ mạng GIS và hiện trường để đánh giá cự ly kéo cáp từ hộp ODF/DP đến nhà khách hàng và số lượng cổng kết nối (Port) còn trống khả dụng. Đây là điểm kiểm soát Go/No-Go xác định tính khả thi trước khi ký kết thương mại.
- **Quy trình tư vấn và ký hợp đồng:**
  - _Nội dung:_ Nhân viên kinh doanh tư vấn chi tiết gói cước, thiết bị (Modem ONT, Router Mesh Wi-Fi 6), thu thập ảnh định danh (eKYC) và tiến hành ký kết Hợp đồng điện tử (E-Contract) xác thực mã OTP qua SMS.
- **Quy trình tạo và phân bổ Work Order:**
  - _Nội dung:_ Sau khi hợp đồng ký kết thành công, hệ thống BPMS tự động tạo lệnh thi công (Work Order), phân bổ ca làm việc và tự động gán cho Kỹ thuật viên (TNC) phụ trách tuyến theo thuật toán tối ưu vị trí địa lý.
- **Quy trình thi công lắp đặt:**
  - _Nội dung:_ Kỹ thuật viên nhận vật tư thiết bị từ kho, di chuyển đến địa chỉ khách hàng, kéo rải cáp quang, hàn nối sợi quang, lắp đặt thiết bị Modem/ONT, cấu hình mạng Wi-Fi, kiểm tra suy hao quang và tiến hành nghiệm thu tốc độ (Speedtest) cùng khách hàng.
- **Quy trình kích hoạt và hậu mãi:**
  - _Nội dung:_ Hệ thống BPMS tự động gửi lệnh Provisioning kích hoạt tài khoản Internet trên mạng lõi (Radius/AAA), gửi thông tin xác nhận qua SMS/Email. Sau 24–48h, bộ phận CSKH thực hiện khảo sát mức độ hài lòng (NPS) và hỗ trợ kỹ thuật sau bán hàng.

---

### 3. Nhóm quy trình hỗ trợ (Support Processes)

**Đặc điểm:** Đảm bảo nguồn lực vật chất, tài chính và công nghệ luôn sẵn sàng để các quy trình cốt lõi và quản lý vận hành liên tục, trơn tru.

- **Quy trình quản lý kho và vật tư:**
  - _Nội dung:_ Kiểm kê định kỳ, theo dõi mức tồn kho an toàn (_Safety Stock_), lập đề xuất mua sắm bổ sung và thực hiện xuất - nhập kho thiết bị (Modem quang, Router Mesh, dây cáp quang drop wire, đầu nối fast connector...) cho đội ngũ kỹ thuật thi công.
- **Quy trình tài chính - kế toán:**
  - _Nội dung:_ Xuất hóa đơn cước hòa mạng/phí lắp đặt ban đầu, theo dõi và quản lý việc thanh toán cước phí hàng tháng của khách hàng, đối soát công nợ và tổng hợp báo cáo tài chính doanh thu.
- **Quy trình Công nghệ Thông tin (CRM / BPMS / ERP):**
  - _Nội dung:_ Quản trị, vận hành và bảo trì hệ thống máy chủ, hạ tầng phần mềm CRM và BPMS; tự động hóa luồng chuyển dữ liệu từ Hợp đồng $\rightarrow$ Work Order $\rightarrow$ Kích hoạt dịch vụ; bảo đảm an toàn thông tin và sao lưu dữ liệu định kỳ.

---

## 2.2. Sơ đồ kiến trúc nghiệp vụ FPT Telecom

Hình 2.1. Kiến trúc nghiệp vụ FPT Telecom — phân nhóm Quản lý / Cốt lõi / Hỗ trợ
![Quy trình tiếp nhận yêu cầu](/assets/diagrams/kien_truc/kien-truc-tong-quan.png)
