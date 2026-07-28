# WORKLIST.md — thứ tự dịch Princes of Darkness

Danh sách công việc theo thứ tự. **Làm từ trên xuống, không nhảy bậc.**

- Quy tắc kỹ thuật → [TRANSLATION_RULES.md](TRANSLATION_RULES.md)
- Từ điển thuật ngữ → [TERMINOLOGY.md](TERMINOLOGY.md)
- Chính sách dịch → [README.md](README.md)
- Cấu trúc repo → [CLAUDE.md](CLAUDE.md)

Cập nhật lần cuối: 2026-07-28 (đợt 17 — **việc #12 HOÀN TẤT 57/57 file**. Việc tiếp theo: quay lại thứ tự gốc, làm việc #10 `buildings/`).

---

## ✅ VIỆC #12 HOÀN TẤT (2026-07-28, đợt 17) — quay lại thứ tự gốc: #10 rồi #11

**Việc #12** (root-level `*.yml` còn lại, 57 file trừ `nicknames_POD_l_english.yml` tách riêng ngoài phạm vi) đã dịch xong hoàn toàn: 13 file SKIP + 6 file MOSTLY SKIP + 38/38 file TRANSLATE. 6 file lớn cuối cùng (`single_combat_POD` 1988 dòng, `POD_regiments` 729 dòng, `struggle_POD` 490 dòng, `game_POD_rules` 466 dòng, `schemes_POD` 377 dòng, `POD_coterie` 372 dòng) đã dịch xong trong đợt 17, mỗi file qua 3-7 agent chia đoạn + coordinator merge bằng Python (đối chiếu key-tuần-tự, dòng trống byte-for-byte, token count, `Glossary()`/`UmbraGlossaryLocalized()` multiset với `git show HEAD`). Chi tiết từng file → TERMINOLOGY.md `B12-single-combat`, `B12-regiments`, `B12-struggle`, `B12-rules`, `B12-schemes`, `B12-coterie`.

**Bài học lớn nhất đợt 17:** tên Discipline (Potence/Celerity/Fortitude/Dominate/Oblivion...) phải giữ nguyên tiếng Anh **ngay cả khi nằm lồng giữa câu văn xuôi** ("with the power of Celerity") — nhiều agent có xu hướng dịch nghĩa khi gặp dạng này dù đã biết quy tắc chung. Từ `single_combat_POD` (2/7 agent mắc lỗi) đến `POD_regiments` (0 lỗi sau khi thêm cảnh báo cụ thể vào prompt) cho thấy cảnh báo rõ ràng, cụ thể trong prompt thực sự hiệu quả.

**2 việc nợ lại — CHƯA làm, cần xử lý khi có dịp đụng lại các file liên quan:**
1. `game_POD_concepts_l_english.yml:66` — tách bạch Blood Magic (lifestyle, "Chú Thuật Huyết Mạch")/Blood Sorcery (Discipline, "Huyết Thuật") đang dùng chung 1 bản dịch. Xem `B12-effects`.
2. **Xung đột thuật ngữ "the Embrace" chưa thống nhất toàn repo** — 4 bản dịch tồn tại song song (Trao truyền/Hiến Máu/Sự Ôm Ấp, xem `B12-struggle` để biết file nào dùng bản nào). Người dùng đã chọn **"Trao truyền"** làm chuẩn cho file MỚI, nhưng các file cũ (`game_POD_concepts`, `effects_POD`, `POD_journeys`, `interactions/POD_character_interactions_vampire`, `POD_ashirra`, `interactions/POD_character_interactions_numina`) CHƯA được sửa lại. Cần hỏi người dùng có muốn dành 1 đợt riêng thống nhất toàn repo không.

**Việc tiếp theo theo đúng thứ tự gốc: #10 (`buildings/`, 6.309 key, 8 file — có hậu tố `:0` trong `building_grand_city_POD_l_english.yml`, cẩn thận không đổi), rồi #11 (`artifacts/`).**

---

## Tình hình

| | Số liệu |
|---|---|
| Tổng cộng | **460 file, 104.366 dòng** |
| Đã xong hoàn toàn | **6 file traits/** + **36/36 file religion/** + **6/6 file custom_localization/** + **30/30 file gui/ (việc #4 HOÀN TẤT)** + **28/28 file interactions/ (việc #5 HOÀN TẤT)** + **11/11 file decisions/ (việc #6 HOÀN TẤT)** + **54/54 file modifiers/ (việc #7 HOÀN TẤT)** + **27/27 file lifestyles/ (việc #8 HOÀN TẤT)** + **4/4 file root-level ưu tiên (việc #9 HOÀN TẤT)** + **57/57 file việc #12 (13 SKIP + 6 MOSTLY SKIP + 38/38 TRANSLATE) — việc #12 HOÀN TẤT** |
| Việc tiếp theo | **Việc #10 (`buildings/`, 6.309 key, 8 file)** |

## ✅ ĐÃ XONG — đừng dịch lại

| File | Trạng thái | Commit |
|---|---|---|
| `glossary_POD_l_english.yml` | 105/105 key | `fb969bd` `81cbd59` `18a6716` |
| `custom_localization/POD_misc_custom_loc_l_english.yml` | 121/121 key | `152c52c` |
| `custom_localization/insult_POD_custom_loc_l_english.yml` | 272/272 dòng — **xong cả file** | `1c28cc3` |
| `custom_localization/POD_signature_weapon_custom_loc_l_english.yml` | 31/31 dòng — **xong cả file** | `bd3b4d0` |
| `custom_localization/POD_resonance_custom_loc_l_english.yml` | 30/30 dòng — **xong cả file** | `642e27f` |
| `custom_localization/secrets_POD_custom_loc_l_english.yml` | 177/177 dòng — **xong cả file** | `6d6b2f4` |
| `custom_localization/POD_modifier_custom_loc_l_english.yml` | 38 dòng — 100% script reference, không có gì để dịch | *(không sửa, không commit)* |
| `traits/traits_predator_types_POD_l_english.yml` | 48/48 dòng, 30/30 key — **xong cả file** | `9701e54` |
| `traits/POD_fae_traits_l_english.yml` | 330/330 dòng, 241 key — **xong cả file** | `94e6593` |
| `traits/POD_fera_traits_l_english.yml` | 479/479 dòng — **xong cả file** (18 tên tộc + 16 desc từ trước, phần còn lại ~223 key) | `9d4ba47` + `2481866` |
| `traits/traits_POD_l_english.yml` | **1563/1563 dòng — xong cả file** | `a88f55d` `c05c30d` + 6 đợt dòng 600→1563 |

### `traits_POD_l_english.yml` — HOÀN TẤT 100%

File lớn nhất trong `traits/` (1563 dòng). Toàn bộ: tên splat, mọi clan/bloodline/lineage VtM, Dị năng (Discipline) và Huyết Thuật, torpor, Thế Hệ 1-16, bloodline phụ (Nagaraja/Hecata/Impundulu/Lamia/Anda/Ahrimane), trait "làm gương" theo clan, Đẳng Cấp Salubri, Inquisition (orison/oculi/acre/Murnau/Sisters/Red/Holy Alliance), Pháp Môn Kuei-Jin 0-10, Khí Thuật, Mummy (Shemsu-Heru/Cabiri/Wu Tian/Wu Kuei), bệnh ma cà rồng + bệnh WoD khác, Wraith (Spectre castes, Arcanos, Corpus/Fetter/Skinlands), Fallen/Earthbound/Demon, Anathema/Golconda, Ashen landless traits, thanh máu (wound track), Quỷ Học, Chén Thánh, Fleshcrafted.

Baseline cuối cùng khớp hoàn toàn với TRANSLATION_RULES.md §8: ref 305, bracket 501, icon 29, mở tag 75, đóng tag 88, `\n` 256, `\"` 0, dòng 1563, rawquote 2385.

**Việc #1 (toàn bộ `traits/`) đã xong.** Chuyển sang việc #2 (`religion/`).

---

## Thứ tự công việc

Sắp theo **đòn bẩy giảm dần**: việc trước là nguồn của việc sau. Làm sai thứ tự sẽ phải dịch lại.

### #1 — `traits/`  ✅ HOÀN TẤT — cả 4 file

Làm trước tiên vì trait được **hàng nghìn** chuỗi khác trỏ tới qua `[GetTrait('x').GetName]`. Tất cả 4 file (`traits_POD`, `POD_fera_traits`, `POD_fae_traits`, `traits_predator_types_POD`) đã dịch 100%.

### #2 — `religion/`  6.689 key, 36 file  — ✅ **HOÀN TẤT 36/36**

Ưu tiên cao vì **có 2 chỗ trỏ ngược về bước 1**, phải khớp:

- `kueijin_high_god_name` = "the August Personage of Jade" → **Ngọc Hoàng**
- `kueijin_devil_name` → `[Glossary('Demon Emperor',…)]` → **Ma Hoàng**
- 5 Pháp Môn (faith Kuei-Jin): `deviltigers_religion`=**Ma Hổ**, `boneflowers_religion`=**Ảnh Ca**, `resplendentcranes_religion`=**Thụy Hạc**, `thrashingdragons_religion`=**Đằng Long**, và **Cốt Hoa** là tên thứ hai của `boneflowers_religion` (KHÔNG phải faith thứ 5)
- Wyld / Weaver / Wyrm **giữ tiếng Anh** — `rf_wyrm`, `wyrm_religion_adj`, `doctrine_fera_triat_alignment_*_name`
- `gaia_devil_name` = `"$glossary_wyrm$"` → **không sửa**, đã có giá trị

Chi tiết ở TERMINOLOGY.md mục B3c.

### #3 — `custom_localization/`  ✅ HOÀN TẤT — cả 6 file

Nhỏ nhưng là nguồn của nhiều chuỗi khác. Toàn bộ 6 file đã xong: `POD_misc_custom_loc` (121/121 key), `insult_POD_custom_loc` (272/272 dòng), `POD_signature_weapon_custom_loc` (31/31 dòng), `POD_resonance_custom_loc` (30/30 dòng, chỉ 4 dòng có chữ thật), `secrets_POD_custom_loc` (177/177 dòng), `POD_modifier_custom_loc` (38 dòng — 100% script reference, xác nhận không có gì để dịch).

### #4 — `gui/`  4.458 key, 30 file

Text giao diện. **Giữ ngắn** — UI CK3 chật, tooltip dài sẽ vỡ layout. Có `:0` trong `gui/POD_hud_l_english.yml`.

### #5 — `interactions/`  3.780 key, 28 file — ✅ **HOÀN TẤT 28/28**
### #6 — `decisions/`  2.441 key, 11 file — ✅ **HOÀN TẤT 11/11**
### #7 — `modifiers/`  4.344 key, 54 file — ✅ **HOÀN TẤT 54/54**

### #8 — `lifestyles/`  6.740 key, 27 file — ⏸️ **26/27, còn `POD_wraith_lifestyle_l_english.yml` (1064 dòng)**

### #9 — 4 file ưu tiên từ root-level (tách ra làm sớm)  — ✅ **HOÀN TẤT 4/4**

**Quyết định 2026-07-27:** tách 4 file sau ra khỏi khối root-level (việc #12), đôn lên làm trước `buildings/` — vì đây là những thứ người chơi thấy sớm nhất và nhiều nhất khi mới vào ván (tên khái niệm tra cứu, phe phái, chính thể, tước vị):

- `game_POD_concepts_l_english.yml` — ✅ đã dịch (825/825 dòng)
- `factions_POD_l_english.yml` — ✅ đã dịch (23/23 dòng)
- `government_POD_l_english.yml` — ✅ đã dịch (555/555 dòng)
- `titles_POD_l_english.yml` — ✅ QUYẾT ĐỊNH KHÔNG DỊCH (toàn bộ tên tước vị/danh hiệu, giữ nguyên như base_game_vh)

### #10 — `buildings/`  6.309 key, 8 file — 🔜 **VIỆC TIẾP THEO**

Có `:0` trong `building_grand_city_POD_l_english.yml`.

### #11 — `artifacts/`  1.489 key, 4 file
### #12 — root-level `*.yml` còn lại  17.974 key, 58 file (đã tách 4 file sang việc #9) — ✅ **HOÀN TẤT 57/57** *(đã tách thêm `nicknames_POD_l_english.yml` ra ngoài phạm vi, không tính vào 57)*

Khối lớn thứ hai. Gồm `secrets_POD_l_english.yml` (có `:0`), `effects_POD`, `POD_regiments`, `single_combat_POD`, `struggle_POD`, `game_POD_rules`, `schemes_POD`, `POD_coterie`… Chi tiết đầy đủ → TERMINOLOGY.md các mục `B12-*`.

### #13 — `event_localization/`  20.530 key, 160 file — ⚠️ NGOẠI LỆ THỨ TỰ, làm trước #10/#11 theo yêu cầu người dùng 2026-07-28

**Khối lớn nhất.** Văn xuôi thuần, đòn bẩy thấp → để cuối theo thứ tự gốc, nhưng người dùng đã yêu cầu làm trước #10 (`buildings/`)/#11 (`artifacts/`) — giống ngoại lệ đã áp dụng cho việc #9/#12 trước đó. Sau khi xong #13, quay lại làm #10 rồi #11.

**Cấu trúc thật (đã khảo sát 2026-07-28):** 48 file trực tiếp trong `event_localization/` (~10.485 dòng, file lớn nhất `POD_canon_chars_l_english.yml` 2739 dòng, `POD_1230objectives_l_english.yml` 1370 dòng) + 29 thư mục con. Thư mục con lớn nhất: `schemes/` (19 file, ~3.338 dòng), `POD_journeys/` (14 file, ~1.796 dòng), `POD_1230endgame/` (5 file, ~1.728 dòng), `POD_umbra/` (2 file, ~1.329 dòng), `POD_chargen/` (1 file, ~1.345 dòng), `POD_disciplines/` (12 file, ~458 dòng), `POD_flavor/` (10 file, ~766 dòng), `POD_introductions/` (3 file, ~724 dòng), `POD_fera/` (6 file, ~450 dòng), `POD_wraith/` (8 file, ~294 dòng). Nhiều thư mục nhỏ ≤200 dòng (`POD_gehenna`, `POD_inquisition`, `POD_masquerade`, `POD_powers`, `POD_interactions_misc`, `stress_events`, `secret_events`, `POD_negotiation`, `POD_numina`, `POD_gargoyles`, `POD_knights`, `POD_worldgen`, `POD_ghoul`, `POD_fae`, `POD_decisions`, `POD_sins`).

**Quy trình đề xuất:**
1. Xử lý 48 file trực tiếp trong `event_localization/` trước (không phải thư mục con) — chia theo độ lớn giống các đợt trước: file khổng lồ (`POD_canon_chars` 2739 dòng, `POD_1230objectives` 1370 dòng) chia nhiều agent theo đoạn dòng trống; file vừa (100-700 dòng) mỗi file 1 agent chạy song song; file nhỏ (<100 dòng) coordinator tự dịch trực tiếp.
2. Sau đó xử lý từng thư mục con theo thứ tự lớn dần hoặc nhỏ dần tùy chọn — khuyến nghị làm các thư mục nhỏ trước để tích lũy tiến độ nhanh, dồn `schemes/`/`POD_journeys/`/`POD_1230endgame`/`POD_umbra`/`POD_chargen` (5 thư mục lớn nhất, tổng ~8.656 dòng) vào các đợt riêng cuối cùng.
3. **Tra TERMINOLOGY.md xuyên suốt trước khi dịch** — đây là văn xuôi event thuần, mật độ thuật ngữ đã chốt (Discipline giữ nguyên kể cả giữa câu, Embrace→Trao truyền, Torpor→Miên Trạng, Blood Hunt/Oath, True Faith, Feng Shui/Tzu Wei/Tapestry...) sẽ cao hơn hẳn các file rule/mechanic đã dịch ở việc #12.
4. Áp dụng đầy đủ bài học từ việc #12: cảnh báo rõ ràng về Discipline-name-in-prose, dòng trống 2 loại (rỗng/1-space), agent tự đối chiếu key-tuần-tự trước khi nộp, coordinator luôn tự chạy lại đối chiếu Glossary()/UmbraGlossaryLocalized() với `git show HEAD` chứ không tin báo cáo agent.
5. Đo lại baseline `grep -c ''` cho từng file trước khi chia đoạn — đừng tin số liệu ở bảng trên nếu nghi file đã đổi.
6. Nếu gặp mâu thuẫn thuật ngữ giữa 2 mục TERMINOLOGY.md → DỪNG LẠI, hỏi người dùng bằng AskUserQuestion trước khi merge.
7. Xong toàn bộ `event_localization/` (160 file) → việc #13 HOÀN TẤT → cập nhật WORKLIST.md → quay lại làm việc #10 (`buildings/`) rồi #11 (`artifacts/`) theo đúng thứ tự gốc.

### #14 — `bookmark/`  1.128 key, 1 file

Mô tả nhân vật mở đầu. Văn phong quan trọng — người chơi đọc đầu tiên.

### #15 — `replace/`  481 key, 6 file  ⚠️ CẨN TRỌNG — **TẠM BỎ QUA**

**Ghi đè key vanilla** → sửa ở đây là đổi luôn UI của CK3 gốc, đè lên bản dịch trong `base_game_vh`. Phần lớn là template tên (`CHARACTER_FIRST_NAME_AND_DYNASTY: "$NAME$"`) — **chỉ dịch dòng có chữ thật**. Có `:0`.

`POD_do_not_translate_this_l_english.yml` (cả bản trong `replace/`) → **bỏ qua cả file**.

**Quyết định 2026-07-27:** tạm bỏ qua toàn bộ khối này. Không dịch không gây lỗi kỹ thuật — chỉ để lại vài chục dòng tiếng Anh lẻ tẻ trong `pod_replace_artifact_modifiers_l_english.yml`, `pod_replace_fog_of_war_l_english.yml`, `pod_replace_vanilla_temporary_l_english.yml` (các file có chữ thật, không phải template tên). Sẽ quyết định có dịch tiếp hay không sau khi trải nghiệm game thực tế.

### #16 — `names/` `dynasties/`  6.528 key, 4 file  → **KHÔNG DỊCH**

Tên riêng. Để nguyên, giống cách `base_game_vh` xử lý tên vanilla. Liệt kê ở đây chỉ để khỏi ai tưởng bị bỏ sót.

---

## Quy trình bắt buộc cho mỗi file

### Trước khi sửa

```bash
f=<đường dẫn file>
grep -c ''                  "$f"   # tổng dòng
grep -cE '^[[:space:]]*$'   "$f"   # dòng trống
grep -cE '^ [A-Za-z_]'      "$f"   # key thụt đúng 1 space
grep -oE '[$][^$]*[$]'      "$f" | wc -l   # string ref
grep -oE '\[[^]]*\]'        "$f" | wc -l   # script/concept
grep -oE '@[a-z_0-9]+!'     "$f" | wc -l   # icon
grep -oF '#!'               "$f" | wc -l   # tag đóng
grep -oF '\n'               "$f" | wc -l   # xuống dòng
grep -oF '\"'               "$f" | wc -l   # dấu " lồng
```

Ghi lại các số này. Sau khi dịch phải **bằng nhau hết**.

### Sau khi sửa — 3 lớp

**1. Đếm lại** toàn bộ số trên.

**2. Kiểm tra định dạng** (formatter/script hay phá chỗ này):

```bash
grep -cE '^  [A-Za-z_]' "$f"      # key thụt 2 space — phải là 0
python -c "
d=open('$f','rb').read()
print('BOM',d[:3]==b'\xef\xbb\xbf')
print('loneLF',sum(1 for i,b in enumerate(d) if b==0x0A and (i==0 or d[i-1]!=0x0D)))  # phải 0
d.decode('utf-8')"
```

**3. Diff ID với HEAD** — đây là lớp mà đếm token KHÔNG bắt được:

```bash
for pat in "Get(Trait|Building)\('[^']*'\)" "UmbraGlossary(Localized)?\('[^']*'" \
           "#TOOLTIP:[A-Za-z_:]+(,[a-z_]+,)?" '\[[a-z_]+\|E\]' \
           '[$][A-Za-z_.]+[$]' '^ [A-Za-z_][A-Za-z0-9_.]*:'; do
  diff <(git show HEAD:"$f" | grep -oE "$pat" | sort) \
       <(grep -oE "$pat" "$f" | sort) >/dev/null && echo "OK $pat" || echo "SAI $pat"
done
```

> Mẫu `[$][A-Za-z_.]+[$]` là **bắt buộc**, không bỏ được. Đã thử phá thật: đổi `$pod_vitae$` thành `$pod_VITAE_SAI$` thì **số ref vẫn là 1** — đếm token không thấy gì, chỉ phép diff này báo `SAI`. Đây đúng là loại lỗi làm string biến mất khỏi game mà mọi con số vẫn khớp.

Rồi **tự đọc `git diff`**. Bắt buộc — 3 lỗi dưới đây làm mọi con số vẫn khớp.

### 3 lỗi mà self-check không bắt được

1. **Dịch sai tham số `Glossary()` / `UmbraGlossaryLocalized()`** — số bracket, ref không đổi, check pass, tooltip vỡ trong game.
2. **Đổi ID trong `'…'`** — `GetTrait('vampire')` → `GetTrait('ma_ca_rong')` vẫn đếm ra 1 bracket.
3. **Formatter/script phá định dạng** — đổi thụt đầu dòng, xóa dòng trống, biến `\"` thành `"`, biến `\n` thành newline thật.

---

## 6 cái bẫy đã có người sập

### 1. `UmbraGlossaryLocalized()` — thứ tự tham số NGƯỢC với `Glossary()`

```
[Glossary('Diablerie','game_concept_diablerie_desc')]   → tham số 1 = CHỮ, 2 = KEY
[UmbraGlossaryLocalized('yomi_wan','Yomi Hell')]        → tham số 1 = ID,  2 = CHỮ
```

**271 lần trong 50 file.** Có trong hầu hết mọi thư mục — `lifestyles/`, `event_localization/`, `religion/`, `modifiers/`, `gui/`, `interactions/`, `traits/`, `buildings/`, `bookmark/`, `artifacts/`, `decisions/`, `dynasties/`. Sai chiều = tooltip vỡ, self-check không thấy.

Anh em: `[UmbraGlossary('flag')]` — **một** tham số, là ID, **không dịch gì**.

### 2. Thao tác file phải BINARY THUẦN

Đọc `'rb'`, ghi `'wb'`. **Đã hỏng file hai lần** vì:

- đọc text-mode rồi ghi `newline=""` → 1563 CRLF thành LF, rewrite cả file;
- dãy `\n` trong chuỗi Python thành newline **thật** → 1 dòng vỡ thành 3.

Khi cần dấu `\n` văn bản, dựng bằng `chr(92)+"n"`, và `assert "\n" not in bản_dịch`.

### 3. Đừng dịch lại thứ đã có giá trị qua `$ref$`

`trait_fera` = `"$glossary_fera$"`, `gaia_devil_name` = `"$glossary_wyrm$"`. Dòng chỉ chứa một string reference thì **không có gì để dịch**.

### 4. Tag ghép `#L;bold`

Là **một** tag, đóng bằng **một** `#!`. Cả cụm `L;bold` là tên tag. Lệnh đếm tag mở `grep -oE '#[A-Za-z]+ '` **không khớp** nó → số tag mở nhỏ hơn tag đóng là **bình thường** ở file có tag ghép. Chỉ so tag mở của cùng file trước/sau.

### 5. Hậu tố `:0` — giữ y nguyên

**6 file** dùng `key:0 "value"`: `buildings/building_grand_city_POD`, `event_localization/POD_journeys/POD_heists`, `gui/POD_hud`, `religion/POD_religion_gaia`, `replace/pod_replace_vanilla`, `secrets_POD`. Không thêm, không bớt.

### 6. Lỗi chính tả của bản gốc — giữ KEY, sửa CHỮ

- Key `trait_supehunter` (thiếu chữ r) → **giữ nguyên key**.
- `Napolean` → viết `Napoleon` (POD viết đúng ở 4 chỗ khác).
- `Kuei-jin` → viết `Kuei-Jin` (POD: 25 lần đúng / 16 lần sai).
- Dấu tiếng Việt sai trong bản gốc: `Đai Viet`, `Trân`, `Đuc Thanh Hung Đao`, `Cà Đôc Duoc` → **khôi phục dấu đúng**.

---

## Cách làm việc

- **Từng đợt nhỏ, commit từng đợt.** Không có test, git là lưới an toàn duy nhất. Mỗi commit nêu rõ đã kiểm tra gì.
- **Tra TERMINOLOGY.md trước.** Chưa có thì tra `base_game_vh` bằng **key tiếng Anh** (chữ tiếng Anh đã bị ghi đè, chỉ còn key). Vẫn không có thì đặt từ mới và **ghi ngay vào TERMINOLOGY.md**.
- **Dạng chiếm đa số của base thắng.** Ví dụ đã tra: `Chaos`→"Hỗn loạn" (15 lần, 0 lần "Hỗn mang"), `spirit`→"linh hồn" (20), `Nho giáo` (16, không "Khổng giáo").
- **Không sửa** `base_game_vh/`, `simp_chinese/`, hay bất kỳ thứ gì ngoài `princesofdarkness/localization/english/`.
- **Không xóa** `.vscode/settings.json`, `.editorconfig`, `.gitattributes` — 3 lớp chặn formatter.
- Báo lại thuật ngữ mới đã đặt sau mỗi đợt.
