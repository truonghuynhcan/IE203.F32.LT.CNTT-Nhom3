## 3.3. Quy trình quản lý 2: Quản lý và mở rộng hạ tầng viễn thông (Cáp quang & Port)

### 3.3.1. Mô tả quy trình

#### 3.3.1.1. Các tác nhân tham gia – Actor

**Bộ phận Kinh doanh (Sales)** là tác nhân khởi tạo nhu cầu của quy trình. Sales ghi nhận nhu cầu phát triển thuê bao, tình trạng thiếu tài nguyên hoặc nhu cầu mở rộng vùng phủ và gửi yêu cầu mở rộng hạ tầng.

**Bộ phận Kỹ thuật hạ tầng (INF)** là tác nhân chịu trách nhiệm chính trong giai đoạn đánh giá kỹ thuật. INF kiểm tra hiện trạng hạ tầng trên hệ thống, khảo sát thực tế, đánh giá khả năng đáp ứng, lập phương án kỹ thuật và xây dựng dự toán đầu tư.

**Kế hoạch & Đầu tư** chịu trách nhiệm thẩm định phương án mở rộng. Bộ phận này đánh giá tính cần thiết, khả thi và ngân sách trước khi đưa ra quyết định cho phép hoặc không cho phép tiếp tục triển khai.

**Kho vật tư** chịu trách nhiệm chuẩn bị vật tư và thiết bị cần thiết theo phương án đã được phê duyệt.

**Bộ phận phụ trách nguồn lực/đội kỹ thuật** chịu trách nhiệm phân công nhân sự và bố trí đội triển khai tại hiện trường.

**Đội thi công/Kỹ thuật viên** trực tiếp thực hiện kéo cáp, đấu nối, lắp đặt thiết bị, kiểm tra tín hiệu, nghiệm thu công trình và xử lý lỗi kỹ thuật khi phát sinh.

**Hệ thống GIS/CRM** hỗ trợ ghi nhận yêu cầu ban đầu, lưu trữ thông tin hạ tầng và cập nhật trạng thái tài nguyên mạng sau khi công trình hoàn thành.


#### 3.3.1.2. Khách hàng mục tiêu – Customer

Khách hàng của quy trình quản lý và mở rộng hạ tầng bao gồm cả khách hàng nội bộ và khách hàng ngoại bộ.

**Khách hàng nội bộ – Sales:** Bộ phận Sales cần biết khu vực nào đã đủ điều kiện để bán và triển khai dịch vụ, đồng thời cần biết thời điểm Port và tài nguyên mạng đã sẵn sàng. Khi quy trình hoàn tất, Sales có cơ sở để tiếp tục phát triển thuê bao tại khu vực vừa được mở rộng.

**Khách hàng nội bộ – TNC/Kỹ thuật triển khai:** Đội ngũ kỹ thuật triển khai cần Port, tuyến cáp và thiết bị truy cập thực tế phù hợp với dữ liệu được ghi nhận trên hệ thống. Kết quả của quy trình giúp giảm tình trạng nhận lệnh triển khai nhưng thực tế lại thiếu Port, thiếu tuyến cáp hoặc dữ liệu hệ thống không phù hợp với hiện trường.

**Khách hàng ngoại bộ – người dùng Internet:** Người đăng ký dịch vụ là đối tượng hưởng lợi cuối cùng từ việc mở rộng hạ tầng. Những khu vực trước đây không thể tiếp nhận thêm thuê bao do thiếu năng lực mạng có thể được phục vụ sau khi hạ tầng được mở rộng.

**Quản lý doanh nghiệp:** Ban quản lý sử dụng kết quả của quy trình để kiểm soát nhu cầu đầu tư, CAPEX, tiến độ triển khai, chất lượng công trình và khả năng khai thác tài sản sau đầu tư.

#### 3.3.1.3. Các bước thực hiện

###### Bảng 3. : Luồng các bước thực hiện quy trình quản lý và mở rộng hạ tầng viễn thông

