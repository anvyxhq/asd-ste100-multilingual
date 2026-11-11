# Văn phong tài liệu và báo cáo tiếng Việt

Tài liệu này hướng dẫn cách **viết mới hoặc viết lại** tài liệu kỹ thuật bằng tiếng Việt, ví dụ README, tài liệu thiết kế, hướng dẫn, changelog, mô tả PR, báo cáo tiến độ, báo cáo sự cố, biên bản họp.

Người đọc là lập trình viên, kỹ sư, PM, QA người Việt. Họ đọc thuật ngữ tiếng Anh hằng ngày. Vì vậy văn bản phải đọc lên như do một kỹ sư Việt viết, không giống bản dịch máy từ tiếng Anh.

> **Không áp dụng cho chuỗi giao diện app** (UI strings, thông báo cho người dùng cuối, App Store). Người dùng cuối không đọc thuật ngữ kỹ thuật, nên app dùng cấu hình riêng.

## Hai mức văn phong

| | `rules.md` — mức Strict | Tài liệu này — mức tự nhiên |
|---|---|---|
| Người đọc | Agent, hệ thống | Người: kỹ sư, PM, QA |
| Loại văn bản | Error message, tool description, chỉ dẫn cho agent | README, tài liệu, mô tả PR, báo cáo |
| Ưu tiên | Một cách hiểu duy nhất | Rõ nghĩa và dễ đọc |
| Câu | Ngắn, mỗi câu một ý | Dài ngắn xen kẽ, nối ý bằng từ nối |
| Chủ ngữ | Luôn nêu, lặp lại danh từ | Lược khi người đọc đã biết đang nói về ai |

Văn bản cho người đọc mà viết theo mức Strict sẽ nghe như văn dịch: câu cụt, chủ ngữ lặp, ý rời rạc. Ở mức tự nhiên, chỉ tách câu hoặc lặp danh từ khi câu đó thật sự có hai cách hiểu.

Có bốn điều mức tự nhiên vẫn giữ nghiêm như mức Strict: không đổi phỏng đoán thành khẳng định ("có thể" vẫn là "có thể"), không thêm thông tin, không dùng từ quảng cáo, viết đủ dấu.

## 1. Thuật ngữ: tiếng Anh khi nói về kỹ thuật

Nguyên tắc: **khi nói về kỹ thuật thì dùng thuật ngữ tiếng Anh, còn trong câu thường thì từ tiếng Việt cũng được.**

Một từ thuộc ngữ cảnh kỹ thuật khi nó chỉ một thứ cụ thể trong code, trong hệ thống hoặc trong công cụ: một class, một variable, một permission trong IAM, một error mà function trả về. Cùng từ đó, khi dùng theo nghĩa thông thường để nói chuyện với người đọc, thì viết tiếng Việt vẫn tự nhiên.

| Ngữ cảnh kỹ thuật | Câu thường |
|---|---|
| Function `refresh()` throw error khi token hết hạn. | Nếu gặp lỗi, bạn thử đăng nhập lại. |
| Thêm permission `s3:GetObject` cho role. | Bạn cần có quyền admin để xem trang này. |
| Bảng `users` lưu mỗi user một dòng. | Người dùng sẽ thấy màn hình đăng nhập. |
| Giá trị default của `timeout` là 30 giây. | Ứng dụng mở trang chủ theo mặc định. |

Quy tắc giữ thuật ngữ tiếng Anh áp dụng khi người đọc là dev. Khi viết cho người không chuyên, ví dụ PM, QA hoặc bên kiểm định, hãy ưu tiên tả kết quả bằng lời thường. Chỉ giữ những thuật ngữ người đọc đã quen, và giải thích các thuật ngữ còn lại ở lần dùng đầu tiên.
| Run test trước khi merge. | Chạy lệnh sau để cài đặt. |
| Handle error ở tầng API. | Nhóm đã xử lý xong yêu cầu của khách hàng. |

Trong cùng một tài liệu, một khái niệm ở cùng một ngữ cảnh thì giữ một cách viết. Đừng viết "user" ở câu trước rồi "người dùng" ở câu sau khi cả hai cùng chỉ một dòng trong bảng `users`.

### Luôn viết tiếng Anh

Với các thuật ngữ sau, từ tiếng Việt tương ứng gần như không ai dùng. Số trong ngoặc là số bài có dùng từ đó trong 102 bài viết tay của hai blog lập trình tiếng Việt (xem [`evidence.md`](evidence.md)).

