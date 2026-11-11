# Viết báo cáo cụ thể bằng tiếng Việt

Tài liệu này hướng dẫn cách viết bốn loại báo cáo trong nhóm phần mềm: báo cáo tiến độ, báo cáo sự cố, báo cáo kết quả kiểm thử hoặc đo hiệu năng, và báo cáo sau khi làm xong một việc. Phần câu chữ và thuật ngữ theo [`style-docs.md`](style-docs.md). Tài liệu này chỉ nói thêm về một việc: làm sao để báo cáo cụ thể.

Một báo cáo cụ thể trả lời được ba câu hỏi của người đọc: chuyện gì đã xảy ra, dựa vào đâu mà biết, và tôi cần làm gì.

## Sáu nguyên tắc

1. **Kết luận lên đầu.** Câu đầu tiên trả lời điều người đọc hỏi. Quá trình và hoàn cảnh để sau. Các bài hướng dẫn tiếng Việt và các chuẩn viết quốc tế đều thống nhất ở điểm này.
2. **Con số thay cho tính từ.** Viết "xong 9/12 task" thay cho "gần xong", viết "p95 giảm từ 820 ms xuống 310 ms" thay cho "nhanh hơn đáng kể". Con số cần đơn vị và cần một mốc để so sánh.
3. **Rõ người, rõ việc, rõ thời hạn.** Mỗi việc cần làm có một người phụ trách và một ngày cụ thể. Chỉ đạo "5 rõ" trong cơ quan nhà nước cũng nói đúng ý này: rõ người, rõ việc, rõ trách nhiệm, rõ thời gian, rõ kết quả.
4. **Tách điều đã thấy khỏi điều mình đoán.** "Crash 3 lần trong 50 lần chạy" là điều đã thấy. "Có thể do race condition ở cache" là suy đoán. Viết hai ý ở hai câu khác nhau, và ghi rõ câu nào là suy đoán.
5. **Nói rõ đã kiểm chứng đến đâu.** Có ba mức khác nhau: đã xong và đã kiểm chứng, đã xong nhưng chưa kiểm chứng, và chưa xong. Khi báo "đã sửa xong", hãy viết luôn đã kiểm tra bằng cách nào. Chưa tái hiện được lỗi thì chưa nên kết luận là đã sửa xong.
6. **Tin xấu cũng phải báo.** Việc trễ, bước bị bỏ qua và lần chạy thất bại đều thuộc về báo cáo. Vấn đề không được báo sẽ lớn dần cho tới khi không còn sửa kịp.

## Tự kiểm tra từng câu

Sau khi viết xong, đọc lại từng câu và hỏi:

| Câu hỏi | Nếu chưa đạt |
|---|---|
| Con số có đơn vị và có mốc so sánh chưa? | Thêm giá trị trước đó hoặc mục tiêu: "từ 840 ms xuống 400 ms" |
| Việc cần làm có tên người phụ trách chưa? | Ghi một người hoặc một nhóm |
| Thời gian có phải ngày giờ cụ thể không? | Thay "sắp tới", "sớm" bằng "trước 17h ngày 12/11" |
| Câu có nói ai hoặc cái gì đã làm không? | Thêm chủ ngữ: "job deploy đã đổi config" |
| Người đọc có biết khi nào việc này được coi là xong không? | Viết trạng thái kết thúc: "alert khi tỷ lệ lỗi trên 1%" |
| Nếu là lời báo "đã xong", đã nói kiểm chứng bằng cách nào chưa? | Thêm "42/42 unit test pass", hoặc ghi "chưa kiểm chứng" |
| Đây là điều đã thấy hay điều suy đoán? | Thêm "Đã quan sát:" hoặc "Suy đoán, chưa xác nhận:" |
| Câu có nói phần nào chưa kiểm tra không? | Thêm "Chưa thử trên thiết bị thật" |
| Người đọc có biết họ cần quyết định hay làm gì không? | Thêm một câu nêu việc cần họ làm, kèm hạn |

## Viết chung chung và viết cụ thể

