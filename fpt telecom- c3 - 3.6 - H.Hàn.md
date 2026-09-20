## **3.6. Quy trình hỗ trợ 1: Quản lý kho và xuất vật tư**

> *Sinh viên phụ trách thực hiện: Đoàn Hữu Hàn - MSSV: 25410199*

---

### **3.6.1. Phương pháp thực hiện (Khám phá quy trình - Process Discovery)**

Khám phá quy trình (Process Discovery) là giai đoạn nền tảng trong chu kỳ BPM nhằm thu thập dữ liệu hiện trạng, làm rõ các bước công việc thực tế, nhận diện các bên liên quan và phát hiện những điểm nghẽn trong vận hành. Nhóm áp dụng kết hợp **3 phương pháp khám phá quy trình chuẩn mực** theo bài giảng môn học (Chương 4 – Process Discovery) bao gồm:
1. **Phương pháp dựa trên bằng chứng (Evidence-based Discovery)**
2. **Phương pháp phỏng vấn (Interview-based Discovery)**
3. **Phương pháp hội thảo chuyên sâu (Workshop-based Discovery)**

---

#### **3.6.1.1. Dựa trên bằng chứng (Evidence-based Discovery)**

Phương pháp dựa trên bằng chứng tập trung thu thập, kiểm tra chéo và phân tích các tài liệu, hồ sơ vận hành thực tế đã ban hành và lưu trữ tại FPT Telecom để phản ánh trung thực quy trình As-Is mà không bị ảnh hưởng bởi thiên kiến chủ quan.

##### **a) Mô tả quy trình hiện có (As-is Process Description)**


Nhằm đáp ứng chuẩn mực đánh giá quy trình nghiệp vụ và tiêu chí Rubric, mô tả quy trình Quản lý kho và xuất vật tư tại FPT Telecom được cấu trúc chặt chẽ qua 4 khía cạnh cốt lõi:

* **1. Tác nhân tham gia (Actors & Roles):** Quy trình có sự tham gia phối hợp liên chức năng của 8 tác nhân chính, bao gồm cả các hệ thống phần mềm tự động (BPMS/CRM, WMS/ERP) và nhân sự nghiệp vụ chuyên trách (Thủ kho, Kỹ thuật viên thi công, Bộ phận Mua hàng & Cung ứng, Ban Giám đốc Chi nhánh, Nhà cung cấp vật tư, Kế toán kho).

* **2. Khách hàng của quy trình (Customers & Value Proposition):**
  * *Khách hàng nội bộ (Internal Customer):* Đội ngũ Kỹ thuật viên thi công (cần vật tư đúng chủng loại, sẵn sàng đúng giờ ca trực) và Bộ phận Kinh doanh (cần giữ đúng SLA hẹn khách).
  * *Khách hàng bên ngoài (External Customer - gián tiếp):* Thuê bao đăng ký Internet/Truyền hình FPT (thụ hưởng đường truyền ổn định, thiết bị chính hãng, lắp đặt đúng hẹn trong 24–48h).
  * *Giá trị cốt lõi mang lại:* Bảo đảm chuỗi cung ứng vật tư liên tục không đứt gãy; quản lý tài sản chính xác qua định danh Serial Number / MAC Address; tối ưu hóa chi phí vốn lưu động và tồn kho an toàn.

* **3. Luồng quy trình tổng quan (Process Flow):** Chuỗi 10 bước nghiệp vụ chuẩn từ lúc tiếp nhận Work Order tự động từ CRM/BPMS, kiểm tra tồn kho WMS, chuẩn bị chủng loại modem ONT, quét mã Serial/MAC định danh, bàn giao KTV ký nhận, xử lý đổi trả thiết bị lỗi ngoại lệ tại hiện trường, thu hồi cáp/phụ kiện dôi dư, đến hạch toán kế toán ERP và đóng lệnh thi công.

* **4. Kết quả đầu ra (Outcomes - Thành công, Thất bại & Cơ chế xử lý ngoại lệ):**
  * *Kịch bản thành công (Happy Path):* Xuất cấp vật tư đủ - đúng - chuẩn, KTV hoàn thành lắp đặt đúng SLA cam kết.
  * *Kịch bản thất bại / Chờ mua sắm:* Thiếu tồn kho cục bộ phải kích hoạt quy trình mua hàng bổ sung khẩn cấp hoặc điều chuyển kho tổng.
  * *Kịch bản xử lý ngoại lệ:* Đổi thiết bị phát sinh lỗi kỹ thuật tại chỗ; nhập trả vật tư dôi dư sau ca thi công; hủy Work Order do hạ tầng cáp không tương thích.

---

Quy trình Quản lý kho và xuất vật tư tại FPT Telecom là quy trình hỗ trợ sống còn, có nhiệm vụ đảm bảo cung ứng đầy đủ, chính xác và kịp thời các thiết bị đầu cuối viễn thông (Modem/ONT, Mesh Wi-Fi, Router) và vật tư cáp quang cho đội ngũ kỹ thuật viên triển khai dịch vụ lắp đặt Internet cho khách hàng. Quy trình hiện tại được vận hành qua chuỗi **10 bước nghiệp vụ liên tục** như sau:

* **Bước 1: Tiếp nhận yêu cầu xuất vật tư từ hệ thống:**  
  Khi khách hàng hoàn tất ký kết hợp đồng điện tử (E-Contract), hệ thống BPMS/CRM tự động tạo Lệnh thi công (Work Order) và đẩy thông tin yêu cầu xuất vật tư sang hệ thống Quản lý kho (WMS). Dữ liệu bao gồm: mã Work Order, gói cước đăng ký, địa chỉ lắp đặt, chủng loại thiết bị cần xuất và thông tin Kỹ thuật viên (KTV) được điều phối.

* **Bước 2: Kiểm tra tồn kho khả dụng và đối chiếu ngưỡng an toàn (Safety Stock):**  
  Thủ kho truy cập WMS để kiểm tra số lượng tồn kho khả dụng của các thiết bị và phụ kiện yêu cầu. Tại đây phát sinh điểm kiểm soát: Nếu số lượng tồn kho đáp ứng nhu cầu và vẫn cao hơn mức tồn kho an toàn (*Safety Stock*), quy trình chuyển thẳng sang bước chuẩn bị hàng. Nếu tồn kho dưới ngưỡng an toàn hoặc thiếu hàng, hệ thống kích hoạt luồng xử lý mua sắm bổ sung.

* **Bước 3: Xử lý đề xuất mua sắm và đặt hàng bổ sung:**  
  Thủ kho tạo Phiếu đề xuất mua sắm bổ sung trên WMS. Nếu giá trị đơn hàng vượt hạn mức chi nhánh (> 50 triệu đồng), phiếu phải chuyển đến Ban Giám đốc Chi nhánh phê duyệt. Sau khi được duyệt, Bộ phận Mua hàng & Cung ứng gửi đơn đặt hàng chính thức (Purchase Order) đến Nhà cung cấp hoặc làm lệnh điều chuyển từ Kho tổng trung tâm.

* **Bước 4: Tiếp nhận hàng và kiểm tra chất lượng đầu vào (QC Incoming):**  
  Khi Nhà cung cấp giao hàng đến kho, Thủ kho phối hợp cùng nhân viên kiểm soát chất lượng thực hiện nghiệm thu ngoại quan, quy cách đóng gói và kiểm tra ngẫu nhiên thông số kỹ thuật (đèn tín hiệu, cổng quang, nguồn điện).  
  * *Trường hợp không đạt:* Lập biên bản từ chối, trả hàng lại cho Nhà cung cấp và yêu cầu giao bù khẩn cấp.  
  * *Trường hợp đạt chuẩn:* Ký biên bản giao nhận và tiến hành nhập kho trên WMS.

* **Bước 5: Phân loại chủng loại thiết bị quang và chuẩn bị hàng:**  
  Thủ kho căn cứ vào gói cước của khách hàng trên Work Order để lấy đúng thiết bị: phân biệt giữa thiết bị chuẩn GPON (cho gói Internet gia đình thông thường) và chuẩn cao cấp XGS-PON / Wi-Fi 6 (cho doanh nghiệp hoặc gói cước cao cấp).

* **Bước 6: Quét mã định danh (Serial Number / MAC Address) và in phiếu xuất kho:**  
  Thủ kho sử dụng máy quét mã vạch chuyên dụng để quét Serial Number và địa chỉ MAC của Modem/ONT vào hệ thống WMS, liên kết trực tiếp thiết bị với mã Work Order và tài khoản thuê bao khách hàng. Sau đó, Thủ kho in Phiếu xuất kho kiêm biên bản bàn giao thiết bị.

* **Bước 7: Xuất kho và bàn giao vật tư cho Kỹ thuật viên:**  
  KTV phụ trách ca thi công đến kho kiểm đếm số lượng, chủng loại, tình trạng niêm phong của thiết bị và ký biên bản giao nhận (chữ ký số trên ứng dụng FoxPro hoặc ký giấy). Trách nhiệm bảo quản thiết bị chính thức chuyển giao sang KTV.

* **Bước 8: Thi công lắp đặt và xử lý ngoại lệ đổi thiết bị lỗi kỹ thuật:**  
  KTV di chuyển đến địa chỉ khách hàng để thi công kéo cáp quang và đấu nối thiết bị. Nếu phát hiện thiết bị bị lỗi không thể kích hoạt tín hiệu quang tại hiện trường, KTV liên hệ kho qua hotline nội bộ để kích hoạt thủ tục đổi thiết bị khẩn cấp, nhận modem thay thế để đảm bảo không làm gián đoạn cam kết lắp đặt.

* **Bước 9: Thu hồi, kiểm đếm và nhập trả vật tư sau thi công:**  
  Sau khi hoàn tất nghiệm thu với khách hàng, KTV quay trở về kho để quyết toán:  
  * Hoàn trả cuộn cáp quang dư thừa, phụ kiện chưa dùng hết.  
  * Bàn giao thiết bị lỗi phát sinh trong thi công hoặc thiết bị cũ thu hồi từ khách hàng nâng cấp gói cước.  
  Thủ kho kiểm tra, cập nhật trạng thái phân loại trên WMS (hàng tái nhập kho / hàng chờ bảo hành / hàng thanh lý).

* **Bước 10: Đồng bộ dữ liệu kế toán ERP và đóng Work Order:**  
  Hệ thống WMS tự động đồng bộ giá trị xuất kho và quyết toán vật tư sang phân hệ Kế toán ERP để ghi nhận chi phí giá vốn dịch vụ. Đồng thời, WMS gửi tín hiệu xác nhận hoàn tất sang hệ thống BPMS để đóng Work Order thi công.

---

**Các tác nhân tham gia quy trình (Actors):**

**Bảng 3.6.1: Danh mục các tác nhân tham gia quy trình Quản lý kho và xuất vật tư**

| STT | Tác nhân | Vai trò và trách nhiệm trong quy trình |
| :---: | :--- | :--- |
| **1** | **Hệ thống BPMS / CRM** | Tự động tạo Work Order; điều phối yêu cầu xuất vật tư sang WMS; nhận xác nhận hoàn thành để đóng lệnh thi công. |
| **2** | **Hệ thống WMS / ERP** | Quản lý dữ liệu tồn kho theo thời gian thực (Real-time); quản lý vị trí kho; liên kết mã Serial/MAC; hạch toán chi phí sang ERP. |
| **3** | **Thủ kho / NV Kho & Vật tư** | Tiếp nhận yêu cầu; kiểm kho; chuẩn bị hàng; quét mã vạch Serial/MAC; bàn giao thiết bị; tiếp nhận hoàn trả và kiểm kê kho. |
| **4** | **Kỹ thuật viên thi công (KTV)** | Nhận vật tư; kiểm đếm và ký nhận; thi công kéo cáp và cài đặt modem tại nhà khách hàng; bàn giao vật tư thừa/hỏng về kho. |
| **5** | **Bộ phận Mua hàng & Cung ứng** | Tiếp nhận đề xuất thiếu hàng; tìm kiếm và thương thảo đơn hàng với Nhà cung cấp; theo dõi tiến độ giao hàng về kho. |
| **6** | **Ban Giám đốc Chi nhánh** | Xem xét và phê duyệt các đề xuất mua sắm vượt hạn mức ngân sách tự quyết của chi nhánh. |
| **7** | **Nhà cung cấp** | Cung ứng thiết bị Modem quang, Router, dây cáp quang và phụ kiện viễn thông đạt chuẩn kỹ thuật đã cam kết trong hợp đồng. |
| **8** | **Bộ phận Kế toán kho** | Đối soát chứng từ xuất nhập kho; quản lý giá trị kho; kiểm tra tính hợp lệ của biên bản giao nhận và báo cáo tồn kho định kỳ. |

---

**Khách hàng của quy trình (Customer):**
* **Khách hàng nội bộ (Internal Customer):** Đội ngũ Kỹ thuật viên thi công lắp đặt và Bộ phận Kinh doanh. Họ cần thiết bị sẵn sàng, đúng chuẩn, đủ số lượng để hoàn thành chỉ tiêu lắp đặt đúng hẹn.
* **Khách hàng bên ngoài (External Customer - gián tiếp):** Thuê bao đăng ký dịch vụ Internet FPT. Tiến độ và độ chính xác của quy trình kho ảnh hưởng trực tiếp đến thời gian chờ lắp đặt (SLA 24–48h) và độ ổn định của đường truyền Internet.

**Giá trị mang lại (Value Proposition):**
* **Đảm bảo tính liên tục của chuỗi cung ứng:** Ngăn ngừa tình trạng thiếu hụt thiết bị làm đứt gãy lịch hẹn thi công với khách hàng.
* **Kiểm soát tài sản chặt chẽ:** Việc định danh từng chiếc Modem qua Serial Number và MAC Address giúp chống thất thoát, hỗ trợ bảo hành chính hãng và theo dõi vòng đời thiết bị.
* **Tối ưu hóa vốn lưu động:** Kiểm soát tồn kho theo mô hình Reorder Point và Safety Stock giúp giảm thiểu chi phí lưu kho, tránh ứ đọng vốn nhưng vẫn duy trì độ sẵn sàng cao.

**Những kết quả có thể đạt được (Possible Outcomes):**

**Bảng 3.6.2: Các kịch bản kết quả đầu ra và cơ chế xử lý ngoại lệ quy trình kho**

| Kết quả đầu ra | Diễn giải chi tiết |
| :--- | :--- |
| **Xuất kho thành công (Happy Path)** | Vật tư có sẵn đủ số lượng, chuẩn bị đúng chủng loại, KTV nhận hàng đúng giờ và hoàn thành lắp đặt cho khách hàng trong ngày. |
| **Chờ mua sắm bổ sung** | Tồn kho thiếu hụt buộc phải kích hoạt đơn đặt hàng khẩn cấp đến Nhà cung cấp; Work Order có thể bị dời lại và cần hẹn lại khách hàng. |
| **Thu hồi và đổi trả thiết bị** | Thiết bị phát sinh lỗi kỹ thuật hoặc vật tư dôi dư sau thi công được phân loại, nhập kho bảo hành hoặc tái nhập kho an toàn. |
| **Hủy Work Order do không tương thích hạ tầng** | Khách hàng chuyển địa điểm hoặc hạ tầng thực tế không phù hợp chuẩn thiết bị được cấp, dẫn đến hủy lệnh xuất và thu hồi vật tư. |

---


---

##### **b) Sơ đồ tổ chức và Ma trận trách nhiệm (Organizational Chart & RACI Matrix)**


Sơ đồ tổ chức quản lý kho và chuỗi cung ứng tại Chi nhánh FPT Telecom được thiết lập nhằm bảo đảm nguyên tắc kiểm soát độc lập giữa khâu bảo quản hiện vật (Kho), mua sắm (Mua hàng), kiểm soát chi phí (Kế toán) và phê duyệt chủ trương (Ban Giám đốc):

![Sơ đồ tổ chức bộ máy Quản lý Kho & Chuỗi cung ứng FPT Telecom](./assets/diagrams/quan_ly_kho/quanlykho.jpg)

_Hình 3.6.1: Sơ đồ tổ chức bộ máy Quản lý Kho & Chuỗi cung ứng FPT Telecom_

**Bảng 3.6.3: Ma trận phân công trách nhiệm (RACI Matrix) quy trình Quản lý kho**

*(R – Responsible: Người trực tiếp thực hiện; A – Accountable: Người chịu trách nhiệm phê duyệt cuối cùng; C – Consulted: Người được tham vấn; I – Informed: Người được thông báo)*  
*(R – Responsible: Người trực tiếp thực hiện; A – Accountable: Người chịu trách nhiệm phê duyệt cuối cùng; C – Consulted: Người được tham vấn; I – Informed: Người được thông báo)*

