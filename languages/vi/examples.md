# Ví dụ trước / sau — tiếng Việt

Các ví dụ này được viết riêng cho bản tiếng Việt của skill để minh họa quy tắc trong `languages/vi/rules.md`, không trích từ hệ thống thật nào.

Độ dài tính theo âm tiết: mỗi token phân tách bằng dấu cách là một âm tiết.

## Ví dụ: mô tả công cụ

**Trước:**
> Công cụ này sẽ tiến hành việc đồng bộ hóa trạng thái giữa các backend đã được cấu hình, và nếu có sự xung đột được phát hiện thì nó có thể tự động giải quyết tùy theo chiến lược đã được thiết lập, hay là đưa xung đột ra để xem xét thủ công.

**Vi phạm:**
- Danh từ hóa: "tiến hành việc đồng bộ hóa", "có sự xung đột".
- Một câu chứa ba ý: đồng bộ, giải quyết, báo xung đột.
- "nó" không rõ chỉ công cụ hay chiến lược.
- "hay là" có thể đọc thành "hoặc", cũng có thể đọc thành một lựa chọn trong chiến lược.
- 55 âm tiết, vượt giới hạn 30.

Không vi phạm: "có thể tự động giải quyết". "Có thể" cho biết công cụ không cam kết sẽ giải quyết, nên bản viết lại cũng không được cam kết.

**Sau:**
> Công cụ cố gắng đồng bộ trạng thái giữa các backend đã cấu hình. Nếu công cụ tìm thấy xung đột, công cụ đọc chiến lược đã cấu hình. Nếu chiến lược cho phép tự động giải quyết, công cụ có thể tự giải quyết xung đột. Nếu công cụ không giải quyết xung đột, công cụ báo xung đột để người dùng xem xét.

Câu cuối xét theo kết quả (công cụ không giải quyết được), không xét theo chiến lược. Đó mới đúng là ý của "hay là" trong bản gốc: xung đột được chuyển cho người xem xét cả khi chiến lược cho phép tự giải quyết mà công cụ vẫn không giải quyết được.

## Ví dụ: thông báo lỗi

**Trước:**
> Đã có lỗi có thể xảy ra trong quá trình xử lý yêu cầu của bạn do sự không khớp về định dạng dữ liệu, điều này có thể là do phiên bản client đã cũ.

**Vi phạm:**
- "Đã có lỗi có thể xảy ra" vừa khẳng định vừa nói là chưa chắc. Người đọc không biết lỗi có xảy ra hay không.
- Danh từ hóa: "quá trình xử lý", "sự không khớp".
- "điều này" không rõ chỉ lỗi hay chỉ sự không khớp.
- Một câu chứa ba nhận định.

Không vi phạm: "có thể" ở cả hai chỗ. Hệ thống không biết chắc nguyên nhân, và hai chữ "có thể" nói đúng điều đó.

**Sau:**
> Yêu cầu của bạn có thể đã thất bại. Nguyên nhân có thể là định dạng dữ liệu không khớp với định dạng máy chủ cần. Phiên bản client cũ có thể gây ra lỗi không khớp này. Kiểm tra phiên bản client của bạn.

Bản gốc viết "Đã có lỗi", một khẳng định. Nhưng ngay sau đó là "có thể xảy ra". Bản viết lại chọn cách nói dè dặt hơn ("có thể đã"), vì câu gốc không đủ căn cứ để khẳng định. Không viết "Yêu cầu đã thất bại", và không viết "phiên bản cũ là nguyên nhân phổ biến nhất". Bản gốc không nói cả hai điều đó.

## Ví dụ: chỉ dẫn giữa các agent

**Trước:**
> Sau khi job upstream đã xong rồi và giả sử không có lỗi gì thì agent downstream nên tiến hành xử lý artifact đầu ra, tuy nhiên cần lưu ý rằng đôi khi artifact không đầy đủ được tạo ra khi bị timeout.

