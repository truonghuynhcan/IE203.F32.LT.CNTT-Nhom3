### 3.3. QUY TRÌNH TƯ VẤN, ĐĂNG KÝ VÀ TIẾP NHẬN YÊU CẦU LẮP ĐẶT INTERNET FPT TELECOM

#### 3.3.1. Mô tả quy trình

Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom bắt đầu khi khách hàng phát sinh nhu cầu sử dụng dịch vụ Internet hoặc các dịch vụ đi kèm. Khách hàng có thể gửi yêu cầu thông qua nhiều kênh như Website, Hotline, cửa hàng giao dịch hoặc nhân viên kinh doanh. Sau khi yêu cầu được ghi nhận, bộ phận Kinh doanh (Sales) tiếp nhận thông tin, tư vấn gói cước, lập hồ sơ đăng ký sơ bộ và phối hợp với bộ phận Kỹ thuật (Technical) để kiểm tra khả năng triển khai dịch vụ tại địa chỉ khách hàng. 

Ở giai đoạn khởi tạo, khách hàng lựa chọn kênh đăng ký và cung cấp các thông tin cần thiết, bao gồm thông tin liên hệ, địa chỉ lắp đặt và nhu cầu sử dụng dịch vụ. Đối với kênh Website, khách hàng chủ động nhập thông tin đăng ký. Đối với Hotline, cửa hàng giao dịch hoặc đăng ký thông qua nhân viên kinh doanh, thông tin được tiếp nhận trực tiếp bởi nhân sự phụ trách.

Sau khi tiếp nhận yêu cầu, Sales ghi nhận và kiểm tra các thông tin cơ bản của khách hàng, bao gồm họ tên, số điện thoại liên hệ, địa chỉ lắp đặt và nhu cầu sử dụng dịch vụ. Trên cơ sở đó, Sales tư vấn gói cước phù hợp. Khách hàng xác nhận gói cước và nhu cầu sử dụng trước khi Sales lập hồ sơ đăng ký sơ bộ.

Hồ sơ sơ bộ được chuyển sang Technical để kiểm tra khả năng cung cấp dịch vụ. Technical tiếp nhận yêu cầu, kiểm tra hạ tầng cáp quang tại khu vực lắp đặt, kiểm tra số lượng cổng kết nối (Port) còn khả dụng và đánh giá điều kiện cung cấp dịch vụ.

Kết quả kiểm tra kỹ thuật tạo ra hai hướng xử lý:

- **Không đủ điều kiện kỹ thuật:** Sales thông báo kết quả cho khách hàng và kết thúc yêu cầu do chưa thể triển khai dịch vụ.
- **Đủ điều kiện kỹ thuật:** Sales yêu cầu khách hàng hoàn thiện hồ sơ đăng ký và cung cấp các giấy tờ cần thiết.

Đối với trường hợp đủ điều kiện, khách hàng hoàn thiện hồ sơ và gửi lại cho Sales. Sales kiểm tra tính đầy đủ, hợp lệ của hồ sơ. Nếu hồ sơ còn thiếu hoặc chưa hợp lệ, Sales yêu cầu khách hàng bổ sung hoặc chỉnh sửa; hồ sơ sau khi hoàn thiện được gửi lại để kiểm tra. Vòng xử lý này được lặp lại cho đến khi hồ sơ đáp ứng yêu cầu.

Khi hồ sơ đầy đủ và hợp lệ, Sales đề nghị khách hàng xác nhận lịch lắp đặt. Sau khi nhận được xác nhận lịch, Sales gửi hợp đồng để khách hàng ký. Khách hàng ký hợp đồng bằng hình thức điện tử hoặc hợp đồng giấy và gửi lại hợp đồng đã ký.

Sales tiếp nhận hợp đồng đã ký và chuyển thông tin vào hệ thống BPMS/CRM. Hệ thống ghi nhận hợp đồng, tạo Work Order (đơn lắp đặt), phân công đơn cho đội kỹ thuật phụ trách khu vực và cập nhật trạng thái để chuyển sang giai đoạn triển khai.

Quy trình kết thúc khi Work Order đã được tạo, được phân công cho đội kỹ thuật khu vực và trạng thái yêu cầu đã được cập nhật trên hệ thống.

