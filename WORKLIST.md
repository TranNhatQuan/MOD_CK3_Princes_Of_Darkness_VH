# WORKLIST.md — thứ tự dịch Princes of Darkness

Danh sách công việc theo thứ tự. **Làm từ trên xuống, không nhảy bậc.**

- Quy tắc kỹ thuật → [TRANSLATION_RULES.md](TRANSLATION_RULES.md)
- Từ điển thuật ngữ → [TERMINOLOGY.md](TERMINOLOGY.md)
- Chính sách dịch → [README.md](README.md)
- Cấu trúc repo → [CLAUDE.md](CLAUDE.md)

Cập nhật lần cuối: 2026-07-27.

---

## Tình hình

| | Số liệu |
|---|---|
| Tổng cộng | **460 file, 104.366 dòng** |
| Đã xong hoàn toàn | **6 file**: glossary_POD, POD_misc_custom_loc, traits_predator_types_POD, POD_fae_traits, POD_fera_traits, **traits_POD** (mới xong) |
| Còn lại | ~454 file khác |

Ba bước nền (glossary → custom_loc → tên splat) **đã hoàn tất**. Toàn bộ thuật ngữ gốc đã chốt trong TERMINOLOGY.md (~150 mục, đã bổ sung B4b–B4j cho Fae/Fera/VtM/Wraith/Mummy/Kuei-Jin). Phần còn lại là **tra bảng và áp dụng**, không còn phải tự đặt thuật ngữ nền.

**Việc #1 (`traits/`) đã HOÀN TẤT — cả 4 file trong thư mục này đã xong 100%.** Việc tiếp theo là **#2 — `religion/`** (xem chi tiết bên dưới). Đừng nhảy bậc sang #3 trở đi trước khi xong `religion/`.

**Việc #2 (`religion/`) tiến độ: 27/36 file đã dịch + verify + commit.** Danh sách commit theo thứ tự: `2952a68`(kueijin) `5b9051f` `50b5f57`(framework+unexamined_horizons) `dbc28f0`(roadoflaibon) `7354a25`(ghoul+ashirra+ignorance) `2ed606c`(POD_religion_l — file neo thứ 2) `2fd168c` `917b421`(calomenasforsaken) `2f2943f`(talmahera+naktanchara+codeoftremere+hunter) `6126548`(bloodgnosticism) `8f196bc` `0fe45f0`(roadofblood) `30c2110`(roadofset) `8aef336`(roadoflilith) `f9a2fb5`(raktasadhus) `b10442b`(roadofbones) `3fa8ac8`(vampirespecialdoctrines) `8825ac1` `4b6a855`(roadofbeast) `6993ff4`(roadofheaven) `644bcc8`(roadofmetamorphosis) `f510d34`(roadofhumanity) `3e786fb`(roadofkings) `512ce7d`(sửa nốt roadofbeast) `74a8443`(roadofsin) `d5d2cd7`(TERMINOLOGY.md bổ sung B3x/B4k/B4l).

**Còn 9 file chưa dịch:** `demons`(141 dòng), `docrtineandtenets`(1652 dòng — lớn nhất, để cuối cùng), `fae`(566 dòng), `gaia`(860 dòng), `mummy`(119 dòng), `ordos`(119 dòng), `roadofzarathustra`(117 dòng), `wraiths`(750 dòng), `wyrm`(243 dòng), `modern`(124 dòng).

### ⚠️ BÀN GIAO GIỮA SESSION (2026-07-27, do vượt ~400k token context)