| STT | Bước thực hiện | Bộ phận/Lane thực hiện | Loại phần tử BPMN | Mô tả chi tiết | Kết quả/nhánh tiếp theo |
|---:|---|---|---|---|---|
| 1 | Phát sinh nhu cầu mở rộng hạ tầng | Bộ phận Kinh doanh (Sales) | Start Event | Quy trình bắt đầu khi phát sinh nhu cầu mở rộng hạ tầng do tăng nhu cầu thuê bao, thiếu Port, cần mở rộng vùng phủ hoặc cần bổ sung năng lực mạng. | Chuyển sang tiếp nhận yêu cầu mở rộng hạ tầng. |
| 2 | Tiếp nhận yêu cầu mở rộng hạ tầng | Bộ phận Kinh doanh (Sales) | User Task | Sales tiếp nhận và tổng hợp thông tin về khu vực cần mở rộng, nhu cầu phát triển thuê bao và tình trạng tài nguyên hạ tầng. | Chuyển sang ghi nhận yêu cầu trên hệ thống. |
| 3 | Ghi nhận yêu cầu mở rộng trên hệ thống | Hệ thống GIS/CRM | Service Task | Hệ thống ghi nhận thông tin ban đầu của yêu cầu để phục vụ việc kiểm tra và đánh giá hạ tầng. | Chuyển sang kiểm tra hiện trạng hạ tầng. |
| 4 | Kiểm tra hiện trạng hạ tầng | Bộ phận Kỹ thuật hạ tầng (INF) | User Task | INF kiểm tra dữ liệu hiện có như tuyến cáp, số lượng Port khả dụng, thiết bị truy cập và tài nguyên mạng tại khu vực. | Chuyển sang khảo sát thực tế. |
| 5 | Khảo sát thực tế khu vực triển khai | Bộ phận Kỹ thuật hạ tầng (INF) | User Task | INF khảo sát thực địa để xác định điều kiện tuyến cáp, vị trí lắp đặt, khả năng thi công và các yếu tố ảnh hưởng đến phương án mở rộng. | Chuyển sang đánh giá khả năng đáp ứng hạ tầng. |
| 6 | Đánh giá khả năng đáp ứng hạ tầng | Bộ phận Kỹ thuật hạ tầng (INF) | User Task | INF tổng hợp dữ liệu hệ thống và kết quả khảo sát để đánh giá khả năng đáp ứng của hạ tầng hiện hữu. | Chuyển sang GW1. |
| 7 | GW1: Hạ tầng hiện tại đáp ứng? | Bộ phận Kỹ thuật hạ tầng (INF) | Exclusive Gateway | Xác định hạ tầng hiện tại có đủ khả năng đáp ứng nhu cầu hay không. | **Có:** kết thúc, không cần mở rộng. **Không:** lập phương án kỹ thuật và dự toán đầu tư. |
| 8 | Lập phương án kỹ thuật và dự toán đầu tư | Bộ phận Kỹ thuật hạ tầng (INF) | User Task | INF xây dựng phương án mở rộng, xác định hạng mục kỹ thuật, vật tư, thiết bị, nhân lực và chi phí dự kiến. | Chuyển sang gửi hồ sơ phương án mở rộng. |
| 9 | Gửi hồ sơ phương án mở rộng | Bộ phận Kỹ thuật hạ tầng (INF) | Send Task | Hồ sơ phương án được chuyển sang Bộ phận Kế hoạch & Đầu tư để thẩm định. | Chuyển sang thẩm định kế hoạch mở rộng. |
| 10 | Thẩm định kế hoạch mở rộng | Kế hoạch & Đầu tư | User Task | Bộ phận Kế hoạch & Đầu tư đánh giá tính cần thiết, tính khả thi và ngân sách của phương án. | Chuyển sang GW2. |
| 11 | GW2: Kế hoạch được phê duyệt? | Kế hoạch & Đầu tư | Exclusive Gateway | Xác định phương án mở rộng có được phê duyệt để triển khai hay không. | **Không:** kết thúc, không được phê duyệt đầu tư. **Có:** chuẩn bị vật tư và nguồn lực. |
| 12 | Chuẩn bị vật tư và nguồn lực | Kho vật tư | User Task | Chuẩn bị các điều kiện cần thiết trước thi công, bao gồm vật tư, thiết bị và nguồn lực phục vụ triển khai. | Chuyển sang GW3. |
| 13 | GW3: Phân tách chuẩn bị triển khai | Kho vật tư | Parallel Gateway – Split | Tách quá trình chuẩn bị thành hai luồng được thực hiện song song. | Luồng 1: Chuẩn bị thiết bị. Luồng 2: Phân công nhân lực. |
| 14 | Chuẩn bị thiết bị | Kho vật tư | User Task | Kho chuẩn bị các vật tư và thiết bị cần thiết theo phương án đã được phê duyệt. | Chuyển vào GW4. |
| 15 | Phân công nhân lực | Bộ phận phụ trách nguồn lực/đội kỹ thuật | User Task | Bố trí nhân sự và đội kỹ thuật thực hiện công việc tại hiện trường. | Chuyển vào GW4. |
| 16 | GW4: Hoàn tất chuẩn bị triển khai | Khối triển khai | Parallel Gateway – Join | Đồng bộ hai luồng chuẩn bị, chỉ cho phép tiếp tục khi cả thiết bị và nhân lực đều sẵn sàng. | Chuyển sang thi công mở rộng hạ tầng. |
| 17 | Thi công mở rộng hạ tầng | Đội thi công/Kỹ thuật viên | User Task | Thực hiện kéo cáp, đấu nối, lắp đặt thiết bị và bổ sung tài nguyên mạng theo phương án đã được phê duyệt. | Chuyển sang kiểm tra tín hiệu và chất lượng công trình. |
| 18 | Kiểm tra tín hiệu và chất lượng công trình | Đội thi công/Kỹ thuật viên | User Task | Kiểm tra tín hiệu, chất lượng kết nối và mức độ đáp ứng các yêu cầu kỹ thuật sau thi công. | Chuyển sang GW5. |
| 19 | GW5: Nghiệm thu đạt? | Đội thi công/Kỹ thuật viên | Exclusive Gateway | Xác định công trình có đạt yêu cầu nghiệm thu hay không. | **Đạt:** cập nhật dữ liệu GIS/CRM. **Không:** xử lý lỗi kỹ thuật. |
| 20 | Xử lý lỗi kỹ thuật | Đội thi công/Kỹ thuật viên | User Task | Xác định nguyên nhân và xử lý các lỗi phát sinh trong quá trình kiểm tra, nghiệm thu. | Chuyển sang GW7. |
| 21 | GW7: Tình trạng khắc phục lỗi? | Đội thi công/Kỹ thuật viên | Exclusive Gateway | Đánh giá kết quả xử lý lỗi kỹ thuật. | **Không thể khắc phục:** kết thúc không đạt nghiệm thu. **Đã khắc phục:** xác nhận kết quả khắc phục. |
| 22 | Xác nhận kết quả khắc phục | Đội thi công/Kỹ thuật viên | User Task | Xác nhận tình trạng sau xử lý và ghi nhận kết quả khắc phục lỗi. | Kết thúc instance xử lý lỗi hiện tại. |
| 23 | Cập nhật dữ liệu hạ tầng trên GIS/CRM | Hệ thống GIS/CRM | Service Task | Cập nhật thông tin tuyến cáp, thiết bị, Port và trạng thái khai thác của hạ tầng sau khi nghiệm thu đạt. | Chuyển sang GW6. |
| 24 | GW6: Cập nhật dữ liệu thành công? | Hệ thống GIS/CRM | Exclusive Gateway | Kiểm tra kết quả cập nhật dữ liệu hạ tầng trên hệ thống. | **Có:** hoàn tất mở rộng hạ tầng. **Không:** xử lý lỗi dữ liệu. |
| 25 | Xử lý lỗi dữ liệu | Hệ thống GIS/CRM | Service Task | Xử lý lỗi phát sinh trong quá trình ghi nhận hoặc cập nhật dữ liệu hạ tầng. | Nếu vẫn không thể hoàn tất, chuyển đến End Event cập nhật thất bại. |
| 26 | Hoàn tất mở rộng hạ tầng | Hệ thống GIS/CRM | End Event | Quy trình kết thúc thành công khi công trình đạt nghiệm thu và dữ liệu được cập nhật thành công. | Kết thúc quy trình. |
| 27 | Kết thúc - Không cần mở rộng hạ tầng | Bộ phận Kỹ thuật hạ tầng (INF) | End Event | Hạ tầng hiện hữu vẫn đáp ứng nhu cầu nên không cần thực hiện đầu tư mở rộng. | Kết thúc quy trình. |
| 28 | Kết thúc - Không được phê duyệt đầu tư | Kế hoạch & Đầu tư | End Event | Phương án không được phê duyệt nên không tiếp tục triển khai. | Kết thúc quy trình. |
| 29 | Kết thúc - Không đạt nghiệm thu | Đội thi công/Kỹ thuật viên | End Event | Công trình hoặc lỗi kỹ thuật không thể xử lý đạt yêu cầu nghiệm thu. | Kết thúc quy trình. |
| 30 | END - Cập nhật thất bại | Hệ thống GIS/CRM | End Event | Dữ liệu hạ tầng không thể cập nhật thành công sau khi xử lý lỗi. | Kết thúc quy trình. |


