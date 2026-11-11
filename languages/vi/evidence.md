# Bằng chứng: dev Việt viết thế nào

Tài liệu này ghi lại số liệu làm căn cứ cho các quy tắc trong `style-docs.md` và các mức cảnh báo của linter. Nhờ vậy ai cũng kiểm chứng được từng quy tắc, và sửa lại khi có dữ liệu tốt hơn.

Một người rà soát độc lập đã chạy lại toàn bộ phép đếm và đọc từng lần xuất hiện của các từ nhiều nghĩa. Bản này đã sửa theo kết quả rà soát đó.

## Ngữ liệu

156 bài viết của hai blog lập trình tiếng Việt, khoảng 194 nghìn âm tiết và 11.400 câu.

| Nhóm | Nguồn | Số bài | Âm tiết | Vai trò |
|---|---|---|---|---|
| A | Blog thứ nhất: chia sẻ về nghề lập trình và web, 2015–2026 | 73 | 69 nghìn | Văn viết tay |
| B | Blog thứ hai, bài 2020–2022: hướng dẫn lập trình iOS | 29 | 43 nghìn | Văn viết tay |
| C1 | Blog thứ hai, bài 2023–2024: vẫn là hướng dẫn iOS | 18 | 30 nghìn | Đối chứng |
| C2 | Blog thứ hai, bài 2025–2026: phần lớn là bài luận về AI | 36 | 51 nghìn | Đối chứng |

Nhóm A có 10–11 bài mỗi năm cho giai đoạn 2015–2021 và 2 bài mỗi năm cho 2024–2026. Blog này không có bài nào trong hai năm 2022–2023.

Hai nhóm C được tách riêng vì văn phong khác hẳn nhóm B của cùng tác giả (xem mục "Dấu hiệu của văn giống máy dịch"). Nguyên nhân chưa được kiểm chứng, nên tài liệu này chỉ mô tả sự khác biệt và không kết luận về cách các bài đó được viết.

**Cách đếm:**

- Tên hai blog không được nêu ở đây. Bài được lấy từ trang gốc hoặc từ bản lưu trữ công khai của trang.
- Chỉ đếm văn xuôi trong thân bài. Những phần sau đã bị loại: khối code, code viết liền trong câu, mục lục, bình luận, các đoạn ngắn hơn 6 âm tiết, và các đoạn lặp lại ở từ 4 bài trở lên (thẻ, bài liên quan, lời chào cuối bài).
- "Số bài" là số bài có dùng từ đó ít nhất một lần. Số trong ngoặc là tổng số lần xuất hiện.

**Giới hạn:**

- Đây là văn blog của hai tác giả. Tài liệu nội bộ của công ty có thể trang trọng hơn.
- Nhiều dòng trong bảng thuật ngữ gần như chỉ dựa vào một tác giả. Ví dụ "server", "database", "debug", "module", "performance", "team" chủ yếu đến từ nhóm A, còn "khai báo", "định nghĩa" chủ yếu đến từ nhóm B.
- Từ nhiều nghĩa bị máy đếm lẫn nghĩa. Với các dòng có ghi "đã đọc từng chỗ", con số là số lần dùng đúng nghĩa đang xét. Các dòng khác là số đếm thô.
- Số đếm của từ tiếng Anh gồm cả tên kiểu dữ liệu và tiêu đề tiếng Anh, ví dụ `String`, `Task`, "Fetching Data from API".
- Thuật ngữ Git (commit, branch, merge, pull request, repo) xuất hiện ở dưới 5 bài, nên chưa đủ dữ liệu để kết luận.
- Hai nhóm C khác nhóm B cả về chủ đề lẫn văn phong. Riêng C1 có cùng chủ đề với B, nên chỉ ở C1 mới so sánh được văn phong một cách sạch.

## Thuật ngữ

Các bảng dưới đây tính trên 102 bài viết tay (nhóm A và B). Một cách viết được coi là chiếm ưu thế rõ khi nó có mặt ở ít nhất 10 bài và nhiều gấp 3 lần cách viết kia.

### Tiếng Anh chiếm ưu thế rõ

