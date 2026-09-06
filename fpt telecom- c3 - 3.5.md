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
  * **Nhánh 2 – Tồn kho thiếu:** Lập phiếu đề xuất mua sắm. Bộ phận Mua hàng liên hệ Nhà cung cấp để đặt bổ sung hoặc điều chuyển từ kho tổng. Khi hàng về, thực hiện QC Incoming, nhập kho WMS rồi tiến hành xuất.

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
| **5** | **Bộ phận mua hàng & cung ứng** | Xử lý đề xuất mua sắm khi kho thiếu hụt; liên hệ Nhà cung cấp đặt hàng; theo dõi tiến độ giao hàng. |
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
| **Chờ bổ sung - đặt hàng khẩn cấp** | Tồn kho dưới mức an toàn kích hoạt quy trình đặt hàng bổ sung từ Nhà cung cấp hoặc điều chuyển kho. Work Order bị trì hoãn và cần thông báo lại lịch hẹn cho khách hàng. |
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
| **Bộ phận Mua hàng** | Nhận đề xuất → Liên hệ Nhà cung cấp/Kho tổng → Đặt hàng hoặc điều chuyển vật tư bổ sung |
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

Bảng dưới đây phân loại toàn bộ các hoạt động trong quy trình **Quản lý kho và xuất vật tư** theo ba nhóm:
- **VA (Value-Added):** Hoạt động tạo ra giá trị trực tiếp cho khách hàng; khách hàng sẵn sàng chi trả.
- **BVA (Business Value-Added):** Bắt buộc theo yêu cầu nội bộ hoặc quy định, nhưng khách hàng không trực tiếp nhận ra giá trị.
- **NVA (Non-Value-Added):** Không tạo ra giá trị, cần được giảm thiểu hoặc loại bỏ.

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

_Bảng 3.5.1: Phân loại giá trị gia tăng quy trình Quản lý kho và xuất vật tư_

**Tổng hợp phân loại:**

| Loại giá trị | Số lượng hoạt động | Tỉ lệ |
| :---: | :---: | :---: |
| **VA** | 6 | 27,3% |
| **BVA** | 12 | 54,5% |
| **NVA** | 4 | 18,2% |
| **Tổng** | **22** | **100%** |

> **Nhận xét:** Tỉ lệ NVA chiếm 18,2% — chủ yếu phát sinh ở kịch bản tồn kho thiếu (mua sắm qua Nhà cung cấp) và thời gian hoàn trả vật tư thừa. Đây là các điểm cần ưu tiên tối ưu hóa nhằm nâng cao hiệu quả quy trình.

---


#### **3.5.3.2. Phân tích lãng phí**

Dựa trên 7 loại lãng phí (7 Wastes) theo phương pháp Lean, bảng dưới đây xác định các lãng phí hiện diện trong quy trình Quản lý kho và xuất vật tư tại FPT Telecom:

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

#### **3.5.3.3. Phân tích các bên liên quan (Stakeholder Analysis)**

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

### **3.5.4. Phân tích định lượng**

#### **3.5.4.1. Định lượng thời gian**

Bảng thời gian xử lý của từng hoạt động trong **luồng chính (Happy Path — Tồn kho đủ)**:

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

$$\text{Ngắn nhất: } 1+2+3+5+5+3+5+2+5+60+5+2 = 98 \text{ phút}$$
$$\text{Dài nhất: } 3+5+10+15+15+10+15+5+15+120+15+5 = 233 \text{ phút}$$

**Thời gian chu kỳ (Cycle Time — VA + BVA + NVA):**

Có **20%** trường hợp tồn kho thiếu → phải qua quy trình Nhà cung cấp (thời gian chờ NVA: 480 phút best-case / 2.400 phút worst-case):

$$\text{CT ngắn nhất} = 98 + 10_{\text{(NVA hoàn trả)}} + 0{,}20 \times (15 + 30 + 480 + 15 + 10) = 108 + 110 = 218 \text{ phút}$$
$$\text{CT dài nhất} = 233 + 30_{\text{(NVA hoàn trả)}} + 0{,}20 \times (30 + 60 + 2.400 + 30 + 20) = 263 + 508 = 771 \text{ phút}$$

**Thời gian xử lý thực tế (bao gồm xác suất luồng phụ):**

$$\text{PT ngắn nhất} = 98 + 0{,}20 \times (15 + 10) = 98 + 5 = 103 \text{ phút}$$
$$\text{PT dài nhất} = 233 + 0{,}20 \times (30 + 20) = 233 + 10 = 243 \text{ phút}$$