![Hình 3.1. Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom](./docs/Quy-trinh-tu-van-lap-dat.png)

*Hình 3.1. Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom*

---

#### 3.3.2. Phân tích quy trình

##### 3.3.2.1. Các tác nhân tham gia quy trình

**Khách hàng (Customer)**

Khách hàng là cá nhân hoặc doanh nghiệp có nhu cầu đăng ký sử dụng dịch vụ Internet FPT Telecom. Khách hàng khởi tạo nhu cầu, cung cấp thông tin, xác nhận gói cước, hoàn thiện hồ sơ, xác nhận lịch lắp đặt và ký hợp đồng.

Các hoạt động chính của khách hàng gồm:

- Phát sinh nhu cầu sử dụng dịch vụ.
- Lựa chọn kênh đăng ký.
- Cung cấp thông tin đăng ký.
- Xác nhận gói cước và nhu cầu sử dụng.
- Hoàn thiện, bổ sung hoặc chỉnh sửa hồ sơ khi được yêu cầu.
- Xác nhận lịch lắp đặt.
- Ký và gửi lại hợp đồng.

**Bộ phận Kinh doanh (Sales)**

Sales là đầu mối tiếp nhận và điều phối yêu cầu trong giai đoạn đăng ký. Bộ phận này kết nối khách hàng với Technical và hệ thống BPMS/CRM, đồng thời chịu trách nhiệm kiểm soát tính đầy đủ của thông tin trước khi chuyển yêu cầu sang giai đoạn triển khai.

Các hoạt động chính của Sales gồm:

- Tiếp nhận, kiểm tra và ghi nhận thông tin khách hàng.
- Tư vấn gói cước phù hợp.
- Tiếp nhận xác nhận gói cước và nhu cầu sử dụng.
- Lập hồ sơ đăng ký sơ bộ.
- Chuyển yêu cầu kiểm tra kỹ thuật.
- Thông báo kết quả trong trường hợp không đủ điều kiện triển khai.
- Yêu cầu khách hàng hoàn thiện hồ sơ.
- Tiếp nhận và kiểm tra tính đầy đủ, hợp lệ của hồ sơ.
- Yêu cầu bổ sung hoặc chỉnh sửa hồ sơ khi cần thiết.
- Đề nghị và tiếp nhận xác nhận lịch lắp đặt.
- Gửi hợp đồng cho khách hàng ký và tiếp nhận hợp đồng đã ký.
- Chuyển thông tin hợp đồng vào BPMS/CRM.

**Bộ phận Kỹ thuật (Technical)**

Technical chịu trách nhiệm xác định khả năng cung cấp dịch vụ tại địa chỉ đăng ký. Kết quả kiểm tra kỹ thuật là điều kiện đầu vào cho quyết định tiếp tục hoặc dừng quy trình.

Các hoạt động chính của Technical gồm:

- Tiếp nhận yêu cầu kiểm tra.
- Kiểm tra hạ tầng cáp quang.
- Kiểm tra số lượng cổng kết nối (Port).
- Đánh giá điều kiện cung cấp dịch vụ.
- Cập nhật kết quả kiểm tra để Sales tiếp tục xử lý.

**Hệ thống BPMS/CRM**

BPMS/CRM tiếp nhận dữ liệu sau khi hợp đồng đã được ký, quản lý Work Order và duy trì trạng thái xử lý của yêu cầu.

Các chức năng chính gồm:

- Ghi nhận hợp đồng đã ký.
- Tạo Work Order.
- Phân công Work Order cho đội kỹ thuật khu vực.
- Lưu trữ và cập nhật trạng thái yêu cầu.
- Chuyển yêu cầu sang giai đoạn triển khai lắp đặt.

##### 3.3.2.2. Khách hàng của quy trình

Khách hàng chính của quy trình là **khách hàng đăng ký dịch vụ Internet FPT Telecom**.

Kết quả của quy trình phải đáp ứng hai yêu cầu: xác định được khả năng triển khai tại địa chỉ đăng ký và hoàn tất các điều kiện cần thiết để chuyển yêu cầu sang giai đoạn lắp đặt. Đối với yêu cầu đủ điều kiện, đầu ra của quy trình là hồ sơ hợp lệ, hợp đồng đã ký và Work Order đã được tạo, phân công trên hệ thống.