| Khái niệm | Số bài (số lần) | Ghi chú |
|---|---|---|
| file | file 41 (219) · tệp 0 | |
| server | server 24 (108) · máy chủ 2 (2) | |
| database | database 21 (39) · cơ sở dữ liệu 3 (4) | |
| framework | framework 24 (56) · khung 0–1 | "Khung" có ở 5 bài nhưng gần như không mang nghĩa framework |
| code | code 90 (787) · mã nguồn 2 (3) | |
| debug | debug 14 (25) · gỡ lỗi 0 | |
| build | build 26 (63) | |
| API | API 29 (87) | |
| module | module 12 (28) · mô-đun 0 | |
| link | link 26 (48) · liên kết 0 | "Liên kết" có ở 7 bài nhưng không lần nào nghĩa là đường link |
| performance | performance 12 (13) · hiệu năng 2 · hiệu suất 2 | |
| deploy | deploy 14 (28) · triển khai 0 | Đã đọc từng chỗ: "triển khai" có ở 7 bài, đều mang nghĩa "implement" |
| class | class 27 (137) · lớp 5 (10) | Đã đọc từng chỗ: 19 trong 29 lần "lớp" là lớp học, lớp trừu tượng, lớp bản đồ |
| test | test 26 (89) · kiểm thử 3 (4) | "Kiểm tra" có ở 17 bài nhưng gần như luôn nghĩa là "check" |
| team | team 31 (81) · nhóm khoảng 6 | Đã đọc từng chỗ: phần lớn "nhóm" là "nhóm toán tử" |
| array | array 15 (35) · mảng 3 (7) | Đã đọc từng chỗ: một nửa số lần "mảng" nghĩa là lĩnh vực |

### Tiếng Việt chiếm ưu thế rõ

| Khái niệm | Số bài (số lần) | Ghi chú |
|---|---|---|
| variable | biến khoảng 22 (60) · variable 0 | Đã trừ "phổ biến", "biến đổi" |
| library | thư viện 30 (62) · library 6 (7) | |
| user | người dùng 35 (93) · user 8 (10) | |
| system | hệ thống 39 (161) · system 5 (5) | |
| install | cài đặt 28 (66) · install 1 | |
| run | chạy 62 (230) · run 9 (15) | |
| handle | xử lý 31 (75) · handle 4 (4) | |
| support | hỗ trợ 25 (45) · support 2 (3) | |
| define | khai báo 21 (95) · định nghĩa 14 (30) · define 4 (7) | |
| error | lỗi 31 (100) · error 7 (29) | |
| feature | chức năng 25 (44) · tính năng 13 (23) · feature 1 | |
| default | mặc định 15 (19) · default 2 | |
| permission | quyền 16 (33) · permission 1 | |
| algorithm | thuật toán 11 (51) | |

### Cả hai cách đều phổ biến

| Khái niệm | Số bài (số lần) | Ghi chú |
|---|---|---|
| function | function 28 (155) · hàm 39 (134) | Đã đọc từng chỗ: 39 trong 40 lần "hàm" đúng nghĩa |
| object | object 15 (60) · đối tượng 27 (148) | |
| method | method 10 (16) · phương thức 10 (15) | |
| property | property 13 (32) · thuộc tính 15 (99) | |
| string | string 16 (34) · chuỗi 7 (12) | |
| data | data 19 (56) · dữ liệu 48 (374) | |
| UI | UI 18 (51) · giao diện 29 (85) | |
| project | project 38 (108) · dự án 36 (105) | |
| app | app 31 (108) · ứng dụng 44 (142) | |
| version | version 15 (17) · phiên bản 11 (20) | Đã đọc từng chỗ: 32 trong 35 lần "phiên bản" đúng nghĩa |
| developer | developer 39 (117) · dev 27 (64) · lập trình viên 25 (46) | |
| bug | bug 13 (26) · lỗi 31 (100) | |
| fix | fix 13 (19) · sửa 27 | Đã trừ "chỉnh sửa", "sửa chữa" |
| config | config 8 (11) · cấu hình 9 (17) | |
| tool | tool 12 (30) · công cụ 14 (21) | |
| update | update 11 (22) · cập nhật 20 (51) | |
| design | design 15 (33) · thiết kế 27 (51) | |
| task | task 10 (74) · nhiệm vụ 7 (11) | |
| service | service 14 (26) · dịch vụ 10 (18) | |
| document | document 10 (21) · tài liệu 8 (16) | |
| model | model 13 (25) · mô hình 14 (30) | |
| security | security 4 (6) · bảo mật 10 (38) | |

### Bản dịch của các hãng

Không bài viết tay nào dùng "tệp", "tập tin", "gỡ lỗi", "mô-đun", "nhật ký" (theo nghĩa log), "bộ nhớ đệm", "mã thông báo", "điểm cuối" hay "yêu cầu kéo". "Máy chủ", "cơ sở dữ liệu", "kiểm thử" và "mã nguồn" mỗi từ có ở 2–3 bài trong 102 bài.

