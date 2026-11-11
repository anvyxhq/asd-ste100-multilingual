# Bằng chứng: dev Việt viết thế nào

Tài liệu này ghi lại số liệu làm căn cứ cho các quy tắc trong `style-docs.md` và các mức cảnh báo của linter. Nhờ vậy ai cũng kiểm chứng được từng quy tắc, và sửa lại khi có dữ liệu tốt hơn.

## Ngữ liệu

156 bài viết của hai blog lập trình tiếng Việt, khoảng 194 nghìn âm tiết và 11.400 câu.

| Nhóm | Nguồn | Số bài | Âm tiết | Vai trò |
|---|---|---|---|---|
| A | Blog thứ nhất: chia sẻ về nghề lập trình và web, 2015–2026, lấy mẫu đều theo năm | 73 | 69 nghìn | Văn viết tay |
| B | Blog thứ hai, bài 2020–2022: hướng dẫn lập trình iOS | 29 | 43 nghìn | Văn viết tay |
| C | Blog thứ hai, bài 2023–2026: phần lớn về AI và prompt | 54 | 81 nghìn | Nhóm đối chứng |

Nhóm C được tách riêng vì văn phong khác hẳn nhóm B của cùng tác giả (xem mục "Dấu hiệu của văn giống máy dịch"). Nguyên nhân chưa được kiểm chứng, nên tài liệu này chỉ mô tả sự khác biệt và không kết luận về cách các bài đó được viết.

**Cách đếm:**

- Tên hai blog không được nêu ở đây. Bài được lấy từ trang gốc hoặc từ bản lưu trữ công khai của trang.
- Chỉ đếm văn xuôi trong thân bài. Khối code, mục lục, bình luận và các đoạn lặp lại ở từ 4 bài trở lên (thẻ, bài liên quan, lời chào cuối bài) đã bị loại.
- "Số bài" là số bài có dùng từ đó ít nhất một lần. Số trong ngoặc là tổng số lần xuất hiện.

**Giới hạn:**

- Đây là văn blog của hai tác giả. Tài liệu nội bộ của công ty có thể trang trọng hơn.
- Từ đa nghĩa bị đếm lẫn nghĩa. Ví dụ "yêu cầu" gồm cả nghĩa "request" và "requirement", "kiểm tra" gồm cả "test" và "check". Với các từ này, hãy đọc con số như một mức trần.
- Thuật ngữ Git (commit, branch, merge, pull request, repo) xuất hiện ở dưới 5 bài, nên chưa đủ dữ liệu để kết luận.

## Thuật ngữ

Cột "Viết tay" là số bài trong 102 bài của nhóm A và B. Cột "Đối chứng" là số bài trong 54 bài của nhóm C.

### Tiếng Anh chiếm ưu thế rõ

| Khái niệm | Viết tay: số bài (số lần) | Đối chứng: số bài |
|---|---|---|
| file | file 41 (219) · tệp 0 | file 16 · tệp 2 |
| server | server 24 (108) · máy chủ 2 (2) | server 4 · máy chủ 3 |
| database | database 21 (39) · cơ sở dữ liệu 3 (4) | database 3 · cơ sở dữ liệu 8 |
| framework | framework 24 (56) · khung 5 (6) | framework 7 · khung 14 |
| code | code 90 (787) · mã nguồn 2 (3) | code 37 · mã nguồn 16 |
| debug | debug 14 (25) · gỡ lỗi 0 | debug 4 · gỡ lỗi 1 |
| build | build 26 (63) | build 7 |
| API | API 29 (87) | API 18 |
| module | module 12 (28) · mô-đun 0 | module 4 · mô-đun 1 |
| link | link 26 (48) · liên kết 7 (13) | link 5 · liên kết 6 |
| log | log 8 (75) · nhật ký 0 | log 3 · nhật ký 3 |
| callback | callback 7 (37) · gọi lại 1 (1) | callback 1 · gọi lại 2 |
| upload | upload 7 (14) · tải lên 1 (1) | upload 0 · tải lên 1 |
| performance | performance 12 (13) · hiệu năng 2 · hiệu suất 2 | performance 4 · hiệu suất 12 |

### Tiếng Việt chiếm ưu thế rõ