##### 3.3.2.3. Giá trị mà quy trình mang lại

Quy trình tạo ra các giá trị chính sau:

- **Xác định đúng nhu cầu dịch vụ:** ghi nhận nhu cầu sử dụng, địa chỉ lắp đặt và gói cước phù hợp với khách hàng.
- **Xác định khả năng cung cấp dịch vụ:** kiểm tra hạ tầng cáp quang và Port trước khi cam kết triển khai.
- **Kiểm soát chất lượng hồ sơ:** bảo đảm thông tin và giấy tờ đáp ứng yêu cầu trước khi ký hợp đồng.
- **Giảm rủi ro triển khai:** hạn chế trường hợp tạo đơn khi địa chỉ chưa đủ điều kiện kỹ thuật hoặc hồ sơ chưa hợp lệ.
- **Chuẩn hóa phối hợp liên phòng ban:** xác định rõ trách nhiệm giữa Customer, Sales, Technical và BPMS/CRM.
- **Chuyển đổi yêu cầu thành đơn triển khai:** tạo Work Order và phân công đội kỹ thuật khu vực sau khi hoàn tất điều kiện đăng ký.

##### 3.3.2.4. Kết quả của quy trình

Quy trình có hai kết quả chính:

**Trường hợp 1 – Không đủ điều kiện triển khai**

Khi Technical xác định khu vực chưa đáp ứng điều kiện hạ tầng hoặc không còn Port phù hợp, kết quả được chuyển về Sales để phản hồi khách hàng. Quy trình kết thúc và không tạo Work Order.

**Trường hợp 2 – Đủ điều kiện triển khai**

Khi khu vực đáp ứng điều kiện kỹ thuật, khách hàng hoàn thiện hồ sơ; Sales kiểm tra tính đầy đủ và hợp lệ. Nếu phát sinh thiếu sót, hồ sơ được bổ sung hoặc chỉnh sửa và kiểm tra lại. Sau khi hồ sơ hợp lệ, khách hàng xác nhận lịch lắp đặt và ký hợp đồng. Hợp đồng đã ký được ghi nhận trên BPMS/CRM; hệ thống tạo Work Order, phân công đội kỹ thuật khu vực và cập nhật trạng thái để chuyển sang giai đoạn triển khai.

Đầu ra của trường hợp này là **một yêu cầu đăng ký đã có hồ sơ hợp lệ, hợp đồng đã ký và Work Order đã được tạo, phân công trên hệ thống**.

---

### 3.3.3. Phân tích định tính

#### 3.3.3.1. Phân tích giá trị gia tăng

Phân tích giá trị gia tăng được sử dụng để đánh giá mức độ đóng góp của từng hoạt động đối với khách hàng và yêu cầu vận hành của doanh nghiệp. Các hoạt động được phân loại theo ba nhóm:

- **VA (Value-Added):** hoạt động tạo giá trị trực tiếp cho khách hàng, góp phần đáp ứng nhu cầu hoặc xác lập kết quả dịch vụ mà khách hàng mong muốn.
- **BVA (Business-Value-Added):** hoạt động không tạo giá trị trực tiếp cho khách hàng nhưng cần thiết để đáp ứng yêu cầu vận hành, kiểm soát, pháp lý hoặc quản trị của doanh nghiệp.
- **NVA (Non-Value-Added):** hoạt động không tạo giá trị cho khách hàng và có thể loại bỏ, rút gọn hoặc tự động hóa mà không làm giảm chất lượng đầu ra của quy trình.


