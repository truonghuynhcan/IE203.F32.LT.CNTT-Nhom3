## **3.5. Quy trình hỗ trợ: Quản lý kho và xuất vật tư**

### **3.5.1. Mô tả quy trình**

#### **a) Tổng quan luồng quy trình**

Quy trình Quản lý kho và xuất vật tư tại FPT Telecom được thực hiện tuần tự qua 6 bước chính, với sự phối hợp giữa Hệ thống BPMS/WMS, Bộ phận kho & Vật tư, Kỹ thuật viên và Bộ phận mua hàng:

<div align="center">
  <img src="assets/diagrams/quan_ly_kho/diagram%20flow.jpg" alt="Hình 3.5.1 - Sơ đồ tổng quan luồng quy trình Quản lý kho và xuất vật tư (FPT Telecom)" width="100%" style="max-width: 100%; height: auto;" />
  <br>
  <em>Hình 3.5.1 – Sơ đồ tổng quan luồng quy trình Quản lý kho và xuất vật tư (FPT Telecom)</em>
</div>

#### **b) Diễn giải luồng vận hành**

Quy trình Quản lý kho và xuất vật tư tại FPT Telecom là quy trình hỗ trợ then chốt, đảm bảo nguồn cung thiết bị liên tục và kịp thời cho các hoạt động thi công lắp đặt Internet cho khách hàng. Quy trình được khởi phát tự động từ hệ thống và kết thúc khi toàn bộ vật tư được quyết toán, hệ thống ghi nhận đầy đủ.

* **Bước 1: Tiếp nhận yêu cầu xuất vật tư**  
  Sau khi khách hàng ký kết hợp đồng lắp đặt dịch vụ Internet, hệ thống BPMS/CRM tự động tạo Work Order và đồng thời đẩy yêu cầu xuất vật tư sang hệ thống Quản lý kho (WMS). Yêu cầu xuất vật tư bao gồm: mã Work Order, địa chỉ lắp đặt, loại gói cước, danh sách vật tư cần xuất (Modem/ONT, Router Wi-Fi, dây cáp quang drop wire, hộp nối quang, phụ kiện đầu nối...) và thông tin kỹ thuật viên được phân công.

* **Bước 2: Kiểm tra tồn kho khả dụng**  
  Thủ kho tiếp nhận yêu cầu trên WMS và kiểm tra số lượng tồn kho thực tế. Tại đây phát sinh điểm quyết định:
  * **Nhánh 1 – Tồn kho đủ:** Đáp ứng yêu cầu và số lượng tồn kho vẫn trên ngưỡng Safety Stock → tiến hành chuẩn bị và xuất kho.
  * **Nhánh 2 – Tồn kho thiếu:** Lập phiếu đề xuất mua sắm. Bộ phận Mua hàng liên hệ NCC để đặt bổ sung hoặc điều chuyển từ kho tổng. Khi hàng về, thực hiện QC Incoming, nhập kho WMS rồi tiến hành xuất.

* **Bước 3: Chuẩn bị và soát mã thiết bị**  
  Thủ kho lấy thiết bị và thực hiện:
  * **Kiểm tra ngoại quan:** Bao bì nguyên vẹn, đèn tín hiệu hoạt động bình thường.
  * **Quét mã vạch/QR:** Nhập Serial Number và địa chỉ MAC vào WMS, gắn với mã Work Order và thuê bao khách hàng.
  * **Chuẩn bị vật tư tiêu hao:** Cáp quang, jack SC/APC, băng keo, clip cáp... theo định mức.
  * **In Phiếu xuất kho:** Phiếu xuất kho phải đầy đủ thông tin cần thiết.

* **Bước 4: Xuất kho và bàn giao cho kỹ thuật viên**  
  Kỹ thuật viên (KTV) được phân công đến nhận vật tư, kiểm đếm theo Phiếu xuất kho và ký xác nhận (giấy hoặc ký điện tử trên thiết bị di động kết nối WMS). Từ thời điểm này, trách nhiệm quản lý thiết bị chuyển từ Thủ kho sang KTV cho đến khi hoàn tất lắp đặt và nghiệm thu.

