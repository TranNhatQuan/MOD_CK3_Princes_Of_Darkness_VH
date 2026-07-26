# WORKLIST.md — thứ tự dịch Princes of Darkness

Danh sách công việc theo thứ tự. **Làm từ trên xuống, không nhảy bậc.**

- Quy tắc kỹ thuật → [TRANSLATION_RULES.md](TRANSLATION_RULES.md)
- Từ điển thuật ngữ → [TERMINOLOGY.md](TERMINOLOGY.md)
- Chính sách dịch → [README.md](README.md)
- Cấu trúc repo → [CLAUDE.md](CLAUDE.md)

Cập nhật lần cuối: 2026-07-26.

---

## Tình hình

| | Số liệu |
|---|---|
| Tổng cộng | **460 file, 104.366 dòng** |
| Đã xong | **3 file** (glossary_POD, POD_misc_custom_loc, + 48 key splat trong traits/) |
| Còn lại | ~457 file, ~103.700 dòng |

Ba bước nền (glossary → custom_loc → tên splat) **đã hoàn tất**. Toàn bộ thuật ngữ gốc đã chốt trong TERMINOLOGY.md (~150 mục). Phần còn lại là **tra bảng và áp dụng**, không còn phải tự đặt thuật ngữ nền.

---

## ✅ ĐÃ XONG — đừng dịch lại

| File | Trạng thái | Commit |
|---|---|---|
| `glossary_POD_l_english.yml` | 105/105 key | `fb969bd` `81cbd59` `18a6716` |
| `custom_localization/POD_misc_custom_loc_l_english.yml` | 121/121 key | `152c52c` |
| `traits/` — **chỉ 28 tên splat + 36 key `_desc`** | xong phần splat | `9d4ba47` |

> ⚠️ `traits/` **chưa xong cả file** — còn ~1.660 key (xem việc #1).

---

## Thứ tự công việc

Sắp theo **đòn bẩy giảm dần**: việc trước là nguồn của việc sau. Làm sai thứ tự sẽ phải dịch lại.

### #1 — `traits/` phần còn lại  ~1.660 key, 4 file

Làm trước tiên vì trait được **hàng nghìn** chuỗi khác trỏ tới qua `[GetTrait('x').GetName]`.

| File | Dòng | Nội dung còn lại |
|---|---|---|
| `traits_POD_l_english.yml` | 1563 | Dị năng, thế hệ, trait tính cách, trait bệnh |
| `POD_fera_traits_l_english.yml` | 479 | trait phụ của Fera (đã xong 18 tên tộc + 16 mô tả) |
| `POD_fae_traits_l_english.yml` | 330 | kith Fae (đã xong `trait_fae`, `trait_changeling`) |
| `traits_predator_types_POD_l_english.yml` | 48 | kiểu kiếm ăn — **chưa dịch dòng nào** |

Chia nhỏ theo khối 100–150 key, commit từng đợt.

### #2 — `religion/`  6.689 key, 36 file

Ưu tiên cao vì **có 2 chỗ trỏ ngược về bước 1**, phải khớp:

- `kueijin_high_god_name` = "the August Personage of Jade" → **Ngọc Hoàng**
- `kueijin_devil_name` → `[Glossary('Demon Emperor',…)]` → **Ma Hoàng**
- 5 Pháp Môn (faith Kuei-Jin): `deviltigers_religion`=**Ma Hổ**, `boneflowers_religion`=**Ảnh Ca**, `resplendentcranes_religion`=**Thụy Hạc**, `thrashingdragons_religion`=**Đằng Long**, và **Cốt Hoa** là tên thứ hai của `boneflowers_religion` (KHÔNG phải faith thứ 5)
- Wyld / Weaver / Wyrm **giữ tiếng Anh** — `rf_wyrm`, `wyrm_religion_adj`, `doctrine_fera_triat_alignment_*_name`
- `gaia_devil_name` = `"$glossary_wyrm$"` → **không sửa**, đã có giá trị

Chi tiết ở TERMINOLOGY.md mục B3c.

### #3 — `custom_localization/` phần còn lại  ~510 key, 5 file

Nhỏ nhưng là nguồn của nhiều chuỗi khác. `POD_misc_custom_loc` đã xong.

### #4 — `gui/`  4.458 key, 30 file

Text giao diện. **Giữ ngắn** — UI CK3 chật, tooltip dài sẽ vỡ layout. Có `:0` trong `gui/POD_hud_l_english.yml`.

### #5 — `interactions/`  3.780 key, 28 file
### #6 — `decisions/`  2.441 key, 11 file
### #7 — `modifiers/`  4.344 key, 54 file

Tên modifier ngắn, lặp nhiều. Tra TERMINOLOGY.md phần A trước — phần lớn là thuật ngữ vanilla đã có bản dịch.

### #8 — `lifestyles/`  6.740 key, 27 file
### #9 — `buildings/`  6.309 key, 8 file

Có `:0` trong `building_grand_city_POD_l_english.yml`.

### #10 — `artifacts/`  1.489 key, 4 file
### #11 — root-level `*.yml`  17.974 key, 62 file

Khối lớn thứ hai. Gồm `secrets_POD_l_english.yml` (có `:0`), `effects_POD`, `POD_regiments`, `game_POD_concepts`…

`game_POD_concepts_l_english.yml` nên làm **sớm trong khối này** — nó chứa các key `_desc` mà `Glossary()` ở bước 1 trỏ tới.

### #12 — `event_localization/`  20.530 key, 160 file

**Khối lớn nhất.** Văn xuôi thuần, đòn bẩy thấp → để cuối. Chia theo thư mục con (`POD_chargen/`, `POD_umbra/`, `POD_wraith/`, `POD_gehenna/`, `schemes/`, `POD_journeys/`…), mỗi thư mục 1–2 commit.

### #13 — `bookmark/`  1.128 key, 1 file

Mô tả nhân vật mở đầu. Văn phong quan trọng — người chơi đọc đầu tiên.

### #14 — `replace/`  481 key, 6 file  ⚠️ CẨN TRỌNG

**Ghi đè key vanilla** → sửa ở đây là đổi luôn UI của CK3 gốc, đè lên bản dịch trong `base_game_vh`. Phần lớn là template tên (`CHARACTER_FIRST_NAME_AND_DYNASTY: "$NAME$"`) — **chỉ dịch dòng có chữ thật**. Có `:0`.

`POD_do_not_translate_this_l_english.yml` (cả bản trong `replace/`) → **bỏ qua cả file**.

### #15 — `names/` `dynasties/`  6.528 key, 4 file  → **KHÔNG DỊCH**

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