### Kịch bản thành công

Một process instance được xem là hoàn thành thành công khi nhu cầu mở rộng hạ tầng đã được xác định là cần thiết, phương án đầu tư được phê duyệt, công tác chuẩn bị và thi công được thực hiện đầy đủ, công trình đạt yêu cầu nghiệm thu và dữ liệu hạ tầng được cập nhật thành công trên hệ thống.

Cụ thể, quy trình phải thỏa mãn các điều kiện sau:

- Hạ tầng hiện hữu được đánh giá là không còn đủ khả năng đáp ứng nhu cầu.
- Phương án kỹ thuật và dự toán đầu tư được lập đầy đủ.
- Kế hoạch mở rộng được Bộ phận Kế hoạch & Đầu tư phê duyệt.
- Vật tư, thiết bị và nhân lực phục vụ triển khai đã sẵn sàng.
- Công tác thi công được thực hiện theo phương án đã phê duyệt.
- Kết quả kiểm tra tín hiệu và chất lượng công trình đạt yêu cầu nghiệm thu.
- Thông tin về tuyến cáp, thiết bị, Port và trạng thái khai thác được cập nhật thành công trên GIS/CRM.
- Hạ tầng mới được ghi nhận ở trạng thái sẵn sàng để các bộ phận Sales và Kỹ thuật triển khai tiếp tục khai thác.

Khi toàn bộ các điều kiện trên được đáp ứng, process instance kết thúc tại trạng thái **Hoàn tất mở rộng hạ tầng**.

### Kịch bản thất bại/ngoại lệ

Trong quá trình thực hiện, process instance có thể kết thúc hoặc chuyển sang nhánh xử lý ngoại lệ tại một số điểm kiểm soát.

Trường hợp thứ nhất, sau khi kiểm tra và khảo sát, nếu hạ tầng hiện tại vẫn đáp ứng nhu cầu thì quy trình kết thúc tại trạng thái **Không cần mở rộng hạ tầng**. Đây không phải lỗi kỹ thuật mà là trường hợp yêu cầu mở rộng không còn cần thiết sau khi được đánh giá.

Trường hợp thứ hai, nếu hạ tầng không đáp ứng nhưng phương án kỹ thuật hoặc ngân sách không được Bộ phận Kế hoạch & Đầu tư phê duyệt thì quy trình kết thúc tại trạng thái **Không được phê duyệt đầu tư**.

Trường hợp thứ ba, trong giai đoạn thi công và nghiệm thu, nếu công trình không đạt yêu cầu thì Đội thi công/Kỹ thuật viên phải thực hiện xử lý lỗi kỹ thuật. Nếu lỗi không thể khắc phục, quy trình kết thúc tại trạng thái **Không đạt nghiệm thu**.

Trường hợp thứ tư, công trình đã đạt yêu cầu nghiệm thu nhưng quá trình cập nhật thông tin hạ tầng trên GIS/CRM phát sinh lỗi. Hệ thống thực hiện xử lý lỗi dữ liệu; nếu vẫn không thể cập nhật thành công, quy trình kết thúc tại trạng thái **Cập nhật thất bại**.

Ngoài các trạng thái kết thúc trên, một số vấn đề có thể phát sinh trong quá trình thực hiện như dữ liệu hiện trạng chưa đầy đủ, kết quả khảo sát chưa chính xác, vật tư hoặc nhân lực chưa sẵn sàng, lỗi kỹ thuật trong thi công hoặc sai lệch giữa dữ liệu hệ thống và hiện trạng thực tế. Các trường hợp này cần được xử lý trước khi quy trình có thể tiếp tục sang bước tiếp theo.

### Business Value

Quy trình quản lý và mở rộng hạ tầng tạo ra các nhóm giá trị chính cho hoạt động kinh doanh và vận hành của doanh nghiệp.

**Khả năng phục vụ khách hàng:** Quy trình giúp chuyển các khu vực đang thiếu năng lực hạ tầng, thiếu Port hoặc chưa đủ vùng phủ thành khu vực có khả năng tiếp nhận và triển khai thuê bao mới. Qua đó, doanh nghiệp có thể mở rộng khả năng cung cấp dịch vụ tại những khu vực có nhu cầu thực tế.

**Hỗ trợ hoạt động Sales và triển khai kỹ thuật:** Sau khi quy trình hoàn tất, Sales và đội ngũ kỹ thuật có cơ sở rõ ràng để xác định khu vực đã sẵn sàng triển khai. Điều này giúp hạn chế tình trạng tiếp nhận yêu cầu bán hàng nhưng hạ tầng thực tế chưa đáp ứng.

**Kiểm soát CAPEX:** Việc đầu tư không được thực hiện ngay khi phát sinh nhu cầu mà phải trải qua kiểm tra hiện trạng, khảo sát, lập phương án kỹ thuật, dự toán và phê duyệt. Cơ chế này giúp doanh nghiệp gắn quyết định đầu tư với nhu cầu thực tế và kiểm soát chi phí trước khi triển khai.

**Kiểm soát chất lượng hạ tầng:** Công trình sau thi công phải được kiểm tra tín hiệu và chất lượng trước khi được xem là hoàn thành. Nếu không đạt, quy trình chuyển sang nhánh xử lý lỗi kỹ thuật thay vì đưa tài nguyên chưa đạt chuẩn vào khai thác.

**Đảm bảo độ tin cậy của dữ liệu:** Việc cập nhật GIS/CRM được xem là một đầu ra bắt buộc của quy trình. Hạ tầng chỉ được coi là hoàn tất khi thông tin tuyến cáp, thiết bị, Port và trạng thái khai thác đã được ghi nhận thành công trên hệ thống. Điều này giúp giảm chênh lệch giữa hạ tầng vật lý thực tế và dữ liệu được sử dụng cho bán hàng, điều phối và triển khai kỹ thuật.

#### 3.3.1.4 Mô hình hóa quy trình

img
Hình...

###### Bảng 3. : Danh sách Gateway và logic kiểm soát

