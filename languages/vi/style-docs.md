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

## 1. Thuật ngữ: viết như dev Việt viết

Phần này dựa trên 102 bài viết tay của hai blog lập trình tiếng Việt. Số liệu đầy đủ và cách đếm nằm trong [`evidence.md`](evidence.md). Đây là văn blog của hai tác giả, nên hãy coi các bảng dưới đây là mặc định hợp lý chứ không phải chuẩn. Nếu nhóm bạn đã có bảng thuật ngữ riêng thì theo bảng đó.

Số trong ngoặc là số bài có dùng từ đó, trên tổng 102 bài.

### Giữ tiếng Anh

| Viết | Ít gặp hoặc không gặp |
|---|---|
| file (41) | tệp (0), tập tin (0) |
| server (24) | máy chủ (2) |
| database (21) | cơ sở dữ liệu (3) |
| framework (24) | khung (5) |
| code (90) | mã nguồn (2) |
| debug (14) | gỡ lỗi (0) |
| module (12) | mô-đun (0) |
| log (8) | nhật ký (0) |
| build (26), API (29), callback (7), link (26), upload (7), performance (12) | |

Thuật ngữ Git (commit, branch, merge, pull request, repo) và endpoint, token, middleware, payload có quá ít dữ liệu trong mẫu. Nên giữ tiếng Anh cho các từ này, vì bản dịch của các hãng không thống nhất (xem bên dưới).

### Viết tiếng Việt

| Viết | Ít gặp |
|---|---|
| biến (45) | variable (0) |
| thư viện (30) | library (6) |
| người dùng (35) | user (8) |
| hệ thống (39) | system (5) |
| giao diện (29) | interface (2) |
| cài, cài đặt (36) | install (1) |
| chạy (62) | run (9) |
| xử lý (31) | handle (4) |
| hỗ trợ (25) | support (2) |
| khai báo (21), định nghĩa (14) | define (4) |
| lỗi (31) | error (7) |
| sửa (34) | fix (13) |
| chức năng (25), tính năng (13) | feature (1) |
| mặc định (15), quyền (16), mạng (25), bảo mật (10), thuật toán (11), trình duyệt (8) | |

### Cả hai cách đều phổ biến

| Tiếng Anh | Tiếng Việt |
|---|---|
| function (28) | hàm (39) |
| class (27) | lớp (11) |
| object (15) | đối tượng (27) |
| method (10) | phương thức (10) |
| property (13) | thuộc tính (15) |
| array (15), string (16) | mảng (8), chuỗi (7) |
| data (19) | dữ liệu (48) |
| project (38) | dự án (36) |
| app (31) | ứng dụng (44) |
| version (15) | phiên bản (11) |
| developer (39), dev (27) | lập trình viên (25) |
| team (31) | nhóm (15) |
| test (26) | kiểm tra (17), kiểm thử (3) |
| deploy (14) | triển khai (7) |
| bug (13) | lỗi (31) |
| config (8), tool (12) | cấu hình (9), công cụ (14) |
| update (11), design (15) | cập nhật (20), thiết kế (27) |

Với nhóm này, chọn một cách cho mỗi khái niệm rồi giữ trong cả tài liệu.

### Từ có trong bảng thuật ngữ của các hãng nhưng dev ít dùng

**Từ Việt chuẩn, dùng trong giao diện sản phẩm và văn bản trang trọng:** tệp, máy chủ, cơ sở dữ liệu, kiểm thử, gỡ lỗi, mã nguồn. Các từ này đúng và dễ hiểu. Hãy dùng khi người đọc không phải dev (khách hàng, lãnh đạo), hoặc khi nhóm bạn đã quen. Trong 102 bài viết tay, mỗi từ chỉ xuất hiện ở 0–3 bài.

**Bản dịch ít người dùng:** yêu cầu kéo (pull request), cam kết (commit), điểm cuối (endpoint), mã thông báo (token), gọi lại (callback), khuôn khổ hoặc khung (framework), phần mềm trung gian (middleware), tải trọng (payload). Các từ này không sai: phần lớn là thuật ngữ chính thức trong bảng thuật ngữ của Microsoft. Nhưng dev không quen, và các hãng dịch không thống nhất. Cache là "bộ đệm ẩn" ở Microsoft nhưng "bộ nhớ đệm" ở Apple. Framework là "khuôn khổ" ở Microsoft nhưng "khung" ở Google. "Cam kết" của Microsoft là commit của giao dịch cơ sở dữ liệu, không phải commit của Git.

Nếu bạn viết chuỗi giao diện cho một sản phẩm đã bản địa hóa, hãy theo bảng thuật ngữ của nền tảng đó, không theo phần này.

### Cách viết thuật ngữ tiếng Anh

