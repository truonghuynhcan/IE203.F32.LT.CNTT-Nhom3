## **3.4. Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom**

### **3.4.1. Mô tả Quy trình**

Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet là quy trình đầu vào của chuỗi cung cấp dịch vụ Internet FPT Telecom. Quy trình bắt đầu khi khách hàng phát sinh nhu cầu sử dụng dịch vụ và kết thúc khi yêu cầu đủ điều kiện đã được ghi nhận trên BPMS/CRM, tạo Work Order và phân công cho đội kỹ thuật khu vực để chuyển sang giai đoạn triển khai lắp đặt.
#### **3.4.1.1. Các bước thực hiện**
Quy trình gồm **13 bước nghiệp vụ chính**, **07 cổng quyết định Exclusive XOR (GW1–GW7)** và **06 cổng gộp nhánh Exclusive XOR**. Các cổng quyết định thể hiện các lựa chọn về kênh đăng ký, xác nhận dịch vụ, điều kiện kỹ thuật, tính hợp lệ của hồ sơ, lịch lắp đặt và hình thức ký hợp đồng; các cổng gộp nhánh không mang điều kiện nghiệp vụ, chỉ bảo đảm mỗi hoạt động có đúng một luồng vào theo chuẩn BPMN 2.0.

| Bước | Nội dung |
|---|---|
| **Bước 1: Khách hàng phát sinh nhu cầu và lựa chọn kênh đăng ký – GW1** | Khách hàng có nhu cầu sử dụng Internet hoặc dịch vụ đi kèm lựa chọn kênh tiếp nhận ban đầu. **GW1 – XOR: Kênh đăng ký?** gồm bốn nhánh: Website, Hotline, cửa hàng giao dịch hoặc nhân viên kinh doanh. Các nhánh hội tụ tại thời điểm thông tin đăng ký ban đầu được chuyển cho Sales xử lý. |
| **Bước 2: Khách hàng cung cấp thông tin đăng ký ban đầu** | Khách hàng cung cấp họ tên, số điện thoại liên hệ, địa chỉ lắp đặt và nhu cầu sử dụng. Đối với Website, khách hàng chủ động nhập thông tin; đối với Hotline, cửa hàng hoặc nhân viên kinh doanh, thông tin được nhân sự phụ trách tiếp nhận. |
| **Bước 3: Sales tiếp nhận, kiểm tra thông tin và tư vấn gói cước** | Sales ghi nhận các thông tin cơ bản, làm rõ nhu cầu sử dụng và tư vấn gói cước phù hợp. |
| **Bước 4: Khách hàng xác nhận gói cước và nhu cầu – GW2** | Sau bước tư vấn, **GW2 – XOR: Khách hàng đã xác nhận gói cước và nhu cầu sử dụng?**<br><br>* **Đã xác nhận:** Sales được phép lập hồ sơ đăng ký sơ bộ.<br>* **Chưa xác nhận:** Sales tiếp tục tư vấn, làm rõ nhu cầu và duy trì yêu cầu ở giai đoạn tư vấn cho đến khi khách hàng xác nhận gói cước và nhu cầu sử dụng. |
| **Bước 5: Sales lập hồ sơ đăng ký sơ bộ và chuyển Technical kiểm tra** | Khi khách hàng đã xác nhận gói cước, Sales lập hồ sơ đăng ký sơ bộ và chuyển yêu cầu sang Technical để kiểm tra khả năng cung cấp dịch vụ tại địa chỉ đăng ký. |
| **Bước 6: Technical kiểm tra hạ tầng cáp quang – GW3** | Technical kiểm tra điều kiện hạ tầng cáp quang tại khu vực lắp đặt. Kết quả kiểm tra được đánh giá tại **GW3 – XOR: Hạ tầng cáp quang có đáp ứng?**<br><br>* **Không đáp ứng:** Kết luận yêu cầu chưa đủ điều kiện kỹ thuật; Sales thông báo khách hàng và quy trình kết thúc, không tạo Work Order.<br>* **Đáp ứng:** Chuyển sang kiểm tra số lượng Port còn khả dụng. |
| **Bước 7: Technical kiểm tra Port – GW4** | Technical kiểm tra số lượng cổng kết nối (Port) còn khả dụng. **GW4 – XOR: Có Port khả dụng?**<br><br>* **Không có Port khả dụng:** Kết luận yêu cầu chưa đủ điều kiện kỹ thuật; Sales thông báo khách hàng và quy trình kết thúc, không tạo Work Order.<br>* **Có Port khả dụng:** Technical xác nhận điều kiện kỹ thuật đáp ứng và quy trình chuyển sang hoàn thiện hồ sơ. |
| **Bước 8: Sales yêu cầu khách hàng hoàn thiện hồ sơ đăng ký** | Khi đủ điều kiện kỹ thuật, Sales yêu cầu khách hàng hoàn thiện hồ sơ và cung cấp các giấy tờ cần thiết; khách hàng hoàn thiện và gửi lại hồ sơ cho Sales. |
| **Bước 9: Sales kiểm tra tính đầy đủ, hợp lệ của hồ sơ – GW5** | **GW5 – XOR: Hồ sơ đầy đủ và hợp lệ?**<br><br>* **Không:** Sales yêu cầu khách hàng bổ sung hoặc chỉnh sửa; khách hàng gửi lại hồ sơ và Sales kiểm tra lại. Vòng lặp tiếp tục cho đến khi hồ sơ đáp ứng yêu cầu.<br>* **Có:** Chuyển sang bước xác nhận lịch lắp đặt. |
| **Bước 10: Xác nhận lịch lắp đặt – GW6** | Sales đề nghị khách hàng xác nhận lịch lắp đặt. **GW6 – XOR: Khách hàng đã xác nhận lịch lắp đặt?**<br><br>* **Đã xác nhận:** Sales chuyển sang gửi hợp đồng để khách hàng ký.<br>* **Chưa xác nhận:** Sales tiếp tục phối hợp với khách hàng để xác nhận lịch; quy trình chuyển sang bước gửi hợp đồng sau khi lịch lắp đặt được chốt. |
| **Bước 11: Gửi và ký hợp đồng – GW7** | Sales gửi hợp đồng cho khách hàng. **GW7 – XOR: Hình thức ký hợp đồng?** gồm hai nhánh:<br><br>* **Ký điện tử.**<br>* **Ký hợp đồng giấy.**<br><br>Hai nhánh hội tụ tại trạng thái “Hợp đồng đã ký”. |
| **Bước 12: Sales tiếp nhận hợp đồng đã ký và chuyển thông tin vào BPMS/CRM** | Sales tiếp nhận hợp đồng đã ký, chuyển thông tin vào hệ thống để ghi nhận giao dịch và trạng thái đăng ký. |
| **Bước 13: BPMS/CRM tạo Work Order, phân công và kết thúc quy trình** | BPMS/CRM ghi nhận hợp đồng, tạo Work Order, phân công đơn cho đội kỹ thuật phụ trách khu vực và cập nhật trạng thái để chuyển sang giai đoạn triển khai lắp đặt. Quy trình kết thúc khi Work Order đã được tạo, phân công và trạng thái yêu cầu được cập nhật. |

#### **3.4.1.2. Các tác nhân tham gia quy trình (Actors):**

| STT | Tác nhân | Vai trò và trách nhiệm trong quy trình |
| :---: | :--- | :--- |
| **1** | **Khách hàng (Customer)** | Khởi tạo nhu cầu; lựa chọn kênh đăng ký; cung cấp thông tin; xác nhận gói cước; hoàn thiện/bổ sung hồ sơ; xác nhận lịch; ký hợp đồng. |
| **2** | **Bộ phận Kinh doanh (Sales)** | Tiếp nhận và ghi nhận thông tin; tư vấn; lập hồ sơ sơ bộ; chuyển yêu cầu kiểm tra kỹ thuật; kiểm tra hồ sơ; điều phối lịch; gửi/nhận hợp đồng; chuyển dữ liệu vào BPMS/CRM. |
| **3** | **Bộ phận Kỹ thuật (Technical)** | Kiểm tra hạ tầng cáp quang; kiểm tra Port; đánh giá khả năng cung cấp dịch vụ; trả kết quả kỹ thuật. |
| **4** | **Hệ thống BPMS/CRM** | Ghi nhận hợp đồng; tạo Work Order; phân công đội kỹ thuật khu vực; lưu và cập nhật trạng thái yêu cầu. |
| **5** | **Đội kỹ thuật khu vực** | Là tác nhân nhận đầu ra của quy trình; tiếp nhận Work Order để thực hiện quy trình triển khai lắp đặt tiếp theo. |


