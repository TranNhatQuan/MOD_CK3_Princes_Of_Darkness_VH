# WORKLIST.md — thứ tự dịch Princes of Darkness

Danh sách công việc theo thứ tự. **Làm từ trên xuống, không nhảy bậc.**

- Quy tắc kỹ thuật → [TRANSLATION_RULES.md](TRANSLATION_RULES.md)
- Từ điển thuật ngữ → [TERMINOLOGY.md](TERMINOLOGY.md)
- Chính sách dịch → [README.md](README.md)
- Cấu trúc repo → [CLAUDE.md](CLAUDE.md)

Cập nhật lần cuối: 2026-07-27 (đợt 11 — việc #7 `modifiers/` đạt 54/54, HOÀN TẤT).

---

## Tình hình

| | Số liệu |
|---|---|
| Tổng cộng | **460 file, 104.366 dòng** |
| Đã xong hoàn toàn | **6 file traits/** + **36/36 file religion/** + **6/6 file custom_localization/** + **30/30 file gui/ (việc #4 HOÀN TẤT)** + **28/28 file interactions/ (việc #5 HOÀN TẤT)** + **11/11 file decisions/ (việc #6 HOÀN TẤT)** + **54/54 file modifiers/ (việc #7 HOÀN TẤT)** |
| Việc tiếp theo | Chuyển sang việc **#8 (`lifestyles/`, 6.740 key, 27 file)** → #9 (4 file root-level ưu tiên) theo đúng thứ tự trong mục "Thứ tự công việc" |

### ✅ ĐỢT 11 (2026-07-27) — 6 file lớn cuối `modifiers/` xong, việc #7 HOÀN TẤT 54/54

6 file lớn còn lại của `modifiers/` bàn giao từ đợt 10 đã dịch xong, verify xong, commit xong theo 2 đợt nhỏ:

- **Đợt nhỏ 1** (5 file, commit `2cc1c71`): `1230objectives_POD_modifiers` (233 dòng), `POD_fera_modifiers` (326 dòng), `artifact_POD_modifiers` (447 dòng, 223 tag mở/đóng nhiều nhất `modifiers/`), `misc_POD_modifiers` (378 dòng) — dịch qua agent song song (mỗi agent 1 file, ghi scratch riêng), coordinator tự merge bằng key-matching + verify 3 lớp. `umbra_expedition_POD_modifiers` (241 dòng, 623 bracket nhiều nhất `modifiers/`) — dịch trực tiếp bằng script perl (không qua agent) vì 99% nội dung là công thức lặp `"[umbra|E] Blessing: ..."`.
  - Lỗi merge phát hiện và sửa: `1230objectives` mất khoảng trắng cuối 4 dòng comment; `POD_fera` mất khoảng trắng ở 17 dòng "chỉ chứa 1 khoảng trắng"; `misc` bị agent ghi **thiếu BOM và dùng LF thuần thay vì CRLF cho toàn bộ file** (lỗi nặng nhất đợt này) + 27 dòng blank/space-only lệch độ dài — khôi phục toàn bộ bằng script perl trước khi merge vào repo.
- **Đợt nhỏ 2** (`houses_POD_modifiers`, 770 dòng — **file lớn nhất `modifiers/`**, commit `5906ddf`): dịch qua 4 agent chia đoạn (1-197, 198-465, 466-680, 681-770). **4 lỗi merge phát hiện và sửa, đáng chú ý vì xảy ra ngay tại ranh giới giữa các đoạn:**
  1. Dòng 681 (`dynn_horus_modifier: "Shemsu-Heru"`) bị **bỏ sót hoàn toàn** — đoạn 3 dừng đúng ở dòng 680, nhưng đoạn 4 lại bắt đầu nhầm từ dòng 682 thay vì 681, cả 2 agent đều tự tin báo đúng phạm vi. Phát hiện nhờ cộng tổng số dòng 4 đoạn ra thiếu 2 so với 770, rồi dò từng ranh giới bằng `awk 'NR==...'` trên bản gốc.
  2. Đoạn 2 (198-465) thiếu đúng 1 dòng trống ở cuối (dòng 465) dù agent tự báo "268 dòng khớp" — phát hiện nhờ so khớp key-sequence + vị trí dòng trống toàn file bằng script, không chỉ đếm số lượng dòng trống.
  3. Đoạn 1 tự đặt "House"→"Chi Hệ" dù được nhắc tra TERMINOLOGY.md trước — bỏ lỡ tiền lệ đã chốt từ lâu ("House"="Gia tộc", mục A10). 3 đoạn còn lại tự tra và dùng đúng "Gia Tộc". Sửa lại 120 chỗ ở đoạn 1 khi merge.
  4. Dòng 151 mất 1 dấu cách thừa cuối dòng so với bản gốc — khôi phục thủ công.

Diff bracket-set/ref-set với HEAD cho cả 6 file xác nhận không lệch (trừ các thay đổi chủ đích: `Underworld`→"Âm Phủ" B4j, `Demon Emperor`→"Ma Hoàng" B3c, `Beast`→"Dã Thú"). Thuật ngữ mới → TERMINOLOGY.md `B7-modifiers-houses`.

**modifiers/ đạt 54/54 file → việc #7 HOÀN TẤT.** Việc tiếp theo: #8 (`lifestyles/`, 6.740 key, 27 file).

### ⏸️ ĐỢT 10 (2026-07-27) — việc #7 `modifiers/` đạt 47/54 file, BÀN GIAO 6 file lớn cuối cho session sau

**Người dùng đã yêu cầu dừng lại** khi context vượt 300k token, để verify + cập nhật worklist trước khi tiếp tục — KHÔNG phải do gặp lỗi kỹ thuật.

47/54 file `modifiers/` đã dịch xong, verify xong, commit xong theo 5 đợt nhỏ trong cùng session:
- **Đợt nhỏ 1** (9 file rất nhỏ ≤10 dòng, commit `281f002`): `POD_kai`, `health_POD`, `POD_serpentis`, `POD_flavour_events`, `POD_cultural`, `POD_rift`, `POD_numina_theurgy`, `POD_shapeshift_bestial_form`, `vampire_discipline_draught` — coordinator tự dịch trực tiếp.
- **Đợt nhỏ 2** (18 file vừa, commit `6893811`): `00_POD_heritage_house`, `POD_clan`, `POD_gargoyle_caste`, `POD_government`, `POD_journey`, `POD_obtenebration`, `POD_presence`, `POD_province`, `POD_shih`, `daimonion_POD`, `gehenna_POD`, `gehenna_seer_POD`, `masquerade_POD`, `possessed_POD`, `scheme_POD`, `vampire_predatortypes`, `visual_looks_POD`, `vampire_bloodhunger`, `vampire_camarilla` — coordinator tự dịch. **Phát hiện mẫu lỗi mới: Edit tool tự động rút gọn các dòng "chỉ chứa 1 khoảng trắng" (hợp lệ trong CRLF gốc) thành dòng trống thật khi search/replace chạm gần đó** — đã khôi phục byte-for-byte bằng perl ở 8 file bị ảnh hưởng.
- **Đợt nhỏ 3** (7 file, commit `d9cbeda`): `POD_infernalism`, `vampire_blood_surge`, `vampire_discipline_shapeshift_forms` (184 dòng, nhiều tên hình dạng biến hình), `POD_kueijin/POD_kueijin_modifiers`, `POD_kueijin/kueijin_arts_POD_modifiers`, `POD_kueijin/kueijin_regular_activity_POD_modifiers`, `POD_necromancy`. **Từ đợt này coordinator chuyển hẳn sang dùng script perl trực tiếp (đọc/ghi binary, thay thế theo cặp chuỗi khớp chính xác) thay vì Edit tool — giải quyết dứt điểm vấn đề rút gọn khoảng trắng, 0 lỗi phát sinh từ đợt 3 trở đi.**
- **Đợt nhỏ 4** (3 file, commit `81e95b8`): `POD_numina_psi` (61 dòng "Channelling a weak/strong X wraith" lặp lại), `POD_numina_sorcery`, `vampire_bloodpotency` (23 dòng key thụt 2 space, mỗi dòng desc dài lặp mẫu theo ngưỡng Blood Potency 0-10, dịch nhất quán bằng regex theo từng cụm câu).
- **Đợt nhỏ 5** (9 file, commit `e1bdea5`): `POD_bloodmagic`, `demon_POD`, `mummy_POD`, `POD_custom_modifiers`, `umbra_gauntlet_POD`, `umbra_POD` (170 dòng, nhiều `UmbraGlossaryLocalized`), `wraith_POD`, `fae_POD`, `craft_POD` (212 dòng, rất nhiều tên thuốc/linh dược lặp mẫu). **8/9 file dịch qua agent song song** (mỗi agent 1 file, ghi scratch riêng ngoài repo — không đụng file thật), coordinator tự merge bằng script perl key-matching (đối chiếu tuần tự key giữa bản gốc CRLF và bản dịch LF của agent, giữ nguyên byte-for-byte mọi thứ ngoài phần giá trị dịch) + verify đủ 3 lớp. `craft_POD` dịch trực tiếp bằng script perl (không qua agent).

**2 lỗi thật bắt được khi merge kết quả agent (đáng chú ý — xác nhận quy trình merge cẩn thận vẫn cần thiết dù có agent-generated content):**
1. `umbra_gauntlet_POD`: agent dịch `UmbraGlossaryLocalized('shadowlands','Underworld')` thành tham số 2 = "Âm Giới" thay vì "Âm Phủ" đã chốt cứng ở TERMINOLOGY.md B4j — nhầm lẫn với quy tắc "Yin World"→"Âm Giới" khác. Sửa lại đúng 10 chỗ.
2. `fae_POD`: agent tự thêm 2 bracket `[dreamers|E]`/`[cantrips|E]` không có trong bản gốc (bản gốc dùng chữ thường "dreamers"/"Cantrips", không phải concept-link) — bracket count lệch 25 vs baseline 23, bắt được nhờ diff bracket-set với HEAD, đã sửa về đúng 23.

`umbra_POD` verify đúng cả 2 giá trị `UmbraGlossaryLocalized('shadowlands',...)` khác nhau trong cùng 1 file (`Underworld`→"Âm Phủ" dòng 75/164, `Yin World`→"Âm Giới" dòng 94) không bị lẫn lộn — agent xử lý đúng ngay từ đầu.

**6 file lớn CHƯA dịch — làm tiếp theo, theo đúng thứ tự (đã đo baseline sẵn, xem lệnh baseline chuẩn ở mục "Quy trình bắt buộc" bên dưới):**
1. `modifiers/1230objectives_POD_modifiers_l_english.yml` (233 dòng)
2. `modifiers/POD_fera_modifiers_l_english.yml` (326 dòng)
3. `modifiers/artifact_POD_modifiers_l_english.yml` (447 dòng, rất nhiều `#tag` — 223 tag mở/đóng)
4. `modifiers/misc_POD_modifiers_l_english.yml` (378 dòng)
5. `modifiers/umbra_expedition_POD_modifiers_l_english.yml` (241 dòng, RẤT NHIỀU bracket — 623, file nhiều bracket nhất `modifiers/`)
6. `modifiers/houses_POD_modifiers_l_english.yml` (770 dòng — **file lớn nhất `modifiers/`**, để cuối cùng)

Khuyến nghị: file 1-4 giao agent song song (mỗi agent 1 file, ghi scratch riêng), file `umbra_expedition` và `houses` nên chia nhỏ theo đoạn dòng cho nhiều agent (giống cách đã làm với `decisions/POD_decisions_l_english.yml` 1972 dòng ở đợt 9) vì quá lớn cho 1 agent duy nhất — nhớ luôn diff bracket-set/ref-set với HEAD sau khi merge, không chỉ đếm số lượng, và kiểm tra kỹ mọi `UmbraGlossaryLocalized('shadowlands',...)` xem giá trị tham số 2 là "Underworld" (→"Âm Phủ") hay "Yin World" (→"Âm Giới") — đây là lỗi đã xảy ra thật ở đợt này.

Sau khi xong 6 file này, `modifiers/` đạt 54/54 → **việc #7 HOÀN TẤT** → chuyển sang việc #8 (`lifestyles/`, 6.740 key, 27 file).

### ✅ ĐỢT 9 (2026-07-27) — `decisions/` đạt 11/11, việc #6 HOÀN TẤT

Toàn bộ 11 file của `decisions/` (2.973 dòng thật — đo bằng `grep -c ''`, khớp đúng baseline) đã dịch xong, verify xong, commit xong theo 6 đợt nhỏ trong cùng session:

- **Đợt nhỏ 1** (5 file nhỏ, commit `06914b1`): `POD_decisions_book_of_nod` (9 dòng), `POD_decisions_demon` (83 dòng), `POD_decisions_kj` (50 dòng), `POD_fera/POD_decisions_bastet` (19 dòng), `POD_fera/POD_decisions_werewolves` (19 dòng) — coordinator tự dịch trực tiếp, không qua agent.
- **Đợt nhỏ 2** (`POD_fera/POD_decisions_fera` 40 dòng + `POD_numina_sorcery_decisions` 98 dòng, commit `561b665`): coordinator tự dịch. Lần đầu dịch đầy đủ 14 trường phái Sorcery (Alchemy/Conjuration/Conveyance/Cursing/Divination/Enchantment/Ephemera/Fascination/Healing/Hellfire/Mana Manipulation/Oneiromancy/Shadow Casting/Shapeshifting/Summoning Warding and Binding/Weather Control) → TERMINOLOGY.md `B6-decisions-sorcery`.
- **Đợt nhỏ 3** (`POD_decisions_wraiths`, 192 dòng, commit `cb20a62`): coordinator tự dịch. Tự phát hiện thiếu 1 dòng trống cuối file (byte-for-byte so với HEAD) và tự sửa trước khi commit.
- **Đợt nhỏ 4** (`POD_decisions_fae`, 207 dòng, commit `31f654c`): coordinator tự dịch. Tự phát hiện + sửa 2 lỗi: đổi nhầm `[rulers|E]`→`[ruler|E]` ở 3 dòng, và làm mất bracket `[marriages|E]` ở 1 câu văn dài khi diễn đạt lại — bắt được nhờ diff nội dung bracket (không chỉ đếm số lượng).
- **Đợt nhỏ 5** (`POD_decisions_misc`, 284 dòng, commit `00932f3`): coordinator tự dịch. Tự phát hiện + sửa 2 lỗi byte-for-byte: mất 1 dấu cách trong dòng trống cuối file, và mất 1 dấu cách cuối dòng comment `#Visceratika ` (lộ ra qua đếm tag mở lệch 45 vs 46 dù đây chỉ là comment, không phải tag thật).
- **Đợt nhỏ 6** (`POD_decisions_l_english.yml`, 1972 dòng — **file lớn nhất `decisions/`**, commit `3f979b2` + `2865de1`): dịch qua 6 agent chia đoạn (1-415, 416-773, 774-988, 989-1319, 1320-1649, 1650-1972), mỗi agent ghi 1 file scratch riêng ngoài repo. **6 lỗi merge tự phát hiện và sửa trước khi commit** (xem chi tiết bên dưới — đây là đợt phát hiện nhiều lỗi nhất từ trước đến nay trong 1 lần merge).

**6 lỗi phát hiện khi merge `POD_decisions_l_english.yml` (đáng chú ý vì đa dạng loại lỗi hơn hẳn các đợt trước):**
1. "the Masquerade" dịch nhầm "Lớp Mặt Nạ" thay vì "Màn Che" đã chốt (B3/B4h).
2. "Hun"/"P'o" (2 khái niệm hồn phách Kuei-Jin) dịch nghĩa nhầm thành "Hồn"/"Phách" thay vì giữ nguyên tiếng Anh đã chốt.
3. "Underworld" (tham số 2 của `UmbraGlossaryLocalized('shadowlands',...)`) bị dịch sai ở 2 chỗ khác nhau ("Địa Ngục Giới" và giữ nguyên tiếng Anh) thay vì "Âm Phủ" đã chốt cứng B4j.
4. "Antediluvians" (số nhiều) bị agent tự rút gọn nhầm thành "Antediluvian" (số ít) — trái với chốt "giữ nguyên kể cả dạng số nhiều".
5. "Demon Emperor" chỉ dịch đúng 1/4 lần thành "Ma Hoàng", 3 lần còn lại bỏ sót hoàn toàn — phát hiện nhờ lệnh gom nhóm `Glossary()` theo tham số 2.
6. **Toàn bộ 28 lần "Second/Third/Fourth/Fifth/Sixth Age" (tham số 1 của `Glossary()`) bị bỏ sót hoàn toàn ở 2 trong 6 đoạn** (không phải 1-2 chỗ lẻ tẻ mà là cả một mẫu lặp xuyên suốt 2 đoạn ~650 dòng) — cùng loại lỗi với #5, chỉ bắt được bằng lệnh gom nhóm theo tham số 2, đếm bracket thường không phát hiện được vì Glossary vẫn còn 1 bracket dù tham số 1 sai ngôn ngữ.
7. Thiếu đúng 1 dòng trống cuối 1 đoạn (agent xuất scratch ngắn hơn 1 dòng — lỗi quen thuộc đã gặp nhiều lần trước đây).
8. **Lỗi line-ending nghiêm trọng nhất từ trước đến nay: 2/6 đoạn (653/1972 dòng, ~1/3 toàn file) bị ghi bằng LF thuần thay vì CRLF**, dù prompt đã dặn rất kỹ. Đáng chú ý: lệnh `file <path>` báo **"CRLF line terminators"** cho CẢ FILE ĐÃ MERGE dù 1/3 nội dung bên trong là LF thuần — `file` chỉ lấy mẫu đầu file, không quét toàn bộ, nên KHÔNG đủ tin cậy để xác nhận line-ending của file lớn đã ghép từ nhiều nguồn. Chỉ lệnh đếm "lone LF" trên toàn file (`perl -0777 -ne '$c=()=/(?<!\r)\n/g; print $c'`, phải bằng 0 nếu file thuần CRLF) mới bắt được chính xác.

**Cảnh báo công cụ mới phát hiện trong đợt này: `sed -i` trên Git Bash/MinGW tự ý strip byte CR khi sửa tại chỗ một file CRLF** — coordinator tự gây ra lỗi #8 ở trên khi dùng `sed -i` để sửa hàng loạt tham số `Glossary()` cho lỗi #6, vô tình biến 2 file từ CRLF thành LF. **Từ nay: dùng `perl -pi -e 's/pattern/replacement/'` thay cho `sed -i` khi cần sửa tại chỗ trên file `.yml` của repo này (vốn luôn là CRLF)**, hoặc nếu bắt buộc dùng `sed -i`, phải convert lại LF→CRLF (`perl -pi -e 's/\n/\r\n/' file` sau khi xác nhận file gốc không có CR nào để tránh nhân đôi) ngay sau đó và verify lại bằng lệnh đếm lone-LF.

Thuật ngữ mới → TERMINOLOGY.md `B6-decisions-sorcery`, `B6-decisions-l`.

decisions/ đạt 11/11 file → **việc #6 HOÀN TẤT.** Việc tiếp theo: #7 (`modifiers/`, 4.344 key, 54 file). Tra TERMINOLOGY.md phần A trước khi dịch — phần lớn modifier là thuật ngữ vanilla đã có bản dịch.

### ✅ ĐỢT 8 (2026-07-27) — `vampire` + `wraith` xong, `interactions/` đạt 28/28, việc #5 HOÀN TẤT

Cả 2 file lớn cuối cùng của `interactions/` đã dịch xong, verify xong, commit xong:

- `interactions/POD_character_interactions_vampire_l_english.yml` (1187/1187 dòng thật — `grep -c ''`, KHÔNG phải 1186 như `wc -l` báo vì dòng cuối không có newline) — commit `99ecb29`. Dịch qua 8 agent chia đoạn (1-155, 156-321, 322-444, 445-592, 593-726, 727-889, 890-1033, 1034-1187). 2 lỗi merge tự phát hiện và sửa trước khi commit: (1) đoạn 322-444 thiếu đúng 1 dòng trống cuối (dòng 444) do agent xuất scratch ngắn hơn 1 dòng; (2) BOM đôi do agent phần 1 tự thêm BOM vào scratch, script merge coordinator lại thêm 1 lần nữa. Thuật ngữ mới → TERMINOLOGY.md `B5-vampire-p1` đến `p8` (~150 mục).
- `interactions/POD_character_interactions_wraith_l_english.yml` (738/738 dòng thật, KHÔNG phải 737 như `wc -l` báo) — commit `616da91`. Dịch qua 6 agent chia đoạn (1-132, 133-246, 247-369, 370-495, 496-615, 616-738). 2 lỗi merge tự phát hiện và sửa trước khi commit: (1) đoạn 247-369 agent ghi bằng LF thay vì CRLF — đã chuyển đổi khi merge; (2) đoạn 496-615 thiếu đúng 1 dòng trống cuối đoạn (dòng 615) — khôi phục bằng cách so khớp key tuần tự với bản gốc. Thuật ngữ mới → TERMINOLOGY.md `B5-wraith-p1` đến `p6`.

**Bài học lặp lại lần thứ N (đã thấy ở cả 2 file trong đợt này): khi chia file cho nhiều agent dịch theo đoạn dòng, luôn có khả năng 1 agent xuất scratch thiếu đúng 1 dòng trống ở ranh giới cuối đoạn (do dùng `split()` rồi lỡ bỏ luôn phần tử rỗng hợp lệ), hoặc dùng sai line-ending (LF thay vì CRLF) dù đã được dặn kỹ trong prompt.** Coordinator PHẢI tự chạy lại đúng số dòng từng file scratch trước khi ghép (`len(data.split(b'\r\n'))`, cẩn thận phân biệt "phần tử rỗng cuối vì có `\r\n` thừa hợp lệ" với "thiếu 1 dòng thật") — không tin báo cáo "đã khớp 100%" của agent, dù agent tự claim đã verify. Cách xử lý an toàn khi phát hiện thiếu 1 dòng: so khớp KEY tuần tự (regex bắt tên key trước dấu `:`) giữa đoạn gốc (`git show HEAD:<file>` cắt đúng range) và đoạn dịch, tìm đúng vị trí lệch, chèn dòng trống bị thiếu vào đúng chỗ.

**Nghi vấn thuật ngữ chưa giải quyết dứt điểm ở `wraith` (không phải lỗi kỹ thuật, chỉ là chưa rà toàn cục), cần lưu ý khi gặp lại các từ này ở file khác:**
- "Conduit" (cơ chế biến động vật thành vật trung gian liên lạc của Wraith) — giữ nguyên tiếng Anh, chưa dịch nghĩa.
- "Angst" (chỉ số nội tâm Wraith, khác Pathos) — giữ nguyên tiếng Anh, chưa có tiền lệ dịch nghĩa.
- "Catharsis" — dịch tạm là "Tịnh Hóa" (lần đầu trong repo, B5-wraith-p3), nhưng agent tự ghi chú nghi ngờ nghĩa gốc là "Bóng thắng thế/chiếm quyền kiểm soát" chứ không phải "thanh tẩy" tích cực — nên rà lại khi gặp mô tả Catharsis đầy đủ hơn ở file khác.
- Viết hoa "Oan Hồn Bị Ràng Buộc" (nhãn UI) vs "oan hồn bị ràng buộc" (văn xuôi thường) — đã thống nhất theo ngữ cảnh (nhãn ngắn viết hoa, câu văn dài viết thường), không phải lỗi.

interactions/ đạt 28/28 file → **việc #5 HOÀN TẤT.** Việc tiếp theo: #6 (`decisions/`, 2.441 key, 11 file).

### ⏸️ ĐỢT 7 (2026-07-27) — việc #5 `interactions/` đạt 25/28 file, BÀN GIAO 2 file cuối cho session sau

**Người dùng đã yêu cầu dừng lại sau khi xong đợt này** — batch 6 (`wraith`) và batch 7 (`vampire`) để session sau làm tiếp, KHÔNG phải do gặp lỗi hay hết context.

25/28 file `interactions/` đã dịch xong, verify xong, commit xong, theo 5 đợt nhỏ (batch) trong cùng session:
- **Batch 1** (12 file nhỏ <100 dòng, commit `39a44c1`): `POD_categories`, `character_interactions_blood_tithe_POD` (toàn comment, không sửa), `POD_character_interactions_coterie/artifact/debug/ghoul/grand_city/hint/journeys/qiao/spirits`, `character_interactions_POD` (287 dòng).
- **Batch 2** (9 file `POD_demons/` + `POD_fera/`, commit `395a575`): `demon_arcana/demon_infernalist/demon_lores/demon_thrall`; `bastet/fera/mokole/werewolf/wyrm`.
- **Batch 3** (3 file 150-290 dòng, commit `f416c1b`): `mummy` (158 dòng), `kuejin` (158 dòng), `numina` (275 dòng).
- **Batch 4** (`hunter`, 369 dòng — chú ý KHÔNG phải 368 vì dòng cuối không có newline, `wc -l` báo thiếu 1 dòng, commit `4d9b7f1`): dịch qua 4 agent chia đoạn (1-92, 93-183, 184-276, 277-369).
- **Batch 5** (`fae`, 458 dòng, commit `56dc1d2`): dịch qua 4 agent chia đoạn (1-114, 115-229, 230-341, 342-458).

**2 file lớn cuối cùng CHƯA dịch — làm tiếp theo, theo đúng thứ tự:**
1. `interactions/POD_character_interactions_wraith_l_english.yml` (737 dòng) — chia ~4-6 agent theo đoạn dòng (giống cách đã làm với `hunter`/`fae`), ranh giới tự nhiên theo dòng trống, KHÔNG cắt ngang giữa 1 entry logic.
2. `interactions/POD_character_interactions_vampire_l_english.yml` (1186 dòng, **file lớn nhất trong `interactions/`**) — chia ~6-8 agent theo đoạn dòng.

Sau khi xong cả 2 file này, `interactions/` đạt 28/28 → việc #5 HOÀN TẤT → chuyển sang việc #6 (`decisions/`, 2.441 key, 11 file).

**Lỗi thật đã bắt được trong đợt này (bằng chứng tiếp tục xác nhận: đếm token/bracket KHÔNG đủ, phải đối chiếu NỘI DUNG bracket byte-for-byte bằng diff, không chỉ đếm số lượng):**
- `numina`: agent tự thêm 7 bracket `[artifact|E]`/`[piety|E]`/`[knight|E]`/`[councillor|E]`/`[house|E]`/`[consort|E]` không có trong bản gốc (bản gốc dùng chữ thường, không phải concept link) ở 1 dòng — bracket count lệch 65→72 lộ ra lỗi. Agent tự phát hiện và tự sửa trước khi báo cáo.
- `kuejin`: agent tự phát hiện và tự sửa lỗi `UmbraGlossaryLocalized('shadowlands','Underworld')` chưa dịch tham số 2 (phải là "Âm Phủ" theo B4j) trước khi báo cáo.
- `hunter`: file thật có **369 dòng**, không phải 368 như `wc -l` báo (dòng cuối `gotchiweapon_notification` không có newline theo sau) — agent phụ trách đoạn cuối tự phát hiện dòng lẻ này nằm ngoài phạm vi 4 đoạn ban đầu (1-92/93-183/184-276/277-368) và tự dịch bổ sung. **Bài học: luôn `grep -c ''` để xác nhận số dòng THẬT trước khi chia đoạn cho nhiều agent, đừng tin `wc -l` nếu dòng cuối không có newline.**
- `fae`: merge 4 đoạn làm mất 2 script token `[target.GetHerHis]` và `[oath_guardian.GetHerselfHimself]` ở 2 câu văn dài (agent diễn đạt lại câu và bỏ sót token possessive/reflexive lặp) — bracket count lệch 264→262 lộ ra lỗi, coordinator tự sửa lại đúng vị trí ngữ nghĩa sau khi merge.
- **Kết luận chung: luôn chạy `diff <(git show HEAD:<file> | grep -oE '\[[^]]*\]' | sort) <(grep -oE '\[[^]]*\]' <file> | sort)` sau khi merge — đối chiếu NỘI DUNG bracket, không chỉ đếm SỐ LƯỢNG, vì 2 lỗi mất-1-thêm-1 hoặc thêm-mới ở chỗ khác có thể làm số lượng vẫn khớp trong khi nội dung sai.**

**Race condition TERMINOLOGY.md tiếp diễn (đã biết từ trước, xảy ra nhiều lần hơn ở đợt này do 4-9 agent chạy đồng thời):** heading `B5a`-`B5s` gần như bị dùng hết và trùng lặp liên tục (`B5b`, `B5e`, `B5f`, `B5m`, `B5n`, `B5o`, `B5p`, `B5q`, `B5r` mỗi cái đều bị ≥2 agent chọn trùng ở các thời điểm khác nhau trong session). Coordinator phải chạy lại `grep -n "^## B[34][a-zA-Z_-]*\." TERMINOLOGY.md | sed -E 's/^[0-9]+:## (B[34][a-zA-Z_-]*)\..*/\1/' | sort | uniq -d` nhiều lần trong lúc các agent còn đang chạy (không chỉ 1 lần cuối) và đổi tên các heading trùng ngay khi phát hiện. Một số agent tự chuyển sang đặt heading dạng slug (`B5-mummy`, `B5-kuejin`, `B5-numina`, `B5-hunter`, `B5-fae`, `B5-demon-lores`, `B5-demon-thrall`) để giảm khả năng đụng độ — cách này hiệu quả hơn ký tự tuần tự khi có nhiều agent song song, **nên áp dụng cho các đợt sau có ≥4 agent chạy đồng thời viết TERMINOLOGY.md.**

### ✅ ĐỢT 6 (2026-07-27) — hoàn tất `POD_craft` + `POD_umbra_window`, `gui/` đạt 30/30, việc #4 HOÀN TẤT

Cả 2 file lớn cuối cùng của `gui/` đã dịch xong, verify xong, commit xong:
- `gui/POD_craft_l_english.yml` (1187/1187 dòng) — commit `f40fd0d`. Dịch qua 4 agent chia đoạn (1-403, 404-825, 826-1049, 1050-1187). Phát hiện + sửa lệch thuật ngữ độ hiếm hiện vật (Common/Masterwork/Famed/Illustrious) giữa các đoạn — chuẩn hóa về Thường/Tinh xảo/Danh tiếng/Lừng lẫy (ghi TERMINOLOGY.md B5c).
- `gui/POD_umbra_window_l_english.yml` (1572/1572 dòng) — commit `5acdce5`. Dịch qua 6 agent chia đoạn (1-160, 161-324, 325-540, 541-798, 799-1189, 1190-1572). Phát hiện + sửa **17 dòng sót tiếng Anh** (13 dòng `court_of_*_effect_desc` giống hệt nhau + 4 dòng `*_duchy_effect_desc` — agent nhầm tưởng đây là dòng chỉ chứa `$ref$`/script vì đứng cạnh các dòng thật sự rỗng khác) — **bẫy y hệt lỗi 132 dòng ở `docrtineandtenets`**, chỉ bắt được nhờ chạy grep English-sót riêng, KHÔNG phải nhờ 3 lớp kiểm tra số liệu chuẩn (số liệu vẫn khớp 100% dù thiếu 17 dòng này). Cũng chuẩn hóa 4 thuật ngữ `Glossary()` tham số 1 lệch giữa các đoạn (Dark Kingdom, Home Realm, Yama King, Stable Point) về đúng tiền lệ đã chốt trong TERMINOLOGY.md. Ghi TERMINOLOGY.md mục B5d.

**Bài học nhắc lại (lần thứ N):** dù chia đoạn cẩn thận theo ranh giới tự nhiên và mỗi agent chỉ ghi 1 file scratch riêng (không có race condition), vẫn luôn phải:
1. Tự chạy grep bắt English-sót riêng sau khi merge — đừng tin 3 lớp số liệu chuẩn, vì dòng sót vẫn giữ cấu trúc `$ref$`/bracket hợp lệ nên số liệu không đổi.
2. Tự chạy lệnh gom nhóm `Glossary()`/`UmbraGlossaryLocalized()` theo tham số 2 (key) để phát hiện tham số 1 (chữ hiển thị) bị dịch lệch giữa các đoạn — ví dụ lệnh: `grep -oE "Glossary\('[^']*','[^']*'\)" <file> | sed -E "s/Glossary\('([^']*)','([^']*)'\)/\2\t\1/" | sort | awk -F'\t' '{c[$1]++; v[$1]=v[$1]" \| "$2} END{for(k in c) if(c[k]>1) print k": "v[k]}'` — bất kỳ key nào có ≥2 biến thể tham số 1 khác nhau (không phải chỉ số ít/nhiều của cùng 1 bản dịch) là lỗi cần sửa.
3. Tra TERMINOLOGY.md trước khi để agent tự đặt thuật ngữ mới — nhiều thuật ngữ tưởng là "đặt mới" thực ra đã có tiền lệ chốt từ trước (vd. Yama King→Diêm Ma Vương đã chốt ở B3c từ khi dịch `religion/`, nhưng 2 agent trong đợt này không tra mà tự dịch thành "Vua Yama").

**Việc cần làm tiếp theo:** chuyển sang việc #5 (`interactions/`, 3.780 key, 28 file), rồi tiếp tục tuần tự #6 → #7 → #8 → #9 theo đúng thứ tự ghi ở mục "Thứ tự công việc" bên dưới. Đã xác nhận lại với người dùng: đi tuần tự 5-6-7-8-9, KHÔNG nhảy thẳng lên #9.

### ✅ ĐỢT 4 (2026-07-27) — hoàn tất việc #3 (`custom_localization/` phần còn lại)

5 file cuối của `custom_localization/` đã xử lý xong, verify xong, commit xong (`1c28cc3`, `bd3b4d0`, `642e27f`, `6d6b2f4`):
- `insult_POD_custom_loc_l_english.yml` (272/272 dòng) — danh sách từ sỉ nhục giữa các splat, tên clan/splat giữ nguyên (chỉ xuất hiện ở key), chỉ dịch danh từ/tính từ/hành vi sỉ nhục.
- `POD_signature_weapon_custom_loc_l_english.yml` (31/31 dòng) — từ vựng vũ khí tự nhiên (móng vuốt/răng nanh) lắp ráp combat log.
- `POD_resonance_custom_loc_l_english.yml` (30/30 dòng) — **chỉ 4/30 dòng có chữ thật** (`POD_resonance_intensity_1-4`), 16 dòng tooltip-ID/icon + 4 dòng concept-link giữ nguyên không dịch. Thuật ngữ mới → TERMINOLOGY.md **B4x**.
- `secrets_POD_custom_loc_l_english.yml` (177/177 dòng) — mô tả bí mật nhân vật, tra đúng tên trait/education vanilla từ `base_game_vh` (Nóng giận/Tham lam/Trinh khiết/Hào phóng/Chăm chỉ/Khoan dung/Nhân hậu/Khiêm tốn/Tiết độ/Dâm dục/Kiêu ngạo/Phàm ăn...).
- `POD_modifier_custom_loc_l_english.yml` (38 dòng) — **không sửa gì, không commit riêng.** Xác nhận toàn bộ 34 dòng có nội dung đều là `key: "[GetModifier('...').GetNameWithTooltip]"` — 100% script reference, không có chữ hiển thị nào để dịch. Bản dịch thật của các modifier này (`bloodpotency<N>_modifier`, `gauntlet<N>_modifier`, `shroud<N>_modifier`) nằm ở file khác thuộc `modifiers/` (việc #7, chưa tới lượt).

Quy trình: 5 agent song song, mỗi agent 1 file riêng (an toàn, không đụng file chung — khác với race condition suýt xảy ra ở `docrtineandtenets`). Coordinator tự verify từng file: đếm dòng/bracket/ref/icon khớp baseline, diff ref/key/Glossary param với `git show HEAD`, chạy grep bắt sót tiếng Anh + lỗi dính dòng, đọc git diff đầy đủ, kiểm tra không trùng heading TERMINOLOGY.md — không có sai sót nào bị phát hiện ở đợt này (khác các đợt trước).

**Việc cần làm tiếp theo:** chuyển sang việc #4 (`gui/`, 4.458 key, 30 file). Chú ý `gui/POD_hud_l_english.yml` dùng hậu tố `:0`, và UI CK3 chật nên phải giữ bản dịch ngắn gọn tương đương độ dài tiếng Anh gốc.

Ba bước nền (glossary → custom_loc → tên splat) **đã hoàn tất**. Toàn bộ thuật ngữ gốc đã chốt trong TERMINOLOGY.md (~200 mục, B3/B4 đầy đủ cho VtM/Fae/Fera/Wraith/Mummy/Kuei-Jin/Demon/Garou). Phần còn lại là **tra bảng và áp dụng**, không còn phải tự đặt thuật ngữ nền.

**Việc #1 (`traits/`) đã HOÀN TẤT — cả 4 file trong thư mục này đã xong 100%.**

**Việc #2 (`religion/`) đã HOÀN TẤT 36/36 file.** Danh sách commit theo thứ tự (rút gọn — 27 file đầu, xem chi tiết trong lịch sử git nếu cần): `2952a68`…`d5d2cd7` (27/36, xem bản WORKLIST cũ trong git log nếu cần tra lại), rồi tiếp: `1b41e1e`(mummy, 28/36) `93321dd`(demons, 29/36) `722a757`(modern, 30/36) `b61c2d0`(sửa trùng heading B4q) `c4a49cf`(roadofzarathustra, 31/36) `47fc7a6`(ordos, 32/36) `4223927`(wyrm, 33/36) `627f794`(fae, 34/36) `13742c8`(wraiths, 35/36) `83164a2`(gaia, 36/36 trừ docrtineandtenets) và cuối cùng `docrtineandtenets` (36/36, xem đợt 3 bên dưới).

### ✅ ĐỢT 3 (2026-07-27) — hoàn tất `docrtineandtenets`, `religion/` đạt 36/36

File cuối cùng của `religion/` (1652 dòng, 1121 bracket — nhiều `Glossary()`/`UmbraGlossaryLocalized()` nhất thư mục, kho doctrine/tenet dùng chung mọi splat) đã dịch xong, verify xong, commit xong. Chi tiết thuật ngữ mới → TERMINOLOGY.md mục **B4w**.

**⚠️ Sự cố suýt xảy ra, đã ngăn kịp thời:** thiết kế ban đầu giao 3 agent song song mỗi agent tự đọc-toàn file-rồi-ghi-đè-toàn file (chỉ sửa đúng đoạn dòng được giao) — đây là race condition thật sự vì 3 agent ghi cùng 1 đường dẫn gần như đồng thời, agent ghi sau cùng sẽ xóa sạch bản dịch của các agent ghi trước mà không có cảnh báo lỗi nào. Phát hiện ra vấn đề ngay sau khi phóng agent (trước khi agent nào kịp ghi file thật) và dừng cả 3 bằng TaskStop, xác nhận file gốc chưa bị chạm (`git status` sạch, đếm ký tự tiếng Việt vẫn = baseline). **Sửa lại thiết kế: mỗi agent chỉ ghi ra 1 file scratch riêng ngoài repo (không đụng file thật), điều phối viên tự đọc toàn bộ 6 file scratch, đối chiếu thuật ngữ chéo giữa các đợt, rồi tự ghép + ghi 1 lần duy nhất vào file thật.** Bài học: **không bao giờ giao ≥2 agent song song ghi trực tiếp vào cùng 1 file**, kể cả khi mỗi agent chỉ phụ trách 1 đoạn dòng riêng biệt — luôn dùng file scratch trung gian + hợp nhất thủ công ở agent điều phối.

**Lỗi hệ thống nghiêm trọng phát hiện SAU KHI cả 6 lớp kiểm tra kỹ thuật đã PASS 100%:** 3/6 agent (132/165 dòng, tương đương ~8% toàn file) để nguyên **hoàn toàn tiếng Anh** ở mẫu câu `doctrine_parameter_*_illegal/shunned/accepted`: `"Characters with the [trait] [trait|E] are [criminals|E]/[shunned|E]/fully accepted"` — nhầm tưởng đây là chuỗi script nội bộ không cần dịch, trong khi thực ra đây là tooltip hiển thị cho người chơi trong UI giáo lý đức tin (không có tiền lệ mẫu này ở bất kỳ file `religion/` nào khác nên agent không có gì để đối chiếu). **Toàn bộ 3 lớp kiểm tra chuẩn (đếm token/bracket/ref, BOM/CRLF, diff ID script) đều PASS dù thiếu sót này** — vì các dòng bị bỏ sót vẫn giữ nguyên cấu trúc bracket/ref hợp lệ 100%, không "hỏng" theo nghĩa kỹ thuật. Chỉ phát hiện được nhờ chạy thêm 1 lệnh `grep` riêng tìm từ tiếng Anh thông dụng (`the/and/of/with/are/is...`) loại trừ script ID sau khi hợp nhất — đúng như cảnh báo TRANSLATION_RULES.md §8 rằng đếm token không đủ, nhưng lần này ở quy mô lớn hơn nhiều (132 dòng) so với các lỗi lẻ tẻ 1-2 dòng đã gặp ở các file trước. Đã sửa bằng script Python thay thế mẫu câu hàng loạt (mẫu đủ đều để làm tay an toàn hơn giao lại cho agent).

**Lỗi thuật ngữ chéo giữa các đợt cũng phát hiện qua rà thủ công (không phải agent tự báo):**
- Nhãn trạng thái doctrine ("Criminal"/"Shunned"/"Accepted"/"Evil") — 3 agent dùng 3 biến thể khác nhau ("Bị Xa Lánh" vs "Xa Lánh" vs "Bị Ruồng Bỏ", "Được Chấp Nhận" vs "Chấp Nhận") → chuẩn hóa về 1 bộ duy nhất (xem B4w).
- `Prodigal(s)` đã khóa "Kẻ Hoang Đàng" ở B3z nhưng 2 agent dịch lệch (giữ nguyên tiếng Anh, hoặc phiên âm hóa thành tính từ "Cainite Ấn Độ" thay vì "Hậu Duệ Cain người Ấn" cho `"Indian Cainites"`) — sửa lại khớp B3z.
- Cụm "can appoint Justicar" — 1 agent dùng "bổ nhiệm" trong khi 15 chỗ khác dùng "chỉ định" — thống nhất về "chỉ định" (đa số thắng).

**Việc cần làm tiếp theo:** chuyển sang việc #3 (`custom_localization/` phần còn lại, xem mục "#3" bên dưới).

### ⚠️ BÀN GIAO GIỮA SESSION (2026-07-27, đợt 2, do gần chạm ~300k token context) — LỊCH SỬ, đã xử lý xong ở đợt 3

9 file còn lại của đợt trước (`demons`, `mummy`, `ordos`, `roadofzarathustra`, `modern`, `wyrm`, `fae`, `wraiths`, `gaia`) đã dịch xong, verify xong, commit xong **trong chính session này** trước khi bàn giao — **không có agent nào dở dang, không cần resume gì cả**. `religion/` giờ chỉ còn thiếu đúng 1 file: `docrtineandtenets` (1652 dòng, lớn nhất thư mục).

**Lỗi phát hiện và sửa trong đợt verify này (đọc kỹ, các lỗi lặp lại + lỗi mới):**
- **TERMINOLOGY.md bị trùng heading NHIỀU LẦN trong đợt này** — không phải 1 lần mà liên tiếp: `demons` tự đặt `B4k` trùng với `roadofkings` đã dùng trước → đổi thành `B4p`. `modern` tự đặt `B4q` trùng với `ordos` cũng tự đặt `B4q` cùng lúc → đổi `modern` thành `B4r`. **Bài học: khi chạy ≥2 agent song song viết TERMINOLOGY.md, luôn chạy lại `grep -n "^## B[34]" TERMINOLOGY.md | awk -F'[.#]' '{print $2}' | awk '{print $1}' | sort | uniq -d` SAU KHI cả hai agent đã xong, không chỉ trước khi mỗi agent bắt đầu — vì chúng đọc file cùng một thời điểm và không thấy heading của nhau.**
- `modern`: agent không tự ghi mục TERMINOLOGY.md nào dù báo cáo có liệt kê thuật ngữ mới (Gehenna, Convention of Thorns, pack, 9 tên tín đồ Path Sabbat...) — coordinator phải tự viết mục B4r thay agent trước khi commit. **Bài học: đừng giả định agent đã ghi TERMINOLOGY.md chỉ vì báo cáo liệt kê thuật ngữ — luôn `grep` xác nhận mục đó thực sự tồn tại trong file trước khi commit.**
- `fae`: phát hiện **2 lỗi thật khi đọc git diff** (số liệu tự kiểm tra của agent vẫn khớp 100% dù có lỗi — đúng như cảnh báo ở TRANSLATION_RULES.md §8 rằng đếm token không đủ):
  1. Dòng 369 (`holy_order_winters_teeth`): agent để **cả giá trị gốc tiếng Anh và giá trị dịch tiếng Việt dính liền nhau trên cùng 1 dòng** (`"Winter's Teeth" holy_order_winters_teeth: "Răng Mùa Đông"`) — dạng lỗi merge/ghi đè hỏng, chưa từng gặp trước đây. Đã dọn về 1 dòng sạch.
  2. Dòng 104 (comment dịch thêm, không bắt buộc): sót đúng 1 từ tiếng Anh "obsession" giữa câu văn tiếng Việt đã dịch phần còn lại — sửa thành "nỗi ám ảnh". **Bài học mới: khi agent dịch cả các đoạn comment dài (không bắt buộc theo TRANSLATION_RULES.md §5 nhưng agent tự chọn dịch để nhất quán), phải rà kỹ hơn vì khả năng sót từ lẻ tăng theo độ dài đoạn — nên grep tìm các từ tiếng Anh thông dụng còn sót (`the/and/of/with/seek/believe/obsession...`) trong toàn bộ file sau khi agent báo hoàn tất.**
- `wyrm`: agent tự phát hiện và tự sửa **BOM đôi** (`ef bb bf ef bb bf`) do lỗi trong chính script Python của nó trước khi báo cáo hoàn tất — không cần coordinator can thiệp nhưng đã verify lại kỹ (đếm BOM bằng `d[:3]==b'\xef\xbb\xbf' and d[3:6]!=b'\xef\xbb\xbf'`) để chắc chắn.
- `wraiths`: agent tự phát hiện và tự sửa sót dịch tham số 2 của `UmbraGlossaryLocalized('shadowlands','Underworld')` (6 lần trong file) trước khi báo cáo — verify lại xác nhận đúng cả 6 chỗ.
- `gaia`: agent tự phát hiện và tự sửa 2 chỗ sót (`gaia_health_god_name`, tham số 2 của `UmbraGlossaryLocalized('astral_reaches',...)`) trước khi báo cáo — verify lại xác nhận đúng.
- ⚠️ **Phát hiện KHÔNG PHẢI lỗi kỹ thuật nhưng đáng lưu ý: `wyrm` và `gaia` xử lý tên riêng "camp" (đơn vị xã hội con của bộ tộc Garou) KHÔNG nhất quán với nhau.** `wyrm` dịch nghĩa tên camp (`Black Spiral Dancers`→"Vũ Công Xoáy Đen", `Princes of Ruin`→"Chúa Tể Diệt Vong"…) trong khi `gaia` giữ nguyên tiếng Anh phần lớn tên camp (`Servants of the Unicorn`, `Children of Gaia`, `Get of Fenris`…, chỉ dịch nghĩa vài cái như holy order). TERMINOLOGY.md chỉ chốt "camp" (danh từ chung) = "Trại", không chốt quy tắc dịch hay giữ nguyên **tên riêng** của từng camp cụ thể. **Việc cần làm: session sau nên rà lại 2 file này (và các file `religion/` khác có nhắc tên camp) để quyết định 1 quy tắc nhất quán — có thể chấp nhận "camp lore quan trọng/dịch được nghĩa thì dịch, camp chỉ là danh xưng khó dịch thì giữ nguyên" nhưng cần ghi rõ vào TERMINOLOGY.md, không để tùy hứng từng agent.**

**Việc cần làm tiếp theo (session mới), theo thứ tự:**
1. **Dịch nốt `religion/POD_religion_docrtineandtenets_l_english.yml`** (1652 dòng — file lớn nhất `religion/`, để cuối cùng của việc #2). Baseline đã đo (dùng để đối chiếu sau khi dịch xong toàn bộ): dòng 1652, dòng trống 260, key thụt 1 space 1328, ref `$...$` 124, bracket `[...]` 1121 (RẤT NHIỀU — file này chắc chắn dùng nhiều `Glossary()`/`UmbraGlossaryLocalized()`, phải cẩn thận đặc biệt), icon 0, tag mở 39, tag đóng 31, `\n` 106, `\"` 2, `:0` 0 lần (không dùng hậu tố này).
2. Chia `docrtineandtenets` thành nhiều đợt/agent theo đoạn dòng (như đã làm với `traits_POD_l_english.yml` — ví dụ 5-6 đợt ~300 dòng/đợt), đừng giao nguyên file 1652 dòng cho 1 agent. Đọc trước để xem cấu trúc file (nhiều faith con hay 1 khối lớn?) rồi chia theo ranh giới tự nhiên (theo faith/đoạn `###`), không chia cứng theo số dòng nếu cắt ngang giữa 1 khối logic.
3. **CẢNH BÁO ĐÃ CÓ TIỀN LỆ SAI (xem mục B4m TERMINOLOGY.md):** một agent từng hallucinate rằng `docrtineandtenets` "đã dịch xong 100%" — đã xác nhận lại bằng `grep`/đếm ký tự tiếng Việt, **file này KHÔNG có bản dịch nào, 100% tiếng Anh tính đến hết session này**. Đừng tin bất kỳ claim nào khác nói ngược lại mà không tự grep xác nhận.
4. Xong `docrtineandtenets` → `religion/` đạt 36/36 → chuyển sang việc #3 (`custom_localization/` phần còn lại, xem mục "#3" bên dưới).
5. Trước hoặc sau khi làm `docrtineandtenets`, cân nhắc dành 1 đợt nhỏ rà soát nhất quán tên camp giữa `wyrm`/`gaia` (xem mục cảnh báo phía trên) — không bắt buộc phải làm ngay, có thể để dồn vào lúc rà soát toàn bộ `religion/` sau này.

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

### #8 — `lifestyles/`  6.740 key, 27 file

### #9 — 4 file ưu tiên từ root-level (tách ra làm sớm)

**Quyết định 2026-07-27:** tách 4 file sau ra khỏi khối root-level (việc #12), đôn lên làm trước `buildings/` — vì đây là những thứ người chơi thấy sớm nhất và nhiều nhất khi mới vào ván (tên khái niệm tra cứu, phe phái, chính thể, tước vị):

- `game_POD_concepts_l_english.yml` — **làm trước tiên trong 4 file này**, chứa các key `_desc` mà `Glossary()` ở bước glossary trỏ tới.
- `factions_POD_l_english.yml`
- `government_POD_l_english.yml`
- `titles_POD_l_english.yml`

### #10 — `buildings/`  6.309 key, 8 file

Có `:0` trong `building_grand_city_POD_l_english.yml`.

### #11 — `artifacts/`  1.489 key, 4 file
### #12 — root-level `*.yml` còn lại  17.974 key, 58 file (đã tách 4 file sang việc #9)

Khối lớn thứ hai. Gồm `secrets_POD_l_english.yml` (có `:0`), `effects_POD`, `POD_regiments`…

### #13 — `event_localization/`  20.530 key, 160 file

**Khối lớn nhất.** Văn xuôi thuần, đòn bẩy thấp → để cuối. Chia theo thư mục con (`POD_chargen/`, `POD_umbra/`, `POD_wraith/`, `POD_gehenna/`, `schemes/`, `POD_journeys/`…), mỗi thư mục 1–2 commit.

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
