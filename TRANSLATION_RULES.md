# TRANSLATION_RULES.md

Quy tắc kỹ thuật khi dịch file localization CK3 trong repo này.

- Chính sách dịch (ưu tiên thuật ngữ, văn phong) → [README.md](README.md)
- Cấu trúc repo, quy ước file → [CLAUDE.md](CLAUDE.md)
- Từ điển thuật ngữ cố định → [TERMINOLOGY.md](TERMINOLOGY.md)

---

## 1. Phạm vi được sửa

| Thư mục | Được sửa? |
|---|---|
| `princesofdarkness/localization/english/` | **Có** — đây là nơi duy nhất cần dịch |
| `base_game_vh/` | **Không** — chỉ đọc để tra cứu |
| `princesofdarkness/` (mọi thư mục khác: `common/`, `events/`, `gui/`, `gfx/`, `history/`…) | **Không** |
| `princesofdarkness/localization/simp_chinese/` và các ngôn ngữ khác | **Không** |
| `princesofdarkness/fonts/fonts.font` | **Ngoại lệ duy nhất** — xem dưới |

**Ngoại lệ font.** Cả hai mod đều ghi đè `fonts/fonts.font`. `base_game_vh` map `l_english` sang font có dấu tiếng Việt (Open Sans / Gitan / Fondamento); POD map `l_english` sang font trang trí (`cinzeldecorative-*.ttf`, `pirataone-regular.ttf`, `cabaletta.ttf`) nhiều khả năng thiếu dấu. Mod nào load sau thì thắng. Nếu vào game thấy chữ Việt **mất dấu hoặc hiện ô vuông**, sửa ở `fonts.font` của POD — **không phải** lỗi file `.yml`, đừng bỏ dấu để né.

Tiếng Việt được ghi đè trực tiếp lên tiếng Anh, giữ nguyên header `l_english:` và tên file `*_l_english.yml`. Không tạo thư mục `localization/vietnamese/` — game sẽ bỏ qua.

---

## 2. Quy tắc vàng

> **Chỉ đổi phần chữ mà người chơi đọc được, nằm bên trong dấu `"…"`. Mọi thứ còn lại giữ nguyên byte-for-byte.**

Cấu trúc một dòng:

```
 trait_diablerist_desc: "This character has committed $pod_diablerie$ by consuming the hearts blood."
 └┬┘└──────┬─────────┘└┬┘ └────────────┬────────────┘ └──────┬─────┘ └──────────┬──────────────┘
  │        │           │               │                     │                  │
  │      KEY         dấu :          dịch được          KHÔNG đổi              dịch được
  │   KHÔNG đổi     KHÔNG đổi
 thụt đầu dòng (giữ y nguyên)
```

Ngoại lệ duy nhất của quy tắc này: `Select_CString()` — xem mục 4.

---

## 3. Bảng token bảo vệ — tuyệt đối không sửa

Tất cả ví dụ dưới đây đều lấy từ file thật trong repo.

| Loại | Ví dụ thật | Ghi chú |
|---|---|---|
| **Localization key** | `trait_diablerist_desc:` | Đổi key = string biến mất khỏi game |
| **String reference** | `$pod_diablerie$`, `$NAME$`, `$NICK$`, `$TIER$`, `$game_concept_barter_goods$` | Trỏ tới key khác. Dịch nó = lỗi |
| **Data variable** | `$VALUE\|+0=$`, `$NUM\|V0$`, `$TIER\|E$` | Kể cả phần format sau dấu `\|` |
| **Script function** | `[Character.GetShortUIName]`, `[GetTrait('vampire').GetName(GetNullCharacter)]`, `[GetBuilding('tribe_01').GetName]` | Chuỗi trong `'…'` là ID script |
| **Concept link** | `[armies\|E]`, `[stewardship\|E]`, `[pod_clan\|E]` | Chữ trong ngoặc là **key**, không phải chữ hiển thị |
| **Icon** | `@gold_icon!`, `@artifact_icon!`, `@assamite_icon!`, `@skill_stewardship_icon!` | |
| **Format tag** | `#V …#!`, `#T …#!`, `#S …#!`, `#L …#!`, `#weak …#!`, `#flavor …#!`, `#bold …#!`, `#italic …#!` | Từ ngay sau `#` là tên tag |
| **Tooltip inline** | `#TOOLTIP:GAME_TRAIT,fae,[GetNullCharacter] #L Fae#!#!`, `#TOOLTIP:BUILDING,glade_freehold_ …#!` | Có trong **59 file** POD. Phần sau `#TOOLTIP:` đến hết dấu phẩy cuối là ID script — chỉ dịch chữ nằm sau nó (`Fae`) |
| **Điều kiện** | `[AddLocalizationIf( GreaterThan_int32( … ), 'MODIFIER_PREVIOUS_LEVELS_APPLY_NEWLINE' )]` | |
| **Xuống dòng** | `\n`, `\n\n` | Không thay bằng Enter thật |
| **Dấu " lồng nhau** | `#weak \"Câu trích dẫn.\"#!` | Giữ nguyên `\"` — 29 file POD dùng cách này |