| Chung chung | Cụ thể |
|---|---|
| Gần xong. | Xong 9/12 task. 3 task còn lại dự kiến xong ngày 14/11. |
| Hình như trễ task. | Task xuất hóa đơn trễ 2 ngày so với kế hoạch. Hạn mới là 15/11. |
| Chưa hoàn thành. | Chưa hoàn thành, còn 3/8 endpoint. Nguyên nhân: chờ spec từ đối tác. Ảnh hưởng: lùi ngày test 2 ngày. |
| Đã xử lý nhiều yêu cầu. | Đã xử lý 35 yêu cầu trong tuần. |
| Cần hỗ trợ thêm. | Cần team hạ tầng cấp quyền đọc DB production trước 17h ngày 12/11. |
| Hệ thống gặp sự cố một thời gian. | Checkout lỗi từ 20h05 đến 20h31 ngày 14/11 (giờ Việt Nam). |
| Ảnh hưởng một số người dùng. | 1.240 người dùng gặp lỗi 500, 86 giao dịch thất bại. |
| Sẽ sớm khắc phục. | Dự kiến mở lại giao dịch vào thứ Hai, ngày 18/11. |
| Kết quả test tốt. | 8/10 test case Pass. 2 Fail: 1 Major (thanh toán trả lỗi 500), 1 Minor (giao diện). |
| Còn một số lỗi. | Còn bug #125, mức Major: thanh toán trả lỗi 500. |
| Do lỗi cấu hình. | Service chưa cấu hình graceful shutdown, nên request đang xử lý bị hủy khi deploy. |
| Hiệu năng tăng gấp đôi. | Thông lượng tăng từ 350 lên 700 req/s, đo trên cùng máy 4 vCPU, 200 kết nối đồng thời, chạy 10 phút. |
| Đã test xong, chạy ổn. | 42/42 unit test pass. Chưa chạy UI test. |
| Sẽ chú ý hơn, kiểm tra kỹ hơn. | Thêm bước kiểm tra tự động: từ chối config có khóa lạ. |
| Đang kiểm tra, có gì báo sau. | Đang kiểm tra. Sẽ cập nhật lúc 20h30. |

## Những từ nên thay bằng số liệu

**Từ chỉ lượng và thời gian mơ hồ.** "Một số", "khá nhiều", "đáng kể", "phần lớn", "gần xong", "sắp tới", "sẽ sớm". Trong văn thường, các từ này rất phổ biến và không có gì sai. Trong báo cáo, người đọc cần con số để quyết định, nên hãy thay bằng số lượng hoặc ngày giờ.

**Lối văn báo cáo hành chính.** "Cơ bản hoàn thành", "về cơ bản", "tích cực triển khai", "kịp thời", "đẩy mạnh", "quyết liệt", "trong thời gian tới". Trong 108 bài viết tay của lập trình viên Việt (xem [`evidence.md`](evidence.md)), mỗi cụm này chỉ xuất hiện ở 0–1 bài. Chúng làm báo cáo kỹ thuật nghe như văn bản hành chính, và không cho người đọc biết thêm điều gì.

**"Chưa" đi kèm từ giảm nhẹ.** "Chưa hoàn thành tốt một số nhiệm vụ", "chưa thực sự ổn định", "chưa được cải thiện đáng kể". Cách nói này làm mờ một kết quả không đạt. Hãy nói thẳng và kèm số: "không đạt mục tiêu 250 ms, p95 hiện là 400 ms".

**Lời khẳng định không kèm cách kiểm chứng.** "Chạy ổn", "hoạt động tốt", "không có vấn đề gì", "đã test xong". Hãy viết đã kiểm tra bằng cách nào, hoặc ghi rõ là chưa kiểm tra.

## Nói rõ mình chắc đến đâu

Người đọc hiểu các từ chỉ khả năng rất khác nhau. Trong một nghiên cứu của tình báo Mỹ, cùng một cụm "khả năng đáng kể" được người đọc hiểu là từ 20% đến 80%. Vì vậy mỗi nhận định chưa chắc nên kèm căn cứ, và kèm con số nếu có.

| Mức | Cách viết | Ví dụ |
|---|---|---|
| Đã xác nhận | Nêu cách xác nhận | Đã xác nhận nguyên nhân: tái hiện được lỗi khi tắt graceful shutdown. |
| Nhiều khả năng | Nêu căn cứ | Nhiều khả năng do cache: lỗi chỉ xuất hiện khi bật cache (4/20 request). |
| Có thể | Nêu căn cứ và điều chưa kiểm tra | Có thể do phiên bản client cũ. Chưa kiểm tra log phía client. |
| Chưa rõ | Nói thẳng, kèm bước tiếp theo | Chưa xác định được nguyên nhân. Đang đọc log của gateway. |

Với thời hạn, viết "dự kiến" kèm ngày: "dự kiến xong ngày 14/11". Với số ước lượng, viết "khoảng" kèm số: "khoảng 100 đơn hàng".