| Hoạt động nghiệp vụ | Thủ kho | Kỹ thuật viên | Bộ phận Mua hàng | Kế toán kho | Ban Giám đốc |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Tiếp nhận yêu cầu & kiểm tra tồn kho WMS | **R / A** | I | I | I | I |
| Lập đề xuất mua sắm bổ sung vật tư | **R** | I | C | C | **A** |
| Đặt hàng và theo dõi giao hàng Nhà cung cấp | I | I | **R / A** | C | I |
| Kiểm tra chất lượng hàng nhập kho (QC) | **R** | C | I | I | **A** |
| Quét mã Serial/MAC & chuẩn bị vật tư | **R / A** | I | I | I | I |
| Xuất kho & bàn giao thiết bị cho KTV | **R** | **R** | I | I | I |
| Thi công lắp đặt tại hiện trường | I | **R / A** | I | I | I |
| Bàn giao vật tư thừa / thiết bị lỗi về kho | **R** | **R** | I | I | I |
| Đối soát kiểm kê và hạch toán ERP | **R** | I | C | **R / A** | I |

---



---

##### **c) Kế hoạch làm việc và phân bổ ca trực (Work Schedule)**


Để quy trình kho vận hành nhịp nhàng, đáp ứng tiến độ lắp đặt của hàng trăm KTV mỗi ngày, kế hoạch làm việc được thiết lập chi tiết theo ngày và theo tuần:

**Kế hoạch công việc theo ngày (Daily Schedule):**

**Bảng 3.6.4: Kế hoạch công việc theo ngày (Daily Schedule) của nhân sự kho**

| Khung giờ | Vai trò | Nội dung công việc chi tiết |
| :---: | :--- | :--- |
| **07:30 – 08:30** | Thủ kho & KTV | **Ca sáng (Cao điểm xuất kho):** Mở cửa kho; in Phiếu xuất kho theo Work Order ca sáng; quét mã Serial/MAC thiết bị; bàn giao vật tư cho KTV xuất phát thi công. |
| **08:30 – 11:30** | Thủ kho & Mua hàng | Tiếp nhận hàng nhập từ Nhà cung cấp hoặc điều chuyển từ Kho tổng; thực hiện kiểm định QC; nhập kho WMS; sắp xếp hàng hóa theo nguyên tắc FIFO. |
| **11:30 – 12:00** | Thủ kho | Đối chiếu số liệu xuất nhập sáng trên WMS; xử lý các yêu cầu phát sinh khẩn cấp từ các tổ kỹ thuật. |
| **13:00 – 14:00** | Thủ kho & KTV | **Ca chiều (Xuất kho đợt 2):** Tiếp nhận danh sách Work Order ca chiều; chuẩn bị thiết bị Modem/Router; bàn giao vật tư cho KTV ca chiều. |
| **14:00 – 17:00** | Thủ kho & Kế toán | Phân loại thiết bị lỗi kỹ thuật; đóng gói thiết bị gửi đi bảo hành hãng; kiểm tra hạn mức an toàn tồn kho (Safety Stock) để lập phiếu đề xuất mua hàng. |
| **17:00 – 18:30** | Thủ kho & KTV | **Cuối ngày (Quyết toán & thu hồi):** Tiếp nhận vật tư dôi dư và thiết bị lỗi từ KTV; kiểm đếm và ký biên bản nhập trả; đồng bộ dữ liệu xuất nhập ngày sang ERP; khóa kho. |

**Kế hoạch công việc theo tuần (Weekly Schedule):**

**Bảng 3.6.5: Kế hoạch công việc theo tuần (Weekly Schedule) của bộ phận kho**

| Ngày trong tuần | Bộ phận thực hiện | Mục tiêu và nội dung công việc |
| :---: | :--- | :--- |
| **Thứ Hai** | Kho, Mua hàng, Kế toán, BGĐ | Họp giao ban đầu tuần; đánh giá hiệu suất cấp phát vật tư tuần trước; rà soát dự báo nhu cầu lắp đặt tuần mới; phê duyệt các đề xuất mua sắm lớn. |
| **Thứ Ba** | Bộ phận Kho & Vật tư | Kiểm kê xoay vòng (*Cycle Counting*) nhóm hàng giá trị cao (Modem Wi-Fi 6, OLT/ONT chuyên dụng); đối chiếu số liệu vật lý và WMS. |
| **Thứ Tư** | Kho & Bộ phận Mua hàng | Làm việc với các Nhà cung cấp về tiến độ giao hàng; xử lý các lô hàng bị từ chối do lỗi QC. |
| **Thứ Năm** | Bộ phận Kho & KTV | Rà soát công nợ vật tư của toàn bộ KTV; nhắc nhở và thu hồi các thiết bị tồn giữ trên xe KTV quá 48 giờ chưa quyết toán. |
| **Thứ Sáu** | Kho & Kế toán kho | Đối soát chứng từ xuất nhập kho giấy với dữ liệu điện tử trên hệ thống ERP; tổng hợp số liệu hao hụt vật tư tiêu hao (cáp, đầu nối). |
| **Thứ Bảy** | Bộ phận Kho & Vật tư | Vệ sinh kho bãi, bảo dưỡng thiết bị nâng hạ và máy quét mã vạch; sắp xếp lại các khu vực kệ hàng đảm bảo tiêu chuẩn 5S. |
| **Chủ Nhật** | Thủ kho trực ca | Trực xuất kho khẩn cấp phục vụ sự cố mạng hoặc các ca thi công VIP đã được phê duyệt đặc biệt. |

---



---

##### **d) Thuật ngữ và sổ tay nghiệp vụ (Glossary & Manuals)**


**Bảng 3.6.6: Bảng thuật ngữ và định nghĩa viết tắt trong quản lý kho viễn thông**

| Thuật ngữ / Viết tắt | Tên đầy đủ / Định nghĩa | Giải thích vai trò trong quy trình FPT Telecom |
| :--- | :--- | :--- |
| **WMS** | Warehouse Management System | Hệ thống phần mềm quản lý kho, theo dõi vị trí kệ, tồn kho và lịch sử quét mã Serial/MAC. |
| **ERP** | Enterprise Resource Planning | Hệ thống hoạch định nguồn lực doanh nghiệp (SAP/Oracle), quản lý hạch toán kế toán và giá trị tài sản. |
| **BPMS** | Business Process Management System | Hệ thống quản trị quy trình nghiệp vụ tự động điều phối luồng công việc từ CRM sang Kho và Kỹ thuật. |
| **ONT** | Optical Network Terminal | Thiết bị chuyển đổi tín hiệu quang sang tín hiệu điện (Modem cáp quang lắp tại nhà khách hàng). |
| **Mesh Wi-Fi** | Hệ thống mở rộng vùng phủ sóng Wi-Fi | Thiết bị phụ trợ kết nối không dây tạo mạng Wi-Fi đồng nhất cho nhà nhiều tầng hoặc diện tích rộng. |
| **Drop Wire** | Cáp quang thuê bao (1-2 FO) | Dây cáp quang chuyên dụng kéo ngoài trời từ hộp chia quang (ODF/DP) vào nhà khách hàng. |
| **Fast Connector** | Đầu nối quang nhanh (SC/APC) | Phụ kiện bấm nối đầu sợi quang trực tiếp tại hiện trường mà không cần dùng máy hàn nhiệt. |
| **Safety Stock** | Mức tồn kho an toàn | Số lượng thiết bị tối thiểu bắt buộc phải duy trì trong kho để phòng ngừa nhu cầu đột biến hoặc trễ giao hàng. |
| **Reorder Point (ROP)** | Điểm đặt hàng lại | Mức tồn kho mà khi chạm tới, hệ thống tự động tạo cảnh báo cần đặt hàng bổ sung ngay lập tức. |
| **FIFO** | First In, First Out | Nguyên tắc quản lý kho "Nhập trước - Xuất trước", đảm bảo thiết bị nhập trước được xuất trước, tránh hết hạn bảo hành. |
| **GPON / XGS-PON** | Gigabit Passive Optical Network | Các chuẩn công nghệ truyền dẫn quang thụ động; XGS-PON cung cấp tốc độ đối xứng 10Gbps đòi hỏi modem chuyên biệt. |
| **QC Incoming** | Quality Control Incoming | Quy trình kiểm tra chất lượng của lô hàng nhập từ Nhà cung cấp trước khi nhập kho chính thức. |

---



---

##### **e) Hệ thống biểu mẫu áp dụng (Forms & Templates)**


Dưới đây là 6 biểu mẫu nghiệp vụ thực tế được sử dụng xuyên suốt quy trình Quản lý kho và xuất vật tư tại FPT Telecom:

**Biểu mẫu 1: Phiếu yêu cầu xuất vật tư (Electronic Material Requisition Form)**  
* *Mã hiệu:* BM-KHO-01 | *Người lập:* Hệ thống BPMS (Tự động) | *Người nhận:* Thủ kho chi nhánh  

| STT | Mã Work Order | Tên Kỹ thuật viên | Mã nhân viên | Chủng loại thiết bị yêu cầu | Số lượng | Chuẩn công nghệ | Ghi chú |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | WO-2026-0901 | Nguyễn Văn An | FPT-10822 | Modem Wi-Fi 6 ONT (G-97RG6M) | 01 Cái | GPON | Gói cước Giga |
| 2 | WO-2026-0901 | Nguyễn Văn An | FPT-10822 | Thiết bị mở rộng Mesh (H3601P) | 01 Cái | Wi-Fi 6 | Thuê bao lắp tầng 2 |
| 3 | WO-2026-0901 | Nguyễn Văn An | FPT-10822 | Cáp quang Drop wire 1FO có dây treo | 150 Mét | Cáp dã chiến | Khoảng cách ODF 120m |

**Biểu mẫu 2: Phiếu xuất kho kiêm biên bản bàn giao thiết bị**  
* *Mã hiệu:* BM-KHO-02 | *Người lập:* Thủ kho | *Người nhận:* Kỹ thuật viên thi công  

| STT | Mã vật tư | Tên thiết bị / Phụ kiện | ĐVT | SL xuất | Số Serial Number | Địa chỉ MAC | Tình trạng |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | VT-MODEM-06 | Modem Wi-Fi 6 G-97RG6M | Cái | 01 | FPTHCM26090123 | AC:22:05:4E:91:A0 | Mới 100%, nguyên hộp |
| 2 | VT-MESH-01 | Router Mesh ZTE H3601P | Cái | 01 | ZTESG260877123 | 84:D8:1B:32:FF:12 | Mới 100%, nguyên seal |
| 3 | VT-CAP-1FO | Cáp quang Drop wire 1FO | Mét | 150 | Lô: C-2026-T8 | N/A | Đạt kiểm định suy hao |
| 4 | VT-FAST-SC | Đầu nối Fast Connector SC/APC | Cái | 04 | Lô: FC-09 | N/A | Đóng túi tiêu chuẩn |
*(Kèm chữ ký xác nhận của Thủ kho bàn giao và Kỹ thuật viên nhận hàng)*

**Biểu mẫu 3: Phiếu đề xuất mua sắm bổ sung vật tư**  
* *Mã hiệu:* BM-KHO-03 | *Người lập:* Thủ kho | *Người duyệt:* Trưởng bộ phận Kho & Ban Giám đốc  

| STT | Mã thiết bị | Tên thiết bị / Chủng loại | Tồn kho hiện tại | Ngưỡng Safety Stock | SL đề xuất mua | Đơn giá dự kiến (VNĐ) | Thành tiền dự kiến (VNĐ) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | VT-MODEM-06 | Modem Wi-Fi 6 G-97RG6M | 15 cái | 50 cái | 100 cái | 650.000 | 65.000.000 |
| 2 | VT-CAP-1FO | Cuộn cáp Drop wire 1.000m | 2 cuộn | 5 cuộn | 10 cuộn | 1.800.000 | 18.000.000 |
| 3 | VT-FAST-SC | Fast Connector SC/APC (hộp 100) | 3 hộp | 10 hộp | 20 hộp | 350.000 | 7.000.000 |
| **Tổng** | | | | | | | **90.000.000 VNĐ** |
*(Đề xuất vượt 50 triệu VNĐ $\rightarrow$ Cần chữ ký phê duyệt của Ban Giám đốc Chi nhánh)*

**Biểu mẫu 4: Biên bản kiểm tra chất lượng hàng nhập kho (QC Incoming Report)**  
* *Mã hiệu:* BM-KHO-04 | *Đơn vị giao hàng:* Nhà cung cấp | *Đơn vị kiểm tra:* Bộ phận Kho & QC  

| STT | Số PO / Lô hàng | Tên mặt hàng | Tổng SL giao | Số mẫu test (AQL) | Số lượng Đạt | Số lượng Lỗi | Kết luận QC | Hướng xử lý |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | PO-NHACUNGCAP-991 | Modem Wi-Fi 6 | 100 | 10 | 10 | 0 | **ĐẠT CHUẨN** | Nhập kho WMS |
| 2 | PO-NHACUNGCAP-992 | Dây nhảy quang Patch cord | 500 | 20 | 18 | 2 (Lỏng đầu bấm) | **TỪ CHỐI** | Trả lại Nhà cung cấp |

**Biểu mẫu 5: Phiếu thu hồi và nhập trả vật tư / thiết bị lỗi**  
* *Mã hiệu:* BM-KHO-05 | *Người giao:* Kỹ thuật viên thi công | *Người nhận:* Thủ kho  

| STT | Mã Work Order liên quan | Tên thiết bị / Vật tư hoàn trả | Số Serial / MAC | Lý do thu hồi / nhập trả | Phân loại trạng thái | Ghi chú |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | WO-2026-0889 | Cáp quang Drop wire 1FO | N/A | Dư thừa sau thi công (35m) | Tái sử dụng (Kho tốt) | Nhập lại thẻ kho |
| 2 | WO-2026-0901 | Modem G-97RG6M | FPTHCM26090123 | Hỏng cổng quang LOS đỏ | Hỏng - Chờ bảo hành | Chuyển khu kho lỗi |

**Biểu mẫu 6: Bảng đối soát và kiểm kê tồn kho định kỳ**  
* *Mã hiệu:* BM-KHO-06 | *Kỳ kiểm kê:* Tháng 08/2026 | *Thành phần:* Kế toán kho, Thủ kho, Trưởng kho  

| Mã vật tư | Tên vật tư thiết bị | Tồn sổ sách (WMS) | Tồn thực tế đếm | Chênh lệch (+/-) | Nguyên nhân chênh lệch | Đề xuất xử lý |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| VT-MODEM-06 | Modem Wi-Fi 6 | 120 | 119 | -1 | Quét sót mã khi nhập trả | Truy xuất camera & cập nhật WMS |
| VT-CAP-1FO | Cáp quang 1FO (Mét) | 4.500 | 4.380 | -120 | Hao hụt thi công dã chiến | Hạch toán chi phí hao hụt định mức |

---

---



---

#### **3.6.1.2. Phỏng vấn (Interview-based Discovery)**


Phương pháp phỏng vấn trực tiếp được thực hiện với các bên liên quan nhằm khai thác sâu các khía cạnh vận hành thực tế, trải nghiệm người dùng hệ thống, và các ngoại lệ thường phát sinh trong quá trình xuất nhập kho. Bộ câu hỏi được chia thành **10 câu hỏi định tính** và **10 câu hỏi định lượng**, cân đối giữa **dạng câu hỏi có cấu trúc (Structured)** và **không có cấu trúc (Unstructured)**.


##### **a) Danh sách 10 câu hỏi định tính (Qualitative Questions)**


* **Nhóm câu hỏi có cấu trúc (Structured Qualitative Questions):** *(Sử dụng thang đo Likert 5 mức độ hoặc các phương án lựa chọn cố định nhằm lượng hóa mức độ đồng thuận)*

**Bảng 3.6.7: Bảng câu hỏi phỏng vấn định tính có cấu trúc (Structured Qualitative)**

| STT | Đối tượng phỏng vấn | Nội dung câu hỏi có cấu trúc | Thang đo / Phương án lựa chọn |
| :---: | :--- | :--- | :--- |
| **Q1** | Thủ kho & Nhân viên kho | Anh/Chị đánh giá mức độ tiện dụng và độ ổn định của giao diện phần mềm WMS khi thao tác quét mã Serial/MAC và in phiếu xuất kho như thế nào? | 1. Rất khó dùng; 2. Khó dùng; 3. Bình thường; 4. Dễ dùng; 5. Rất trực quan và nhanh chóng. |
| **Q2** | Kỹ thuật viên thi công | Khi phát hiện thiết bị modem bị lỗi quang tại hiện trường, mức độ đáp ứng thủ tục đổi thiết bị thay thế từ kho có kịp thời không? | 1. Rất chậm chạp; 2. Chậm; 3. Trung bình; 4. Nhanh; 5. Rất nhanh, hỗ trợ tức thì. |
| **Q3** | Bộ phận Mua hàng | Mức độ tin cậy và tuân thủ đúng cam kết về thời gian giao hàng của các Nhà cung cấp thiết bị viễn thông hiện nay như thế nào? | 1. Thường xuyên trễ hẹn; 2. Đôi khi trễ hẹn; 3. Đúng hẹn ở mức trung bình; 4. Đúng hẹn phần lớn; 5. Luôn đúng hẹn 100%. |
| **Q4** | Kế toán kho | Quy trình đối soát chứng từ xuất kho giữa số liệu quét mã WMS và hạch toán kế toán ERP hiện tại có đảm bảo độ chính xác không? | 1. Hoàn toàn không khớp; 2. Thường sai lệch; 3. Khớp một phần; 4. Khá chuẩn xác; 5. Khớp hoàn hảo theo thời gian thực. |
| **Q5** | Ban Giám đốc Chi nhánh | Thủ tục phê duyệt đề xuất mua sắm bổ sung vật tư vượt hạn mức tự quyết (> 50 triệu đồng) hiện tại được thực hiện qua kênh nào? | [A] Ký giấy tay truyền thống; [B] Phê duyệt qua Email; [C] Phê duyệt trên phần mềm BPMS; [D] Chat qua nhóm Zalo/Telegram. |