- Viết thường giữa câu như danh từ chung: "tạo một branch mới", "deploy lên server". Viết hoa tên riêng (GitHub, Swift), từ viết tắt (API, PR) và tên thành phần ("Cache Server").
- Không thêm đuôi số nhiều: "các function", "hai pull request", "44 test". Hơn 90% trường hợp trong mẫu viết như vậy.
- Tên hàm, biến, lệnh, đường dẫn: đặt trong backtick, không dịch.
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
| Thư viện này được sử dụng để xử lý ảnh. | Thư viện này dùng để xử lý ảnh. |
| Tính năng này cho phép bạn xuất PDF. | Bạn có thể xuất PDF bằng tính năng này. |
| Cache đóng một vai trò quan trọng trong hiệu năng. | Cache ảnh hưởng lớn tới hiệu năng. |
| Hàm này trả về giá trị một cách nhanh chóng. | Hàm này trả về giá trị nhanh. |

"Một cách + tính từ" không sai, và các nhà nghiên cứu vẫn dùng. Chỉ bỏ khi câu không đổi nghĩa.

Các cụm này có trong văn viết tay, nhưng hiếm. Ở nhóm bài đối chứng trong [`evidence.md`](evidence.md), chúng xuất hiện nhiều gấp 2–30 lần, cùng với tiêu đề viết hoa mọi chữ và số viết kiểu "1,000". Một văn bản dày đặc các cụm này sẽ đọc lên như bản dịch máy.

### Những chỗ gượng hay gặp khi AI viết tiếng Việt

Các lỗi dưới đây đều do người đọc thật chỉ ra trong chính tài liệu của repo này. Từng chữ trong câu đều đúng, nhưng người Việt không nói như vậy. Linter chỉ bắt được hai kiểu đầu, nên sau khi viết xong hãy tự đọc lại theo bảng này.

| Kiểu gượng | Ví dụ | Viết lại |
|---|---|---|
| Dịch sát một câu nói gọn của tiếng Anh | "văn bản mà giọng văn là mục đích", "Mức độ chắc chắn là nội dung", "…là chìa khóa" | Nói ý đó bằng lời bình thường: "những văn bản cần giọng văn riêng", "bỏ chữ 'có thể' là đổi nghĩa câu" |
| Câu cụt kiểu ghi chú | "Muốn thêm một ngôn ngữ? Xem `languages/README.md`.", "MIT — xem LICENSE." | Viết thành câu đầy đủ: "Nếu bạn muốn thêm một ngôn ngữ mới, hãy làm theo hướng dẫn trong `languages/README.md`." |
| Tự ghép ra thuật ngữ mới | "từ chỉ mức độ chắc chắn", "từ rào đón" | Gọi bằng ví dụ: những từ như "có thể", "có lẽ" |
| Dùng thuật ngữ ngữ pháp với người đọc không chuyên | "hư từ", "tình thái" | Giải thích bằng lời thường hoặc nêu ví dụ |
| Tiêu đề và nhãn dịch từng chữ | "Đầu ra sạch", "Hệ quả cho quy tắc", "nằm ở lõi", "số liệu đứng sau quy tắc" | "Kết quả gọn", "Quy tắc cần điều chỉnh", "dùng cho mọi ngôn ngữ", "số liệu làm căn cứ cho quy tắc" |
| Ô bảng và gạch đầu dòng chỉ là chuỗi cụm từ | "Python 3, chỉ dùng thư viện chuẩn, không gọi mạng." | "Một script Python 3 chỉ dùng thư viện chuẩn và không kết nối mạng." |

Cách tự kiểm tra: đọc to từng câu rồi tự hỏi "mình có nói câu này với đồng nghiệp không?". Nếu không thì viết lại ý đó đúng như khi nói.

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

- **Tiêu đề tiếng Việt chỉ viết hoa chữ đầu và tên riêng**: "Tổng quan dự án", không phải "Tổng Quan Dự Án". Title Case là quy ước tiếng Anh. Trong 357 tiêu đề tiếng Việt của văn viết tay, chỉ 1 tiêu đề viết hoa mọi chữ. Style guide của Microsoft và Mozilla đều yêu cầu như vậy, và Nghị định 30/2020/NĐ-CP cũng chỉ viết hoa âm tiết đầu của câu và của tên tác phẩm. Tên cơ quan, tổ chức viết hoa theo quy tắc riêng ("Bộ Tài nguyên và Môi trường").
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
- Thuật ngữ: viết như dev Việt viết. Giữ tiếng Anh cho commit, PR, API, request, token,
  server, database, file, framework, build, debug, code. Viết tiếng Việt cho biến,
  thư viện, người dùng, giao diện, hệ thống, lỗi, cài đặt, xử lý, chức năng, bảo mật.
  Không dùng bản dịch ít người dùng ("yêu cầu kéo", "điểm cuối", "mã thông báo").
- Tiêu đề chỉ viết hoa chữ đầu. Câu chủ động. Không dùng "được ... bởi".
- Viết tự nhiên như kỹ sư Việt viết: nối ý bằng từ nối ("nên", "vì", "rồi"),
  chỉ lược chủ ngữ khi không thể hiểu nhầm, câu dài ngắn xen kẽ. Không cắt mọi câu thành câu cụt.
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

Profile `docs` nới giới hạn độ dài câu lên 45 âm tiết và không cảnh báo "hay". Đừng dùng profile mặc định (`strict`) cho tài liệu, vì nó sẽ đẩy bạn về lối câu cụt.

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
