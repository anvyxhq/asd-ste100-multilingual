<div align="center">

# ASD-STE100 Multilingual Skill

**Viết lại văn bản kỹ thuật để agent, hệ thống và người đọc không thể hiểu sai — bằng nhiều ngôn ngữ.**

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

Skill này mang cùng nguyên tắc đó sang một kiểu người đọc khác: **AI agent**. Agent phải tự hiểu tool description, error message hay chỉ dẫn từ agent khác mà không có ai để hỏi lại, nên chỉ cần một câu hiểu được hai cách là agent có thể làm sai.

Ngôn ngữ nào cũng có câu mơ hồ, nhưng mỗi thứ tiếng mơ hồ theo một kiểu: tiếng Anh vướng phrasal verb, tiếng Việt vướng những từ ngắn nhiều nghĩa ("hay", "được", "rồi") và chữ viết không dấu, còn tiếng Nhật thường lược chủ ngữ. Vì thế repo được tổ chức thành **khung đa ngôn ngữ**: nguyên tắc chung nằm ở lõi, quy tắc riêng của từng thứ tiếng nằm trong một gói tách biệt.

## Ngôn ngữ hỗ trợ

| Ngôn ngữ | Mã | Quy tắc | Ví dụ | Linter |
|---|---|---|---|---|
| English | `en` | [`SKILL.md`](SKILL.md), [`references/writing-rules.md`](references/writing-rules.md) | [`examples/before-after.md`](examples/before-after.md) | ✅ |
| Tiếng Việt | `vi` | [`languages/vi/rules.md`](languages/vi/rules.md), [văn phong tài liệu](languages/vi/style-docs.md) | [`languages/vi/examples.md`](languages/vi/examples.md) | ✅ |
| Ngôn ngữ khác | — | Chỉ áp dụng quy tắc chung | — | Quy tắc chung |

Ngôn ngữ chưa có gói riêng vẫn dùng được. Khi đó skill chỉ áp dụng các quy tắc chung (mỗi câu một chỉ dẫn, nêu rõ ai làm, không lược thành phần câu, giữ nguyên các từ chỉ mức độ chắc chắn như "có thể", "có lẽ") và báo cho bạn biết.

Muốn thêm một ngôn ngữ? Xem [`languages/README.md`](languages/README.md).

## Trước / Sau

**Tiếng Việt**

| Trước | Sau |
|---|---|
| Đã có lỗi có thể xảy ra trong quá trình xử lý yêu cầu của bạn do sự không khớp về định dạng dữ liệu, điều này có thể là do phiên bản client đã cũ. | Yêu cầu của bạn có thể đã thất bại. Nguyên nhân có thể là định dạng dữ liệu không khớp với định dạng máy chủ cần. Phiên bản client cũ có thể gây ra lỗi không khớp này. Kiểm tra phiên bản client của bạn. |

**English**

| Before | After |
|---|---|
| An error may have occurred while processing your request due to a possible mismatch in the expected data format, which could be caused by an outdated client version. | Your request may have failed. The cause may be a data format that does not match what the server expects. An outdated client can cause this mismatch. Check your client version. |

Error message là văn bản cho agent đọc, nên bản viết lại theo mức Strict: câu ngắn, lặp lại danh từ để không ai hiểu nhầm. Các từ chỉ mức độ chắc chắn ("có thể", "may") vẫn được giữ nguyên, vì mức độ chắc chắn cũng là nội dung chứ không phải chữ thừa.

## Tính năng

| | |
|---|---|
| **Đa ngôn ngữ** | Tự nhận diện ngôn ngữ đầu vào. Viết lại bằng đúng ngôn ngữ đó, không tự dịch. |
| **Hai mức văn phong** | **Strict** cho văn bản agent đọc: error message, tool description, chỉ dẫn. **Tự nhiên** cho văn bản người đọc: README, tài liệu, PR, báo cáo. |
| **Giữ mức độ chắc chắn** | Không bao giờ biến "có thể đã thất bại" thành "đã thất bại". Không thêm thông tin mà bản gốc không có. |
| **Đầu ra sạch** | Mặc định chỉ trả về văn bản đã viết lại. Yêu cầu "show the diff" để xem bảng quy tắc. |
| **Linter** | Python 3, chỉ dùng thư viện chuẩn, không gọi mạng. Kiểm tra được tài liệu trộn nhiều ngôn ngữ. |
| **Văn phong tài liệu** | Viết tài liệu và báo cáo tiếng Việt như kỹ sư Việt viết: dùng thuật ngữ theo cách dev Việt thật sự viết (số liệu từ 156 bài, xem [`evidence.md`](languages/vi/evidence.md)), nối ý bằng từ nối thay vì câu cụt, tiêu đề không viết hoa mọi chữ. Xem [`languages/vi/style-docs.md`](languages/vi/style-docs.md). |
| **Dễ mở rộng** | Thêm một thứ tiếng chỉ cần một thư mục tài liệu và một mục trong registry của linter. |