Toàn bộ lô 6 file (`roadofbeast`, `roadofheaven`, `roadofhumanity`, `roadofkings`, `roadofmetamorphosis`, `roadofsin`) đã dịch xong, verify xong, commit xong **trong chính session này** trước khi bàn giao — session mới bắt đầu sạch, **không có agent nào dở dang, không cần resume gì cả**. Đã phát hiện và sửa 3 lỗi trong đợt verify này (ghi lại để session sau rút kinh nghiệm, các lỗi này lặp đi lặp lại nên rất đáng chú ý):
- `roadofbeast`: agent tự thêm `$pod_Embrace$` mới (không có trong bản gốc) khi dịch động từ "Embraced" → sửa lại thành văn xuôi thường "chỉ Trao truyền". Sau đó phát hiện thêm 1 dòng "World of Darkness" bị bỏ sót (agent tự sửa tiếp sau khi tôi đã commit, phải commit thêm lần nữa).
- `roadofmetamorphosis`: bắt gặp giữa lúc agent đang ghi đè file → có khoảnh khắc file **mất BOM và CRLF→LF** (đúng kiểu lỗi nguy hiểm nhất theo TRANSLATION_RULES.md §6) — nhưng agent tự sửa lại đúng trước khi kết thúc, verify lại lần 2 mới thấy ổn. **Bài học: nếu bắt gặp file mất BOM/CRLF giữa chừng lúc agent còn đang chạy, đợi agent ghi xong rồi kiểm tra lại, đừng vội kết luận lỗi.**
- `POD_religion_vampirespecialdoctrines` (đã xong trước lô này): agent giữ nguyên "Theurgist"/"Theurgy" trong văn xuôi vì tưởng trait chưa dịch — thực ra `trait_theurgist`="Nhà Thần Thuật" đã chốt ở B4h từ lâu. Bài học: **luôn grep `traits/traits_POD_l_english.yml` để xác nhận trạng thái dịch của trait được nhắc tới trong file khác, đừng tin agent tự đánh giá "chưa chốt".**
- `roadofkings`: agent tự báo cáo đã sửa lỗi tự thêm `$pod_cainite$` mới khi dịch từ "Cainite" bare — đã tự phát hiện và tự sửa trước khi báo cáo, không cần coordinator can thiệp thêm, nhưng vẫn nên double-check khi verify các file `roadof*` còn lại.
- ⚠️ **`roadofsin`: agent tự báo cáo SAI rằng `religion/POD_religion_docrtineandtenets_l_english.yml` "đã hoàn tất 100%"** và dùng file đó làm tiền lệ để giữ nguyên "Sire". Đã kiểm tra lại bằng `grep` trực tiếp nội dung file — **`docrtineandtenets` vẫn 100% tiếng Anh**, không phải bản dịch, agent đã hallucinate. Đã đính chính lại trong TERMINOLOGY.md (mục B4m, ghi chú Sire). **Bài học quan trọng nhất rút ra từ session này: một agent tự nhận "file X đã dịch xong/đã có tiền lệ" KHÔNG phải bằng chứng — luôn tự `grep` nội dung thật của file được nhắc tới để xác nhận, đặc biệt khi agent dùng nó làm căn cứ cho quyết định thuật ngữ.**

**Việc cần làm tiếp theo, theo thứ tự:**
1. Dịch 9 file còn lại: `demons`, `fae`, `gaia`, `mummy`, `ordos`, `roadofzarathustra`, `wraiths`, `wyrm`, `modern` — thứ tự không quan trọng, có thể dịch song song theo lô như đã làm (5-6 agent/lô là hợp lý).
2. Để `docrtineandtenets` (1652 dòng, file lớn nhất `religion/`) làm cuối cùng của việc #2 — nên chia nhỏ thành nhiều đợt/agent theo đoạn dòng như đã làm với `traits_POD_l_english.yml` trước đây, đừng giao nguyên file 1652 dòng cho 1 agent.
3. Xong hết `religion/` (36/36) thì chuyển sang việc #3 (`custom_localization/` phần còn lại).

