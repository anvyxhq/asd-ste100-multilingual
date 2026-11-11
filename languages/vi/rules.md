# Quy tắc STE cho tiếng Việt

ASD-STE100 là chuẩn dành riêng cho tiếng Anh. Tệp này đem các nguyên tắc của chuẩn đó áp dụng cho tiếng Việt. Đây là bản chuyển thể không chính thức, chưa được ASD công nhận.

Mục tiêu vẫn như cũ: mỗi câu chỉ có một cách hiểu, vì người đọc là agent, hệ thống hoặc một người không thể hỏi lại tác giả. Yêu cầu này không xa lạ với tiếng Việt. Quy định về soạn thảo văn bản pháp luật cũng đòi hỏi câu chữ "không làm phát sinh nhiều cách hiểu" và thuật ngữ phải "sử dụng thống nhất" (Nghị quyết 351/2017/UBTVQH14, Điều 18).

Đọc tệp này khi văn bản đầu vào là tiếng Việt. Khi viết tài liệu, đọc thêm `style-docs.md`. Khi viết báo cáo, đọc thêm `style-reports.md`. Các phần còn lại của `SKILL.md` vẫn áp dụng: hai chế độ, giữ nguyên phỏng đoán, không thêm thông tin, định dạng đầu ra.

## Khác biệt chính so với tiếng Anh

| Tiếng Anh | Tiếng Việt | Quy tắc cần điều chỉnh |
|---|---|---|
| Động từ chia thì | Động từ không biến đổi. Người viết có thể thêm hoặc không thêm "đã/đang/sẽ" | Thiếu "đã/đang/sẽ" có thể gây mơ hồ. Xem quy tắc 6 |
| Câu luôn có chủ ngữ | Chủ ngữ thường bị lược | Văn bản mô tả và trạng thái phải nêu chủ ngữ. Xem quy tắc 2 |
| Phrasal verb dễ bị hiểu nhiều nghĩa | Không có phrasal verb | Dễ bị hiểu nhiều nghĩa là các từ ngắn như "hay", "được", "rồi", "cho", "mà", "lại". Xem quy tắc 8 |
| Một từ là một token | Một âm tiết là một token | Giới hạn độ dài tính theo âm tiết. Xem quy tắc 4 |
| Cụm danh từ: bổ ngữ đứng trước | Bổ ngữ đứng sau danh từ chính | Chuỗi bổ ngữ dài làm mơ hồ quan hệ sở hữu. Xem quy tắc 5 |
| Không có dấu thanh | Đổi dấu thanh là đổi nghĩa của từ | Bắt buộc viết đủ dấu. Xem quy tắc 1 |

## Quy tắc cấu trúc — áp dụng đầy đủ

### 1. Viết đủ dấu

Tiếng Việt viết không dấu rất dễ bị hiểu sai. "ban" có thể là "bạn", "bán", "bàn", "bản" hoặc "bận". Agent đọc "xoa tep" thì phải đoán nghĩa.

- Viết đủ dấu ở mọi chế độ.
- Dùng Unicode dựng sẵn (NFC). Văn bản ở dạng tổ hợp (NFD) trông giống hệt, nhưng khi so khớp chuỗi sẽ cho kết quả sai.
- Chọn một kiểu đặt dấu ("xóa" hoặc "xoá") và dùng thống nhất trong cả tài liệu. Cả hai kiểu đều đang được dùng. Sách giáo khoa theo kiểu mới ("hoà", "thuỷ") từ Quyết định 1989/QĐ-BGDĐT. Giao diện của Apple và Microsoft dùng kiểu cũ ("Hủy", "Xóa").

### 2. Câu chủ động, có chủ ngữ rõ ràng