## Cài đặt

**Cách 1 — skills CLI** (cho một project):

```bash
npx skills add anvyxhq/asd-ste100-multilingual
```

CLI gửi telemetry ẩn danh khi cài đặt. Đặt `DISABLE_TELEMETRY=1` để tắt.

**Cách 2 — clone** (cho mọi project trên máy):

```bash
git clone https://github.com/anvyxhq/asd-ste100-multilingual ~/.claude/skills/asd-ste100
```

Cập nhật bằng `git pull`.

## Sử dụng

Trong Claude Code, dán văn bản kèm yêu cầu bằng bất kỳ thứ tiếng nào:

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
python3 scripts/ste-lint.py --profile docs README.md  # văn bản cho người đọc: nới giới hạn câu
python3 scripts/ste-lint.py --json --baseline 5 docs/
python3 scripts/ste-lint.py --selftest
```

Kết quả mẫu:

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

Mặc định linter dùng profile `strict`, dành cho văn bản agent đọc. Với README, tài liệu hay báo cáo, hãy dùng `--profile docs`. Profile này nới giới hạn câu tiếng Việt lên 45 âm tiết và không cảnh báo "hay" theo nghĩa "hoặc". Dấu chấm phẩy, từ quảng cáo và cụm từ đệm cũng chỉ còn là cảnh báo. Các mức này được chỉnh theo [số liệu từ 102 bài viết tay](languages/vi/evidence.md) của dev Việt. Các từ chỉ mức độ chắc chắn ("may", "might", "có thể", "có lẽ") không bao giờ bị báo lỗi.

Danh sách quy tắc: tiếng Anh xem [`README.en.md`](README.en.md), tiếng Việt xem [`languages/vi/rules.md`](languages/vi/rules.md#kiểm-tra-bằng-linter).

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
│       ├── evidence.md        # số liệu từ 156 bài viết của dev Việt
│       └── examples.md        # ví dụ tiếng Việt
├── scripts/
│   └── ste-lint.py            # linter, registry ngôn ngữ trong LANGUAGES
├── README.md                  # tài liệu này
└── README.en.md               # README tiếng Anh (gốc)
```

## Phạm vi và giới hạn

**Dùng cho:** tin nhắn giữa các agent, tool/function description, error message, system prompt, thông báo trạng thái.

**Không dùng cho:** văn sáng tác, văn quảng cáo hoặc bất kỳ văn bản nào mà giọng văn là mục đích.

**Giới hạn:**

- Skill sửa cách viết chứ không sửa nội dung: một đoạn không có gì để nói thì viết lại vẫn rỗng, chỉ gọn hơn thôi.
- Giấy phép của ASD-STE100 không cho phân phối lại bộ từ điển khoảng 900 từ, nên skill không kèm từ điển đó và quy tắc từ vựng chỉ mang tính định hướng.
- ASD chỉ định nghĩa STE cho tiếng Anh, nên mọi bản cho thứ tiếng khác đều là **chuyển thể không chính thức**.
- Đây không phải công cụ biên soạn STE có chứng nhận. Nếu viết tài liệu bảo trì máy bay thật, hãy dùng chuẩn gốc.

## Đóng góp

Đóng góp đáng giá nhất là **thêm thứ tiếng mới**. Bạn viết quy tắc và ví dụ, thêm một mục vào registry `LANGUAGES` của linter rồi chạy `--selftest`. Chi tiết ở [`languages/README.md`](languages/README.md).

Muốn sửa quy tắc của thứ tiếng đã có, hãy sửa trong `scripts/ste-lint.py`, thêm ca kiểm thử vào `selftest()` và cập nhật bảng quy tắc trong `languages/<mã>/rules.md`.

Dù sửa gì, nguyên tắc cốt lõi vẫn giữ nguyên: **không bao giờ báo lỗi hay xóa từ chỉ mức độ chắc chắn**.

## Ghi công

Repo được fork từ [danyuchn/asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill) của Dustin Yuchen Teng. Bộ quy tắc tiếng Anh, linter gốc và phần parse Markdown là công của tác giả gốc.

Một số bản chuyển thể độc lập khác có thể gộp vào `languages/` sau này: [tiếng Hebrew](https://github.com/g4lb/asd-ste100-hebrew-skill) · [tiếng Indonesia](https://github.com/jshsinaga/asd-ste100-indonesian-skill)

## Giấy phép

MIT — xem [LICENSE](LICENSE).