**Nhắc lại quy trình bắt buộc mỗi khi verify file agent con vừa dịch xong (đúc kết từ ~27 file đã làm):**
- Luôn tự chạy lại đủ 3 lớp kiểm tra bằng lệnh riêng, KHÔNG tin số liệu agent tự báo cáo trong phần tóm tắt (đã bắt được ít nhất 2 lần agent tự báo cáo sai số baseline).
- Luôn chạy `diff` so sánh **tập hợp** `$ref$` giữa bản gốc (`git show HEAD:<file>`) và bản đã dịch — không chỉ đếm số lượng. Đây là lớp bắt được lỗi agent tự thêm ref mới (đã xảy ra ít nhất 2 lần: `roadofbeast`, và nghi ngờ ở `roadofkings`).
- Kiểm tra kỹ tham số 1 của mọi `Glossary(...)` đã được dịch đúng, trừ các ngoại lệ đã ghi rõ trong TERMINOLOGY.md (Antediluvian, Wan Kuei, Kakuri, Shikome, Anda, Sire — Sire vì `game_concept_Sire` ở `game_POD_concepts` chưa dịch).
- TERMINOLOGY.md dễ bị nhiều agent song song cùng thêm heading trùng số — luôn `grep -n "^## B[34]" TERMINOLOGY.md | awk -F. '{print $1}' | sort | uniq -d` trước khi commit để bắt trùng.

⚠️ **Đã chốt: cụm `"principle of faith"`** (dùng trong `calomenasforsaken`, `bloodgnosticism`, và sẽ gặp lại ở `roadofkings`/`roadofhumanity`/`roadofheaven`) → dịch thống nhất là **"Nguyên Tắc Đức Tin"**. Một agent đã dịch lệch thành "nguyên lý đức tin" ở `bloodgnosticism`, phải sửa lại — kiểm tra kỹ khi tới các file `roadof*` còn lại.

Quy trình đã dùng: giao agent con dịch từng file (song song theo lô), người điều phối tự chạy đủ 3 lớp kiểm tra + đọc git diff trước khi commit — **agent đầu tiên để sót lỗi Glossary() tham số 1 (không dịch) trên toàn bộ file, phải yêu cầu sửa lại.** Luôn kiểm tra kỹ tham số 1 của mọi `Glossary(...)` trong file mới, không chỉ tin báo cáo của agent. Lưu ý: khi chạy nhiều agent song song, chúng có thể cùng thêm mục TERMINOLOGY.md với cùng số thứ tự (vd. hai agent cùng tạo "B3g") — luôn kiểm tra và đánh số lại cho khỏi trùng trước khi commit. Cũng đã gặp: agent tự báo cáo baseline token-count sai (do tính luôn lỗi của chính nó) — luôn tự đếm lại từ `git show HEAD` chứ không tin số agent đưa ra.

---

## ✅ ĐÃ XONG — đừng dịch lại

| File | Trạng thái | Commit |
|---|---|---|
| `glossary_POD_l_english.yml` | 105/105 key | `fb969bd` `81cbd59` `18a6716` |
| `custom_localization/POD_misc_custom_loc_l_english.yml` | 121/121 key | `152c52c` |
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

### #14 — `replace/`  481 key, 6 file  ⚠️ CẨN TRỌNG — **TẠM BỎ QUA**

**Ghi đè key vanilla** → sửa ở đây là đổi luôn UI của CK3 gốc, đè lên bản dịch trong `base_game_vh`. Phần lớn là template tên (`CHARACTER_FIRST_NAME_AND_DYNASTY: "$NAME$"`) — **chỉ dịch dòng có chữ thật**. Có `:0`.

`POD_do_not_translate_this_l_english.yml` (cả bản trong `replace/`) → **bỏ qua cả file**.

**Quyết định 2026-07-27:** tạm bỏ qua toàn bộ khối này. Không dịch không gây lỗi kỹ thuật — chỉ để lại vài chục dòng tiếng Anh lẻ tẻ trong `pod_replace_artifact_modifiers_l_english.yml`, `pod_replace_fog_of_war_l_english.yml`, `pod_replace_vanilla_temporary_l_english.yml` (các file có chữ thật, không phải template tên). Sẽ quyết định có dịch tiếp hay không sau khi trải nghiệm game thực tế.

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