| Gateway | Loại Gateway | Điểm kiểm soát | Logic kiểm soát | Nhánh/Kết quả |
|---|---|---|---|---|
| **GW1 – Hạ tầng hiện tại đáp ứng?** | Exclusive Gateway (XOR) | Sau bước đánh giá khả năng đáp ứng hạ tầng | Kiểm tra hạ tầng hiện hữu có đủ tài nguyên mạng, Port và khả năng phục vụ nhu cầu phát sinh hay không. | **Có:** kết thúc quy trình tại “Không cần mở rộng hạ tầng”. **Không:** tiếp tục lập phương án kỹ thuật và dự toán đầu tư. |
| **GW2 – Kế hoạch được phê duyệt?** | Exclusive Gateway (XOR) | Sau bước thẩm định kế hoạch mở rộng | Kiểm soát quyết định đầu tư dựa trên tính cần thiết, tính khả thi của phương án và ngân sách dự kiến. | **Có:** chuyển sang chuẩn bị vật tư và nguồn lực. **Không:** kết thúc tại “Không được phê duyệt đầu tư”. |
| **GW3 – Phân tách chuẩn bị triển khai** | Parallel Gateway (AND – Split) | Sau bước chuẩn bị vật tư và nguồn lực | Tách một luồng thực hiện thành hai luồng song song nhằm rút ngắn thời gian chuẩn bị trước thi công. Cả hai nhánh đều được kích hoạt đồng thời. | **Nhánh 1:** Chuẩn bị thiết bị. **Nhánh 2:** Phân công nhân lực. |
| **GW4 – Hoàn tất chuẩn bị triển khai** | Parallel Gateway (AND – Join) | Sau hai hoạt động chuẩn bị song song | Đồng bộ hai luồng được tạo từ GW3. Quy trình chỉ được tiếp tục khi cả hai hoạt động chuẩn bị thiết bị và phân công nhân lực đều hoàn thành. | Khi **cả hai nhánh hoàn tất**, quy trình chuyển sang thi công mở rộng hạ tầng. |
| **GW5 – Nghiệm thu đạt?** | Exclusive Gateway (XOR) | Sau bước kiểm tra tín hiệu và chất lượng công trình | Kiểm soát chất lượng công trình sau thi công, xác định kết quả có đáp ứng yêu cầu kỹ thuật và điều kiện nghiệm thu hay không. | **Đạt:** chuyển sang cập nhật dữ liệu hạ tầng trên GIS/CRM. **Không:** chuyển sang xử lý lỗi kỹ thuật. |
| **GW6 – Cập nhật dữ liệu thành công?** | Exclusive Gateway (XOR) | Sau bước cập nhật dữ liệu hạ tầng trên GIS/CRM | Kiểm tra dữ liệu về tuyến cáp, thiết bị, Port và trạng thái khai thác đã được ghi nhận thành công trên hệ thống hay chưa. | **Có:** kết thúc thành công tại “Hoàn tất mở rộng hạ tầng”. **Không:** chuyển sang xử lý lỗi dữ liệu, sau đó kết thúc tại “Cập nhật thất bại” nếu không thể hoàn tất trong instance hiện tại. |
| **GW7 – Tình trạng khắc phục lỗi?** | Exclusive Gateway (XOR) | Sau bước xử lý lỗi kỹ thuật | Đánh giá khả năng khắc phục các lỗi được phát hiện trong quá trình kiểm tra và nghiệm thu công trình. | **Đã khắc phục:** chuyển sang xác nhận kết quả khắc phục. **Không thể khắc phục:** kết thúc tại “Không đạt nghiệm thu”. |

### 3.3.2. Phân tích quy trình

#### 3.3.2.1. Bộ câu hỏi phỏng vấn thu thập dữ liệu quy trình

####### Bảng 3. : Bộ câu hỏi phỏng vấn định tính có cấu trúc (Structured Qualitative Interview)

| STT | Đối tượng phỏng vấn | Câu hỏi khảo sát | Các lựa chọn trả lời | Mục đích thu thập dữ liệu |
|---|---|---|---|---|
| 1 | Nhân viên vận hành quy trình | Anh/chị đánh giá mức độ rõ ràng của các bước trong quy trình hiện tại như thế nào? | ☐ Rất rõ ràng  ☐ Khá rõ ràng  ☐ Bình thường  ☐ Khó hiểu  ☐ Không có hướng dẫn cụ thể | Đánh giá mức độ chuẩn hóa của quy trình |
| 2 | Nhân viên thực hiện | Trong quá trình thực hiện quy trình, anh/chị thường gặp vấn đề ở nhóm nguyên nhân nào? | ☐ Thiếu thông tin đầu vào  ☐ Quy trình phức tạp  ☐ Hệ thống lỗi/chậm  ☐ Phối hợp giữa bộ phận chưa tốt  ☐ Khác: ______ | Xác định nhóm nguyên nhân gây ảnh hưởng đến quy trình |
| 3 | Bộ phận phối hợp | Việc bàn giao thông tin giữa các bộ phận trong quy trình hiện tại được thực hiện như thế nào? | ☐ Rất hiệu quả  ☐ Hiệu quả  ☐ Bình thường  ☐ Chưa hiệu quả  ☐ Thường xuyên xảy ra sai sót | Đánh giá khả năng phối hợp giữa các tác nhân |
| 4 | Trưởng bộ phận | Theo anh/chị, mức độ cần thiết của việc cải tiến quy trình hiện tại là như thế nào? | ☐ Không cần thiết  ☐ Ít cần thiết  ☐ Cần thiết  ☐ Rất cần thiết | Đánh giá nhu cầu tái thiết kế quy trình |
| 5 | Người trực tiếp xử lý | Trong quá trình vận hành, các trường hợp ngoại lệ thường xảy ra với tần suất như thế nào? | ☐ Chưa từng xảy ra  ☐ Hiếm khi  ☐ Thỉnh thoảng  ☐ Thường xuyên  ☐ Rất thường xuyên | Xác định các trường hợp ngoại lệ cần bổ sung vào BPMN |


## Bảng 3.. Bộ câu hỏi phỏng vấn định tính không có cấu trúc

| STT | Đối tượng phỏng vấn | Câu hỏi | Mục đích thu thập dữ liệu |
|---|---|---|---|
| 1 | Nhân viên vận hành | Anh/chị có thể chia sẻ những khó khăn thường gặp khi thực hiện quy trình này không? | Khám phá các vấn đề phát sinh trong thực tế vận hành |
| 2 | Nhân viên có kinh nghiệm | Theo kinh nghiệm của anh/chị, điều gì khiến quy trình hiện tại chưa đạt hiệu quả tối ưu? | Thu thập nhận định chuyên môn từ người vận hành |
| 3 | Bộ phận liên quan | Anh/chị đánh giá như thế nào về sự phối hợp giữa các bộ phận trong quy trình? | Phân tích sự liên kết giữa các actor |
| 4 | Người quản lý | Nếu được thay đổi một điểm trong quy trình hiện tại, anh/chị sẽ thay đổi điều gì đầu tiên? Vì sao? | Xác định các khu vực ưu tiên cải tiến |
| 5 | Người trực tiếp xử lý | Có trường hợp ngoại lệ nào thường xuyên xảy ra nhưng chưa được thể hiện trong quy trình chuẩn không? | Phát hiện các luồng ngoại lệ cần bổ sung vào BPMN |