## Báo cáo tiến độ

Các phần, theo thứ tự:

1. **Tóm tắt:** một hoặc hai câu về tình trạng chung so với kế hoạch.
2. **Cần quyết định hoặc cần hỗ trợ:** cần gì, từ ai, trước lúc nào. Phần này đặt gần đầu để không bị bỏ sót.
3. **Đã xong:** viết kết quả, không viết hoạt động. "Fix xong crash khi login" thay cho "làm việc với bug login".
4. **Đang làm:** còn lại bao nhiêu việc, dự kiến xong khi nào. Nếu trễ thì nêu lý do.
5. **Vấn đề:** mỗi vấn đề kèm hướng giải quyết và hạn xử lý.
6. **Kế hoạch kỳ tới.**

Dùng "9/12 task" thay cho "75%" khi có thể: người đọc thấy ngay còn lại mấy việc. Một task chỉ tính là xong khi đã xong hẳn, không tính "xong 90%".

```markdown
## Báo cáo tuần 45 (04/11 – 08/11/2026)

**Tóm tắt:** Sprint 14 xong 9/12 task, chậm 2 ngày so với kế hoạch vì chờ spec từ đối tác.

**Cần hỗ trợ:** Cần team hạ tầng cấp quyền đọc DB production trước 17h ngày 12/11.
Nếu chậm hơn, ngày test tích hợp sẽ lùi tương ứng.

### Đã xong
- Tích hợp đăng nhập bằng Apple (PR #128), đã merge và chạy trên staging.
- Fix crash khi token hết hạn: 42/42 unit test pass.

### Đang làm
- API xuất hóa đơn: xong 5/8 endpoint. 3 endpoint còn lại dự kiến xong ngày 14/11.

### Vấn đề
- Staging hết dung lượng đĩa. Hướng giải quyết: dọn log cũ trong tuần này,
  rồi tăng đĩa lên 200 GB. Người phụ trách: An. Hạn: 13/11.

### Kế hoạch tuần tới
- Hoàn thành 3 endpoint còn lại. Bắt đầu test tích hợp ngày 18/11.
```

## Báo cáo sự cố

Các phần, theo thứ tự:

1. **Tóm tắt:** chuyện gì xảy ra, từ lúc nào đến lúc nào, do đâu.
2. **Ảnh hưởng:** bao nhiêu người dùng, bao nhiêu giao dịch, bao lâu. Nêu cả phần không bị ảnh hưởng.
3. **Dòng thời gian:** ít nhất bốn mốc là lúc xảy ra, lúc phát hiện, lúc bắt đầu xử lý, lúc khắc phục xong. Ghi rõ múi giờ.
4. **Phát hiện:** nhờ alert hay nhờ người dùng báo, và sau bao lâu.
5. **Nguyên nhân gốc rễ:** nguyên nhân trực tiếp, nguyên nhân gián tiếp, và lý do sâu hơn khiến lỗi lọt qua được.
6. **Bài học:** điều gì làm tốt, điều gì chưa tốt, chỗ nào gặp may.
7. **Hành động ngăn tái diễn:** mỗi hành động bắt đầu bằng động từ, có trạng thái hoàn thành kiểm tra được, có người phụ trách và hạn.

Ba điều cần giữ khi viết:

- **Không đổ lỗi.** Báo cáo sự cố không phải bản kiểm điểm. Trong phần kể lại, hãy gọi theo vai trò ("kỹ sư on-call") và theo hệ thống, không gọi tên người. Tên người chỉ xuất hiện ở cột người phụ trách hành động.
- **Không nhận "sẽ cẩn thận hơn" làm hành động.** Một hành động dựa vào việc ai đó nhớ kiểm tra thì sẽ lại sót. Hãy thay bằng một bước kiểm tra tự động hoặc một alert.
- **Dùng đúng mức độ.** Chỉ viết "sập" hay "ngừng dịch vụ" khi toàn bộ dịch vụ ngừng. Nếu 31% request lỗi thì viết "31% request lỗi".

Trong lúc đang xử lý, mỗi lần cập nhật nên có ba ý: đã biết gì, đang làm gì, bao giờ cập nhật tiếp. Ví dụ: "Đã tìm ra nguyên nhân: deadlock ở DB. Đang viết script xử lý. Dự kiến 20 phút nữa xong, sẽ cập nhật lúc 20h40."

