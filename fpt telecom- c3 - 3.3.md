## **3.3. Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom**

### **3.3.1. Phương pháp thực hiện (Khám phá quy trình - Process Discovery)**

Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet là quy trình đầu vào của chuỗi cung cấp dịch vụ Internet FPT Telecom. Quy trình bắt đầu khi khách hàng phát sinh nhu cầu sử dụng dịch vụ và kết thúc khi yêu cầu đủ điều kiện đã được ghi nhận trên BPMS/CRM, tạo Work Order và phân công cho đội kỹ thuật khu vực để chuyển sang giai đoạn triển khai lắp đặt.

Hoạt động khám phá quy trình được triển khai theo ba hướng: **dựa trên bằng chứng (Evidence-based Discovery)** để xác lập luồng nghiệp vụ As-Is; **phỏng vấn (Interview-based Discovery)** để làm rõ trải nghiệm xử lý, thời gian chờ và các điểm phát sinh xử lý lại; và **Workshop (Workshop-based Discovery)** để thống nhất ranh giới quy trình, trách nhiệm giữa các bên và các điểm ra quyết định trong mô hình BPMN.

---

#### **3.3.1.1. Dựa trên bằng chứng (Evidence-based Discovery)**

Phương pháp dựa trên bằng chứng tập trung vào các thông tin nghiệp vụ hình thành trực tiếp trong quá trình đăng ký dịch vụ, gồm kênh tiếp nhận, thông tin khách hàng, nội dung tư vấn, kết quả kiểm tra kỹ thuật, hồ sơ đăng ký, lịch lắp đặt, hợp đồng và Work Order. Các thông tin này được liên kết theo trình tự xử lý để mô tả quy trình As-Is.

##### **a) Mô tả quy trình hiện có (As-Is Process Description)**

Quy trình gồm **13 bước nghiệp vụ chính** và **07 cổng quyết định Exclusive XOR (GW1–GW7)**. Các cổng quyết định thể hiện các lựa chọn về kênh đăng ký, xác nhận dịch vụ, điều kiện kỹ thuật, tính hợp lệ của hồ sơ, lịch lắp đặt và hình thức ký hợp đồng.

* **Bước 1: Khách hàng phát sinh nhu cầu và lựa chọn kênh đăng ký – GW1**  
  Khách hàng có nhu cầu sử dụng Internet hoặc dịch vụ đi kèm lựa chọn kênh tiếp nhận ban đầu. **GW1 – XOR: Kênh đăng ký?** gồm bốn nhánh: Website, Hotline, cửa hàng giao dịch hoặc nhân viên kinh doanh. Các nhánh hội tụ tại thời điểm thông tin đăng ký ban đầu được chuyển cho Sales xử lý.

* **Bước 2: Khách hàng cung cấp thông tin đăng ký ban đầu**  
  Khách hàng cung cấp họ tên, số điện thoại liên hệ, địa chỉ lắp đặt và nhu cầu sử dụng. Đối với Website, khách hàng chủ động nhập thông tin; đối với Hotline, cửa hàng hoặc nhân viên kinh doanh, thông tin được nhân sự phụ trách tiếp nhận.

* **Bước 3: Sales tiếp nhận, kiểm tra thông tin và tư vấn gói cước**  
  Sales ghi nhận các thông tin cơ bản, làm rõ nhu cầu sử dụng và tư vấn gói cước phù hợp.

* **Bước 4: Khách hàng xác nhận gói cước và nhu cầu – GW2**  
  Sau bước tư vấn, **GW2 – XOR: Khách hàng đã xác nhận gói cước và nhu cầu sử dụng?**  
  * *Đã xác nhận:* Sales được phép lập hồ sơ đăng ký sơ bộ.  
  * *Chưa xác nhận:* Sales tiếp tục tư vấn, làm rõ nhu cầu và duy trì yêu cầu ở giai đoạn tư vấn cho đến khi khách hàng xác nhận gói cước và nhu cầu sử dụng.

* **Bước 5: Sales lập hồ sơ đăng ký sơ bộ và chuyển Technical kiểm tra**  
  Khi khách hàng đã xác nhận gói cước, Sales lập hồ sơ đăng ký sơ bộ và chuyển yêu cầu sang Technical để kiểm tra khả năng cung cấp dịch vụ tại địa chỉ đăng ký.

* **Bước 6: Technical kiểm tra hạ tầng cáp quang – GW3**  
  Technical kiểm tra điều kiện hạ tầng cáp quang tại khu vực lắp đặt. Kết quả kiểm tra được đánh giá tại **GW3 – XOR: Hạ tầng cáp quang có đáp ứng?**  
  * *Không đáp ứng:* Kết luận yêu cầu chưa đủ điều kiện kỹ thuật; Sales thông báo khách hàng và quy trình kết thúc, không tạo Work Order.  
  * *Đáp ứng:* Chuyển sang kiểm tra số lượng Port còn khả dụng.

* **Bước 7: Technical kiểm tra Port – GW4**  
  Technical kiểm tra số lượng cổng kết nối (Port) còn khả dụng. **GW4 – XOR: Có Port khả dụng?**  
  * *Không có Port khả dụng:* Kết luận yêu cầu chưa đủ điều kiện kỹ thuật; Sales thông báo khách hàng và quy trình kết thúc, không tạo Work Order.  
  * *Có Port khả dụng:* Technical xác nhận điều kiện kỹ thuật đáp ứng và quy trình chuyển sang hoàn thiện hồ sơ.


* **Bước 8: Sales yêu cầu khách hàng hoàn thiện hồ sơ đăng ký**  
  Khi đủ điều kiện kỹ thuật, Sales yêu cầu khách hàng hoàn thiện hồ sơ và cung cấp các giấy tờ cần thiết; khách hàng hoàn thiện và gửi lại hồ sơ cho Sales.

* **Bước 9: Sales kiểm tra tính đầy đủ, hợp lệ của hồ sơ – GW5**  
  **GW5 – XOR: Hồ sơ đầy đủ và hợp lệ?**  
  * *Không:* Sales yêu cầu khách hàng bổ sung hoặc chỉnh sửa; khách hàng gửi lại hồ sơ và Sales kiểm tra lại. Vòng lặp tiếp tục cho đến khi hồ sơ đáp ứng yêu cầu.  
  * *Có:* Chuyển sang bước xác nhận lịch lắp đặt.

* **Bước 10: Xác nhận lịch lắp đặt – GW6**  
  Sales đề nghị khách hàng xác nhận lịch lắp đặt. **GW6 – XOR: Khách hàng đã xác nhận lịch lắp đặt?**  
  * *Đã xác nhận:* Sales chuyển sang gửi hợp đồng để khách hàng ký.  
  * *Chưa xác nhận:* Sales tiếp tục phối hợp với khách hàng để xác nhận lịch; quy trình chuyển sang bước gửi hợp đồng sau khi lịch lắp đặt được chốt.

* **Bước 11: Gửi và ký hợp đồng – GW7**  
  Sales gửi hợp đồng cho khách hàng. **GW7 – XOR: Hình thức ký hợp đồng?** gồm hai nhánh:  
  * *Ký điện tử.*  
  * *Ký hợp đồng giấy.*  
  Hai nhánh hội tụ tại trạng thái “Hợp đồng đã ký”.

* **Bước 12: Sales tiếp nhận hợp đồng đã ký và chuyển thông tin vào BPMS/CRM**  
  Sales tiếp nhận hợp đồng đã ký, chuyển thông tin vào hệ thống để ghi nhận giao dịch và trạng thái đăng ký.