| Viết | Ít gặp hoặc không gặp |
|---|---|
| file (41) | tệp (0), tập tin (0) |
| server (24) | máy chủ (2) |
| database (21) | cơ sở dữ liệu (3) |
| framework (24) | khung (0–1) |
| code (90) | mã nguồn (2) |
| debug (14) | gỡ lỗi (0) |
| module (12) | mô-đun (0) |
| deploy (14) | triển khai (0) |
| class (27) | lớp (5) |
| test (26) | kiểm thử (3) |
| team (31) | nhóm (khoảng 6) |
| array (15) | mảng (3) |
| build (26), API (29), link (26), performance (12) | |

Thuật ngữ Git (commit, branch, merge, pull request, repo) và endpoint, token, callback, middleware, payload cũng viết tiếng Anh.

"Triển khai" vẫn được dùng nhiều, nhưng theo nghĩa "implement": "triển khai phương thức này như sau". "Kiểm tra" cũng vậy, gần như luôn mang nghĩa "check" chứ không phải "test".

### Tiếng Anh khi nói về kỹ thuật, tiếng Việt trong câu thường

| Nhóm | Thuật ngữ tiếng Anh | Từ tiếng Việt dùng trong câu thường |
|---|---|---|
| Code | variable, function, object, method, property, string, library | biến, hàm, đối tượng, phương thức, thuộc tính, chuỗi, thư viện |
| Hệ thống | user, system, error, bug, permission, default, config, data, version | người dùng, hệ thống, lỗi, quyền, mặc định, cấu hình, dữ liệu, phiên bản |
| Sản phẩm | feature, UI, app, project, tool, algorithm | tính năng, giao diện, ứng dụng, dự án, công cụ, thuật toán |
| Thao tác | install, run, handle, support, define, fix, update, design | cài đặt, chạy, xử lý, hỗ trợ, khai báo, sửa, cập nhật, thiết kế |

Đây là lựa chọn riêng của bộ quy tắc này. Trong mẫu 102 bài, nhiều tác giả viết tiếng Việt cho nhóm này ngay cả khi nói về kỹ thuật, ví dụ "biến" (khoảng 22 bài, so với 0 bài viết "variable") hay "chạy" (62 bài, so với 9 bài viết "run"). Nếu nhóm bạn quen viết tiếng Việt thì cứ giữ, miễn là nhất quán. Nếu nhóm bạn đã có bảng thuật ngữ riêng thì theo bảng đó.

### Từ có trong bảng thuật ngữ của các hãng nhưng dev ít dùng

**Từ Việt chuẩn, dùng trong giao diện sản phẩm và văn bản trang trọng:** tệp, máy chủ, cơ sở dữ liệu, kiểm thử, gỡ lỗi, mã nguồn. Các từ này đúng và dễ hiểu. Hãy dùng khi người đọc không phải dev (khách hàng, lãnh đạo), khi viết thông báo cho người dùng cuối, hoặc khi nhóm bạn đã quen. Trong 102 bài viết tay, mỗi từ chỉ xuất hiện ở 0–3 bài.

**Bản dịch ít người dùng:** yêu cầu kéo (pull request), cam kết (commit), điểm cuối (endpoint), mã thông báo (token), gọi lại (callback), khuôn khổ hoặc khung (framework), phần mềm trung gian (middleware), tải trọng (payload). Các từ này không sai: phần lớn là thuật ngữ chính thức trong bảng thuật ngữ của Microsoft. Nhưng dev không quen, và các hãng dịch không thống nhất. Cache là "bộ đệm ẩn" ở Microsoft nhưng "bộ nhớ đệm" ở Apple. Framework là "khuôn khổ" ở Microsoft nhưng "khung" ở Google. "Cam kết" của Microsoft là commit của giao dịch cơ sở dữ liệu, không phải commit của Git.

Nếu bạn viết chuỗi giao diện cho một sản phẩm đã bản địa hóa, hãy theo bảng thuật ngữ của nền tảng đó, không theo phần này.

### Cách viết thuật ngữ tiếng Anh

- Viết thường giữa câu như danh từ chung: "tạo một branch mới", "deploy lên server". Viết hoa tên riêng (GitHub, Swift), từ viết tắt (API, PR) và tên thành phần ("Cache Server").
- Không thêm đuôi số nhiều: "các function", "hai pull request", "44 test". Hơn 90% trường hợp trong mẫu viết như vậy.
- Tên hàm, tên variable, lệnh, đường dẫn: đặt trong backtick, không dịch.
- Lần đầu dùng một thuật ngữ ít quen, chú thích trong ngoặc: "bảo mật 2 lớp (two-factor authentication)". Thuật ngữ dev nào cũng biết thì không cần chú thích.
- Tiêu đề viết bằng tiếng Anh thì giữ cách viết hoa của tiếng Anh.

## 2. Câu văn: viết như người Việt

### Những kiểu câu bị giới ngôn ngữ học phê bình