| Khái niệm | Viết tay: số bài (số lần) | Đối chứng: số bài |
|---|---|---|
| variable | biến 45 (109) · variable 0 | biến 39 |
| library | thư viện 30 (62) · library 6 (7) | thư viện 11 · library 0 |
| user | người dùng 35 (93) · user 8 (10) | người dùng 27 · user 3 |
| system | hệ thống 39 (161) · system 5 (5) | hệ thống 35 · system 5 |
| interface | giao diện 29 (85) · interface 2 (2) | giao diện 9 · interface 1 |
| install | cài 36 (95) · cài đặt 28 (66) · install 1 | cài 9 · cài đặt 8 |
| run | chạy 62 (230) · run 9 (15) | chạy 20 · run 1 |
| handle | xử lý 31 (75) · handle 4 (4) | xử lý 32 |
| support | hỗ trợ 25 (45) · support 2 (3) | hỗ trợ 21 |
| define | khai báo 21 (95) · định nghĩa 14 (30) · define 4 (7) | định nghĩa 19 · khai báo 10 |
| error | lỗi 31 (100) · error 7 (29) | lỗi 30 · error 1 |
| fix | sửa 34 (72) · fix 13 (19) | sửa 14 · fix 0 |
| feature | chức năng 25 (44) · tính năng 13 (23) · feature 1 | tính năng 10 · chức năng 8 |
| default | mặc định 15 (19) · default 2 | mặc định 7 |
| permission | quyền 16 (33) · permission 1 | quyền 9 |
| network | mạng 25 (33) · network 2 | mạng 15 |
| security | bảo mật 10 (38) · security 4 (6) | bảo mật 10 |
| algorithm | thuật toán 11 (51) | thuật toán 9 |
| browser | trình duyệt 8 (13) | trình duyệt 1 |

### Cả hai cách đều phổ biến

| Khái niệm | Viết tay: số bài (số lần) | Đối chứng: số bài |
|---|---|---|
| function | function 28 (155) · hàm 39 (134) | function 2 · hàm 17 |
| class | class 27 (137) · lớp 11 (29) | class 7 · lớp 22 |
| object | object 15 (60) · đối tượng 27 (148) | object 1 · đối tượng 18 |
| method | method 10 (16) · phương thức 10 (15) | method 2 · phương thức 11 |
| property | property 13 (32) · thuộc tính 15 (99) | property 3 · thuộc tính 14 |
| array | array 15 (35) · mảng 8 (15) | array 1 · mảng 3 |
| string | string 16 (34) · chuỗi 7 (12) | string 4 · chuỗi 18 |
| data | data 19 (56) · dữ liệu 48 (374) | data 6 · dữ liệu 36 |
| project | project 38 (108) · dự án 36 (105) | project 8 · dự án 20 |
| app | app 31 (108) · ứng dụng 44 (142) | app 4 · ứng dụng 32 |
| version | version 15 (17) · phiên bản 11 (20) | version 3 · phiên bản 12 |
| developer | developer 39 (117) · dev 27 (64) · lập trình viên 25 (46) | developer 7 · lập trình viên 16 |
| team | team 31 (81) · nhóm 15 (29) | team 3 · nhóm 5 |
| test | test 26 (89) · kiểm tra 17 (28) · kiểm thử 3 (4) | test 11 · kiểm tra 29 · kiểm thử 6 |
| deploy | deploy 14 (28) · triển khai 7 (21) | deploy 6 · triển khai 14 |
| bug | bug 13 (26) · lỗi 31 (100) | bug 4 · lỗi 30 |
| config | config 8 (11) · cấu hình 9 (17) | config 1 · cấu hình 6 |
| tool | tool 12 (30) · công cụ 14 (21) | tool 4 · công cụ 28 |
| update | update 11 (22) · cập nhật 20 (51) | update 3 · cập nhật 9 |
| design | design 15 (33) · thiết kế 27 (51) | design 8 · thiết kế 28 |
| task | task 10 (74) · nhiệm vụ 7 (11) | task 9 · nhiệm vụ 23 |
| service | service 14 (26) · dịch vụ 10 (18) | service 3 · dịch vụ 4 |
| document | document 10 (21) · tài liệu 8 (16) | document 2 · tài liệu 15 |
| model | model 13 (25) · mô hình 14 (30) | model 6 · mô hình 27 |
| folder | folder 4 (9) · thư mục 3 (3) | folder 4 · thư mục 6 |
| cache | cache 4 (5) · bộ đệm 2 (14) | cache 1 · bộ đệm 1 · bộ nhớ đệm 1 |

### Bản dịch của các hãng

Không bài viết tay nào dùng "tệp", "tập tin", "gỡ lỗi", "mô-đun", "nhật ký" (theo nghĩa log), "bộ nhớ đệm", "mã thông báo", "điểm cuối" hay "yêu cầu kéo". "Máy chủ", "cơ sở dữ liệu", "kiểm thử", "mã nguồn" và "khung" xuất hiện ở 2–5 bài trong 102 bài.

Ở nhóm đối chứng, các từ này xuất hiện nhiều hơn dù số bài chỉ bằng một nửa: "khung" 14 bài, "mã nguồn" 16 bài, "cơ sở dữ liệu" 8 bài, "kiểm thử" 6 bài.

## Dấu hiệu của văn giống máy dịch

Các kiểu câu dưới đây hiếm trong văn viết tay và nhiều hơn hẳn ở nhóm đối chứng. Đơn vị là số lần trên 1000 âm tiết, trừ khi ghi khác.