### Về `§Y`

Cú pháp `§Y…§!` là của Stellaris/HOI4, **không dùng trong CK3**. Repo này có **0 lần xuất hiện** ký tự `§` ở cả hai cây thư mục. Tag màu trong CK3 là `#Y …#!`. Nếu gặp `§` ở đâu đó thì cứ giữ nguyên, nhưng đừng tự thêm vào.

---

## 4. `[Glossary('…','…')]` — cái bẫy hay gặp nhất

POD dùng rất nhiều wrapper glossary. Cú pháp có **hai tham số với vai trò khác nhau**:

```
pod_diablerie: "[Glossary('Diablerie','game_concept_diablerie_desc')]"
                          └────┬────┘ └───────────┬──────────────┘
                        chữ HIỂN THỊ            KEY tooltip
                          → DỊCH              → KHÔNG DỊCH
```

Đúng:
```
pod_diablerie: "[Glossary('Diablerie','game_concept_diablerie_desc')]"
```

Sai (dịch nhầm tham số 2, tooltip sẽ vỡ):
```
pod_diablerie: "[Glossary('Diablerie','mô tả diablerie')]"
```

> `base_game_vh` có sẵn **một lỗi loại này** tại `game_concepts_l_english.yml:614` — `[Glossary('rattan', 'MÂY TRE')]`. Đừng bắt chước.

### Nhưng key `_tt` thì PHẢI dịch

Đừng nhầm hai việc. Tham số 2 chỉ là cái *tên* để trỏ đi — không dịch. Nhưng dòng định nghĩa của chính key đó là văn xuôi thật, phải dịch:

```
 glossary_clan_curse:    "[Glossary('Clan Curse', 'glossary_clan_curse_tt')]"
                                                  └──────────┬──────────┘
                                                   tên key → KHÔNG dịch
 glossary_clan_curse_tt: "A Clan Curse is a supernatural limitation…"
 └──────────┬─────────┘   └──────────────────┬──────────────────────┘
   cùng cái tên đó         nhưng đây là nội dung → PHẢI dịch
```

`glossary_POD_l_english.yml` có 40 dòng key = **28 shortcut** `Glossary()` + **12 key `_tt`** chứa nội dung tooltip.

### `Select_CString()` — ngược lại với `Glossary()`

Có trong **23 file** POD. Ở hàm này, chuỗi trong `'…'` **có thể là chữ hiển thị**, khác hẳn `Glossary()`:

```
[Select_CString( bomkazi_candidate.IsFemale, 'sister', 'brother' )]   → 'sister'/'brother' là CHỮ, phải dịch
[Select_CString( IsInGame, GuiScope.Custom('POD_colosseum_loc') … )]  → 'POD_colosseum_loc' là ID, không dịch
```

Cách phân biệt: nếu chuỗi là **từ tiếng Anh thường** (`'sister'`, `'brother'`) → dịch. Nếu là **snake_case có tiền tố / trông như key** (`'POD_colosseum_loc'`, `'POD_can_start_travel_phase_sgui'`) → giữ nguyên. Nghi ngờ thì `grep` chuỗi đó xem có phải là key ở file khác không.