* **Bước 5: Thu hồi và nhập trả vật tư**  
  Sau khi hoàn thành thi công, KTV quyết toán vật tư:
  * **Vật tư thừa:** Mang về kho, Thủ kho kiểm đếm và nhập trả WMS.
  * **Thiết bị hỏng/lỗi:** KTV liên hệ kho đổi thiết bị mới, mang thiết bị hỏng về. Thủ kho gán trạng thái “Hỏng – chờ bảo hành/thanh lý”, chuyển sang khu vực kho hàng lỗi riêng.
  * **Thiết bị thu hồi từ KH cũ (hủy hợp đồng, nâng cấp):** Nhập kho thu hồi, phân loại (dùng lại/thanh lý).

* **Bước 6: Cập nhật và đồng bộ hệ thống**  
  Sau khi mọi giao dịch xuất/nhập được hoàn tất, WMS tự động đồng bộ dữ liệu tồn kho sang ERP để cập nhật giá trị kho hàng phục vụ hạch toán. Trạng thái Work Order trên BPMS được đóng lại, xác nhận hoàn chỉnh giai đoạn cung ứng vật tư. Bộ phận Kế toán kho đối soát chứng từ xuất nhập định kỳ (ngày/tuần/tháng).

#### **c) Các tác nhân tham gia quy trình (Actors)**

| STT | Tác nhân | Vai trò trong quy trình |
| :---: | :--- | :--- |
| **1** | **Hệ thống BPMS/CRM** | Tự động tạo và đẩy yêu cầu xuất vật tư khi có Work Order lắp đặt mới; nhận xác nhận hoàn tất từ WMS để đóng đơn. |
| **2** | **Hệ thống WMS / ERP** | Lưu trữ và quản lý dữ liệu tồn kho theo thời gian thực; ghi nhận giao dịch xuất/nhập; đồng bộ hạch toán sang ERP. |
| **3** | **Thủ kho / NV Kho & Vật tư** | Tiếp nhận yêu cầu; kiểm tra tồn kho; chuẩn bị, soát mã và xuất thiết bị; tiếp nhận vật tư thu hồi/trả lại; cập nhật WMS. |
| **4** | **Kỹ thuật viên thi công** | Tiếp nhận và ký nhận vật tư; sử dụng thiết bị trong quá trình thi công; hoàn trả vật tư thừa/hỏng sau thi công. |
| **5** | **Bộ phận mua hàng & cung ứng** | Xử lý đề xuất mua sắm khi kho thiếu hụt; liên hệ NCC đặt hàng; theo dõi tiến độ giao hàng. |
| **6** | **Nhà cung cấp** | Cung cấp Modem/ONT, Router Wi-Fi, cáp quang và phụ kiện viễn thông theo đơn đặt hàng của FPT Telecom. |
| **7** | **Bộ phận kế toán kho** | Đối soát chứng từ xuất nhập kho; hạch toán giá thành vật tư theo từng Work Order; lập báo cáo tồn kho định kỳ. |

#### **d) Khách hàng của quy trình (Customer)**

* **Khách hàng nội bộ (Internal Customer):** Đội Kỹ thuật viên thi công – những người trực tiếp nhận vật tư từ kho để thực hiện lắp đặt tại nhà khách hàng. Họ cần vật tư đúng chủng loại, đủ số lượng và kịp thời để đảm bảo hoàn thành Work Order đúng lịch hẹn với khách hàng cuối.
* **Khách hàng bên ngoài (External Customer) – gián tiếp:** Người dùng cuối đăng ký dịch vụ Internet FPT Telecom. Chất lượng và tiến độ xuất kho ảnh hưởng trực tiếp đến thời gian chờ lắp đặt và chất lượng thiết bị được cung cấp.

#### **e) Giá trị mang lại (Value Proposition)**