```markdown
## Báo cáo sự cố: mất trạng thái đơn hàng khi deploy order-service

**Tóm tắt:** Từ 20h05 đến 20h08 ngày 14/11/2026 (giờ Việt Nam), khoảng 100 đơn hàng
bị mất trạng thái trong lúc deploy order-service. Nguyên nhân: service chưa cấu hình
graceful shutdown.

**Ảnh hưởng:** Khoảng 100 đơn hàng phải khôi phục thủ công, mất 4 giờ.
Không mất dữ liệu thanh toán. Các service khác không bị ảnh hưởng.

### Dòng thời gian (giờ Việt Nam, UTC+7)
- 20h00: bắt đầu deploy.
- 20h05: request đang xử lý bị hủy khi pod cũ tắt.
- 20h12: phát hiện qua phản ánh của bộ phận chăm sóc khách hàng.
- 20h20: kỹ sư on-call rollback.
- 20h31: xác nhận đơn hàng mới được xử lý bình thường.

### Nguyên nhân gốc rễ
- Trực tiếp: pod bị tắt ngay khi nhận SIGTERM, không chờ request đang chạy.
- Gián tiếp: không có alert cho đơn hàng mất trạng thái, nên phát hiện chậm 7 phút.
- Gốc rễ: checklist deploy không có bước kiểm tra cấu hình shutdown.

### Hành động ngăn tái diễn
| Hành động | Người phụ trách | Hạn |
|---|---|---|
| Bật graceful shutdown với thời gian chờ 30 giây cho order-service | Lan | 18/11 |
| Thêm alert khi có trên 50 đơn hàng lỗi trong 1 phút | Minh | 20/11 |
| Thêm bước kiểm tra cấu hình shutdown vào pipeline deploy | Lan | 25/11 |
```

## Báo cáo kết quả kiểm thử hoặc đo hiệu năng

Các phần, theo thứ tự:

1. **Kết luận:** trả lời thẳng câu người đọc hỏi, ví dụ đã đủ điều kiện release chưa.
2. **Phạm vi:** đã kiểm tra gì, không kiểm tra gì, và phần nào không kiểm tra được.
3. **Môi trường và cách đo:** máy, phiên bản, dữ liệu, số lần chạy. Người khác phải chạy lại được.
4. **Kết quả:** số tuyệt đối kèm đơn vị, kèm mốc so sánh. Với phép đo, thêm độ dao động.
5. **Kết quả xấu:** chỗ chậm đi, chỗ tốn thêm tài nguyên, trường hợp không cải thiện.
6. **Nhận định:** ghi rõ đây là suy đoán nếu chưa kiểm chứng.
7. **Đề xuất:** việc cần làm tiếp.

Tên trạng thái và chỉ số giữ tiếng Anh như cách dev vẫn dùng: Pass, Fail, Blocked, Critical, Major, Minor, p95, throughput. Đơn vị và phần giải thích viết tiếng Việt.

Khi báo một tỷ lệ, luôn kèm số gốc. "Nhanh hơn 40%" chưa đủ, hãy viết "thời gian build giảm từ 10 phút xuống 6 phút (40%)".

```markdown
## Kết quả đo parser v2

**Kết luận:** Parser v2 nhanh gấp 2,1 lần v1 trên dữ liệu production và cho kết quả giống hệt.
Đề xuất bật v2 cho file dưới 40 MB.

**Phạm vi:** Đã đo file từ 4 KB đến 48 MB. Chưa đo trên Windows và chưa đo file trên 50 MB.

**Cách đo:** Chạy mỗi parser 30 lần trên MacBook Air M2, macOS 15.1, commit 4f2a9c, bản release.
Dữ liệu: 1.200 file lấy mẫu từ log production tháng 2/2026.

**Kết quả:** Thời gian parse trung vị giảm từ 840 ms (v1) xuống 400 ms (v2).
Một nửa số lần chạy của v2 nằm trong khoảng 370–450 ms.

**Kết quả xấu:** Bộ nhớ tăng 12%, từ 210 MB lên 235 MB. File trên 40 MB không nhanh hơn.

**Nhận định:** Phần nhanh hơn có thể đến từ tokenizer mới. Chưa profile để xác nhận.

**Chạy lại:** `make bench CORPUS=prod-2026-02` tại commit 4f2a9c.
```

## Báo cáo sau khi làm xong một việc

Loại này dùng khi một kỹ sư hoặc một AI agent báo lại kết quả cho người giao việc. Người đọc thường không theo dõi quá trình làm, nên báo cáo phải tự đủ nghĩa.

Các phần, theo thứ tự:

1. **Kết quả:** câu đầu tiên nói việc đã xong đến đâu.
2. **Đã kiểm chứng:** kiểm tra gì, bằng cách nào, kết quả ra sao.
3. **Chưa kiểm chứng:** phần nào chưa thử.
4. **Chưa làm, bỏ qua hoặc thất bại:** kèm lý do.
5. **Đã thay đổi gì:** kể cả những thay đổi nhỏ ngoài yêu cầu.
6. **Cần người đọc quyết định gì.**
7. **Bước tiếp theo.**

Ba lỗi hay gặp ở loại báo cáo này: báo "đã xong" khi chưa kiểm chứng, không nhắc tới bước đã bỏ qua, và chỉ kể thay đổi lớn mà bỏ sót thay đổi nhỏ. Trước khi gửi, hãy đối chiếu từng lời khẳng định với một kết quả mình thật sự đã thấy.

```markdown
Đã sửa crash khi login: app không còn crash khi token hết hạn.

**Đã kiểm chứng:** Tái hiện được crash trước khi sửa, sau khi sửa thì không còn.
42/42 unit test của phần auth pass.

**Chưa kiểm chứng:** Chưa thử trên thiết bị thật và chưa thử trên iOS 17.

**Bỏ qua:** Chưa chạy script migration vì không kết nối được DB staging.

**Đã thay đổi:** Sửa phần kiểm tra token trong `AuthSession.swift` và thêm một file test.
Ngoài yêu cầu, tôi đổi tên một hàm private cho dễ đọc.

**Cần bạn quyết định:** Khi token hết hạn, app nên đăng xuất hay tự làm mới token?

**Bước tiếp theo:** Chạy UI test trên thiết bị thật trước khi release.
```

## Thời gian và số

- Viết giờ theo kiểu 24 giờ: "20h05" hoặc "20:05", kèm ngày.
- Báo cáo sự cố ghi múi giờ một lần ở đầu dòng thời gian: "(giờ Việt Nam, UTC+7)".
- Dùng ngày cụ thể thay cho "tuần sau", "sắp tới", "gần đây". Báo cáo còn được đọc lại nhiều tuần sau đó.
- Ghi rõ số liệu được chốt lúc nào khi con số còn thay đổi: "tính đến 17h ngày 12/11".

## Kiểm tra bằng linter

```bash
python3 scripts/ste-lint.py --lang vi --profile report bao-cao.md
```

Profile `report` giữ mọi thiết lập của profile `docs` và cảnh báo thêm ba nhóm: từ chỉ lượng mơ hồ (`vague-quantity`), thời gian mơ hồ (`vague-time`), và lời khẳng định không kèm cách kiểm chứng (`unverified-claim`). Lối văn hành chính (`officialese`) được cảnh báo ở mọi profile. Linter không biết con số có đúng hay không, và không biết báo cáo có thiếu phần nào không. Hai việc đó người viết phải tự kiểm tra.

## Nguồn tham khảo

Các trích dẫn do công cụ đọc web trả về và chưa được đối chiếu lại từng chữ, nên tài liệu này chỉ thuật lại ý, không trích nguyên văn.

**Cách người Việt viết báo cáo**