## Bảng 3.. Bộ câu hỏi phỏng vấn định lượng có cấu trúc

| STT | Đối tượng phỏng vấn | Câu hỏi khảo sát | Các lựa chọn trả lời | Mục đích thu thập dữ liệu |
|---|---|---|---|---|
| 1 | Nhân viên vận hành quy trình | Thời gian trung bình để hoàn thành toàn bộ quy trình là bao lâu? | ☐ Dưới 30 phút ☐ 30 phút - 1 giờ ☐ 1 - 3 giờ ☐ 3 - 8 giờ ☐ Trên 8 giờ | Xác định Cycle Time của toàn bộ quy trình |
| 2 | Nhân viên thực hiện từng bước | Thời gian xử lý trung bình của một bước trong quy trình là bao nhiêu? | ☐ Dưới 5 phút ☐ 5 - 15 phút ☐ 15 - 30 phút ☐ 30 phút - 1 giờ ☐ Trên 1 giờ | Xác định Processing Time của từng hoạt động |
| 3 | Quản lý bộ phận | Trong một tháng, quy trình phát sinh lỗi hoặc phải thực hiện lại bao nhiêu lần? | ☐ 0 lần ☐ 1 - 5 lần ☐ 6 - 10 lần ☐ 11 - 20 lần ☐ Trên 20 lần | Xác định tần suất lỗi và tỷ lệ Rework |
| 4 | Bộ phận vận hành | Trung bình số lượng yêu cầu được xử lý trong một ngày là bao nhiêu? | ☐ Dưới 10 yêu cầu ☐ 10 - 50 yêu cầu ☐ 51 - 100 yêu cầu ☐ 101 - 500 yêu cầu ☐ Trên 500 yêu cầu | Đo lường Throughput của quy trình |
| 5 | Quản lý/Bộ phận tài chính | Chi phí trung bình để xử lý một trường hợp trong quy trình là khoảng bao nhiêu? | ☐ Dưới 50.000 VNĐ ☐ 50.000 - 200.000 VNĐ ☐ 200.000 - 500.000 VNĐ ☐ 500.000 - 1.000.000 VNĐ ☐ Trên 1.000.000 VNĐ | Ước lượng Process Cost |


## Bảng 3.. Bộ câu hỏi phỏng vấn định lượng không có cấu trúc

| STT | Đối tượng phỏng vấn | Câu hỏi mở | Mục đích thu thập dữ liệu |
|---|---|---|---|
| 1 | Nhân viên vận hành | Anh/chị có thể cho biết thời gian thực tế để hoàn thành toàn bộ quy trình trong một trường hợp bình thường là bao lâu không? | Thu thập Cycle Time thực tế của quy trình |
| 2 | Nhân viên thực hiện | Anh/chị có thể cung cấp thời gian xử lý trung bình của từng bước trong quy trình không? | Xác định Processing Time của từng Activity |
| 3 | Quản lý bộ phận | Trong thời gian gần đây, trung bình có bao nhiêu trường hợp phát sinh lỗi hoặc cần xử lý lại? | Đánh giá Error Rate và Rework Rate |
| 4 | Bộ phận vận hành | Trung bình mỗi ngày/tháng bộ phận xử lý được bao nhiêu yêu cầu liên quan đến quy trình này? | Xác định lưu lượng xử lý (Throughput) |
| 5 | Người quản lý | Anh/chị có thể ước lượng tổng chi phí nhân sự, thời gian và nguồn lực cần thiết để thực hiện một lần quy trình không? | Xác định chi phí vận hành quy trình (Process Cost) |

#### 3.3.2.2 Phân tích định tính

##### 3.3.2.2.1. Phân tích giá trị gia tăng (Value Added Analysis)

| Nhóm | Hoạt động trong quy trình | Phân loại | Mô tả giá trị tạo ra | Hướng xử lý |
|---|---|---|---|---|
| VA | Thi công mở rộng hạ tầng mạng | Hoạt động tạo giá trị | Tạo thêm khả năng cung cấp dịch vụ Internet đến khu vực mới, giúp tăng khả năng phục vụ khách hàng | Duy trì và tối ưu thời gian triển khai |
| VA | Cập nhật trạng thái hạ tầng sau triển khai | Hoạt động tạo giá trị | Đảm bảo dữ liệu hạ tầng chính xác, hỗ trợ Sales và vận hành khai thác dịch vụ | Chuẩn hóa dữ liệu và cập nhật tự động |
| BVA | Khảo sát nhu cầu mở rộng khu vực | Hoạt động tăng giá trị kinh doanh | Giúp doanh nghiệp xác định khu vực có nhu cầu cao để đưa ra quyết định đầu tư phù hợp | Tích hợp dữ liệu thị trường để hỗ trợ phân tích |
| BVA | Đánh giá độ phủ cáp quang và số lượng Port hiện tại | Hoạt động tăng giá trị kinh doanh | Giúp kiểm soát khả năng đáp ứng của hạ tầng trước khi triển khai mở rộng | Tự động hóa việc kiểm tra dữ liệu GIS |
| BVA | Lập và phê duyệt dự án đầu tư mở rộng | Hoạt động tăng giá trị kinh doanh | Đảm bảo nguồn lực và ngân sách được kiểm soát trước khi triển khai | Rút ngắn thời gian phê duyệt |
| NVA | Chờ phê duyệt hồ sơ mở rộng hạ tầng | Hoạt động không tạo giá trị | Không làm thay đổi trạng thái hạ tầng nhưng làm kéo dài thời gian hoàn thành quy trình | Áp dụng phê duyệt điện tử và SLA rõ ràng |
| NVA | Nhập lại dữ liệu hạ tầng thủ công từ nhiều nguồn | Hoạt động không tạo giá trị | Tăng nguy cơ sai lệch dữ liệu và tiêu tốn thời gian nhân sự | Đồng bộ dữ liệu tự động giữa các hệ thống |

# 3.3.2.2.2. Phân tích sự lãng phí (Waste Analysis)