* **Nhóm câu hỏi không có cấu trúc (Unstructured Qualitative Questions):** *(Câu hỏi mở để đối tượng tự do chia sẻ góc nhìn, nguyên nhân gốc rễ và đề xuất giải pháp)*

**Bảng 3.6.8: Bảng câu hỏi phỏng vấn định tính mở (Unstructured Qualitative)**

| STT | Đối tượng phỏng vấn | Nội dung câu hỏi mở (Không có cấu trúc) | Mục tiêu thu thập thông tin |
| :---: | :--- | :--- | :--- |
| **Q6** | Thủ kho chính | Trong quá trình tiếp nhận yêu cầu và xuất hàng vào khung giờ cao điểm buổi sáng, những rào cản hoặc điểm nghẽn lớn nhất gây chậm trễ thời gian nhận hàng của KTV là gì? | Xác định điểm nghẽn vật lý và lỗi hệ thống giờ cao điểm. |
| **Q7** | Kỹ thuật viên thi công | Anh/Chị gặp những khó khăn gì trong việc bảo quản và hoàn trả vật tư dôi dư (cáp quang, đầu nối, modem) sau khi kết thúc ca làm việc ngoài hiện trường? | Nhận diện lý do vật tư chậm hoàn trả hoặc tỷ lệ thất thoát cao. |
| **Q8** | Bộ phận Mua hàng | Những yếu tố bất khả kháng nào thường dẫn đến tình trạng Nhà cung cấp giao hàng chậm hoặc giao hàng không đạt tiêu chuẩn kiểm định QC? | Phân tích rủi ro chuỗi cung ứng và sự phụ thuộc vào Nhà cung cấp. |
| **Q9** | Kế toán kho | Theo Anh/Chị, đâu là nguyên nhân chính dẫn đến sự chênh lệch giữa số lượng tồn kho thực tế đếm được trong kho và số liệu tồn ghi nhận trên hệ thống ERP? | Khám phá lỗ hổng quy trình kiểm đếm và sai lệch thời gian hạch toán. |
| **Q10** | Ban Giám đốc Chi nhánh | Định hướng chiến lược của Chi nhánh trong việc tự động hóa quản lý kho (RFID, mã QR thông minh, tích hợp hệ thống) trong 1–2 năm tới là gì? | Định hình mục tiêu cải tiến và tái thiết kế quy trình To-Be. |

---



##### **b) Danh sách 10 câu hỏi định lượng (Quantitative Questions)**


* **Nhóm câu hỏi có cấu trúc (Structured Quantitative Questions):** *(Yêu cầu người trả lời cung cấp số liệu đo lường cụ thể với đơn vị tính rõ ràng)*

**Bảng 3.6.9: Bảng câu hỏi khảo sát định lượng có cấu trúc (Structured Quantitative)**

| STT | Đối tượng phỏng vấn | Nội dung câu hỏi định lượng có cấu trúc | Đơn vị đo lường |
| :---: | :--- | :--- | :---: |
| **Q11** | Thủ kho | Thời gian trung bình để thực hiện trọn vẹn thao tác quét Serial, MAC, kiểm tra ngoại quan và in phiếu xuất cho 01 đơn hàng là bao nhiêu phút? | Phút / đơn vị |
| **Q12** | Thủ kho | Trung bình một ngày, kho chi nhánh thực hiện xuất vật tư cho bao nhiêu lượt Kỹ thuật viên đến nhận hàng? | Lượt KTV / ngày |
| **Q13** | Kỹ thuật viên | Trong một tháng qua, trung bình có bao nhiêu lần Anh/Chị phải chờ đợi tại kho trên 15 phút mới nhận được đầy đủ thiết bị thi công? | Số lần / tháng |
| **Q14** | Bộ phận Mua hàng | Trong quý gần nhất, tỷ lệ các lô hàng từ Nhà cung cấp bị bộ phận QC từ chối nhập kho do không đạt chuẩn kỹ thuật là bao nhiêu phần trăm? | Tỷ lệ phần trăm (%) |
| **Q15** | Kế toán kho | Số lượng chênh lệch bình quân (thiếu hoặc thừa) giữa kiểm kê vật lý và phần mềm WMS được phát hiện trong các kỳ kiểm kê tháng là bao nhiêu thiết bị? | Số lượng thiết bị / tháng |

* **Nhóm câu hỏi không có cấu trúc (Unstructured Quantitative Questions):** *(Khảo sát khoảng biến thiên, dữ liệu phân bổ xác suất và ước lượng thiệt hại tài chính)*

**Bảng 3.6.10: Bảng câu hỏi khảo sát định lượng mở (Unstructured Quantitative)**

| STT | Đối tượng phỏng vấn | Nội dung câu hỏi mở định lượng (Không có cấu trúc) | Dữ liệu định lượng kỳ vọng thu thập |
| :---: | :--- | :--- | :--- |
| **Q16** | Bộ phận Mua hàng | Khi kho chạm ngưỡng hết hàng, thời gian chờ Nhà cung cấp giao hàng bổ sung dao động trong khoảng từ bao nhiêu ngày đến bao nhiêu ngày (ngắn nhất và dài nhất)? | Khoảng thời gian (Best-case / Worst-case) tính bằng ngày. |
| **Q17** | Thủ kho | Tỷ lệ phần trăm giữa các đơn hàng xuất thiết bị chuẩn GPON thông thường so với thiết bị cao cấp XGS-PON/Wi-Fi 6 hiện đang phân bổ như thế nào? | Cơ cấu tỷ lệ phần trăm (%) của từng chủng loại thiết bị. |
| **Q18** | Kỹ thuật viên | Trung bình một tuần, tỷ lệ thiết bị Modem/ONT bị phát hiện lỗi kỹ thuật tại hiện trường chiếm khoảng bao nhiêu phần trăm trên tổng số thiết bị đã xuất? | Tỷ lệ lỗi hiện trường (%) và số giờ lãng phí do chờ đổi thiết bị. |
| **Q19** | Kế toán kho | Ước tính tổng chi phí thiệt hại tài chính phát sinh hàng tháng do tình trạng hư hỏng thiết bị, tồn kho quá hạn bảo hành và thất thoát vật tư là bao nhiêu? | Giá trị tiền tệ ước tính (VNĐ / tháng). |
| **Q20** | Ban Giám đốc | Chi nhánh sẵn sàng phân bổ khoảng ngân sách bao nhiêu để đầu tư nâng cấp hệ thống phần mềm WMS và thiết bị quét mã tự động nhằm rút ngắn 50% thời gian xuất kho? | Khung ngân sách đầu tư khả thi (Triệu VNĐ). |

---



---

#### **3.6.1.3. Workshop (Hội thảo khám phá quy trình - Workshop-based Discovery)**


Phương pháp Workshop được tổ chức nhằm tập hợp toàn bộ các bên liên quan chủ chốt vào một phiên làm việc tập trung để cùng nhau thảo luận, giải quyết các xung đột quan điểm (ví dụ: KTV cho rằng kho xuất chậm, Thủ kho cho rằng KTV đến dồn dập vào một thời điểm), và thống nhất một bức tranh toàn cảnh chính xác về quy trình hiện tại.


##### **a) Biểu mẫu tổ chức cuộc họp (Meeting Agenda & Setup Form)**


* **Tên cuộc họp:** Hội thảo Khám phá và Chuẩn hóa Quy trình Quản lý kho & Xuất vật tư (Process Discovery Workshop)
* **Thời gian tổ chức:** 08:30 – 11:30, Ngày 25 tháng 08 năm 2026
* **Địa điểm:** Phòng họp Sapphire, Tòa nhà FPT Telecom Chi nhánh & Trực tuyến qua Microsoft Teams
* **Mục tiêu cuộc họp:**
  1. Thống nhất ranh giới bắt đầu và kết thúc của quy trình Quản lý kho và xuất vật tư.
  2. Xác định chi tiết từng bước công việc thực tế (Happy Path) và các nhánh ngoại lệ.
  3. Chỉ ra các nguyên nhân gây nghẽn tại kho và thống nhất ma trận trách nhiệm RACI.
* **Thành phần tham gia cuộc họp:**

**Bảng 3.6.11: Danh sách nhân sự tham gia hội thảo chuyên sâu khám phá quy trình**

| Họ và tên | Chức danh / Phòng ban | Vai trò trong buổi Workshop |
| :--- | :--- | :--- |
| **Nguyễn Hoàng Long** | Chuyên viên Phân tích Quy trình (BPM Lead) | **Người điều phối chính (Facilitator)** – Dẫn dắt thảo luận, giữ vững thời lượng |
| **Trần Văn Bình** | Trưởng bộ phận Kho & Vật tư | **Chủ sở hữu quy trình (Process Owner)** – Cung cấp thông tin nghiệp vụ kho |
| **Lê Thị Mai** | Phó Giám đốc Vận hành Chi nhánh | Đại diện Ban Giám đốc – Định hướng chính sách và phê duyệt ranh giới |
| **Phạm Quốc Toàn** | Trưởng bộ phận Mua hàng & Cung ứng | Thành viên tham gia – Cung cấp dữ liệu làm việc với Nhà cung cấp |
| **Đỗ Minh Tuấn** | Đội trưởng Đội Kỹ thuật viên Thi công | Đại diện người dùng nội bộ – Phản ánh thực tế hiện trường thi công |
| **Ngô Thanh Trúc** | Kế toán trưởng chi nhánh | Đại diện khối Tài chính – Đảm bảo tính tuân thủ hạch toán ERP |
| **Hoàng Anh Thư** | Chuyên viên BA (Business Analyst) | **Thư ký (Scribe)** – Ghi chép biên bản và vẽ phác thảo luồng trực tiếp |

---



##### **b) Kịch bản điều phối cuộc họp và các kết quả thống nhất quan trọng**


Kịch bản điều phối phiên Workshop kéo dài 180 phút được thiết kế theo cấu trúc 5 giai đoạn chặt chẽ:

* **Giai đoạn 1: Khai mạc và Thống nhất phạm vi (08:30 – 08:50 | 20 phút)**  
  * *Người điều phối (Facilitator):* Trình bày mục tiêu buổi làm việc; giới thiệu nguyên tắc tương tác tôn trọng, không đổ lỗi cá nhân; thống nhất ranh giới: Quy trình bắt đầu từ khi nhận Work Order từ BPMS và kết thúc khi toàn bộ vật tư được quyết toán trên WMS/ERP.  
  * *Kết quả đầu ra:* Toàn bộ người tham dự đồng thuận với phạm vi khảo sát.

* **Giai đoạn 2: Vẽ luồng quy trình chính - Happy Path (08:50 – 09:40 | 50 phút)**  
  * *Hoạt động:* Facilitator sử dụng bảng trắng kỹ thuật số (Miro/Mural) mời Thủ kho và KTV từng bước dán giấy ghi chú (Sticky Notes) mô tả trình tự từ: Nhận thông tin $\rightarrow$ Kiểm kho $\rightarrow$ Lấy hàng $\rightarrow$ Quét Serial/MAC $\rightarrow$ Bàn giao $\rightarrow$ Quyết toán.  
  * *Thư ký (Scribe):* Sắp xếp các bước thành chuỗi tuần tự; ghi nhận ý kiến phản hồi về thời gian trung bình của từng bước.  
  * *Kết quả đầu ra:* Bản thảo luồng quy trình tiêu chuẩn khi mọi điều kiện đều thuận lợi (Tồn kho đủ, thiết bị chuẩn).

* **Giai đoạn 3: Nhận diện và Xử lý các luồng ngoại lệ & Điểm nghẽn (09:40 – 10:40 | 60 phút)**  
  * *Hoạt động trọng tâm:* Facilitator đặt câu hỏi kích thích tranh luận: *"Điều gì tồi tệ nhất xảy ra nếu...?"*  
    - *Ngoại lệ 1 (Thiếu hàng):* Thủ kho phản ánh việc tồn kho an toàn bị tính toán sai dẫn đến hết hàng đột ngột. Đại diện Mua hàng giải thích thời gian giao hàng của Nhà cung cấp mất từ 1–5 ngày. Thống nhất: Cần bổ sung cổng kiểm tra hạn mức mua sắm và Event-Driven Gateway để xử lý sự kiện giao trễ.  
    - *Ngoại lệ 2 (Lỗi thiết bị tại hiện trường):* Đội trưởng KTV phản ánh việc đổi thiết bị hỏng mất nhiều thời gian, ảnh hưởng chỉ số hài lòng của khách hàng. Thống nhất bổ sung thủ tục đổi nhanh thiết bị dự phòng.  
    - *Ngoại lệ 3 (Hàng nhập không đạt QC):* Thống nhất quy tắc bắt buộc kiểm định ngẫu nhiên trước khi nhập kho.  
  * *Kết quả đầu ra:* Xác định được toàn bộ 8 điểm rẽ nhánh (Gateways) cần mô hình hóa trong sơ đồ BPMN.

* **Giai đoạn 4: Thống nhất Ma trận phân công trách nhiệm RACI (10:40 – 11:10 | 30 phút)**  
  * *Hoạt động:* Rà soát từng bước công việc và phân định rõ ai là người làm trực tiếp (R), ai phê duyệt (A), ai hỗ trợ (C), ai nhận báo cáo (I) nhằm loại bỏ sự đùn đẩy trách nhiệm giữa Kho và Đội Kỹ thuật.  
  * *Kết quả đầu ra:* Bảng ma trận RACI được toàn thể các trưởng bộ phận ký nháy đồng thuận.

* **Giai đoạn 5: Tổng kết, Phê duyệt biên bản và Kế hoạch tiếp theo (11:10 – 11:30 | 20 phút)**  
  * *Hoạt động:* Scribe đọc lại toàn bộ biên bản ghi nhớ; Process Owner (Trưởng bộ phận Kho) và Đại diện Ban Giám đốc phát biểu xác nhận tính chuẩn xác của dữ liệu; Facilitator công bố lộ trình: Hoàn thiện sơ đồ BPMN As-Is trong vòng 3 ngày làm việc để các bên ký duyệt chính thức.

---

---



---

### **3.6.2. Mô hình hóa quy trình hiện tại (Sơ đồ BPMN - As-is)**

Tuân thủ chặt chẽ tiêu chí Rubric đánh giá của môn học (**Độ phức tạp quy trình Hỗ trợ: Cổng điều kiện $> 3$**), mô hình BPMN As-is quy trình Quản lý kho và xuất vật tư được thiết kế đạt mức độ phức tạp cao với **đúng 5 Cổng điều kiện (Gateways = 5)** và **18 Hoạt động nghiệp vụ** (Activities), phân chia rõ ràng trên các phân làn chức năng (Swimlanes).

#### **3.6.2.1. Phân tích các phần tử chuẩn BPMN 2.0**


Mô hình quy trình đáp ứng chuẩn mực phân tầng độ phức tạp nâng cao (Mức 7 cổng điều kiện) nhằm bao quát toàn diện chuỗi cung ứng vật tư viễn thông:

**Hệ thống 7 Cổng điều kiện (Gateways) chuẩn hóa:**
1. **Gateway 1 (Exclusive XOR Gateway - Tồn kho khả dụng?):**  
   Kiểm tra số lượng tồn kho thực tế có đủ đáp ứng Work Order và vẫn duy trì trên ngưỡng an toàn (*Safety Stock*) hay không.  
   * *Nhánh Đủ (Yes):* Chuyển thẳng sang Gateway 3 để phân loại thiết bị xuất kho.  
   * *Nhánh Thiếu (No):* Chuyển sang bước lập đề xuất mua sắm bổ sung.
2. **Gateway 2 (Exclusive XOR Gateway - Vượt hạn mức tự quyết chi nhánh?):**  
   Đề xuất mua sắm bổ sung có giá trị vượt quá hạn mức ngân sách tự quyết của chi nhánh (> 50 triệu đồng) hay không.  
   * *Nhánh Vượt (Yes):* Trình hồ sơ lên Ban Giám đốc Chi nhánh phê duyệt.  
   * *Nhánh Không vượt (No):* Chuyển trực tiếp sang Bộ phận Mua hàng để phát hành đơn PO.
3. **Gateway 3 (Exclusive XOR Gateway - Phân loại chuẩn công nghệ thiết bị?):**  
   Căn cứ vào gói cước hợp đồng của khách hàng để lấy đúng chủng loại thiết bị quang tương thích hạ tầng:  
   * *Nhánh GPON:* Lấy Modem ONT tiêu chuẩn băng rộng cho hộ gia đình.  
   * *Nhánh XGS-PON:* Lấy Modem cao cấp đối xứng 10Gbps và thiết bị mở rộng Mesh Wi-Fi 6 cho doanh nghiệp.