| Dấu hiệu | A | B | C: đối chứng |
|---|---|---|---|
| Tiêu đề tiếng Việt viết hoa mọi chữ | 1 trong 242 (0,4%) | 0 trong 115 | 26 trong 452 (5,8%) |
| "được sử dụng để" | 0,01 | 0,05 | 0,33 |
| "cho phép bạn / chúng ta" | 0,15 | 0,07 | 0,54 |
| "một cách + từ" | 0,17 | 0,55 | 1,06 |
| "được / bị … bởi" | 0,15 | 0,12 | 0,36 |
| "đóng vai trò" | 0,03 | 0,05 | 0,15 |
| ", và" | 0,60 | 0,09 | 1,66 |
| Số viết kiểu Anh "1,000" (số lần) | 0 | 0 | 10 |
| "hóa" (kiểu cũ) so với "hoá" (kiểu mới), số lần | 50 so với 71 | 59 so với 83 | 278 so với 9 |
| "nhé", "nha" | 4,32 | 1,02 | 0,35 |
| "mình" | 13,88 | 3,87 | 1,65 |

Linter dùng các dấu hiệu này cho những quy tắc `mt-phrase`, `adverb-calque`, `passive-voice`, `calque-term` và `title-case-heading`. Tất cả đều ở mức cảnh báo, vì văn viết tay vẫn dùng chúng, chỉ là ít hơn nhiều.

## Kiểu câu trong văn viết tay

Số lần trên 1000 âm tiết.

| Kiểu câu | A | B | Nhận xét |
|---|---|---|---|
| "tiến hành" | 0 | 0,81 | Tác giả nhóm B dùng trong các bước hướng dẫn: "Tiến hành kéo thả giao diện". Vì vậy linter chỉ cảnh báo. |
| "thực hiện việc" | 0 | 0,16 | Như trên. |
| "đến từ" | 0 | 0,12 | Hiếm. |
| "là một + danh từ" | 1,48 | 2,65 | Rất phổ biến, nên không có quy tắc nào cấm. |
| "việc + từ" | 3,40 | 7,12 | Rất phổ biến, nên không có quy tắc nào cấm. |
| "hay" (trừ "hay không") | 3,48 | 2,86 | Nhiều ngang "hoặc" (3,09 và 2,01). Profile `docs` không cảnh báo "hay". |
| Dấu chấm phẩy | 0,67 (30/73 bài) | 0 | Profile `docs` chỉ cảnh báo. |
| "các + từ tiếng Anh" có đuôi -s | 6 trong 110 | 29 trong 306 | 91–95% không thêm -s: "các function". |

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

| Nhóm | Số câu | Trung vị | 75% câu ngắn hơn | 90% câu ngắn hơn | Dài hơn 30 | Dài hơn 45 |
|---|---|---|---|---|---|---|
| A | 3.584 | 18 | 24 | 31 | 10,7% | 0,8% |
| B | 3.269 | 12 | 17 | 21 | 1,3% | 0,1% |
| C: đối chứng | 4.573 | 16 | 23 | 31 | 10,8% | 1,6% |

Chưa tới 1% số câu viết tay dài hơn 45 âm tiết, là giới hạn của profile `docs`. Giới hạn 30 âm tiết của mức Strict chặn khoảng 1 trong 10 câu của văn blog. Điều đó hợp lý, vì văn bản cho agent đọc cần ngắn hơn văn blog.

## Định dạng

- **Phần trăm:** trong cả ngữ liệu, kiểu "25%" xuất hiện 64 lần, kiểu "25 %" không lần nào.
- **Nhóm số:** văn viết tay dùng dấu chấm ("1.000", 7 lần) và không dùng dấu phẩy.
- **Dấu thanh:** văn viết tay dùng cả hai kiểu: "hoá" 154 lần, "hóa" 109 lần.

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

Nhóm trên cùng là lối văn báo cáo hành chính. Văn viết tay gần như không dùng, nên linter cảnh báo ở mọi profile (`officialese`). Các từ chỉ lượng như "một số" thì rất phổ biến trong văn thường, nên linter chỉ cảnh báo khi chạy `--profile report`.

## Linter trên văn viết tay

Chạy `--lang vi --profile docs` trên văn xuôi của 102 bài viết tay. Lỗi mức hard còn lại:

| Quy tắc | Số lần | Ghi chú |
|---|---|---|
| `long-sentence` | 33 | Câu dài hơn 45 âm tiết, khoảng 0,5% số câu |
| `synonym-rotation` | 2 | Một bài dùng lẫn "xoá" với từ cùng nhóm, và "chỉnh sửa" với "sửa đổi" |

Trước khi có số liệu này, linter báo thêm 52 lỗi hard cho "tiến hành", 8 lỗi cho các từ như "mượt mà", "liền mạch", "vượt trội" và 46 lỗi cho dấu chấm phẩy trên cùng các bài đó.