| Loại lãng phí | Hoạt động gây lãng phí | Mô tả vấn đề | Hướng khắc phục |
|---|---|---|---|
| Move | Kỹ thuật viên phải di chuyển nhiều lần để khảo sát hoặc kiểm tra hiện trạng hạ tầng | Thông tin khu vực chưa đầy đủ khiến nhân viên phải quay lại khảo sát nhiều lần | Sử dụng dữ liệu GIS, bản đồ hạ tầng số để giảm khảo sát lặp lại |
| Move | Di chuyển hồ sơ giữa các phòng ban để xin xác nhận | Quy trình phụ thuộc nhiều vào trao đổi thủ công | Sử dụng hệ thống quản lý quy trình điện tử BPMS |
| Hold | Chờ Ban Giám đốc phê duyệt kế hoạch đầu tư | Hồ sơ có thể bị tồn đọng trước khi chuyển sang bước triển khai | Thiết lập SLA phê duyệt và workflow tự động |
| Hold | Chờ cập nhật dữ liệu giữa bộ phận kỹ thuật và vận hành | Dữ liệu chưa được đồng bộ theo thời gian thực | Tích hợp hệ thống GIS và quản lý tài sản mạng |
| Overdo | Kiểm tra lại nhiều lần thông tin hạ tầng đã có trên hệ thống | Trùng lặp thao tác kiểm tra dữ liệu | Chuẩn hóa nguồn dữ liệu dùng chung |
| Overdo | Lập nhiều báo cáo thủ công cho cùng một mục đích | Tiêu tốn thời gian tổng hợp và dễ sai lệch | Xây dựng dashboard theo dõi tự động |

# 3.3.2.2.3. Phân tích các bên liên quan (Stakeholder Analysis)

hình xuong ca....


| Nhóm nguyên nhân | Nguyên nhân cụ thể |
|---|---|
| Con người (People) | Nhân viên giữa các bộ phận chưa thống nhất cách cập nhật thông tin; phụ thuộc nhiều vào kinh nghiệm cá nhân |
| Quy trình (Process) | Quy trình phê duyệt nhiều bước; chưa có SLA rõ ràng cho từng giai đoạn |
| Công nghệ (Technology) | Dữ liệu GIS, hệ thống quản lý hạ tầng và hệ thống vận hành chưa đồng bộ hoàn toàn |
| Dữ liệu (Data) | Thông tin về Port, tuyến cáp và trạng thái hạ tầng có thể chưa được cập nhật kịp thời |
| Quản lý (Management) | Việc ưu tiên đầu tư mở rộng chưa dựa hoàn toàn trên dữ liệu phân tích nhu cầu |

### Nguyên nhân gốc rễ:

Nguyên nhân chính khiến quy trình chưa đạt hiệu quả tối ưu là sự phụ thuộc vào thao tác thủ công và sự phối hợp giữa nhiều bộ phận. Việc thiếu dữ liệu đồng bộ theo thời gian thực làm tăng thời gian kiểm tra, phê duyệt và triển khai.

### Đề xuất cải thiện:

| Vấn đề | Giải pháp đề xuất |
|---|---|
| Chậm phê duyệt dự án | Xây dựng workflow phê duyệt điện tử trên BPMS |
| Dữ liệu hạ tầng chưa đồng bộ | Tích hợp GIS với hệ thống quản lý tài sản mạng |
| Khảo sát lặp lại nhiều lần | Sử dụng dữ liệu hiện trạng hạ tầng số để hỗ trợ quyết định |
| Khó theo dõi tiến độ | Xây dựng dashboard giám sát trạng thái mở rộng hạ tầng |

## 3.3.2.3. Phân tích định lượng

Phân tích định lượng được thực hiện nhằm đánh giá hiệu quả vận hành của quy trình **quản lý và mở rộng hạ tầng** thông qua các chỉ số đo lường cụ thể bao gồm thời gian xử lý, chất lượng quyết định, hiệu suất quy trình và chi phí nguồn lực.

Các số liệu trong phần phân tích được xây dựng theo hướng giả định mô phỏng dựa trên đặc điểm vận hành của doanh nghiệp viễn thông, nhằm phục vụ mục đích phân tích mô hình BPMN, nhận diện điểm nghẽn và đề xuất cải tiến quy trình.

---

# 3.3.2.3.1. Phạm vi và giả định

Phân tích được thực hiện trên một **instance mở rộng hạ tầng mạng cho một khu vực mới**. Quy trình bắt đầu từ bước khảo sát nhu cầu mở rộng, đánh giá khả năng đáp ứng hạ tầng hiện tại, lập kế hoạch đầu tư, phê duyệt, triển khai thi công và kết thúc khi cập nhật trạng thái hạ tầng trên hệ thống GIS.

Các giả định trong mô hình:

| Nội dung | Giả định |
|---|---|
| Phạm vi phân tích | Một dự án mở rộng hạ tầng mạng tại một khu vực mới |
| Quy mô | Mở rộng tuyến cáp quang và bổ sung khả năng cung cấp dịch vụ |
| Dữ liệu thời gian | Số liệu giả định dựa trên đặc điểm vận hành doanh nghiệp viễn thông |
| Vòng lặp xử lý | Không có vòng lặp trong cùng một instance |
| Xử lý lại | Không tính chi phí và thời gian rework trong cùng instance |
| Kết quả quy trình | Instance hoàn thành khi hạ tầng được nghiệm thu và cập nhật GIS |

---

# 3.3.2.3.2. Phân tích thời gian (Time Analysis)

Thời gian của quy trình được phân tích dựa trên hai thành phần:

- **Processing Time (PT):** thời gian thực hiện công việc thực tế.
- **Waiting Time (WT):** thời gian chờ giữa các bước xử lý.
- **Cycle Time (CT):** tổng thời gian từ khi bắt đầu đến khi kết thúc hoạt động.

| STT | Hoạt động trong quy trình | Processing Time (PT) | Waiting Time (WT) | Cycle Time (CT) |
|---|---|---:|---:|---:|
| 1 | Khảo sát nhu cầu mở rộng khu vực | 3 ngày | 1 ngày | 4 ngày |
| 2 | Đánh giá độ phủ cáp quang và số lượng Port hiện tại | 2 ngày | 1 ngày | 3 ngày |
| 3 | Lập dự án đầu tư mở rộng hạ tầng | 5 ngày | 3 ngày | 8 ngày |
| 4 | Phê duyệt kế hoạch triển khai | 2 ngày | 7 ngày | 9 ngày |
| 5 | Chuẩn bị nguồn lực và vật tư | 3 ngày | 2 ngày | 5 ngày |
| 6 | Thi công mở rộng hạ tầng mạng | 10 ngày | 2 ngày | 12 ngày |
| 7 | Kiểm tra nghiệm thu và cập nhật GIS | 3 ngày | 1 ngày | 4 ngày |
| **Tổng cộng** | | **28 ngày** | **17 ngày** | **45 ngày** |