Các quy tắc trong bảng này đều có nguồn (xem cuối tài liệu).

| Kiểu câu "Tây" | Viết tự nhiên | Cách làm |
|---|---|---|
| Dữ liệu được mã hóa bởi server. | Server mã hóa dữ liệu. / Dữ liệu được server mã hóa. / Dữ liệu do server mã hóa. | Bỏ "bởi". Dùng câu chủ động, hoặc đặt tác nhân trước động từ. |
| Bạn phải nhận được sự cho phép của admin. | Bạn phải được admin cho phép. | Đổi "sự/việc + động từ" thành câu có chủ ngữ và động từ. |
| Cảm ơn sự quan tâm của bạn. | Cảm ơn bạn đã quan tâm. | Như trên. |
| Những lập trình viên Việt thường viết "file". | Lập trình viên Việt thường viết "file". | Bỏ "những/các" khi nói chung chung. |
| Cài gói rồi cấu hình nó. | Cài gói rồi cấu hình. / Cài rồi cấu hình gói. | Không dịch "it" thành "nó". Bỏ đi, hoặc lặp lại danh từ. |
| Request đến từ client. | Request của client. / Client gửi request. | "Đến từ" là cách nói dịch từ "come from". |
| hoàn thành xong, tái tạo lại, tối ưu nhất | hoàn thành, tái tạo, tối ưu | Bỏ từ thừa. |
| Qua bảng 2 cho thấy lỗi tăng. | Bảng 2 cho thấy lỗi tăng. | Không để trạng ngữ đứng thay chủ ngữ. |
| Nếu cổng bị chiếm, service không khởi động. | Nếu cổng bị chiếm thì service không khởi động. | Dùng đủ cặp từ nối: nếu… thì, vì… nên, tuy… nhưng. |

Nguyên nhân, điều kiện và thời gian thường đứng đầu câu: "Vì hết bộ nhớ nên service dừng", "Vào 2 giờ sáng, hệ thống khởi động lại".

Về "được": câu bị động có "được" vẫn là tiếng Việt tự nhiên khi tác nhân đứng trước động từ. Khi không cần nêu ai làm, hãy thử bỏ hẳn "được": "File cấu hình lưu trong thư mục gốc".

### Quy ước riêng của bộ quy tắc này

Các điểm sau chưa tìm thấy nguồn tiếng Việt nào nêu tên. Chúng là quy ước riêng, bạn có thể bỏ qua nếu không hợp.

| Rườm rà | Gọn hơn |
|---|---|
| Library này được sử dụng để xử lý ảnh. | Library này dùng để xử lý ảnh. |
| Tính năng này cho phép bạn xuất PDF. | Bạn có thể xuất PDF bằng tính năng này. |
| Cache đóng một vai trò quan trọng trong hiệu năng. | Cache ảnh hưởng lớn tới hiệu năng. |
| Hàm này trả về giá trị một cách nhanh chóng. | Hàm này trả về giá trị nhanh. |

"Một cách + tính từ" không sai, và các nhà nghiên cứu vẫn dùng. Chỉ bỏ khi câu không đổi nghĩa.

Các cụm này có trong văn viết tay, nhưng hiếm. Ở hai nhóm bài đối chứng trong [`evidence.md`](evidence.md), chúng xuất hiện nhiều hơn từ 2 đến hơn 25 lần. Một nhóm còn có tiêu đề viết hoa mọi chữ và số viết kiểu "1,000". Một văn bản dày đặc các cụm này sẽ đọc lên như bản dịch máy.

### Những chỗ gượng hay gặp khi AI viết tiếng Việt

Các lỗi dưới đây đều do người đọc thật chỉ ra, phần lớn trong chính tài liệu của repo này. Từng chữ trong câu đều đúng, nhưng người Việt không nói như vậy. Linter chỉ bắt được hai kiểu đầu và kiểu cuối cùng, nên sau khi viết xong hãy tự đọc lại theo bảng này.