| STT | Hoạt động | Người thực hiện | Loại giá trị |
| ---: | --- | --- | :---: |
| 1 | Lựa chọn kênh đăng ký | Khách hàng | BVA |
| 2 | Cung cấp thông tin đăng ký | Khách hàng | BVA |
| 3 | Tiếp nhận và ghi nhận thông tin | Sales | BVA |
| 4 | Tư vấn gói cước phù hợp | Sales | VA |
| 5 | Xác nhận gói cước / nhu cầu sử dụng | Khách hàng | VA |
| 6 | Lập hồ sơ đăng ký sơ bộ | Sales | BVA |
| 7 | Chuyển yêu cầu sang bộ phận kỹ thuật | Sales | NVA |
| 8 | Tiếp nhận yêu cầu kiểm tra | Technical | NVA |
| 9 | Kiểm tra hạ tầng cáp quang | Technical | BVA |
| 10 | Kiểm tra số lượng Port | Technical | BVA |
| 11 | Đánh giá điều kiện cung cấp dịch vụ | Technical | BVA |
| 12 | Thông báo kết quả không đủ điều kiện | Technical / Sales | BVA |
| 13 | Yêu cầu khách hàng hoàn thiện hồ sơ | Sales | BVA |
| 14 | Hoàn thiện / cung cấp hồ sơ lần đầu | Khách hàng | BVA |
| 15 | Nhận hồ sơ khách hàng | Sales | NVA |
| 16 | Kiểm tra tính đầy đủ, hợp lệ của hồ sơ | Sales | BVA |
| 17 | Yêu cầu bổ sung / chỉnh sửa hồ sơ | Sales | NVA |
| 18 | Bổ sung / chỉnh sửa hồ sơ theo yêu cầu | Khách hàng | NVA |
| 19 | Xác nhận / chốt lịch lắp đặt | Sales / Khách hàng | VA |
| 20 | Ký hợp đồng điện tử hoặc hợp đồng giấy | Khách hàng | BVA |
| 21 | Ghi nhận hợp đồng trên BPMS/CRM | BPMS/CRM | BVA |
| 22 | Tạo Work Order | BPMS/CRM | BVA |
| 23 | Phân công đội kỹ thuật khu vực | BPMS/CRM | BVA |
| 24 | Lưu và theo dõi trạng thái đơn hàng | BPMS/CRM | BVA |

*Bảng 3.2. Phân tích giá trị gia tăng của quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom*

Các hoạt động **VA** tập trung tại những điểm trực tiếp xác lập giá trị đối với khách hàng: tư vấn gói cước phù hợp, xác nhận nhu cầu sử dụng và chốt lịch lắp đặt. Đây là các hoạt động giúp khách hàng lựa chọn đúng dịch vụ và xác định điều kiện triển khai phù hợp với nhu cầu thực tế.

Nhóm **BVA** chiếm tỷ trọng lớn do quy trình dịch vụ viễn thông yêu cầu nhiều bước kiểm soát trước khi triển khai. Kiểm tra hạ tầng, kiểm tra Port, đánh giá điều kiện kỹ thuật, kiểm tra hồ sơ, ký hợp đồng, tạo Work Order và phân công đội kỹ thuật không trực tiếp tạo ra giá trị cảm nhận cho khách hàng nhưng là điều kiện cần để kiểm soát rủi ro và bảo đảm khả năng cung cấp dịch vụ.

Nhóm **NVA** tập trung tại các hoạt động chuyển giao, tiếp nhận thủ công và xử lý lại. Việc chuyển yêu cầu giữa Sales và Technical, thao tác tiếp nhận yêu cầu hoặc hồ sơ đơn thuần, cùng vòng lặp bổ sung/chỉnh sửa hồ sơ không làm tăng giá trị của đầu ra. Các hoạt động này cần được ưu tiên rút gọn hoặc tự động hóa.

Mục tiêu tối ưu không phải loại bỏ các bước kiểm soát BVA cần thiết mà là giảm NVA, hạn chế xử lý lặp lại và rút ngắn thời gian chờ giữa các tác nhân.

#### 3.3.3.2. Phân tích lãng phí

Các lãng phí chính của quy trình tập trung vào thời gian chờ, chuyển giao thông tin, xử lý dư thừa, nhập liệu lặp lại và xử lý lại hồ sơ.