| Nên | Không nên |
|---|---|
| "Agent ghi dữ liệu vào tệp." | "Dữ liệu được ghi bởi agent." — kiểu bị động "được ... bởi", thường bị coi là câu văn "Tây" |
| "Hệ thống đã xóa tệp." | "Đã xóa tệp." — trong văn bản mô tả, người đọc không biết ai xóa |
| "Xóa tệp." | — câu mệnh lệnh không cần chủ ngữ. Chỉ câu mệnh lệnh mới được lược chủ ngữ |

"Bị" thường mang sắc thái tiêu cực. "Được" thường mang sắc thái tích cực, và cũng dùng được ở nghĩa trung tính ("Trà được trồng ở Nhật Bản"). Sắc thái này tính theo góc nhìn của chủ ngữ: "Lạm phát bị đẩy lùi" là tin tốt. "Không được" là lời cấm, không phải bị động: "Không ai được vắng mặt". "Tệp bị xóa" ngầm báo một sự cố. Không dùng "bị" cho hành động bình thường của hệ thống.

Chỉ dùng câu bị động khi tác nhân thật sự không rõ hoặc không quan trọng. Khi cần nêu tác nhân, có ba cách viết tự nhiên thay cho "được ... bởi": câu chủ động ("Agent ghi dữ liệu"), tác nhân đứng trước động từ ("Dữ liệu được agent ghi"), hoặc dùng "do" ("Dữ liệu do agent ghi").

### 3. Mỗi câu một chỉ dẫn

| Nên | Không nên |
|---|---|
| "Mở tệp. Đọc dòng 3." | "Mở tệp và đọc dòng 3, sau đó kiểm tra xem có khớp không." |

### 4. Độ dài câu (tính theo âm tiết)

- Chỉ dẫn, quy trình: tối đa **24 âm tiết**.
- Mô tả: tối đa **30 âm tiết**.

Các số này tương ứng với giới hạn 20 và 25 từ của STE. Trong kho ngữ liệu song ngữ PhoMT (3,02 triệu cặp câu), một câu tiếng Anh 15,7 từ ứng với 19,0 âm tiết tiếng Việt, tức khoảng 1,2 lần. Một âm tiết là một token phân tách bằng dấu cách. Mã nguồn trong backtick không tính.

Hai giới hạn trên dành cho văn bản agent đọc. Văn bản cho người đọc (README, tài liệu, báo cáo) theo `style-docs.md`, với giới hạn 45 âm tiết. Số 45 là quy ước riêng của bộ quy tắc này, không suy ra từ STE.

### 5. Cụm danh từ ngắn, quan hệ rõ ràng

Mỗi cụm chỉ nên có một danh từ chính và tối đa hai bổ ngữ. Khi cụm dài hơn, hãy viết rõ quan hệ giữa các từ bằng "của", "cho", "dùng để", "trong".

| Nên | Không nên |
|---|---|
| "bộ xử lý đặt độ ưu tiên cho hàng đợi tác vụ" | "bộ xử lý ưu tiên hàng đợi tác vụ agent" — không rõ "agent" bổ nghĩa cho từ nào |

### 6. Thời gian: nêu đủ, không nêu thừa

Tiếng Việt không chia thì, nên dễ mắc hai lỗi ngược nhau.

- **Thiếu từ chỉ thời gian.** "Tác vụ hoàn tất" có thể là "đã hoàn tất" hoặc "sẽ hoàn tất". Trong thông báo trạng thái, luôn viết rõ "đã", "đang" hoặc "sẽ". Đây là điểm ngược với tiếng Anh: STE bỏ thì phức, còn tiếng Việt phải thêm từ chỉ thời gian thì câu mới hết mơ hồ.
- **Thừa từ chỉ thời gian.** "đã từng", "đã đang", "sẽ đang". Chỉ dùng một từ.
- Không thêm "rồi" sau "đã" ("đã xong rồi"). "Rồi" vừa nghĩa là "đã xong" vừa nghĩa là "sau đó".