| Kiểu gượng | Ví dụ | Viết lại |
|---|---|---|
| Dịch sát một câu nói gọn của tiếng Anh | "văn bản mà giọng văn là mục đích", "Mức độ chắc chắn là nội dung", "…là chìa khóa" | Nói ý đó bằng lời bình thường: "những văn bản cần giọng văn riêng", "bỏ chữ 'có thể' là đổi nghĩa câu" |
| Câu cụt kiểu ghi chú | "Muốn thêm một ngôn ngữ? Xem `languages/README.md`.", "MIT — xem LICENSE." | Viết thành câu đầy đủ: "Nếu bạn muốn thêm một ngôn ngữ mới, hãy làm theo hướng dẫn trong `languages/README.md`." |
| Tự ghép ra thuật ngữ mới | "từ chỉ mức độ chắc chắn", "từ rào đón" | Gọi bằng ví dụ: những từ như "có thể", "có lẽ" |
| Dùng thuật ngữ ngữ pháp với người đọc không chuyên | "hư từ", "tình thái" | Giải thích bằng lời thường hoặc nêu ví dụ |
| Tiêu đề và nhãn dịch từng chữ | "Đầu ra sạch", "Hệ quả cho quy tắc", "nằm ở lõi", "số liệu đứng sau quy tắc" | "Kết quả gọn", "Quy tắc cần điều chỉnh", "dùng cho mọi ngôn ngữ", "số liệu làm căn cứ cho quy tắc" |
| Ô bảng và gạch đầu dòng chỉ là chuỗi cụm từ | "Python 3, chỉ dùng standard library, không gọi mạng." | "Một script Python 3 chỉ dùng standard library và không kết nối mạng." |
| Giải thích cơ chế thay vì nói kết quả | "Cache ghi sau khi response đã gửi. Request thứ hai tới trước thì đọc giá trị cũ." | "Sau khi lưu, người dùng có thể thấy dữ liệu cũ trong vài giây." Nói chuyện gì xảy ra trước. Cơ chế để sau, và chỉ viết khi người đọc cần. |
| Vào thẳng chi tiết khi chưa nói tài liệu bàn về cái gì | Trang mở bằng mục "Khi cache hết hạn thì service làm gì", trong khi người đọc chưa biết cache nào | Câu đầu nêu đối tượng và mục đích: "Service lưu kết quả tìm kiếm vào cache trong 5 phút để giảm tải cho database." |
| Dùng từ nội bộ chưa giải thích | "full sync", "cờ dirty", "có gap", "cờ dirty bật thì sync lại" | Từ nào người đọc chưa gặp thì là từ khó, dù là tiếng Anh hay tiếng Việt. Giải thích một lần ở chỗ dùng đầu tiên, hoặc thay bằng kết quả: "dữ liệu đã đổi thì sync lại". |
| Gọi thành phần bằng tên lấy từ code | Tài liệu gọi bộ phận giới hạn số request là "Gatekeeper", vì class trong code tên là `Gatekeeper` | Gọi bằng tên mà ngành vẫn dùng: "Rate limiting". Nếu cần dẫn về code thì ghi tên code trong ngoặc, "Rate limiting (class `Gatekeeper`)", và chỉ ghi như vậy trong tài liệu nội bộ. |
| Lẫn lịch sử vào tài liệu mô tả | Khung cảnh báo "lỗi này đã xảy ra tuần trước", dòng "Trạng thái ngày 05/03", một mục chữ nhắc lại điều sơ đồ đã thể hiện | Tài liệu mô tả chỉ ghi trạng thái hiện tại. Sự cố và tiến độ thuộc về báo cáo. Điều sơ đồ đã thể hiện thì không viết lại bằng chữ. |
| Tiêu đề không nói phạm vi | "Các bước kiểm tra" | "Các bước kiểm tra khi đăng nhập" |
| Tả một thành phần bằng cách nó chạy, không nói việc nó làm | "Health check: mỗi 30 giây, rất nhẹ. Lỗi 3 lần liền thì restart container." | Câu đầu nói nó làm gì, bằng lời thường: "Health check: phát hiện service bị treo." Tần suất, ngưỡng và cơ chế để sau, và chỉ viết khi người đọc cần. |
| Các mục ngang hàng tả lệch kiểu | Một mục tả bằng cơ chế ("mỗi 30 giây, lỗi 3 lần thì restart"), mục bên cạnh tả bằng thời gian chạy ("chạy khoảng 2 phút mỗi đêm") | Các mục ngang hàng dùng chung một khuôn câu: "Health check: phát hiện service bị treo." và "Backup đêm: sao lưu database." Người đọc so được ngay chỗ khác nhau. |
| Câu tự nói về tài liệu | "Tài liệu này gồm 5 phần.", "Nội dung gồm: …", "(xem mục 4)" | Bỏ câu đó. Trang mục lục chỉ cần danh sách các trang. Khi cần dẫn sang chỗ khác thì gọi tên mục, không gọi số. |

Câu giải thích cơ chế không sai, nhưng nó bắt người đọc tự ghép nhiều mảnh mới hiểu chuyện gì xảy ra. Hãy tự hỏi: người đọc cần biết điều gì để quyết định? Viết điều đó trước. Từ viết tắt tự đặt cũng làm câu khó hơn, nên viết đủ cả từ.