| Loại lãng phí | Biểu hiện trong quy trình |
| --- | --- |
| **Waiting – Chờ** | Khách hàng chờ Sales liên hệ; Sales chờ Technical kiểm tra hạ tầng; khách hàng chờ kết quả kiểm tra hồ sơ; yêu cầu chờ tạo hoặc phân công Work Order. |
| **Handoff – Chuyển giao** | Yêu cầu được chuyển từ Customer sang Sales, từ Sales sang Technical, từ Technical quay lại Sales và tiếp tục chuyển sang BPMS/CRM. |
| **Over-processing – Xử lý dư thừa** | Thông tin có thể phải được xác nhận lại ở nhiều bước; một số nội dung có thể được kiểm tra lặp lại trước khi tạo Work Order. |
| **Duplicate entry – Nhập liệu lặp lại** | Thông tin khách hàng đã có từ Website hoặc hồ sơ đăng ký có thể phải nhập lại vào hệ thống nếu các kênh chưa được tích hợp đầy đủ. |
| **Rework – Xử lý lại** | Hồ sơ thiếu, sai hoặc chưa hợp lệ dẫn đến việc Sales yêu cầu bổ sung/chỉnh sửa và khách hàng phải thực hiện lại một phần quy trình. |

*Bảng 3.3. Phân tích lãng phí của quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom*

**Waiting** là nguồn lãng phí có ảnh hưởng lớn đến thời gian chu kỳ. Khi yêu cầu phải chờ Sales tiếp nhận, chờ Technical kiểm tra hoặc chờ khách hàng bổ sung hồ sơ, tổng thời gian xử lý tăng dù thời gian thao tác thực tế của từng bước không thay đổi đáng kể.

**Handoff** phát sinh do quy trình có nhiều điểm chuyển giao giữa Customer, Sales, Technical và BPMS/CRM. Chuyển giao là cần thiết về mặt tổ chức, nhưng nếu được thực hiện thủ công hoặc thiếu đồng bộ dữ liệu thì sẽ làm tăng thời gian xử lý và nguy cơ sai lệch thông tin.

**Over-processing** xuất hiện khi thông tin đã được cung cấp nhưng tiếp tục phải xác nhận hoặc kiểm tra lại ở các bước sau. Việc thiếu chuẩn dữ liệu đầu vào hoặc thiếu cơ chế kiểm tra tự động là nguyên nhân chính dẫn đến xử lý dư thừa.

**Duplicate entry** phát sinh khi dữ liệu từ Website, kênh bán hàng và BPMS/CRM chưa được tích hợp xuyên suốt. Nhập lại dữ liệu làm tăng thời gian xử lý và rủi ro sai sót.

**Rework** xuất hiện trong vòng lặp bổ sung/chỉnh sửa hồ sơ. Đây là NVA rõ ràng của quy trình và cần được giảm bằng cơ chế kiểm tra dữ liệu ngay tại bước tiếp nhận, hướng dẫn hồ sơ theo checklist và kiểm tra điều kiện bắt buộc trước khi khách hàng gửi hồ sơ.

Các ưu tiên cải tiến gồm:

- Chuẩn hóa dữ liệu đầu vào và kiểm tra tính đầy đủ ngay tại bước tiếp nhận.
- Tự động chuyển yêu cầu từ Sales sang Technical.
- Đồng bộ kết quả kiểm tra kỹ thuật về một nguồn dữ liệu dùng chung.
- Hạn chế nhập lại dữ liệu giữa các kênh và BPMS/CRM.
- Giảm số vòng bổ sung/chỉnh sửa hồ sơ.
- Thiết lập cơ chế thông báo trạng thái tự động để giảm thời gian chờ và thao tác theo dõi thủ công.

---

### 3.3.4. Phân tích định lượng

#### 3.3.4.1. Thời gian xử lý

Do không có số liệu vận hành nội bộ của FPT Telecom trong phạm vi tài liệu này, các giá trị thời gian dưới đây được sử dụng làm **số liệu giả định phục vụ phân tích đồ án**.

Thời gian của từng hoạt động được xác định theo hai mức: **thời gian ngắn nhất** và **thời gian dài nhất**. Hai mức thời gian phản ánh sự khác biệt giữa trường hợp thông tin đầy đủ, hạ tầng rõ ràng và trường hợp cần kiểm tra hoặc bổ sung thông tin.