#### **3.4.1.3. Khách hàng của quy trình (Customer):**

* **Khách hàng bên ngoài:** Cá nhân hoặc doanh nghiệp đăng ký sử dụng dịch vụ Internet FPT Telecom. Khách hàng kỳ vọng được tư vấn đúng nhu cầu, biết sớm khả năng triển khai, hoàn tất thủ tục thuận tiện và có lịch lắp đặt rõ ràng.
* **Khách hàng nội bộ:** Đội kỹ thuật khu vực tiếp nhận Work Order. Đầu ra cần có đủ thông tin cần thiết để đội kỹ thuật có thể tiếp tục triển khai mà không phải xác minh lại các nội dung đã được xử lý ở giai đoạn đăng ký.


  **Giá trị mang lại:**

* **Xác định đúng nhu cầu dịch vụ:** Giúp khách hàng lựa chọn gói cước phù hợp với nhu cầu sử dụng.
* **Xác định khả năng cung cấp trước khi cam kết:** Kiểm tra hạ tầng và Port trước khi chuyển sang triển khai.
* **Kiểm soát chất lượng hồ sơ:** Hạn chế việc tạo đơn khi hồ sơ còn thiếu hoặc chưa hợp lệ.
* **Giảm rủi ro triển khai:** Ngăn các yêu cầu không đủ điều kiện kỹ thuật chuyển sang giai đoạn thi công.
* **Chuẩn hóa phối hợp liên bộ phận:** Làm rõ điểm giao tiếp giữa Customer, Sales, Technical và BPMS/CRM.
* **Chuyển đổi nhu cầu thành lệnh triển khai:** Tạo Work Order có trạng thái và đơn vị kỹ thuật phụ trách cụ thể.

#### **3.4.1.4. Những kết quả có thể đạt được:**

| Kết quả / trạng thái | Diễn giải chi tiết |
| :--- | :--- |
| **Đăng ký thành công (Happy Path)** | Khách hàng xác nhận gói cước; hạ tầng và Port đáp ứng; hồ sơ hợp lệ; lịch lắp đặt được xác nhận; hợp đồng được ký; BPMS/CRM tạo và phân công Work Order. |
| **Kết thúc do hạ tầng không đáp ứng** | Tại GW3, hạ tầng cáp quang tại khu vực lắp đặt không đáp ứng; Sales thông báo khách hàng; không tạo Work Order. |
| **Kết thúc do không có Port khả dụng** | Tại GW4, không có Port khả dụng; Sales thông báo khách hàng; không tạo Work Order. |
| **Chờ hoàn thiện hồ sơ** | Tại GW5, hồ sơ thiếu hoặc chưa hợp lệ; Sales yêu cầu bổ sung/chỉnh sửa và kiểm tra lại. |
| **Chờ xác nhận của khách hàng** | Tại GW2 hoặc GW6, yêu cầu được duy trì tại bước tư vấn hoặc xác nhận lịch cho đến khi khách hàng hoàn tất xác nhận để chuyển sang công đoạn tiếp theo. |
| **Biến thể kênh/hình thức ký** | GW1 phân nhánh theo kênh đăng ký ban đầu; GW7 phân nhánh theo ký điện tử hoặc ký giấy. Các nhánh hội tụ về cùng luồng nghiệp vụ tiếp theo. |


#### **3.4.1.5. Phỏng vấn**

Phương pháp phỏng vấn tập trung làm rõ trải nghiệm xử lý của Customer, Sales và Technical; mức độ thuận tiện của các kênh tiếp nhận; nguyên nhân phát sinh thời gian chờ; tỷ lệ hồ sơ phải bổ sung; và mức độ liên thông dữ liệu giữa các kênh đăng ký với BPMS/CRM. Bộ câu hỏi gồm **10 câu hỏi định tính** và **10 câu hỏi định lượng**, kết hợp câu hỏi có cấu trúc và câu hỏi không có cấu trúc.

##### **3.4.1.5.1. Câu hỏi phỏng vấn định tính**

**Nhóm câu hỏi có cấu trúc:**

| STT | Đối tượng | Nội dung câu hỏi | Thang đo / phương án lựa chọn |
| :---: | :--- | :--- | :--- |
| **1** | Khách hàng | Mức độ thuận tiện khi gửi yêu cầu đăng ký qua kênh đã lựa chọn như thế nào? | Likert 1–5: rất bất tiện → rất thuận tiện. |
| **2** | Khách hàng | Mức độ rõ ràng của thông tin tư vấn gói cước do Sales cung cấp? | Likert 1–5. |
| **3** | Sales | Mức độ đầy đủ của thông tin khách hàng ngay lần tiếp nhận đầu tiên? | Likert 1–5. |
| **4** | Sales | Việc chuyển yêu cầu sang Technical hiện chủ yếu được thực hiện bằng cách nào? | [A] Tự động trên hệ thống; [B] BPMS/CRM có thao tác thủ công; [C] Email/chat; [D] Cách khác. |
| **5** | Technical | Mức độ thuận tiện khi tra cứu hạ tầng và Port phục vụ kiểm tra yêu cầu? | Likert 1–5. |

**Nhóm câu hỏi không có cấu trúc:**

| STT | Đối tượng | Nội dung câu hỏi mở | Mục tiêu thu thập thông tin |
| :---: | :--- | :--- | :--- |
| **1** | Sales | Những nguyên nhân nào thường làm yêu cầu đăng ký bị chậm ngay từ bước tiếp nhận và tư vấn? | Xác định bottleneck đầu quy trình. |
| **2** | Technical | Khó khăn lớn nhất khi xác định khả năng cung cấp dịch vụ tại địa chỉ khách hàng là gì? | Nhận diện hạn chế dữ liệu/hệ thống kỹ thuật. |
| **3** | Sales | Những lỗi hồ sơ nào khiến khách hàng phải bổ sung hoặc chỉnh sửa nhiều nhất? | Xác định nguyên nhân Rework. |
| **4** | Khách hàng | Bước nào trong quá trình đăng ký khiến khách hàng phải chờ hoặc cung cấp lại thông tin nhiều nhất? | Đánh giá trải nghiệm khách hàng và NVA. |
| **5** | Sales / Quản lý vận hành | Nếu chỉ được ưu tiên tự động hóa một điểm của quy trình, Anh/Chị sẽ chọn điểm nào và vì sao? | Xác định ưu tiên To-Be. |

##### **3.4.1.5.2. Câu hỏi phỏng vấn định lượng**

**Nhóm câu hỏi có cấu trúc:**

| STT | Đối tượng | Nội dung câu hỏi | Thang đo / phương án lựa chọn |
| :---: | :--- | :--- | :--- |
| **1** | Sales | Thời gian trung bình từ khi có lead/yêu cầu đến khi Sales liên hệ lần đầu là bao lâu? | [A] ≤15 phút; [B] 16–30 phút; [C] 31–60 phút; [D] 61–120 phút; [E] >120 phút. |
| **2** | Sales | Thời gian trung bình để tư vấn và lập hồ sơ đăng ký sơ bộ cho một yêu cầu? | [A] ≤20 phút; [B] 21–40 phút; [C] 41–60 phút; [D] >60 phút. |
| **3** | Technical | Thời gian trung bình để kiểm tra hạ tầng và Port cho một địa chỉ? | [A] ≤15 phút; [B] 16–30 phút; [C] 31–45 phút; [D] >45 phút. |
| **4** | Sales | Tỷ lệ hồ sơ đầy đủ, hợp lệ ngay lần đầu là bao nhiêu? | [A] <50%; [B] 50–69%; [C] 70–89%; [D] ≥90%. |
| **5** | BPMS/CRM / Sales | Thời gian từ khi nhận hợp đồng đã ký đến khi Work Order được tạo và phân công? | [A] ≤10 phút; [B] 11–20 phút; [C] 21–30 phút; [D] >30 phút. |

