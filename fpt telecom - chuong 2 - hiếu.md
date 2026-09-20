# CHƯƠNG 2: HỆ THỐNG QUY TRÌNH NGHIỆP VỤ FPT TELECOM

## 2.1. Kiến trúc quy trình nghiệp vụ của FPT Telecom

Để đảm bảo hoạt động hiệu quả trong việc cung cấp dịch vụ viễn thông và Internet chất lượng cao đến khách hàng, **FPT Telecom** xây dựng một hệ thống quy trình nghiệp vụ chặt chẽ, xuyên suốt từ định hướng chiến lược, vận hành cốt lõi đến các hoạt động hỗ trợ. Mô hình quản trị này giúp công ty tối ưu hóa trải nghiệm khách hàng ở mọi điểm chạm, duy trì lợi thế cạnh tranh trên thị trường viễn thông, đồng thời phát triển bền vững và nâng cao năng lực vận hành số hóa.

Hệ thống quy trình của FPT Telecom được phân định rõ ràng thành 3 nhóm chính: Nhóm quy trình quản lý (Management Processes), Nhóm quy trình cốt lõi (Core Processes) và Nhóm quy trình hỗ trợ (Support Processes).

### 2.1.1. Nhóm quy trình quản lý (Management Processes)

Nhóm quy trình này tập trung vào việc định hướng phát triển dài hạn, hoạch định chính sách, đo lường hiệu quả vận hành và đảm bảo công ty có chiến lược kinh doanh cũng như quản trị tối ưu.

#### 2.1.1.1. Quy trình hoạch định chiến lược kinh doanh

**Tác nhân (Actor):** Hội đồng Quản trị, Ban Điều hành, Khối Kinh doanh & Marketing.

**Khách hàng (Customer):** Khách hàng nội bộ (Các khối nghiệp vụ, Chi nhánh cấp dưới).

**Luồng thực hiện (Workflow):** Phân tích biến động thị trường, đánh giá đối thủ cạnh tranh, xây dựng kế hoạch kinh doanh trung và dài hạn. Sau đó trình Hội đồng Quản trị phê duyệt và tiến hành phân bổ chỉ tiêu xuống các Khối/Chi nhánh.

**Kết quả đầu ra:**
Nếu tích cực, chiến lược được thông qua, công ty mở rộng thị phần thành công.
Nếu tiêu cực, định hướng sai lệch dẫn đến lãng phí ngân sách đầu tư.

#### 2.1.1.2. Quy trình quản lý và mở rộng hạ tầng

**Tác nhân (Actor):** Khối Kỹ thuật & Hạ tầng, Ban Giám đốc.

**Khách hàng (Customer):** Đội ngũ Kỹ thuật, Khách hàng cuối tại khu vực mở rộng.

**Luồng thực hiện (Workflow):** Khảo sát nhu cầu vùng để đánh giá độ phủ cáp quang và số lượng cổng Port hiện tại. Tiến hành lập dự án đầu tư mở rộng, sau đó thi công hạ tầng mạng và cập nhật bản đồ GIS.

**Kết quả đầu ra:**
Nếu tích cực, khắc phục triệt để tình trạng hết Port, sẵn sàng hạ tầng cho Sales bán hàng.
Nếu tiêu cực, dự án bị chậm tiến độ do vướng mắc giấy phép ngầm hóa hoặc cột điện lực.

#### 2.1.1.3. Quy trình đo lường chất lượng dịch vụ (NPS / KPI)

**Tác nhân (Actor):** Khối CSKH & Vận hành (Quản lý chất lượng).

**Khách hàng (Customer):** Khách hàng sử dụng dịch vụ, Ban Giám đốc.

**Luồng thực hiện (Workflow):** Trích xuất danh sách khách hàng mới lắp đặt để thực hiện khảo sát qua tin nhắn SMS hoặc tổng đài gọi điện. Ghi nhận điểm số Net Promoter Score (NPS), tổng hợp báo cáo KPI định kỳ và đề xuất hướng cải tiến.

**Kết quả đầu ra:**
Nếu tích cực, tỷ lệ khách hàng hài lòng cao (Promoters), nhân viên đạt KPI thưởng.
Nếu tiêu cực, tỷ lệ phàn nàn cao (Detractors), nhân sự bị trừ KPI thưởng.

