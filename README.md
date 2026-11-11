<div align="center">

# ASD-STE100 Multilingual Skill

**Viết lại văn bản kỹ thuật sao cho agent, hệ thống và người đọc không thể hiểu sai. Hỗ trợ nhiều ngôn ngữ.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-skill-d97757.svg)](SKILL.md)
[![Languages](https://img.shields.io/badge/languages-English%20%7C%20Ti%E1%BA%BFng%20Vi%E1%BB%87t-green.svg)](#ngôn-ngữ-hỗ-trợ)
[![Linter](https://img.shields.io/badge/linter-Python%203%20stdlib-3776ab.svg)](scripts/ste-lint.py)
[![PRs welcome](https://img.shields.io/badge/PRs-th%C3%AAm%20ng%C3%B4n%20ng%E1%BB%AF-brightgreen.svg)](languages/README.md)

**Tiếng Việt** · [English](README.en.md)

</div>

---

## Giới thiệu

[ASD-STE100](https://www.asd-ste100.org/) (Simplified Technical English) là chuẩn viết tiếng Anh do ngành hàng không và quốc phòng châu Âu xây dựng. Chuẩn giới hạn từ vựng và cấu trúc câu để mỗi câu chỉ có một cách hiểu, nhờ vậy kỹ thuật viên bảo trì máy bay, phần lớn không phải người bản ngữ, không đọc nhầm chỉ dẫn.

Skill này đem nguyên tắc đó áp dụng cho một loại người đọc khác: **AI agent**. Agent phải tự hiểu tool description, error message hay chỉ dẫn từ agent khác mà không có ai để hỏi lại, nên chỉ cần một câu hiểu được hai cách là agent có thể làm sai.

Ngôn ngữ nào cũng có câu mơ hồ, nhưng mỗi thứ tiếng mơ hồ theo một kiểu: tiếng Anh vướng phrasal verb, tiếng Việt vướng những từ ngắn nhiều nghĩa ("hay", "được", "rồi") và chữ viết không dấu, còn tiếng Nhật thường lược chủ ngữ. Vì thế repo được tổ chức thành **khung đa ngôn ngữ**: nguyên tắc chung dùng cho mọi ngôn ngữ, còn quy tắc riêng của từng thứ tiếng nằm trong một gói riêng.

## Ngôn ngữ hỗ trợ

| Ngôn ngữ | Mã | Quy tắc | Ví dụ | Linter |
|---|---|---|---|---|
| English | `en` | [`SKILL.md`](SKILL.md), [`references/writing-rules.md`](references/writing-rules.md) | [`examples/before-after.md`](examples/before-after.md) | ✅ |
| Tiếng Việt | `vi` | [`languages/vi/rules.md`](languages/vi/rules.md), [văn phong tài liệu](languages/vi/style-docs.md) | [`languages/vi/examples.md`](languages/vi/examples.md) | ✅ |
| Ngôn ngữ khác | — | Chỉ có các quy tắc chung | — | Chỉ kiểm tra quy tắc chung |

Ngôn ngữ chưa có gói riêng vẫn dùng được. Khi đó skill chỉ áp dụng các quy tắc chung (mỗi câu một chỉ dẫn, nêu rõ ai làm, không lược thành phần câu, giữ nguyên những từ như "có thể", "có lẽ") và báo cho bạn biết.

Nếu bạn muốn thêm một ngôn ngữ mới, hãy làm theo hướng dẫn trong [`languages/README.md`](languages/README.md).

## Trước / Sau

**Tiếng Việt**

| Trước | Sau |
|---|---|
| Đã có lỗi có thể xảy ra trong quá trình xử lý yêu cầu của bạn do sự không khớp về định dạng dữ liệu, điều này có thể là do phiên bản client đã cũ. | Yêu cầu của bạn có thể đã thất bại. Nguyên nhân có thể là định dạng dữ liệu không khớp với định dạng máy chủ cần. Phiên bản client cũ có thể gây ra lỗi không khớp này. Kiểm tra phiên bản client của bạn. |

**English**

| Before | After |
|---|---|
| An error may have occurred while processing your request due to a possible mismatch in the expected data format, which could be caused by an outdated client version. | Your request may have failed. The cause may be a data format that does not match what the server expects. An outdated client can cause this mismatch. Check your client version. |

Error message là văn bản cho agent đọc, nên bản viết lại theo mức Strict: câu ngắn, lặp lại danh từ để không ai hiểu nhầm. Các chữ "có thể" và "may" vẫn được giữ nguyên: hệ thống mới chỉ phỏng đoán, nên bản viết lại không được biến phỏng đoán thành khẳng định.

## Tính năng

| | |
|---|---|
| **Đa ngôn ngữ** | Skill tự nhận ra văn bản viết bằng tiếng gì và viết lại bằng đúng thứ tiếng đó, không tự ý dịch. |
| **Hai mức văn phong** | Mức **Strict** dành cho văn bản agent đọc như error message, tool description, chỉ dẫn. Mức **tự nhiên** dành cho văn bản người đọc như README, tài liệu, mô tả PR, báo cáo. |
| **Không đổi phỏng đoán thành khẳng định** | "Có thể đã thất bại" không bao giờ bị viết lại thành "đã thất bại". Bản viết lại cũng không thêm thông tin mà bản gốc không có. |
| **Kết quả gọn** | Mặc định skill chỉ trả về văn bản đã viết lại, để bạn dán dùng ngay. Nếu muốn biết đã sửa những gì, hãy thêm "show the diff" vào yêu cầu. |
| **Linter** | Một script Python 3 chỉ dùng thư viện chuẩn và không kết nối mạng. Script kiểm tra được cả tài liệu viết lẫn nhiều thứ tiếng. |
| **Văn phong tài liệu** | Hướng dẫn viết tài liệu và báo cáo tiếng Việt sao cho giống kỹ sư Việt viết: dùng thuật ngữ đúng thói quen của dev Việt, nối các ý với nhau thay vì viết câu cụt, không viết hoa mọi chữ trong tiêu đề. Hướng dẫn nằm ở [`languages/vi/style-docs.md`](languages/vi/style-docs.md), số liệu làm căn cứ nằm ở [`evidence.md`](languages/vi/evidence.md). | |
| **Báo cáo cụ thể** | Hướng dẫn viết báo cáo tiến độ, báo cáo sự cố, báo cáo kết quả đo và báo cáo sau khi làm xong việc: kết luận lên đầu, con số thay cho tính từ, nói rõ đã kiểm chứng đến đâu. Hướng dẫn nằm ở [`languages/vi/style-reports.md`](languages/vi/style-reports.md). |
| **Dễ mở rộng** | Muốn thêm một thứ tiếng, bạn chỉ cần thêm một thư mục tài liệu và một mục trong registry của linter. |

## Cài đặt

**Cách 1 — skills CLI** (cho một project):

```bash
npx skills add anvyxhq/asd-ste100-multilingual
```

Khi cài đặt, CLI này gửi telemetry ẩn danh. Nếu không muốn, bạn đặt environment variable `DISABLE_TELEMETRY=1` trước khi chạy.

**Cách 2 — clone** (cho mọi project trên máy):

```bash
git clone https://github.com/anvyxhq/asd-ste100-multilingual ~/.claude/skills/asd-ste100
```

Khi cần cập nhật, bạn chạy `git pull` trong thư mục đó.

## Sử dụng

Trong Claude Code, bạn dán đoạn văn bản cần sửa rồi nêu yêu cầu, bằng tiếng Việt hay tiếng Anh đều được:

```text
Viết lại thông báo lỗi này để agent không hiểu sai
Áp dụng STE cho tool description này, show the diff
Disambiguate this tool description
Rewrite this error message so an agent can't misparse it
```

## Linter

```bash
python3 scripts/ste-lint.py README.md            # mọi ngôn ngữ (mặc định: --lang auto)
python3 scripts/ste-lint.py --lang vi docs/*.md  # chỉ quy tắc tiếng Việt
python3 scripts/ste-lint.py --profile docs README.md  # văn bản tiếng Việt cho người đọc: nới giới hạn câu
python3 scripts/ste-lint.py --profile report bao-cao.md  # báo cáo: cảnh báo thêm từ mơ hồ
python3 scripts/ste-lint.py --json --baseline 5 docs/
python3 scripts/ste-lint.py --selftest
```

Ví dụ kết quả khi chạy trên một câu tiếng Việt:

```console
$ echo "Tiến hành kiểm tra tệp, khong được bỏ qua. Dữ liệu được ghi bởi agent." | python3 scripts/ste-lint.py --lang vi
<stdin>:1:1 nominalization: Hành động bị danh từ hóa. Dùng thẳng động từ ("kiểm tra", không phải "tiến hành việc kiểm tra"). [Tiến hành kiểm]
<stdin>:1:25 missing-diacritics: Tiếng Việt không dấu là đa nghĩa (ban = bạn/bán/bàn). Viết đủ dấu. [khong]
<stdin>:1:52 passive-voice: Câu bị động kiểu "được/bị ... bởi" thường bị coi là câu văn "Tây". Viết câu chủ động, hoặc "được + tác nhân + động từ", hoặc "do + tác nhân + động từ". [được ghi bởi]

3 violations (1 hard, baseline 0), 15 words, 20.0 per 100 words
```

| Mã thoát | Ý nghĩa |
|---|---|
| `0` | Số vi phạm hard không vượt `--baseline` |
| `1` | Số vi phạm hard vượt `--baseline` (mặc định 0) |
| `2` | Lỗi cách dùng: sai flag, sai mã quy tắc, không đọc được tệp |

Ở chế độ `--lang auto`, linter chạy quy tắc của mọi thứ tiếng, và mỗi câu được đo theo giới hạn của chính thứ tiếng đó: 25 từ với tiếng Anh, 30 âm tiết với tiếng Việt. Nhờ vậy tài liệu trộn hai thứ tiếng vẫn được kiểm tra đúng.

Mặc định linter dùng profile `strict`, dành cho văn bản agent đọc. Với README hay tài liệu tiếng Việt, hãy dùng `--profile docs`. Profile này nới giới hạn câu tiếng Việt lên 45 âm tiết và không cảnh báo "hay" theo nghĩa "hoặc". Dấu chấm phẩy, từ quảng cáo và cụm từ đệm cũng chỉ còn là cảnh báo. Các thay đổi này chỉ áp dụng cho dòng tiếng Việt, còn dòng tiếng Anh giữ nguyên mọi mức. Các mức này được chỉnh theo [số liệu từ 102 bài viết tay](languages/vi/evidence.md) của dev Việt. Với báo cáo, hãy dùng `--profile report`: ngoài các thiết lập của `docs`, profile này cảnh báo thêm từ chỉ lượng mơ hồ ("một số", "gần xong"), thời gian mơ hồ ("sẽ sớm") và lời khẳng định không kèm cách kiểm chứng ("chạy ổn"). Những từ như "may", "might", "có thể", "có lẽ" không bao giờ bị báo lỗi.

Danh sách quy tắc của tiếng Anh nằm trong [`README.en.md`](README.en.md), của tiếng Việt nằm trong [`languages/vi/rules.md`](languages/vi/rules.md#kiểm-tra-bằng-linter).

## Cấu trúc thư mục

```text
asd-ste100-multilingual/
├── SKILL.md                   # chỉ dẫn cho Claude: lõi + cơ chế chọn ngôn ngữ
├── references/
│   └── writing-rules.md       # tóm tắt quy tắc ASD-STE100 (tiếng Anh, lõi)
├── examples/
│   ├── before-after.md        # ví dụ tiếng Anh
│   └── linter-edge-cases.md   # fixture kiểm thử (cố ý sai)
├── languages/
│   ├── README.md              # hướng dẫn thêm ngôn ngữ
│   └── vi/
│       ├── rules.md           # quy tắc chuyển thể cho tiếng Việt
│       ├── style-docs.md      # văn phong tài liệu và báo cáo (không dùng cho UI app)
│       ├── style-reports.md   # cách viết báo cáo cụ thể, có mẫu cho 4 loại báo cáo
│       ├── evidence.md        # số liệu từ 156 bài viết của dev Việt
│       └── examples.md        # ví dụ tiếng Việt
├── scripts/
│   └── ste-lint.py            # linter, registry ngôn ngữ trong LANGUAGES
├── README.md                  # tài liệu này
└── README.en.md               # README tiếng Anh (gốc)
```

## Phạm vi và giới hạn

**Nên dùng cho:** tin nhắn giữa các agent, tool description, error message, system prompt và thông báo trạng thái.

**Không nên dùng cho:** văn sáng tác, văn quảng cáo và những văn bản cần giọng văn riêng.

**Giới hạn:**

- Skill sửa cách viết chứ không sửa nội dung: một đoạn không có gì để nói thì viết lại vẫn rỗng, chỉ gọn hơn thôi.
- Giấy phép của ASD-STE100 không cho phân phối lại bộ từ điển khoảng 900 từ, nên skill không kèm từ điển đó. Phần quy tắc từ vựng vì thế chỉ là gợi ý.
- ASD chỉ định nghĩa STE cho tiếng Anh, nên mọi bản cho thứ tiếng khác đều là **chuyển thể không chính thức**.
- Đây không phải công cụ biên soạn STE có chứng nhận. Nếu viết tài liệu bảo trì máy bay thật, hãy dùng chuẩn gốc.

## Đóng góp

Cách đóng góp hữu ích nhất là **thêm thứ tiếng mới**. Bạn viết quy tắc và ví dụ, thêm một mục vào registry `LANGUAGES` của linter rồi chạy `--selftest`. Chi tiết ở [`languages/README.md`](languages/README.md).

Muốn sửa quy tắc của thứ tiếng đã có, hãy sửa trong `scripts/ste-lint.py`, thêm ca kiểm thử vào `selftest()` và cập nhật bảng quy tắc trong `languages/<mã>/rules.md`.

Dù sửa gì cũng phải giữ một nguyên tắc: **không bao giờ báo lỗi hay xóa những từ như "có thể", "có lẽ"**. Người viết dùng chúng khi chưa chắc, bỏ đi là biến phỏng đoán thành khẳng định.

## Ghi công

Repo được fork từ [danyuchn/asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill) của Dustin Yuchen Teng. Bộ quy tắc tiếng Anh, linter gốc và phần parse Markdown là công của tác giả gốc.

Một số bản chuyển thể độc lập khác có thể gộp vào `languages/` sau này: [tiếng Hebrew](https://github.com/g4lb/asd-ste100-hebrew-skill) · [tiếng Indonesia](https://github.com/jshsinaga/asd-ste100-indonesian-skill)

## Giấy phép

Dự án dùng giấy phép MIT. Bạn có thể đọc toàn văn giấy phép trong [LICENSE](LICENSE).