**Nhóm câu hỏi không có cấu trúc:**

| STT | Đối tượng | Nội dung câu hỏi | Dữ liệu kỳ vọng |
| :---: | :--- | :--- | :--- |
| **1** | Sales | Trong một tháng, số yêu cầu phải bổ sung/chỉnh sửa hồ sơ dao động trong khoảng bao nhiêu? | Số yêu cầu/tháng |
| **2** | Technical | Tỷ lệ yêu cầu bị từ chối do không đủ hạ tầng hoặc hết Port là bao nhiêu? | % |
| **3** | Sales | Một hồ sơ bị Rework thường phải bổ sung bao nhiêu vòng trước khi hợp lệ? | Số vòng/hồ sơ |
| **4** | Sales / BPMS | Tỷ lệ yêu cầu phải nhập lại dữ liệu giữa kênh tiếp nhận và BPMS/CRM là bao nhiêu? | % |
| **5** | Quản lý vận hành | Mức giảm Cycle Time mục tiêu nếu tích hợp tự động các kênh đăng ký, Technical và BPMS/CRM là bao nhiêu? | % hoặc phút |

---

### **3.4.2. Mô hình hóa quy trình**
#### **3.4.2.1 Mô hình hóa Quy trình BPMN**

![Hình 3.4.1. Mô hình hóa Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom](./docs/Quy%20trinh%20Tu%20van%20Lap%20dat%20Internet%20FPT.png)

Mô hình BPMN As-Is của quy trình được xây dựng với **07 cổng quyết định Exclusive XOR (GW1–GW7)**, phản ánh các điểm lựa chọn và kiểm soát chính từ khi khách hàng phát sinh nhu cầu đến khi Work Order được tạo và phân công. Hai điều kiện kỹ thuật về **hạ tầng cáp quang** và **Port khả dụng** được thể hiện thành hai cổng quyết định riêng để làm rõ nguyên nhân dẫn đến kết quả đủ hoặc không đủ điều kiện triển khai. Tại mọi điểm có từ hai luồng xử lý trở lên cùng hội tụ vào một hoạt động (kênh đăng ký, nhánh sau quyết định, hoặc vòng lặp xử lý lại), mô hình sử dụng một **cổng gộp nhánh Exclusive XOR** tường minh trước khi vào hoạt động đó. Tổng số cổng trong sơ đồ BPMN As-Is là **13**, gồm 07 cổng quyết định (GW1–GW7) và 06 cổng gộp nhánh.

#### **3.4.2.1 Các gateway**

**Hệ thống 07 cổng quyết định (Decision) Exclusive XOR:**
| Gateway | Loại | Nội dung |
|---|---|---|
| **GW1** | **XOR** | **Khách hàng đăng ký qua kênh nào?**<br><br>* Website.<br>* Hotline.<br>* Cửa hàng giao dịch.<br>* Nhân viên kinh doanh.<br><br>GW1 phản ánh lựa chọn kênh đầu vào của **một yêu cầu đăng ký cụ thể**. Các nhánh hội tụ trước bước Sales xử lý thông tin. |
| **GW2** | **XOR** | **Khách hàng đã xác nhận gói cước và nhu cầu sử dụng?**<br><br>* **Đã xác nhận:** Sales lập hồ sơ đăng ký sơ bộ.<br>* **Chưa xác nhận:** Sales tiếp tục tư vấn và làm rõ nhu cầu; khi khách hàng xác nhận, luồng quay lại GW2 và chuyển sang lập hồ sơ đăng ký sơ bộ. |
| **GW3** | **XOR** | **Hạ tầng cáp quang tại khu vực lắp đặt có đáp ứng?**<br><br>* **Có:** Chuyển sang kiểm tra Port.<br>* **Không:** Kết luận chưa đủ điều kiện kỹ thuật → Sales thông báo khách hàng → kết thúc yêu cầu, không tạo Work Order. |
| **GW4** | **XOR** | **Có Port khả dụng?**<br><br>* **Có:** Xác nhận đủ điều kiện kỹ thuật → chuyển sang hoàn thiện hồ sơ.<br>* **Không:** Kết luận chưa đủ điều kiện kỹ thuật → Sales thông báo khách hàng → kết thúc yêu cầu, không tạo Work Order. |
| **GW5** | **XOR** | **Hồ sơ đầy đủ và hợp lệ?**<br><br>* **Có:** Chuyển sang xác nhận lịch lắp đặt.<br>* **Không:** Sales yêu cầu bổ sung/chỉnh sửa → Customer bổ sung/chỉnh sửa → Sales kiểm tra lại → quay về GW5.<br><br>Nhánh này tạo thành **Rework Loop** cho đến khi hồ sơ đạt yêu cầu. |
| **GW6** | **XOR** | **Khách hàng đã xác nhận lịch lắp đặt?**<br><br>* **Đã xác nhận:** Sales gửi hợp đồng để khách hàng ký.<br>* **Chưa xác nhận:** Sales tiếp tục phối hợp xác nhận lịch; khi lịch được chốt, luồng quay lại GW6 và chuyển sang gửi hợp đồng. |
| **GW7** | **XOR** | **Hình thức ký hợp đồng?**<br><br>* **Ký điện tử.**<br>* **Ký hợp đồng giấy.**<br><br>Hai nhánh hội tụ tại trạng thái **“Hợp đồng đã ký”**, sau đó Sales/BPMS/CRM tiếp tục xử lý chung. |

**Hệ thống 06 cổng gộp nhánh Exclusive XOR:**

Sáu cổng gộp không mang điều kiện nghiệp vụ, đóng vai trò điểm hội tụ kỹ thuật của luồng xử lý:
| Gateway | Loại | Nội dung |
|---|---|---|
| **Gộp 4 nhánh kênh đăng ký** | **Exclusive XOR – Gộp nhánh** | Gộp 4 nhánh đầu ra GW1: Website, Hotline, cửa hàng giao dịch, nhân viên kinh doanh → trước bước **"Gửi yêu cầu và thông tin đăng ký"**. |
| **Gộp luồng tư vấn lần đầu và luồng làm rõ nhu cầu** | **Exclusive XOR – Gộp nhánh** | Gộp luồng tư vấn lần đầu và luồng làm rõ nhu cầu (vòng lặp GW2 – nhánh "Chưa xác nhận") → trước bước **"Nhận tư vấn gói cước"**. |
| **Gộp hồ sơ gửi lần đầu và hồ sơ đã bổ sung** | **Exclusive XOR – Gộp nhánh** | Gộp hồ sơ gửi lần đầu và hồ sơ đã bổ sung → trước bước **"Nhận đề nghị xác nhận lịch lắp đặt"**. |
| **Gộp hai hình thức ký hợp đồng** | **Exclusive XOR – Gộp nhánh** | Gộp hai hình thức ký hợp đồng (đầu ra GW7: ký điện tử / ký giấy) → trước bước **"Gửi hợp đồng đã ký"**. |
| **Gộp hai nhánh "Không" của GW3 và GW4** | **Exclusive XOR – Gộp nhánh** | Gộp hai nhánh "Không" của GW3 và GW4 (hạ tầng không đáp ứng / không có Port khả dụng) → trước bước **"Thông báo không đủ điều kiện cho khách hàng"**. |
| **Gộp hồ sơ khách hàng gửi lần đầu và hồ sơ gửi lại sau khi bổ sung** | **Exclusive XOR – Gộp nhánh** | Gộp hồ sơ khách hàng gửi lần đầu và hồ sơ gửi lại sau khi bổ sung (vòng lặp GW5 – nhánh "Không") → trước bước **"Nhận hồ sơ khách hàng"**. |


