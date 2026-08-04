## **MÔ TẢ QUY TRÌNH TỪ LÚC KHÁCH HÀNG CÓ NHU CẦU ĐẾN KHI HOÀN THÀNH ĐẶT HÀNG.**

### **1. Phân tích quy trình**

Tên quy trình: Quy trình đăng ký và tiếp nhận yêu cầu lắp đặt Internet
FPT Telecom

**Customer (Khách hàng)**

- Khách hàng là cá nhân hoặc doanh nghiệp có nhu cầu đăng ký sử dụng
  dịch vụ Internet của FPT Telecom.

- Khách hàng là đối tượng khởi tạo quy trình bằng việc gửi yêu cầu đăng
  ký dịch vụ, đồng thời cung cấp các thông tin cần thiết, lựa chọn gói
  cước và ký hợp đồng trước khi dịch vụ được triển khai.

**Actor (Các tác nhân tham gia)**

### **1.1. Khách hàng (Customer)**

Vai trò:

- Khởi tạo nhu cầu sử dụng dịch vụ.

- Cung cấp thông tin cá nhân.

- Lựa chọn gói cước.

- Cung cấp giấy tờ.

- Ký hợp đồng.

- Chờ lắp đặt.

### **1.2. Nhân viên kinh doanh (Sales)**

Vai trò:

- Tiếp nhận yêu cầu từ khách hàng.

- Tư vấn các gói dịch vụ.

- Kiểm tra sơ bộ thông tin.

- Lập hợp đồng điện tử hoặc giấy.

- Hẹn lịch lắp đặt.

- Chuyển hồ sơ sang bộ phận kỹ thuật.

### **1.3. Bộ phận kỹ thuật**

Vai trò:

- Tiếp nhận yêu cầu trên hệ thống.

- Kiểm tra hạ tầng cáp quang.

- Kiểm tra số lượng cổng kết nối (Port).

- Xác nhận khả năng triển khai dịch vụ.

### **1.4. Hệ thống BPMS/CRM**

Vai trò:

- Tiếp nhận dữ liệu hợp đồng.

- Sinh Work Order.

- Quản lý quy trình.

- Phân công đội kỹ thuật khu vực.

## **DIỄN GIẢI LUỒNG VẬN HÀNH**

Quy trình đăng ký lắp đặt dịch vụ Internet của FPT Telecom được bắt đầu
khi khách hàng phát sinh nhu cầu sử dụng dịch vụ Internet hoặc truyền
hình. Khách hàng có thể đăng ký thông qua nhiều kênh khác nhau như
Website chính thức của FPT Telecom, Hotline chăm sóc khách hàng, trực
tiếp tại các cửa hàng giao dịch hoặc thông qua nhân viên kinh doanh.

Có 3 trường hợp Khách hàng đăng ký như sau:

\- Đối với hình thức đăng ký trên Website, khách hàng chủ động nhập đầy
đủ các thông tin cá nhân, địa chỉ lắp đặt, số điện thoại liên hệ và lựa
chọn gói cước mong muốn. Sau khi gửi biểu mẫu đăng ký, hệ thống ghi nhận
thông tin và chuyển đến nhân viên kinh doanh để liên hệ xác nhận.

\- Nếu khách hàng đăng ký qua Hotline, tổng đài viên hoặc nhân viên kinh
doanh sẽ tiếp nhận thông tin, tư vấn các gói cước phù hợp, đồng thời ghi
nhận nhu cầu lắp đặt trên hệ thống.

\- Trong trường hợp khách hàng đến trực tiếp cửa hàng giao dịch hoặc gặp
nhân viên kinh doanh, nhân viên sẽ tư vấn chi tiết về các gói dịch vụ,
chính sách khuyến mãi và hướng dẫn khách hàng hoàn tất thủ tục đăng ký.

Sau khi tiếp nhận yêu cầu, nhân viên kinh doanh tiến hành thu thập đầy
đủ các thông tin cần thiết bao gồm họ tên khách hàng, địa chỉ lắp đặt,
số điện thoại liên hệ và gói cước đăng ký.

Đối với khách hàng đăng ký trực tuyến, nhân viên kinh doanh sẽ chủ động
liên hệ để xác nhận thông tin, tư vấn dịch vụ phù hợp, lập hợp đồng điện
tử, lựa chọn thiết bị Modem WiFi và thống nhất lịch lắp đặt.

Đối với khách hàng đăng ký trực tiếp hoặc thông qua hoạt động khảo sát
thị trường, nhân viên kinh doanh sẽ kiểm tra sơ bộ điều kiện triển khai
tại khu vực, đánh giá khả năng kéo cáp đến địa chỉ lắp đặt và xác nhận
các thông tin trước khi lập hợp đồng và hẹn lịch thi công.

Sau khi hồ sơ được hoàn tất, yêu cầu sẽ được chuyển sang bộ phận kỹ
thuật để kiểm tra khả năng cung cấp dịch vụ. Nhân viên kỹ thuật tiếp
nhận yêu cầu trên hệ thống quản lý và tiến hành kiểm tra hạ tầng cáp
quang tại khu vực lắp đặt, đồng thời xác minh số lượng cổng kết nối
(Port) còn khả dụng.

Tại bước này phát sinh điểm quyết định. Nếu khu vực chưa có hạ tầng hoặc
không còn cổng kết nối khả dụng thì bộ phận kỹ thuật sẽ thông báo cho
nhân viên kinh doanh để phản hồi khách hàng về việc chưa thể triển khai
dịch vụ và quy trình kết thúc.

Ngược lại, nếu khu vực đáp ứng đầy đủ điều kiện triển khai thì quy trình
tiếp tục sang bước tư vấn và ký kết hợp đồng. Nhân viên kinh doanh tư
vấn lần cuối về gói cước, các chương trình ưu đãi, thời gian triển khai
và hướng dẫn khách hàng cung cấp các giấy tờ cần thiết. Sau khi hai bên
thống nhất nội dung, khách hàng thực hiện ký hợp đồng bằng hình thức
điện tử hoặc hợp đồng giấy.

Khi hợp đồng đã được xác nhận, toàn bộ thông tin sẽ được chuyển vào hệ
thống BPMS/CRM. Hệ thống tự động tạo Work Order (đơn lắp đặt) và phân
công nhiệm vụ cho đội kỹ thuật phụ trách khu vực để chuẩn bị triển khai
lắp đặt theo lịch đã hẹn với khách hàng. Đây là bước kết thúc của quy
trình tiếp nhận và xử lý yêu cầu đăng ký dịch vụ.
