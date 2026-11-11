# Thêm một ngôn ngữ

ASD-STE100 chỉ định nghĩa cho tiếng Anh. Mỗi thư mục ở đây là một bản chuyển thể không chính thức cho một ngôn ngữ khác.

| Mã | Ngôn ngữ | Trạng thái |
|---|---|---|
| `en` | English | Lõi của skill — `SKILL.md`, `references/`, `examples/` |
| `vi` | Tiếng Việt | Đầy đủ: quy tắc, ví dụ, linter |

Muốn thêm ngôn ngữ mới, mở pull request với các bước dưới đây. Dùng mã ISO 639-1 làm tên thư mục (`ja`, `ko`, `th`, `id`...).

## 1. Viết quy tắc — `languages/<mã>/rules.md`

Không dịch quy tắc tiếng Anh. Tìm xem ngôn ngữ của bạn gây mơ hồ ở đâu. Trả lời các câu hỏi sau:

- **Từ là gì?** Ngôn ngữ có dấu cách giữa các từ không? Tính độ dài câu theo đơn vị nào: từ, âm tiết hay ký tự? Đặt giới hạn tương đương 20 từ (chỉ dẫn) và 25 từ (mô tả) của tiếng Anh. Lấy tỷ lệ độ dài từ ngữ liệu song ngữ nếu có, đừng ước lượng. Ví dụ tiếng Việt: khoảng 1,2 âm tiết cho mỗi từ tiếng Anh theo PhoMT, nên giới hạn là 24 và 30 âm tiết.
- **Thời gian:** động từ có chia thì không? Nếu không, khi nào thiếu dấu hiệu thời gian thì câu mơ hồ?
- **Chủ ngữ:** ngôn ngữ có hay lược chủ ngữ không? Khi nào phải giữ?
- **Từ đa nghĩa:** những từ ngắn nào có nhiều nghĩa (như "hay", "được" trong tiếng Việt)? Thay bằng gì?
- **Văn dịch máy:** cấu trúc nào là dịch từ tiếng Anh (bị động, danh từ hóa)?
- **Chữ viết:** có dấu, có nhiều bảng chữ, có nhiều cách viết cùng một từ không?
- **Từ phỏng đoán:** liệt kê những từ người viết dùng khi chưa chắc (ví dụ "có thể", "có lẽ" trong tiếng Việt, "may", "might" trong tiếng Anh). Các từ này **không bao giờ** bị xóa, và không bị đổi thành lời khẳng định.
- **Số và ngày:** quy ước dấu thập phân, định dạng ngày.

Giữ cấu trúc của `languages/vi/rules.md`: quy tắc cấu trúc (áp dụng đầy đủ), quy tắc từ vựng (định hướng), danh sách rà soát, giữ nguyên phỏng đoán, đầu ra, bảng quy tắc linter.

## 2. Viết ví dụ — `languages/<mã>/examples.md`

Ít nhất 4 ví dụ trước/sau: mô tả công cụ, thông báo lỗi, chỉ dẫn giữa các agent, README. Mỗi ví dụ ghi rõ vi phạm và những từ phỏng đoán đã giữ. Mọi bản "Sau" phải lint sạch:

```bash
grep -A1 '^\*\*Sau:\*\*' languages/<mã>/examples.md | grep '^>' | sed 's/^> //' \
  | python3 scripts/ste-lint.py --lang <mã>
```

Đổi `Sau:` thành nhãn tương ứng trong ngôn ngữ của bạn.

## 3. Thêm quy tắc linter — `scripts/ste-lint.py`

1. Định nghĩa `<MÃ>_RULES`: danh sách `(rule_id, level, pattern, message)`. Dùng lại mã quy tắc có sẵn khi cùng ý nghĩa (`nominalization`, `marketing-adjective`, `passive-voice`...) để `--disable` dùng chung được.
   - `"advisory-free"`: lỗi hard, làm lint thất bại. Chỉ dùng cho mẫu gần như không có báo nhầm.
   - `"advisory"`: chỉ cảnh báo.
2. Định nghĩa `<MÃ>_SYNONYM_GROUPS`: các nhóm từ hay bị dùng lẫn cho cùng một khái niệm.
3. Thêm một mục vào `LANGUAGES`:

   ```python
   "ja": Language(
       name="日本語",
       rules=JA_RULES,
       synonyms=[(g, [_ja_word_re(b) for b in g]) for g in JA_SYNONYM_GROUPS],
       max_words=..., unit="characters", detect=JA_CHAR,
       hedges={...}),
   ```

   `detect` là mẫu nhận diện một câu thuộc ngôn ngữ này ở chế độ `--lang auto`. Chọn ký tự **chỉ** ngôn ngữ đó có.
4. Thêm ca kiểm thử vào `selftest()`, gồm ít nhất: mỗi quy tắc bắt đúng một câu sai, và một câu có từ phỏng đoán **không** bị báo lỗi.
5. Chạy `python3 scripts/ste-lint.py --selftest`.

Nếu ngôn ngữ không có dấu cách giữa các từ (tiếng Nhật, tiếng Trung, tiếng Thái), `_count_words` cần đếm theo đơn vị khác. Mở issue trước khi làm phần này.

## 4. Hồ sơ văn phong (tùy chọn)

Ngoài `rules.md`, một ngôn ngữ có thể có hồ sơ văn phong cho từng loại văn bản, ví dụ `style-docs.md` cho tài liệu và báo cáo. Hồ sơ này xử lý độ tự nhiên: thuật ngữ nào giữ tiếng Anh, cụm nào là dịch máy, quy ước tiêu đề, ngày và số. Xem mẫu `languages/vi/style-docs.md`.

## 5. Cập nhật tài liệu

- Bảng **Languages** trong `SKILL.md`.
- Bảng ngôn ngữ ở đầu tệp này.
- Bảng **Ngôn ngữ hỗ trợ** trong `README.md`.
- Thêm trigger của ngôn ngữ mới vào `description` trong `SKILL.md`.

## Nguồn

Với thuật ngữ, hãy lấy mẫu từ bài viết thật của lập trình viên bản ngữ, đừng dựa vào bảng thuật ngữ của các hãng: bản dịch chính thức thường khác xa cách dev viết. Bản tiếng Việt lấy mẫu 18 bài từ hai blog.

Chuẩn có thể dẫn cho mọi ngôn ngữ: ISO 24495-1:2023 (ngôn ngữ dễ hiểu) và ISO/TS 24620-1:2015 (ngôn ngữ có kiểm soát).

Mỗi nhận định về ngôn ngữ trong `rules.md` cần có nguồn: sách ngữ pháp, quy định chính tả, style guide bản địa hóa (Microsoft, Mozilla), dữ liệu locale (CLDR). Ghi nguồn ở cuối tệp. Quy tắc nào không có nguồn thì ghi rõ là quy ước riêng.

## Nguyên tắc không đổi

- Không bao giờ báo lỗi hoặc xóa từ phỏng đoán. Bỏ đi là biến phỏng đoán thành khẳng định.
- Không thêm thông tin mà bản gốc không có.
- Viết lại bằng đúng ngôn ngữ đầu vào. Không tự dịch.
- Ghi rõ đây là bản chuyển thể không chính thức.