Ba lỗi "từ nội bộ chưa giải thích", "tên lấy từ code" và "từ viết tắt tự đặt" có chung một gốc: người viết dùng từ của mình, không dùng từ của người đọc. Trước khi đặt tên cho một thành phần, hãy tự hỏi người đọc và ngành gọi nó là gì, rồi đối chiếu với chuẩn hoặc tài liệu chính thức của lĩnh vực đó. Tên chuẩn thì người ngoài team hiểu ngay, tra cứu được, và so được với chuẩn họ đang dùng. Tên trong code chỉ có nghĩa với người đã đọc code.

Cách tự kiểm tra: đọc to từng câu rồi tự hỏi "mình có nói câu này với đồng nghiệp không?". Nếu không thì viết lại ý đó đúng như khi nói.

### Gọi tên bằng danh từ, đừng gắn nhãn A, B, C

Khi so sánh nhiều cách làm, AI hay đặt nhãn "Cách A", "Cách B", "Phương án 1", "Phương án 2" rồi dùng nhãn đó suốt tài liệu. Nhãn không cho biết nội dung, nên mỗi lần gặp "Cách B" người đọc phải quay lại chỗ định nghĩa để nhớ đó là cách nào. Tài liệu vì thế vừa loãng vừa khó đọc.

Hãy đặt cho mỗi cách một tên bằng danh từ nói rõ nội dung, rồi dùng đúng tên đó từ đầu đến cuối tài liệu.

| Gắn nhãn | Gọi tên |
|---|---|
| Cách A: lưu session trong Redis. Cách B: dùng JWT. Nên chọn cách B, vì cách A cần thêm một server. | Có hai cách: lưu session trong Redis, hoặc dùng JWT. Nên dùng JWT, vì lưu session trong Redis cần thêm một server. |
| Tiêu đề "Phương án 1", "Phương án 2", "Phương án 3" | Tiêu đề "Tách service", "Giữ monolith và thêm cache", "Viết lại bằng Go" |
| Cột bảng "A", "B", "C1" | Cột bảng "Bài web", "iOS 2020–2022", "iOS 2023–2024" |
| "Ví dụ A", "Ví dụ B" | "Ví dụ: mô tả công cụ", "Ví dụ: thông báo lỗi" |

Khi đặt tên:

- Tên là một cụm danh từ ngắn, lấy từ chính điểm khác nhau giữa các cách.
- Đã đặt tên thì giữ nguyên tên đó. Đừng đổi sang từ gần nghĩa, và đừng rút lại thành chữ cái ở phần sau của tài liệu.
- Tiêu đề, cột bảng và chú thích hình cũng dùng tên đó.
- Các bước phải làm theo thứ tự thì vẫn đánh số bình thường, vì ở đó con số cho biết thứ tự. Mã có sẵn như mã ticket, số phiên bản hay tên biến cũng giữ nguyên.

Linter cảnh báo kiểu gắn nhãn này bằng quy tắc `opaque-label`. Đây là quy ước riêng của bộ quy tắc này: trong bài viết tay, dev Việt vẫn có lúc viết "Cách 1", "Cách 2".

### Viết cho mạch lạc

Văn dịch thường đúng từng câu nhưng rời rạc cả đoạn. Các cách sau giúp đoạn văn mạch lạc hơn:

| Rời rạc | Mạch lạc | Cách làm |
|---|---|---|
| Agent đọc tool description. Agent không thể hỏi lại tác giả. Một câu có hai cách hiểu sẽ dẫn tới hành động sai. | Agent phải tự hiểu tool description mà không có ai để hỏi lại, nên chỉ cần một câu hiểu được hai cách là agent có thể làm sai. | Nối các ý có quan hệ nhân quả. Bỏ chủ ngữ lặp. |
| Hệ thống sẽ kiểm tra token. Sau đó, hệ thống sẽ gửi request. | Hệ thống kiểm tra token rồi gửi request. | Gộp hai hành động liên tiếp của cùng một chủ thể. Bỏ "sẽ" khi không cần nhấn thời gian. |
| Đối với trường hợp mà người dùng chưa đăng nhập, ứng dụng sẽ hiển thị màn hình đăng nhập. | Nếu người dùng chưa đăng nhập thì ứng dụng hiện màn hình đăng nhập. | Thay cụm rườm rà bằng từ nối ngắn. |
| Bạn cần mở file. Bạn cần sửa dòng 3. Bạn cần lưu lại. | Mở file, sửa dòng 3 rồi lưu lại. | Hướng dẫn nhiều bước ngắn: dùng câu mệnh lệnh. |

Quy tắc chung:

- Nối các ý có quan hệ bằng từ nối, đừng cắt mọi câu thành câu cụt. Các phép liên kết của tiếng Việt gồm: nối ("nhưng", "ngoài ra", "vì vậy"), thế ("điều này", "việc đó"), lặp, và lược.
- Chỉ lược chủ ngữ khi người đọc khôi phục được đúng một chủ ngữ từ câu trước. Văn bản trang trọng thì viết đủ thành phần câu.
- Lặp lại thuật ngữ chính xác thay vì đổi sang từ gần nghĩa. Lặp để chính xác không phải là lỗi.
- Giữ "của" khi bỏ đi có thể hiểu sai quan hệ: "góc nhìn của người Pháp", không phải "góc nhìn người Pháp". Bỏ "của" ở quan hệ hiển nhiên: "tên tôi", "cấu hình server".
- Câu dài ngắn xen kẽ. Trong văn viết tay, một nửa số câu ngắn hơn 12–18 âm tiết và 90% số câu ngắn hơn 31 âm tiết. Chỉ tách câu khi câu dài hơn 45 âm tiết hoặc có hai cách hiểu.
- "Hay" theo nghĩa "hoặc" là tự nhiên trong văn cho người đọc: mẫu dùng "hay" nhiều ngang "hoặc". Chỉ ở mức Strict mới phải viết "hoặc".
- Đọc to đoạn văn. Chỗ nào phải ngắt hơi gượng ép hoặc nghe như Google Dịch thì viết lại.

### Xưng hô

- Hướng dẫn: gọi người đọc là "bạn", nhưng không đặt "bạn" ở mọi câu.
- Blog và chia sẻ nội bộ: cả hai blog trong mẫu xưng "mình" và gọi "bạn". "Tôi" rất hiếm.
- Tài liệu chính thức và báo cáo: xưng "chúng tôi" hoặc tên nhóm. Không dùng "quý vị".

## 3. Định dạng

- **Tiêu đề tiếng Việt chỉ viết hoa chữ đầu và tên riêng**: "Tổng quan dự án", không phải "Tổng Quan Dự Án". Title Case là quy ước tiếng Anh. Trong 357 tiêu đề tiếng Việt của văn viết tay, chỉ 2 tiêu đề viết hoa mọi chữ. Style guide của Microsoft và Mozilla đều yêu cầu như vậy, và Nghị định 30/2020/NĐ-CP cũng chỉ viết hoa âm tiết đầu của câu và của tên tác phẩm. Tên cơ quan, tổ chức viết hoa theo quy tắc riêng ("Bộ Tài nguyên và Môi trường").
- **Dấu câu**: không có dấu cách trước `.`, `,`, `:`, `;`, `?`, `!`. Có một dấu cách sau. Không đặt dấu phẩy trước "và", "hoặc" trong chuỗi liệt kê.
- **Ngày tháng**: tài liệu cho người đọc viết ngày trước, tháng sau: `11/11/2026`. Dữ liệu, log và văn bản cho agent dùng ISO 8601 `2026-11-11`.
- **Số**: phân cách hàng nghìn bằng dấu chấm (`1.000.000`), thập phân bằng dấu phẩy (`2,5`) trong văn bản cho người đọc. Với đại lượng đo lường, TCVN 7870-1:2010 khuyên tách nhóm số bằng khoảng trắng nhỏ thay cho dấu chấm. Trong bảng số liệu kỹ thuật, ghi rõ quy ước nếu trộn với dữ liệu từ hệ thống.
- **Đơn vị**: có dấu cách giữa số và đơn vị: `30 giây`, `512 MB`. Không có dấu cách trước `%`: `25%`. Mẫu có 64 lần viết liền và không lần nào viết cách.

## 4. Báo cáo

Báo cáo theo mọi quy tắc ở trên, và thêm một yêu cầu riêng: phải cụ thể. Hướng dẫn đầy đủ nằm trong [`style-reports.md`](style-reports.md), gồm sáu nguyên tắc, bảng tự kiểm tra từng câu và mẫu cho bốn loại báo cáo: tiến độ, sự cố, kết quả kiểm thử hoặc đo hiệu năng, và báo cáo sau khi làm xong một việc.

Tóm tắt sáu nguyên tắc:

- Kết luận lên đầu.
- Con số thay cho tính từ: "xong 9/12 task", không phải "gần xong".
- Rõ người, rõ việc, rõ thời hạn.
- Tách điều đã thấy khỏi điều mình đoán.
- Nói rõ đã kiểm chứng đến đâu: "42/42 unit test pass, chưa chạy UI test".
- Tin xấu cũng phải báo.

## 5. Dùng làm cấu hình cho Claude

Thêm đoạn sau vào `CLAUDE.md` của project. Muốn áp dụng cho mọi project thì thêm vào `~/.claude/CLAUDE.md`:

```markdown
## Viết tài liệu và báo cáo tiếng Việt

Khi viết tài liệu, README, mô tả PR, changelog hoặc báo cáo bằng tiếng Việt,
theo `~/.claude/skills/asd-ste100/languages/vi/style-docs.md`:
- Thuật ngữ: khi nói về kỹ thuật thì dùng tiếng Anh: commit, PR, API, request, token,
  server, database, file, framework, library, build, deploy, test, debug, class,
  variable, function, user, error, permission, default, run, handle (và các thuật ngữ
  kỹ thuật khác). Trong câu thường, từ tiếng Việt cũng được: người dùng, lỗi, chạy, cài đặt.
  Không dùng bản dịch ít người dùng ("yêu cầu kéo", "điểm cuối", "mã thông báo").
- Tiêu đề chỉ viết hoa chữ đầu. Câu chủ động. Không dùng "được ... bởi".
- Viết tự nhiên như kỹ sư Việt viết: nối ý bằng từ nối ("nên", "vì", "rồi"),
  chỉ lược chủ ngữ khi không thể hiểu nhầm, câu dài ngắn xen kẽ. Không cắt mọi câu thành câu cụt.
- Không gắn nhãn chữ cái hoặc số cho các cách làm, phương án, nhóm, ví dụ ("Cách A", "Phương án 2").
  Đặt cho mỗi thứ một tên bằng danh từ nói rõ nội dung ("cách dùng JWT") và dùng đúng tên đó
  trong cả tài liệu. Chỉ đánh số các bước phải làm theo thứ tự.
- Nói kết quả hoặc hậu quả trước, cơ chế để sau và chỉ viết khi người đọc cần.
  Không dùng từ viết tắt tự đặt.
- Không viết câu tự mô tả tài liệu ("Tài liệu này gồm...", "Nội dung gồm:", "xem mục 4").
- Câu đầu của tài liệu nói nó bàn về cái gì và để làm gì. Tiêu đề nói rõ phạm vi.
  Tả mỗi thành phần bằng việc nó làm trước, cách nó chạy để sau. Các mục ngang hàng dùng chung một khuôn câu.
  Tài liệu mô tả chỉ ghi trạng thái hiện tại: sự cố và tiến độ đưa vào báo cáo.
- Viết cho người không chuyên (PM, QA, bên kiểm định): tả kết quả bằng lời thường,
  giải thích mỗi thuật ngữ và từ nội bộ ở lần dùng đầu tiên.
- Gọi mỗi thành phần bằng tên mà người đọc và ngành vẫn dùng, đối chiếu với chuẩn của lĩnh vực.
  Không lấy tên class hay function làm tên trong tài liệu. Cần dẫn về code thì ghi tên code
  trong ngoặc, và chỉ ở tài liệu nội bộ.
- Bảng ưu nhược điểm: nhược điểm là hậu quả xấu cho người dùng hoặc hệ thống, không phải công sức
  làm thêm. Không có thì ghi "Không có". Đối chiếu code hoặc số đo trước khi ghi mỗi ô.
- Báo cáo: theo `style-reports.md` cùng thư mục. Kết luận lên đầu, con số thay cho tính từ,
  mỗi việc có người phụ trách và ngày cụ thể. Khi báo "đã xong", nói rõ đã kiểm chứng bằng
  cách nào, phần nào chưa kiểm chứng và bước nào đã bỏ qua.
- Không áp dụng cho chuỗi giao diện app: app có quy ước riêng.
```

Kiểm tra bằng linter:

```bash
python3 scripts/ste-lint.py --lang vi --profile docs docs/
python3 scripts/ste-lint.py --lang vi --profile report bao-cao.md
```

Profile `docs` nới giới hạn độ dài câu lên 45 âm tiết và không cảnh báo "hay". Đừng dùng profile default (`strict`) cho tài liệu, vì nó sẽ đẩy bạn về lối câu cụt.

Các quy tắc liên quan: `calque-term`, `mt-phrase`, `title-case-heading`, `passive-voice`, `adverb-calque` (đều ở mức advisory).

## Nguồn tham khảo

**Cách dev Việt dùng thuật ngữ**