## Tính toán thời gian

Tổng Cycle Time:

\[
CT = PT + WT
\]

\[
CT = 28 + 17 = 45 \text{ ngày}
\]

Tỷ lệ thời gian chờ:

\[
Waiting\ Ratio = \frac{WT}{CT} \times 100\%
\]

\[
Waiting\ Ratio = \frac{17}{45} \times 100\% = 37,8\%
\]

### Nhận xét:

Kết quả cho thấy quy trình mất tổng cộng **45 ngày** để hoàn thành một instance mở rộng hạ tầng. Trong đó, thời gian chờ chiếm khoảng **37,8%**, tập trung chủ yếu tại bước phê duyệt kế hoạch triển khai và quá trình phối hợp giữa các bộ phận.

Điểm gây ảnh hưởng lớn nhất là bước:

**Phê duyệt kế hoạch triển khai**

- Processing Time: 2 ngày
- Waiting Time: 7 ngày
- Cycle Time: 9 ngày

Đây là vị trí có khả năng gây chậm tiến độ cao nhất trong toàn bộ quy trình.

---

# 3.3.2.3.3. Phân tích chất lượng (Quality Analysis)

Chất lượng quy trình được đánh giá thông qua khả năng hoàn thành các điểm kiểm soát quan trọng mà không phát sinh lỗi hoặc phải xử lý bổ sung.

Các Gateway kiểm soát chính trong quy trình:

| Gateway | Điều kiện kiểm tra | Xác suất đạt |
|---|---|---:|
| GW1 | Khu vực có nhu cầu mở rộng phù hợp | 90% |
| GW2 | Hạ tầng hiện tại đủ điều kiện mở rộng | 85% |
| GW3 | Dự án đầu tư được phê duyệt | 80% |
| GW4 | Hạ tầng thi công đạt yêu cầu nghiệm thu | 90% |

Xác suất hoàn thành toàn bộ quy trình:

\[
FPY = 0,9 \times 0,85 \times 0,8 \times 0,9
\]

\[
FPY = 55,1\%
\]

### Nhận xét:

Theo mô hình giả định, khoảng **55,1% instance** có thể hoàn thành toàn bộ quy trình ngay từ lần đầu tiên mà không gặp vấn đề tại các điểm kiểm soát.

Các nguyên nhân chính làm giảm tỷ lệ hoàn thành:

| Nguyên nhân | Ảnh hưởng |
|---|---|
| Dữ liệu hiện trạng hạ tầng chưa cập nhật | Có thể sai lệch khi đánh giá Port/cáp quang |
| Kế hoạch đầu tư chưa được phê duyệt kịp thời | Làm kéo dài thời gian triển khai |
| Sai sót trong quá trình thi công | Phát sinh kiểm tra và xử lý bổ sung |
| Chậm cập nhật dữ liệu sau nghiệm thu | Ảnh hưởng khả năng khai thác dịch vụ |

---

# 3.3.2.3.4. Phân tích Processing Time và Process Efficiency

Processing Time được sử dụng để đánh giá tỷ lệ thời gian thực sự tạo ra giá trị trong tổng thời gian hoàn thành quy trình.

| Bước | Hoạt động | Cycle Time (CT) | Tỷ lệ xử lý | Processing Time (PT) |
|---|---|---:|---:|---:|
| 1 | Khảo sát nhu cầu mở rộng khu vực | 4 ngày | 75% | 3 ngày |
| 2 | Đánh giá độ phủ cáp quang và Port | 3 ngày | 67% | 2 ngày |
| 3 | Lập dự án đầu tư mở rộng | 8 ngày | 62,5% | 5 ngày |
| 4 | Phê duyệt kế hoạch triển khai | 9 ngày | 22% | 2 ngày |
| 5 | Chuẩn bị nguồn lực và vật tư | 5 ngày | 60% | 3 ngày |
| 6 | Thi công mở rộng hạ tầng | 12 ngày | 83% | 10 ngày |
| 7 | Kiểm tra nghiệm thu và cập nhật GIS | 4 ngày | 75% | 3 ngày |
| **Tổng cộng** | | **45 ngày** | | **28 ngày** |

Hiệu suất quy trình:

\[
Process\ Efficiency = \frac{PT}{CT}\times100\%
\]

\[
Process\ Efficiency = \frac{28}{45}\times100\%
\]

\[
Process\ Efficiency = 62,2\%
\]

### Nhận xét:

Hiệu suất xử lý của quy trình đạt khoảng **62,2%**. Phần thời gian còn lại chủ yếu đến từ hoạt động chờ phê duyệt, chờ phối hợp và đồng bộ thông tin giữa các bộ phận.

---

# 3.3.2.3.5. Phân tích chi phí (Cost Analysis)

Chi phí quy trình được tính dựa trên công thức:

\[
Cost = \sum(Time_i \times Cost/day_i)
\]

Chi phí nhân sự giả định:

| Nhóm nguồn lực | Chi phí/ngày |
|---|---:|
| Kỹ thuật & Hạ tầng | 700.000 VNĐ |
| Đội thi công | 1.000.000 VNĐ |
| Quản lý dự án | 1.500.000 VNĐ |
| Ban Giám đốc | 2.000.000 VNĐ |

Chi phí theo từng hoạt động:

| Hoạt động | Nguồn lực | Thời gian | Chi phí |
|---|---|---:|---:|
| Khảo sát và đánh giá hiện trạng | Kỹ thuật & Hạ tầng | 5 ngày | 3.500.000 VNĐ |
| Lập dự án đầu tư | Kỹ thuật + Quản lý | 5 ngày | 7.500.000 VNĐ |
| Phê duyệt dự án | Ban Giám đốc | 2 ngày | 4.000.000 VNĐ |
| Chuẩn bị vật tư và nguồn lực | Kỹ thuật & Hạ tầng | 3 ngày | 2.100.000 VNĐ |
| Thi công mở rộng hạ tầng | Đội thi công | 10 ngày | 10.000.000 VNĐ |
| Nghiệm thu và cập nhật GIS | Kỹ thuật & Vận hành | 3 ngày | 2.100.000 VNĐ |
| **Tổng cộng** | | | **29.200.000 VNĐ** |