Ngoại lệ: "có thể đã", "có lẽ đã từng" thể hiện người viết chưa chắc chắn. Giữ nguyên, vì bỏ đi là đổi nghĩa câu.

### 7. Không lược bớt thành phần câu

| Nên | Không nên |
|---|---|
| "Hệ thống sẽ mất các tệp chưa sao lưu." | "Tệp chưa sao lưu sẽ mất." — không rõ một tệp hay tất cả |
| "Kiểm tra cấu hình của máy chủ." | "Kiểm tra cấu hình máy chủ." khi có nhiều loại cấu hình — chỉ rút gọn khi không còn cách hiểu khác |

Giữ "các/những" khi số lượng quan trọng. Giữ "của" khi quan hệ sở hữu có thể bị hiểu sai.

### 8. Tránh từ ngắn đa nghĩa

Đây là các từ chỉ dùng để nối câu hoặc đánh dấu ngữ pháp (thuật ngữ ngữ pháp gọi là *hư từ*). Mỗi từ có nhiều nghĩa, và người đọc phải đoán nghĩa từ ngữ cảnh.

| Từ | Các nghĩa | Thay bằng |
|---|---|---|
| "hay" | hoặc / thường xuyên / tốt | "hoặc" (khi nghĩa là "or"). Câu hỏi "có ... hay không" vẫn rõ nghĩa |
| "được" | bị động / được phép / có thể / đạt được | "được phép", "có thể" hoặc viết câu chủ động |
| "rồi" | đã xong / sau đó | "đã" hoặc "sau đó" |
| "cho" | đưa / dành cho / để cho phép | "gửi", "dành cho", "cho phép" |
| "mà" | nhưng / đại từ quan hệ | "nhưng" hoặc tách câu |
| "lại" | lần nữa / quay về / trái lại | "lần nữa", "quay về", "nhưng" |
| "nó" | chỉ đối tượng nào? | lặp lại danh từ |

### 9. Không dấu chấm phẩy

Giống STE Rule 8.1: không dùng dấu chấm phẩy. Tách thành câu riêng.

### 10. Đoạn văn và danh sách

- Mỗi đoạn một chủ đề, tối đa 6 câu.
- Từ 3 bước hoặc 3 điều kiện trở lên thì dùng danh sách.
- Mục danh sách không kết thúc bằng "và" hoặc "hoặc".

### 11. Số, ngày, đơn vị

Văn bản tiếng Việt cho máy đọc hay gặp ba lỗi sau.

- "1.000" là một nghìn theo kiểu Việt Nam, nhưng là 1,0 theo kiểu tiếng Anh. Trong văn bản cho agent, không dùng dấu phân cách hàng nghìn, hoặc nêu rõ quy ước.
- "03/04/2026" có thể là 3 tháng 4 hoặc 4 tháng 3. Dùng ISO 8601 (`2026-04-03`) hoặc viết "ngày 3 tháng 4 năm 2026".
- Luôn ghi đơn vị: "30 giây", không phải "30".

## Quy tắc từ vựng — chỉ là gợi ý

### Một khái niệm, một từ

Mỗi khái niệm chọn một từ, rồi dùng thống nhất trong cả tài liệu.

| Nhóm hay bị trộn | Chọn một |
|---|---|
| xác minh / kiểm chứng | |
| xóa / loại bỏ / gỡ bỏ | |
| bắt đầu / khởi chạy | |
| chỉnh sửa / sửa đổi | |
| khắc phục / sửa lỗi | |
| tệp / tập tin / file | |
| thư mục / folder | |
| người dùng / người sử dụng | |

### Thuật ngữ tiếng Anh

Văn bản kỹ thuật tiếng Việt thường dùng lẫn thuật ngữ tiếng Anh. Điều đó không sao, miễn là dùng nhất quán.