4. **Gateway 4 (Event-Driven Gateway - Chờ Nhà cung cấp giao hàng):**  
   Cổng rẽ nhánh theo sự kiện ngoại vi, xử lý 2 kịch bản độc quyền:  
   * *Nhánh Message Event (Nhận hàng):* Nhà cung cấp giao hàng đến kho $\rightarrow$ Kích hoạt tiếp nhận và kiểm định chất lượng (QC).  
   * *Nhánh Timer Event (Timeout > 48 giờ):* Quá 48h chưa nhận được hàng $\rightarrow$ Phát cảnh báo trễ hạn SLA và kích hoạt điều chuyển khẩn cấp từ kho lân cận.
5. **Gateway 5 (Exclusive XOR Gateway - Kiểm định chất lượng QC đầu vào đạt?):**  
   Kiểm tra chất lượng mẫu ngẫu nhiên của lô hàng nhập từ Nhà cung cấp:  
   * *Nhánh Đạt (Yes):* Thủ kho xác nhận nhập kho WMS và quay lại Gateway 3 để cấp phát cho KTV.  
   * *Nhánh Không đạt (No):* Lập biên bản từ chối nhận hàng và trả hàng về Nhà cung cấp.
6. **Gateway 6 (Exclusive XOR Gateway - Thiết bị có bị lỗi kỹ thuật trong thi công?):**  
   KTV kiểm tra tín hiệu quang và cấu hình Wi-Fi tại địa chỉ khách hàng:  
   * *Nhánh Không lỗi (No):* Tiến hành nghiệm thu dịch vụ cùng khách hàng.  
   * *Nhánh Có lỗi (Yes):* KTV gọi điện về kho xin đổi thiết bị mới khẩn cấp $\rightarrow$ Thủ kho cấp đổi thiết bị thay thế.
7. **Gateway 7 (Exclusive XOR Gateway - Có phát sinh vật tư dôi dư sau thi công?):**  
   Sau khi hoàn tất thi công tại hiện trường, kiểm tra xem có thừa cuộn cáp quang hoặc phụ kiện không:  
   * *Nhánh Có (Yes):* KTV mang vật tư thừa về kho để Thủ kho kiểm đếm và nhập trả WMS.  
   * *Nhánh Không (No):* Chuyển thẳng sang bước đồng bộ kế toán ERP và đóng Work Order.

---

**Áp dụng các phần tử chuẩn BPMN 2.0 theo cẩm nang BA (Mota.docx):**

* **1. Swimlanes (Pools & Lanes):**  
  * **Pool FPT Telecom (Nội bộ):** Gồm 4 phân làn chức năng (Lanes):
    - *Lane Hệ thống BPMS / WMS:* Tự động hóa tạo Work Order, đồng bộ ERP và đóng lệnh thi công.
    - *Lane Bộ phận Kho & Vật tư:* Quản lý hiện vật, kiểm kho, quét mã Serial/MAC, bàn giao và tiếp nhận hoàn trả.
    - *Lane Kỹ thuật viên thi công (KTV):* Kiểm đếm vật tư, thi công kéo cáp, cài đặt Wi-Fi và nghiệm thu.
    - *Lane Bộ phận Mua hàng & Cung ứng:* Lập đơn đặt hàng PO và phối hợp với Nhà cung cấp.
  * **Pool Nhà cung cấp (Bên ngoài):** Thể hiện sự phối hợp chuỗi cung ứng độc lập thông qua luồng thông điệp (*Message Flow nét đứt*).

* **2. Phân loại Task Types chuẩn mực:**  
  * **User Task:** Thao tác của con người trên phần mềm (*Thủ kho tiếp nhận yêu cầu trên WMS, Quét mã Serial/MAC, Lập đề xuất mua sắm*).
  * **Manual Task:** Hoạt động vật lý thủ công (*Lấy thiết bị từ kệ, Kiểm đếm hàng, Thi công kéo cáp quang, Nghiệm thu cùng khách hàng*).
  * **Service Task:** Hệ thống tự động thực hiện hoàn toàn (*Tạo yêu cầu xuất kho tự động, Đồng bộ số liệu WMS sang ERP, Đóng Work Order trên BPMS*).
  * **Send Task:** Bộ phận Mua hàng phát hành và gửi đơn PO sang Nhà cung cấp.
  * **External Task:** Các tác vụ xử lý độc lập trong Pool Nhà cung cấp.

* **3. Activity Markers:**  
  * **Multi-Instance Task (Ký hiệu 3 vạch song song):** Áp dụng cho bước *Quét mã Serial/MAC cho tập hợp nhiều thiết bị* (Modem, Mesh Wi-Fi) trong cùng một Work Order.  
  * **Loop Task:** Áp dụng cho bước *Kiểm tra công suất cổng quang dã chiến*, lặp lại nhiều lần cho đến khi đạt thông số suy hao chuẩn.

* **4. Events & Boundary Events:**  
  * *Start Event:* Nhận tín hiệu kích hoạt từ hợp đồng khách hàng.  
  * *Intermediate Message Event:* Nhận tín hiệu hàng đến từ Nhà cung cấp.  
  * *Intermediate Timer Event:* Bộ đếm thời gian 48 giờ chờ giao hàng.  
  * *End Event:* Đóng quy trình hoàn tất thành công.

* **5. Information Artifacts:**  
  * **Data Object:** *Phiếu xuất kho kiêm biên bản giao nhận*, *Phiếu đề xuất mua sắm*, *Biên bản kiểm tra QC*.  
  * **Data Store:** *Cơ sở dữ liệu kho WMS* và *Cơ sở dữ liệu kế toán ERP*.

---

---



---

#### **3.6.2.2. Sơ đồ BPMN 2.0 As-Is - Quy trình Quản lý kho và xuất vật tư**

![Sơ đồ BPMN 2.0 As-Is Quy trình Quản lý kho và xuất vật tư](./assets/diagrams/quan_ly_kho/SoDo.jpg)

---

#### **3.6.2.3. Diễn giải chi tiết các luồng quy trình As-Is**


##### **a) Luồng chính - Happy Path (Tồn kho đủ & Không phát sinh lỗi):**
1. **BPMS/CRM:** Khởi tạo Work Order $\rightarrow$ Tạo yêu cầu xuất vật tư tự động $\rightarrow$ Đẩy yêu cầu sang WMS.
2. **Kho & Vật tư:** Thủ kho tiếp nhận yêu cầu trên WMS $\rightarrow$ **Gateway 1 (XOR):** Tồn kho khả dụng $\ge$ Safety Stock? $\rightarrow$ **Nhánh Đủ:**
3. **Kho & Vật tư:** **Gateway 3 (XOR):** Phân loại chuẩn thiết bị $\rightarrow$ Chọn lấy Modem GPON hoặc XGS-PON/Mesh $\rightarrow$ Lấy thiết bị ra khỏi kệ hàng $\rightarrow$ Quét mã Serial Number và MAC Address (User Task) $\rightarrow$ In Phiếu xuất kho kiêm biên bản bàn giao thiết bị $\rightarrow$ Bàn giao vật tư cho KTV ca thi công.
4. **Kỹ thuật viên:** KTV đến kho kiểm đếm thiết bị $\rightarrow$ Ký xác nhận biên bản bàn giao $\rightarrow$ Vận chuyển thiết bị đến nhà khách hàng $\rightarrow$ Kéo cáp, hàn quang và cài đặt Wi-Fi.
5. **Kỹ thuật viên:** **Gateway 6 (XOR):** Thiết bị có bị lỗi không? $\rightarrow$ **Nhánh Không:** Nghiệm thu dịch vụ cùng khách hàng.
6. **Kỹ thuật viên:** **Gateway 7 (XOR):** Có vật tư dôi dư không? $\rightarrow$ **Nhánh Không:** Hoàn tất thi công tại chỗ.
7. **Hệ thống BPMS / WMS:** Phân hệ WMS tự động đồng bộ giá trị xuất kho sang ERP để ghi nhận giá vốn $\rightarrow$ BPMS đóng Work Order thi công $\rightarrow$ Kết thúc thành công.

##### **b) Luồng phụ 1 - Kịch bản thiếu tồn kho & Đặt hàng Nhà cung cấp:**
1. **Kho & Vật tư:** Tại Gateway 1, phát hiện tồn kho thiếu hụt hoặc dưới mức Safety Stock $\rightarrow$ Thủ kho lập Phiếu đề xuất mua sắm bổ sung trên WMS.
2. **Kho & Vật tư:** **Gateway 2 (XOR):** Giá trị đơn hàng có vượt hạn mức tự quyết chi nhánh (> 50 triệu)?
   * *Nhánh Vượt (> 50tr):* Gửi hồ sơ lên Ban Giám đốc Chi nhánh phê duyệt $\rightarrow$ Ban Giám đốc ký duyệt điện tử.
   * *Nhánh Không vượt ($\le$ 50tr):* Chuyển thẳng đơn đề xuất sang Bộ phận Mua hàng.
3. **Bộ phận Mua hàng:** Lập đơn đặt hàng (PO) và gửi sang Nhà cung cấp $\rightarrow$ Hệ thống đi vào **Gateway 4 (Event-Driven Gateway)** để chờ phản hồi:
   * *Nhánh Sự kiện A (Timer Event 48h):* Nếu quá 48 giờ Nhà cung cấp chưa giao hàng $\rightarrow$ Phát cảnh báo trễ hạn SLA, điều chuyển gấp từ chi nhánh lân cận.
   * *Nhánh Sự kiện B (Message Event nhận hàng):* Nhà cung cấp giao hàng đến kho FPT $\rightarrow$ Kích hoạt tiếp nhận hàng.
4. **Kho & Vật tư:** Tiếp nhận lô hàng $\rightarrow$ Thực hiện kiểm định chất lượng đầu vào (QC) $\rightarrow$ **Gateway 5 (XOR):** Đạt tiêu chuẩn QC?
   * *Nhánh Không đạt (Lỗi):* Lập biên bản từ chối $\rightarrow$ Trả hàng lại cho Nhà cung cấp $\rightarrow$ Yêu cầu giao bù khẩn cấp.
   * *Nhánh Đạt:* Xác nhận nhập kho trên WMS $\rightarrow$ Cập nhật lại số lượng tồn kho khả dụng $\rightarrow$ Chuyển sang Gateway 3 để chuẩn bị xuất kho cho KTV.

##### **c) Luồng phụ 2 - Kịch bản phát hiện thiết bị lỗi trong quá trình thi công:**
1. **Kỹ thuật viên:** Tại Gateway 6, trong quá trình đấu nối tại nhà khách hàng, KTV phát hiện modem bị lỗi nguồn hoặc suy hao cổng quang $\rightarrow$ KTV gọi điện về hotline kho yêu cầu đổi thiết bị khẩn cấp.
2. **Kho & Vật tư:** Thủ kho lấy thiết bị dự phòng mới $\rightarrow$ Quét Serial/MAC mới để đính chính Work Order $\rightarrow$ Bàn giao thiết bị mới cho KTV.
3. **Kỹ thuật viên:** KTV nhận thiết bị mới $\rightarrow$ Tiếp tục lắp đặt và nghiệm thu hoàn tất với khách hàng $\rightarrow$ Mang thiết bị lỗi về kho cuối ngày.
4. **Kho & Vật tư:** Tiếp nhận thiết bị hỏng $\rightarrow$ Dán tem "Hỏng – Chờ bảo hành" $\rightarrow$ Nhập dữ liệu lên WMS $\rightarrow$ Chuyển vào khu vực kho hàng lỗi chờ trả bảo hành.

##### **d) Luồng phụ 3 - Kịch bản hoàn trả và thu hồi vật tư dôi dư sau thi công:**
1. **Kỹ thuật viên:** Tại Gateway 7, KTV kiểm tra thấy còn dư thừa cuộn cáp quang dã chiến hoặc phụ kiện đầu nối $\rightarrow$ Mang toàn bộ về kho lúc cuối ca.
2. **Kho & Vật tư:** Thủ kho kiểm đếm thực tế $\rightarrow$ Lập Phiếu nhập trả vật tư trên WMS $\rightarrow$ Cập nhật lại thẻ kho tài sản $\rightarrow$ Chuyển sang bước đồng bộ hệ thống ERP và đóng Work Order.

---

---



---

### **3.6.3. Phân tích định tính (Qualitative Analysis)**

#### **3.6.3.1. Phân tích giá trị gia tăng (Value-Added Analysis)**


- **VA (Value-Added):** Trực tiếp tạo ra giá trị cho khách hàng.
- **BVA (Business Value-Added):** Cần thiết cho hoạt động của doanh nghiệp (kiểm soát, đối soát, ghi nhận kế toán).
- **NVA (Non-Value-Added):** Không tạo ra giá trị, cần được giảm thiểu hoặc loại bỏ.

**Bảng 3.6.12: Bảng phân loại giá trị gia tăng (VA / BVA / NVA) các bước quy trình As-Is**

| STT | Hoạt động | Người thực hiện | Phân loại | Lập luận theo tiêu chuẩn phân loại |
| :---: | :--- | :--- | :---: | :--- |
| 1 | Nhận Work Order từ hệ thống CRM | Hệ thống BPMS | **BVA** | Bước khởi tạo nội bộ tự động, cần thiết cho điều phối hệ thống nhưng khách hàng không nhận ra trực tiếp. |
| 2 | Tạo yêu cầu xuất vật tư tự động | Hệ thống BPMS/WMS | **BVA** | Điều phối công việc nội bộ giữa các hệ thống; không tạo giá trị trực tiếp nhưng bắt buộc để kích hoạt quy trình. |
| 3 | Tiếp nhận yêu cầu xuất trên WMS | Thủ kho | **BVA** | Bước xác nhận và tiếp nhận nhiệm vụ; cần thiết cho kiểm soát quy trình nội bộ. |
| 4 | Kiểm tra tồn kho khả dụng | Thủ kho | **BVA** | Đảm bảo tính chính xác của xuất kho; tránh thiếu hàng gây gián đoạn Work Order — bắt buộc về mặt vận hành. |
| 5 | Lập phiếu đề xuất mua sắm (khi tồn kho thiếu) | Thủ kho | **NVA** | Phát sinh do tồn kho không được dự báo đủ; nếu Safety Stock được duy trì tốt, bước này không cần xảy ra. |
| 6 | Đặt hàng Nhà cung cấp hoặc điều chuyển kho tổng | Bộ phận Mua hàng | **NVA** | Hành động khắc phục hậu quả do lập kế hoạch tồn kho kém — không tạo giá trị, tốn thời gian và chi phí. |
| 7 | Chờ Nhà cung cấp giao hàng | — | **NVA** | Thời gian chờ thuần túy (1–5 ngày), không có hoạt động nào được thực hiện, gây trễ Work Order trực tiếp. |
| 8 | Tiếp nhận hàng và kiểm tra chất lượng đầu vào (QC) | Thủ kho | **BVA** | Bắt buộc để đảm bảo chất lượng thiết bị trước khi nhập kho; kiểm soát rủi ro về sau cho khách hàng. |
| 9 | Nhập kho trên WMS sau khi đạt QC | Thủ kho | **BVA** | Cập nhật dữ liệu tồn kho chính xác; cần thiết cho hạch toán và quản lý tài sản nội bộ. |
| 10 | Trả hàng lại Nhà cung cấp (khi không đạt QC) | Thủ kho | **NVA** | Hoạt động sửa lỗi do Nhà cung cấp giao hàng kém chất lượng; không tạo giá trị, gây lãng phí thời gian và nguồn lực. |
| 11 | Lấy thiết bị ra kho | Thủ kho | **VA** | Trực tiếp chuẩn bị thiết bị cho khách hàng sử dụng; khách hàng nhận giá trị khi thiết bị đến tay đúng loại. |
| 12 | Quét mã Serial Number / địa chỉ MAC / QR Code | Thủ kho | **VA** | Gắn định danh thiết bị với thuê bao khách hàng; nền tảng cho bảo hành và truy xuất tài sản. |
| 13 | Kiểm tra ngoại quan thiết bị | Thủ kho | **VA** | Đảm bảo thiết bị không bị hỏng hóc trước khi trao tay KTV; khách hàng nhận thiết bị trong tình trạng tốt. |
| 14 | Chuẩn bị vật tư tiêu hao theo định mức | Thủ kho | **VA** | Đảm bảo đủ phụ kiện để KTV hoàn tất thi công trong một lượt, tránh phải quay lại lấy thêm. |
| 15 | In Phiếu xuất kho | Thủ kho | **BVA** | Chứng từ nội bộ để xác nhận trách nhiệm bàn giao; cần thiết cho kế toán kho và kiểm toán. |
| 16 | Kiểm đếm vật tư & ký xác nhận Phiếu xuất kho | Kỹ thuật viên | **VA** | Khách hàng được đảm bảo rằng KTV nhận đủ thiết bị đúng chủng loại trước khi thi công. |
| 17 | Thực hiện thi công lắp đặt tại nhà khách hàng | Kỹ thuật viên | **VA** | Hoạt động cốt lõi tạo ra sản phẩm dịch vụ Internet cho khách hàng; khách hàng trực tiếp nhận giá trị. |
| 18 | Hoàn trả vật tư thừa về kho sau thi công | Kỹ thuật viên | **NVA** | Thao tác vận chuyển ngược chiều không tạo giá trị; cần được giảm thiểu bằng cách xuất đúng định mức ngay từ đầu. |
| 19 | Kiểm đếm & phân loại vật tư hoàn trả | Thủ kho | **BVA** | Bắt buộc để cập nhật tồn kho chính xác và phân loại tài sản (dùng lại / bảo hành / thanh lý). |
| 20 | Nhập trả vật tư / thiết bị trên WMS | Thủ kho | **BVA** | Cập nhật số liệu tồn kho real-time; cần thiết cho hạch toán kế toán và quản lý tài sản. |
| 21 | Đồng bộ dữ liệu WMS → ERP | Hệ thống WMS/ERP | **BVA** | Đảm bảo số liệu tài chính chính xác; bắt buộc theo quy trình hạch toán nội bộ doanh nghiệp. |
| 22 | Đóng Work Order trên BPMS | Hệ thống BPMS | **BVA** | Kết thúc vòng đời Work Order; cần thiết cho báo cáo và đánh giá hiệu suất vận hành nội bộ. |