> Cấu trúc `IsFemale, 'sister', 'brother'` giả định ngôn ngữ phân biệt giống. Tiếng Việt phải chọn theo ngữ cảnh (`'chị'`/`'anh'` hay `'em gái'`/`'em trai'`) — đọc event xung quanh để biết vai vế, đừng dịch máy móc thành `'chị gái'`/`'anh trai'` ở mọi chỗ.

### Dịch glossary trước

File [glossary_POD_l_english.yml](princesofdarkness/localization/english/glossary_POD_l_english.yml) và [custom_localization/POD_misc_custom_loc_l_english.yml](princesofdarkness/localization/english/custom_localization/POD_misc_custom_loc_l_english.yml) (chứa các `POD_splat_*`) là nguồn của hàng nghìn chuỗi khác thông qua `$pod_*$` và `$POD_splat_*$`. **Dịch hai file này đầu tiên** thì thuật ngữ tự lan ra toàn mod và không bị lệch.

⚠️ `POD_splat_*` **không chứa chữ** — chúng trỏ `[GetTrait('vampire').GetName(…)]`. Muốn đổi cách gọi một chủng loài trên toàn mod thì sửa `trait_vampire` trong [traits/](princesofdarkness/localization/english/traits/), **không** sửa `POD_splat_vampire`.

---

## 5. File / dòng KHÔNG được dịch

- [POD_do_not_translate_this_l_english.yml](princesofdarkness/localization/english/POD_do_not_translate_this_l_english.yml) và bản sao trong `replace/` — *giá trị* là định danh script (`"potence_visible"`, `"always_yes_gui"`), GUI đọc trực tiếp. Bỏ qua cả file.
- Dòng chỉ chứa string reference: `feature_book_title_stewardship: "$stewardship_old_ledger_name$"` — không có gì để dịch.
- Template tên nhân vật trong [replace/pod_replace_vanilla_l_english.yml](princesofdarkness/localization/english/replace/pod_replace_vanilla_l_english.yml): `CHARACTER_FIRST_NAME_AND_DYNASTY: "$NAME$"`. Chỉ dịch những dòng thật sự có chữ (ví dụ `"$NICK$ $TIER$ $NAME$ of $TITLE$"` → chữ `of`).
- Dòng comment bắt đầu bằng `#` ở đầu dòng (kể cả key bị comment như `#trait_cultist: "Demonic Cultist"`). Giữ nguyên.
- Tên riêng trong `names/`, `dynasties/`, `bookmark/` — theo cách `base_game_vh` xử lý tên vanilla: để nguyên.

> ⚠️ Thư mục `replace/` **ghi đè key vanilla**. Sửa ở đây là sửa luôn giao diện CK3 gốc, đè lên bản dịch trong `base_game_vh`. Cân nhắc kỹ.

---

## 6. Vệ sinh file

| Mục | Yêu cầu |
|---|---|
| Encoding | UTF-8 **có BOM** (`EF BB BF`). Mất BOM → CK3 không đọc được file |
| Line ending | POD dùng **CRLF**. Giữ nguyên, đừng chuyển sang LF |
| Header | Dòng đầu luôn là `l_english:` (sau BOM) |
| Thụt đầu dòng | **Giữ y nguyên dòng gốc.** Đa số là 1 space, nhưng POD có 349 key sát lề, 168 key thụt 2+ space và 3 dòng dùng tab. Đừng "chuẩn hóa" |
| Hậu tố version | **Giữ y nguyên dòng gốc.** Đa số POD viết `key: "value"` không số, nhưng có **55 key dùng `:0`** (trong `buildings/`, `gui/POD_hud`, `religion/POD_religion_gaia`, `replace/pod_replace_vanilla`, `secrets_POD`). Không thêm, không bớt |
| Key | Không thêm key mới, không xóa, không đổi thứ tự |
| Dòng trống, comment | Giữ nguyên như file gốc |
| Số dòng | File sau khi dịch phải có đúng số dòng như trước |