**Vi phạm:**
- "đã xong rồi": "rồi" thừa sau "đã".
- "tiến hành xử lý": danh từ hóa.
- "cần lưu ý rằng": cụm đệm.
- "được tạo ra khi bị timeout": câu bị động, không rõ ai tạo artifact.
- Một câu chứa ba sự kiện: điều kiện, hành động, cảnh báo.

**Sau:**
> Chờ job upstream hoàn tất mà không có lỗi. Sau đó đọc artifact đầu ra. Cảnh báo: khi bị timeout, job upstream có thể tạo artifact không đầy đủ. Kiểm tra artifact đầy đủ trước khi dùng.

Có ba điểm cần nói rõ:
- "nên tiến hành xử lý" thành câu mệnh lệnh "đọc". Điều này đúng với chỉ dẫn gửi cho agent thực thi. Không làm vậy với văn bản mô tả.
- Câu cuối là **nội dung mới**. Bản gốc cảnh báo nhưng không nói phải làm gì. Nếu tác giả cố ý không nói, xóa câu đó.
- "đôi khi" thành "có thể". Cả hai đều nói việc đó không chắc xảy ra. Bản viết lại không biến "đôi khi" thành "luôn luôn".

## Ví dụ: README (văn bản cho người đọc)

**Trước:**
> Lớp cache của chúng tôi được thiết kế để tích hợp một cách liền mạch vào stack hiện tại của bạn mà không gặp trở ngại nào; nó tận dụng độ tương đồng ngữ nghĩa để giảm đáng kể tình trạng cache miss vốn là vấn đề nan giải của các workload LLM.

**Vi phạm:**
- Từ quảng cáo và khẳng định không có số đo: "một cách liền mạch", "không gặp trở ngại nào", "đáng kể", "nan giải".
- Dấu chấm phẩy nối hai ý.
- "nó" ở đầu vế sau.
- 53 âm tiết, vượt cả giới hạn 45 của văn bản cho người đọc.

**Sau:**
> Chúng tôi thiết kế lớp cache để tích hợp vào stack hiện tại của bạn. Lớp cache dùng độ tương đồng ngữ nghĩa để giảm cache miss, một vấn đề lâu nay của các workload LLM.

Với văn bản cho người đọc, không cần thay "cache", "stack", "workload" bằng từ tiếng Việt. Các thuật ngữ đó được giữ nguyên vì dev quen dùng và cả đoạn dùng nhất quán. Bản viết lại vẫn bỏ từ quảng cáo, dấu chấm phẩy và chữ "nó". Bản viết lại giữ "thiết kế để", vì bản gốc nói về mục tiêu thiết kế, không nói về kết quả đo được.

## Ví dụ: lỗi riêng của tiếng Việt

| Quy tắc | Trước | Sau | Lý do |
|---|---|---|---|
| Viết đủ dấu | "Khong the ket noi, vui long thu lai." | "Không thể kết nối. Thử lại." | "ket noi" còn đoán được, nhưng "thu" có thể là "thử", "thu" hoặc "thư". |
| Thiếu dấu hiệu thời gian | "Tác vụ hoàn tất." | "Tác vụ đã hoàn tất." | Không có "đã", câu có thể là trạng thái hiện tại hoặc kết quả mong muốn. |
| "hay" đa nghĩa | "Dùng tệp A hay tệp B." | "Dùng tệp A hoặc tệp B." | "hay" còn có nghĩa "thường" hoặc "tốt". |
| "được" đa nghĩa | "Người dùng được xóa tệp." | "Người dùng có quyền xóa tệp." | Câu gốc có thể nghĩa là "người dùng bị xóa" hoặc "người dùng được phép xóa". |
| Số và ngày | "Giới hạn 1.000 bản ghi, hết hạn 03/04/2026." | "Giới hạn 1000 bản ghi. Hết hạn ngày 2026-04-03." | "1.000" có thể là 1,0. "03/04" có thể là tháng 3 hoặc tháng 4. |
| Bị động kiểu "được ... bởi" | "Tệp được xóa bởi hệ thống." | "Hệ thống xóa tệp." | "được ... bởi" thường bị coi là câu văn "Tây". Câu chủ động ngắn và rõ hơn. |