| STT | Hoạt động | Tác nhân | Thời gian ngắn nhất (phút) | Thời gian dài nhất (phút) |
| ---: | --- | --- | ---: | ---: |
| 1 | Cung cấp thông tin đăng ký | Customer | 5 | 10 |
| 2 | Tiếp nhận và ghi nhận thông tin | Sales | 5 | 10 |
| 3 | Tư vấn gói cước | Sales | 10 | 20 |
| 4 | Lập hồ sơ đăng ký sơ bộ | Sales | 10 | 20 |
| 5 | Tiếp nhận yêu cầu kiểm tra | Technical | 5 | 10 |
| 6 | Kiểm tra hạ tầng cáp quang | Technical | 15 | 30 |
| 7 | Kiểm tra số lượng Port | Technical | 5 | 10 |
| 8 | Đánh giá điều kiện cung cấp dịch vụ | Technical | 5 | 10 |
| 9 | Kiểm tra tính đầy đủ, hợp lệ của hồ sơ | Sales | 10 | 20 |
| 10 | Hoàn thiện / cung cấp hồ sơ theo yêu cầu | Customer | 5 | 15 |
| 11 | Điều phối và chốt lịch lắp đặt | Sales | 5 | 10 |
| 12 | Ký hợp đồng | Customer | 5 | 10 |
| 13 | Ghi nhận hợp đồng trên BPMS/CRM | BPMS/CRM | 2 | 5 |
| 14 | Tạo Work Order | BPMS/CRM | 2 | 5 |
| 15 | Phân công đội kỹ thuật khu vực | BPMS/CRM | 3 | 10 |
| 16 | Lưu và cập nhật trạng thái | BPMS/CRM | 2 | 5 |

*Bảng 3.4. Thời gian xử lý các hoạt động trong quy trình*

Trong bảng thời gian, phần trao đổi và xác nhận lịch của khách hàng được gộp vào hoạt động điều phối, chốt lịch của Sales để giữ thống nhất cách tính theo từng công đoạn.

Thời gian xử lý ngắn nhất:

`5 + 5 + 10 + 10 + 5 + 15 + 5 + 5 + 10 + 5 + 5 + 5 + 2 + 2 + 3 + 2 = 94 phút`

**Thời gian xử lý ngắn nhất = 94 phút**

Thời gian xử lý dài nhất:

`10 + 10 + 20 + 20 + 10 + 30 + 10 + 10 + 20 + 15 + 10 + 10 + 5 + 5 + 10 + 5 = 200 phút`

**Thời gian xử lý dài nhất = 200 phút**

Khoảng 94–200 phút phản ánh thời gian xử lý của một lượt theo các hoạt động chính. Nếu hồ sơ phải bổ sung hoặc chỉnh sửa nhiều lần, một số hoạt động sẽ lặp lại và tổng thời gian thực tế có thể cao hơn phạm vi giả định này.

#### 3.3.4.2. Thời gian chu kỳ

Thời gian xử lý nêu trên chưa bao gồm thời gian chờ giữa các tác nhân. Đối với trường hợp xử lý thuận lợi, thời gian chờ được giả định như sau:

- Chờ Sales tiếp nhận và liên hệ: 30 phút.
- Chờ Technical tiếp nhận yêu cầu: 30 phút.
- Chờ kết quả kiểm tra và phản hồi: 30 phút.
- Chờ khách hàng hoàn thiện hồ sơ và ký hợp đồng: 30 phút.

**Tổng thời gian chờ ngắn nhất = 120 phút**

**Thời gian chu kỳ ngắn nhất = 94 + 120 = 214 phút**, tương đương **3 giờ 34 phút**.

Đối với trường hợp xử lý chậm hơn:

- Chờ Sales liên hệ: 120 phút.
- Chờ Technical tiếp nhận: 120 phút.
- Chờ kiểm tra và phản hồi: 180 phút.
- Chờ khách hàng bổ sung hồ sơ và ký hợp đồng: 120 phút.

**Tổng thời gian chờ dài nhất = 540 phút**

**Thời gian chu kỳ dài nhất = 200 + 540 = 740 phút**, tương đương **12 giờ 20 phút**.