* **Bước 13: BPMS/CRM tạo Work Order, phân công và kết thúc quy trình**  
  BPMS/CRM ghi nhận hợp đồng, tạo Work Order, phân công đơn cho đội kỹ thuật phụ trách khu vực và cập nhật trạng thái để chuyển sang giai đoạn triển khai lắp đặt. Quy trình kết thúc khi Work Order đã được tạo, phân công và trạng thái yêu cầu được cập nhật.

**Các tác nhân tham gia quy trình (Actors):**

| STT | Tác nhân | Vai trò và trách nhiệm trong quy trình |
| :---: | :--- | :--- |
| **1** | **Khách hàng (Customer)** | Khởi tạo nhu cầu; lựa chọn kênh đăng ký; cung cấp thông tin; xác nhận gói cước; hoàn thiện/bổ sung hồ sơ; xác nhận lịch; ký hợp đồng. |
| **2** | **Bộ phận Kinh doanh (Sales)** | Tiếp nhận và ghi nhận thông tin; tư vấn; lập hồ sơ sơ bộ; chuyển yêu cầu kiểm tra kỹ thuật; kiểm tra hồ sơ; điều phối lịch; gửi/nhận hợp đồng; chuyển dữ liệu vào BPMS/CRM. |
| **3** | **Bộ phận Kỹ thuật (Technical)** | Kiểm tra hạ tầng cáp quang; kiểm tra Port; đánh giá khả năng cung cấp dịch vụ; trả kết quả kỹ thuật. |
| **4** | **Hệ thống BPMS/CRM** | Ghi nhận hợp đồng; tạo Work Order; phân công đội kỹ thuật khu vực; lưu và cập nhật trạng thái yêu cầu. |
| **5** | **Đội kỹ thuật khu vực** | Là tác nhân nhận đầu ra của quy trình; tiếp nhận Work Order để thực hiện quy trình triển khai lắp đặt tiếp theo. |

**Khách hàng của quy trình (Customer):**

* **Khách hàng bên ngoài:** Cá nhân hoặc doanh nghiệp đăng ký sử dụng dịch vụ Internet FPT Telecom. Khách hàng kỳ vọng được tư vấn đúng nhu cầu, biết sớm khả năng triển khai, hoàn tất thủ tục thuận tiện và có lịch lắp đặt rõ ràng.
* **Khách hàng nội bộ:** Đội kỹ thuật khu vực tiếp nhận Work Order. Đầu ra cần có đủ thông tin cần thiết để đội kỹ thuật có thể tiếp tục triển khai mà không phải xác minh lại các nội dung đã được xử lý ở giai đoạn đăng ký.

**Giá trị mang lại (Value Proposition):**

* **Xác định đúng nhu cầu dịch vụ:** Giúp khách hàng lựa chọn gói cước phù hợp với nhu cầu sử dụng.
* **Xác định khả năng cung cấp trước khi cam kết:** Kiểm tra hạ tầng và Port trước khi chuyển sang triển khai.
* **Kiểm soát chất lượng hồ sơ:** Hạn chế việc tạo đơn khi hồ sơ còn thiếu hoặc chưa hợp lệ.
* **Giảm rủi ro triển khai:** Ngăn các yêu cầu không đủ điều kiện kỹ thuật chuyển sang giai đoạn thi công.
* **Chuẩn hóa phối hợp liên bộ phận:** Làm rõ điểm giao tiếp giữa Customer, Sales, Technical và BPMS/CRM.
* **Chuyển đổi nhu cầu thành lệnh triển khai:** Tạo Work Order có trạng thái và đơn vị kỹ thuật phụ trách cụ thể.

**Những kết quả có thể đạt được (Possible Outcomes):**

| Kết quả / trạng thái | Diễn giải chi tiết |
| :--- | :--- |
| **Đăng ký thành công (Happy Path)** | Khách hàng xác nhận gói cước; hạ tầng và Port đáp ứng; hồ sơ hợp lệ; lịch lắp đặt được xác nhận; hợp đồng được ký; BPMS/CRM tạo và phân công Work Order. |
| **Kết thúc do hạ tầng không đáp ứng** | Tại GW3, hạ tầng cáp quang tại khu vực lắp đặt không đáp ứng; Sales thông báo khách hàng; không tạo Work Order. |
| **Kết thúc do không có Port khả dụng** | Tại GW4, không có Port khả dụng; Sales thông báo khách hàng; không tạo Work Order. |
| **Chờ hoàn thiện hồ sơ** | Tại GW5, hồ sơ thiếu hoặc chưa hợp lệ; Sales yêu cầu bổ sung/chỉnh sửa và kiểm tra lại. |
| **Chờ xác nhận của khách hàng** | Tại GW2 hoặc GW6, yêu cầu được duy trì tại bước tư vấn hoặc xác nhận lịch cho đến khi khách hàng hoàn tất xác nhận để chuyển sang công đoạn tiếp theo. |
| **Biến thể kênh/hình thức ký** | GW1 phân nhánh theo kênh đăng ký ban đầu; GW7 phân nhánh theo ký điện tử hoặc ký giấy. Các nhánh hội tụ về cùng luồng nghiệp vụ tiếp theo. |

---

##### **b) Sơ đồ tổ chức và Ma trận trách nhiệm (Organizational View & RACI Matrix)**

Quy trình được tổ chức theo chuỗi phối hợp **Customer → Sales → Technical → Sales → BPMS/CRM → Đội kỹ thuật khu vực**. Sales là đầu mối điều phối nghiệp vụ; Technical chịu trách nhiệm đánh giá khả năng cung cấp dịch vụ; BPMS/CRM ghi nhận giao dịch và tạo Work Order; khách hàng tham gia tại các điểm cung cấp thông tin, xác nhận và ký hợp đồng.

**Ma trận phân công trách nhiệm (RACI Matrix):**  
*(R – Responsible: trực tiếp thực hiện; A – Accountable: chịu trách nhiệm cuối cùng đối với hoạt động; C – Consulted: được tham vấn/phối hợp; I – Informed: được thông báo)*

| Hoạt động nghiệp vụ | Customer | Sales | Technical | BPMS/CRM | Đội kỹ thuật khu vực |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Lựa chọn kênh và cung cấp thông tin đăng ký | **R / A** | C | I | I | I |
| Tiếp nhận thông tin và tư vấn gói cước | C | **R / A** | I | I | I |
| Xác nhận gói cước / nhu cầu sử dụng | **R / A** | C | I | I | I |
| Lập hồ sơ đăng ký sơ bộ | C | **R / A** | I | I | I |
| Chuyển yêu cầu kiểm tra kỹ thuật | I | **R / A** | I | I | I |
| Kiểm tra hạ tầng cáp quang | I | C | **R / A** | I | I |
| Kiểm tra Port và đánh giá khả năng cung cấp | I | C | **R / A** | I | I |
| Hoàn thiện/bổ sung hồ sơ | **R / A** | C | I | I | I |
| Kiểm tra tính đầy đủ, hợp lệ của hồ sơ | C | **R / A** | I | I | I |
| Xác nhận/chốt lịch lắp đặt | **R** | **R / A** | I | I | I |
| Gửi, ký và tiếp nhận hợp đồng | **R** | **R / A** | I | I | I |
| Ghi nhận hợp đồng trên hệ thống | I | **A** | I | **R** | I |
| Tạo và phân công Work Order | I | **A** | I | **R** | I |
| Tiếp nhận Work Order để triển khai | I | I | I | I | **R / A** |


---

##### **c) Kế hoạch xử lý công việc (Case-based Work Schedule)**

Quy trình được xử lý theo từng yêu cầu đăng ký, với trình tự công việc từ tiếp nhận nhu cầu đến tạo Work Order như sau:

| Giai đoạn | Tác nhân chính | Nội dung xử lý | Đầu ra |
| :---: | :--- | :--- | :--- |
| **1. Khởi tạo yêu cầu** | Customer | Lựa chọn kênh đăng ký và cung cấp thông tin ban đầu. | Thông tin đăng ký được ghi nhận. |
| **2. Tiếp nhận và tư vấn** | Sales | Kiểm tra thông tin, làm rõ nhu cầu, tư vấn gói cước và tiếp nhận xác nhận của khách hàng. | Gói cước/nhu cầu được xác nhận. |
| **3. Kiểm tra khả năng cung cấp** | Sales / Technical | Lập hồ sơ sơ bộ, kiểm tra hạ tầng cáp quang và Port khả dụng. | Kết quả đủ/không đủ điều kiện kỹ thuật. |
| **4. Hoàn thiện hồ sơ** | Customer / Sales | Khách hàng cung cấp hồ sơ; Sales kiểm tra và xử lý vòng bổ sung khi hồ sơ chưa hợp lệ. | Hồ sơ đầy đủ và hợp lệ. |
| **5. Xác nhận lịch và ký hợp đồng** | Customer / Sales | Xác nhận lịch lắp đặt; gửi và ký hợp đồng điện tử hoặc hợp đồng giấy. | Hợp đồng đã ký và lịch lắp đặt được xác nhận. |
| **6. Ghi nhận và tạo lệnh triển khai** | Sales / BPMS/CRM | Ghi nhận hợp đồng, tạo Work Order, phân công đội kỹ thuật và cập nhật trạng thái. | Work Order sẵn sàng chuyển sang quy trình triển khai lắp đặt. |

---

##### **d) Thuật ngữ và sổ tay nghiệp vụ (Glossary & Manuals)**

| Thuật ngữ / Viết tắt | Tên đầy đủ / Định nghĩa | Vai trò trong quy trình |
| :--- | :--- | :--- |
| **Customer** | Khách hàng | Chủ thể phát sinh nhu cầu, cung cấp thông tin, xác nhận dịch vụ, lịch lắp đặt và ký hợp đồng. |
| **Sales** | Bộ phận Kinh doanh | Đầu mối tiếp nhận và điều phối yêu cầu đăng ký. |
| **Technical** | Bộ phận Kỹ thuật | Kiểm tra điều kiện hạ tầng và khả năng cung cấp dịch vụ. |
| **Port** | Cổng kết nối trên hạ tầng truy nhập | Điều kiện kỹ thuật cần kiểm tra để xác định khả năng cấp dịch vụ tại khu vực đăng ký. |
| **BPMS** | Business Process Management System | Hệ thống quản trị quy trình nghiệp vụ, hỗ trợ ghi nhận và điều phối trạng thái xử lý. |
| **CRM** | Customer Relationship Management | Hệ thống quản lý dữ liệu và quan hệ khách hàng. |
| **Work Order (WO)** | Lệnh/đơn công việc lắp đặt | Đầu ra chính của quy trình, được chuyển cho đội kỹ thuật khu vực để triển khai. |
| **As-Is** | Quy trình hiện tại | Cách quy trình đang được mô tả/vận hành trước khi thiết kế cải tiến To-Be. |
| **Rework** | Xử lý lại | Vòng lặp phát sinh khi hồ sơ thiếu, sai hoặc chưa hợp lệ và phải bổ sung/chỉnh sửa. |

---

##### **e) Hệ thống biểu mẫu và dữ liệu nghiệp vụ (Forms, Records & Data Objects)**

Các hồ sơ và dữ liệu nghiệp vụ được sử dụng xuyên suốt quy trình gồm thông tin đăng ký ban đầu, hồ sơ đăng ký, kết quả kiểm tra kỹ thuật, thông tin lịch lắp đặt, hợp đồng, Work Order và trạng thái xử lý trên BPMS/CRM.

| STT | Hồ sơ / dữ liệu | Người khởi tạo / cung cấp | Người/hệ thống sử dụng | Mục đích |
| :---: | :--- | :--- | :--- | :--- |
| **1** | Thông tin đăng ký ban đầu | Customer / kênh tiếp nhận | Sales | Ghi nhận nhu cầu, thông tin liên hệ và địa chỉ lắp đặt. |
| **2** | Hồ sơ đăng ký sơ bộ | Sales | Technical | Làm căn cứ kiểm tra khả năng cung cấp dịch vụ. |
| **3** | Kết quả kiểm tra hạ tầng và Port | Technical | Sales | Quyết định tiếp tục hay kết thúc yêu cầu. |
| **4** | Hồ sơ đăng ký hoàn chỉnh | Customer | Sales | Kiểm tra điều kiện hồ sơ trước khi ký hợp đồng. |
| **5** | Thông tin xác nhận lịch lắp đặt | Customer / Sales | Sales, đội kỹ thuật | Xác lập thời điểm dự kiến triển khai. |
| **6** | Hợp đồng đã ký | Customer / Sales | BPMS/CRM | Xác nhận giao dịch và làm căn cứ tạo Work Order. |
| **7** | Work Order | BPMS/CRM | Đội kỹ thuật khu vực | Kích hoạt quy trình triển khai lắp đặt. |
| **8** | Trạng thái yêu cầu | BPMS/CRM | Sales và các bộ phận liên quan | Theo dõi tiến độ và trạng thái của yêu cầu đăng ký. |

---

#### **3.3.1.2. Phỏng vấn (Interview-based Discovery)**

Phương pháp phỏng vấn tập trung làm rõ trải nghiệm xử lý của Customer, Sales và Technical; mức độ thuận tiện của các kênh tiếp nhận; nguyên nhân phát sinh thời gian chờ; tỷ lệ hồ sơ phải bổ sung; và mức độ liên thông dữ liệu giữa các kênh đăng ký với BPMS/CRM. Bộ câu hỏi gồm **10 câu hỏi định tính** và **10 câu hỏi định lượng**, kết hợp câu hỏi có cấu trúc và câu hỏi mở.

##### **a) Danh sách 10 câu hỏi định tính**

**Nhóm câu hỏi có cấu trúc (Structured Qualitative Questions):**

| STT | Đối tượng | Nội dung câu hỏi | Thang đo / phương án lựa chọn |
| :---: | :--- | :--- | :--- |
| **1** | Khách hàng | Mức độ thuận tiện khi gửi yêu cầu đăng ký qua kênh đã lựa chọn như thế nào? | Likert 1–5: rất bất tiện → rất thuận tiện. |
| **2** | Khách hàng | Mức độ rõ ràng của thông tin tư vấn gói cước do Sales cung cấp? | Likert 1–5. |
| **3** | Sales | Mức độ đầy đủ của thông tin khách hàng ngay lần tiếp nhận đầu tiên? | Likert 1–5. |
| **4** | Sales | Việc chuyển yêu cầu sang Technical hiện chủ yếu được thực hiện bằng cách nào? | [A] Tự động trên hệ thống; [B] BPMS/CRM có thao tác thủ công; [C] Email/chat; [D] Cách khác. |
| **5** | Technical | Mức độ thuận tiện khi tra cứu hạ tầng và Port phục vụ kiểm tra yêu cầu? | Likert 1–5. |

**Nhóm câu hỏi không có cấu trúc (Unstructured Qualitative Questions):**