### 2.1.2. Nhóm quy trình cốt lõi (Core Processes)

Đây là chuỗi hoạt động trực tiếp tạo ra giá trị gia tăng xuyên suốt hành trình trải nghiệm dịch vụ của khách hàng, bắt đầu từ lúc phát sinh nhu cầu đăng ký Internet đến khi sử dụng ổn định.

#### 2.1.2.1. Quy trình tiếp nhận yêu cầu

**Tác nhân (Actor):** Khách hàng, Nhân viên Sales, Tổng đài viên.

**Khách hàng (Customer):** Cá nhân hoặc doanh nghiệp có nhu cầu đăng ký Internet.

**Luồng thực hiện (Workflow):** Tiếp nhận thông tin qua các điểm chạm đa kênh (Website, Hotline, Nhân viên thị trường). Ghi nhận nhu cầu, địa chỉ lắp đặt, nhập liệu cơ sở dữ liệu lên hệ thống CRM/Mobisale và chuyển sang bộ phận khảo sát.

**Kết quả đầu ra:**
Chuyển đổi thành công thông tin người quan tâm thành Lead (Cơ hội bán hàng) trên hệ thống.

#### 2.1.2.2. Quy trình khảo sát hạ tầng

**Tác nhân (Actor):** Bộ phận Kỹ thuật khảo sát.

**Khách hàng (Customer):** Khách hàng đăng ký, Nhân viên Sales.

**Luồng thực hiện (Workflow):** Nhận ticket phân công từ CRM, tiến hành kiểm tra bản đồ mạng GIS. Đối chiếu cự ly cáp thực tế so với vị trí nhà khách hàng và kiểm tra cổng Port còn khả dụng tại hộp ODF, sau đó đưa ra quyết định Go/No-Go.

**Kết quả đầu ra:**
Nếu tích cực, hệ thống xác nhận đủ hạ tầng và cho phép Sales tiến hành ký kết Hợp đồng.
Nếu tiêu cực, khu vực bị hết cáp hoặc hết port, buộc phải hủy yêu cầu và xin lỗi khách hàng.

#### 2.1.2.3. Quy trình tư vấn và ký hợp đồng

**Tác nhân (Actor):** Nhân viên Sales, Khách hàng.

**Khách hàng (Customer):** Người đăng ký dịch vụ.

**Luồng thực hiện (Workflow):** Nhân viên tư vấn chốt gói cước băng thông và thiết bị đi kèm (Modem ONT, Mesh). Thu thập hình ảnh định danh eKYC, lên Hợp đồng điện tử (E-Contract), gửi mã OTP qua tin nhắn SMS để khách hàng xác thực và ký số.

**Kết quả đầu ra:**
Hợp đồng pháp lý được ký kết thành công trên hệ thống và hệ thống ghi nhận doanh thu dự kiến.

#### 2.1.2.4. Quy trình tạo và phân bổ Work Order

**Tác nhân (Actor):** Hệ thống BPMS / CRM.

**Khách hàng (Customer):** Đội Kỹ thuật viên (TNC), Bộ phận Kho.

**Luồng thực hiện (Workflow):** Hệ thống BPMS tiếp nhận dữ liệu Hợp đồng điện tử. Tự động sinh lệnh thi công (Work Order), chạy thuật toán tối ưu hóa định tuyến vị trí và phân công ca trực tiếp cho Kỹ thuật viên phù hợp.

**Kết quả đầu ra:**
Nguồn lực được phân bổ hoàn toàn tự động, đảm bảo đúng người, đúng tuyến và không có độ trễ thời gian.

#### 2.1.2.5. Quy trình thi công lắp đặt

**Tác nhân (Actor):** Kỹ thuật viên (TNC), Khách hàng.

**Khách hàng (Customer):** Người sử dụng dịch vụ.

**Luồng thực hiện (Workflow):** Kỹ thuật viên nhận vật tư thiết bị từ kho, di chuyển đến địa chỉ nhà khách hàng. Thực hiện kéo rải cáp quang, hàn nối sợi quang, lắp đặt Modem, cấu hình mạng Wi-Fi, chạy bài kiểm tra tốc độ (Speedtest) và yêu cầu khách ký nghiệm thu.