Các ví dụ trong tệp này dùng "tệp", "máy chủ" theo thuật ngữ giao diện của Apple và Microsoft, vì error message thường hiện cho người dùng cuối. Trong tài liệu giữa các dev, "file" và "server" phổ biến hơn nhiều (xem `style-docs.md`).

- Nếu đã dùng từ tiếng Anh ("cache", "commit") thì lần nào cũng dùng từ đó. Không đổi qua lại giữa "cache" và "bộ nhớ đệm".
- Nếu dùng từ tiếng Việt, ghi từ tiếng Anh trong ngoặc ở lần đầu: "bộ nhớ đệm (cache)".
- Tên hàm, tên variable, lệnh: đặt trong backtick và không dịch.

### Dùng động từ, không danh từ hóa

| Nên | Không nên |
|---|---|
| "Kiểm tra tệp." | "Tiến hành kiểm tra tệp." / "Thực hiện việc kiểm tra tệp." |
| "Cấu hình thay đổi." | "Có sự thay đổi trong cấu hình." |
| "Công cụ hỗ trợ người dùng." | "Công cụ cung cấp sự hỗ trợ cho người dùng." |

### Dùng từ thông thường, không dùng từ trang trọng

Ưu tiên từ phổ biến nhất có cùng nghĩa: "dùng" thay vì "vận dụng", "bắt đầu" thay vì "khởi xướng". Từ Hán Việt vẫn được dùng khi nó là thuật ngữ chuẩn ("cấu hình", "đồng bộ").

## Danh sách rà soát

Rà soát sáu lỗi sau trước khi viết lại.

1. **Đổi tên cho cùng một thứ.** "người dùng", "khách hàng", "user" trong cùng một tài liệu.
2. **Chồng nhiều lớp "có thể".** "điều quan trọng cần lưu ý là việc này có thể có khả năng giúp cải thiện". Nói thẳng nội dung hoặc xóa.
3. **Danh từ hóa.** "tiến hành", "thực hiện việc", "có sự", "cung cấp sự".
4. **Từ ngữ quảng cáo.** liền mạch, mượt mà, vượt trội, đột phá, hàng đầu, siêu nhanh. Xóa hoặc thay bằng số đo.
5. **Câu dài nối nhiều ý.** Nhiều ý nối bằng dấu phẩy, "và", "đồng thời", "trong khi đó". Mỗi câu một ý.
6. **Câu văn "Tây".** "được ... bởi", "một cách + tính từ" ("một cách tự động" → "tự động"), "Nó là cần thiết để", "là một trong những".

## Không đổi phỏng đoán thành khẳng định

Người viết dùng "có thể", "có lẽ", "có khả năng", "có thể đã", "chưa chắc", "thường" khi chưa chắc về điều mình nói. Không bao giờ bỏ các từ này, và không đổi chúng thành lời khẳng định. Làm vậy là đổi nghĩa câu.

- "Yêu cầu có thể đã thất bại." giữ nguyên "có thể đã". Không viết lại thành "Yêu cầu đã thất bại."
- "Lỗi có thể do phiên bản client cũ." không được viết lại thành "Lỗi do phiên bản client cũ."

## Đầu ra

- Viết lại bằng **cùng ngôn ngữ với đầu vào**. Không dịch, trừ khi người dùng yêu cầu.
- Dòng ghi chú `Kept as-is:` viết bằng tiếng Việt: `Giữ nguyên:`.
- Bảng quy tắc (khi người dùng yêu cầu) dùng tiêu đề tiếng Việt: `| Quy tắc vi phạm | Bản gốc | Bản viết lại |`.

## Kiểm tra bằng linter

`scripts/ste-lint.py` kiểm tra tiếng Việt khi chạy với `--lang auto` (mặc định) hoặc `--lang vi`. Các quy tắc linter:

| Mã quy tắc | Mức | Kiểm tra |
|---|---|---|
| `semicolon` | hard (advisory với `--profile docs`) | dấu chấm phẩy |
| `marketing-adjective` | hard (advisory với `--profile docs`) | danh sách từ quảng cáo |
| `filler-phrase` | hard (advisory với `--profile docs`) | "điều quan trọng cần lưu ý là", "cần lưu ý rằng", "như đã đề cập ở trên" |
| `missing-diacritics` | hard | các từ không dấu phổ biến ("khong", "duoc", "kiem tra"...) |
| `synonym-rotation` | hard | trộn các từ trong cùng một nhóm ở bảng "Một khái niệm, một từ" |
| `long-sentence` | hard | câu dài hơn 30 âm tiết (45 với `--profile docs`) |
| `dangling-conjunction` | hard | mục danh sách kết thúc bằng "và" hoặc "hoặc" |
| `nominalization` | advisory | "tiến hành", "thực hiện việc/sự", "có sự", "cung cấp sự", và "sự + động từ" sau từ nối ("do sự không khớp", "nhận được sự cho phép") |
| `passive-voice` | advisory | "được/bị ... bởi" |
| `tense-stack` | advisory | "đã từng", "đã đang"... (bỏ qua khi có "có thể" đứng trước) |
| `adverb-calque` | advisory | "một cách + tính từ" |
| `ambiguous-word` | advisory, không chạy với `--profile docs` và `report` | "hay" (bỏ qua "hay không", "thường hay") |
| `redundant-word` | advisory | từ thừa: "hoàn thành xong", "tái tạo lại", "tối ưu nhất" |
| `calque-term` | advisory | bản dịch ít người dùng của thuật ngữ: "yêu cầu kéo", "điểm cuối", "mã thông báo"... |
| `mt-phrase` | advisory | cụm rườm rà (quy ước riêng): "được sử dụng để", "cho phép bạn", "là một trong những"... |
| `title-case-heading` | advisory | tiêu đề tiếng Việt viết hoa mọi chữ, từ 3 từ trở lên |
| `number-format` | advisory | "25 %" có dấu cách, số kiểu Anh "1,000" trong dòng tiếng Việt |
| `officialese` | advisory | lối văn báo cáo hành chính: "cơ bản hoàn thành", "kịp thời", "đẩy mạnh", "trong thời gian tới" |
| `vague-quantity` | advisory, chỉ với `--profile report` | "một số", "khá nhiều", "đáng kể", "gần xong" |
| `vague-time` | advisory, chỉ với `--profile report` | "sẽ sớm", "sắp tới", "gần đây" |
| `unverified-claim` | advisory, chỉ với `--profile report` | "chạy ổn", "hoạt động tốt", "đã test xong" |
| `terse-pointer` | advisory | câu cụt kiểu ghi chú: "Muốn thêm ngôn ngữ? Xem README.", "MIT — xem LICENSE." |
| `literal-idiom` | advisory | dịch sát câu nói gọn của tiếng Anh: "…là mục đích.", "…là chìa khóa." |

Các mức này được chỉnh theo số liệu từ 102 bài viết tay của lập trình viên Việt. Xem [`evidence.md`](evidence.md).

Profile `docs` và `report` chỉ nới lỏng trên những dòng linter nhận ra là tiếng Việt, tức là dòng có ít nhất một chữ cái chỉ tiếng Việt mới có (ă, đ, ơ, ư hoặc nguyên âm có dấu thanh). Dòng tiếng Anh giữ nguyên mọi mức.

Linter không kiểm tra: chủ ngữ bị lược, cụm danh từ dài, "được/rồi/cho/mà" đa nghĩa, số và ngày mơ hồ. Các quy tắc đó cần hiểu ngữ cảnh. Model phải tự áp dụng chúng.

## Nguồn tham khảo

Các nhận định về tiếng Việt trong tệp này dựa trên những nguồn sau. Mỗi quy tắc không có nguồn là quy ước riêng của bộ quy tắc này.