| STT | Đối tượng | Nội dung câu hỏi mở | Mục tiêu thu thập thông tin |
| :---: | :--- | :--- | :--- |
| **1** | Sales | Những nguyên nhân nào thường làm yêu cầu đăng ký bị chậm ngay từ bước tiếp nhận và tư vấn? | Xác định bottleneck đầu quy trình. |
| **2** | Technical | Khó khăn lớn nhất khi xác định khả năng cung cấp dịch vụ tại địa chỉ khách hàng là gì? | Nhận diện hạn chế dữ liệu/hệ thống kỹ thuật. |
| **3** | Sales | Những lỗi hồ sơ nào khiến khách hàng phải bổ sung hoặc chỉnh sửa nhiều nhất? | Xác định nguyên nhân Rework. |
| **4** | Khách hàng | Bước nào trong quá trình đăng ký khiến khách hàng phải chờ hoặc cung cấp lại thông tin nhiều nhất? | Đánh giá trải nghiệm khách hàng và NVA. |
| **5** | Sales / Quản lý vận hành | Nếu chỉ được ưu tiên tự động hóa một điểm của quy trình, Anh/Chị sẽ chọn điểm nào và vì sao? | Xác định ưu tiên To-Be. |

##### **b) Danh sách 10 câu hỏi định lượng**

**Nhóm câu hỏi có cấu trúc (Structured Quantitative Questions):**

| STT | Đối tượng | Nội dung câu hỏi | Đơn vị đo lường |
| :---: | :--- | :--- | :---: |
| **1** | Sales | Thời gian trung bình từ khi có lead/yêu cầu đến khi Sales liên hệ lần đầu là bao lâu? | Phút |
| **2** | Sales | Thời gian trung bình để tư vấn và lập hồ sơ đăng ký sơ bộ cho một yêu cầu? | Phút/yêu cầu |
| **3** | Technical | Thời gian trung bình để kiểm tra hạ tầng và Port cho một địa chỉ? | Phút/yêu cầu |
| **4** | Sales | Tỷ lệ hồ sơ đầy đủ, hợp lệ ngay lần đầu là bao nhiêu? | % |
| **5** | BPMS/CRM / Sales | Thời gian từ khi nhận hợp đồng đã ký đến khi Work Order được tạo và phân công? | Phút |

**Nhóm câu hỏi mở định lượng (Unstructured Quantitative Questions):**

| STT | Đối tượng | Nội dung câu hỏi | Dữ liệu kỳ vọng |
| :---: | :--- | :--- | :--- |
| **1** | Sales | Trong một tháng, số yêu cầu phải bổ sung/chỉnh sửa hồ sơ dao động trong khoảng bao nhiêu? | Số yêu cầu/tháng |
| **2** | Technical | Tỷ lệ yêu cầu bị từ chối do không đủ hạ tầng hoặc hết Port là bao nhiêu? | % |
| **3** | Sales | Một hồ sơ bị Rework thường phải bổ sung bao nhiêu vòng trước khi hợp lệ? | Số vòng/hồ sơ |
| **4** | Sales / BPMS | Tỷ lệ yêu cầu phải nhập lại dữ liệu giữa kênh tiếp nhận và BPMS/CRM là bao nhiêu? | % |
| **5** | Quản lý vận hành | Mức giảm Cycle Time mục tiêu nếu tích hợp tự động các kênh đăng ký, Technical và BPMS/CRM là bao nhiêu? | % hoặc phút |

---

#### **3.3.1.3. Workshop (Hội thảo khám phá quy trình - Workshop-based Discovery)**

Workshop tập trung vào việc thống nhất ranh giới quy trình, chuỗi hoạt động chính, các điểm chuyển giao giữa Customer, Sales, Technical và BPMS/CRM, đồng thời rà soát các nhánh ngoại lệ và trách nhiệm của từng bên trong quy trình.

##### **a) Biểu mẫu cuộc họp (Meeting Agenda & Setup Form)**

* **Tên cuộc họp:** Workshop khám phá và chuẩn hóa quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet.
* **Mục tiêu:**
  1. Thống nhất điểm bắt đầu và kết thúc của quy trình.
  2. Xác nhận luồng chính từ phát sinh nhu cầu đến tạo Work Order.
  3. Làm rõ các nhánh không đủ điều kiện kỹ thuật, hồ sơ chưa hợp lệ và các biến thể kênh đăng ký/ký hợp đồng.
  4. Xác nhận trách nhiệm RACI và các điểm chuyển giao dữ liệu.
  5. Thu thập số liệu thực tế về thời gian chờ, Rework và tỷ lệ hồ sơ đạt ngay lần đầu.
* **Thành phần tham gia theo vai trò:**

| Vai trò | Đại diện tham gia | Trách nhiệm trong Workshop |
| :--- | :--- | :--- |
| **Facilitator** | BA/nhóm phân tích quy trình | Điều phối, giữ phạm vi và thống nhất kết quả. |
| **Process Owner/đại diện Sales** | Quản lý hoặc nhân sự Sales | Xác nhận luồng tiếp nhận, tư vấn, hồ sơ, hợp đồng. |
| **Đại diện Technical** | Nhân sự kiểm tra hạ tầng | Xác nhận bước kiểm tra hạ tầng, Port và điều kiện cung cấp. |
| **Đại diện hệ thống** | Quản trị BPMS/CRM | Xác nhận điểm ghi nhận dữ liệu, tạo/phân công Work Order. |
| **Đại diện đội kỹ thuật khu vực** | Đội nhận Work Order | Xác nhận chất lượng đầu ra cần thiết cho quy trình tiếp theo. |
| **Scribe** | BA/thư ký | Ghi biên bản, cập nhật sơ đồ và danh sách vấn đề. |

##### **b) Kịch bản cuộc họp (Meeting Script & Facilitation Guide)**

* **Giai đoạn 1 – Thống nhất phạm vi**  
  Xác nhận Start Event là khách hàng phát sinh nhu cầu; End Event thành công là Work Order đã được tạo và phân công; End Event không thành công là yêu cầu kết thúc do không đủ điều kiện kỹ thuật.

* **Giai đoạn 2 – Vẽ luồng chính (Happy Path)**  
  Đi lần lượt qua các bước: tiếp nhận → tư vấn → hồ sơ sơ bộ → kiểm tra kỹ thuật → hoàn thiện hồ sơ → chốt lịch → ký hợp đồng → BPMS/CRM → Work Order.

* **Giai đoạn 3 – Xác định 7 gateway và luồng ngoại lệ**  
  Rà soát bảy điểm quyết định của quy trình: **GW1 kênh đăng ký; GW2 xác nhận gói cước/nhu cầu; GW3 hạ tầng cáp quang đáp ứng; GW4 Port khả dụng; GW5 hồ sơ đầy đủ/hợp lệ; GW6 xác nhận lịch lắp đặt; GW7 hình thức ký hợp đồng**. Các nhánh được đối chiếu với trình tự xử lý để bảo đảm luồng chính và luồng ngoại lệ thống nhất trong mô hình BPMN As-Is.

* **Giai đoạn 4 – Rà soát dữ liệu và RACI**  
  Kiểm tra ai tạo, ai sửa và ai chịu trách nhiệm cuối cùng cho từng thông tin: thông tin đăng ký, kết quả kỹ thuật, hồ sơ hợp lệ, lịch lắp đặt, hợp đồng và Work Order.

* **Giai đoạn 5 – Chốt số liệu và hành động tiếp theo**  
  Thống nhất các chỉ số cần đo: Lead Response Time, Technical Check Time, First-Time-Right hồ sơ, số vòng Rework, thời gian từ hợp đồng đến Work Order và tổng Cycle Time.

---

### **3.3.2. Mô hình hóa quy trình hiện tại (Sơ đồ BPMN - As-Is)**