**Kết quả đầu ra:**
Nếu tích cực, thông số suy hao quang đạt tiêu chuẩn kỹ thuật, tốc độ Internet đúng như cam kết.
Nếu tiêu cực, gặp lỗi thiết bị hoặc đứt cáp ngầm, kỹ thuật viên phải thi công lại từ đầu (Rework).

#### 2.1.2.6. Quy trình kích hoạt và hậu mãi

**Tác nhân (Actor):** Hệ thống Radius/AAA, Bộ phận CSKH.

**Khách hàng (Customer):** Người sử dụng dịch vụ.

**Luồng thực hiện (Workflow):** Kỹ thuật viên báo cáo hoàn tất trên ứng dụng. Hệ thống BPMS gửi lệnh Provisioning kích hoạt tài khoản trên mạng lõi, đồng thời gửi SMS/Email xác nhận cho khách. Sau đó, bộ phận CSKH sẽ hỗ trợ kỹ thuật sau bán hàng.

**Kết quả đầu ra:**
Dịch vụ chính thức được hạch toán vận hành thương mại, khách hàng sử dụng mạng ổn định.

### 2.1.3. Nhóm quy trình hỗ trợ (Support Processes)

Nhóm quy trình này làm nhiệm vụ đảm bảo các nguồn lực cốt lõi về vật chất, tài chính và công nghệ luôn sẵn sàng để chuỗi vận hành chính hoạt động trơn tru.

#### 2.1.3.1. Quy trình quản lý kho và xuất vật tư

**Tác nhân (Actor):** Bộ phận Kho & Vật tư, Kỹ thuật viên.

**Khách hàng (Customer):** Đội ngũ Kỹ thuật viên (TNC).

**Luồng thực hiện (Workflow):** Thực hiện kiểm kê kho định kỳ và nhập hàng hóa mới. Tiếp nhận yêu cầu xuất kho từ Work Order, quét mã Barcode hoặc mã MAC thiết bị, bàn giao Modem và vật tư phụ cho Kỹ thuật viên, cuối cùng tiến hành đối soát lượng tồn kho.

**Kết quả đầu ra:**
Vật tư được cấp phát đầy đủ, chính xác thông số series, không gây gián đoạn quá trình thi công.

#### 2.1.3.2. Quy trình tài chính - kế toán

**Tác nhân (Actor):** Khối Tài chính - Kế toán (Kế toán công nợ, Kế toán doanh thu).

**Khách hàng (Customer):** Khách hàng thanh toán, Ban Giám đốc.

**Luồng thực hiện (Workflow):** Kế toán tiếp nhận thông tin từ Hợp đồng điện tử để thu phí hòa mạng ban đầu. Thực hiện theo dõi quản lý cước trả sau hàng tháng, đối soát công nợ qua các cổng thanh toán (VNPay, Foxpay) và xuất hóa đơn điện tử e-Invoice.

**Kết quả đầu ra:**
Đảm bảo thu hồi dòng tiền nhanh chóng, sổ sách kế toán minh bạch và tuân thủ đúng luật thuế hiện hành.

#### 2.1.3.3. Quy trình Công nghệ Thông tin (CRM / BPMS / ERP)

**Tác nhân (Actor):** Ban Công nghệ / Quản trị viên hệ thống.

**Khách hàng (Customer):** Toàn bộ nhân viên FPT Telecom sử dụng hệ thống phần mềm.

**Luồng thực hiện (Workflow):** Đội ngũ IT giám sát hoạt động của máy chủ, bảo trì và nâng cấp phần mềm CRM/BPMS. Quản trị phân quyền truy cập dữ liệu người dùng, xử lý các sự cố tắc nghẽn mạng nội bộ và tiến hành sao lưu (Backup) an toàn thông tin định kỳ.

**Kết quả đầu ra:**
Hệ thống vận hành với chỉ số uptime 99.99%, đảm bảo luồng chuyển dữ liệu xuyên suốt và dữ liệu khách hàng được bảo mật tuyệt đối.

## 2.2. Sơ đồ kiến trúc nghiệp vụ FPT Telecom

![Sơ đồ tổ chức](<assets/Sơ đồ cơ cấu tổ chức tổng thể v3.png>)


Hình 2.1. Kiến trúc nghiệp vụ FPT Telecom — phân nhóm Quản lý / Cốt lõi / Hỗ trợ