- [`evidence.md`](evidence.md): số liệu từ 156 bài của hai blog lập trình tiếng Việt, gồm 102 bài viết tay và 54 bài đối chứng.
- [Viblo — tìm "pull request"](https://viblo.asia/search?q=pull%20request) · [ITviec — GitOps là gì](https://itviec.com/blog/gitops-la-gi/)
- Tường Minh, ["Lạm dụng tiếng Anh"](https://vnexpress.net/lam-dung-tieng-anh-4373194.html), VnExpress, 2021. Bài này nêu chiều ngược lại: từ nào tiếng Việt diễn tả được chính xác thì nên dùng tiếng Việt.

**Thuật ngữ và quy ước của các hãng**

- [Microsoft Vietnamese Localization Style Guide](https://download.microsoft.com/download/b/f/e/bfecb1b4-21ab-48fd-a48c-c2471b026f8f/vie-vnm-StyleGuide.pdf): chỉ viết hoa chữ đầu, xưng hô "bạn", không dấu cách trước dấu câu và `%`, không dấu phẩy trước "và".
- [Microsoft Terminology Collection](https://learn.microsoft.com/en-us/globalization/reference/microsoft-terminology): điểm cuối, mã thông báo, yêu cầu kéo, phần mềm trung gian, tải trọng, bộ đệm ẩn.
- [Mozilla — Vietnamese Style Guide](https://wiki.mozilla.org/L10n:Teams:vi/Style_Guide): "Tránh Viết Hoa Kiểu Title Tiếng Anh", chuyển câu bị động thành chủ động.
- Các trang tiếng Việt của Microsoft Learn và Google Developers là bản dịch máy (chính các trang đó ghi rõ), nên không dùng làm bằng chứng cho cách viết tự nhiên.

**Câu văn tiếng Việt**

- Cao Xuân Hạo, "Linh hồn tiếng Việt", 2001 ([bản đăng lại](https://cavenui.wordpress.com/2007/10/20/cao-xuan-h%E1%BA%A1o/)): câu Việt theo cấu trúc đề–thuyết, "bàn chưa lau sạch" thay cho "bàn bị lau chưa sạch".
- Đỗ Lan Anh, ["Vấn đề giao thoa trong dịch thuật Pháp–Việt"](https://js.vnu.edu.vn/FS/article/view/2000/1902), Tạp chí Khoa học ĐHQGHN, 2016: bỏ "bởi", đổi cụm danh từ thành mệnh đề, đặt trạng ngữ thời gian lên đầu.
- Nguyễn Văn Khang, dẫn trong ["Tiếng Việt đang bị dùng dễ dãi, thiếu chuẩn mực"](https://vietnamnet.vn/tieng-viet-dang-bi-dung-de-dai-thieu-chuan-muc-338087.html), VietNamNet, 2016: "làm bởi", "đến từ".
- Minh Khải, ["Chữ và nghĩa báo chí"](https://congly.vn/chu-va-nghia-bao-chi-51113.html), Công Lý, 2019: "được viết bởi", "cảm ơn sự quan tâm", bỏ "của" sai chỗ.
- Đặng Đình Cung, ["Chó treo mèo đậy"](https://vnexpress.net/cho-treo-meo-day-4759651.html), VnExpress, 2024: "là một giáo viên", "những phụ nữ", "nhận được sự cho phép".
- ["Vật thể lạ"](https://tapchicongthuong.vn/vat-the-la-35212.htm), Tạp chí Công Thương, 2014: "nó" dịch từ "it".
- Nguyễn Thị Thu Hà, [Bài giảng Tiếng Việt thực hành](https://docs.hoeit.edu.vn/NGONNGUANH_21/NGUYENTHITHUHA/baigiangtvthuchanh.pdf): lỗi thiếu chủ ngữ, cặp từ nối, các phép liên kết câu.
- Đỗ Thị Thanh Nga, ["Những yêu cầu khi sử dụng từ Hán Việt trong văn bản quản lí nhà nước"](https://vjol.info.vn/index.php/ngonngu/article/download/18885/16688/), Ngôn ngữ, 2012: từ thừa ("hoàn thành xong", "tối ưu nhất").

**Định dạng**

- Nghị định 30/2020/NĐ-CP, Phụ lục II ([tóm tắt](https://luatvietnam.vn/hanh-chinh/cac-truong-hop-phai-viet-hoa-theo-nghi-dinh-30-570-24161-article.html)): quy tắc viết hoa.
- CLDR `vi`: [numbers](https://raw.githubusercontent.com/unicode-org/cldr-json/main/cldr-json/cldr-numbers-full/main/vi/numbers.json), [dates](https://raw.githubusercontent.com/unicode-org/cldr-json/main/cldr-json/cldr-dates-full/main/vi/ca-gregorian.json).
- [TCVN 7870-1:2010 (ISO 80000-1)](https://caselaw.vn/van-ban-phap-luat/252813-tieu-chuan-quoc-gia-tcvn-7870-1-2010-iso-80000-1-2009-ve-dai-luong-va-don-vi-phan-1-quy-dinh-chung-nam-2010): tách nhóm số bằng khoảng trắng cho đại lượng.

Các nguồn về ngữ pháp tiếng Việt (bị/được, đặt dấu thanh, tỷ lệ độ dài câu) nằm trong [`rules.md`](rules.md#nguồn-tham-khảo).