#### **3.4.2.2. Diễn giải chi tiết các luồng quy trình**

##### **1. Luồng chính – Happy Path:**
| STT | Thành phần | Nội dung |
|---|---|---|
| **1** | **Customer** | Phát sinh nhu cầu → **GW1** chọn một kênh đăng ký → cung cấp thông tin. |
| **2** | **Sales** | Tiếp nhận, kiểm tra thông tin → tư vấn gói cước. |
| **3** | **GW2** | Khách hàng **đã xác nhận** gói cước/nhu cầu → Sales lập hồ sơ đăng ký sơ bộ. |
| **4** | **Technical** | Tiếp nhận yêu cầu → kiểm tra hạ tầng cáp quang. |
| **5** | **GW3** | Hạ tầng **đáp ứng** → Technical kiểm tra Port. |
| **6** | **GW4** | **Có Port khả dụng** → xác nhận đủ điều kiện kỹ thuật. |
| **7** | **Sales / Customer** | Sales yêu cầu hoàn thiện hồ sơ → Customer gửi hồ sơ → Sales kiểm tra. |
| **8** | **GW5** | Hồ sơ **đầy đủ và hợp lệ** → chuyển sang xác nhận lịch. |
| **9** | **Sales / Customer** | Sales đề nghị xác nhận lịch → Customer phản hồi. |
| **10** | **GW6** | Lịch **đã được xác nhận** → Sales gửi hợp đồng. |
| **11** | **GW7** | Customer chọn **một** hình thức ký: điện tử hoặc giấy → hợp đồng đạt trạng thái đã ký. |
| **12** | **Sales / BPMS/CRM** | Sales tiếp nhận hợp đồng đã ký → chuyển dữ liệu vào hệ thống → BPMS/CRM ghi nhận hợp đồng → tạo Work Order → phân công đội kỹ thuật khu vực → cập nhật trạng thái. |
| **13** | **End Event** | Yêu cầu chuyển sang giai đoạn triển khai lắp đặt. |

##### **2. Luồng phụ**
| Luồng phụ                                         | Gateway | Điều kiện / Trạng thái     | Nội dung xử lý                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------- | ------- | -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Khách hàng chưa xác nhận gói cước/nhu cầu**  | **GW2** | **Chưa xác nhận**          | 1. Sales đã thực hiện tư vấn gói cước.<br>2. Tại **GW2**, trạng thái là **“Chưa xác nhận”**.<br>3. Quy trình **chưa lập hồ sơ đăng ký sơ bộ** và chưa chuyển sang Technical.<br>4. Sales tiếp tục tư vấn và làm rõ nhu cầu; khi khách hàng xác nhận, luồng quay lại GW2 và chuyển sang bước lập hồ sơ đăng ký sơ bộ.                  |
| **2. Hạ tầng cáp quang không đáp ứng**            | **GW3** | **Không đáp ứng**          | 1. Technical kiểm tra hạ tầng cáp quang.<br>2. Tại **GW3**, kết quả là **“Không đáp ứng”**.<br>3. Kết quả được phản hồi để Sales thông báo khách hàng rằng yêu cầu chưa thể triển khai.<br>4. Quy trình kết thúc; không tạo Work Order.                                                                                               |
| **3. Không có Port khả dụng**                     | **GW4** | **Không có Port khả dụng** | 1. Sau khi hạ tầng đáp ứng, Technical kiểm tra Port.<br>2. Tại **GW4**, kết quả là **“Không có Port khả dụng”**.<br>3. Yêu cầu được xác định chưa đủ điều kiện kỹ thuật; Sales thông báo khách hàng.<br>4. Quy trình kết thúc; không tạo Work Order.                                                                                  |
| **4. Hồ sơ thiếu hoặc chưa hợp lệ (Rework Loop)** | **GW5** | **Không**                  | 1. Customer gửi hồ sơ đăng ký.<br>2. Sales kiểm tra tính đầy đủ và hợp lệ.<br>3. Tại **GW5**, kết quả là **“Không”** → Sales yêu cầu bổ sung/chỉnh sửa.<br>4. Customer bổ sung/chỉnh sửa và gửi lại hồ sơ.<br>5. Sales kiểm tra lại → quay về **GW5**.<br>6. Chỉ khi GW5 = **“Có”**, quy trình mới chuyển sang xác nhận lịch lắp đặt. |
| **5. Khách hàng chưa xác nhận lịch lắp đặt**      | **GW6** | **Chưa xác nhận**          | 1. Sales đề nghị khách hàng xác nhận lịch.<br>2. Tại **GW6**, trạng thái là **“Chưa xác nhận”**.<br>3. Quy trình chưa chuyển sang gửi/ký hợp đồng và tiếp tục ở trạng thái chờ/xác nhận lịch.<br>4. Sales tiếp tục phối hợp xác nhận lịch; khi khách hàng chốt lịch, luồng quay lại GW6 và chuyển sang bước gửi hợp đồng.             |


##### **3. Luồng biến thể – GW1 và GW7:**

| Gateway | Nội dung |
|---|---|
| **GW1** | Một yêu cầu có thể đi vào từ Website, Hotline, cửa hàng hoặc nhân viên kinh doanh; khác biệt chỉ nằm ở cách thông tin đầu vào được tiếp nhận. Các nhánh hội tụ trước xử lý của Sales. |
| **GW7** | Khách hàng ký điện tử hoặc ký giấy; cả hai nhánh hội tụ tại trạng thái **“Hợp đồng đã ký”** rồi tiếp tục qua BPMS/CRM. |
---
### **3.4.3. Phân tích định tính**

#### **3.4.3.1. Phân tích giá trị gia tăng**

![Hình 3.4.2. Mô hình hóa phân tích giá trị gia tăng](./docs/Mo%20hinh%20hoa%20Quy%20trinh%20phan%20tich%20gia%20tri%20gia%20tang.png)

Phân tích giá trị gia tăng phân loại các hoạt động theo ba nhóm:

* **VA (Value-Added):** Tạo giá trị trực tiếp cho khách hàng hoặc trực tiếp xác lập dịch vụ khách hàng lựa chọn.
* **BVA (Business Value-Added):** Không tạo giá trị cảm nhận trực tiếp nhưng cần thiết cho vận hành, kiểm soát hoặc tính hợp lệ của giao dịch.
* **NVA (Non-Value-Added):** Không làm tăng giá trị đầu ra, thường liên quan chuyển giao, tiếp nhận lặp lại hoặc xử lý lại và cần được giảm thiểu.

Các nhánh thay thế cùng thực hiện một mục đích nghiệp vụ và hội tụ về cùng luồng xử lý tiếp theo được phân tích như một hoạt động logic. Các thao tác gửi/nhận nằm trong cùng một tương tác nghiệp vụ được gộp khi không tạo thành một công đoạn xử lý độc lập. Điểm khởi tạo “Phát sinh nhu cầu sử dụng dịch vụ Internet” là sự kiện kích hoạt quy trình và không tính trong tỷ lệ VA/BVA/NVA.