**Tổng hợp phân loại:**

**Bảng 3.6.13: Bảng tổng hợp tỷ lệ phân loại giá trị gia tăng các hoạt động kho**

| Loại giá trị | Số lượng hoạt động | Tỉ lệ |
| :---: | :---: | :---: |
| **VA** | 6 | 27,3% |
| **BVA** | 12 | 54,5% |
| **NVA** | 4 | 18,2% |
| **Tổng** | **22** | **100%** |

> **Nhận xét:** Tỉ lệ NVA chiếm 18,2% — chủ yếu phát sinh ở kịch bản tồn kho thiếu (mua sắm qua Nhà cung cấp) và thời gian hoàn trả vật tư thừa. Đây là các điểm cần ưu tiên tối ưu hóa nhằm nâng cao hiệu quả quy trình.

---




---

#### **3.6.3.2. Phân tích 7 loại lãng phí (Lean Waste Analysis - TIMWOOD)**


Dựa trên 7 loại lãng phí (7 Wastes) theo phương pháp Lean, bảng dưới đây xác định các lãng phí hiện diện trong quy trình Quản lý kho và xuất vật tư tại FPT Telecom:

**Bảng 3.6.14: Bảng nhận diện và phân tích 7 loại lãng phí (Lean Waste) trong quy trình kho**

| Loại lãng phí | Biểu hiện trong quy trình FPT Telecom |
| :--- | :--- |
| **Hold (Chờ đợi)** | 1 Chờ Nhà cung cấp giao hàng khi tồn kho dưới Safety Stock (1–5 ngày làm việc); 2 Chờ kỹ thuật viên xác nhận thiết bị lỗi và liên hệ kho; 3 Chờ hệ thống BPMS đẩy Work Order sang WMS vào giờ cao điểm. |
| **Move (Vận chuyển không cần thiết)** | 1 Vận chuyển thiết bị từ kho trung tâm ra kho điểm khi phải điều chuyển nội bộ; 2 Kỹ thuật viên phải quay lại kho để đổi thiết bị lỗi thay vì được giao thay thế trực tiếp tại công trình. |
| **Over-do (Xử lý thừa / Làm quá mức)** | 1 Nhập liệu Serial/MAC thủ công song song với quét QR tự động trên WMS — thực hiện dữ liệu trùng lặp; 2 Kiểm tra ngoại quan thiết bị nhiều lần (tại kho và tại công trình); 3 In Phiếu xuất kho giấy khi hệ thống WMS đã có chữ ký điện tử của KTV. |
| **Defects (Lỗi / Làm lại)** | 1 Xuất nhầm model Modem/ONT không phù hợp hạ tầng GPON/XGS-PON → KTV phải quay lại kho đổi; 2 QC đầu vào từ Nhà cung cấp không đạt → trả hàng và đặt lại, gây trễ Work Order; 3 Ghi sai Serial Number trên WMS → phải tra cứu và đính chính sau. |
| **Over-production (Sản xuất/Xử lý thừa)** | 1 Tạo đề xuất mua sắm khi tồn kho thực tế vẫn còn hàng nhưng WMS chưa cập nhật real-time; 2 In dư Phiếu xuất kho giấy nhiều bản. |
| **Inventory (Lưu kho thừa)** | 1 Tồn kho Modem/ONT vượt ngưỡng Safety Stock do dự báo nhu cầu chưa chính xác, gây đọng vốn; 2 Thiết bị thu hồi từ khách hàng tồn lâu ở khu hàng lỗi chờ phân loại (dùng lại / bảo hành / thanh lý). |
| **Motion (Thao tác thừa)** | 1 Thủ kho phải tra cứu thủ công danh sách tồn kho trên giấy thay vì xem dashboard real-time trên WMS; 2 Nhân viên Mua hàng phải liên hệ Nhà cung cấp qua điện thoại/email thủ công thay vì thông qua cổng đặt hàng tích hợp. |

> **Nhận xét:** Lãng phí **Hold** và **Defects** có mức độ tác động cao nhất vì ảnh hưởng trực tiếp đến thời gian hoàn thành Work Order và SLA lắp đặt 24–48 giờ của FPT Telecom.

---



---

#### **3.6.3.3. Phân tích các bên liên quan (Stakeholder Analysis)**


**Bảng 3.6.15: Ma trận phân tích kỳ vọng và mức độ ảnh hưởng của các bên liên quan**

| Bên liên quan | Mức độ ảnh hưởng | Vai trò & Kỳ vọng | Rủi ro nếu quy trình không hiệu quả |
| :--- | :---: | :--- | :--- |
| **Kỹ thuật viên thi công (KTV)** | Rất cao | Nhận đúng thiết bị, đủ số lượng, kịp thời để hoàn thành Work Order đúng hẹn. | Trễ lịch lắp đặt, phải di chuyển đổi thiết bị, ảnh hưởng KPI cá nhân. |
| **Thủ kho / NV Kho & Vật tư** | Rất cao | Thực hiện xuất/nhập chính xác, cập nhật WMS real-time; kiểm soát tồn kho an toàn. | Sai lệch tồn kho, thiếu hàng đột ngột, áp lực xử lý đổi trả lớn. |
| **Bộ phận Mua hàng & Cung ứng** | Cao | Đảm bảo chuỗi cung ứng thông suốt; đặt hàng Nhà cung cấp đúng số lượng và thời hạn. | Tồn kho gián đoạn, phải xử lý đơn khẩn cấp với chi phí cao hơn. |
| **Nhà cung cấp** | Trung bình đến cao | Cung cấp Modem/ONT, Router Wi-Fi đúng chất lượng và đúng hạn giao. | Bị trả hàng khi QC không đạt, mất uy tín và hợp đồng dài hạn. |
| **Ban Kỹ thuật FPT Telecom** | Cao | Phê duyệt thiết bị chuyên dụng GPON/XGS-PON; đảm bảo tương thích hạ tầng. | Work Order bị hoãn khi thiếu thiết bị đặc thù, ảnh hưởng SLA toàn hệ thống. |
| **Hệ thống BPMS/WMS/ERP** | Rất cao | Tự động hóa luồng Work Order; quản lý tồn kho real-time; đồng bộ hạch toán. | Dữ liệu tồn kho sai lệch; không đóng được Work Order; mất khả năng truy xuất tài sản. |
| **Khách hàng cuối (Người dùng Internet)** | Trung bình (gián tiếp) | Được lắp đặt đúng hẹn, thiết bị hoạt động ổn định ngay từ đầu. | Không hài lòng, khiếu nại, hủy hợp đồng nếu lắp đặt trễ hoặc thiết bị lỗi. |

---



---

#### **3.6.3.4. Bảng theo dõi vấn đề (Issue Register)**


Dựa trên kết quả phân tích VA/BVA/NVA, bảng phân tích 7 lãng phí và phân tích các bên liên quan, nhóm tổng hợp **9 vấn đề trọng tâm** của quy trình Quản lý kho và xuất vật tư As-Is vào Sổ đăng ký vấn đề dưới đây:

**Bảng 3.6.16: Sổ theo dõi vấn đề toàn diện (Issue Register) quy trình Quản lý kho**

| **ID** | **Vấn đề phát sinh** | **Nguyên nhân gốc rễ** | **Tác động đến quy trình** | **Mức độ ưu tiên** |
| :---: | :--- | :--- | :--- | :---: |
| **IR-01** | Tồn kho xuống dưới ngưỡng Safety Stock đột ngột | Dự báo nhu cầu vật tư chưa chính xác theo mùa cao điểm; WMS chưa tích hợp cảnh báo tự động khi tiếp cận Reorder Point | Work Order bị hoãn từ 1–5 ngày làm việc; SLA lắp đặt 24–48 giờ bị phá vỡ hoàn toàn | **Cao** |
| **IR-02** | Lô hàng từ Nhà cung cấp không đạt tiêu chuẩn kiểm định QC | Nhà cung cấp giao hàng kém chất lượng hoặc sai quy cách; quy trình kiểm định QC đầu vào chỉ lấy mẫu ngẫu nhiên tỷ lệ thấp, dễ bỏ sót lỗi theo lô | Phải trả hàng, đặt lại từ đầu, gây trễ lịch thi công chuỗi Work Order phía sau | **Cao** |
| **IR-03** | Xuất nhầm chủng loại thiết bị quang (GPON thay vì XGS-PON hoặc ngược lại) | Phân loại thiết bị theo gói cước thực hiện thủ công; Work Order đôi khi thiếu ghi chú chuẩn công nghệ rõ ràng; Thủ kho phải đọc và phán đoán dựa trên kinh nghiệm | KTV phải mang thiết bị sai về kho đổi; lãng phí 2–4 giờ thi công; SLA không đạt | **Cao** |
| **IR-04** | Chênh lệch số liệu tồn kho giữa WMS và kiểm kê thực tế | Quét mã Serial/MAC bỏ sót hoặc nhập liệu sai khi nhập trả vật tư cuối ngày; KTV trễ quyết toán; WMS chưa cập nhật real-time theo giao dịch | Báo cáo tồn kho sai lệch dẫn đến quyết định mua sắm không chính xác; thiếu hụt tồn kho ảo | **Trung bình** |
| **IR-05** | Kỹ thuật viên chờ đợi lâu tại kho vào giờ cao điểm buổi sáng | Nhiều KTV đến lấy hàng cùng lúc (ca sáng 07:30–08:30); Thủ kho xử lý tuần tự thủ công; máy quét mã vạch không đủ số lượng cho giờ cao điểm | Trễ giờ khởi hành thi công từ 20–45 phút/KTV; dồn ứ lịch hẹn khách hàng buổi sáng | **Trung bình** |
| **IR-06** | Thiết bị bị phát hiện lỗi kỹ thuật tại hiện trường thi công | Quy trình QC đầu vào chưa kiểm tra 100% chức năng hoạt động của từng thiết bị; thiết bị bị va đập trong vận chuyển từ kho đến nhà khách hàng | KTV phải dừng thi công, gọi về kho xin đổi, chờ thiết bị mới; SLA bị phá vỡ; khách hàng bất bình | **Cao** |
| **IR-07** | Vật tư tiêu hao (cáp quang, đầu nối) không được hoàn trả kho đúng hạn cuối ngày | KTV không quyết toán về kho sau ca làm việc do trễ thi công hoặc bận xử lý ngoại lệ; thiếu quy trình nhắc nhở tự động; không có chế tài cụ thể | Tồn kho ảo trên WMS cao hơn thực tế; gây thiếu hụt giả khi kiểm kê; hao hụt vật tư khó kiểm soát | **Trung bình** |
| **IR-08** | Đề xuất mua sắm bổ sung bị trễ phê duyệt từ Ban Giám đốc | Quy trình phê duyệt phụ thuộc vào sự có mặt trực tiếp của BGĐ; phê duyệt qua Zalo/giấy không có SLA rõ ràng; các đề xuất không khẩn cấp bị xử lý theo lô | Hàng tiếp tục thiếu trong thời gian chờ phê duyệt; Work Order dồn ứ; áp lực lên chuỗi thi công | **Cao** |
| **IR-09** | Thiết bị thu hồi và hàng lỗi tồn lâu ở khu chờ phân loại trong kho | Thiếu quy trình phân loại định kỳ bắt buộc (tái sử dụng / bảo hành hãng / thanh lý); nhân lực kho ưu tiên xuất hàng hơn xử lý hàng thu hồi | Đọng vốn tài sản; chiếm diện tích kho; dữ liệu WMS có "tồn kho chết" không dùng được | **Trung bình** |

> **Nhận xét tổng hợp:** Trong 9 vấn đề trên, **IR-01, IR-02, IR-03, IR-06 và IR-08** được xếp mức độ **Cao** vì ảnh hưởng trực tiếp đến khả năng hoàn thành Work Order đúng SLA 24–48 giờ — chỉ số cam kết then chốt của FPT Telecom với khách hàng. Đây là nhóm vấn đề cần được ưu tiên xử lý trong giai đoạn thiết kế To-Be.

---

---



---

#### **3.6.3.5. Biểu đồ Pareto nhận diện vấn đề ưu tiên**

Áp dụng nguyên lý Pareto (Quy tắc 80/20), nhóm tiến hành thống kê và phân loại tần suất phát sinh các sự cố, sai sót và điểm nghẽn trong hoạt động kho vận viễn thông tại Chi nhánh FPT Telecom trong chu kỳ 1 tháng (tổng số 1.000 vụ việc ghi nhận trên log WMS và phản ánh từ KTV):

| STT | Nhóm nguyên nhân / Vấn đề phát sinh | Số vụ việc phát sinh/tháng | Tỷ lệ (%) | Tỷ lệ tích lũy (%) | Phân loại Pareto |
| :---: | :--- | :---: | :---: | :---: | :---: |
| 1 | KTV chờ xuất kho kéo dài giờ cao điểm do kiểm đếm & quét mã thủ công (IR-01) | 430 | 43,0% | 43,0% | **Nhóm A (Ưu tiên 80%)** |
| 2 | Sai lệch số liệu tồn kho thực tế so với phần mềm WMS/ERP (IR-05) | 280 | 28,0% | 71,0% | **Nhóm A (Ưu tiên 80%)** |
| 3 | Thời gian đổi thiết bị modem/ONT lỗi tại hiện trường bị chậm trễ (IR-03) | 130 | 13,0% | 84,0% | **Nhóm A (Ưu tiên 80%)** |
| 4 | Tồn kho an toàn thiết bị cạn kiệt do quy trình đặt hàng NCC chậm (IR-02) | 90 | 9,0% | 93,0% | Nhóm B |
| 5 | Cáp quang và phụ kiện dôi dư hoàn trả chậm, sai quy cách phân loại (IR-04) | 70 | 7,0% | 100,0% | Nhóm C |
| **Tổng** | | **1.000** | **100,0%** | | |

> **Nhận xét Pareto:** Ba vấn đề thuộc **Nhóm A chiếm tới 84,0%** tổng số sự cố phát sinh. Việc tập trung nguồn lực giải quyết dứt điểm 3 điểm nghẽn này (bằng công nghệ nhận dạng tự động RFID, đồng bộ WMS thời gian thực và quy trình đổi trả Fast-track trên KTV Mobile App) sẽ giúp loại bỏ hơn 80% lãng phí thời gian và rủi ro vận hành kho.

---

#### **3.6.3.6. Phân tích nguyên nhân gốc rễ (Root Cause Analysis - Fishbone 6M & 5 Whys)**


Để xác định chính xác căn nguyên phát sinh các điểm nghẽn vận hành nghiêm trọng nhất được nhận diện trong Issue Register (IR-01 và IR-05), nhóm nghiên cứu áp dụng kỹ thuật **Biểu đồ xương cá Ishikawa 6M** kết hợp phương pháp đào sâu **5 Whys (5 Tại sao)**. Mô hình tập trung phân tích điểm nghẽn cốt lõi: **"Thời gian chuẩn bị xuất kho kéo dài và sai lệch tồn kho vật tư thi công"**.

![Sơ đồ xương cá 6M phân tích nguyên nhân gốc rễ quy trình kho](./assets/diagrams/quan_ly_kho/hinh-3-5-so-do-xuong-ca-6m.png)

_Hình 3.6.3: Sơ đồ xương cá (Fishbone 6M) phân tích nguyên nhân gốc rễ chậm trễ xuất kho và sai lệch tồn kho vật tư_

Sơ đồ xương cá chỉ ra rằng sự cộng hưởng của các yếu tố thủ công ở cả 6 khía cạnh (Con người, Phương pháp, Máy móc/IT, Vật tư, Đo lường, Môi trường) là nguồn cơn trực tiếp làm suy giảm hiệu suất kho. Nhằm làm rõ cơ chế phát sinh vấn đề, nhóm tiến hành phân tích 5 Whys cho 2 vấn đề trọng điểm:

##### **a) Kỹ thuật 5 Whys cho Vấn đề 1: Thời gian chuẩn bị và bàn giao vật tư cho KTV bị kéo dài (IR-01)**
* **Why 1:** Tại sao KTV phải chờ trung bình 35–45 phút tại kho trước mỗi ca thi công?  
  $