Mô hình BPMN As-Is của quy trình được xây dựng với **07 cổng quyết định Exclusive XOR (GW1–GW7)**, phản ánh các điểm lựa chọn và kiểm soát chính từ khi khách hàng phát sinh nhu cầu đến khi Work Order được tạo và phân công. Hai điều kiện kỹ thuật về **hạ tầng cáp quang** và **Port khả dụng** được thể hiện thành hai cổng quyết định riêng để làm rõ nguyên nhân dẫn đến kết quả đủ hoặc không đủ điều kiện triển khai.

#### **a) Phân tích độ phức tạp và các phần tử BPMN 2.0**

**Hệ thống 07 cổng điều kiện Exclusive XOR:**

1. **GW1 – XOR: Khách hàng đăng ký qua kênh nào?**  
   * Website.  
   * Hotline.  
   * Cửa hàng giao dịch.  
   * Nhân viên kinh doanh.  
   GW1 phản ánh lựa chọn kênh đầu vào của **một yêu cầu đăng ký cụ thể**. Các nhánh hội tụ trước bước Sales xử lý thông tin.

2. **GW2 – XOR: Khách hàng đã xác nhận gói cước và nhu cầu sử dụng?**  
   * **Đã xác nhận:** Sales lập hồ sơ đăng ký sơ bộ.  
   * **Chưa xác nhận:** Sales tiếp tục tư vấn và làm rõ nhu cầu; khi khách hàng xác nhận, luồng quay lại GW2 và chuyển sang lập hồ sơ đăng ký sơ bộ.

3. **GW3 – XOR: Hạ tầng cáp quang tại khu vực lắp đặt có đáp ứng?**  
   * **Có:** Chuyển sang kiểm tra Port.  
   * **Không:** Kết luận chưa đủ điều kiện kỹ thuật → Sales thông báo khách hàng → kết thúc yêu cầu, không tạo Work Order.

4. **GW4 – XOR: Có Port khả dụng?**  
   * **Có:** Xác nhận đủ điều kiện kỹ thuật → chuyển sang hoàn thiện hồ sơ.  
   * **Không:** Kết luận chưa đủ điều kiện kỹ thuật → Sales thông báo khách hàng → kết thúc yêu cầu, không tạo Work Order.

5. **GW5 – XOR: Hồ sơ đầy đủ và hợp lệ?**  
   * **Có:** Chuyển sang xác nhận lịch lắp đặt.  
   * **Không:** Sales yêu cầu bổ sung/chỉnh sửa → Customer bổ sung/chỉnh sửa → Sales kiểm tra lại → quay về GW5.  
   Nhánh này tạo thành **Rework Loop** cho đến khi hồ sơ đạt yêu cầu.

6. **GW6 – XOR: Khách hàng đã xác nhận lịch lắp đặt?**  
   * **Đã xác nhận:** Sales gửi hợp đồng để khách hàng ký.  
   * **Chưa xác nhận:** Sales tiếp tục phối hợp xác nhận lịch; khi lịch được chốt, luồng quay lại GW6 và chuyển sang gửi hợp đồng.

7. **GW7 – XOR: Hình thức ký hợp đồng?**  
   * **Ký điện tử.**  
   * **Ký hợp đồng giấy.**  
   Hai nhánh hội tụ tại trạng thái **“Hợp đồng đã ký”**, sau đó Sales/BPMS/CRM tiếp tục xử lý chung.


**1. Pools & Lanes:**

* **Pool Khách hàng (Customer):** chọn kênh, cung cấp thông tin, xác nhận gói cước/nhu cầu, hoàn thiện/bổ sung hồ sơ, xác nhận lịch và ký hợp đồng.
* **Pool FPT Telecom:** có các Lane phù hợp với phạm vi quy trình:
  * **Lane Sales:** tiếp nhận, kiểm tra thông tin, tư vấn, lập hồ sơ sơ bộ, điều phối kiểm tra kỹ thuật, kiểm tra hồ sơ, xác nhận lịch, gửi/nhận hợp đồng và chuyển dữ liệu vào BPMS/CRM.
  * **Lane Technical:** kiểm tra hạ tầng cáp quang, kiểm tra Port, đánh giá khả năng cung cấp và trả kết quả.
  * **Lane BPMS/CRM:** ghi nhận hợp đồng, tạo Work Order, phân công đội kỹ thuật khu vực và cập nhật trạng thái.
* **Đội kỹ thuật khu vực:** tiếp nhận Work Order sau khi hệ thống phân công; đây là điểm chuyển giao sang quy trình triển khai lắp đặt.

**2. Phân loại Task Types:**

* **User Task:** Sales tiếp nhận và kiểm tra thông tin, tư vấn, lập hồ sơ sơ bộ, kiểm tra hồ sơ; Technical thực hiện kiểm tra và cập nhật kết quả; Customer thực hiện các bước xác nhận điện tử.
* **Manual Task:** Customer chuẩn bị hồ sơ giấy và ký hợp đồng giấy.
* **Service Task:** BPMS/CRM ghi nhận hợp đồng, tạo Work Order, phân công đội kỹ thuật và cập nhật trạng thái.
* **Send/Message Task:** Sales chuyển yêu cầu kiểm tra kỹ thuật, thông báo kết quả, yêu cầu bổ sung hồ sơ và gửi hợp đồng.

**3. Activity Markers:**

* **Loop Marker / Loop logic:** áp dụng cho cụm “kiểm tra hồ sơ → yêu cầu bổ sung/chỉnh sửa → khách hàng gửi lại → kiểm tra lại” tại GW5.

**4. Events:**

* **Start Event:** Khách hàng phát sinh nhu cầu sử dụng dịch vụ.
* **Intermediate Message Event:** thể hiện các điểm nhận phản hồi từ Customer hoặc Technical, đặc biệt tại các bước xác nhận gói cước, kết quả kỹ thuật và lịch lắp đặt.
* **End Event – Thành công:** Work Order được tạo, phân công cho đội kỹ thuật khu vực và trạng thái được cập nhật.
* **End Event – Không đủ điều kiện kỹ thuật:** kết thúc từ nhánh “Không” của GW3 hoặc GW4; không tạo Work Order.

**5. Information Artifacts:**

* **Data Objects:** thông tin đăng ký ban đầu; hồ sơ đăng ký sơ bộ; kết quả kiểm tra hạ tầng/Port; hồ sơ hoàn chỉnh; xác nhận lịch; hợp đồng đã ký; Work Order.
* **Data Store:** BPMS/CRM.

---

#### **b) Diễn giải chi tiết các luồng quy trình As-Is**

##### **1. Luồng chính – Happy Path:**

1. **Customer:** Phát sinh nhu cầu → **GW1** chọn một kênh đăng ký → cung cấp thông tin.
2. **Sales:** Tiếp nhận, kiểm tra thông tin → tư vấn gói cước.
3. **GW2:** Khách hàng **đã xác nhận** gói cước/nhu cầu → Sales lập hồ sơ đăng ký sơ bộ.
4. **Technical:** Tiếp nhận yêu cầu → kiểm tra hạ tầng cáp quang.
5. **GW3:** Hạ tầng **đáp ứng** → Technical kiểm tra Port.
6. **GW4:** **Có Port khả dụng** → xác nhận đủ điều kiện kỹ thuật.
7. **Sales / Customer:** Sales yêu cầu hoàn thiện hồ sơ → Customer gửi hồ sơ → Sales kiểm tra.
8. **GW5:** Hồ sơ **đầy đủ và hợp lệ** → chuyển sang xác nhận lịch.
9. **Sales / Customer:** Sales đề nghị xác nhận lịch → Customer phản hồi.
10. **GW6:** Lịch **đã được xác nhận** → Sales gửi hợp đồng.
11. **GW7:** Customer chọn **một** hình thức ký: điện tử hoặc giấy → hợp đồng đạt trạng thái đã ký.
12. **Sales / BPMS/CRM:** Sales tiếp nhận hợp đồng đã ký → chuyển dữ liệu vào hệ thống → BPMS/CRM ghi nhận hợp đồng → tạo Work Order → phân công đội kỹ thuật khu vực → cập nhật trạng thái.
13. **End Event:** Yêu cầu chuyển sang giai đoạn triển khai lắp đặt.