| STT | Hoạt động | Người thực hiện | Phân loại | Lập luận theo tiêu chuẩn phân loại |
| :---: | :--- | :--- | :---: | :--- |
| 1 | Lựa chọn kênh đăng ký | Customer | **BVA** | Cần để yêu cầu đi vào kênh tiếp nhận phù hợp, nhưng bản thân việc lựa chọn kênh không trực tiếp tạo giá trị cho dịch vụ. |
| 2 | Cung cấp/gửi thông tin đăng ký | Customer | **BVA** | Dữ liệu bắt buộc để nhận diện khách hàng, địa chỉ lắp đặt và nhu cầu sử dụng. |
| 3 | Tiếp nhận, kiểm tra và ghi nhận thông tin | Sales | **BVA** | Cần cho kiểm soát đầu vào và điều phối yêu cầu trong quy trình. |
| 4 | Tư vấn gói cước và làm rõ nhu cầu | Sales | **VA** | Trực tiếp giúp khách hàng xác định gói dịch vụ phù hợp với nhu cầu sử dụng. |
| 5 | Xác nhận gói cước / nhu cầu sử dụng | Customer | **VA** | Xác lập lựa chọn dịch vụ mà khách hàng mong muốn. |
| 6 | Lập hồ sơ đăng ký sơ bộ | Sales | **BVA** | Cần để hình thành thông tin nghiệp vụ phục vụ kiểm tra khả năng cung cấp dịch vụ. |
| 7 | Chuyển yêu cầu kiểm tra kỹ thuật | Sales | **NVA** | Chuyển giao nội bộ không làm tăng giá trị đầu ra và có thể được tự động hóa. |
| 8 | Tiếp nhận yêu cầu kiểm tra | Technical | **NVA** | Thao tác tiếp nhận nội bộ không trực tiếp tạo thêm giá trị và có thể giảm bằng tích hợp hệ thống. |
| 9 | Kiểm tra hạ tầng cáp quang | Technical | **BVA** | Điều kiện kỹ thuật cần thiết để tránh cam kết dịch vụ khi hạ tầng không đáp ứng. |
| 10 | Kiểm tra cổng kết nối (Port) | Technical | **BVA** | Điều kiện kỹ thuật bắt buộc để xác định khả năng cấp dịch vụ tại địa chỉ đăng ký. |
| 11 | Thông báo không đủ điều kiện cho khách hàng | Sales | **BVA** | Cần để phản hồi kết quả kiểm tra kỹ thuật và đóng yêu cầu đúng trạng thái. |
| 12 | Yêu cầu khách hàng hoàn thiện hồ sơ | Sales | **BVA** | Hướng dẫn khách hàng cung cấp đủ thông tin và giấy tờ cần thiết cho giao dịch. |
| 13 | Hoàn thiện/cung cấp hồ sơ lần đầu | Customer | **BVA** | Cần để kiểm tra tính hợp lệ, ký hợp đồng và tạo Work Order. |
| 14 | Nhận hồ sơ khách hàng | Sales | **NVA** | Thao tác tiếp nhận/chuyển hồ sơ không làm tăng giá trị đầu ra và có thể được số hóa. |
| 15 | Kiểm tra tính đầy đủ, hợp lệ của hồ sơ | Sales | **BVA** | Kiểm soát chất lượng và tính hợp lệ của hồ sơ trước khi ký hợp đồng. |
| 16 | Yêu cầu bổ sung/chỉnh sửa hồ sơ | Sales | **NVA** | Phát sinh khi hồ sơ chưa đạt yêu cầu và tạo thêm một vòng xử lý lại. |
| 17 | Bổ sung/chỉnh sửa và gửi lại hồ sơ | Customer | **NVA** | Rework phát sinh do hồ sơ chưa đúng hoặc chưa đủ ngay lần đầu. |
| 18 | Xác nhận/chốt lịch lắp đặt | Sales / Customer | **VA** | Xác lập thời điểm cung cấp dịch vụ phù hợp với nhu cầu và khả năng phối hợp của khách hàng. |
| 19 | Ký hợp đồng điện tử hoặc giấy | Customer | **BVA** | Điều kiện pháp lý/nghiệp vụ để chính thức hóa đăng ký dịch vụ. |
| 20 | Ghi nhận hợp đồng trên BPMS/CRM | BPMS/CRM | **BVA** | Cần để lưu giao dịch và kích hoạt các công việc tiếp theo trên hệ thống. |
| 21 | Tạo Work Order | BPMS/CRM | **BVA** | Chuyển yêu cầu hợp lệ thành lệnh triển khai chính thức. |
| 22 | Phân công đội kỹ thuật khu vực | BPMS/CRM | **BVA** | Cần để Work Order có đơn vị chịu trách nhiệm thực hiện. |
| 23 | Cập nhật trạng thái và chuyển sang triển khai | BPMS/CRM | **BVA** | Cần cho quản trị, truy vết và chuyển giao yêu cầu sang giai đoạn triển khai lắp đặt. |

**Tổng hợp phân loại:**

| Loại giá trị | Số hoạt động | Tỷ lệ |
| :---: | :---: | :---: |
| **VA** | 3 | **13,04%** |
| **BVA** | 15 | **65,22%** |
| **NVA** | 5 | **21,74%** |
| **Tổng** | **23** | **100%** |

> **Nhận xét:** BVA chiếm tỷ trọng lớn do quy trình có nhiều hoạt động kiểm soát điều kiện kỹ thuật, hồ sơ, hợp đồng và lệnh triển khai. NVA tập trung ở chuyển giao nội bộ, tiếp nhận hồ sơ và vòng bổ sung/chỉnh sửa. VA tập trung tại tư vấn dịch vụ, xác nhận nhu cầu và chốt lịch lắp đặt.
---

#### **3.4.3.2. Phân tích lãng phí**

![Hình 3.4.3. Mô hình hóa Phân tích lãng phí](./docs/Mo%20hinh%20hoa%20Quy%20trinh%20phan%20tich%20lang%20phi.png)

Phân tích lãng phí theo Lean tập trung vào các điểm chờ trước khi một yêu cầu được xử lý, các bước chuyển giao giữa các tác nhân, thao tác xử lý lặp lại và lượng công việc tồn đọng trong quá trình đăng ký dịch vụ. Bảy nhóm lãng phí được đánh giá như sau:

| Loại lãng phí Lean | Biểu hiện trong quy trình |
| :--- | :--- |
| **Waiting (Chờ đợi)** | Yêu cầu đăng ký có thể chờ trước khi được Sales tiếp nhận và xử lý; yêu cầu kiểm tra có thể chờ trước khi được Technical tiếp nhận; yêu cầu tiếp tục chờ trong quá trình kiểm tra hạ tầng/Port, hoàn thiện hồ sơ, ký hợp đồng hoặc trước khi Work Order được tạo và phân công. |
| **Transportation / Handoff (Chuyển giao)** | Yêu cầu và dữ liệu được chuyển qua nhiều điểm Customer → Sales → Technical → Sales → BPMS/CRM. Các bước chuyển giao thủ công có thể làm tăng độ trễ và nguy cơ sai lệch thông tin. |
| **Over-processing (Xử lý thừa)** | Cùng một thông tin có thể phải được tra cứu, xác nhận hoặc kiểm tra lại ở nhiều công đoạn khi dữ liệu giữa các kênh tiếp nhận, Technical và BPMS/CRM chưa được liên thông đầy đủ. |
| **Defects / Rework (Lỗi và làm lại)** | Hồ sơ thiếu, sai hoặc chưa hợp lệ làm phát sinh yêu cầu bổ sung/chỉnh sửa, gửi lại hồ sơ và kiểm tra lại trước khi quy trình có thể tiếp tục. |
| **Over-production (Xử lý trước nhu cầu)** | Không ghi nhận là lãng phí trọng tâm trong luồng As-Is; Work Order chỉ được tạo sau khi hoàn tất các điều kiện đăng ký, kiểm tra kỹ thuật, hồ sơ và hợp đồng. |
| **Inventory / Backlog (Tồn đọng công việc)** | Các yêu cầu chưa được Sales hoặc Technical tiếp nhận, các yêu cầu đang chờ kết quả kiểm tra hoặc chờ khách hàng hoàn thiện hồ sơ/ký hợp đồng có thể tích tụ thành hàng đợi công việc và làm tăng Cycle Time. |
| **Motion (Thao tác không cần thiết)** | Phát sinh khi nhân sự phải tra cứu ở nhiều nguồn, xác nhận lại hoặc nhập lại cùng một thông tin do dữ liệu giữa kênh tiếp nhận, Technical và BPMS/CRM chưa được liên thông xuyên suốt. |



**Định hướng cải tiến từ phân tích lãng phí:**