* **Đảm bảo tính liên tục của chuỗi cung ứng dịch vụ:** Kho vật tư hoạt động trơn tru giúp không có Work Order nào bị trì hoãn do thiếu thiết bị, góp phần duy trì SLA lắp đặt trong vòng 24–48 giờ sau khi ký hợp đồng.
* **Kiểm soát tài sản chính xác:** Việc quét và ghi nhận Serial/MAC của từng Modem/ONT, gắn với thuê bao cụ thể, giúp FPT Telecom truy xuất tài sản, hỗ trợ bảo hành và ngăn ngừa thất thoát thiết bị.
* **Tối ưu hóa vốn lưu động:** Quản lý tồn kho theo Safety Stock và Reorder Point giúp tránh đọng vốn do tồn kho quá lớn hoặc gián đoạn dịch vụ do tồn kho quá ít.

#### **f) Những kết quả có thể đạt được (Possible Outcomes)**

| Kết quả | Mô tả |
| :--- | :--- |
| **Thành công - xuất kho đủ & đúng hàng** | Tồn kho đủ thiết bị được xuất kho đúng loại, đủ số lượng, KTV nhận hàng và hoàn tất lắp đặt cho khách hàng trong ngày, quyết toán vật tư thành công. |
| **Chờ bổ sung - đặt hàng khẩn cấp** | Tồn kho dưới mức an toàn kích hoạt quy trình đặt hàng bổ sung từ NCC hoặc điều chuyển kho. Work Order bị trì hoãn và cần thông báo lại lịch hẹn cho khách hàng. |
| **Thu hồi & đổi trả thiết bị** | Thiết bị phát hiện lỗi tại hiện trường hoặc vật tư thừa sau thi công được hoàn trả kho, phân loại và xử lý (bảo hành/thanh lý). |
| **Hủy Work Order do thiết bị không tương thích** | Trường hợp thiếu thiết bị chuyên dụng cho hạ tầng GPON/XGS-PON đặc thù Work Order bị tạm hoãn và chờ phê duyệt đặt hàng chuyên biệt từ Ban Kỹ thuật. |

---

### **3.5.2. Mô hình hóa quy trình hiện tại (Sơ đồ BPMN - As-is)**

Sơ đồ BPMN dưới đây mô tả toàn bộ luồng quy trình Quản lý kho và xuất vật tư tại FPT Telecom theo trạng thái hiện tại (As-is), bao gồm 4 phân làn trách nhiệm (Swimlanes) tương ứng với 4 nhóm tác nhân chính tham gia quy trình.

#### **a) Phân tích các phần tử BPMN - Pools và Lanes**

| Phân vùng (Pool) | Làn trách nhiệm (Lane) | Diễn giải |
| :--- | :--- | :--- |
| **FPT Telecom** | **Hệ thống BPMS / WMS** | Nền tảng hệ thống tự động hóa; xử lý Work Order, quản lý dữ liệu tồn kho và đồng bộ ERP. |
| **FPT Telecom** | **Bộ phận kho & Vật tư** | Thực hiện toàn bộ hoạt động vật lý: kiểm kho, chuẩn bị, xuất và nhập trả thiết bị. |
| **FPT Telecom** | **Kỹ thuật viên thi công** | Nhận vật tư, sử dụng trong thi công, hoàn trả vật tư thừa/thiết bị lỗi sau công việc. |
| **Bên ngoài** | **Bộ phận mua hàng / nhà cung cấp** | Xử lý đơn mua hàng bổ sung và cung ứng thiết bị khi kho thiếu hụt. |

#### **b) Diễn giải luồng chính (Happy Path - Tồn kho đủ)**