| Nội dung | Nguồn |
|---|---|
| Động từ không chia thì, "đã/đang/sẽ" là tùy chọn. Chủ ngữ có thể lược. Sắc thái "bị/được" | [Vietnamese grammar — Wikipedia](https://en.wikipedia.org/wiki/Vietnamese_grammar) · Microsoft Vietnamese Localization Style Guide |
| Các nghĩa của "hay", "được", "rồi", "cho", "mà", "lại" | Wiktionary: [hay](https://en.wiktionary.org/wiki/hay), [được](https://en.wiktionary.org/wiki/được), [rồi](https://en.wiktionary.org/wiki/rồi), [cho](https://en.wiktionary.org/wiki/cho), [mà](https://en.wiktionary.org/wiki/mà), [lại](https://en.wiktionary.org/wiki/lại) |
| Tiếng Việt không dấu là đa nghĩa | [Nghiên cứu khôi phục dấu tiếng Việt (arXiv 1709.07104)](https://arxiv.org/pdf/1709.07104) |
| Quy tắc đặt dấu thanh | [Quyết định 1989/QĐ-BGDĐT (2018), Điều 8](https://luatvietnam.vn/giao-duc/quyet-dinh-1989-qd-bgddt-2018-quy-dinh-ve-chinh-ta-trong-chuong-trinh-sach-giao-khoa-gdpt-307547-d1.html) · [Quy tắc đặt dấu thanh — Wikipedia](https://vi.wikipedia.org/wiki/Quy_tắc_đặt_dấu_thanh_trong_chữ_quốc_ngữ) |
| NFC và so khớp chuỗi | [W3C Character Model: String Matching](https://www.w3.org/TR/charmod-norm/) |
| Bị động "được ... bởi" bị phê bình là câu văn "Tây" | Cao Xuân Hạo, "Linh hồn tiếng Việt" (2001) · Đỗ Lan Anh, ["Vấn đề giao thoa trong dịch thuật Pháp–Việt"](https://js.vnu.edu.vn/FS/article/view/2000/1902) (2016) · Nguyễn Văn Khang, dẫn trong [VietNamNet (2016)](https://vietnamnet.vn/tieng-viet-dang-bi-dung-de-dai-thieu-chuan-muc-338087.html) · ý kiến phản bác của [Trịnh Hữu Tuệ (talawas, 2004)](https://talawas.org/bai/tra-loi-cao-xuan-hao/) |
| Sắc thái "bị/được" tính theo chủ ngữ, "không được" là lời cấm | Nguyễn Văn Đen, ["Một số cách dùng các từ 'bị', 'được'"](https://vjol.info.vn/index.php/NNDS/article/download/16484/14766), Ngôn ngữ & Đời sống, 2012 |
| Tỷ lệ độ dài câu Anh–Việt khoảng 1,2 | [PhoMT (arXiv 2110.12199), Bảng 1](https://arxiv.org/abs/2110.12199) |
| Dấu thập phân, dấu nhóm số, định dạng ngày | [CLDR `vi` — numbers](https://raw.githubusercontent.com/unicode-org/cldr-json/main/cldr-json/cldr-numbers-full/main/vi/numbers.json), [CLDR `vi` — dates](https://raw.githubusercontent.com/unicode-org/cldr-json/main/cldr-json/cldr-dates-full/main/vi/ca-gregorian.json) |
| Câu chữ "không làm phát sinh nhiều cách hiểu", thuật ngữ dùng thống nhất | Nghị quyết 351/2017/UBTVQH14, Điều 18, dẫn theo [Tạp chí Quản lý nhà nước (2025)](https://www.quanlynhanuoc.vn/2025/03/20/nhung-yeu-to-tac-dong-den-viec-su-dung-ngon-ngu-trong-van-ban-quy-pham-phap-luat/) |

Chưa tìm thấy chuẩn hay công trình nào về một "tiếng Việt kỹ thuật đơn giản hóa" tương tự STE.