Trong các bài cùng chủ đề của cùng tác giả, "mã nguồn" tăng từ 2 trong 29 bài (nhóm B) lên 6 trong 18 bài (nhóm C1). Các từ khác không so sánh được, vì chủ đề của nhóm C2 khác hẳn.

## Dấu hiệu của văn giống máy dịch

Các kiểu câu dưới đây hiếm trong văn viết tay và nhiều hơn hẳn ở hai nhóm đối chứng. Đơn vị là số lần trên 1000 âm tiết, trừ khi ghi khác.

| Dấu hiệu | A | B | C1 | C2 |
|---|---|---|---|---|
| "được sử dụng để" | 0,01 | 0,05 | 0,86 | 0,02 |
| "cho phép bạn / chúng ta" | 0,15 | 0,05 | 1,36 | 0,02 |
| "là một + danh từ" | 1,48 | 2,65 | 5,75 | 2,70 |
| "một cách + từ" | 0,17 | 0,55 | 1,20 | 0,98 |
| "được / bị … bởi" | 0,15 | 0,12 | 0,43 | 0,31 |
| ", và" | 0,60 | 0,09 | 1,03 | 2,03 |
| "đóng vai trò" | 0,03 | 0,05 | 0,07 | 0,20 |
| Tiêu đề tiếng Việt viết hoa mọi chữ (ít nhất) | 2 trong 242 | 0 trong 115 | 0 trong 82 | 88 trong 370 |
| Số viết kiểu Anh "1,000" (số lần) | 0 | 0 | 0 | 6 |
| "hóa" (kiểu cũ) so với "hoá" (kiểu mới), số lần | 50 so với 65 | 17 so với 82 | 55 so với 1 | 155 so với 0 |
| "nhé", "nha" | 4,32 | 1,02 | 0,80 | 0,08 |
| "mình" | 13,88 | 3,87 | 2,89 | 0,92 |
| Câu dài hơn 30 âm tiết | 10,7% | 1,3% | 5,5% | 14,4% |

Hai nhóm đối chứng khác văn viết tay theo hai kiểu:

- **C1** cùng chủ đề với B nhưng dùng "được sử dụng để" nhiều gấp 17 lần, "cho phép bạn" nhiều gấp hơn 25 lần, và "là một" nhiều gấp đôi. Các cụm này tập trung ở một số bài: 3 bài chứa hơn một nửa số lần xuất hiện.
- **C2** gần như không dùng hai cụm trên. Điểm khác của nhóm này là tiêu đề viết hoa mọi chữ, dấu phẩy trước "và", số viết kiểu Anh, và câu dài. Chủ đề và thể loại của C2 cũng khác, nên không tách được phần nào là do văn phong.

Về các con số trong bảng:

- Phép đếm tiêu đề chỉ bắt những tiêu đề mà mọi từ đều viết hoa, nên con số là mức tối thiểu. Một phép đếm lỏng hơn (ít nhất 70% số từ viết hoa) cho 187 trong 370 tiêu đề ở C2 và 4 trong 357 ở văn viết tay.
- Ở nhóm A, 28 trong 41 lần ", và" nằm trong 6 bài viết năm 2024–2026.
- Linter dùng các dấu hiệu này cho những quy tắc `mt-phrase`, `adverb-calque`, `passive-voice`, `number-format` và `title-case-heading`. Tất cả đều ở mức cảnh báo, vì văn viết tay vẫn dùng chúng, chỉ là ít hơn nhiều.

## Kiểu câu trong văn viết tay

Số lần trên 1000 âm tiết. Các dòng này đếm mọi nghĩa của từ.

| Kiểu câu | A | B | Nhận xét |
|---|---|---|---|
| "tiến hành" | 0 | 0,81 | Tác giả nhóm B dùng trong các bước hướng dẫn: "Tiến hành kéo thả giao diện". Vì vậy linter chỉ cảnh báo. |
| "thực hiện việc" | 0 | 0,16 | Như trên. |
| "đến từ" | 0 | 0,12 | Hiếm. |
| "việc + từ" | 3,40 | 7,12 | Rất phổ biến, nên không có quy tắc nào cấm. |
| "hay" (trừ "hay không") | 3,48 | 2,86 | Nhiều ngang "hoặc" (3,09 và 2,01). Profile `docs` không cảnh báo "hay". |
| Dấu chấm phẩy | 0,67 (30 trong 73 bài) | 0 | Profile `docs` chỉ cảnh báo. |

**Số nhiều của từ tiếng Anh:** hơn 90% trường hợp không thêm đuôi -s: "các function". Phép đếm tự động còn lẫn những từ vốn kết thúc bằng s như "class", nên tỷ lệ thật cao hơn, khoảng 95–98%.