##### **2. Luồng phụ – GW2: Khách hàng chưa xác nhận gói cước/nhu cầu:**

1. Sales đã thực hiện tư vấn gói cước.
2. Tại **GW2**, trạng thái là **“Chưa xác nhận”**.
3. Quy trình **chưa lập hồ sơ đăng ký sơ bộ** và chưa chuyển sang Technical.
4. Sales tiếp tục tư vấn và làm rõ nhu cầu; khi khách hàng xác nhận, luồng quay lại GW2 và chuyển sang bước lập hồ sơ đăng ký sơ bộ.

##### **3. Luồng phụ – GW3: Hạ tầng cáp quang không đáp ứng:**

1. Technical kiểm tra hạ tầng cáp quang.
2. Tại **GW3**, kết quả là **“Không đáp ứng”**.
3. Kết quả được phản hồi để Sales thông báo khách hàng rằng yêu cầu chưa thể triển khai.
4. Quy trình kết thúc; không tạo Work Order.

##### **4. Luồng phụ – GW4: Không có Port khả dụng:**

1. Sau khi hạ tầng đáp ứng, Technical kiểm tra Port.
2. Tại **GW4**, kết quả là **“Không có Port khả dụng”**.
3. Yêu cầu được xác định chưa đủ điều kiện kỹ thuật; Sales thông báo khách hàng.
4. Quy trình kết thúc; không tạo Work Order.

##### **5. Luồng phụ – GW5: Hồ sơ thiếu hoặc chưa hợp lệ (Rework Loop):**

1. Customer gửi hồ sơ đăng ký.
2. Sales kiểm tra tính đầy đủ và hợp lệ.
3. Tại **GW5**, kết quả là **“Không”** → Sales yêu cầu bổ sung/chỉnh sửa.
4. Customer bổ sung/chỉnh sửa và gửi lại hồ sơ.
5. Sales kiểm tra lại → quay về **GW5**.
6. Chỉ khi GW5 = **“Có”**, quy trình mới chuyển sang xác nhận lịch lắp đặt.

##### **6. Luồng phụ – GW6: Khách hàng chưa xác nhận lịch lắp đặt:**

1. Sales đề nghị khách hàng xác nhận lịch.
2. Tại **GW6**, trạng thái là **“Chưa xác nhận”**.
3. Quy trình chưa chuyển sang gửi/ký hợp đồng và tiếp tục ở trạng thái chờ/xác nhận lịch.
4. Sales tiếp tục phối hợp xác nhận lịch; khi khách hàng chốt lịch, luồng quay lại GW6 và chuyển sang bước gửi hợp đồng.

##### **7. Luồng biến thể – GW1 và GW7:**

* **GW1:** một yêu cầu có thể đi vào từ Website, Hotline, cửa hàng hoặc nhân viên kinh doanh; khác biệt chỉ nằm ở cách thông tin đầu vào được tiếp nhận. Các nhánh hội tụ trước xử lý của Sales.
* **GW7:** khách hàng ký điện tử hoặc ký giấy; cả hai nhánh hội tụ tại trạng thái “Hợp đồng đã ký” rồi tiếp tục qua BPMS/CRM.

---

#### **c) Sơ đồ BPMN As-Is – Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt**

Sơ đồ dưới đây thể hiện toàn bộ luồng As-Is với **07 cổng quyết định XOR GW1–GW7**, hai nhánh kết thúc do không đủ điều kiện kỹ thuật, vòng lặp bổ sung hồ sơ và các điểm hội tụ trước khi tạo Work Order:

![Hình 3.3. Quy trình tư vấn, đăng ký và tiếp nhận yêu cầu lắp đặt Internet FPT Telecom](./docs/Quy%20trinh%20tu%20van%20lap%20dat%20FPT.png)
---

### **3.3.3. Phân tích định tính**

#### **3.3.3.1. Phân tích giá trị gia tăng**

Phân tích giá trị gia tăng phân loại các hoạt động theo ba nhóm:

* **VA (Value-Added):** Tạo giá trị trực tiếp cho khách hàng hoặc trực tiếp xác lập dịch vụ khách hàng lựa chọn.
* **BVA (Business Value-Added):** Không tạo giá trị cảm nhận trực tiếp nhưng cần thiết cho vận hành, kiểm soát hoặc tính hợp lệ của giao dịch.
* **NVA (Non-Value-Added):** Không làm tăng giá trị đầu ra, thường liên quan chuyển giao, tiếp nhận lặp lại hoặc xử lý lại và cần được giảm thiểu.

| STT | Hoạt động | Người thực hiện | Phân loại | Lập luận theo tiêu chuẩn phân loại |
| :---: | :--- | :--- | :---: | :--- |
| 1 | Lựa chọn kênh đăng ký | Customer | **BVA** | Cần để yêu cầu đi vào hệ thống tiếp nhận, nhưng bản thân việc chọn kênh không làm thay đổi giá trị dịch vụ. |
| 2 | Cung cấp thông tin đăng ký | Customer | **BVA** | Dữ liệu bắt buộc để nhận diện và xử lý yêu cầu. |
| 3 | Tiếp nhận và ghi nhận thông tin | Sales | **BVA** | Cần cho kiểm soát đầu vào và điều phối quy trình. |
| 4 | Tư vấn gói cước phù hợp | Sales | **VA** | Trực tiếp giúp khách hàng chọn dịch vụ phù hợp nhu cầu. |
| 5 | Xác nhận gói cước / nhu cầu sử dụng | Customer | **VA** | Xác lập lựa chọn dịch vụ mà khách hàng mong muốn. |
| 6 | Lập hồ sơ đăng ký sơ bộ | Sales | **BVA** | Cần để chuyển yêu cầu sang khâu kiểm tra kỹ thuật. |
| 7 | Chuyển yêu cầu sang Technical | Sales | **NVA** | Chuyển giao nội bộ không làm tăng giá trị; có thể tự động hóa. |
| 8 | Tiếp nhận yêu cầu kiểm tra | Technical | **NVA** | Thao tác tiếp nhận thuần túy, có thể giảm bằng tích hợp hệ thống. |
| 9 | Kiểm tra hạ tầng cáp quang | Technical | **BVA** | Điều kiện cần để tránh cam kết dịch vụ khi không thể triển khai. |
| 10 | Kiểm tra số lượng Port | Technical | **BVA** | Điều kiện kỹ thuật bắt buộc cho khả năng cấp dịch vụ. |
| 11 | Đánh giá điều kiện cung cấp dịch vụ | Technical | **BVA** | Điểm kiểm soát quyết định quy trình tiếp tục hay dừng. |
| 12 | Thông báo kết quả không đủ điều kiện | Technical / Sales | **BVA** | Cần để đóng yêu cầu đúng trạng thái và phản hồi khách hàng. |
| 13 | Yêu cầu khách hàng hoàn thiện hồ sơ | Sales | **BVA** | Hướng dẫn khách hàng đáp ứng điều kiện giao dịch. |
| 14 | Hoàn thiện/cung cấp hồ sơ lần đầu | Customer | **BVA** | Cần để ký hợp đồng và tạo Work Order hợp lệ. |
| 15 | Nhận hồ sơ khách hàng | Sales | **NVA** | Thao tác nhận/chuyển hồ sơ không làm tăng giá trị; có thể số hóa. |
| 16 | Kiểm tra tính đầy đủ, hợp lệ của hồ sơ | Sales | **BVA** | Kiểm soát chất lượng và tính hợp lệ trước khi ký hợp đồng. |
| 17 | Yêu cầu bổ sung/chỉnh sửa hồ sơ | Sales | **NVA** | Phát sinh do hồ sơ chưa đạt; là xử lý lại. |
| 18 | Bổ sung/chỉnh sửa hồ sơ theo yêu cầu | Customer | **NVA** | Rework do đầu vào chưa đúng ngay lần đầu. |
| 19 | Xác nhận/chốt lịch lắp đặt | Sales / Customer | **VA** | Xác lập cam kết thời điểm cung cấp dịch vụ theo nhu cầu khách hàng. |
| 20 | Ký hợp đồng điện tử hoặc giấy | Customer | **BVA** | Điều kiện pháp lý/nghiệp vụ để chính thức hóa đăng ký. |
| 21 | Ghi nhận hợp đồng trên BPMS/CRM | BPMS/CRM | **BVA** | Cần để lưu giao dịch và kích hoạt công việc tiếp theo. |
| 22 | Tạo Work Order | BPMS/CRM | **BVA** | Chuyển yêu cầu đã hợp lệ thành lệnh triển khai chính thức. |
| 23 | Phân công đội kỹ thuật khu vực | BPMS/CRM | **BVA** | Bắt buộc để Work Order có đơn vị thực hiện. |
| 24 | Lưu và theo dõi trạng thái đơn hàng | BPMS/CRM | **BVA** | Cần cho quản trị, truy vết và phối hợp giữa các bộ phận. |