| Chỉ tiêu | Thời gian ngắn nhất | Thời gian dài nhất |
| --- | ---: | ---: |
| Thời gian xử lý | 94 phút | 200 phút |
| Thời gian chờ | 120 phút | 540 phút |
| Tổng thời gian chu kỳ | 214 phút | 740 phút |
| Quy đổi | 3 giờ 34 phút | 12 giờ 20 phút |

*Bảng 3.5. Tổng thời gian chu kỳ của quy trình*

Thời gian chờ chiếm tỷ trọng đáng kể trong tổng thời gian chu kỳ. Hiệu suất thời gian được tính như sau:

**Trường hợp ngắn nhất**

`94 / 214 × 100% = 43,93%`

**Trường hợp dài nhất**

`200 / 740 × 100% = 27,03%`

| Chỉ tiêu | Trường hợp ngắn nhất | Trường hợp dài nhất |
| --- | ---: | ---: |
| Thời gian xử lý | 94 phút | 200 phút |
| Tổng thời gian chu kỳ | 214 phút | 740 phút |
| Thời gian chờ | 120 phút | 540 phút |
| Hiệu suất thời gian | **43,93%** | **27,03%** |

*Bảng 3.6. Hiệu suất thời gian của quy trình*

Kết quả cho thấy thời gian chờ là một trong những yếu tố ảnh hưởng lớn nhất đến hiệu quả của quy trình. Việc tối ưu chỉ tập trung vào thời gian thao tác sẽ không tạo ra cải thiện đáng kể nếu các điểm chờ và chuyển giao vẫn giữ nguyên.

#### 3.3.4.3. Thời gian theo tác nhân

| Tác nhân | Thời gian ngắn nhất | Thời gian dài nhất |
| --- | ---: | ---: |
| Customer | 15 phút | 35 phút |
| Sales | 40 phút | 80 phút |
| Technical | 30 phút | 60 phút |
| BPMS/CRM | 9 phút | 25 phút |
| **Tổng cộng** | **94 phút** | **200 phút** |

Sales có thời gian tham gia lớn nhất do xử lý xuyên suốt từ tiếp nhận, tư vấn, lập hồ sơ sơ bộ, kiểm tra hồ sơ đến điều phối lịch lắp đặt. Technical có thời gian xử lý thấp hơn Sales nhưng giữ vai trò quyết định trong việc xác định khả năng cung cấp dịch vụ. BPMS/CRM có thời gian xử lý trực tiếp thấp nhất do phần lớn hoạt động được hệ thống hỗ trợ.

#### 3.3.4.4. Chi phí xử lý

Chi phí được tính trên thời gian xử lý của các nguồn lực tham gia. Đối với Sales và Technical, đây là chi phí lao động giả định. Đối với BPMS/CRM, đơn giá được hiểu là **chi phí vận hành hệ thống quy đổi theo giờ**, không phải chi phí lao động.

| Tác nhân | Đơn giá xử lý giả định |
| --- | ---: |
| Sales | 50.000 VNĐ/giờ |
| Technical | 60.000 VNĐ/giờ |
| BPMS/CRM | 55.000 VNĐ/giờ |

Các mức trên chỉ được sử dụng để minh họa phương pháp tính trong phạm vi đồ án, không đại diện cho mức lương, chi phí nhân sự hoặc chi phí vận hành hệ thống thực tế của FPT Telecom.

**Sales**

- Trường hợp ngắn nhất: `40 / 60 × 50.000 = 33.333 VNĐ`
- Trường hợp dài nhất: `80 / 60 × 50.000 = 66.667 VNĐ`

**Technical**

- Trường hợp ngắn nhất: `30 / 60 × 60.000 = 30.000 VNĐ`
- Trường hợp dài nhất: `60 / 60 × 60.000 = 60.000 VNĐ`

**BPMS/CRM**

- Trường hợp ngắn nhất: `9 / 60 × 55.000 = 8.250 VNĐ`
- Trường hợp dài nhất: `25 / 60 × 55.000 = 22.917 VNĐ`

Do thời gian của khách hàng không được tính vào chi phí vận hành nội bộ của doanh nghiệp, Customer không được đưa vào tổng chi phí xử lý nội bộ.

**Tổng chi phí xử lý nội bộ giả định**