| Làn trách nhiệm (Swimlane) | Hoạt động / Luồng xử lý |
| :--- | :--- |
| **BPMS/WMS** | Nhận Work Order từ CRM → Tạo yêu cầu xuất vật tư → Gửi yêu cầu sang WMS |
| **Kho & Vật tư** | Tiếp nhận yêu cầu → Kiểm tra tồn kho → XOR Gateway: Tồn kho đủ? |
| **Kho & Vật tư** | Đủ → Lấy thiết bị → Quét mã Serial/MAC và kiểm tra ngoại quan → In Phiếu xuất kho → Bàn giao thiết bị cho KTV |
| **Kỹ thuật viên** | Kiểm đếm vật tư → Ký xác nhận Phiếu xuất kho → Thực hiện thi công, lắp đặt → Hoàn tất công việc → Mang vật tư thừa về kho |
| **Kho & Vật tư** | Tiếp nhận vật tư hoàn trả → Kiểm đếm → Nhập trả trên WMS |
| **BPMS/WMS** | Cập nhật Work Order “Hoàn tất vật tư” → Đồng bộ dữ liệu sang ERP → Kết thúc |

#### **c) Luồng phụ 1: Kịch bản tồn kho thiếu**

| Làn trách nhiệm (Swimlane) | Hoạt động / Luồng xử lý |
| :--- | :--- |
| **Kho & Vật tư** | XOR Gateway: Tồn kho thiếu → Lập Phiếu đề xuất mua sắm |
| **Bộ phận Mua hàng** | Nhận đề xuất → Liên hệ NCC/Kho tổng → Đặt hàng hoặc điều chuyển vật tư bổ sung |
| **Nhà cung cấp** | Giao hàng đến FPT Telecom |
| **Kho & Vật tư** | Tiếp nhận hàng → Kiểm tra chất lượng đầu vào |
| **Kho & Vật tư** | XOR Gateway: Đạt chất lượng? |
| **Kho & Vật tư** | Không đạt → Trả hàng cho nhà cung cấp |
| **Kho & Vật tư** | Đạt → Nhập kho trên WMS → Quay lại luồng xuất kho |

#### **d) Luồng phụ 2: Kịch bản thiết bị lỗi**

| Làn trách nhiệm (Swimlane) | Hoạt động / Luồng xử lý |
| :--- | :--- |
| **Kỹ thuật viên** | XOR Gateway: Thiết bị lỗi? → Có → Liên hệ Kho yêu cầu đổi thiết bị mới |
| **Kho & Vật tư** | Chuẩn bị thiết bị thay thế → Bàn giao cho kỹ thuật viên |
| **Kỹ thuật viên** | Nhận thiết bị mới → Tiếp tục thi công → Hoàn tất công việc → Mang thiết bị lỗi về kho |
| **Kho & Vật tư** | Tiếp nhận thiết bị lỗi → Gán trạng thái “Hỏng – Chờ bảo hành” trên WMS → Chuyển vào khu vực kho hàng lỗi riêng biệt |

#### **e) Sơ đồ BPMN - Quản lý xuất kho và xuất vật tư**

<div align="center">
  <img src="assets/diagrams/quan_ly_kho/warehouse%20management.png" alt="Hình 3.5.2 - Sơ đồ BPMN As-is: Quy trình Quản lý kho và xuất vật tư tại FPT Telecom" width="100%" style="max-width: 100%; height: auto;" />
  <br>
  <em>Hình 3.5.2 – Sơ đồ BPMN As-is: Quy trình Quản lý kho và xuất vật tư tại FPT Telecom</em>
</div>

---

### **3.5.3. Phân tích định tính**

#### **3.5.3.1. Phân tích giá trị gia tăng**

(VA, BVA, NVA)

[nội dung… mẫu tài liệu CellPhoneS]

#### **3.5.3.2. Phân tích lãng phí**

(Sự vận chuyển, Thời gian chờ/Hold, Làm quá mức...)

[nội dung… mẫu tài liệu CellPhoneS]

#### **3.5.3.3. Phân tích các bên liên quan**

[tùy trường hợp sẽ không có mục này…]

(Stakeholder Analysis) và Sổ đăng ký vấn đề (Issue Register)

---

### **3.5.4. Phân tích định lượng**

Định lượng Thời gian (Cycle time, Wait time)

Định lượng Chi phí