---

## 7. Quy tắc tiếng Việt

- **Dấu đầy đủ.** Không viết không dấu, không teencode, không viết tắt.
- **Không hiện đại hóa.** Giữ giọng trung cổ/gothic như `base_game_vh`. Tránh từ hiện đại ("OK", "deal", "quản lý dự án"…).
- **Viết hoa.** Theo `base_game_vh`: tên khái niệm game viết hoa chữ đầu mỗi từ chính (`Uy quyền Quân chủ`, `Hợp đồng Chư hầu`, `Cấp độ Căng thẳng`); câu văn thường thì viết hoa bình thường.
- **Dấu câu.** Giữ nguyên `…`, `—`, `:`; không đổi `"` thành `“”` bên trong chuỗi.
- **Một thuật ngữ = một bản dịch.** Xem [TERMINOLOGY.md](TERMINOLOGY.md). Không luân phiên đồng nghĩa.
- **Độ dài.** UI CK3 chật; tên nút/tooltip ngắn nên giữ ngắn tương đương tiếng Anh.
- **Số nhiều.** CK3 tách key số ít / số nhiều (`game_concept_vassal` / `game_concept_vassals`). Tiếng Việt không biến đổi từ → mặc định **dịch cả hai giống nhau**, như base làm với "Chư hầu". Base có vài chỗ thêm "Các" (`game_concept_artifacts` = "Các Hiện vật") nhưng đó là thiểu số — chỉ thêm khi câu văn thật sự cần, đừng làm theo thói quen.
- **`|U` và các format sau `\|`.** `[CHARACTER.GetFirstNameNoTooltip\|U]` ép viết hoa chữ đầu — tiếng Việt không cần, nhưng **vẫn phải giữ tag**. Xóa nó là đổi hành vi script.

---

## 8. Quy trình cho mỗi file

1. Đọc trọn file tiếng Anh trước khi sửa.
2. Với mỗi thuật ngữ: tra [TERMINOLOGY.md](TERMINOLOGY.md) → nếu chưa có, tra `base_game_vh` bằng **key tiếng Anh** (chữ tiếng Anh đã bị xóa khỏi cây đó, chỉ còn key) → nếu vẫn không có, đặt từ mới và **ghi ngay vào TERMINOLOGY.md**.
3. Dịch, giữ nguyên toàn bộ token ở mục 3.
4. Tự kiểm tra trước khi lưu.

### Tự kiểm tra

So sánh file trước/sau, các con số này phải **bằng nhau**:

```bash
f=princesofdarkness/localization/english/traits/traits_POD_l_english.yml
grep -oE '[$][^$]*[$]' "$f" | wc -l   # string reference
grep -oE '\[[^]]*\]'   "$f" | wc -l   # script / concept link
grep -oE '@[a-z_]+!'   "$f" | wc -l   # icon
grep -oE '#[A-Za-z]+ ' "$f" | wc -l   # mở tag format
grep -oF '#!'          "$f" | wc -l   # đóng tag format
grep -oF '\n'          "$f" | wc -l   # xuống dòng
grep -oF '\"'          "$f" | wc -l   # dấu " lồng nhau
grep -c  ''            "$f"           # tổng số dòng
head -c 3 "$f" | xxd -p                # phải ra efbbbf
```

Nếu lệch bất kỳ con số nào → đã làm hỏng một token, sửa lại trước khi lưu.

> Dùng `-F` (khớp chuỗi thô) cho `\n`, `\"`, `#!` và `-E` cho phần còn lại. Đừng viết `grep -o '\\n'` — tùy shell mà backslash bị nuốt, khi đó pattern thành `n` và đếm ra **6850** thay vì **256** trên chính file ví dụ trên.

Số liệu tham chiếu của `traits_POD_l_english.yml` (bản tiếng Anh gốc, để đối chiếu khi thử lệnh): ref `305`, bracket `501`, icon `29`, mở tag `75`, đóng tag `88`, `\n` `256`, `\"` `0`, dòng `1563`.