* Chuẩn hóa và kiểm tra dữ liệu đầu vào ngay tại điểm tiếp nhận.
* Tích hợp các kênh Website/Hotline/cửa hàng/Sales vào nguồn dữ liệu dùng chung.
* Tự động chuyển yêu cầu đủ thông tin sang Technical và ghi nhận thời điểm bắt đầu chờ để kiểm soát hàng đợi.
* Đồng bộ kết quả kiểm tra hạ tầng và Port về BPMS/CRM để giảm thời gian chờ và thao tác chuyển giao.
* Sử dụng checklist hồ sơ và validation bắt buộc để tăng tỷ lệ hồ sơ đúng ngay lần đầu và giảm Rework.
* Thông báo trạng thái tự động cho Customer/Sales để giảm thao tác hỏi–đáp, xác nhận lại và theo dõi thủ công.
* Theo dõi số lượng yêu cầu tồn, thời gian chờ trước từng công đoạn và số vòng Rework để nhận diện bottleneck.

---

#### **3.4.3.3. Phân tích các bên liên quan (Stakeholder Analysis)**

| Bên liên quan | Mức độ ảnh hưởng | Vai trò & kỳ vọng | Rủi ro khi quy trình không hiệu quả |
| :--- | :---: | :--- | :--- |
| **Khách hàng** | **Rất cao** | Được tư vấn đúng; biết sớm khả năng triển khai; thủ tục đơn giản; lịch lắp đặt rõ ràng. | Chờ lâu, cung cấp lại thông tin, trải nghiệm kém, có thể từ bỏ đăng ký. |
| **Sales** | **Rất cao** | Tiếp nhận và điều phối nhanh; hồ sơ đạt chuẩn; có trạng thái rõ để theo dõi. | Quá tải thao tác, nhiều Rework, mất thời gian theo dõi/chuyển giao. |
| **Technical** | **Rất cao** | Nhận đủ dữ liệu để kiểm tra; truy cập được thông tin hạ tầng/Port chính xác. | Kiểm tra chậm hoặc trả kết quả sai, gây cam kết sai khả năng cung cấp. |
| **BPMS/CRM** | **Rất cao** | Dữ liệu nhất quán; tạo/phân công Work Order đúng trạng thái. | Sai dữ liệu, tạo đơn chậm/trùng, khó truy vết tiến độ. |
| **Đội kỹ thuật khu vực** | **Cao** | Nhận Work Order có đủ thông tin và lịch lắp đặt để triển khai. | Phải xác minh lại, đổi lịch, giảm hiệu suất thi công. |
| **Bộ phận quản lý vận hành** | **Cao** | Theo dõi SLA, tỷ lệ chuyển đổi, Rework và bottleneck của quy trình. | Thiếu dữ liệu để đánh giá hiệu suất và ưu tiên cải tiến. |

---

### **3.4.4. Phân tích định lượng**

![Hình 3.4.4. Mô hình hóa Phân tích định lượng](./docs/Quy_trinh_Tu_Van_Lap_Dat_Phan_tich_dinh_luong.png)

Phân tích định lượng sử dụng cách tiếp cận **Cycle Time (CT) – Processing Time (PT)** kết hợp xác suất tại các cổng quyết định để lượng hóa thời gian chu kỳ, thời gian xử lý thực tế, hiệu quả chu kỳ, chi phí xử lý và tỷ lệ đạt ngay lần đầu của một yêu cầu đăng ký. Trong mô hình này, **CT** phản ánh tổng thời gian trôi qua của yêu cầu, bao gồm cả thời gian chờ và phản hồi; **PT** chỉ phản ánh thời gian nguồn lực nội bộ của FPT Telecom thực sự xử lý. Thời gian khách hàng tự thao tác hoặc chờ khách hàng phản hồi vẫn được tính trong CT nhưng không tính vào PT nội bộ. Gateway không cộng thời gian riêng mà chỉ quyết định xác suất đi tiếp, kết thúc hoặc lặp lại.

Các số liệu dưới đây là giả định phục vụ mô hình phân tích quy trình As-Is và được sử dụng thống nhất trong toàn bộ phép tính.

#### **3.4.4.1. Giả định thời gian và xác suất từng bước**

**Thời gian CT và PT của các hoạt động:**

| Ký hiệu | Hoạt động | Tác nhân | CT (phút) | PT (phút) | Ghi chú |
| :---: | :--- | :--- | ---: | ---: | :--- |
| **t1** | Lựa chọn kênh và cung cấp thông tin đăng ký ban đầu | Customer | 10 | 0 | Thời gian phía khách hàng; không tính vào PT nội bộ. |
| **t2** | Sales tiếp nhận, kiểm tra thông tin và tư vấn gói cước | Sales | 60 | 25 | CT bao gồm thời gian yêu cầu chờ được tiếp nhận và phản hồi. |
| **r2** | Tiếp tục tư vấn/làm rõ nhu cầu khi khách hàng chưa xác nhận tại GW2 | Sales / Customer | 30 | 10 | Vòng lặp, chỉ phát sinh khi GW2 = “Chưa xác nhận”. |
| **t3** | Lập hồ sơ đăng ký sơ bộ và chuyển yêu cầu sang Technical | Sales | 15 | 10 | Bao gồm thao tác lập hồ sơ và chuyển giao nội bộ. |
| **t4** | Technical tiếp nhận và kiểm tra hạ tầng cáp quang | Technical | 90 | 30 | CT bao gồm thời gian chờ hàng đợi và thời gian kiểm tra thực tế. |
| **t5** | Thông báo khách hàng khi hạ tầng không đáp ứng | Sales | 10 | 5 | Nhánh kết thúc tại GW3. |
| **t6** | Kiểm tra Port khả dụng | Technical | 15 | 10 | Chỉ thực hiện khi hạ tầng đáp ứng. |
| **t7** | Thông báo khách hàng khi không có Port khả dụng | Sales | 10 | 5 | Nhánh kết thúc tại GW4. |
| **t8** | Yêu cầu và chờ khách hàng hoàn thiện hồ sơ đăng ký | Sales / Customer | 60 | 5 | Phần lớn CT là thời gian khách hàng chuẩn bị/gửi hồ sơ. |
| **t9** | Kiểm tra tính đầy đủ, hợp lệ của hồ sơ | Sales | 15 | 15 | Lần kiểm tra đầu tiên. |
| **r5** | Bổ sung/chỉnh sửa và kiểm tra lại hồ sơ | Sales / Customer | 60 | 20 | Vòng lặp khi GW5 = “Không”. |
| **t10** | Đề nghị, phối hợp và xác nhận lịch lắp đặt | Sales / Customer | 45 | 10 | Lần xác nhận đầu tiên. |
| **r6** | Phối hợp lại lịch khi khách hàng chưa xác nhận | Sales / Customer | 30 | 5 | Vòng lặp khi GW6 = “Chưa xác nhận”. |
| **t11e** | Gửi và ký hợp đồng điện tử | Sales / Customer | 15 | 5 | Nhánh ký điện tử tại GW7. |
| **t11p** | Gửi và ký hợp đồng giấy | Sales / Customer | 60 | 10 | Nhánh ký giấy tại GW7. |
| **t12** | Ghi nhận hợp đồng, tạo Work Order, phân công và cập nhật trạng thái | BPMS/CRM | 15 | 10 | Chỉ phát sinh với yêu cầu vượt qua điều kiện kỹ thuật. |

**Xác suất tại các cổng quyết định:**

| Gateway | Điều kiện | Xác suất | Cách xử lý trong mô hình |
| :---: | :--- | ---: | :--- |
| **GW1** | Kênh đăng ký | — | Không cộng thời gian gateway riêng; ảnh hưởng của kênh đã được gộp trong t1–t2. |
| **GW2** | Khách hàng xác nhận gói cước/nhu cầu ngay lần đầu | **85%** | 15% còn lại phát sinh vòng lặp r2 cho đến khi xác nhận. |
| **GW3** | Hạ tầng cáp quang đáp ứng | **90%** | 10% kết thúc tại t5; 90% đi tiếp sang kiểm tra Port. |
| **GW4** | Có Port khả dụng | **95%** | 5% kết thúc tại t7; 95% đi tiếp sang hoàn thiện hồ sơ. |
| **GW5** | Hồ sơ đầy đủ, hợp lệ ngay lần đầu | **80%** | 20% phát sinh vòng lặp r5 cho đến khi hồ sơ hợp lệ. |
| **GW6** | Khách hàng xác nhận lịch ngay lần đầu | **90%** | 10% phát sinh vòng lặp r6 cho đến khi chốt được lịch. |
| **GW7** | Hình thức ký hợp đồng | **70% điện tử / 30% giấy** | Hai nhánh đều hợp lệ và hội tụ về cùng bước ghi nhận hợp đồng. |