- Le Thi Ha, ["Kỹ năng báo cáo và liên lạc"](https://viblo.asia/p/ky-nang-bao-cao-va-lien-lac-xQMGJDNdkam), Viblo, 2016: trình bày từ kết luận, dùng con số, tách sự thật khỏi cảm nhận, báo cả việc sai.
- Phan Duy Van, ["Chia sẻ kinh nghiệm viết báo cáo"](https://viblo.asia/p/chia-se-kinh-nghiem-viet-bao-cao-RQqKLeomZ7z), Viblo, 2020: tránh "gần xong", "hình như trễ", đặt điều được hỏi lên đầu.
- Thuy Coi, ["Cách viết báo cáo công việc hiệu quả"](https://viblo.asia/p/cach-viet-bao-cao-cong-viec-hieu-qua-naQZRxWQ5vx), Viblo, 2019: các phần của báo cáo định kỳ, vấn đề tồn đọng kèm hạn xử lý.
- MISA AMIS, ["7 mẫu báo cáo công việc"](https://amis.misa.vn/33156/bao-cao-cong-viec/): việc chưa hoàn thành cần trạng thái, nguyên nhân, ảnh hưởng và ngày dự kiến xong.
- Trang Can, ["Cách báo cáo sự cố và mindset về cách phòng tránh lặp lại sự cố"](https://viblo.asia/p/cach-bao-cao-su-co-va-mindset-ve-cach-phong-tranh-lap-lai-su-co-ma-engineer-nen-biet-1VgZv6ErZAw), Viblo, 2021: bốn mốc thời gian, ba tầng nguyên nhân, không đổ lỗi, không nhận "chú ý hơn" làm đối sách.
- Huy Hoàng, ["Bí kíp sinh tồn khi chạy production"](https://viblo.asia/p/tam-su-code-bi-kip-sinh-ton-khi-chay-production-kich-ban-xu-ly-khung-hoang-tu-so-0-ymJXDQYPJkq), Viblo: cách cập nhật trong lúc xử lý sự cố, hành động có ngưỡng cụ thể.
- Hưng Phạm, ["Cả trăm đơn hàng bốc hơi chỉ trong 3 phút"](https://viblo.asia/p/ca-tram-don-hang-boc-hoi-chi-trong-3-phut-tat-ca-vi-mot-dong-config-bi-quen-oK9VygxdJQR), Viblo, 2025: bài kể lại một sự cố thật, là cơ sở cho ví dụ ở trên.
- Better Bytes Academy, ["Báo cáo kết quả kiểm thử"](https://viblo.asia/p/bao-cao-ket-qua-kiem-thu-buc-tranh-toan-canh-cho-team-WR5JR9zr4Gv), Viblo, 2025: kết luận là câu trả lời "đã sẵn sàng release chưa".
- Chu Ngọc Cường, ["Thay 'chưa' bằng 'không'"](https://vnexpress.net/thay-chua-bang-khong-3081888.html), VnExpress, 2014: phê bình lối dùng "chưa" để giảm nhẹ.
- Hà Vũ, ["Nhiều khoảng trống từ báo cáo chống lãng phí"](https://vneconomy.vn/nhieu-khoang-trong-tu-bao-cao-chong-lang-phi.htm), VnEconomy, 2018: báo cáo bị phê bình vì chung chung, thiếu số liệu.
- Lê Ngọc Hồng, ["Chuẩn hóa công tác soạn thảo văn bản báo cáo"](https://www.quanlynhanuoc.vn/?p=13453), Tạp chí Quản lý nhà nước, 2021: số liệu phải thống nhất đơn vị và có thời điểm chốt.

Chưa tìm thấy báo cáo sự cố công khai nào của một công ty Việt Nam. Phần báo cáo sự cố vì thế dựa trên các bài hướng dẫn và một bài kể lại sự cố, chưa dựa trên báo cáo thật.

**Thông lệ quốc tế**

- Google, [SRE Book: Postmortem Culture](https://sre.google/sre-book/postmortem-culture/) và [Example Postmortem](https://sre.google/sre-book/example-postmortem/), cùng [SRE Workbook, chương 10](https://sre.google/workbook/postmortem-culture/): các phần của postmortem, hành động có trạng thái kết thúc kiểm tra được và một người phụ trách.
- Atlassian, [Incident Management Handbook](https://pages.eml.atlassian.com/rs/594-ATC-127/images/Atlassian-incident-management-handbook-.pdf): dòng thời gian ghi múi giờ, gọi theo vai trò.
- PagerDuty, [Postmortem guide](https://docs.pagerduty.com/ops-guides/postmortem-best-practices/step-by-step): hành động bắt đầu bằng động từ, dùng đúng từ chỉ mức độ.
- Sherman Kent, ["Words of Estimative Probability"](https://www.cia.gov/resources/csi/static/Words-of-Estimative-Probability.pdf), CIA, 1964: người đọc hiểu từ chỉ khả năng rất khác nhau.
- ODNI, [ICD 203 Analytic Standards](https://archive.dni.gov/files/documents/ICD/ICD-203.pdf), 2015: kết luận lên đầu, tách thông tin khỏi nhận định.
- Gernot Heiser, ["Systems Benchmarking Crimes"](https://gernot-heiser.org/benchmarking-crimes.html): số tuyệt đối kèm tỷ lệ, có mốc so sánh, có độ dao động.
- Simon Tatham, ["How to Report Bugs Effectively"](https://www.chiark.greenend.org.uk/~sgtatham/bugs.html), 1999: nêu sự kiện trước, chẩn đoán sau.
- Anthropic, [Prompting Claude Fable 5](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5): báo cáo cuối task mở đầu bằng kết quả, đối chiếu từng lời khẳng định với kết quả đã thấy.