**Tổng hợp phân loại:**

| Loại giá trị | Số hoạt động | Tỷ lệ |
| :---: | :---: | :---: |
| **VA** | 3 | **12,5%** |
| **BVA** | 16 | **66,7%** |
| **NVA** | 5 | **20,8%** |
| **Tổng** | **24** | **100%** |

> **Nhận xét:** BVA chiếm tỷ trọng lớn vì quy trình phải kiểm soát điều kiện kỹ thuật, hồ sơ, hợp đồng và tạo Work Order trước khi triển khai. NVA tập trung ở **handoff và rework**; đây là nhóm cần ưu tiên giảm bằng tích hợp dữ liệu, kiểm tra đầu vào và tự động chuyển trạng thái.

---

#### **3.3.3.2. Phân tích lãng phí**

Phân tích lãng phí theo Lean cho thấy các tổn thất chủ yếu tập trung ở thời gian chờ, chuyển giao thông tin, xử lý lặp lại và tồn đọng yêu cầu giữa các công đoạn. Bảy nhóm lãng phí được đánh giá như sau:

| Loại lãng phí Lean | Biểu hiện trong quy trình |
| :--- | :--- |
| **Waiting (Chờ đợi)** | Khách hàng chờ Sales liên hệ; Sales chờ Technical kiểm tra; chờ khách hàng bổ sung hồ sơ/ký hợp đồng; chờ Work Order được tạo/phân công. |
| **Transportation / Handoff (Chuyển giao)** | Dữ liệu đi qua nhiều điểm Customer → Sales → Technical → Sales → BPMS/CRM; nếu chuyển thủ công sẽ tăng độ trễ và nguy cơ sai lệch. |
| **Over-processing (Xử lý thừa)** | Thông tin có thể được xác nhận hoặc kiểm tra lại ở nhiều bước nếu các kênh tiếp nhận không chia sẻ một nguồn dữ liệu thống nhất. |
| **Defects / Rework (Lỗi và làm lại)** | Hồ sơ thiếu/sai/chưa hợp lệ dẫn đến yêu cầu bổ sung và lặp lại kiểm tra. Đây là biểu hiện NVA rõ nhất trong mô tả hiện có. |
| **Over-production (Xử lý trước nhu cầu)** | Không ghi nhận là lãng phí trọng tâm trong luồng As-Is; Work Order chỉ được tạo sau khi hoàn tất các điều kiện đăng ký và ký hợp đồng. |
| **Inventory / Backlog (Tồn đọng công việc)** | Các yêu cầu chờ Sales xử lý, chờ kết quả Technical hoặc chờ khách hàng hoàn thiện hồ sơ hình thành hàng đợi công việc và làm tăng Cycle Time. |
| **Motion (Thao tác không cần thiết)** | Phát sinh ở các thao tác tra cứu, xác nhận lại hoặc nhập lại cùng một thông tin khi dữ liệu giữa kênh tiếp nhận và BPMS/CRM chưa được liên thông xuyên suốt. |

**Định hướng cải tiến từ phân tích lãng phí:**

* Chuẩn hóa và kiểm tra dữ liệu đầu vào ngay tại điểm tiếp nhận.
* Tích hợp các kênh Website/Hotline/cửa hàng/Sales vào nguồn dữ liệu dùng chung.
* Tự động chuyển yêu cầu đạt điều kiện sang Technical.
* Đồng bộ kết quả kiểm tra hạ tầng và Port về BPMS/CRM.
* Sử dụng checklist hồ sơ và validation bắt buộc để tăng tỷ lệ hồ sơ đúng ngay lần đầu.
* Thông báo trạng thái tự động cho Customer/Sales để giảm thao tác hỏi–đáp và theo dõi thủ công.
* Theo dõi số lượng case tồn, thời gian chờ và số vòng Rework theo từng công đoạn.

---

#### **3.3.3.3. Phân tích các bên liên quan (Stakeholder Analysis)**

| Bên liên quan | Mức độ ảnh hưởng | Vai trò & kỳ vọng | Rủi ro khi quy trình không hiệu quả |
| :--- | :---: | :--- | :--- |
| **Khách hàng** | **Rất cao** | Được tư vấn đúng; biết sớm khả năng triển khai; thủ tục đơn giản; lịch lắp đặt rõ ràng. | Chờ lâu, cung cấp lại thông tin, trải nghiệm kém, có thể từ bỏ đăng ký. |
| **Sales** | **Rất cao** | Tiếp nhận và điều phối nhanh; hồ sơ đạt chuẩn; có trạng thái rõ để theo dõi. | Quá tải thao tác, nhiều Rework, mất thời gian theo dõi/chuyển giao. |
| **Technical** | **Rất cao** | Nhận đủ dữ liệu để kiểm tra; truy cập được thông tin hạ tầng/Port chính xác. | Kiểm tra chậm hoặc trả kết quả sai, gây cam kết sai khả năng cung cấp. |
| **BPMS/CRM** | **Rất cao** | Dữ liệu nhất quán; tạo/phân công Work Order đúng trạng thái. | Sai dữ liệu, tạo đơn chậm/trùng, khó truy vết tiến độ. |
| **Đội kỹ thuật khu vực** | **Cao** | Nhận Work Order có đủ thông tin và lịch lắp đặt để triển khai. | Phải xác minh lại, đổi lịch, giảm hiệu suất thi công. |
| **Bộ phận quản lý vận hành** | **Cao** | Theo dõi SLA, tỷ lệ chuyển đổi, Rework và bottleneck của quy trình. | Thiếu dữ liệu để đánh giá hiệu suất và ưu tiên cải tiến. |

---

### **3.3.4. Phân tích định lượng**