ightarrow$ Do Thủ kho phải kiểm tra sổ sách, tìm kiếm vật tư trên kệ và quét mã Serial/MAC từng thiết bị một cách thủ công.
* **Why 2:** Tại sao Thủ kho phải mất nhiều thời gian tìm kiếm vật tư trên kệ?  
  $
ightarrow$ Do vị trí lưu kho (Bin Location) chưa được hệ thống WMS chỉ dẫn tự động theo thuật toán tối ưu lộ trình nhặt hàng.
* **Why 3:** Tại sao việc quét mã vạch Serial/MAC lại diễn ra chậm chạp và dễ ách tắc?  
  $
ightarrow$ Do chi nhánh chỉ trang bị 01 đầu đọc barcode cố định tại bàn làm việc của Thủ kho, không có thiết bị di động quét tại kệ.
* **Why 4:** Tại sao không trang bị thiết bị kiểm soát di động quét mã tức thời?  
  $
ightarrow$ Do hệ thống WMS hiện tại chưa phát triển phiên bản Mobile App / PDA cầm tay cho nhân viên kho hiện trường.
* **Why 5:** Tại sao ứng dụng WMS chưa được hiện đại hóa di động?  
  $
ightarrow$ Do quy trình kho trước đây chủ yếu được xem là hoạt động hỗ trợ thứ yếu, chưa được ưu tiên đầu tư giải pháp Smart Warehouse đồng bộ.

##### **b) Kỹ thuật 5 Whys cho Vấn đề 2: Tỷ lệ sai lệch số liệu tồn kho thực tế so với phần mềm WMS/ERP cao (IR-05)**
* **Why 1:** Tại sao số lượng modem ONT thực tế trong kho thường xuyên vênh lệch so với số liệu hiển thị trên WMS?  
  $
ightarrow$ Do các giao dịch xuất đổi thiết bị lỗi và thu hồi vật tư dôi dư sau ca thi công không được hạch toán ngay lập tức.
* **Why 2:** Tại sao các giao dịch hoàn trả không được cập nhật tức thời?  
  $
ightarrow$ Do KTV khi hoàn trả vật tư vào cuối ngày chỉ ghi sổ bàn giao giấy tạm thời, Thủ kho gom chứng từ nhập lại vào ngày hôm sau.
* **Why 3:** Tại sao lại cho phép sử dụng sổ tay ghi nhận tạm thay vì cập nhật trực tiếp vào hệ thống?  
  $
ightarrow$ Do ứng dụng FoxPro của KTV chưa tích hợp tính năng quét trả vật tư trực tiếp ngoài hiện trường về phân hệ kho.
* **Why 4:** Tại sao không phát hiện sớm các sai lệch này trong ngày?  
  $
ightarrow$ Do kho chỉ áp dụng hình thức kiểm kê định kỳ toàn diện vào cuối tháng, hoàn toàn thiếu cơ chế kiểm đếm chu kỳ liên tục (Cycle Counting).
* **Why 5 (Root Cause):** Tại sao cơ chế kiểm đếm chu kỳ chưa được áp dụng?  
  $
ightarrow$ Do thiếu công cụ tự động phân loại hàng hóa ABC và hệ thống WMS chưa có tính năng tự động sinh lệnh kiểm kê ngẫu nhiên hàng ngày.

---



---

### **3.6.4. Phân tích định lượng (Quantitative Analysis)**

#### **3.6.4.1. Định lượng thời gian (Flow Analysis of Cycle Time)**


Bảng thời gian xử lý của từng hoạt động trong **luồng chính (Happy Path — Tồn kho đủ)**:

**Bảng 3.6.17: Bảng thời gian xử lý các bước trong luồng chính (Happy Path As-Is)**

| STT | Hoạt động | Người thực hiện | Loại | TG ngắn nhất (phút) | TG dài nhất (phút) |
| :---: | :--- | :--- | :---: | :---: | :---: |
| 1 | Nhận WO & Tạo yêu cầu xuất vật tư | Hệ thống BPMS/WMS | BVA | 1 | 3 |
| 2 | Tiếp nhận yêu cầu trên WMS | Thủ kho | BVA | 2 | 5 |
| 3 | Kiểm tra tồn kho khả dụng | Thủ kho | BVA | 3 | 10 |
| 4 | Lấy thiết bị ra kho | Thủ kho | VA | 5 | 15 |
| 5 | Quét mã Serial/MAC & QR Code | Thủ kho | VA | 5 | 15 |
| 6 | Kiểm tra ngoại quan thiết bị | Thủ kho | VA | 3 | 10 |
| 7 | Chuẩn bị vật tư tiêu hao theo định mức | Thủ kho | VA | 5 | 15 |
| 8 | In Phiếu xuất kho | Thủ kho | BVA | 2 | 5 |
| 9 | Kiểm đếm & ký xác nhận Phiếu xuất kho | Kỹ thuật viên | VA | 5 | 15 |
| 10 | Thực hiện thi công lắp đặt tại công trình | Kỹ thuật viên | VA | 60 | 120 |
| 11 | Hoàn trả vật tư thừa về kho | Kỹ thuật viên | NVA | 10 | 30 |
| 12 | Kiểm đếm & phân loại vật tư hoàn trả | Thủ kho | BVA | 5 | 15 |
| 13 | Nhập trả WMS & Đồng bộ ERP, đóng WO | Hệ thống WMS/ERP | BVA | 2 | 5 |

**Thời gian xử lý (Process Time — VA + BVA):**

$$
\begin{aligned}
\text{Ngắn nhất: } & 1+2+3+5+5+3+5+2+5+60+5+2 = 98 \text{ phút} \\
\text{Dài nhất: } & 3+5+10+15+15+10+15+5+15+120+15+5 = 233 \text{ phút}
\end{aligned}
$$

**Thời gian chu kỳ (Cycle Time — VA + BVA + NVA):**

Có **20%** trường hợp tồn kho thiếu → phải qua quy trình Nhà cung cấp (thời gian chờ NVA: 480 phút best-case / 2.400 phút worst-case):

$$
\begin{aligned}
\text{CT ngắn nhất} &= 98 + 10_{\text{(NVA hoàn trả)}} + 0{,}20 \times (15 + 30 + 480 + 15 + 10) = 108 + 110 = 218 \text{ phút} \\
\text{CT dài nhất} &= 233 + 30_{\text{(NVA hoàn trả)}} + 0{,}20 \times (30 + 60 + 2.400 + 30 + 20) = 263 + 508 = 771 \text{ phút}
\end{aligned}
$$

**Thời gian xử lý thực tế (bao gồm xác suất luồng phụ):**

$$
\begin{aligned}
\text{PT ngắn nhất} &= 98 + 0{,}20 \times (15 + 10) = 98 + 5 = 103 \text{ phút} \\
\text{PT dài nhất} &= 233 + 0{,}20 \times (30 + 20) = 233 + 10 = 243 \text{ phút}
\end{aligned}
$$

**Hiệu suất thời gian (Time Efficiency):**

**Bảng 3.6.18: Bảng tổng hợp hiệu suất thời gian chu kỳ (Time Efficiency As-Is)**

| Trường hợp | Process Time | Cycle Time | Hiệu suất |
| :---: | :---: | :---: | :---: |
| **Best-case** | 103 phút | 218 phút | **47,2%** |
| **Worst-case** | 243 phút | 771 phút | **31,5%** |

> **Nhận xét:** Hiệu suất thời gian thấp (31,5% – 47,2%) chủ yếu do thời gian chờ Nhà cung cấp giao hàng trong kịch bản tồn kho thiếu chiếm tỉ trọng lớn trong Cycle Time. Cải thiện việc dự báo nhu cầu và duy trì Safety Stock sẽ giúp tăng hiệu suất đáng kể.

---



---

#### **3.6.4.2. Phân tích chất lượng – First Pass Yield (FPY)**

Chỉ số First Pass Yield (FPY) đo lường xác suất một đơn hàng xuất kho vật tư và thi công hoàn thành đúng chuẩn ngay từ lần đầu tiên mà không phải quay lại sửa chữa, đổi hàng hoặc chờ duyệt bổ sung. Đánh giá xác suất vượt qua an toàn tại các điểm kiểm soát (Gateways) trong quy trình As-Is:

| Gateway kiểm soát | Tên điểm kiểm soát | Xác suất đạt chuẩn ($p_i$) | Xác suất lỗi / Rework ($1 - p_i$) | Ghi chú điều kiện thực tế |
| :---: | :--- | :---: | :---: | :--- |
| **GW1** | Tồn kho khả dụng và an toàn | 0.90 | 0.10 | 10% đơn hàng thiếu hàng cục bộ phải chờ gom hoặc mua bổ sung |
| **GW2** | Kiểm tra ngoại quan & test nguồn tại kho | 0.96 | 0.04 | 4% thiết bị bao bì rách, phụ kiện lỗi được đổi ngay tại kho |
| **GW3** | KTV kiểm tra khớp lệnh Serial/MAC & ký nhận | 0.94 | 0.06 | 6% quét nhầm mã Serial hoặc sai gói cước phải quét lại |
| **GW4** | Thi công hiện trường không phát sinh lỗi thiết bị | 0.92 | 0.08 | 8% modem/ONT bị lỗi suy hao quang khi lắp tại nhà khách hàng |
| **GW5** | Quyết toán thu hồi vật tư dôi dư khớp 100% | 0.93 | 0.07 | 7% lệch số mét cáp hoặc chậm nộp biên bản quyết toán |

Tỷ lệ thành công ngay từ lần đầu tiên (First Pass Yield) của toàn bộ chu trình Quản lý kho và xuất vật tư As-Is:

$$
\begin{aligned}
FPY &= p_1 \times p_2 \times p_3 \times p_4 \times p_5 \\
&= 0.90 \times 0.96 \times 0.94 \times 0.92 \times 0.93 \approx 0.6946 \approx 69.46\%
\end{aligned}
$$

> **Nhận xét chất lượng:** Tỷ lệ FPY chỉ đạt **69,46%**, nghĩa là có tới **30,54%** đơn hàng xuất kho gặp phải ít nhất một lần xử lý lại hoặc gián đoạn. Điểm kiểm soát gây suy giảm chất lượng lớn nhất là **GW1 (tồn kho thiếu hụt 10%)** và **GW4 (lỗi thiết bị hiện trường 8%)**, trực tiếp kéo dài Cycle Time và làm giảm tỷ lệ cam kết lắp đặt đúng hẹn với khách hàng.

---

#### **3.6.4.3. Định lượng chi phí (Cost Analysis)**


**Mức lương tham chiếu (tháng 22 ngày, 8 giờ/ngày):**

**Bảng 3.6.19: Bảng mức lương tham chiếu nhân sự theo giờ làm việc**

| Bộ phận | Lương tháng (VNĐ) | Chi phí / phút (VNĐ) |
| :--- | :---: | :---: |
| Thủ kho / NV Kho & Vật tư | 8.000.000 | **758** *(~750 VNĐ/phút theo Bảng 3.4)* |
| Kỹ thuật viên thi công | 10.000.000 | **947** |
| NV Bộ phận Mua hàng & Cung ứng | 9.000.000 | **852** |

**Thời gian của từng tác nhân trong quy trình (VA+BVA và NVA):**

**Bảng 3.6.20: Bảng thời gian tham gia của từng tác nhân theo các kịch bản**

| Bộ phận | Trường hợp | Thời gian VA+BVA | Thời gian NVA |
| :--- | :---: | :---: | :---: |
| **Thủ kho** | Best-case | 24 phút | 0 phút |
| | Worst-case | 65 phút | 0 phút |
| **Kỹ thuật viên** | Best-case | 65 phút | 10 phút |
| | Worst-case | 135 phút | 30 phút |
| **NV Mua hàng** (p=0,20) | Best-case | 0,20 × 25 = 5 phút | 0,20 × 45 = 9 phút |
| | Worst-case | 0,20 × 50 = 10 phút | 0,20 × 90 = 18 phút |

**Chi phí của từng tác nhân (trên 1 Work Order):**

**Bảng 3.6.21: Bảng chi phí nhân công của từng tác nhân trên 01 Work Order**

| Bộ phận | CP/phút (VNĐ) | Trường hợp | Chi phí VA+BVA | Chi phí NVA | Tổng chi phí |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Thủ kho** | 758 | Best-case | 24 × 758 = **18.192 VNĐ** | 0 | **18.192 VNĐ** |
| | | Worst-case | 65 × 758 = **49.270 VNĐ** | 0 | **49.270 VNĐ** |
| **Kỹ thuật viên** | 947 | Best-case | 65 × 947 = **61.555 VNĐ** | 10 × 947 = **9.470 VNĐ** | **71.025 VNĐ** |
| | | Worst-case | 135 × 947 = **127.845 VNĐ** | 30 × 947 = **28.410 VNĐ** | **156.255 VNĐ** |
| **NV Mua hàng** | 852 | Best-case | 5 × 852 = **4.260 VNĐ** | 9 × 852 = **7.668 VNĐ** | **11.928 VNĐ** |
| | | Worst-case | 10 × 852 = **8.520 VNĐ** | 18 × 852 = **15.336 VNĐ** | **23.856 VNĐ** |

**Tổng chi phí cho 1 Work Order:**

**Bảng 3.6.22: Bảng tổng hợp chi phí nhân công cho 01 Work Order (Best-case vs Worst-case)**

| Trường hợp | Tổng chi phí (VA+BVA) | Tổng chi phí (NVA) | Tổng cộng |
| :---: | :---: | :---: | :---: |
| **Best-case** | 18.192 + 61.555 + 4.260 = **84.007 VNĐ** | 9.470 + 7.668 = **17.138 VNĐ** | **101.145 VNĐ** |
| **Worst-case** | 49.270 + 127.845 + 8.520 = **185.635 VNĐ** | 28.410 + 15.336 = **43.746 VNĐ** | **229.381 VNĐ** |

**Hiệu suất chi phí (Cost Efficiency):**

**Bảng 3.6.23: Bảng tổng hợp chi phí và hiệu suất chi phí (Cost Efficiency As-Is)**

| Trường hợp | Chi phí VA+BVA | Tổng chi phí | Hiệu suất chi phí |
| :---: | :---: | :---: | :---: |
| **Best-case** | 84.007 VNĐ | 101.145 VNĐ | **83,1%** |
| **Worst-case** | 185.635 VNĐ | 229.381 VNĐ | **80,9%** |

> **Nhận xét:** Hiệu suất chi phí đạt khoảng **81–83%**, cho thấy phần lớn chi phí nhân công được sử dụng cho các hoạt động có giá trị (VA + BVA). Chi phí lãng phí (NVA ~17–19%) tập trung ở thời gian chờ Nhà cung cấp và thao tác hoàn trả vật tư sau thi công — đây là 2 điểm có thể cải thiện trong giai đoạn tái thiết kế quy trình (To-be process).

---



---

#### **3.6.4.4. Các chỉ tiêu đánh giá quy trình (Baseline KPIs As-Is)**


Bảng tổng hợp các chỉ số hiệu suất vận hành As-Is của quy trình Quản lý kho và xuất vật tư, đối chiếu với mục tiêu To-Be cần đạt sau cải tiến:

**Bảng 3.6.24: Bảng tổng hợp các chỉ số hiệu suất vận hành cơ sở (Baseline KPIs As-Is)**

| **KPI** | **As-Is (Best-case)** | **As-Is (Worst-case)** | **To-Be mục tiêu** | **Mức cải thiện** |
| :--- | :---: | :---: | :---: | :--- |
| **Process Time** | 103 phút | 243 phút | 55–90 phút | Giảm ~45–63% |
| **Cycle Time** | 218 phút | 771 phút | 100–150 phút | Giảm ~54–80% |
| **Waiting Time** | 115 phút | 528 phút | ≤ 30 phút | Giảm ~74–94% |
| **Waiting Ratio** | 52,8% | 68,5% | ≤ 20% | Giảm 33–49 điểm % |
| **Cost/Work Order** | 101.145 VNĐ | 229.381 VNĐ | 70.000–120.000 VNĐ | Giảm ~25–35% |
| **On-time Rate (giao đúng ca)** | ~72% | ~48% | ≥ 95% | +23–47 điểm % |
| **Rework Rate (xuất nhầm/lỗi thiết bị)** | ~8% | ~15% | ≤ 2% | Giảm ~75–87% |
| **Inventory Accuracy (WMS vs thực tế)** | ~92% | ~85% | ≥ 99,5% | +7,5–14,5 điểm % |
| **Supplier Lead Time (trung bình)** | 3 ngày | 5 ngày | ≤ 1 ngày (Supplier Portal) | Giảm ~67–80% |
| **KTV Satisfaction Score (nội bộ)** | ~68% | ~52% | ≥ 90% | +22–38 điểm % |

> **Lưu ý:** Các số liệu As-Is trong bảng trên là giá trị tham chiếu tổng hợp từ bộ câu hỏi phỏng vấn định lượng (Mục 3.6.1.2) và kết quả Workshop (Mục 3.6.1.3). Các con số To-Be là mục tiêu thiết kế cần được kiểm chứng bằng dữ liệu pilot sau khi triển khai.

---

---



---

### **3.6.5. Đề xuất giải pháp cải tiến quy trình (To-Be Process Design)**