- Trường hợp ngắn nhất: `33.333 + 30.000 + 8.250 = 71.583 VNĐ`
- Trường hợp dài nhất: `66.667 + 60.000 + 22.917 = 149.584 VNĐ`

| Tác nhân | Thời gian ngắn nhất | Chi phí ngắn nhất | Thời gian dài nhất | Chi phí dài nhất |
| --- | ---: | ---: | ---: | ---: |
| Sales | 40 phút | 33.333 VNĐ | 80 phút | 66.667 VNĐ |
| Technical | 30 phút | 30.000 VNĐ | 60 phút | 60.000 VNĐ |
| BPMS/CRM | 9 phút | 8.250 VNĐ | 25 phút | 22.917 VNĐ |
| **Tổng cộng** | **79 phút** | **71.583 VNĐ** | **165 phút** | **149.584 VNĐ** |

*Bảng 3.7. Chi phí xử lý yêu cầu đăng ký dịch vụ*

Sales chiếm tỷ trọng chi phí xử lý nội bộ lớn nhất do tham gia nhiều công đoạn và trực tiếp tương tác với khách hàng trong phần lớn quy trình. Technical đứng thứ hai do các hoạt động kiểm tra hạ tầng và Port yêu cầu nguồn lực chuyên môn. Chi phí quy đổi của BPMS/CRM thấp hơn do các hoạt động tạo Work Order, phân công và cập nhật trạng thái được hệ thống hỗ trợ.

Nếu lấy trường hợp ngắn nhất làm cơ sở:

- **Sales:** `33.333 / 71.583 × 100% = 46,57%`
- **Technical:** `30.000 / 71.583 × 100% = 41,91%`
- **BPMS/CRM:** `8.250 / 71.583 × 100% = 11,52%`

Sales và Technical chiếm phần lớn chi phí xử lý nội bộ giả định, do đó đây là hai nhóm nguồn lực cần được ưu tiên khi đánh giá các phương án cải tiến.

#### 3.3.4.5. Nhận xét kết quả phân tích định lượng

Phân tích thời gian và chi phí cho thấy hiệu quả của quy trình chịu tác động lớn từ thời gian chờ và các điểm chuyển giao giữa các tác nhân.

Ở trường hợp ngắn nhất, thời gian xử lý trực tiếp là 94 phút trong tổng thời gian chu kỳ 214 phút; hiệu suất thời gian đạt 43,93%. Ở trường hợp dài nhất, thời gian xử lý là 200 phút trong tổng thời gian chu kỳ 740 phút; hiệu suất giảm còn 27,03%.

Kết quả này cho thấy các phương án cải tiến cần tập trung đồng thời vào hai nhóm vấn đề: giảm thời gian chờ và giảm NVA. Việc chỉ rút ngắn thời gian thao tác tại từng bộ phận sẽ không tạo ra cải thiện đáng kể nếu các điểm chuyển giao, xử lý lại và nhập liệu lặp lại vẫn tồn tại.

Các hướng cải tiến ưu tiên gồm có:

1. Chuẩn hóa dữ liệu đầu vào và kiểm tra tính đầy đủ ngay tại thời điểm tiếp nhận.
2. Tích hợp thông tin từ Website và các kênh đăng ký vào BPMS/CRM để hạn chế nhập liệu lặp lại.
3. Tự động chuyển yêu cầu sang Technical sau khi hồ sơ sơ bộ đạt điều kiện kiểm tra.
4. Tự động cập nhật kết quả kiểm tra hạ tầng và Port trên hệ thống.
5. Thiết lập cơ chế thông báo và phân công tự động để giảm thời gian chờ giữa Sales và Technical.
6. Áp dụng checklist hồ sơ và quy tắc kiểm tra bắt buộc nhằm giảm số vòng bổ sung/chỉnh sửa.
7. Theo dõi trạng thái yêu cầu tập trung trên BPMS/CRM để giảm thao tác xác nhận thủ công.
8. Thiết lập chỉ số theo dõi tỷ lệ hồ sơ đạt ngay lần đầu, số vòng rework và thời gian chờ theo từng công đoạn để phục vụ kiểm soát hiệu suất quy trình.