### Nhận xét:

Chi phí lớn nhất tập trung ở giai đoạn thi công mở rộng hạ tầng do sử dụng nhiều nguồn lực trực tiếp.

Tuy nhiên, các chi phí gián tiếp phát sinh do thời gian chờ phê duyệt và sai lệch dữ liệu cũng cần được kiểm soát nhằm giảm tổng chi phí vận hành.

---

# 3.3.2.3.6. Tổng hợp kết quả phân tích định lượng

| Chỉ tiêu | Kết quả | Ý nghĩa |
|---|---:|---|
| Cycle Time | 45 ngày | Thời gian hoàn thành một instance |
| Processing Time | 28 ngày | Thời gian thực sự xử lý công việc |
| Waiting Time | 17 ngày | Thời gian chờ trong quy trình |
| Waiting Ratio | 37,8% | Tỷ lệ thời gian không tạo giá trị |
| Process Efficiency | 62,2% | Hiệu suất sử dụng thời gian |
| FPY | 55,1% | Khả năng hoàn thành ngay lần đầu |
| Chi phí cơ bản | 29,2 triệu VNĐ | Chi phí nguồn lực trực tiếp |

---

# 3.3.2.3.7. Nhận xét kết quả định lượng

Qua phân tích định lượng, quy trình quản lý và mở rộng hạ tầng có Cycle Time khoảng **45 ngày**, trong đó thời gian chờ chiếm tỷ lệ lớn do các hoạt động phê duyệt và phối hợp giữa nhiều bộ phận.

Hiệu suất xử lý của quy trình đạt khoảng **62,2%**, cho thấy vẫn còn khoảng thời gian chưa tạo giá trị do chờ đợi và xử lý thủ công.

Bên cạnh đó, tỷ lệ hoàn thành ngay từ lần đầu (FPY) đạt **55,1%**, cho thấy các điểm kiểm soát như đánh giá hiện trạng, phê duyệt đầu tư và nghiệm thu cần được cải thiện.

Các hướng cải tiến trọng tâm bao gồm:

| Vấn đề | Giải pháp |
|---|---|
| Thời gian phê duyệt dài | Xây dựng workflow phê duyệt điện tử trên BPMS |
| Dữ liệu hạ tầng chưa đồng bộ | Tích hợp GIS với hệ thống quản lý tài sản mạng |
| Sai lệch khi khảo sát | Chuẩn hóa dữ liệu hiện trạng trước triển khai |
| Khó theo dõi tiến độ | Xây dựng dashboard quản lý trạng thái dự án |


## 3.3.2.4. Kết luận phân tích quy trình quản lý và mở rộng hạ tầng

Qua quá trình phân tích định tính và định lượng, quy trình quản lý và mở rộng hạ tầng của FPT Telecom đã được đánh giá trên các khía cạnh về giá trị tạo ra, sự lãng phí, thời gian xử lý, hiệu suất vận hành và chi phí nguồn lực.

Kết quả phân tích định tính cho thấy quy trình hiện tại đã đảm bảo được các hoạt động quan trọng nhằm tạo giá trị cho doanh nghiệp, trong đó nổi bật là hoạt động **thi công mở rộng hạ tầng mạng** và **cập nhật trạng thái hạ tầng sau triển khai**. Các hoạt động này góp phần trực tiếp nâng cao khả năng cung cấp dịch vụ và đảm bảo dữ liệu hạ tầng được quản lý chính xác.

Tuy nhiên, quy trình vẫn tồn tại một số hoạt động chưa tạo ra giá trị trực tiếp như thời gian chờ phê duyệt hồ sơ, nhập lại dữ liệu thủ công từ nhiều nguồn và sự phụ thuộc vào việc trao đổi thông tin giữa các bộ phận. Các yếu tố này làm tăng thời gian hoàn thành quy trình và ảnh hưởng đến khả năng triển khai hạ tầng trong thực tế.

Phân tích sự lãng phí cho thấy các vấn đề chính tập trung vào ba nhóm gồm **Move**, **Hold** và **Overdo**. Trong đó, nhóm lãng phí Hold có ảnh hưởng lớn nhất do thời gian chờ phê duyệt kế hoạch triển khai và chờ đồng bộ dữ liệu giữa các bộ phận chiếm tỷ trọng đáng kể trong toàn bộ chu trình xử lý.

Đối với phân tích định lượng, quy trình có tổng thời gian hoàn thành (**Cycle Time**) là **45 ngày**, bao gồm **28 ngày Processing Time** và **17 ngày Waiting Time**. Tỷ lệ thời gian chờ chiếm khoảng **37,8%**, cho thấy quy trình vẫn còn nhiều khoảng thời gian chưa trực tiếp tạo ra giá trị. Điểm nghẽn lớn nhất tập trung tại bước **phê duyệt kế hoạch triển khai** với thời gian xử lý thực tế 2 ngày nhưng thời gian chờ lên đến 7 ngày.

Hiệu suất quy trình (**Process Efficiency**) đạt khoảng **62,2%**, phản ánh mức độ sử dụng thời gian hiện tại vẫn còn khả năng cải thiện thông qua việc giảm các hoạt động chờ và tối ưu hóa sự phối hợp giữa các bộ phận. Về chi phí, nguồn lực tập trung chủ yếu tại giai đoạn thi công mở rộng hạ tầng do đây là hoạt động yêu cầu nhiều nhân sự và công việc triển khai thực tế.

Từ kết quả phân tích, các hướng cải tiến trọng tâm của quy trình bao gồm số hóa quy trình phê duyệt thông qua hệ thống BPMS, tích hợp dữ liệu GIS với hệ thống quản lý hạ tầng nhằm giảm sai lệch thông tin, chuẩn hóa dữ liệu khảo sát để hạn chế các hoạt động kiểm tra lặp lại, đồng thời xây dựng cơ chế theo dõi tiến độ tập trung để nâng cao khả năng kiểm soát toàn bộ quá trình triển khai.

Nhìn chung, quy trình quản lý và mở rộng hạ tầng đã có đầy đủ các bước cần thiết để đảm bảo hoạt động mở rộng mạng lưới, tuy nhiên vẫn tồn tại các điểm nghẽn liên quan đến thời gian chờ, dữ liệu chưa đồng bộ và sự phối hợp giữa các tác nhân. Việc áp dụng các giải pháp tự động hóa và quản lý dữ liệu tập trung sẽ giúp quy trình giảm thời gian xử lý, nâng cao hiệu suất vận hành và hỗ trợ khả năng mở rộng dịch vụ trong tương lai.