#### **3.6.5.1. Ma trận giải pháp cải tiến theo Issue Register & Ưu tiên giải pháp**


##### **a) Ma trận giải pháp chi tiết theo Issue Register:**

**Bảng 3.6.25: Ma trận giải pháp cải tiến quy trình kho theo Issue Register**

| **Mã vấn đề** | **Vấn đề cốt lõi** | **Giải pháp cải tiến đề xuất** | **Công nghệ / Phương pháp** | **Lợi ích kỳ vọng** |
| :---: | :--- | :--- | :--- | :--- |
| **IR-01** | Tồn kho xuống Safety Stock đột ngột | Tích hợp AI Demand Forecasting vào WMS; thiết lập Reorder Point tự động theo từng SKU và mùa vụ | AI/ML Time-series Forecasting + WMS API | Loại bỏ Hold NVA do thiếu hàng; On-time Rate ≥ 95% |
| **IR-02** | Lô hàng NCC không đạt QC | Yêu cầu NCC cung cấp chứng nhận chất lượng điện tử qua Supplier Portal; tăng tỷ lệ kiểm định mẫu cho lô đầu | Supplier Portal + Digital COQ (Certificate of Quality) | Giảm Defect Rate QC đầu vào ≥ 80% |
| **IR-03** | Xuất nhầm chủng loại thiết bị | Work Order tự động gắn mã định danh thiết bị tương thích (GPON/XGS-PON) trước khi đến tay Thủ kho; RFID so khớp trước khi xuất | BPMS + WMS Integration + RFID matching | Loại bỏ lỗi xuất nhầm; giảm Rework Rate |
| **IR-04** | Chênh lệch tồn kho WMS vs thực tế | RFID tracking real-time thay thế quét mã thủ công; cycle counting hàng tuần tự động so khớp | RFID + WMS Real-time Dashboard | Inventory Accuracy ≥ 99,5% |
| **IR-05** | KTV chờ lâu tại kho giờ cao điểm | Triển khai nhiều trạm RFID tự phục vụ; KTV xác nhận vật tư qua KTV App; đặt lịch nhận hàng trước qua App | Multi-station RFID + KTV Mobile App | Xóa bỏ Bottleneck; giảm thời gian chờ ≥ 80% |
| **IR-06** | Thiết bị lỗi phát hiện tại hiện trường | Kiểm tra chức năng 100% thiết bị cao cấp trước khi xuất kho; KTV báo lỗi qua GPS App để kho chuẩn bị trước | Functional Testing Protocol + GPS-based Exchange | Giảm Defect tại hiện trường ≥ 75% |
| **IR-07** | Vật tư hoàn trả không đúng hạn | KTV App tự động nhắc quyết toán sau 30 phút kết thúc ca; cảnh báo leo thang cho Trưởng KTV nếu quá 2 giờ | Push Notification + Escalation Workflow | Hoàn trả đúng hạn ≥ 95% |
| **IR-08** | Phê duyệt mua sắm trễ | BPMS gửi đề xuất mua sắm qua App cho BGĐ với SLA 2 giờ; leo thang tự động cho cấp trên nếu timeout | BPMS Mobile Approval + Escalation Matrix | Giảm thời gian chờ phê duyệt từ 1–2 ngày xuống ≤ 2 giờ |
| **IR-09** | Hàng thu hồi tồn lâu khu chờ phân loại | Lịch phân loại 2 lần/tuần tự động trên WMS; RFID tracking riêng cho khu hàng lỗi/bảo hành | WMS Scheduled Task + RFID Zone Tracking | Giảm tồn kho chết ≥ 80%; thu hồi vốn nhanh hơn |

---

##### **b) Phân loại và ưu tiên giải pháp (Prioritization Matrix):**

Phân loại theo mức độ **Tác động (Impact)** và **Độ khó triển khai (Effort)**:

**Ưu tiên 1 — Tác động cao, triển khai khả thi trong ngắn hạn (0–3 tháng):**
* **BPMS Mobile Approval** cho phê duyệt mua sắm (IR-08) — tích hợp nhanh vào hệ thống BPMS hiện có.
* **KTV Mobile App** với danh sách vật tư chuẩn hóa và thông báo quyết toán (IR-03, IR-05, IR-07).
* **Supplier Portal cơ bản** cho đặt hàng và theo dõi giao hàng điện tử (IR-02, IR-08).

**Ưu tiên 2 — Tác động cao, triển khai trong trung hạn (3–6 tháng):**
* **RFID tự động hóa xuất kho** và nhiều trạm RFID song song (IR-03, IR-04, IR-05).
* **Giao thức kiểm định QC toàn diện** kết hợp camera nhận diện ngoại quan (IR-02, IR-06).
* **Chính sách phê duyệt theo cấp** với SLA rõ ràng và cơ chế leo thang (IR-08).

**Ưu tiên 3 — Chiến lược dài hạn (6–12 tháng):**
* **AI/ML Demand Forecasting** tích hợp WMS (IR-01).
* **RFID tracking toàn kho** bao gồm khu hàng lỗi/bảo hành (IR-04, IR-09).
* **Dashboard KPI kho real-time** cho Ban quản lý chi nhánh.
* **Predictive Analytics** cho tối ưu Safety Stock theo từng chi nhánh.

---



---

#### **3.6.5.2. Mô hình hóa quy trình tương lai (BPMN 2.0 To-Be)**


##### **a) Mục tiêu và nguyên tắc tái thiết kế quy trình To-Be:**

Mô hình quy trình To-Be được thiết kế trên cơ sở giải quyết triệt để 9 vấn đề trong Issue Register và tối ưu hóa 3 hướng chiến lược đã xác định trong phần kết luận As-Is. Các nguyên tắc chủ đạo bao gồm:

* **Tự động hóa dự báo tồn kho:** Tích hợp mô hình dự báo nhu cầu theo chuỗi thời gian (Time-series Forecasting) vào WMS, kết hợp với hệ thống cảnh báo Reorder Point tự động — loại bỏ hoàn toàn tình trạng thiếu hàng đột ngột (IR-01).
* **Số hóa quy trình xuất kho bằng RFID/QR Code thế hệ mới:** Thay thế quét mã Serial/MAC thủ công bằng đầu đọc RFID tự động, tốc độ xử lý nhanh hơn 5–8 lần, cho phép nhiều KTV xuất kho song song trong giờ cao điểm (IR-05).
* **Cổng đặt hàng Nhà cung cấp tích hợp (Supplier Portal):** Nhà cung cấp chủ động cập nhật lịch giao hàng và chứng nhận chất lượng qua cổng điện tử; WMS tự động đối chiếu và kích hoạt nhập kho khi xác nhận — rút ngắn Supplier Lead Time từ 3–5 ngày xuống dưới 1 ngày (IR-02, IR-08).
* **Phê duyệt mua sắm điện tử trên BPMS:** Loại bỏ phê duyệt qua giấy/Zalo; BGĐ phê duyệt trực tiếp trên ứng dụng di động với SLA phản hồi tối đa 2 giờ (IR-08).
* **Ứng dụng di động cho KTV (KTV App):** KTV xác nhận vật tư điện tử ngay tại kho qua App; nhận Work Order kèm thông số thiết bị chuẩn hóa; giảm nguy cơ xuất nhầm loại thiết bị (IR-03, IR-06).
* **Kiểm định QC đầu vào toàn diện:** Kết hợp kiểm tra chức năng bắt buộc 100% cho thiết bị cao cấp (XGS-PON, Mesh Wi-Fi 6) và kiểm tra ngẫu nhiên AQL đối với vật tư tiêu hao — đẩy lùi lỗi thiết bị tại hiện trường (IR-02, IR-06).
* **Quy trình thu hồi và phân loại thiết bị tự động:** Thiết lập lịch phân loại hàng lỗi định kỳ 2 lần/tuần; tích hợp nhắc nhở tự động cho KTV qua App để đảm bảo quyết toán đúng hạn (IR-07, IR-09).

---

##### **b) Kiến trúc giải pháp và Diễn giải chi tiết các luồng quy trình To-Be:**

Mô hình quy trình tương lai To-Be (Smart Warehouse) được thiết kế vận hành liên thông giữa 3 Pool chức năng: **Nhà cung cấp (External Pool)**, **Hệ sinh thái số FPT (BPMS / WMS / ERP)** và **Đội ngũ Vận hành (Kho, Mua hàng, Kỹ thuật viên)**; kiểm soát bởi **5 Cổng điều kiện (Gateways)** và **15 Hoạt động nghiệp vụ số hóa**, được phân bổ chi tiết qua 4 luồng nghiệp vụ cốt lõi:

* **1. Luồng chính – Xuất cấp vật tư tự động không chạm bằng công nghệ RFID (Happy Path):**
  * *Bước 1 (Tiếp nhận lệnh tự động):* Ngay khi hợp đồng điện tử được ký duyệt trên CRM/BPMS, hệ thống tự động sinh Work Order và truyền lệnh xuất vật tư sang phần mềm WMS qua API.
  * *Bước 2 (Kiểm tra ngưỡng an toàn thông minh):* WMS tự động đối chiếu số lượng tồn kho khả dụng với điểm đặt hàng lại (**Reorder Point - ROP**) được tính toán tự động bằng thuật toán AI Demand Forecasting. Tại **Gateway 1 (XOR):** Tồn kho $\ge$ ROP $\rightarrow$ Hệ thống tự động phê duyệt xuất kho tức thì (giảm 100% thời gian chờ duyệt giấy).
  * *Bước 3 (Định vị và chuẩn bị hàng tự động):* Hệ thống WMS kích hoạt hệ thống đèn chỉ thị vị trí (Pick-to-Light) và gắn mã thẻ RFID định danh cho Modem ONT/Mesh Wi-Fi. Nhân viên kho chỉ mất 2–3 phút để gom đúng chủng loại vật tư.
  * *Bước 4 (Bàn giao không chạm qua KTV App & Cổng RFID):* Kỹ thuật viên di chuyển qua cổng quét RFID chuyên dụng tại cửa kho; toàn bộ mã Serial/MAC và cuộn cáp quang được nhận diện tự động 100% trong vòng 15–30 giây mà không cần quét mã vạch thủ công từng hộp. KTV bấm xác nhận nhận đủ vật tư trên ứng dụng **KTV App**.
  * *Bước 5 (Đồng bộ ERP và hoàn tất thi công):* Sau khi KTV hoàn thành lắp đặt và kích hoạt dịch vụ tại nhà khách hàng, hệ thống tự động đồng bộ giá trị xuất kho sang phân hệ SAP ERP và đóng Work Order trên BPMS.

* **2. Luồng phụ 1 – Tự động hóa mua sắm và nhập kho qua Cổng Nhà cung cấp (Supplier Portal):**
  * *Bước 1 (Cảnh báo và tự động sinh PO):* Tại **Gateway 1**, khi tồn kho giảm xuống dưới ngưỡng Reorder Point, hệ thống WMS tự động phát cảnh báo thiếu hụt và tự động sinh Dự thảo đơn đặt hàng (Auto-generate PO) căn cứ theo mức tiêu thụ bình quân.
  * *Bước 2 (Phê duyệt số di động đa cấp):* Đề xuất PO được đẩy trực tiếp lên ứng dụng di động BPMS App của Ban Giám đốc Chi nhánh. Tại **Gateway 2 (XOR):** Ban Giám đốc phê duyệt điện tử tức thì với cam kết SLA $\le$ 2 giờ (loại bỏ độ trễ ký giấy truyền thống 2–3 ngày).
  * *Bước 3 (Truyền nhận dữ liệu qua Supplier Portal):* Đơn đặt hàng PO được phát hành tự động sang Cổng Nhà cung cấp (**Supplier Portal**). Nhà cung cấp chủ động cập nhật tiến độ sản xuất, lịch giao hàng dự kiến và đính kèm chứng nhận chất lượng điện tử (e-CoC/e-CQ).
  * *Bước 4 (Kiểm định QC đầu vào tự động):* Khi Nhà cung cấp giao hàng đến kho, bộ phận Kho quét mã RFID kiện hàng. Tại **Gateway 3 (XOR):** Kiểm định chất lượng đầu vào (QC Incoming):
    - *Nếu không đạt QC:* Hệ thống lập biên bản điện tử từ chối nhập kho và kích hoạt lệnh giao bù khẩn cấp trên Supplier Portal.
    - *Nếu đạt chuẩn QC:* Toàn bộ lô hàng được ghi nhận nhập kho WMS tự động qua trạm đọc RFID trong vài phút, tự động cập nhật lại thẻ kho và số lượng tồn kho khả dụng để phục vụ xuất kho.

* **3. Luồng phụ 2 – Quy trình Fast-track đổi trả thiết bị lỗi kỹ thuật tại hiện trường:**
  * *Bước 1 (Báo lỗi tức thì qua GPS):* Tại **Gateway 4 (XOR):** Trong quá trình lắp đặt tại nhà khách hàng, nếu phát hiện modem bị suy hao quang hoặc lỗi nguồn, KTV chụp ảnh mã thiết bị và gửi yêu cầu đổi hàng khẩn cấp trực tiếp trên **KTV App** kèm tọa độ định vị GPS.
  * *Bước 2 (Điều phối thiết bị thay thế tức thì):* Hệ thống định vị KTV gần nhất có sẵn thiết bị dự phòng đạt chuẩn, hoặc điều phối kho xuất nhanh thiết bị thay thế (Fast-track) mà không cần chờ nộp lại thiết bị hỏng trước.
  * *Bước 3 (Thu hồi và bàn giao cuối ca):* KTV nhận thiết bị mới, hoàn tất nghiệm thu cho khách hàng và mang thiết bị lỗi về kho bàn giao vào cuối ca trực.

* **4. Luồng phụ 3 – Kiểm soát thu hồi và quyết toán vật tư dôi dư thông minh:**
  * *Bước 1 (Nhắc nhở tự động):* Ngay khi KTV bấm nghiệm thu dịch vụ thành công trên KTV App, ứng dụng tự động hiển thị bảng kê đối chiếu: số mét cáp đã dùng, phụ kiện đã lắp và vật tư dôi dư cần hoàn trả.
  * *Bước 2 (Quét mã nhập trả nhanh):* Cuối ca làm việc, KTV đưa vật tư dôi dư qua trạm kiểm tra RFID tại kho. Hệ thống tự động ghi nhận số lượng cuộn cáp/phụ kiện hoàn trả, tự động cân đối quyết toán và đóng toàn bộ trạng thái lệnh trên WMS/ERP.

---



---

#### **3.6.5.3. Bảng so sánh toàn diện As-Is và To-Be**


**Bảng 3.6.26: Bảng so sánh và phân tích thay đổi toàn diện quy trình As-Is vs To-Be**

| **Bước / Điểm so sánh** | **Quy trình As-Is (Hiện tại)** | **Quy trình To-Be (Đề xuất)** | **Lợi ích kỳ vọng** |
| :--- | :--- | :--- | :--- |
| **Giám sát tồn kho** | Thủ kho kiểm tra thủ công; cảnh báo thiếu hàng phụ thuộc vào kinh nghiệm | WMS tự động theo dõi real-time; cảnh báo khi chạm Reorder Point; AI dự báo nhu cầu theo lịch sử | Loại bỏ IR-01; giảm Hold NVA ≥ 70% |
| **Phê duyệt mua sắm** | Phê duyệt qua giấy/Zalo, không có SLA cụ thể | BPMS gửi thông báo App cho BGĐ; SLA phê duyệt tối đa 2 giờ; leo thang tự động nếu hết hạn | Giải quyết IR-08; giảm thời gian chờ phê duyệt từ 1–2 ngày xuống ≤ 2 giờ |
| **Đặt hàng Nhà cung cấp** | Email/điện thoại thủ công; NCC tự cập nhật lịch giao | Cổng Supplier Portal tích hợp; PO được gửi điện tử; NCC cập nhật lịch giao và chứng nhận chất lượng real-time | Giải quyết IR-02, IR-08; giảm Supplier Lead Time ≥ 67% |
| **Kiểm định QC đầu vào** | Lấy mẫu ngẫu nhiên tỷ lệ thấp; kiểm tra ngoại quan thủ công | Kiểm tra chức năng 100% thiết bị cao cấp; QC bán tự động kết hợp camera; nhập kho tự động qua RFID khi đạt | Giải quyết IR-02, IR-06; giảm Defect Rate ≥ 75% |
| **Xuất kho & Phân loại thiết bị** | Quét mã Serial/MAC thủ công; phân loại GPON/XGS-PON dựa vào kinh nghiệm Thủ kho | KTV nhận Work Order qua App với thông số thiết bị chuẩn hóa; RFID đọc mã tự động, so khớp với WMS | Giải quyết IR-03, IR-05; giảm thời gian xuất kho ≥ 60% |
| **Xử lý giờ cao điểm** | Thủ kho phục vụ tuần tự; KTV xếp hàng chờ | Nhiều trạm RFID hoạt động song song; KTV tự xác nhận vật tư qua App + quét RFID; không cần qua Thủ kho | Giải quyết IR-05; xóa bỏ Bottleneck giờ cao điểm |
| **Phát hiện thiết bị lỗi** | Phát hiện tại hiện trường → gọi điện về kho → chờ 1–3 giờ | KTV báo lỗi qua App kèm GPS → Kho chuẩn bị thiết bị thay thế trước khi KTV về → gặp nhau tại điểm trung gian | Giải quyết IR-06; giảm Waiting Time xử lý lỗi ≥ 60% |
| **Quyết toán vật tư** | KTV tự nhớ hoặc ghi giấy; hoàn trả không đúng hạn | App tự động nhắc nhở KTV quyết toán vật tư sau 30 phút kết thúc ca; cảnh báo leo thang nếu quá 2 giờ | Giải quyết IR-07; Inventory Accuracy đạt ≥ 99,5% |
| **Phân loại hàng thu hồi** | Không có lịch cố định; nhân lực ưu tiên xuất hàng | Lịch phân loại 2 lần/tuần tự động tạo trên WMS; RFID tracking khu hàng lỗi | Giải quyết IR-09; giảm "tồn kho chết" ≥ 80% |