**Từ nối:**

| Từ nối | A | B |
|---|---|---|
| thì | 5,3 | 12,5 |
| nên | 4,3 | 1,9 |
| mà | 4,1 | 4,2 |
| nhưng | 2,7 | 1,9 |
| còn | 2,5 | 2,1 |
| vì | 2,4 | 2,2 |
| rồi | 2,3 | 2,1 |
| nếu … thì | 1,0 | 2,4 |
| tuy nhiên | 0,9 | 0,7 |
| do đó | 0,6 | 0,5 |

**Xưng hô:** nhóm A xưng "mình" (13,9) và gọi "bạn" (13,6). Nhóm B gọi "bạn" (22,5), dùng "chúng ta" (5,6) và "mình" (3,9). "Tôi" hiếm ở cả hai (0,6 và 0,07).

## Độ dài câu

Tính theo âm tiết.

| Nhóm | Số câu | Trung vị | 90% câu ngắn hơn | Dài hơn 30 | Dài hơn 45 |
|---|---|---|---|---|---|
| A | 3.584 | 18 | 31 | 10,7% | 0,8% |
| B | 3.269 | 12 | 21 | 1,3% | 0,1% |
| C1 | 1.866 | 14 | 26 | 5,5% | 0,6% |
| C2 | 2.707 | 17 | 34 | 14,4% | 2,3% |

Chưa tới 1% số câu viết tay dài hơn 45 âm tiết, là giới hạn của profile `docs`. Giới hạn 30 âm tiết của mức Strict chặn khoảng 11% số câu ở nhóm A và 1% ở nhóm B. Điều đó hợp lý, vì văn bản cho agent đọc cần ngắn hơn văn blog.

## Định dạng

- **Phần trăm:** trong cả ngữ liệu, kiểu "25%" xuất hiện 64 lần, kiểu "25 %" không lần nào.
- **Nhóm số:** văn viết tay dùng dấu chấm ("650.000", "10.000", 4 lần) và không dùng dấu phẩy. Nhóm C2 dùng dấu phẩy 6 lần và dấu chấm 3 lần.
- **Dấu thanh:** văn viết tay dùng cả hai kiểu, "hoá" 147 lần và "hóa" 67 lần. Hai nhóm C gần như chỉ dùng "hóa".

## Từ dùng trong báo cáo

Số bài có dùng từng cụm, trong 108 bài viết tay và 55 bài đối chứng. Phép đếm này dùng toàn bộ file đã tải, nên số bài nhiều hơn các bảng trên một chút.

| Cụm | Viết tay | Đối chứng |
|---|---|---|
| cơ bản hoàn thành, đang triển khai, trong thời gian tới, đẩy mạnh, quyết liệt | 0 | 0 |
| về cơ bản | 1 | 1 |
| tích cực | 1 | 1 |
| kịp thời | 1 | 1 |
| đáng kể | 1 | 7 |
| một số | 53 | 28 |
| khá nhiều | 27 | 3 |
| rất nhiều | 48 | 6 |
| gần đây | 11 | 4 |

Nhóm trên cùng là lối văn báo cáo hành chính. Văn viết tay gần như không dùng, nên linter cảnh báo ở mọi profile (`officialese`). Các từ chỉ lượng như "một số" thì rất phổ biến trong văn thường, nên linter chỉ cảnh báo khi chạy `--profile report`. Bảng này chưa được người rà soát độc lập kiểm tra lại.

## Linter trên văn viết tay

Chạy `--lang vi --profile docs` trên văn xuôi của 102 bài viết tay. Lỗi mức hard còn lại:

| Quy tắc | Số lần | Ghi chú |
|---|---|---|
| `long-sentence` | 33 | Câu dài hơn 45 âm tiết, khoảng 0,5% số câu |
| `synonym-rotation` | 2 | Một bài dùng lẫn "xoá" với từ cùng nhóm, và "chỉnh sửa" với "sửa đổi" |
| `semicolon` | 1 | Một dòng không có chữ cái riêng của tiếng Việt, nên linter không nhận ra đó là dòng tiếng Việt |

Trước khi có số liệu này, quy tắc `nominalization` báo 52 lỗi hard trên cùng các bài đó, cho các cụm "tiến hành", "thực hiện việc" và "có sự". Quy tắc từ quảng cáo báo 8 lỗi hard cho các từ như "mượt mà", "liền mạch", "vượt trội". Dấu chấm phẩy xuất hiện 46 lần và cũng từng là lỗi hard.