Với các gateway tạo vòng lặp, số vòng xử lý lại kỳ vọng được tính theo:

`E(Số vòng Rework) = q / p`

trong đó `p` là xác suất đạt tại một lần kiểm tra/xác nhận và `q = 1 - p`. Do đó, phần thời gian tăng thêm do Rework được tính bằng:

`E(T_rework) = (q / p) × T_rework_mỗi_vòng`

Đối với các cổng có nhánh kết thúc, thời gian được tính theo xác suất có trọng số theo cấu trúc:

`Lvl(n) = Test(n) + p_kết_thúc × End(n) + p_đi_tiếp × Lvl(n+1)`

#### **3.4.4.2. Định lượng thời gian**

**a) Thời gian chu kỳ kỳ vọng (Cycle Time)**

Tính từ trong ra ngoài theo cấu trúc các cổng quyết định của quy trình.

Phần sau khi vượt qua GW4:

`Lvl_HS = t8 + t9 + (0,20 / 0,80) × r5 + t10 + (0,10 / 0,90) × r6 + (0,70 × t11e + 0,30 × t11p) + t12`

`Lvl_HS = 60 + 15 + (0,20 / 0,80) × 60 + 45 + (0,10 / 0,90) × 30 + (0,70 × 15 + 0,30 × 60) + 15`

`Lvl_HS ≈ 181,83 phút`

Tại GW4:

`Lvl_GW4 = t6 + 0,05 × t7 + 0,95 × Lvl_HS`

`Lvl_GW4 = 15 + 0,05 × 10 + 0,95 × 181,83 ≈ 188,24 phút`

Tại GW3:

`Lvl_GW3 = t4 + 0,10 × t5 + 0,90 × Lvl_GW4`

`Lvl_GW3 = 90 + 0,10 × 10 + 0,90 × 188,24 ≈ 260,42 phút`

Toàn bộ quy trình:

`Tct = t1 + t2 + (0,15 / 0,85) × r2 + t3 + Lvl_GW3`

`Tct = 10 + 60 + (0,15 / 0,85) × 30 + 15 + 260,42`

`Tct ≈ 350,71 phút ≈ 5,85 giờ ≈ 5 giờ 51 phút`

Như vậy, **Cycle Time kỳ vọng của một yêu cầu đầu vào là khoảng 350,71 phút**. Kết quả này đã phản ánh xác suất yêu cầu bị kết thúc sớm tại GW3/GW4, xác suất phát sinh xử lý lại tại GW2/GW5/GW6 và tỷ trọng hai hình thức ký hợp đồng tại GW7.

**b) Thời gian xử lý thực tế (Processing Time)**

PT được tính theo đúng cấu trúc xác suất như CT, nhưng chỉ lấy phần thời gian nguồn lực nội bộ thực sự xử lý. Thời gian khách hàng tự chuẩn bị, phản hồi hoặc chờ đợi không được cộng vào PT.

Phần sau khi vượt qua GW4:

`Lvl_HS_PT = 5 + 15 + (0,20 / 0,80) × 20 + 10 + (0,10 / 0,90) × 5 + (0,70 × 5 + 0,30 × 10) + 10`

`Lvl_HS_PT ≈ 52,06 phút`

Tại GW4:

`Lvl_GW4_PT = 10 + 0,05 × 5 + 0,95 × 52,06 ≈ 59,70 phút`

Tại GW3:

`Lvl_GW3_PT = 30 + 0,10 × 5 + 0,90 × 59,70 ≈ 84,23 phút`

Toàn bộ quy trình:

`Tpt = 0 + 25 + (0,15 / 0,85) × 10 + 10 + 84,23`

`Tpt ≈ 121,00 phút ≈ 2,02 giờ`

**c) Độ hiệu quả của chu kỳ (Process Cycle Efficiency – PCE)**

Công thức:

`PCE = Processing Time / Cycle Time × 100%`

`PCE = 121,00 / 350,71 × 100% ≈ 34,50%`

Thời gian không trực tiếp tạo ra hoạt động xử lý nội bộ:

`Waiting/Non-processing Time = 350,71 - 121,00 = 229,71 phút`

Tỷ trọng thời gian chờ và không xử lý trực tiếp:

`229,71 / 350,71 × 100% ≈ 65,50%`

| Chỉ tiêu | Kết quả |
| :--- | ---: |
| **Cycle Time kỳ vọng** | **350,71 phút (≈ 5,85 giờ)** |
| **Processing Time kỳ vọng** | **121,00 phút (≈ 2,02 giờ)** |
| **Waiting/Non-processing Time** | **229,71 phút** |
| **Process Cycle Efficiency (PCE)** | **34,50%** |
| **Tỷ trọng thời gian chờ/không xử lý** | **65,50%** |

> **Nhận xét:** PCE khoảng **34,50%** cho thấy phần lớn thời gian chu kỳ nằm ở thời gian chờ, phản hồi và chuyển giao. Cụm kiểm tra kỹ thuật có CT lớn do bao gồm hàng đợi trước khi Technical xử lý; các vòng lặp hồ sơ và xác nhận lịch tiếp tục làm tăng thời gian chu kỳ dù thời gian xử lý nội bộ tăng không nhiều. Vì vậy, ưu tiên cải tiến nên tập trung vào giảm thời gian chờ trước Technical, tăng tỷ lệ hồ sơ hợp lệ ngay lần đầu và rút ngắn thời gian phản hồi/xác nhận với khách hàng.

---

#### **3.4.4.3. Định lượng chi phí**

**Đơn giá nguồn lực quy đổi:**

| Tác nhân / nguồn lực | Đơn giá quy đổi | Chi phí/phút |
| :--- | ---: | ---: |
| **Sales** | 50.000 VNĐ/giờ | **833,33 VNĐ/phút** |
| **Technical** | 60.000 VNĐ/giờ | **1.000 VNĐ/phút** |
| **BPMS/CRM** | 55.000 VNĐ/giờ | **916,67 VNĐ/phút** |

Thời gian của Customer không được tính vào chi phí lao động nội bộ. Chi phí được tính trên **PT kỳ vọng** của từng tác nhân và theo cùng cấu trúc xác suất của Cycle Time.

**PT kỳ vọng theo tác nhân:**

`PT_Sales = 25 + (0,15 / 0,85) × 10 + 10 + 0,10 × 5 + 0,90 × [0,05 × 5 + 0,95 × (5 + 15 + (0,20 / 0,80) × 20 + 10 + (0,10 / 0,90) × 5 + (0,70 × 5 + 0,30 × 10))]`

`PT_Sales ≈ 73,45 phút`

`PT_Technical = 30 + 0,90 × 10 = 39,00 phút`

`PT_BPMS/CRM = 0,90 × 0,95 × 10 = 8,55 phút`

Tổng PT nội bộ:

`73,45 + 39,00 + 8,55 = 121,00 phút`

**Chi phí xử lý kỳ vọng trên một yêu cầu đầu vào:**

| Tác nhân | PT kỳ vọng | Đơn giá/phút | Chi phí kỳ vọng | Tỷ trọng |
| :--- | ---: | ---: | ---: | ---: |
| **Sales** | 73,45 phút | 833,33 VNĐ | **61.206 VNĐ** | **56,65%** |
| **Technical** | 39,00 phút | 1.000 VNĐ | **39.000 VNĐ** | **36,10%** |
| **BPMS/CRM** | 8,55 phút | 916,67 VNĐ | **7.838 VNĐ** | **7,25%** |
| **Tổng** | **121,00 phút** |  | **108.044 VNĐ/yêu cầu** | **100%** |

Công thức tổng quát:

`Cost = Σ(PT_kỳ_vọng_theo_tác_nhân × Đơn_giá_tác_nhân)`