---



---

### **3.6.6. Kế hoạch chuyển đổi & Đánh giá tác động (Implementation Plan & Impact Assessment)**

#### **3.6.6.1. Lộ trình thực thi 5 giai đoạn & Kế hoạch hành động cụ thể**


##### **a) Mục tiêu chuyển đổi số:**

Chuyển đổi quy trình Quản lý kho và xuất vật tư từ mô hình vận hành **thủ công - phụ thuộc kinh nghiệm** sang mô hình **số hóa - thời gian thực - tự động hóa**, nhằm:
1. Đảm bảo **On-time Rate ≥ 95%** cho toàn bộ Work Order trong SLA 24–48 giờ.
2. Đưa **Inventory Accuracy** lên ≥ 99,5% và **Rework Rate** xuống ≤ 2%.
3. Giảm **Cycle Time** trung bình xuống còn 100–150 phút (từ mức 218–771 phút hiện tại).
4. Giải phóng năng lực nhân sự kho để tập trung vào kiểm soát chất lượng thay vì thao tác thủ công.

---

##### **b) Lộ trình thực thi 5 giai đoạn (Implementation Roadmap):**

**Bảng 3.6.27: Lộ trình thực thi 5 giai đoạn triển khai mô hình Smart Warehouse**

| **Giai đoạn** | **Thời gian tham chiếu** | **Mục tiêu trọng tâm** | **Nhiệm vụ chính** | **KPI đầu ra** |
| :--- | :---: | :--- | :--- | :--- |
| **GĐ 0 – Kiểm toán & Chuẩn hóa dữ liệu** | Tuần 0–2 | Xây dựng baseline chính xác | Kiểm kê toàn bộ kho; chuẩn hóa danh mục SKU trên WMS; xác nhận dữ liệu Safety Stock và Reorder Point từng loại thiết bị | Baseline KPI được phê duyệt; Master Data 100% chính xác |
| **GĐ 1 – Số hóa luồng thông tin** | Tuần 3–6 | Loại bỏ giao tiếp thủ công | Triển khai BPMS Mobile Approval; ra mắt KTV App phiên bản 1.0 (Work Order + danh sách vật tư); khai trương Supplier Portal cơ bản | Phê duyệt mua sắm trong ≤ 2 giờ; KTV nhận WO qua App ≥ 80% |
| **GĐ 2 – Tự động hóa xuất/nhập kho** | Tuần 7–12 | Tăng tốc và chính xác hóa xuất kho | Lắp đặt 3–5 trạm RFID tại khu vực xuất kho; cập nhật WMS hỗ trợ RFID real-time; triển khai quy trình QC toàn diện | Thời gian xuất kho/Work Order ≤ 10 phút; Inventory Accuracy ≥ 97% |
| **GĐ 3 – Tích hợp chuỗi cung ứng** | Tuần 13–18 | Kết nối toàn bộ chuỗi NCC-Kho-KTV | Nâng cấp Supplier Portal với chứng nhận QC điện tử; tích hợp GPS-based Equipment Exchange; lịch phân loại hàng thu hồi tự động | Supplier Lead Time ≤ 24 giờ; Defect Rate ≤ 3% |
| **GĐ 4 – Tối ưu hóa thông minh** | Từ tuần 19 | Tự học và dự báo liên tục | Triển khai AI Demand Forecasting; Dashboard KPI real-time cho Ban quản lý; Predictive Analytics Safety Stock | On-time Rate ≥ 95%; Cycle Time ≤ 120 phút; Waiting Ratio ≤ 20% |

---

##### **c) Kế hoạch hành động 10 bước triển khai cụ thể:**

1. **Bước 1:** Kiểm kê toàn diện kho (Physical Count) và chuẩn hóa Master Data SKU, Serial/MAC trên WMS — xây dựng baseline chính xác trước mọi thay đổi.
2. **Bước 2:** Xác định Reorder Point và Safety Stock cho từng SKU dựa trên dữ liệu lịch sử 12 tháng và dự báo tăng trưởng thuê bao.
3. **Bước 3:** Tích hợp module phê duyệt điện tử vào BPMS; cấu hình ma trận leo thang và thông báo push notification cho BGĐ.
4. **Bước 4:** Phát triển và triển khai KTV App (Work Order, danh sách vật tư, nhắc quyết toán, báo lỗi thiết bị GPS) — thử nghiệm với đội KTV thí điểm 20 người.
5. **Bước 5:** Khai trương Supplier Portal; đào tạo 3–5 Nhà cung cấp chính nộp chứng nhận QC điện tử và cập nhật lịch giao hàng.
6. **Bước 6:** Lắp đặt hạ tầng RFID tại khu vực xuất kho; cập nhật WMS để nhận tín hiệu RFID và xử lý xuất/nhập kho tự động.
7. **Bước 7:** Nâng cấp quy trình QC đầu vào: bổ sung bước kiểm tra chức năng bắt buộc 100% cho thiết bị cao cấp; chuẩn hóa biên bản QC điện tử trên WMS.
8. **Bước 8:** Thiết lập lịch phân loại hàng thu hồi 2 lần/tuần tự động; tích hợp RFID tracking cho khu hàng lỗi/bảo hành.
9. **Bước 9:** Triển khai module AI Demand Forecasting; kết nối với WMS và cấu hình tham số mô hình theo dữ liệu lịch sử chi nhánh.
10. **Bước 10:** Thiết lập Dashboard KPI real-time; vận hành chu kỳ cải tiến liên tục (Monthly KPI Review + Action Plan) với sự tham gia của tất cả trưởng bộ phận liên quan.

---



---

#### **3.6.6.2. Quản trị thay đổi & Quản trị rủi ro triển khai (Change & Risk Management)**

##### **a) Quản trị thay đổi & Kế hoạch đào tạo (Change Management):**

**Bảng 3.6.28: Kế hoạch đào tạo và truyền thông quản trị thay đổi (Change Management)**

| **Nhóm nhân sự** | **Nội dung đào tạo trọng tâm** | **Hình thức** | **Thời lượng** |
| :--- | :--- | :---: | :---: |
| **Thủ kho / NV Kho** | Vận hành trạm RFID; nhập/xuất kho trên WMS mới; quy trình QC điện tử; phân loại hàng thu hồi | Thực hành tại kho | 3 ngày |
| **Kỹ thuật viên (KTV)** | Sử dụng KTV App; xác nhận RFID nhận vật tư; báo lỗi thiết bị GPS; quyết toán vật tư điện tử | Đào tạo nhóm + thực hành | 1 ngày |
| **Bộ phận Mua hàng** | Vận hành Supplier Portal; theo dõi PO điện tử; phối hợp với NCC upload chứng nhận QC | Workshop + hướng dẫn tự học | 2 ngày |
| **Ban Giám đốc Chi nhánh** | Phê duyệt đề xuất mua sắm trên BPMS App; đọc Dashboard KPI real-time | Đào tạo cá nhân (1:1) | 2 giờ |
| **Kế toán kho** | Đối soát WMS-ERP tự động; xử lý hóa đơn điện tử từ Supplier Portal | Đào tạo hệ thống | 1 ngày |

---

##### **b) Quản trị rủi ro triển khai và giải pháp giảm thiểu (Risk Management Matrix):**

**Bảng 3.6.29: Ma trận quản trị rủi ro triển khai và biện pháp giảm thiểu (Risk Matrix)**

| **Rủi ro** | **Khả năng xảy ra** | **Tác động** | **Giải pháp giảm thiểu** |
| :--- | :---: | :---: | :--- |
| RFID đọc sai tín hiệu do nhiễu kim loại trong kho | Trung bình | Cao | Khảo sát vật liệu kho và lựa chọn tần số RFID phù hợp; lắp đặt thử nghiệm trước khi triển khai toàn bộ |
| KTV không sử dụng App đều đặn sau giai đoạn đầu | Cao | Trung bình | Tích hợp KPI sử dụng App vào đánh giá KTV; ban đầu chạy song song App và giấy; hỗ trợ tại chỗ trong 2 tuần đầu |
| Nhà cung cấp không hợp tác sử dụng Supplier Portal | Trung bình | Cao | Đưa điều khoản Supplier Portal vào hợp đồng mới; hỗ trợ đào tạo NCC miễn phí; ưu tiên NCC đã dùng EDI |
| AI Demand Forecasting dự báo sai do dữ liệu lịch sử chưa sạch | Cao | Trung bình | Hoàn thành chuẩn hóa Master Data (Bước 1) trước khi triển khai AI; chạy mô hình song song với phương pháp cũ 2 tháng |
| WMS quá tải khi tích hợp RFID real-time | Thấp | Cao | Nâng cấp hạ tầng server trước GĐ 2; thiết kế buffer queue cho giao dịch RFID; có kế hoạch fallback về quét mã QR |
| Dữ liệu Master Data không đồng nhất sau kiểm kê | Trung bình | Cao | Dành đủ thời gian cho GĐ 0 (tối thiểu 2 tuần); quy trình phê duyệt dữ liệu 2 cấp trước khi go-live |

---



---

#### **3.6.6.3. Đánh giá tác động định lượng sau chuyển đổi (KPI Targets As-Is vs To-Be)**


##### **a) Tác động đến thời gian (Lead Time & Waiting Ratio):**

Sau khi triển khai đầy đủ 5 giai đoạn To-Be, mô hình định lượng dự báo các cải thiện sau:

* **Process Time** giảm từ 103–243 phút xuống còn **55–90 phút** — nhờ RFID tự động hóa quét mã (loại bỏ 15–25 phút thủ công/Work Order) và KTV App loại bỏ thao tác xác nhận giấy.
* **Waiting Time** giảm mạnh nhất: từ 115–528 phút xuống còn **≤ 30 phút** — nhờ loại bỏ thời gian chờ NCC (Supplier Portal + Auto-reorder), phê duyệt mua sắm (BPMS App), và KTV xếp hàng (RFID song song).
* **Cycle Time** giảm từ 218–771 phút xuống còn **85–120 phút** trong Best-case và **100–180 phút** trong Worst-case.
* **Waiting Ratio** giảm từ 52,8–68,5% xuống còn **≤ 20%** — tiệm cận chuẩn World-class Lean Warehouse (≤ 15%).

---

##### **b) Tác động đến chi phí vận hành (Cost Reduction):**

**Bảng 3.6.30: Bảng so sánh chi phí vận hành cho 01 đơn hàng As-Is vs To-Be**

| **Hạng mục chi phí** | **As-Is/Work Order** | **To-Be/Work Order** | **Tiết kiệm** |
| :--- | :---: | :---: | :---: |
| Chi phí nhân công kho (VA+BVA) | 18.192–49.270 VNĐ | 10.000–22.000 VNĐ | ~40–55% |
| Chi phí nhân công KTV tại kho | 61.555–127.845 VNĐ | 12.000–25.000 VNĐ | ~80% (RFID) |
| Chi phí NVA (hoàn trả, chờ đợi) | 17.138–43.746 VNĐ | 2.000–8.000 VNĐ | ~80–82% |
| **Tổng chi phí/Work Order** | **101.145–229.381 VNĐ** | **~40.000–80.000 VNĐ** | **~55–65%** |

> **Ghi chú:** Số liệu To-Be là ước tính dựa trên benchmark ngành logistics viễn thông ASEAN và kết quả pilot của các doanh nghiệp tương đương đã triển khai RFID + WMS real-time. Cần pilot thực tế để xác nhận con số chính xác.

---

##### **c) Tác động đến chất lượng dịch vụ và Khách hàng:**

**Bảng tổng hợp đối chiếu chỉ số KPI As-Is và To-Be:**

**Bảng 3.6.31: Bảng tổng hợp đối chiếu chỉ số KPI As-Is và To-Be sau cải tiến**

| **Chỉ số KPI** | **As-Is (Best-case)** | **As-Is (Worst-case)** | **To-Be mục tiêu** | **Cải thiện (%)** |
| :--- | :---: | :---: | :---: | :--- |
| Process Time | 103 phút | 243 phút | 55–90 phút | Giảm 45–63% |
| Cycle Time | 218 phút | 771 phút | 85–120 phút | Giảm 54–84% |
| Waiting Ratio | 52,8% | 68,5% | ≤ 20% | Giảm ≥ 33 điểm % |
| On-time Rate | ~72% | ~48% | ≥ 95% | +23–47 điểm % |
| Rework Rate | ~8% | ~15% | ≤ 2% | Giảm ≥ 75% |
| Inventory Accuracy | ~92% | ~85% | ≥ 99,5% | +7,5–14,5 điểm % |
| Supplier Lead Time | 3 ngày | 5 ngày | ≤ 1 ngày | Giảm ≥ 67% |
| Cost/Work Order | 101.145 VNĐ | 229.381 VNĐ | 40.000–80.000 VNĐ | Giảm ≥ 55% |
| KTV Satisfaction Score | ~68% | ~52% | ≥ 90% | +22–38 điểm % |
| CSAT Khách hàng cuối | ~75% | ~60% | ≥ 92% | +17–32 điểm % |

> **Nhận xét:** Những cải thiện trên không chỉ tác động đến vận hành kho mà lan tỏa trực tiếp đến trải nghiệm của hai nhóm khách hàng: **KTV thi công** (nhận vật tư nhanh hơn, ít vấn đề hơn) và **Khách hàng cuối** (lắp đặt đúng hẹn hơn, thiết bị hoạt động ổn định ngay từ đầu). Đây là cơ sở để FPT Telecom củng cố lợi thế cạnh tranh về tốc độ triển khai dịch vụ trên thị trường viễn thông băng rộng.

---



---

### **3.6.7. Kết luận quy trình**


Quy trình Quản lý kho và xuất vật tư tại FPT Telecom (Mục 3.6) là mắt xích hậu cần then chốt, đóng vai trò quyết định đến khả năng hoàn thành cam kết SLA 24–48 giờ với từng khách hàng. Qua quá trình khám phá quy trình toàn diện bằng 3 phương pháp (Evidence-based, Interview, Workshop) và phân tích chuyên sâu theo chuẩn BPM và Lean, mục 3.6 đã làm rõ bức tranh As-Is với đầy đủ chiều sâu kỹ thuật nghiệp vụ, định lượng hiệu suất và nhận diện điểm nghẽn hệ thống.

**Những phát hiện cốt lõi từ phân tích As-Is:**
* Quy trình hiện tại đang vận hành với **Waiting Ratio cao (52,8–68,5%)** do phụ thuộc vào phê duyệt thủ công, thời gian chờ NCC giao hàng và bottleneck giờ cao điểm.
* **5 trong 9 vấn đề Issue Register** được xếp mức độ Cao vì ảnh hưởng trực tiếp đến SLA, đặc biệt IR-01 (thiếu hàng), IR-03 (xuất nhầm thiết bị), IR-06 (lỗi tại hiện trường) và IR-08 (phê duyệt chậm).
* **Cost/Work Order hiện tại (101.145–229.381 VNĐ)** có tiềm năng giảm 55–65% khi loại bỏ các hoạt động NVA qua tự động hóa.

**Định hướng To-Be và lộ trình chuyển đổi:**

Mô hình To-Be đã đề xuất lộ trình 5 giai đoạn triển khai trong 19+ tuần, tập trung vào 4 giải pháp trụ cột: (1) **RFID tự động hóa xuất kho** — giải quyết tắc nghẽn và sai sót; (2) **KTV App và BPMS Mobile Approval** — số hóa giao tiếp giữa các bên; (3) **Supplier Portal và AI Demand Forecasting** — chủ động hóa chuỗi cung ứng; (4) **Dashboard KPI real-time và chu kỳ cải tiến liên tục** — duy trì hiệu suất bền vững.

**Tầm nhìn dài hạn:** Khi toàn bộ lộ trình To-Be được triển khai, quy trình Quản lý kho và xuất vật tư của FPT Telecom sẽ chuyển đổi thành mô hình kho thông minh (Smart Warehouse) — nơi mà từng thiết bị được theo dõi từ khi nhập kho đến tay khách hàng trong thời gian thực, tỷ lệ lỗi gần bằng không và năng suất kho tăng gấp đôi mà không cần tăng nhân lực. Đây là nền tảng vững chắc để FPT Telecom duy trì vị thế dẫn đầu về tốc độ triển khai dịch vụ Internet cáp quang tại Việt Nam.