Phân tích định lượng sử dụng bộ số liệu ước tính về thời gian xử lý, thời gian chờ và đơn giá nguồn lực để lượng hóa **Process Time, Cycle Time, Time Efficiency** và chi phí xử lý của một yêu cầu đăng ký. Các giá trị này phục vụ mô hình phân tích quy trình và không được xem là số liệu vận hành công bố của FPT Telecom.

#### **3.3.4.1. Định lượng thời gian**

**Thời gian xử lý trực tiếp của từng hoạt động (một lượt xử lý):**

| STT | Hoạt động | Tác nhân | TG ngắn nhất (phút) | TG dài nhất (phút) |
| :---: | :--- | :--- | :---: | :---: |
| 1 | Cung cấp thông tin đăng ký | Customer | 5 | 10 |
| 2 | Tiếp nhận và ghi nhận thông tin | Sales | 5 | 10 |
| 3 | Tư vấn gói cước | Sales | 10 | 20 |
| 4 | Lập hồ sơ đăng ký sơ bộ | Sales | 10 | 20 |
| 5 | Tiếp nhận yêu cầu kiểm tra | Technical | 5 | 10 |
| 6 | Kiểm tra hạ tầng cáp quang | Technical | 15 | 30 |
| 7 | Kiểm tra số lượng Port | Technical | 5 | 10 |
| 8 | Đánh giá điều kiện cung cấp dịch vụ | Technical | 5 | 10 |
| 9 | Kiểm tra tính đầy đủ, hợp lệ của hồ sơ | Sales | 10 | 20 |
| 10 | Hoàn thiện/cung cấp hồ sơ theo yêu cầu | Customer | 5 | 15 |
| 11 | Điều phối và chốt lịch lắp đặt | Sales | 5 | 10 |
| 12 | Ký hợp đồng | Customer | 5 | 10 |
| 13 | Ghi nhận hợp đồng trên BPMS/CRM | BPMS/CRM | 2 | 5 |
| 14 | Tạo Work Order | BPMS/CRM | 2 | 5 |
| 15 | Phân công đội kỹ thuật khu vực | BPMS/CRM | 3 | 10 |
| 16 | Lưu và cập nhật trạng thái | BPMS/CRM | 2 | 5 |

**Process Time ngắn nhất:**

`5 + 5 + 10 + 10 + 5 + 15 + 5 + 5 + 10 + 5 + 5 + 5 + 2 + 2 + 3 + 2 = 94 phút`

**Process Time dài nhất:**

`10 + 10 + 20 + 20 + 10 + 30 + 10 + 10 + 20 + 15 + 10 + 10 + 5 + 5 + 10 + 5 = 200 phút`


> Khoảng **94–200 phút** phản ánh thời gian xử lý trực tiếp của một lượt theo luồng chính. Các Gateway là điểm quyết định nên không cộng thời gian riêng; thời gian xác nhận tại GW1, GW2, GW6 và GW7 được tính trong các hoạt động liên quan. Vòng lặp GW5 làm tăng Process Time khi hồ sơ phải bổ sung hoặc chỉnh sửa.


**Thời gian chờ sử dụng trong mô hình phân tích:**

| Điểm chờ | Best-case | Worst-case |
| :--- | ---: | ---: |
| Chờ Sales tiếp nhận/liên hệ | 30 phút | 120 phút |
| Chờ Technical tiếp nhận | 30 phút | 120 phút |
| Chờ kết quả kiểm tra/phản hồi | 30 phút | 180 phút |
| Chờ khách hàng hoàn thiện hồ sơ và ký hợp đồng | 30 phút | 120 phút |
| **Tổng thời gian chờ** | **120 phút** | **540 phút** |

**Cycle Time:**

* **Best-case:** `94 + 120 = 214 phút` = **3 giờ 34 phút**.
* **Worst-case:** `200 + 540 = 740 phút` = **12 giờ 20 phút**.

**Hiệu suất thời gian (Time Efficiency):**

| Trường hợp | Process Time | Cycle Time | Waiting Time | Hiệu suất thời gian |
| :---: | ---: | ---: | ---: | ---: |
| **Best-case** | 94 phút | 214 phút | 120 phút | **43,93%** |
| **Worst-case** | 200 phút | 740 phút | 540 phút | **27,03%** |

Công thức:

`Time Efficiency = Process Time / Cycle Time × 100%`

**Thời gian xử lý theo tác nhân:**

| Tác nhân | TG ngắn nhất | TG dài nhất | Nhận xét |
| :--- | ---: | ---: | :--- |
| **Customer** | 15 phút | 35 phút | Không tính vào chi phí lao động nội bộ nhưng ảnh hưởng trực tiếp trải nghiệm khách hàng. |
| **Sales** | 40 phút | 80 phút | Tham gia nhiều công đoạn nhất và là đầu mối điều phối. |
| **Technical** | 30 phút | 60 phút | Tập trung ở bước kiểm tra và quyết định khả năng cung cấp. |
| **BPMS/CRM** | 9 phút | 25 phút | Thời gian xử lý quy đổi thấp hơn do phần lớn hoạt động được hệ thống hỗ trợ. |
| **Tổng** | **94 phút** | **200 phút** | Khớp với Process Time của một lượt xử lý. |

> **Nhận xét:** Thời gian chờ chiếm **56,1% Cycle Time trong best-case** (120/214) và khoảng **73,0% trong worst-case** (540/740). Đây là thành phần ảnh hưởng lớn nhất đến hiệu suất thời gian của quy trình, đặc biệt tại các điểm chuyển giao giữa Sales, Technical và khách hàng.


---

#### **3.3.4.2. Định lượng chi phí**

**Đơn giá nguồn lực quy đổi sử dụng trong mô hình:**

| Tác nhân / nguồn lực | Đơn giá quy đổi | Chi phí/phút |
| :--- | ---: | ---: |
| **Sales** | 50.000 VNĐ/giờ | **833,33 VNĐ/phút** |
| **Technical** | 60.000 VNĐ/giờ | **1.000 VNĐ/phút** |
| **BPMS/CRM** | 55.000 VNĐ/giờ | **916,67 VNĐ/phút** |

> Chi phí BPMS/CRM là chi phí vận hành hệ thống quy đổi theo thời gian xử lý. Thời gian của Customer không được tính vào chi phí vận hành nội bộ của doanh nghiệp.

**Chi phí theo từng tác nhân trên một yêu cầu:**

| Tác nhân | TG best-case | Chi phí best-case | TG worst-case | Chi phí worst-case |
| :--- | ---: | ---: | ---: | ---: |
| **Sales** | 40 phút | **33.333 VNĐ** | 80 phút | **66.667 VNĐ** |
| **Technical** | 30 phút | **30.000 VNĐ** | 60 phút | **60.000 VNĐ** |
| **BPMS/CRM** | 9 phút | **8.250 VNĐ** | 25 phút | **22.917 VNĐ** |
| **Tổng nội bộ** | **79 phút** | **71.583 VNĐ** | **165 phút** | **149.584 VNĐ** |

> Chi phí được làm tròn đến đơn vị đồng.

**Tỷ trọng chi phí nội bộ trong best-case:**

* **Sales:** `33.333 / 71.583 × 100% = 46,57%`.
* **Technical:** `30.000 / 71.583 × 100% = 41,91%`.
* **BPMS/CRM:** `8.250 / 71.583 × 100% = 11,52%`.


> **Nhận xét:** Sales và Technical chiếm phần lớn chi phí xử lý nội bộ. Việc giảm thao tác chuyển giao, hạn chế Rework và tăng mức độ liên thông dữ liệu sẽ tác động trực tiếp đến cả Cycle Time và chi phí xử lý.

---