**Hiệu suất thời gian (Time Efficiency):**

| Trường hợp | Process Time | Cycle Time | Hiệu suất |
| :---: | :---: | :---: | :---: |
| **Best-case** | 103 phút | 218 phút | **47,2%** |
| **Worst-case** | 243 phút | 771 phút | **31,5%** |

> **Nhận xét:** Hiệu suất thời gian thấp (31,5% – 47,2%) chủ yếu do thời gian chờ Nhà cung cấp giao hàng trong kịch bản tồn kho thiếu chiếm tỉ trọng lớn trong Cycle Time. Cải thiện việc dự báo nhu cầu và duy trì Safety Stock sẽ giúp tăng hiệu suất đáng kể.

---

#### **3.5.4.2. Định lượng chi phí**

**Mức lương tham chiếu (tháng 22 ngày, 8 giờ/ngày):**

| Bộ phận | Lương tháng (VNĐ) | Chi phí / phút (VNĐ) |
| :--- | :---: | :---: |
| Thủ kho / NV Kho & Vật tư | 8.000.000 | **758** |
| Kỹ thuật viên thi công | 10.000.000 | **947** |
| NV Bộ phận Mua hàng & Cung ứng | 9.000.000 | **852** |

**Thời gian của từng tác nhân trong quy trình (VA+BVA và NVA):**

| Bộ phận | Trường hợp | Thời gian VA+BVA | Thời gian NVA |
| :--- | :---: | :---: | :---: |
| **Thủ kho** | Best-case | 24 phút | 0 phút |
| | Worst-case | 65 phút | 0 phút |
| **Kỹ thuật viên** | Best-case | 65 phút | 10 phút |
| | Worst-case | 135 phút | 30 phút |
| **NV Mua hàng** (p=0,20) | Best-case | 0,20 × 25 = 5 phút | 0,20 × 45 = 9 phút |
| | Worst-case | 0,20 × 50 = 10 phút | 0,20 × 90 = 18 phút |

**Chi phí của từng tác nhân (trên 1 Work Order):**

| Bộ phận | CP/phút (VNĐ) | Trường hợp | Chi phí VA+BVA | Chi phí NVA | Tổng chi phí |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Thủ kho** | 758 | Best-case | 24 × 758 = **18.192 VNĐ** | 0 | **18.192 VNĐ** |
| | | Worst-case | 65 × 758 = **49.270 VNĐ** | 0 | **49.270 VNĐ** |
| **Kỹ thuật viên** | 947 | Best-case | 65 × 947 = **61.555 VNĐ** | 10 × 947 = **9.470 VNĐ** | **71.025 VNĐ** |
| | | Worst-case | 135 × 947 = **127.845 VNĐ** | 30 × 947 = **28.410 VNĐ** | **156.255 VNĐ** |
| **NV Mua hàng** | 852 | Best-case | 5 × 852 = **4.260 VNĐ** | 9 × 852 = **7.668 VNĐ** | **11.928 VNĐ** |
| | | Worst-case | 10 × 852 = **8.520 VNĐ** | 18 × 852 = **15.336 VNĐ** | **23.856 VNĐ** |

**Tổng chi phí cho 1 Work Order:**

| Trường hợp | Tổng chi phí (VA+BVA) | Tổng chi phí (NVA) | Tổng cộng |
| :---: | :---: | :---: | :---: |
| **Best-case** | 18.192 + 61.555 + 4.260 = **84.007 VNĐ** | 9.470 + 7.668 = **17.138 VNĐ** | **101.145 VNĐ** |
| **Worst-case** | 49.270 + 127.845 + 8.520 = **185.635 VNĐ** | 28.410 + 15.336 = **43.746 VNĐ** | **229.381 VNĐ** |

**Hiệu suất chi phí (Cost Efficiency):**

| Trường hợp | Chi phí VA+BVA | Tổng chi phí | Hiệu suất chi phí |
| :---: | :---: | :---: | :---: |
| **Best-case** | 84.007 VNĐ | 101.145 VNĐ | **83,1%** |
| **Worst-case** | 185.635 VNĐ | 229.381 VNĐ | **80,9%** |

> **Nhận xét:** Hiệu suất chi phí đạt khoảng **81–83%**, cho thấy phần lớn chi phí nhân công được sử dụng cho các hoạt động có giá trị (VA + BVA). Chi phí lãng phí (NVA ~17–19%) tập trung ở thời gian chờ Nhà cung cấp và thao tác hoàn trả vật tư sau thi công — đây là 2 điểm có thể cải thiện trong giai đoạn tái thiết kế quy trình (To-be process).