`Cost ≈ 108.044 VNĐ/yêu cầu`

> **Nhận xét:** Sales chiếm khoảng **56,65%** chi phí xử lý nội bộ do tham gia xuyên suốt từ tiếp nhận, tư vấn, lập hồ sơ, xử lý Rework, điều phối lịch đến hợp đồng. Technical chiếm khoảng **36,10%**, tập trung ở kiểm tra hạ tầng và Port. Do đó, tự động hóa chuyển giao, tăng kiểm tra dữ liệu đầu vào và giảm Rework ở hồ sơ có khả năng tác động trực tiếp đến cả chi phí xử lý và Cycle Time.

---

#### **3.4.4.4. Định lượng chất lượng – First Pass Yield**

First Pass Yield phản ánh tỷ lệ yêu cầu có thể đi qua các điểm kiểm soát chính **ngay lần đầu**, không phát sinh vòng lặp tại GW2/GW5/GW6 và không bị kết thúc do không đủ điều kiện kỹ thuật tại GW3/GW4.

Các tỷ lệ sử dụng:

| Chỉ tiêu | Tỷ lệ đạt ngay lần đầu |
| :--- | ---: |
| Khách hàng xác nhận gói cước/nhu cầu tại GW2 | **85%** |
| Hạ tầng đáp ứng tại GW3 | **90%** |
| Có Port khả dụng tại GW4 | **95%** |
| Hồ sơ đầy đủ, hợp lệ tại GW5 | **80%** |
| Khách hàng xác nhận lịch tại GW6 | **90%** |

GW7 không đưa vào phép nhân RFPY vì ký điện tử và ký giấy là hai **nhánh lựa chọn hợp lệ**, không phải quan hệ đạt/không đạt.

Công thức:

`RFPY = 0,85 × 0,90 × 0,95 × 0,80 × 0,90`

`RFPY ≈ 0,52326 = 52,33%`

Như vậy, **khoảng 52,33% yêu cầu có thể đi qua toàn bộ các điểm kiểm soát chính ngay lần đầu theo mô hình giả định**. Riêng xác suất một yêu cầu vượt qua hai điều kiện kỹ thuật GW3 và GW4 là:

`0,90 × 0,95 = 85,50%`

> **Nhận xét & đề xuất:** RFPY khoảng **52,33%** cho thấy dư địa cải thiện lớn nhất nằm ở các điểm có khả năng phát sinh xử lý lại, đặc biệt là tính đầy đủ/hợp lệ của hồ sơ tại GW5 và xác nhận của khách hàng tại GW2, GW6. Việc sử dụng biểu mẫu có kiểm tra dữ liệu bắt buộc, đồng bộ thông tin giữa các kênh với BPMS/CRM, tự động chuyển yêu cầu sang Technical và tăng tỷ trọng ký điện tử sẽ giúp giảm thời gian chờ, giảm số vòng Rework, tăng PCE và giảm chi phí xử lý trên mỗi yêu cầu.

## **3.4.5. Kết luận**

Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom là quy trình đầu vào của chuỗi cung cấp dịch vụ. Quy trình có vai trò chuyển nhu cầu của khách hàng thành Work Order hợp lệ và đã phân công cho đội kỹ thuật khu vực. Mô hình BPMN As-Is gồm **13 bước nghiệp vụ**, **07 cổng quyết định Exclusive XOR (GW1–GW7)** và **06 cổng gộp nhánh**. Mô hình thể hiện rõ các điểm kiểm soát trước khi tạo lệnh triển khai: xác nhận gói cước, kiểm tra hạ tầng cáp quang, kiểm tra Port, kiểm tra hồ sơ, xác nhận lịch và ký hợp đồng. Nhờ vậy, chỉ những yêu cầu đủ điều kiện kỹ thuật và pháp lý mới được chuyển sang giai đoạn thi công.

### **3.4.5.1 Kết quả phân tích chính**

| Nhóm phân tích | Kết quả |
| :--- | :--- |
| **Giá trị gia tăng (23 hoạt động)** | VA 13,04% (3 hoạt động); BVA 65,22% (15 hoạt động); NVA 21,74% (5 hoạt động) |
| **Cycle Time kỳ vọng** | ≈ 350,71 phút (≈ 5,85 giờ) |
| **Processing Time kỳ vọng** | ≈ 121,00 phút (≈ 2,02 giờ) |
| **Process Cycle Efficiency (PCE)** | ≈ 34,50%; thời gian chờ/không xử lý chiếm ≈ 65,50% |
| **Chi phí xử lý nội bộ** | ≈ 108.044 VNĐ/yêu cầu (Sales 56,65%; Technical 36,10%; BPMS/CRM 7,25%) |
| **Rolled First Pass Yield (RFPY)** | ≈ 52,33% yêu cầu đi qua các điểm kiểm soát chính ngay lần đầu |

### **3.4.5.2. Các điểm nghẽn chính**

* **Thời gian chờ chiếm tỷ trọng lớn.** PCE chỉ đạt khoảng 34,50%, tức phần lớn Cycle Time là thời gian chờ, phản hồi và chuyển giao chứ không phải xử lý trực tiếp. Điểm nghẽn rõ nhất là hàng đợi trước khi Technical kiểm tra hạ tầng (CT 90 phút, PT 30 phút).
* **Rework và vòng lặp xác nhận.** Chỉ khoảng một nửa số yêu cầu đạt ngay lần đầu. Điểm yếu lớn nhất là tính hợp lệ của hồ sơ tại GW5 (80%), sau đó là xác nhận gói cước tại GW2 (85%) và xác nhận lịch tại GW6 (90%).
* **Chuyển giao và nhập liệu thủ công.** Các hoạt động NVA tập trung ở chuyển yêu cầu sang Technical, tiếp nhận hồ sơ và vòng bổ sung/chỉnh sửa. Nguyên nhân gốc là dữ liệu giữa các kênh tiếp nhận, Technical và BPMS/CRM chưa liên thông đầy đủ.
* **Chi phí dồn vào Sales.** Sales tham gia xuyên suốt từ tiếp nhận đến hợp đồng nên chịu tải xử lý và chi phí lớn nhất. Đây là nhóm chịu tác động trực tiếp từ Rework và thao tác thủ công.

### **3.4.5.3. Định hướng cải tiến cho quy trình**

1. Chuẩn hóa và kiểm tra dữ liệu đầu vào ngay tại điểm tiếp nhận, đồng thời tích hợp bốn kênh đăng ký vào một nguồn dữ liệu dùng chung.
2. Tự động chuyển yêu cầu đủ thông tin sang Technical, đồng bộ kết quả kiểm tra hạ tầng và Port về BPMS/CRM, và kiểm soát hàng đợi bằng mốc thời gian chờ.
3. Dùng checklist hồ sơ và validation bắt buộc để tăng tỷ lệ hồ sơ đúng ngay lần đầu, giảm số vòng Rework tại GW5.
4. Tăng tỷ trọng ký hợp đồng điện tử (hiện giả định 70%) để rút ngắn thời gian ký, vì ký giấy có CT gấp bốn lần ký điện tử (60 so với 15 phút).
5. Gửi thông báo trạng thái tự động cho Customer và Sales, đồng thời theo dõi các chỉ số vận hành: số yêu cầu tồn, thời gian chờ từng công đoạn, số vòng Rework, SLA và tỷ lệ chuyển đổi.

### **3.4.5.4. Kết luận chung**

Quy trình As-Is có cấu trúc kiểm soát chặt chẽ, giúp ngăn các yêu cầu chưa đủ điều kiện chuyển sang thi công. Tuy nhiên, hiệu quả vận hành còn hạn chế do thời gian chờ cao, tỷ lệ đạt ngay lần đầu thấp và mức độ liên thông dữ liệu chưa tối ưu. Trọng tâm cải tiến là **giảm thời gian chờ trước Technical, nâng tỷ lệ hồ sơ hợp lệ ngay lần đầu và tự động hóa chuyển giao giữa các kênh, Technical và BPMS/CRM**.
