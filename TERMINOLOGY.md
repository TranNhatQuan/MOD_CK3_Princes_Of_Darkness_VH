# TERMINOLOGY.md

Từ điển thuật ngữ cố định. **Một thuật ngữ = một bản dịch, dùng nhất quán ở mọi nơi.**

- Phần A (vanilla CK3): đã **xác minh** từ `base_game_vh/localization/english/`. Đây là bản dịch bắt buộc — không được đặt từ khác.
- Phần B (Princes of Darkness): **chưa có bản dịch nào tồn tại** trong repo. Các mục ở đây là *đề xuất cần chốt*, không phải sự thật đã có.

Quy tắc kỹ thuật khi áp dụng → [TRANSLATION_RULES.md](TRANSLATION_RULES.md)

---

## Nguyên tắc nguồn

**`base_game_vh` là chuẩn tuyệt đối.** Nếu một thuật ngữ đã có bản dịch ở đó thì dùng đúng bản đó, kể cả khi có cách dịch nghe hay hơn. Mọi mục ở Phần A đều đã được tra ngược từ file thật và ghi kèm key nguồn để kiểm chứng lại.

Chỉ khi `base_game_vh` **hoàn toàn không có** khái niệm tương ứng (thuật ngữ riêng của POD) thì mới đặt từ mới — xem Phần B.

---

# PHẦN A — Thuật ngữ vanilla CK3 (bắt buộc)

Cách tra thêm: chữ tiếng Anh **không còn tồn tại** trong `base_game_vh` (đã bị ghi đè). Phải tra bằng **key**:

```bash
grep -rhE '^\s*game_concept_hook:[0-9]* "' base_game_vh/localization/english/game_concepts_l_english.yml
```

## A1. Chỉ số

| English | Tiếng Việt | Key |
|---|---|---|
| Diplomacy | Ngoại giao | `diplomacy` |
| Martial | Quân sự | `martial` |
| Stewardship | Quản trị | `stewardship` |
| Intrigue | Âm mưu | `intrigue` |
| Learning | Học vấn | `learning` |
| Prowess | Dũng mãnh | `prowess` |
| Skill | Kỹ năng | `game_concept_skill` |

## A2. Hội đồng

| English | Tiếng Việt | Key |
|---|---|---|
| Council | Nội các | `game_concept_council` |
| Chancellor | Tể tướng | `councillor_chancellor` |
| Marshal | Nguyên soái | `councillor_marshal` |
| Steward | Quan Quản khố | `councillor_steward` |
| Spymaster | Trưởng gián điệp | `councillor_spymaster` |
| Court Chaplain | Giáo sĩ Triều đình | `councillor_court_chaplain` |

> Có biến thể theo chính thể (`_celestial_government_imperial` = "Bộ trưởng Tài chính", "Đại thừa tướng", "Ngự sử"…). Dùng đúng biến thể của từng key, đừng gộp.

## A3. Tài nguyên & chỉ số ẩn

| English | Tiếng Việt | Key |
|---|---|---|
| Gold | Vàng | `game_concept_gold` |
| Prestige | Uy tín | `game_concept_prestige` |
| Piety | Mộ đạo | `game_concept_piety` |
| Renown | Danh tiếng | `game_concept_dynasty_prestige` |
| Stress | Căng thẳng | `game_concept_stress` |
| Stress Level | Cấp độ Căng thẳng | `game_concept_stress_level` |
| Dread | Kinh sợ | `game_concept_dread` |
| Grandeur | Uy thế | `game_concept_grandeur` |
| Legitimacy | Tính chính danh | `legitimacy_*` |
| Tyranny | Chuyên chế | `game_concept_tyranny` |
| Opinion | Quan điểm | `game_concept_opinion` |
| Development | Phát triển | `game_concept_development` |
| Control | Kiểm soát | `game_concept_control` |
| County Control | Kiểm soát Bá quốc | `game_concept_county_control` |

## A4. Nhân vật

| English | Tiếng Việt | Key |
|---|---|---|
| Character | Nhân vật | `game_concept_character` |
| Ruler | Nhà cai trị | `game_concept_ruler` |
| Liege | Lãnh chúa | `game_concept_liege` |
| Vassal | Chư hầu | `game_concept_vassal` |
| Direct Vassal | Chư hầu Trực tiếp | `game_concept_direct_vassal` |
| Courtier | Cận thần | `game_concept_courtier` |
| Guest | Khách mời | `game_concept_guest` |
| Knight | Hiệp sỹ | `game_concept_knight` |
| Commander | Chỉ huy | `game_concept_commander` |
| Heir | Người Thừa kế | `game_concept_heir` |
| Holder | Người nắm giữ | `game_concept_holder` |
| Court | Triều đình | `game_concept_court` |

> Lưu ý chính tả: base dùng **"Hiệp sỹ"** (y), không phải "Hiệp sĩ". Giữ nguyên để nhất quán.

## A5. Lối sống & phát triển

| English | Tiếng Việt | Key |
|---|---|---|
| Lifestyle | Lối sống | `game_concept_lifestyle` |
| Intrigue Lifestyle | Lối sống Mưu lược | `game_concept_intrigue_lifestyle` |
| Perk | Thiên phú | `game_concept_perk` |
| Trait | Đặc điểm | `game_concept_trait` |
| Focus | Trọng tâm | `game_concept_focus` |
| Education | Giáo dục | `game_concept_education` |
| Modifier | Sửa đổi | `game_concept_modifier` |

## A6. Mưu mô

| English | Tiếng Việt | Key |
|---|---|---|
| Scheme | Âm mưu | `game_concept_scheme` |
| Secret | Bí mật | `game_concept_secret` |
| Hook | Kiềm chế | `game_concept_hook` |
| Nickname | Biệt hiệu | `game_concept_nickname` |

> `Intrigue` (chỉ số) và `Scheme` đều ra **"Âm mưu"** trong base — đây là điểm trùng có sẵn, không phải lỗi của người dịch mới. Trong ngữ cảnh mơ hồ, dùng "Lối sống Mưu lược" cho lifestyle để phân biệt.

## A7. Tước vị & lãnh thổ

| English | Tiếng Việt | Key |
|---|---|---|
| Baron | Nam tước | `baron` |
| Count | Bá tước | `count` |
| Duke | Công tước | `duke` |
| King | Quốc vương | `king` |
| Emperor | Hoàng đế | `emperor` |
| Barony | Nam tước địa | `barony` |
| County | Bá tước địa | `county` |
| Duchy | Công quốc | `duchy` |
| Kingdom | Vương quốc | `kingdom` |
| Empire | Đế quốc | `empire` |
| Title | Tước vị | `game_concept_title` |
| Primary Title | Tước vị Chính | `game_concept_primary_title` |
| Realm | Quốc gia | `game_concept_realm` |
| Domain | Lãnh địa | `game_concept_domain` |
| Domain Size | Quy mô Lãnh địa | `game_concept_domain_size` |
| Holding | Địa sản | `game_concept_holding` |
| Building | Công trình | `game_concept_buildings` |
| County Capital | Thủ phủ Bá quốc | `game_concept_county_capital` |
| Capital Duchy | Thủ đô Công quốc | `game_concept_capital_duchy` |
| De Jure | De Jure *(giữ nguyên)* | `game_concept_de_jure` |
| De Jure Drift | Biến động De Jure | `game_concept_de_jure_drift` |

> ⚠️ Base không nhất quán: **County** = "Bá tước địa" nhưng trong từ ghép lại là "Bá quốc" (`Thủ phủ Bá quốc`, `Kiểm soát Bá quốc`). Khi dịch POD: dùng **"Bá tước địa"** khi đứng một mình, **"Bá quốc"** trong từ ghép — bám theo tiền lệ của base.

## A8. Quân sự & chiến tranh

| English | Tiếng Việt | Key |
|---|---|---|
| Army | Quân đội | `game_concept_army` |
| Levies | Chiêu binh | `game_concept_levies` |
| Men-at-Arms | Men-at-Arms *(giữ nguyên tiếng Anh)* | `game_concept_men_at_arms` |
| Men-at-Arms Counter | Khắc chế Men-at-Arms | `game_concept_men_at_arms_counter` |
| Regiment | Trung đoàn | `game_concept_regiment` |
| Mercenaries | Lính đánh thuê | `game_concept_mercenaries` |
| Siege | Vây hãm | `game_concept_siege` |
| War | Chiến tranh | `game_concept_war` |
| Casus Belli | Biện minh Chiến tranh | `game_concept_casus_belli` |
| Claim | Yêu sách | `game_concept_claim` |
| Truce | Hiệp định Đình chiến | `game_concept_truce` |
| Faction | Phe phái | `game_concept_faction` |

> **Men-at-Arms để nguyên tiếng Anh** là quyết định có sẵn của base. Giữ nguyên trong POD, kể cả các loại MAA của POD.

## A9. Chính thể & hợp đồng

| English | Tiếng Việt | Key |
|---|---|---|
| Crown Authority | Uy quyền Quân chủ | `game_concept_crown_authority` |
| Limited Crown Authority | Uy quyền Quân chủ Giới hạn | `game_concept_limited_crown_authority` |
| Autonomous Vassals | Chư hầu Tự trị | `game_concept_autonomous_vassals` |
| Contract | Hợp đồng | `game_concept_contract` |
| Vassal Contract | Hợp đồng Chư hầu | `game_concept_vassal_contract` |
| Obligation | Nghĩa vụ | `game_concept_obligation` |
| Vassal Obligations | Nghĩa vụ Chư hầu | `game_concept_vassal_obligations` |
| Diarchy | Chia sẻ Quyền lực | `game_concept_diarchy` |

## A10. Dòng dõi, văn hóa, tín ngưỡng

| English | Tiếng Việt | Key |
|---|---|---|
| Dynasty | Triều đại | `game_concept_dynasty` |
| House | Gia tộc | `game_concept_house` |
| Succession | Kế vị | `game_concept_succession` |
| Culture | Văn hóa | `game_concept_culture` |
| Faith | Đức tin | `game_concept_faith` |
| Religion | Tôn giáo | `game_concept_religion` |
| Doctrine | Giáo lý | `game_concept_doctrine` |
| Core Tenet | Nguyên lý | `game_concept_core_tenet` |

## A11. Nội dung DLC

| English | Tiếng Việt | Key |
|---|---|---|
| Activity | Hoạt động | `game_concept_activity` |
| Travel | Lữ hành | `game_concept_travel` |
| Artifact | Hiện vật | `game_concept_artifact` |
| Accolade | Huân hiệu | `game_concept_accolade` |
| Decision | Quyết nghị | `game_concept_decision` |
| Struggle | Xung Đột | `game_concept_struggle` |
| Domicile | Cơ Sở Cư Trú | `game_concept_domicile` |
| Epidemic | Dịch Bệnh | `game_concept_epidemic` |

> ⚠️ Base không nhất quán ở **Artifact**: `game_concept_artifact` = "Hiện vật" nhưng `game_concept_artifact_rarity` = "**Bảo vật** Hiếm có". Chốt dùng **"Hiện vật"** cho POD.

---

# PHẦN B — Thuật ngữ Princes of Darkness

> **Trạng thái: chưa dịch dòng nào.** Toàn bộ 460 file POD vẫn là tiếng Anh, nên các mục dưới đây là do dự án tự đặt, không phải tra ra từ `base_game_vh`.
>
> Mục đánh ✅ **đã chốt** — dùng bắt buộc. Mục còn lại là **đề xuất**, chốt tới đâu đánh dấu tới đó.

## B0. Chính sách: được phép giữ nguyên tiếng Anh

Không bắt buộc phải Việt hóa mọi thuật ngữ POD. **Giữ nguyên tiếng Anh khi:**

- Đó là **danh từ riêng / thuật ngữ nguyên tác** World of Darkness mà cộng đồng đã quen đọc bằng tiếng Anh (`Clan`, `Vitae`, `Diablerie`, `Wyrm`, `Fera`, `Kuei-Jin`, tên các bộ tộc).
- Việt hóa sẽ **đụng thuật ngữ vanilla** đã có (trường hợp `Clan` vs `House` = "Gia tộc").
- Bản dịch tiếng Việt nghe gượng hoặc dài hơn hẳn, làm vỡ UI.

Có tiền lệ trong chính `base_game_vh`: **Men-at-Arms** và **De Jure** được giữ nguyên tiếng Anh.

Hai điều kiện đi kèm khi giữ nguyên:

1. **Giữ nguyên toàn bộ**, không nửa Anh nửa Việt. `Clan Curse` → `Lời nguyền Clan` là chấp nhận được (từ ghép), nhưng đừng lúc `Clan` lúc `Thị tộc`.
2. **Vẫn phải nhất quán** — ghi vào bảng dưới rồi dùng đúng như thế ở mọi nơi.

## B1. Nơi thuật ngữ POD thực sự được định nghĩa

Không đặt từ tùy tiện ở từng file. Ba nơi này là nguồn, dịch ở đây thì tự lan ra toàn mod:

| Nguồn | Điều khiển |
|---|---|
| [glossary_POD_l_english.yml](princesofdarkness/localization/english/glossary_POD_l_english.yml) | **105 key**: 28 shortcut `$pod_*$` / `$glossary_*$` (tham số 1 của `Glossary()` là chữ hiển thị) + 12 key `_tt` chứa nội dung tooltip + **65 key `podgloss.*`** (22 Kuei-Jin, 43 lịch sử) là văn xuôi thuần. Tất cả đều phải dịch |
| [custom_localization/POD_misc_custom_loc_l_english.yml](princesofdarkness/localization/english/custom_localization/POD_misc_custom_loc_l_english.yml) | `POD_splat_*` — **không chứa chữ**, chỉ trỏ `[GetTrait('vampire').GetName(...)]` |
| [traits/](princesofdarkness/localization/english/traits/) | Tên thật của mọi splat. Dịch `trait_vampire` là đổi luôn mọi `$POD_splat_vampire$` |

**Đòn bẩy thực đo được** của các shortcut trong `glossary_POD` (đếm trong `localization/english/`):

| Shortcut | File | Lần dùng |
|---|---|---|
| `$glossary_wyrm$` | 38 | 161 |
| `$glossary_fera$` | 48 | 151 |
| `$glossary_wyld$` | 19 | 44 |
| `$glossary_weaver$` | 14 | 44 |
| `$glossary_triat$` | 13 | 20 |
| `$glossary_wyrm_triatic$` | 4 | 6 |

→ Chỉ 6 key này đã chi phối **426 điểm gọi**. Đây là lý do phải dịch `glossary_POD` trước mọi thứ khác.

> ⚠️ **Chiều ngược lại cũng có:** `trait_fera` trong `traits/` được định nghĩa là `"$glossary_fera$"`, và `gaia_devil_name` / `gaia_death_deity_name` trong `religion/` là `"$glossary_wyrm$"`. Nghĩa là dịch `glossary_fera`/`glossary_wyrm` ở đây **đã đổi luôn tên trait và tên thần** ở hai file kia. Khi tới `traits/` (bước 3) đừng dịch lại — chúng đã có giá trị rồi.

→ Muốn đổi cách gọi "Vampire" toàn mod thì sửa `trait_vampire` trong `traits/`, **không** sửa `POD_splat_vampire`.

## B2. Thuật ngữ ma cà rồng (từ `glossary_POD_l_english.yml`)

| English | Đề xuất | Ghi chú |
|---|---|---|
| World of Darkness | Thế Giới Bóng Tối | ✅ `pod_wod` |
| Vampire | Ma cà rồng | `trait_vampire` — *chốt ở `traits/`, bước 3* |
| Cainite / Cainites | Hậu duệ Cain | ✅ `pod_cainite(s)` |
| Clan | **Clan** *(giữ nguyên — đã chốt)* | ✅ `pod_clan` — tránh đụng `House` = "Gia tộc" của vanilla |
| Clan Curse | Lời nguyền Clan | ✅ `glossary_clan_curse` |
| Discipline / Disciplines | Dị năng | ✅ `pod_discipline(s)` |
| Vitae | Vitae *(giữ nguyên)* | ✅ `pod_vitae` — thuật ngữ Latin trong nguyên tác |
| Embrace / Embraced | Nghi lễ Trao truyền / được Trao truyền | ✅ `pod_Embrace(d)` |
| Diablerie | Diablerie *(giữ nguyên)* | ✅ `pod_diablerie` |
| Torpor | Miên trạng | ✅ `pod_torpor` |
| Kuei-Jin | Kuei-Jin *(giữ nguyên)* | ✅ `pod_kueijin` |
| Courts of Love | Tòa Ái Tình | ✅ `glossary_courts_of_love` |
| Osirian League | Liên minh Osiris | ✅ `glossary_osirian_league` |

> ✅ = đã áp dụng vào file, không còn là đề xuất.
| Khitta / Khittas | Khitta *(giữ nguyên)* | `glossary_khitta(s)` |

### B2b. Đã chốt khi dịch `glossary_POD` đợt 1a (2026-07-26)

Không có mục nào dưới đây tồn tại trong `base_game_vh` — đã tra và xác nhận. Tất cả **đã áp dụng vào file**, dùng bắt buộc từ đây.

| English | Tiếng Việt | Nguồn / ghi chú |
|---|---|---|
| Book of Nod | Sách Nod | `glossary_clan_curse_tt` |
| Caine | Caine *(giữ nguyên)* | danh từ riêng, B0 |
| Antediluvian | Antediluvian *(giữ nguyên)* | B0 |
| Matriarch | Mẫu Chủ | `glossary_courts_of_love_tt` — chức sắc Toreador, không phải tước phong kiến |
| werecat | người mèo | `glossary_osirian_league_tt` |
| Children of Osiris | Con Cái Osiris | bloodline ma cà rồng |
| Disciples of Anubis | Đệ Tử Anubis | |
| Cult of Isis | Giáo phái Isis | |
| wizard-priest | tăng lữ pháp thuật | |
| lineage | chi hệ | tách khỏi `Bloodline` = "Huyết thống" (B5) |
| Sultan | Sultan *(giữ nguyên)* | ⚠️ **đi lệch khỏi base** — xem ghi chú dưới |
| Garou, Silent Striders, Bubasti, Ashirra, Khitta, tên Clan (Lasombra, Assamite, Nosferatu, Toreador, Ventrue, Setite, True Brujah, Gangrel) | *giữ nguyên* | B0 |

> ⚠️ **`Sultan` là ngoại lệ có ý thức.** `base_game_vh` dịch `sultan:0` = "Quốc vương Hồi giáo". Nhưng trong `glossary_khitta_tt`, từ này đứng cặp với `Prince` — mà `Prince` đã chốt giữ nguyên tiếng Anh (B5). Viết "Quốc vương Hồi giáo hoặc Prince" thì nửa Anh nửa Việt, vỡ giọng. Chọn giữ "Sultan" theo B0 (cặp chức sắc đi liền nhau).
> **Phạm vi ngoại lệ: chỉ khi `Sultan` đứng cặp với `Prince`.** Nếu gặp `Sultan` một mình như tước vị phong kiến ở file khác → dùng "Quốc vương Hồi giáo" của base.

> **Số nhiều gộp làm một** (theo mục 7 TRANSLATION_RULES.md — tiếng Việt không biến đổi từ): `pod_cainite`/`pod_cainites` → cùng "Hậu duệ Cain"; `pod_discipline`/`pod_disciplines` → cùng "Dị năng"; `glossary_khitta`/`glossary_khittas` → cùng "Khitta". Key vẫn giữ đủ cả hai, chỉ giá trị trùng nhau.

## B3. Thuật ngữ người sói / Fera (từ `glossary_POD_l_english.yml`)

| English | Đề xuất | Ghi chú |
|---|---|---|
| Fera | Fera *(giữ nguyên)* | ✅ `glossary_fera` |
| Triat | Tam Vị | ✅ `glossary_triat` |
| Wyld | Wyld *(giữ nguyên)* | ✅ `glossary_wyld` |
| Weaver | Weaver *(giữ nguyên)* | ✅ `glossary_weaver` |
| Wyrm | Wyrm *(giữ nguyên)* | ✅ `glossary_wyrm` |
| Triatic Wyrm | Wyrm Tam Vị | ✅ `glossary_wyrm_triatic` |
| Apep / Apophis | Apep / Apophis *(giữ nguyên)* | ✅ `glossary_wyrm_apep`, `_apophis` |
| Beast of War | Ác Thú Chiến Tranh | ✅ `glossary_wyrm_calamity` |
| Eater of Souls | Kẻ Nuốt Linh Hồn | ✅ `glossary_wyrm_consumption` |
| Defiler Wyrm | Wyrm Ô Uế | ✅ `glossary_wyrm_corruption` |

> **Wyld / Weaver / Wyrm giữ nguyên tiếng Anh là bắt buộc, không phải tùy chọn.** Ba từ này còn là **tên doctrine và tên tôn giáo** trong `religion/` (`doctrine_fera_triat_alignment_wyld_name`, `wyrm_religion_adj`, `rf_wyrm`…). Dịch ở glossary mà không dịch ở đó — hoặc ngược lại — là tạo hai bản dịch cho cùng một thực thể.

### B3b. Đã chốt khi dịch `glossary_POD` đợt 1b (2026-07-26)

| English | Tiếng Việt | Nguồn / ghi chú |
|---|---|---|
| Gaia | Gaia *(giữ nguyên)* | ✅ có tiền lệ base: `Gaia:0 "Gaia"` |
| Mother Goddess | Mẫu Thần | ✅ `glossary_fera_tt` |
| Chaos | Hỗn loạn | ✅ theo base (15 lần "Hỗn loạn", 0 lần "Hỗn mang") |
| spirit *(thực thể linh giới)* | linh hồn | ✅ theo base (20 lần "Linh hồn") |
| Rage | phẫn nộ | ✅ theo base (dạng chiếm đa số) |
| Entropy | Hoại Diệt | ✅ `glossary_wyrm_tt` |
| Creation *(Tạo Hóa)* | Tạo Hóa | ✅ `glossary_wyrm_tt` |
| Dark God | Hắc Thần | ✅ `glossary_wyrm_tt` |
| Wyrm of Calamity | Wyrm Tai Ương | ✅ biến thể của `Beast of War` |
| Wyrm of Consumption | Wyrm Cuồng Thực | ✅ biến thể của `Eater of Souls` |
| Wyrm of Corruption | Wyrm Bôi Nhọ | ✅ biến thể của `Defiler Wyrm` |
| Calamity / Consumption / Corruption *(3 mặt của Wyrm)* | Tai Ương / Cuồng Thực / Ô Uế | ✅ `glossary_wyrm_tt`, tham số 1 của `Glossary()` |
| Werecat / Werecrocodile / Weredragon | Người mèo / Người cá sấu / Người rồng | ✅ `glossary_fera_tt` |
| Garou | Garou *(giữ nguyên)* | ✅ tên bộ tộc, B0 |
| Garden of Eden | Vườn Địa Đàng | ✅ `glossary_wyrm_corruption_tt` |

> ⚠️ **`Corruption` có hai bản dịch có chủ ý, tùy vị trí.** `glossary_wyrm_corruption` (tên cái đầu) = "Wyrm Ô Uế" — giữ theo mục B3 đã có. Nhưng trong `glossary_wyrm_tt`, `[Glossary('Corruption', …)]` đứng thành dãy ba danh từ trừu tượng với `Calamity`/`Consumption`, nên dịch là "Ô Uế" (không kèm "Wyrm"). Cùng một khái niệm, khác chức năng ngữ pháp — **không phải** vi phạm quy tắc một-thuật-ngữ-một-bản-dịch.

## B3c. Kuei-Jin — đã chốt khi dịch `glossary_POD` đợt 1c (2026-07-26)

Register Hán-Việt Phật giáo. **Tiền lệ trong base:** `bodhisattva_barbarian` = "Bồ Tát Man" → base chấp nhận register này.

| English | Tiếng Việt | Nguồn / ghi chú |
|---|---|---|
| Yama King(s) | Diêm Ma Vương | ✅ `podgloss.yamaking` |
| Devil Kings | Ma Vương | ✅ tên gọi khác của Yama King |
| Yama Queen | Diêm Ma Nữ Vương | ✅ `podgloss.toumu` |
| Yomi Hell(s) | Địa Ngục Yomi | ✅ tham số 2 của `UmbraGlossaryLocalized('yomi_wan', …)` |
| Yomi | Yomi *(giữ nguyên)* | ✅ |
| Dharma | Pháp Môn | ✅ `podgloss.dharma` |
| Bodhisattva | Bồ Tát | ✅ **có tiền lệ base** |
| Arhat / Grand Arhat | La Hán / Đại La Hán | ✅ `podgloss.arhat` |
| Hundred Clouds | Bách Vân | ✅ `podgloss.hundredclouds` |
| Demon Emperor | Ma Hoàng | ✅ `podgloss.demonemperor` |
| August Personage of Jade | Ngọc Hoàng | ✅ thuật ngữ tiếng Việt đã có sẵn |
| Wheel of Ages | Bánh Xe Kỷ Nguyên | ✅ `podgloss.wheelofages` |
| Sixth Age | Kỷ Nguyên Thứ Sáu | ✅ |
| Paradise *(mạt thế Kuei-Jin)* | Cực Lạc | ✅ `podgloss.wheelofages` |
| Heavens / Heaven | Thiên Đình | ✅ |
| Karmic cycle | vòng Nghiệp Báo | ✅ `podgloss.dharma` |
| Enlightenment | Giác Ngộ | ✅ |
| Final Death | Cái Chết Cuối Cùng | ✅ `podgloss.bodhisattva` |
| Chi | Khí | ✅ `podgloss.shikome` |
| Yin / Yang | Âm / Dương | ✅ |
| Yin Aspect | Âm Tướng | ✅ `podgloss.emmao` |
| True Name | Chân Danh | ✅ `podgloss.truename` |
| Kindred of the East | Huyết tộc Đông phương | ✅ `podgloss.toumu` |
| Iron Empress | Thiết Nữ Hoàng | ✅ `podgloss.toumu` |
| Hell of Spiked Chains | Địa Ngục Xiềng Gai | ✅ `podgloss.hellspikedchains` |
| Wicked City | Thành Đô Tà Nghiệt | ✅ `podgloss.wickedcity` |
| Night Realm | Dạ Giới | ✅ `podgloss.kakuri` |
| Pit of Salt and Iron | Hầm Muối và Sắt | ✅ `podgloss.wuhua` |
| Iron Brothels | Thanh Lâu Sắt | ✅ `podgloss.wuhua` |
| Infant Devil Civilizer | Quan Khai Hóa Ấu Ma | ✅ `podgloss.infantdevilcivilizer` |
| Judge of Balance | Phán Quan Cân Bằng | ✅ `podgloss.emmao` |
| Demonologist | Nhà Quỷ Học | ✅ `podgloss.truename` |
| Wu | Wu *(giữ nguyên)* | ✅ đơn vị xã hội, giải thích trong `podgloss.wu` |
| Ren | Ren *(giữ nguyên)* | ✅ giữ trong `#italic`, cách gọi Chân Danh của Mummy |
| Nomenclature Hekau | *(giữ nguyên)* | ✅ tên hệ pháp thuật Mummy |
| Emma-O, Mikaboshi, Tou Mu, Wu Hua, Dokhor-Khan, Kakuri, Shikome, Penangallan, Methuselah, Saulot, Yen-Lo, Anda, Itugen | *(giữ nguyên)* | ✅ danh từ riêng, B0 |

### ⚠️ Ngũ Pháp Môn — tên chuẩn nằm ở `religion/`, KHÔNG ở `traits/`

Tôi đã tra: 5 Dharma **không phải trait**, chúng là **faith** (tôn giáo) trong [religion/POD_religion_kueijin_l_english.yml](princesofdarkness/localization/english/religion/POD_religion_kueijin_l_english.yml):

| Key nguồn (chưa dịch) | Chữ tiếng Anh | Đã dùng ở `podgloss.dharma` |
|---|---|---|
| `deviltigers_religion` | Devil Tiger | **Ma Hổ** |
| `boneflowers_religion` | Song of the Shadow | **Ảnh Ca** |
| `resplendentcranes_religion` | Resplendent Crane | **Thụy Hạc** |
| *(Bone Flowers — tên gọi khác của `boneflowers_religion`)* | Bone Flowers | **Cốt Hoa** |
| `thrashingdragons_religion` | Thrashing Dragon | **Đằng Long** |

> **Khi dịch `religion/` phải dùng đúng 5 tên trên.** Lưu ý cái bẫy của POD: key `boneflowers_religion` lại hiển thị là "Song of the Shadow", còn "Bone Flowers" là tên gọi thứ hai của cùng tôn giáo đó — nên `Ảnh Ca` và `Cốt Hoa` là **hai tên của một Pháp Môn**, không phải hai Pháp Môn.
>
> Hai key trong `religion/` cũng đang **trỏ ngược về** đợt 1c này: `kueijin_high_god_name` = "the August Personage of Jade" và `kueijin_devil_name` = `"the [Glossary('Demon Emperor','podgloss.demonemperor')]"`. Khi dịch `religion/` phải khớp "Ngọc Hoàng" / "Ma Hoàng".

## B3d. Glossary lịch sử — đã chốt đợt 1d (2026-07-26)

43 key `podgloss.*` lịch sử Hàn / Việt / Nhật / Indonesia. Không có thuật ngữ WoD.

Theo base (đã tra, dùng dạng chiếm đa số): **Nho giáo** (16 lần, không dùng "Khổng giáo"), **Phật giáo**, **nô lệ**, **Tể tướng**, **Đô đốc**, **khoa cử**, giữ nguyên **Goryeo** / **Joseon** / **Majapahit** / **Nusantara**, dùng **Đại Việt** / **Triều Tiên**.

| English | Tiếng Việt |
|---|---|
| Confucian / neo-Confucian | Nho giáo / Tân Nho giáo |
| Three Extraordinary Watches | Tam Biệt Sao |
| Noble Youth Guards | Đội Cấm Vệ Quý Tộc Thiếu Niên |
| Hall of Worthies | Tập Hiền Điện |
| Literati Purges | Thanh Trừng Văn Nhân |
| turtle ship | Quy thuyền |
| temple name | Miếu hiệu |
| stupa | bảo tháp |
| Kenshō | kiến tính |
| Dharmadhatu | Pháp Giới |
| execution of nine relations | Tru di cửu tộc |
| Patih / Rakryan Patih | Patih *(giữ nguyên)* / Thượng thư |
| harbour master | Quan cảng vụ |
| kshatriya, silat, kakawin, Wali, Songo, Bentahara, Laksamana, Kinalakian, Bhayangkara | *(giữ nguyên)* |

> **Chính tả tiếng Việt trong bản gốc bị sai dấu** — POD viết `Đai Viet`, `Trân`, `Đuc Thanh Hung Đao`, `Cà Đôc Duoc`, `Đan Viêt`. Bản dịch **khôi phục dấu đúng**: Đại Việt, nhà Trần, Đức Thánh Hưng Đạo, Cà Độc Dược. Đây là sửa lỗi của bản gốc, không phải đổi nghĩa.

## B4. Splat (chủng loài) — nguồn: `traits/`

Danh sách đầy đủ lấy từ `POD_splat_*`:

`spirit`, `vampire`, `kueijin`, `werewolf`, `ajaba`, `entomos`, `apis`, `bastet`, `camazotz`, `corax`, `grondr`, `gurahl`, `kitsune`, `mokole`, `nagah`, `nuwisha`, `ratkin`, `rokea`, `fae`, `changeling`, `mage`, `mummy`, `demon`, `wraith`, `supehunter`, `revenant`, `ghoul`, `mortal`

**✅ ĐÃ CHỐT VÀ ĐÃ ÁP DỤNG** (2026-07-26, bước 3). Đây là tên thật trong `traits/`, không còn là đề xuất.

| English (bản gốc) | Tiếng Việt | Key |
|---|---|---|
| Vampire | Ma cà rồng | `trait_vampire` |
| Werewolf | Người sói | `trait_werewolf` |
| Mage | Pháp sư | `trait_mage` |
| Mummy | Xác ướp | `trait_mummy` |
| Demon | Ác quỷ | `trait_demon` |
| Wraith | Oan hồn | `trait_wraith` |
| Hunter | Thợ săn | `trait_supehunter` ⚠️ key là `supehunter`, không phải `hunter` |
| Ghoul | Bộc huyết | `trait_ghoul` |
| Revenant | Huyết tộc Hồi sinh | `trait_revenant` |
| Mortal | Phàm nhân | `trait_mortal` |
| Spirit | Linh thể | `trait_spirit` *(trong `POD_fera_traits`)* |
| **True Fae** | **Fae Chân Chính** | `trait_fae` ⚠️ bản gốc là "True Fae", không phải "Fae" |
| Changeling | Đứa Trẻ Bị Tráo | `trait_changeling` |
| Kuei-jin → **Kuei-Jin** | Kuei-Jin *(giữ nguyên, đã chuẩn hóa hoa/thường)* | `trait_kueijin` |
| Fera | *(không sửa)* | `trait_fera` = `"$glossary_fera$"` — đã có giá trị từ bước 1 |

14 tên bộ tộc Fera giữ nguyên **danh từ riêng** (B4), đã kiểm tra từng dòng: `Ajaba`, `Éntomos`, `Apis`, `Bastet`, `Camazotz`, `Corax`, `Grondr`, `Gurahl`, `Kitsune`, `Mokolé`, `Nagah`, `Nuwisha`, `Ratkin`, `Rokea`. Giữ nguyên cả dấu phụ `É`/`é`.

> ⚠️ **`Kuei-jin` → `Kuei-Jin` là sửa lỗi nhất quán của bản gốc.** POD tự viết hai kiểu: `Kuei-Jin` 25 lần, `Kuei-jin` 16 lần. Đã chuẩn hóa về dạng chiếm đa số. Khi dịch các file khác gặp `Kuei-jin` thì cũng viết `Kuei-Jin`.

> ⚠️ **`trait_fae` là "True Fae", không phải "Fae".** Đừng dịch thành "Fae" trơn — mục B4 cũ ghi "Fae → giữ nguyên" là thiếu chính xác. `$POD_splat_fae$` hiển thị "Fae" (chữ trong `#L` của tooltip, giữ nguyên), còn *trait* thì tên đầy đủ là "Fae Chân Chính".

### Mô tả splat (`_desc`) — đã dịch kèm

Đã dịch 20 key `_desc` của các splat: `vampire`, `ghoul`, `mortal`, `mage`, `wraith`, `kueijin`, `supehunter`, `demon`, `mummy`, `revenant`, `spirit`, `fae`, `changeling`, `werewolf`, và 16 mô tả bộ tộc Fera (`ajaba`, `ananasi`, `apis`, `bastet`, `camazotz`, `corax`, `grondr`, `gurahl`, `kitsune`, `mokole`, `nagah`, `nuwisha`, `ratkin`, `rokea`, `entomos`).

Thuật ngữ mới đặt trong các mô tả này:

| English | Tiếng Việt |
|---|---|
| War of Rage | Cuộc Chiến Phẫn Nộ |
| Rage *(chỉ số Garou)* | Phẫn Nộ |
| Changing Breeds | Chủng Biến Hình |
| Beast Courts | Thú Triều |
| Middle Kingdom | Trung Vương Quốc |
| Heavenly Mandate | Thiên Mệnh |
| Skull Pigs | Trư Đầu Cốt |
| Moon-bulls | Ngưu Nguyệt |
| Matchmakers of Gaia | Kẻ Tác Hợp của Gaia |
| Judges of Gaia | Phán Quan của Gaia |
| Lizard Kings | Vua Thằn Lằn |
| Old Man Coyote | Lão Sói Đồng |
| Changeling Way | Đạo Trao Đổi |
| Umbrood | Umbrood *(giữ nguyên)* |
| werehyena / werespider / wereaurochs / werebat / wereraven / wereboar / werebear / werefox / weresaurian / weresnake / werecoyote / wererat / wereshark | người linh cẩu / người nhện / người bò rừng / người dơi / người quạ / người lợn rừng / người gấu / người cáo / người thằn lằn / người rắn / người sói đồng / người chuột / người cá mập |
| Firstborn, Dark-kin, Inanimae, Adhene, Kithain, Ananasa, Anansi, Luna, C'etites, chimera | *(giữ nguyên — danh từ riêng)* |

> **Chưa dịch trong `traits/`:** ~1.800 key còn lại (trait tính cách, Dị năng, thế hệ, predator type, kith Fae…). Bước 3 theo định nghĩa của dự án là "quyết tên mọi splat" — phần đó đã xong. Phần còn lại thuộc công việc cơ học về sau.

Tên bộ tộc Fera (`bastet`, `corax`, `kitsune`, `mokole`, `nagah`, `nuwisha`, `ratkin`, `rokea`, `ajaba`, `apis`, `camazotz`, `entomos`, `grondr`, `gurahl`) là **danh từ riêng trong nguyên tác → giữ nguyên**, giống cách base giữ tên riêng vanilla.

## B4b. Thuật ngữ Fae / Changeling (từ `POD_fae_traits_l_english.yml`)

Nguồn: `traits/POD_fae_traits_l_english.yml` (330 dòng, kith Fae). Không có tiền lệ nào trong `base_game_vh`. Theo B0: **giữ nguyên tiếng Anh** cho danh từ WoD lõi — dịch nghĩa các từ này (Glamour, Banality, Cantrip…) sẽ vừa dài dòng vừa dễ lệch nghĩa giữa các file.

| English | Xử lý | Ghi chú |
|---|---|---|
| Glamour | *giữ nguyên* | năng lượng phép của Fae, tương đương Vitae/Mộ đạo nhưng không có khái niệm vanilla gần |
| Banality | *giữ nguyên* | lực đối nghịch Glamour |
| Kithain | *giữ nguyên* | tên gọi chung giống loài fae có tổ tiên loài người |
| Chimera | *giữ nguyên* | sinh vật ảo tạo từ Glamour |
| Seelie / Unseelie | *giữ nguyên* | hai Triều đình (Courts) đối lập |
| Cantrip | *giữ nguyên* | phép thuật của Fae, gồm Art + Realm |
| Realm | *giữ nguyên* | ✅ đã dùng: `Realm Actor Mastery` → "Tinh Thông Realm Actor" (xem bảng trait bên dưới) |
| Art | *giữ nguyên* | trường phái phép thuật (Chicanery, Legerdemain…) |
| Sliver | *giữ nguyên* | biến thể Art của Inanimae (Petros, Aquis, Pyros, Stratus, Verdage) |
| Bunk | *giữ nguyên* | nghi thức triệu Glamour để đọc cantrip |
| Arcadia | *giữ nguyên* | quê hương nguyên thủy của Fae |
| Chrysalis | *giữ nguyên* | nghi thức "thức tỉnh" thành Changeling |
| Dán | *giữ nguyên* | khái niệm Số phận/Định mệnh của Kithain gốc Đông Á |
| Kwannon-jin | *giữ nguyên* | phân loại xã hội Hsien |
| Elegbara | *giữ nguyên* | tên gọi Kithain châu Phi (Eshu) |
| Dreaming | Cõi Mộng | ✅ dịch nghĩa — dùng trong `[UmbraGlossary('dreaming')]`, tag không dịch nhưng khi văn xuôi nhắc "the Dreaming" thì dịch "Cõi Mộng" |
| freehold | tổ ấm | nơi trú ẩn của Changeling |
| Patron Council | Hội đồng Bảo Trợ | ✅ `trait_patron_council` |

### Tên kith (giữ nguyên toàn bộ — danh từ riêng chủng loài)

Sidhe, Boggan, Clurichaun, Eshu, Ghille dhu, Oba, Nocker, Piskey, Pooka, Troll, Redcap, River Hag, Satyr, Sluagh, Swan Maiden, Wichtel, Ifrit, Lilin, Qareen, Shaytan, Biloko, Djedi, Kuino, Obambo, Okubili, Hsien (Chu-ih-yu, Chu Jung, Fu Hsi, Hanumen, Heng Po, Hou-chi, Komuko, Nyan, Suijen, Tanuki), Inanimae (Glome, Kubera, Ondine, Paroseme, Solimond, Mannikin), Domovoi, Leshii, Kikimora, Polevik, Vodyanoi, Berenginy, Bannik, Dvorovoi — tên riêng slavic/Eshu cũng giữ nguyên (Agemo, Itiyere, Orisha-Oko, Taiyewo, Iroko, Olokuta, Kehinde, Ijapa, Jakuta, Oshosi, Olu-Igbo, Sonponno).

Tên Art/Sliver giữ nguyên: Chicanery, Legerdemain, Primal, Soothsay, Wayfare, Chronos, Dream-Craft, Naming, Sovereign, Infusion, Tale Craft, Aphrodesia, Kryos, Metamorphosis, Pyretics, Petros, Aquis, Pyros, Stratus, Verdage, Tieh Tan, Lin Tan, Shui Tan, Hou Tan, Di Tan, Nei Tan.

### Mẫu câu đã dùng

`trait_realm_actor: "Realm Actor Mastery"` → **"Tinh Thông Realm Actor"** (mẫu: `Tinh Thông Realm <Tên>` cho 6 Realm; `Art [Tên] Mastery` → **"Tinh Thông Art [Tên]"**; hậu tố `_advanced` giữ cùng mẫu "Tinh Thông").

## B4c. Thuật ngữ Fera / Werewolf (từ `POD_fera_traits_l_english.yml`)

Nguồn: `traits/POD_fera_traits_l_english.yml` (479 dòng, phần trait phụ). Khác với B4b (Fae — giữ nguyên tiếng Anh), ở đây **dịch nghĩa** các danh từ hệ thống/chỉ số, theo đúng cách `base_game_vh` dịch nghĩa chỉ số vanilla (Prestige→Uy tín…). Tên riêng chủng loài (Garou, Ajaba, Ananasi, Bastet, Mokolé, Kitsune…) và tên gọi cấp bậc/giáo phái cụ thể (Ahroun, Ragabash, Ronin…) vẫn **giữ nguyên** theo B4/B0.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Rank | Cấp Bậc | hệ thống thứ bậc Garou/Fera nói chung |
| Renown | Danh Vọng | tài nguyên tích lũy để lên Cấp Bậc |
| Auspice | Thánh Triều | cách phân loại theo tuần trăng lúc sinh (Garou, Gurahl…) |
| Solar Auspice | Thánh Triều Mặt Trời | biến thể của Mokolé |
| Seasonal Auspice | Thánh Triều Mùa | biến thể của Makara/Nagah Ấn Độ |
| Lunisolar Auspice | Thánh Triều Nhật Nguyệt | biến thể của Apis |
| Water Auspice | Thánh Triều Nước | biến thể của Rokea |
| Breed | Dòng Sinh | cách sinh ra: Homid/Lupus/Beastborn... |
| Path | Đạo Lộ | hệ thống của Éntomos/Ananasi thay Auspice |
| Aspect | Diện Mạo | hệ thống của Ajaba (Dawn/Dusk) thay Auspice |
| Faction | Phe Phái | hệ thống của Ratkin/Éntomos |
| Clade | Chi Phái | phân loại phụ của Éntomos |
| Gnosis | Trí Ngộ | năng lượng phép thuật/tâm linh của Fera |
| Bane | Tà Linh | linh thể bị Wyrm làm ô uế |
| Abomination | Nghịch Đồ | người sói bị Trao truyền thành ma cà rồng |
| Kinfolk | Thân Tộc | con người/thú vật có quan hệ huyết thống với Fera |
| Umbrood | Umbrood *(giữ nguyên)* | đã chốt ở B4 (mô tả splat) |
| Stream | Chi Phái *(của Mokolé)* | 4 nhánh Mokolé: Mokolé-mbembe, Gumagan, Makara, Zhong Lung — tên riêng giữ nguyên |

### Tên riêng giữ nguyên (không dịch)

Tên bộ tộc/dòng giống/chi phái cụ thể: Garou, Ajaba, Ananasi, Apis, Bastet, Camazotz, Corax, Grondr, Gurahl, Kitsune, Mokolé, Nagah, Nuwisha, Ratkin, Rokea, Éntomos; các biến thể Wyrm-hóa (Ozuzo, Histpah, Buzzards, Purgers, Nokhomi, Mad Destroyers, Balefire Sharks, Xibalan, Skull Pig, Kumo); tên Cấp Bậc theo Thánh Triều (Ahroun, Galliard, Philodox, Theurge, Ragabash và biến thể ở Gurahl: Uzmati, Kojubat, Rishi, Kieh, Arcas); tên Thánh Triều Mặt Trời của Mokolé (Rising Sun…dịch có, xem dưới) và tên phe của Ratkin (Warriors, Bards, Knife Skulkers, Shadow Seers, Tunnel Runners — dịch nghĩa vì là danh từ mô tả, không phải danh xưng ngoại lai); tên Linh thể (Rabbit Spirit…dịch nghĩa vì mô tả động vật, không phải danh xưng).

> Ghi chú: các tên "Rising Sun", "Warriors", "Rabbit Spirit" v.v. là **cụm mô tả bằng tiếng Anh thường**, không phải danh xưng ngoại lai kiểu "Ahroun" hay "Sidhe" — nên áp dụng dịch nghĩa bình thường như văn xuôi, khác với nhóm tên riêng ở trên.

## B4d. Thuật ngữ ma cà rồng bổ sung (từ `traits_POD_l_english.yml`)

Nguồn: `traits/traits_POD_l_english.yml` (1563 dòng — file lớn nhất trong `traits/`). Gồm tên clan/bloodline/lineage, Dị năng (Discipline), thế hệ (generation), bệnh tật.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Advanced *(hậu tố cấp độ Dị năng)* | Nâng cao | Tra base_game_vh: không có khái niệm WoD tương ứng, nhưng base dùng "Nâng cao" cho hậu tố cấp độ (`found_kingdom_decision_advanced_succesion`→"Kế vị Nâng cao"). Áp dụng: `trait_animalismadvanced`→"Animalism Nâng cao" |
| Frenzy | Phẫn Cuồng | Tra base_game_vh: không có khái niệm tương ứng (đây là cơ chế riêng của WoD). Đặt mới, phân biệt với "Phẫn Nộ" (Rage của Garou, đã chốt B3b) |
| Bloodsorcery / Blood Sorcery | Huyết Thuật | không có tiền lệ base; Dị năng hệ phù thủy máu (Tremere...) |
| Necromancy | Thuật Gọi Hồn | tham khảo base_game_vh (`NECROMANCER_GLOSS`, flavor text, dùng "thuật gọi hồn" cho "necromancer") dù không phải game-concept chính thức |
| Clan Curse (nhắc lại) | Lời nguyền Clan | đã chốt B2, dùng "Lời nguyền" nhất quán với base (`Lời nguyền` cho "curse" ở nhiều nơi) |
| Bloodline | Huyết thống | đã chốt B5 |
| Lineage | Chi hệ | đã chốt B2b, tách khỏi Bloodline |
| Legacy *(của Laibon)* | Di Sản | các dòng Laibon (Akunanse, Guruhi, Ishtarri…) — tên riêng giữ nguyên, "Legacy" dịch nghĩa |
| Caste *(của Assamite)* | Đẳng Cấp | hệ thống ba đẳng cấp Assamite (Warrior, Vizier, Sorcerer) |
| Thin-Blood(ed) | Máu Loãng | ma cà rồng thế hệ cao/máu yếu |
| Antediluvian | Antediluvian *(giữ nguyên)* | đã chốt B2b |
| Methuselah | Methuselah *(giữ nguyên)* | đã chốt B3c |
| Wight | Wight *(giữ nguyên)* | ma cà rồng đã sa vào Dã Thú hoàn toàn, danh từ riêng WoD |
| Gargoyle | Gargoyle *(giữ nguyên)* | bloodline, danh từ riêng |
| Sabbat | Sabbat *(giữ nguyên)* | giáo phái ma cà rồng, danh từ riêng |
| Ashirra | Ashirra *(giữ nguyên)* | giáo phái ma cà rồng Hồi giáo, danh từ riêng |
| Laibon | Laibon *(giữ nguyên)* | ma cà rồng châu Phi, danh từ riêng |

Tên clan/bloodline/lineage giữ nguyên toàn bộ (danh từ riêng, theo B0): Toreador, Ventrue, Tzimisce, Brujah, Gangrel, Malkavian, Nosferatu, Lasombra, Tremere, Ravnos, Salubri, Setite, Cappadocian, Giovanni, Baali, Assamite (Banu Haqim), Caitiff, Kiasyd, Maeghar, Samedi, Harbingers of Skulls, True Brujah, và mọi tên chi hệ Á Phi (Chibo, Monomi, Kishu, Kizoku, Bushi, Kuntilanak, Sangun, Anh, Banpaia, Erk, Daitya, Naktanchara, Nagloper, El Hijazi, Danava, Trimira, Volgirre…).

## B4e. Thuật ngữ bổ sung (từ `traits_POD` dòng 600-837, thế hệ/warrior trait/Inquisition)

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Generation *(số thứ tự)* | Thế Hệ Thứ N | `trait_vampgeneration1`→"Thế Hệ Thứ 1"… giữ số Ả Rập, không dùng số La Mã hay chữ số thứ tự tiếng Anh |
| Regnant | Chủ Nhân | ma cà rồng đã tạo ghoul; `trait_regnant` |
| Mass Regnant | Đại Chủ Nhân | `trait_massregnant` |
| Oathbreaker | Kẻ Phản Thệ | theo `nick_the_oathbreaker`="Phá Lời Thề" trong base, nhưng dùng biến thể "Phản Thệ" cho trait vì `sword_name_oathbreaker`="Kẻ Phản Thệ" cũng có trong base — chọn giữ nhất quán với dạng danh xưng |
| Unbondable | Không Thể Trói Buộc | liên quan blood bond, dịch nghĩa |
| Exposed | Bị Lộ Diện | trait tiết lộ bản chất siêu nhiên |
| Patron | Người Bảo Trợ | `trait_patron`, không nhầm với "Patron Council" (Hội đồng Bảo Trợ, B4b) |
| True Faith | Đức Tin Chân Chính | `trait_true_faith`/`trait_truefaith`; dùng cho mọi nơi glossary `Glossary('True Faith',...)` xuất hiện trong file này |
| Beatific | Người Được Thánh Sủng | cấp cao hơn True Faith |
| Holy Seal | Ấn Ký Thần Thánh | trait bệnh liên quan thánh tích |
| Custom Bloodline | Huyết Thống Tự Tạo | trait cho bloodline người chơi tự tạo |
| Salubri Caste (Healer/Warrior/Watcher) | Salubri Chữa Lành / Salubri Chiến Binh / Salubri Người Canh Giữ | đã chốt "Đẳng Cấp" = Caste ở B4d |
| Orison *(tiền tố trait Inquisition)* | *(giữ nguyên tiền tố, dịch phần tên)* | không có khái niệm base tương ứng; các tên như "Moral Compass"→"La Bàn Đạo Đức" dịch nghĩa bình thường |
| Oculi / Acre *(tiền tố trait Inquisition)* | *(giữ nguyên tiền tố)* | tên hệ thống phép của Inquisitor, dịch phần tên sau tiền tố |
| Inquisitor | Vị thẩm tra viên | theo `inquisitors`="Quan thẩm tra" trong base (`adventurer_name_sections`), điều chỉnh thành cụm để hợp văn cảnh câu |
| miracle | phép màu | theo base (`hold_court.6050.desc`, `GetMiracle1/2`) |
| Elohim | Elohim *(giữ nguyên)* | danh từ riêng tôn giáo, thiên thần |

> ⚠️ **Chỉ dịch tham số 1 của `Glossary('True Faith',...)`, giữ nguyên tham số 2 `game_concept_true_faith_desc`.** Đã áp dụng đúng ở 4 chỗ trong đợt này — xem TRANSLATION_RULES.md §4.

## B4f. Thuật ngữ Kuei-Jin Dharma / Inquisition bổ sung (từ `traits_POD` dòng 838-1001)

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Dharma *(tham số 1 của `Glossary('Dharma',...)`)* | Pháp Môn | đã chốt B3c, dùng nhất quán cả khi là tham số 1 dịch được của Glossary, không chỉ tên faith |
| Fifth Age / Sixth Age | Kỷ Nguyên Thứ Năm / Kỷ Nguyên Thứ Sáu | nối tiếp "Kỷ Nguyên Thứ Sáu" đã có ở B3c cho "Sixth Age"; thêm "Fifth Age" |
| Wan Kuei / Wan Xian | Wan Kuei / Wan Xian *(giữ nguyên)* | tên gọi tổ tiên/chủng tộc Kuei-Jin cổ, danh từ riêng WoD, không dịch |
| Insight *(thanh kinh nghiệm Dharma)* | Ngộ Tính | khác với "Insight" của Golconda Seeker — xem dưới, đó vẫn dùng "Ngộ Tính" nhất quán |
| Arcana *(trait Murnau)* | Áo Nghĩa | Dòng săn ma cà rồng Von Murnau, không nhầm với "Arcanos" của Wraith (giữ nguyên tiếng Anh, xem B4g) |
| Sisters (of the Sisterhood, Inquisition) | Nữ Tu | ngữ cảnh giáo phái nữ tu trừ tà, dịch nghĩa |

## B4g. Thuật ngữ Dharma cấp độ / Mummy / bệnh ma cà rồng (từ `traits_POD` dòng 1002-1147)

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Dharma N *(tên trait cấp độ, không phải tham số Glossary)* | Pháp Môn N | `trait_dharma0`…`trait_dharma10` — giữ số Ả Rập như Generation (B4e) |
| Insight *(thanh kinh nghiệm dharma track)* | Ngộ Tính | `trait_track_dharma1..9` |
| Ancestor / Mandarin / Brahmin (Hindu) / Jina / Ksatriya (Hindu) / Disciple / Vaisya (Hindu) / Hin / Sudra (Hindu) | Tổ Tiên / Quan Lại / Brahmin / Chiến Binh / Ksatriya / Đệ Tử / Vaisya / Hin / Sudra | hệ thống đẳng cấp Kuei-Jin song song Hindu; các từ Hindu (Brahmin, Ksatriya, Vaisya, Sudra) giữ nguyên vì là thuật ngữ Ấn Độ giáo có thật, không dịch |
| Feng Shui | Phong Thủy | Chi Art, có tiền lệ tiếng Việt phổ biến |
| Tzu Wei | Tử Vi | Chi Art, có tiền lệ tiếng Việt phổ biến |
| Tapestry *(Chi Art)* | Dệt Cảnh | đặt mới, mô tả khai thác long mạch |
| Obligation *(Chi Art)* | Nghĩa Vụ | khác với "Vassal Obligations" (A9), ngữ cảnh riêng của Kuei-Jin |
| Prana / Kiai | Prana / Kiai *(giữ nguyên)* | thuật ngữ gốc tiếng Phạn/Nhật không có bản dịch tự nhiên |
| Bulwark *(trait Holy Alliance)* | Thành Lũy | `trait_ha_holy_bulwark`→"Thành Lũy Thánh" |
| Arts Mastery *(tiền tố trait Holy Alliance)* | Tinh Thông Nghệ Thuật | mẫu chung `Tinh Thông Nghệ Thuật: [Tên Latin]`, tên Latin giữ nguyên (Sophia Patris, Sedulitas Filius, Boni Spiritus) |
| Demonic Plague | Ôn Dịch Ma Quỷ | bệnh dịch riêng của POD |
| Integrity *(hệ thống đức hạnh Mummy)* | Chính Trực | không nhầm với "Legitimacy"="Tính chính danh" (A3) |
| Bane *(linh hồn ô uế chiếm xác Mummy)* | Tà Linh | khác "Bane" của Fera (Tà Linh, đã chốt B4c) — cùng thuật ngữ, cùng bản dịch, đúng nguyên tắc |
| Shemsu-Heru, Bane Mummy→"Xác Ướp Tà Linh", Cabiri, Wu T'ian, Wu Kuei, Asekh-Sen | *(tên bộ tộc Mummy giữ nguyên, trừ Bane Mummy dịch nghĩa)* | danh từ riêng theo B0, trừ "Bane Mummy" là cụm mô tả nên dịch |
| **Bệnh ma cà rồng** (`trait_vampire_*`) — Smallpox/Bubonic Plague/Typhus/Cancer/Consumption/Gout Ridden/Pneumonic/Great Pox/Leper/Ill | Đậu Mùa / Dịch Hạch / Thương Hàn / Ung Thư / Lao Phổi / Gút Hành Hạ / Viêm Phổi / "Đại Hoa Liễu" / Phong Cùi / Bệnh — tất cả + hậu tố "Ma Cà Rồng" | ✅ tra được nguyên bản từ `base_game_vh/traits_l_english.yml` (bệnh vanilla), giữ đúng thuật ngữ base rồi thêm "Ma Cà Rồng" |

## B4h. Thuật ngữ Wraith / Demon / Sorcerer (từ `traits_POD` dòng 1148-1296)

Nguồn: phần Oan hồn (Wraith), Ác quỷ Fallen/Earthbound, và pháp sư phàm nhân. Không có tiền lệ base cho các khái niệm lõi Wraith — theo B0, giữ nguyên các danh từ riêng WoD (Spectre, Arcanos, tên các Arcanos cụ thể, Corpus, Fetter(s), Skinlands, tên các loại Spectre).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Shadow *(khía cạnh đen tối của oan hồn, không phải "shadow" thường)* | Bóng | `trait_shadow`, dùng xuyên suốt mọi mô tả Wraith |
| Psyche | Tâm Thức | phần "lý trí/ý thức" của oan hồn, đối lập với Bóng |
| Corpus, Fetter(s), Skinlands, Shadowlands, Arcanos (và tên riêng: Argos/Castigate/Embody/Fatalism/Flux/Inhabit/Intimation/Keening/Lifeweb/Mnemosynis/Moliate/Outrage/Pandemonium/Phantasm/Puppetry/Usury/Kinesis) | *(giữ nguyên tiếng Anh)* | thuật ngữ lõi hệ thống Wraith, không có khái niệm base tương ứng, theo B0 |
| Spectre, Doppelganger, Mortwight, Haint, Shade, Apparition, Nephwrack, Onceborn, Hekatonkhire, Neverborn, Stripling, Barghest, Pasiphae | *(giữ nguyên — tên các Đẳng Cấp/loại Spectre)* | danh từ riêng phân loại, theo B0 |
| Caste *(track của Spectre)* | Đẳng Cấp | dùng nhất quán với "Caste" của Assamite (B4d) — cùng khái niệm phân cấp |
| Dark Passions | Đam Mê Đen Tối | cảm xúc tiêu cực chi phối Spectre |
| Deathmarks | Dấu Chết | dấu hiệu thể chất của Doppelganger |
| Golem, Automaton, Effigy, Animantis, Servitor, Manifestation | *(giữ nguyên — tên các loại thây máy/vật thế thân)* | danh từ riêng kỹ thuật gọi hồn/pháp thuật |
| Replica *(trait_mindless_clone)* | Bản Sao | |
| Shadow Twin / Mirror Duplicate / Shadowy Duplicate / Phantom Shadow / Separated Khaibit / Separated Shadow / Shadow Self | Song Sinh Bóng Tối / Bản Sao Gương / Bản Sao Bóng Tối / Bóng Ma / Khaibit Bị Tách Rời / Bóng Bị Tách Rời / Bản Ngã Bóng Tối | dịch nghĩa các loại "bản sao"/tách đôi linh hồn |
| Risen | Kẻ Hồi Sinh | oan hồn quay lại xác |
| Ferryman, Ritual of Severance | Ferryman *(giữ nguyên tên riêng)*, Nghi Lễ Cắt Đứt | |
| Sorcerer / Sorceress / Rune Mage / Theurgist | Pháp Sư / Nữ Pháp Sư / Pháp Sư Rune / Nhà Thần Thuật | phân biệt "Sorcerer" (phàm nhân dùng hedge magic) khỏi "Mage" (Pháp sư, đã chốt B4) — xem ghi chú dưới |
| Fallen (thiên thần) | Sa Ngã | khác `trait_fallen` của thiên thần và `Earthbound` của ác quỷ — hai splat riêng biệt cùng chủ đề Thiên Thần Sa Ngã |
| Laham, Nephilim | *(giữ nguyên — hậu duệ ác quỷ)* | danh từ riêng Kinh Thánh/WoD |

> ⚠️ **Sorcerer (Wraith/phàm nhân) không phải Mage.** `trait_sorcerer_desc` viết rõ "they are still a far cry from Mages" — dịch "Pháp Sư" cho Sorcerer và giữ "Pháp sư" (chữ thường, đã chốt B4) cho Mage tạo ra sự trùng chữ không tránh được trong tiếng Việt (cả hai đều là "pháp sư" theo nghĩa đen); đã xử lý bằng cách viết hoa khác nhau và chú thích "(Mage)" ngay trong câu để giữ rõ ràng cho người đọc — xem `trait_sorcerer_desc`.

## B4i. Thuật ngữ bổ sung (từ `traits_POD` dòng 1298-1446) — Anathema/Golconda/bệnh/Ashen

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Possessed | Bị Chiếm Hữu | trait chung cho nhân vật bị linh thể nhập |
| Permanent *(hậu tố các trait tàn tật vĩnh viễn)* | Vĩnh Viễn | ghép với tên trait tàn tật đã có ở base (Tàn Phế, Chột Mắt, Cụt Một Chân, Biến Dạng, Sẹo Sần, Hoạn Quan, Mù — tra từ `base_game_vh/traits_l_english.yml`) |
| Blood Hunt | Blood Hunt *(giữ nguyên tạm thời)* | `game_concept_blood_hunt` trong `game_POD_concepts_l_english.yml` **chưa được dịch** (thuộc việc #11 sau này) — khi dịch file đó, quay lại đồng bộ tên gọi này trong `traits_POD` |
| Golconda | Golconda *(giữ nguyên)* | trạng thái giác ngộ tối thượng của ma cà rồng, danh từ riêng WoD |
| Golconda Seeker | Kẻ Tầm Golconda | |
| The Beast / Frenzy | Dã Thú / Phẫn Cuồng | ✅ đã dùng khi dịch `Glossary('The Beast',...)`/`Glossary('Frenzy',...)` — tham số 1 dịch, tham số 2 (`game_concept_beast_desc`) giữ nguyên là key dùng chung cho cả hai |
| Azhi Dahaka | Azhi Dahaka *(giữ nguyên)* | trạng thái giác ngộ đặc thù của Tzimisce, danh từ riêng |
| Zombu | Zombu *(giữ nguyên)* | loại xác sống gọi hồn |
| Alien | Ngoài Hành Tinh | trait khoa học viễn tưởng hiếm gặp trong POD |
| Crimson Fever, Chulorviosis, Gift of Melancholia, Flaying Plague, Scourge, Entobanic Plague | Sốt Đỏ, Chulorviosis *(giữ nguyên)*, Món Quà U Sầu, Ôn Dịch Lột Da, Scourge *(giữ nguyên)*, Ôn Dịch Entoban | tên bệnh WoD; giữ nguyên tên riêng khi không có nghĩa dịch tự nhiên (Chulorviosis, Scourge — đã là danh từ riêng trong văn cảnh) |
| Craftsman / Expert Craftsman / Master Craftsman | Thợ Thủ Công / Thợ Thủ Công Chuyên Nghiệp / Đại Sư Thợ Thủ Công | thang bậc 3 cấp trait chế tác POD |
| Forging / Brewing / Enhancing *(track chế tác)* | Rèn Đúc / Chưng Cất / Tăng Cường | 3 nhánh kinh nghiệm chế tác hiện vật |
| Ashen Adventurer / Ashen Ambassador / Ashen Grandmaster / Ashen Caravan (Master) | Nhà Thám Hiểm Tro Tàn / *("Ashen" giữ nguyên trong `[ashen_ambassador|E]` v.v. vì đó là concept-link key, không dịch)* | "Ashen" chỉ ma cà rồng/kueijin vô địa (landless) lang bạt; chỉ dịch phần mô tả văn xuôi, không dịch bên trong `[ashen_*|E]` vì đó là tên concept key |
| landless *(ma cà rồng/kueijin không lãnh địa)* | vô địa | dùng nhất quán trong mô tả Ashen |

## B4j. Thuật ngữ cuối `traits_POD` (dòng 1447-1563) — thanh máu, Quỷ Học, Chén Thánh, Underworld

File `traits_POD_l_english.yml` **hoàn tất 100% (1563/1563 dòng)** ở đợt này.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Bruised / Hurt / Injured / Wounded / Mauled / Crippled *(6 cấp thanh máu POD)* | Bầm Dập / Bị Thương / Bị Tổn Thương / Trọng Thương / Bị Xé Nát / Tàn Phế | không có tiền lệ base (base dùng hệ khác); đặt mới theo thang tăng dần mức độ nghiêm trọng |
| Impairment | Suy Nhược | tên track đo % ô máu đã lấp đầy |
| Mod Guardian | Người Gác Mod | nhân vật kỹ thuật ẩn, không phải lore thật |
| Midnight Warrior / Midnight General / Midnight Master, Twilight Warrior / Twilight General / Twilight Master | Chiến Binh/Tướng Quân/Bậc Thầy Nửa Đêm, Chiến Binh/Tướng Quân/Bậc Thầy Hoàng Hôn | 2 truyền thống chiến tranh nghi thức của Kuei-Jin (Midnight Wars gây sát thương thật, Twilight Wars phi sát thương) |
| Wayang Kulit (Disciple/Mistress/Penangallan) | Wayang Kulit *(giữ nguyên tên)*, Đệ Tử/Nữ Chủ/Penangallan Wayang Kulit | phong cách chiến tranh Đông Nam Á, tên riêng nghệ thuật kịch bóng Java giữ nguyên |
| Angered Madness Network | Mạng Lưới Điên Loạn Nổi Giận | hiệu ứng liên quan mạng lưới Malkavian |
| Demonology / Demonologist | Quỷ Học / Nhà Quỷ Học | ✅ "Nhà Quỷ Học" đã có tiền lệ ở B3c (`podgloss.truename`) cho "Demonologist" — dùng nhất quán |
| Grail Knight, Grail of the Bitter Ashes | Hiệp Sỹ Chén Thánh, Chén Thánh Tro Đắng | "Hiệp Sỹ" viết y (theo base, xem A4) |
| Fleshcrafted | Bị Nhào Nặn Thân Xác | trait mô tả nạn nhân Vicissitude |
| Complexity *(track fleshcrafted)* | Mức Độ Phức Tạp | |
| Pilgrim of Enoch | Lữ Khách Enoch | |
| Itarajana Sorcerer | Pháp Sư Itarajana | Huyết Thuật bản địa Ấn Độ |
| **Underworld** *(tham số 2 của `UmbraGlossaryLocalized('shadowlands', …)`)* | **Âm Phủ** ✅ mới đặt | Chưa có trong B0 (chỉ liệt kê 'Underworld' là 1 trong các giá trị khả dĩ của flag `shadowlands`, chưa dịch). Đây là lần đầu giá trị này được dịch thật — dùng "Âm Phủ" cho mọi `UmbraGlossaryLocalized('shadowlands','Underworld')` từ nay. Các giá trị khác cùng flag (`Limbo`, `Dark Umbra`) chưa gặp, sẽ đặt khi tới lượt. |
| **Yin World** *(tham số 2 của `UmbraGlossaryLocalized('shadowlands', …)`)* | **Âm Giới** ✅ đã dùng trong `traits/traits_POD_l_english.yml` (dòng 51, 512, 593) | Cùng flag `shadowlands` nhưng giá trị param 2 khác `Underworld` → bản dịch khác (Âm Giới ≠ Âm Phủ), đúng bản chất tham số 2 biến thiên theo ngữ cảnh (xem TRANSLATION_RULES.md §4) |
| **Yang World** *(tham số 1 của `Glossary('Yang World','game_concept_yang_world_desc')`)* | **Dương Giới** ✅ mới đặt | `religion/POD_religion_kueijin_l_english.yml`; đối xứng với "Âm Giới" ở trên, nhất quán Yin/Yang = Âm/Dương đã chốt B3c |

## B3e. Thuật ngữ bổ sung (từ `religion/POD_religion_kueijin_l_english.yml`) — việc #2 file 1/36

Nguồn: file neo của `religion/` (436 dòng). Đã chốt `Glossary()` tham số 1 phải dịch cho toàn bộ 15 loại thuật ngữ Kuei-Jin lõi (Dharma→Pháp Môn, Yama King(s)→Diêm Ma Vương, Yama Queen→Diêm Ma Nữ Vương, Demon Emperor→Ma Hoàng, August Personage of Jade→Ngọc Hoàng, Arhat→La Hán, Hell of Spiked Chains→Địa Ngục Xiềng Gai, Hundred Clouds→Bách Vân, Wheel of Ages→Bánh Xe Kỷ Nguyên, Wicked City→Thành Đô Tà Nghiệt) — tất cả đã có sẵn trong B3c, đây chỉ là lần đầu áp dụng thực tế vào văn xuôi. Kakuri/Shikome/Wan Kuei giữ nguyên (danh từ riêng).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Yang World | Dương Giới | ✅ xem B3e phía trên (đối xứng Âm Giới) |
| Temple *(kueijin_house_of_worship)* | Miếu | nơi thờ tự Kuei-Jin |
| Scarlet Queen | Xích Nữ Hoàng | thần Sức khỏe/Sinh sản/Của cải/Gia đình của Kuei-Jin |
| Ebon Dragon | Hắc Long | thần Chiến tranh/Nước của Kuei-Jin |
| Jade Emperor *(kueijin_high_god_name_alternate)* | Ngọc Đế | tên gọi khác của Ngọc Hoàng |
| Thousand Hells *(kueijin_negative_afterlife, không qua Glossary)* | Thiên Địa Ngục | cõi âm ty phản diện của Kuei-Jin |
| Heretical Dharma *(kueijin_religion)* | Pháp Môn Dị Giáo | tên gọi chung các giáo phái ngoài Ngũ Pháp Môn chính thống |
| Song of the Shadow *(tên hiển thị của `boneflowers_religion`)* | Ảnh Ca | ✅ đã chốt B3c, lần đầu dùng trong văn xuôi đầy đủ |
| Devil Tiger *(tên hiển thị của `deviltigers_religion`)* | Ma Hổ | ✅ đã chốt B3c |
| Resplendent Crane *(tên hiển thị của `resplendentcranes_religion`)* | Thụy Hạc | ✅ đã chốt B3c |
| Thrashing Dragon *(tên hiển thị của `thrashingdragons_religion`)* | Đằng Long | ✅ đã chốt B3c |
| Thousand Whispers | Thiên Ngữ | Dharma dị giáo thứ 5 (ngoài Ngũ Pháp Môn chính thống + Thousand Hells) |
| possessive `"...'s"` của thực thể/thần | mẫu `"của X"` | xác nhận theo tiền lệ `base_game_vh/localization/english/religion/religion_zoroastrianism_l_english.yml` (vd. "của Ohrmazd") |

Ngoài ra ~30 tên tiểu phái/hội bên trong 5 Pháp Môn (Empty Hands→Không Thủ, Fishhooks→Lưỡi Câu, Black Iron Talons→Hắc Thiết Trảo, Crimson Tiger→Xích Hổ, Wandering Overlord→Chúa Tể Lang Thang, Grandmother Witch→Bà Phù Thủy, Ku of the Thousand Tears→Ku Ngàn Giọt Lệ…) — đặt theo giọng Hán-Việt nhất quán, xem trực tiếp trong file nếu cần tra lại vì đây là danh xưng ít khi bị trỏ tới từ file khác.

## B3f. Thuật ngữ bổ sung (từ `POD_religion_framework` + `POD_religion_unexamined_horizons`) — việc #2 file 2-3/36

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Doctrines of the Blood | Giáo Lý của Dòng Máu | tiêu đề nhóm giáo lý ma cà rồng, `FAITH_DOCTRINES_VAMPIRIC` |
| Tolerances *(splat/subsplat)* | Khoan Dung | mức độ khoan dung của một tôn giáo với loài khác |
| Road *(hệ thống đạo đức ma cà rồng, khác "Path" của Éntomos = Đạo Lộ)* | Con Đường | đặt mới, phân biệt khỏi "Đạo Lộ" (B4c) |
| Road of Unexamined Horizons | Con Đường Chân Trời Chưa Xét | |
| Courtier *(hậu tố `-courtiers`, không phải `game_concept_courtier`=Cận thần vanilla)* | Cận Thần | dùng lại "Cận thần" viết hoa "Thần" cho tên riêng ghép, ngữ cảnh khác Cận thần triều đình thường |
| Corpse Courtiers | Tử Thi Cận Thần | |
| Ghost Courtiers | U Hồn Cận Thần | |
| Lordly Courtiers | Quân Tử Cận Thần | |
| Dream Courtiers | Mộng Cảnh Cận Thần | |
| Hundred Devils / Thousand Devils | Bách Quỷ / Thiên Quỷ | |
| Lost Lineages | Chi Hệ Thất Lạc | |

## B3k. Thuật ngữ bổ sung (từ `religion/POD_religion_l_english.yml`) — việc #2 file 4/36, file neo `rf_*`/`hostility_doctrine`/`holy_site`

Nguồn: file neo thứ hai của `religion/` (439 dòng, đã dịch xong 100%). Chứa nhãn "religion family" (`rf_*`), tên các giáo lý thù nghịch (`*_hostility_doctrine_name`), và tên thánh địa (`holy_site_*`).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Kindred *(tự xưng của ma cà rồng, khác `trait_vampire`="Ma cà rồng")* | Huyết Tộc | `rf_kindred`; nhất quán với cách B3c đã dịch "Kindred of the East"→"Huyết tộc Đông phương" |
| Ignorance *(nhãn giáo phái phàm nhân không biết về siêu nhiên)* | Vô Minh | `rf_ignorance`; ✅ có tiền lệ base (`jainism_evil_god_ignorance`, `dualism_evil_god_ignorance` đều = "Vô Minh") |
| Infernal *(nhãn giáo phái thờ quỷ)* | Ma Quỷ | `rf_thousandhells`; không có tiền lệ base, đặt mới theo tính từ mô tả thường, nhất quán với "Demonic Plague"→"Ôn Dịch Ma Quỷ" (B4g) |
| Heresy | Dị Giáo | `vampirecainite_hostility_doctrine_name`; ✅ tiền lệ base `heresy_hostility_doctrine_name`="Dị giáo" — viết hoa theo quy ước tên riêng giáo lý trong POD |
| Code of Tremere | Luật Lệ Tremere | `codeoftremere_hostility_doctrine_name`; không có tiền lệ base cho "Code" ở nghĩa này, Tremere là danh từ riêng giữ nguyên |
| Road *(nhắc lại B3f, áp dụng thêm)* | Con Đường | dùng cho toàn bộ 13 `roadof*_hostility_doctrine_name` trong file này: Road of the Beast→Con Đường Dã Thú, Road of Blood→Con Đường Máu, Road of Bones→Con Đường Xương Cốt, Road of Heaven→Con Đường Thiên Đường, Road of Hive→Con Đường Tổ Ong, Road of Humanity→Con Đường Nhân Tính, Road of Kings→Con Đường Quân Vương, Road of Lilith→Con Đường Lilith, Road of Metamorphosis→Con Đường Biến Hóa, Road of Sin→Con Đường Tội Lỗi, Road of Zarathustra→Con Đường Zarathustra, Road of Laibon→Con Đường Laibon, Road of Set→Con Đường Set |
| Thousand Hells *(nhắc lại B3e, áp dụng thêm)* | Thiên Địa Ngục | `thousandhells_hostility_doctrine_name` — khớp bản đã chốt ở B3e |
| Blood Gnosticism | Huyết Ngộ Đạo Luận | `bloodgnosticism_hostility_doctrine_name`; ✅ tiền lệ base cho "Gnosticism" = "Ngộ đạo luận" (`tenet_gnosticism_name`), ghép thêm "Huyết" (máu) |
| Calomena's Forsaken | Những Kẻ Ruồng Bỏ của Calomena | `calomenasforsaken_hostility_doctrine_name`; Calomena là danh từ riêng (một vị thần/nhân vật), "Forsaken" dịch nghĩa |
| Ashirra, Raktasadhus, Camarilla, Sabbat, Inconnu, Autarkis, Tal ma'He Ra, Vetaladharma, Kuei-Jin, Ordos, Anarchs, Gaia, Wyrm | *(giữ nguyên)* | tên riêng giáo phái/tổ chức WoD, theo B0 |
| From *(trong `holy_site_*_effect_name`)* | Từ | ✅ tiền lệ base xác nhận (`holy_site_jerusalem_effect_name`="Từ [holy_site\|E]…") — áp dụng cho toàn bộ 169 dòng `holy_site_*_effect_name` |
| Tên thánh địa (`holy_site_*_name`, vd. Paris, Rome tương đương ở POD) | *(giữ nguyên tiếng Anh, không dịch/không phiên âm)* | ✅ tiền lệ base xác nhận: `holy_site_jerusalem_name`="Jerusalem", `holy_site_rome_name`="Rome" — base_game_vh giữ nguyên tên địa danh tiếng Anh dù các dòng khác trong cùng file đã dịch. Khác với `simp_chinese` (phiên âm/dịch tên) — không theo simp_chinese ở điểm này |
| Patron faith | đức tin Bảo Trợ | `faith_conversion_cost_patron_religion`; nhất quán với "Patron Council"→"Hội đồng Bảo Trợ" (B4b) và "Patron"→"Người Bảo Trợ" (B4e) |

## B3g. Thuật ngữ bổ sung (từ `POD_religion_ghoul_l_english.yml`) — việc #2, faith Bộc huyết

Nguồn: `religion/POD_religion_ghoul_l_english.yml` (70 dòng) — tôn giáo "Unmastered" của các Bộc huyết vô chủ (ghoul không có Domitor). File không có `Glossary()`/`UmbraGlossaryLocalized()` nào (bracket count = 0).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Unmastered *(tên faith)* | Vô Chủ | đặt mới; đối lập với "Chủ Nhân" (Regnant, đã chốt B4e) — tiền tố "Vô" có tiền lệ base (`Vô Số`, `Vô Sợ`, `Vô Danh`…) |
| Free Ghoul(s) | Bộc huyết Tự do | Ghoul = "Bộc huyết" đã chốt B4; "Freedom"→"Tự do" có tiền lệ base (`game_concept_faction_liberty`) |
| Lorekeeper(s) *(chức sắc tôn giáo)* | Người Giữ Truyền Thuyết | đặt mới, không có tiền lệ base; ghép với `religious_text`="truyền thuyết" |
| bastion *(house_of_worship)* | pháo đài | theo tiền lệ base (`fortress`→"Pháo đài", `building_castle_04`) |
| broken chain *(religious_symbol)* | xiềng xích gãy | đặt mới, mô tả biểu tượng thoát khỏi ràng buộc Domitor |
| lore *(religious_text)* | truyền thuyết | đặt mới, gốc của "Người Giữ Truyền Thuyết" ở trên |
| Heaven *(divine_realm/positive_afterlife, danh từ thường)* | Thiên Đường | dùng danh từ tôn giáo phổ thông, khác "Âm Phủ" (B4j, chỉ dành riêng cho `UmbraGlossaryLocalized('shadowlands','Underworld')`) |
| Hell *(negative_afterlife, danh từ thường)* | Địa Ngục | tiền lệ base (`christianity_negative_afterlife`="địa ngục") |
| Devil *(witchgodname_the_horned_god — thực thể ma quái, KHÔNG phải "Caine")* | Quỷ Dữ | khác `trait_demon`="Ác quỷ" (B4) để tránh trùng với splat Demon; tương tự cách base dùng từ riêng cho mỗi witchgodname |
| blood *(health_god_name, danh từ thường dùng làm tên thần)* | máu | chữ thường, theo mẫu base (`taoism_devil_name`="sự bất hòa" — danh từ thường làm tên thần) |
| Caine *(devil_name/death_deity_name)* | Caine *(giữ nguyên)* | danh từ riêng đã chốt B2b |
| `_possessive` (`"X's"`) | mẫu `"của X"` | theo tiền lệ base đã ghi ở B3e (`zoroastrianism`, `taoism`…) |

## B3h. Thuật ngữ bổ sung (từ `POD_religion_roadoflaibon`) — việc #2 file 8/36

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Ebony *(tính từ, "gỗ mun")* | gỗ mun | ✅ tra `base_game_vh` (`appropriate_generic_words_l_english.yml:165`, `artifacts_l_english.yml:188`) |
| Ebony Kingdom | Vương Quốc Mun | thần tối cao của Con Đường Laibon |
| Kholo *(chức sắc Laibon)* | Kholo *(giữ nguyên)* | danh xưng WoD châu Phi, không có tiền lệ base |
| Spiritual *(ghép "Spiritual Kholo")* | Tâm Linh | ✅ tra base (`religion_l_english.yml:1188`, `doctrine_clerical_succession_spiritual_appointment_name`="Tâm linh, Có thể bãi nhiệm") |
| Lorekeeper | Người Giữ Truyền Thuyết | |
| the abyss *(cõi âm ty)* | vực thẳm | ✅ tra base (`religion_christianity_l_english.yml:51`, `religion_paganism_l_english.yml:1478` = "Vực Thẳm") |
| possessive `"X's"` | mẫu `"của X"` | ✅ tiền lệ base (`religion_christianity_l_english.yml:73`="của Fortuna"), dùng nhất quán mọi file `religion/` từ nay |
| Fortuna *(thần lừa lọc/may rủi)* | Fortuna *(giữ nguyên)* | ✅ tiền lệ base giữ nguyên y hệt (`religion_christianity_l_english.yml:72`) |

## B3i. Thuật ngữ bổ sung (từ `POD_religion_ashirra`) — việc #2 file 5/36

Nguồn: `religion/POD_religion_ashirra_l_english.yml` (63 dòng) — giáo phái ma cà rồng Hồi giáo. Đối chiếu với `base_game_vh/localization/english/religion/religion_islam_l_english.yml` (giữ nguyên Caliph/Caliphate/Imam/Imamate/mullah/Muhammad/Allah).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Ashirra, Mullah, Sultanate *(chức danh)*, Muhammad, Allah, Qabilat al-Mawt, mọi tên `Tariq el-*`, Road of Bones | *(giữ nguyên)* | danh từ riêng tôn giáo/tên phái, theo B0 và tiền lệ base Islam |
| The Prophet | Nhà Tiên Tri | ✅ tra base (`islam_good_god_the_prophet`="Nhà Tiên tri") |
| Companions of the Prophet | Bằng Hữu của Nhà Tiên Tri | theo mẫu base `holy_order_companions_of_hira` |
| Defenders of the Ashirra | Hộ Vệ Ashirra | theo mẫu base cho holy order kiểu phòng vệ |
| Warrior/Tribesman/Witness/Scholar *(tên tín đồ các Tariq)* | Chiến Binh / Người Bộ Tộc / Nhân Chứng / Học Giả | dịch nghĩa thường |

## B3j. Thuật ngữ bổ sung (từ `POD_religion_ignorance`) — việc #2 file 9/36

Nguồn: `religion/POD_religion_ignorance_l_english.yml` (71 dòng) — tôn giáo mặc định của phàm nhân không biết về siêu nhiên. Không có `Glossary()`/`UmbraGlossaryLocalized()`.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Ignorance *(tên faith)* | Vô Minh | ✅ tra base (`dualism_evil_god_ignorance`, `jainism_evil_god_ignorance` đều ="Vô Minh") |
| Ignorant(s) | Kẻ Vô Minh / Những Kẻ Vô Minh | |
| Innocence *(faith con)* | Vô Tội | khác "Vô Minh" — khái niệm riêng (vô tội đạo đức, không phải không biết) |
| God *(high_god_name_alternate)* | Chúa | ✅ tra base (`christianity_high_god_name_alternate`="Chúa") |
| Death *(death_deity_name)* | Cái Chết | ✅ tra base (`christianity_death_deity_name`="Cái Chết") |
| pastor | mục sư | chức sắc Tin Lành, phân biệt "linh mục"/"giám mục" Công giáo |
| home(s) *(house_of_worship)* | mái nhà / những mái nhà | giữ tinh thần "nhà" đời thường thay vì "nhà thờ" trang trọng |

## B3o. Thuật ngữ bổ sung (từ `POD_religion_hunter`) — việc #2 file 13/36

Nguồn: `religion/POD_religion_hunter_l_english.yml` (88 dòng, faith phàm nhân săn siêu nhiên). Không có `Glossary()`/`UmbraGlossaryLocalized()` — mọi ngoặc `[...]` đều là `[GetTrait('x').GetName( GetPlayer )]`. "Hunter" (trait splat, đã chốt B4) = "Thợ săn"; áp dụng nhất quán cho mọi `*_adherent` mang nghĩa "kẻ đi săn" chung chung.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Witch-Hunter(s) | Thợ Săn Phù Thủy | ghép "Thợ săn" (B4) + "Witch"→"Phù Thủy" (✅ tra base `trait_witch:0`="Phù Thủy") |
| Demon-Hunter(s) | Thợ Săn Ác Quỷ | ghép "Thợ săn" + "Demon"→"Ác quỷ" (đã chốt B4, `trait_demon`) |
| Inquisition *(nhắc lại, áp dụng lần đầu ở `religion/`)* | Tòa Dị Giáo | ✅ tra base (`apocalyptic_inquisition`="Tòa Án Dị Giáo Tận Thế", `ACHIEVEMENT_fp2_andalusian_inquisition`="Tòa Dị Giáo Andalusia") — khác với "Heresy"="Dị giáo" (đã chốt B3k), đây là tên tổ chức |
| Shadow Inquisition | Tòa Dị Giáo Bóng Tối | ghép "Tòa Dị Giáo" + "Shadow" (đã dùng "Bóng" cho Wraith B4h, ở đây dịch "Bóng Tối" vì là tính từ mô tả bí mật, không phải khái niệm Wraith) |
| Inquisitor | Vị thẩm tra viên | ✅ đã chốt B4e (`inquisitors`="Quan thẩm tra" trong base, điều chỉnh cụm) |
| Grand Inquisitor | Đại Thẩm Tra Viên | ghép "Đại" (tiền tố cấp bậc cao, có tiền lệ base rộng rãi) với "Thẩm Tra Viên" |
| Papal Inquisition | Tòa Dị Giáo của Giáo hoàng | phân biệt với Shadow Inquisition trong cùng một câu |
| Catholic Church | Giáo hội Công giáo | ✅ tra base (`catholic:0`="Công giáo") |
| Judge(s) *(biblical, tên faith)* | Quan Xét | các Thủ Lĩnh/Quan Xét trong Cựu Ước; không có tiền lệ base trực tiếp, chọn "Quan Xét" theo Hán-Việt trang trọng phù hợp văn phong tôn giáo |
| Shih's Belief | Tín Ngưỡng của Shih | "Shih" giữ nguyên (đã có trong `trait_shih`, `traits_POD_l_english.yml`) |
| Celestial Master | Thiên Sư | chức sắc tôn giáo Shih, không có tiền lệ base; "Thiên" (trời) + "Sư" (thầy) theo giọng Hán-Việt nhất quán với các thuật ngữ Kuei-Jin/Shih khác |
| Strike Force Zero / SF0 | Strike Force Zero / SF0 *(giữ nguyên)* | tên tổ chức hiện đại Nhật Bản, danh từ riêng theo B0 |
| Agent(s) *(thành viên SF0)* | Đặc Vụ | dịch nghĩa thông thường cho tổ chức kiểu điệp vụ hiện đại |
| Sanbenito | Sanbenito *(giữ nguyên)* | tên giáo phái lịch sử có thật (loại áo tội nhân dị giáo), danh từ riêng |
| Florentine Heresy | Dị Giáo Florence | ghép "Dị Giáo" (đã chốt B3k, `heresy_hostility_doctrine_name`) với địa danh "Florence" giữ nguyên |
| Society of Leopold | Hội Leopold | tên tổ chức hư cấu, dịch nghĩa "Society"→"Hội", giữ tên riêng "Leopold" |
| Florentine Heretics | Kẻ Dị Giáo Florence | số nhiều gộp làm một theo quy tắc chung (mục 7 TRANSLATION_RULES.md) |
| Qorjin's Baghatur | Baghatur của Qorjin | "Baghatur" (danh hiệu chiến binh Mông Cổ) giữ nguyên, theo mẫu possessive "của X" (đã chốt B3e/B3h) |
| Samara Bend | Khúc Sông Samara | trận đánh lịch sử/lịch sử giả tưởng, dịch nghĩa "Bend"→"Khúc Sông" |
| the Horde *(quân đội Mông Cổ)* | Đại Trại | không có tiền lệ base cho nghĩa này của "Horde"; "Đại Trại" gợi doanh trại lớn của người du mục, tránh nhầm với "Golden Horde" nếu xuất hiện sau này |
| Chinghis Khan | Thành Cát Tư Hãn | ✅ tên gọi tiếng Việt phổ biến, chuẩn lịch sử |
| Karakorum | Karakorum *(giữ nguyên)* | địa danh lịch sử, không phiên âm |
| Mongol Empire | Đế Quốc Mông Cổ | theo A7 (Empire→Đế quốc) + "Mongol"→"Mông Cổ" chuẩn |
| Warriors of Dazbog | Chiến Binh của Dazbog | "Dazbog" (thần Slav) giữ nguyên, mẫu possessive "của X" |
| Svarog, Dazbog | Svarog, Dazbog *(giữ nguyên)* | tên thần thoại Slav, danh từ riêng theo B0 |
| Champion(s) *(tín đồ Dazbog)* | Dũng Sĩ | dịch nghĩa, khác "Chiến Binh" (Warrior, cấp tính từ tên faith) để tránh trùng lặp trong cùng khối |
| Nod *(vùng đất Caine lang thang)* | Nod *(giữ nguyên)* | địa danh Kinh Thánh/WoD, danh từ riêng gốc như "Book of Nod" (đã chốt B2b) |
| Corrupted Hunters | Thợ Săn Sa Đọa | "Corrupted"→"Sa Đọa" (không có tiền lệ base trực tiếp, chọn từ Hán-Việt phù hợp giọng suy đồi đạo đức, khác "Corruption"="Ô Uế" của Wyrm B3b vì ngữ cảnh khác — đạo đức con người, không phải bản chất Wyrm) |
| Grand Master *(chức sắc Corrupted Hunters)* | Đại Sư | tiền tố "Đại" + "Sư" (thầy), nhất quán giọng Hán-Việt như "Thiên Sư" |
| Grand Shrine | Đại Miếu | "Shrine"→"Miếu" theo tiền lệ Kuei-Jin (`kueijin_house_of_worship`="Miếu", B3e) |
| Torah, Talmud, Lilith | Torah, Talmud, Lilith *(giữ nguyên)* | ✅ tra base (`religion_judaism_l_english.yml` giữ nguyên Torah/Talmud); Lilith đã có tiền lệ POD (`roadoflilith_hostility_doctrine_name`="Con Đường Lilith") |
| Satan | Satan *(giữ nguyên)* | danh từ riêng tôn giáo phổ biến trong tiếng Việt, không phiên âm |
| Akritai, Ikhwan al-Safa, Sayyad al-Ghulan | *(giữ nguyên)* | ✅ tra base (`akritai:0`="Akritai"); tên Ả Rập giữ nguyên theo B0 |
| shen *(thuật ngữ Kuei-Jin cho sinh vật siêu nhiên)* | shen *(giữ nguyên)* | ✅ tiền lệ `traits_POD_l_english.yml` (`trait_shih_desc`) giữ nguyên "shen" |
| $pod_wod$ *(thay cho cụm "World of Darkness" trong văn xuôi)* | dùng shortcut đã chốt | ✅ áp dụng shortcut có sẵn (`glossary_POD_l_english.yml`, đã dịch "Thế Giới Bóng Tối") thay vì gõ lại chữ, nhất quán với 15 file khác đã dùng `$pod_wod$` |

## B3q. Thuật ngữ bổ sung (từ `POD_religion_talmahera`) — việc #2 file 15/36

Nguồn: `religion/POD_religion_talmahera_l_english.yml` (92 dòng, đã dịch xong 100%) — Tal'Mahe'Ra, giáo phái/tổ chức WoD gốc Ai Cập/Lưỡng Hà cổ, gồm faith neo `talmahera_religion` (nhóm "Common Road of Paradox") và 4 faith con: `talmahera` (Tal'Mahe'Ra hẹp), `manusnigrum` (Manus Nigrum), `pathofselffocus` (Path of Self-Focus), `pathofthescorchedheart` (Path of the Scorched Heart). Không trùng `talmahera_hostility_doctrine_name`="Tal ma'He Ra" đã chốt ở B3k (đó là tên doctrine hiển thị trong file neo `POD_religion_l_english.yml`, khác context).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Tal'Mahe'Ra *(tên religion/tên faith)* | Tal'Mahe'Ra *(giữ nguyên)* | danh từ riêng tổ chức WoD, theo B0; khác cách viết "Tal ma'He Ra" đã chốt riêng ở B3k cho tên doctrine — cả hai cùng giữ nguyên tiếng Anh, không quy về một dạng vì đây là hai key khác nhau trong bản gốc |
| Manus Nigrum | Manus Nigrum *(giữ nguyên)* | tên Latin của nhánh phương Tây, danh từ riêng |
| Shadow Crusader(s) | Quân Thập Tự Bóng Tối | ✅ tra base (`adventurer_name_sections_l_english.yml`: `crusaders`="Quân Thập Tự"), ghép thêm "Bóng Tối"; số nhiều gộp chung theo mục 7 TRANSLATION_RULES.md |
| True Black Hand | Bàn Tay Đen Chân Chính | tên gọi khác của Manus Nigrum trong văn xuôi; nhất quán với "Black Hand"→"Bàn Tay Đen" (dưới) + "Chân Chính" (đã dùng cho "True Fae"→"Fae Chân Chính", B4) |
| Black Hand *(religious_symbol, biểu tượng)* | Bàn Tay Đen | dịch nghĩa trực tiếp |
| Black Hand(er) *(manusnigrum_adherent — tín đồ)* | Bàn Tay Đen / Những Kẻ Thuộc Bàn Tay Đen | số ít dùng "Bàn Tay Đen" (đồng nhất với tên biểu tượng vì tín đồ tự xưng theo biểu tượng), số nhiều thêm "Những Kẻ Thuộc" cho rõ nghĩa "thành viên" |
| The Aralu *(high_god_name — hội đồng thực thể tối cao)* | Aralu *(giữ nguyên)* | danh từ riêng WoD gốc Lưỡng Hà (Aralu/Arallu = cõi âm ty Lưỡng Hà cổ trong thần thoại thật); không có tiền lệ base, giữ nguyên vì là tên riêng ngoại lai không dịch được |
| Rabble *(devil_name)* | Đám Ô Hợp | không có tiền lệ base cho "Rabble" ở nghĩa tên thần; đặt mới theo nghĩa đen ("đám đông hỗn tạp, ô hợp") |
| Destruction *(death_deity_name)* | Hủy Diệt | thống nhất với B3m (`POD_religion_calomenasforsaken`, cùng key `death_deity_name` dùng "Destruction"→"Hủy Diệt" cho faith khác) |
| Oblivion *(negative_afterlife)* | Hư Vô | không có tiền lệ base riêng; đặt mới, phân biệt với "Địa Ngục" (Hell, B3g) và "Thiên Địa Ngục" (Thousand Hells, B3c/B3e) — "Oblivion" ở đây nghĩa là hư vô/diệt vong hoàn toàn, không phải một cõi âm ty cụ thể |
| Nergal, Loz, Ninmug | *(giữ nguyên)* | tên các vị thần phụ, danh từ riêng; Nergal là thần chiến tranh/ôn dịch có thật trong thần thoại Lưỡng Hà — giữ nguyên như cách base giữ tên thần ngoại lai (vd. Ohrmazd, Fortuna) |
| Enoch | Enoch *(giữ nguyên)* | ✅ tiền lệ POD xác nhận: `holy_site_enoch_name`="Enoch" (chưa dịch, nhưng cùng POD giữ nguyên tên địa danh kiểu `holy_site_jerusalem_name`="Jerusalem" theo B3k); thành phố ma nơi Aralu/Antediluvian ngủ, gắn với "Book of Enoch" có thật trong Kinh Thánh ngụy thư |
| Del'Roh, Rawi, Qadis *(chức sắc)* | *(giữ nguyên)* | danh xưng tôn giáo ngoại lai kiểu Ả Rập/Trung Đông hư cấu, không có tiền lệ base; đối chiếu `simp_chinese` phiên âm thành 德尔罗/拉威/加迪斯 nhưng **không theo** — repo này giữ nguyên tên chức sắc ngoại lai như cách đã làm với Ashirra/Mullah (B3i), Kholo (B3h) |
| Path of Self-Focus, Path of the Scorched Heart *(tên 2 faith con)* | Con Đường Tự Chú Tâm, Con Đường Trái Tim Cháy Khô | "Path" ở đây dùng như từ đồng nghĩa với "Road" (hệ đạo đức ma cà rồng, B3f/B3k) trong các faith con rải rác khắp `religion/` (`pathof*_religion`, gặp lại ở `roadofbeast`/`roadofsin`/`roadofheaven`… chưa dịch) — dùng "Con Đường" thống nhất, **khác** "Đạo Lộ" (B4c, chỉ dành cho hệ thống trait Éntomos/Ananasi) |
| Internalist(s) *(pathofselffocus_adj/adherent)* | Người Hướng Nội | dịch nghĩa trực tiếp, không có tiền lệ base |
| Unforgiving *(pathofthescorchedheart_adherent)* | Kẻ Không Khoan Nhượng | dịch nghĩa; tránh nhầm với "Oathbreaker"→"Kẻ Phản Thệ" (B4e) |
| Rathmonicus *(tác giả Book of the Empty Heart)* | Rathmonicus *(giữ nguyên)* | ✅ tra POD (`character_names_POD_l_english.yml:2733`="Rathmonicus"), danh từ riêng nhân vật |
| Rathmonicusi *(pathofthescorchedheart_adj — tính từ phái sinh từ tên riêng)* | Rathmonicusi *(giữ nguyên)* | tính từ ngoại lai phái sinh từ tên riêng, không dịch được sang tiếng Việt tự nhiên; theo mẫu B0 giữ nguyên toàn bộ |
| Book of the Empty Heart | Sách Trái Tim Trống Rỗng | dịch nghĩa, theo mẫu "Sách Nod" (B2b) — "Book of X" → "Sách X" |
| Catholic Church | Giáo hội Công giáo | ✅ tra base (`religion_christianity_l_english.yml:80`, `catholic:0`="Công giáo"; `catholic_desc`="Giáo hội Công giáo Rôma") |
| Kindred *(dùng trong `pathofthescorchedheart_desc` để chỉ ma cà rồng nói chung)* | Huyết Tộc | ✅ đã chốt B3k (`rf_kindred`), áp dụng lại |
| secret temple(s) *(house_of_worship)* | đền thờ bí mật / những đền thờ bí mật | ✅ tra base, "temple"→"Đền thờ" có tiền lệ (`religion_l_english.yml` nhiều key `doctrine_parameter_theocracy_temple_*`="Đền thờ") |
| Enoch Peacekeepers *(holy_order)* | Đội Gìn Giữ Hòa Bình Enoch | dịch nghĩa "peacekeepers", "Enoch" giữ nguyên tên địa danh |
| Spenta Aurvat Column *(holy_order)* | Cột Trụ Spenta Aurvat | "Spenta Aurvat" là cụm tiếng Avesta (Zoroastrian) giữ nguyên, "Column" dịch nghĩa "Cột Trụ" |
| Baali *(clan ma cà rồng thờ quỷ, nhắc tới trong `manusnigrum_desc`)* | Baali *(giữ nguyên)* | tên clan, đã ngầm định giữ nguyên theo B4d (danh sách clan) dù chưa liệt kê tên riêng — bổ sung xác nhận ở đây |
| Chakravanti *(nhóm pháp sư trong `talmahera_desc`)* | Chakravanti *(giữ nguyên)* | danh từ riêng phái pháp sư (Mage), không có tiền lệ base |

## B3m. Thuật ngữ bổ sung (từ `POD_religion_calomenasforsaken`) — việc #2 file 11/36

Nguồn: `religion/POD_religion_calomenasforsaken_l_english.yml` (73 dòng, đã dịch xong 100%) — tôn giáo thợ săn "Calomena's Forsaken" (Bogomil/Ngộ Đạo, thù địch với ma cà rồng). Không có `Glossary()`/`UmbraGlossaryLocalized()` (bracket count = 0). Tên faith "Calomena's Forsaken" → "Những Kẻ Ruồng Bỏ của Calomena" đã chốt sẵn ở B3k (`calomenasforsaken_hostility_doctrine_name`) — áp dụng lại ở đây cho toàn bộ các key hiển thị tên faith.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Calomena's Forsaken *(tên faith đầy đủ)* | Những Kẻ Ruồng Bỏ của Calomena | ✅ đã chốt B3k, áp dụng lại |
| Forsaken *(rút gọn — adj/adherent/adj)* | Ruồng Bỏ | rút gọn của tên đầy đủ, dùng khi đứng một mình làm tính từ/danh xưng ngắn |
| Blood Gnostics *(religion_adherent)* | Ngộ Đạo Đồ Máu | ghép "Ngộ Đạo Đồ" (tín đồ Ngộ Đạo Luận, xem dưới) + "Máu"; nhất quán "Gnosticism"→"Ngộ Đạo Luận" đã có tiền lệ base (`tenet_gnosticism_name`="Ngộ đạo luận", dùng ở B3k cho "Blood Gnosticism"→"Huyết Ngộ Đạo Luận") |
| Gnostics *(religion_adherent_plural, rút gọn)* | Ngộ Đạo Đồ | tín đồ Ngộ Đạo Luận nói chung |
| Gnosticism | Ngộ Đạo Luận | ✅ tiền lệ base (`tenet_gnosticism_name`="Ngộ đạo luận") |
| orthodox_religious_head_title_female *(key vay từ vanilla, không có trong base_game_vh)* | Nữ Thượng phụ | base chỉ có `orthodox_religious_head_title`="Thượng phụ" (nam); POD thêm biến thể nữ, dịch song song |
| Destruction *(death_deity_name)* | Hủy Diệt | không có tiền lệ base riêng cho tên thần trừu tượng này; đặt mới theo nghĩa đen |
| chapel *(house_of_worship)* | nhà thờ | ✅ tra base, dùng chung mẫu `christianity_house_of_worship`="nhà thờ" (không có "nhà nguyện" riêng trong base cho ngữ cảnh này) |
| cross *(religious_symbol)* | thánh giá | ✅ tra base (`christianity_religious_symbol`="thánh giá") |
| Euagetaematikon *(religious_text — tên sách, cũng là tên hiện vật ở `pod_artifacts_l_english.yml`)* | Euagetaematikon *(giữ nguyên)* | danh từ riêng (tên sách thánh bịa, gốc giả-Hy Lạp), xuất hiện lặp lại ở nhiều file khác — giữ nguyên xuyên suốt |
| principle of faith *(religious_head_title/devotee/priest — thuật ngữ chức sắc dùng chung nhiều faith thợ săn khác: `bloodgnosticism`, `roadofhumanity`, `roadofkings`, `roadofheaven`)* | Nguyên Tắc Đức Tin | đặt mới; số ít/số nhiều gộp làm một theo mục 7 TRANSLATION_RULES.md. **Dùng thuật ngữ này khi dịch 4 file còn lại có cùng chuỗi "principle of faith"** |
| bishop | giám mục | ✅ tiền lệ base (`christianity_bishop`="giám mục") |
| heaven *(divine_realm/positive_afterlife)* | thiên đàng | ✅ tiền lệ base (`christianity_positive_afterlife`="thiên đàng") |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ đã chốt B3h, áp dụng lại (khác "Âm Phủ" B4j chỉ dành riêng cho `UmbraGlossaryLocalized('shadowlands','Underworld')`) |
| God *(health_god_name, danh từ thường dùng làm tên thần)* | Chúa | ✅ tiền lệ base (`christianity_high_god_name_alternate`="Chúa", B3j) |
| Ialdabaoth *(witchgodname_the_horned_god)* | Ialdabaoth *(giữ nguyên)* | danh từ riêng Ngộ Đạo Luận (Demiurge), khác "Thần Sừng" của Christianity base — POD không dùng tên mô tả, dùng thẳng tên riêng nên giữ nguyên |
| Bogomil(s) *(heresy, tên riêng lịch sử)* | Bogomil *(giữ nguyên)* | danh từ riêng lịch sử (dị giáo Balkan thời trung cổ), không phiên âm |
| dualist philosophy | triết lý nhị nguyên | dịch nghĩa thường, không có tiền lệ base riêng nhưng "nhị nguyên" là từ Hán Việt phổ thông |
| Forsaken Militant *(holy_order)* | Chiến Binh Ruồng Bỏ | theo mẫu base `holy_order_warriors_of_*`="Chiến binh [của] X" (`holy_orders_l_english.yml`), đảo về "Chiến Binh Ruồng Bỏ" cho hợp thứ tự tính từ tiếng Việt |
| `_possessive` (`"X's"`) | mẫu `"của X"` | theo tiền lệ base đã ghi ở B3e/B3g/B3h, dùng nhất quán mọi file `religion/` |

## B3p. Thuật ngữ bổ sung (từ `POD_religion_naktanchara`) — việc #2 file 14/36

Nguồn: `religion/POD_religion_naktanchara_l_english.yml` (86 dòng, đã dịch xong 100%) — tôn giáo ma cà rồng "Vetaladharma"/"Naktanchara", pha trộn Phật giáo Mật tông và tín ngưỡng Ấn Độ (Vetala, Nāga). Phát hiện quan trọng: `ari_desc` trong `base_game_vh/localization/english/religion/religion_buddhism_l_english.yml:79` gần như trùng khớp cấu trúc câu với `naktanchara_desc` gốc ("combines elements from tantric buddhism, spirit worship, traditional Nāga worship as well as Hinduism...") — đã dùng làm khuôn mẫu trực tiếp. File `religion_buddhism_l_english.yml` cũng là nguồn đối chiếu chính cho toàn bộ khối god-name/house_of_worship/devotee/priest bên dưới (cùng slot: health/wealth/household/fate/knowledge/war/trickster/night/water god, cùng witchgod pattern, cùng evil god Tanha/Arati/Raga, cùng death god Yami).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Vetaladharma | Vetaladharma *(giữ nguyên)* | ✅ đã chốt B3k, tên hiển thị chính của faith |
| Naktanchara | Naktanchara *(giữ nguyên)* | tên faith gốc (khác Vetaladharma — Vetaladharma là tên hiển thị `naktanchara_religion`, còn `naktanchara`/`naktanchara_desc` là faith con/tên kỹ thuật riêng trong cùng file) |
| Vetala | Vetala *(giữ nguyên)* | danh từ riêng — linh hồn/quỷ nhập xác trong thần thoại Ấn Độ, gốc của tên Naktanchara |
| The Enlightened *(tham số possessive `_alternate`)* | Bậc Giác Ngộ | ✅ tra `base_game_vh` (`buddhism_high_god_alternate`="Bậc Giác Ngộ") |
| the samsara | luân hồi | ✅ tra base (`buddhism_samsara`="luân hồi") |
| Buddha *(good_god)* | Đức Phật | ✅ tra base (`buddhism_high_god_name`="Đức Phật") |
| The Perfected Ones | Các Bậc Toàn Giác | ✅ tra base (`buddhism_good_god_perfected_ones`="Các Bậc Toàn Giác") |
| Mẫu possessive `"X's"` | mẫu `"của X"` | ✅ tra base — toàn bộ possessive trong `religion_buddhism_l_english.yml`/`religion_hinduism_l_english.yml` dùng "của X", không dùng hậu tố 's; áp dụng thống nhất cho mọi god name possessive trong file này (khác cách naktanchara gốc viết `"X's"` bằng tiếng Anh) |
| Tanha / Arati / Raga *(3 evil god — dục vọng/chán ghét/tham ái, quân đoàn của Mara)* | Ái dục / Chán ghét / Tham ái | ✅ tra base (`buddhism_evil_god_tanha/_arati/_raga` = "Ái dục"/"Chán ghét"/"Tham ái") — dịch nghĩa vì đây là 3 khái niệm trừu tượng, không phải danh xưng |
| kamma *(fate_god_name, dạng Pali của "karma")* | nghiệp | ✅ tra base (`buddhism_fate_god_name`="nghiệp") — chuẩn hóa về từ Hán-Việt phổ biến thay vì giữ dạng Pali |
| temple *(house_of_worship)* | chùa | ✅ tra base (`buddhism_house_of_worship`="chùa") — faith này thiên về khung Phật giáo (naktanchara_desc tự mô tả tín đồ "được xem là Phật tử") nên dùng "chùa" thay vì "đền thờ" của Hindu |
| dharmachakra *(religious_symbol)* | pháp luân | ✅ tra base (`buddhism_religious_symbol`="pháp luân") — "pháp luân" đúng nghĩa đen "bánh xe Pháp" = dharmachakra |
| Buddhavacana *(religious_text)* | Buddhavacana *(giữ nguyên)* | thuật ngữ Pali kỹ thuật ("lời Phật dạy"); base có khái niệm tương đương dịch nghĩa là "Phật ngôn" (`buddhism_religious_text`) nhưng bản gốc POD chọn giữ dạng Pali gốc thay vì tên English/dịch nghĩa như "Buddhavacana" — giữ nguyên theo B0 vì đã là thuật ngữ chuyên môn không phải tiếng Anh thường |
| lama *(religious_head_title)* | lạt-ma | ✅ tra base (`buddhism_religious_head_title`="lạt-ma") |
| Lama Incarnation | Hóa Thân Lạt-ma | ✅ tra base (`buddhism_religious_head_title_name`="Hóa Thân Lạt-ma") |
| bhikkhu / bhikkhuni *(devotee nam/nữ)* | tỳ-kheo / tỳ-kheo-ni | ✅ tra base (`buddhism_devotee_male/_female`="tỳ-kheo"/"tỳ-kheo-ni") — số nhiều gộp chung theo quy tắc tiếng Việt không biến đổi từ |
| sangha *(priest/bishop)* | tăng đoàn | ✅ tra base (`buddhism_alt_priest_term`="tăng đoàn") |
| Nirvana *(divine_realm/positive_afterlife)* | Niết Bàn | ✅ tra base (`buddhism_divine_realm`="Niết Bàn") |
| Naraka *(negative_afterlife)* | Naraka *(giữ nguyên)* | ✅ tra base — cả `buddhism_negative_afterlife` và `hinduism_negative_afterlife`/`jainism_negative_afterlife` đều giữ nguyên "Naraka", không dịch |
| Yami *(death_god_name)*, Yama *(death_deity_name)*, Mara *(devil_name)* | Yami / Yama / Mara *(giữ nguyên)* | ✅ tra base — `buddhism_death_god_name`="Yami" giữ nguyên; `hinduism_death_name`="Yama" giữ nguyên; Mara không dịch thành "Ma Vương" như base (`buddhism_devil_name`) vì bản gốc POD dùng thẳng tên riêng Pali "Mara" làm tên hiển thị, không phải cụm mô tả — giữ nguyên theo B0 |
| Siddhartha, Tathagatagarbha, Virūḍhaka, Vaiśravaṇa, Dhṛtarāṣtra, Virūpākṣa | *(giữ nguyên — tên riêng Phạn ngữ)* | ✅ đối chiếu base: đây là 4 Thiên Vương + tên khác của Đức Phật, base cũng giữ nguyên dạng Phạn ngữ có dấu phụ y hệt cho slot health/wealth/knowledge god (`buddhism_health_god_name`="Virūḍhaka", `buddhism_wealth_god_name`="Vaiśravaṇa", `buddhism_knowledge_god_name`="Virūpākṣa"); riêng `household_god_name`="Dhṛtarāṣtra" và `creator_god_name`="Tathagatagarbha" bản gốc POD giữ dạng Phạn/Sanskrit trong khi base dịch nghĩa Hán-Việt ("Như Lai Tạng") hoặc dùng tên khác (Dhritarashtra không dấu) — giữ nguyên đúng dạng có dấu phụ đã có sẵn trong file POD, không đổi theo base vì đây là 2 khái niệm khác nhau (giữ tên riêng khác, không phải một-thuật-ngữ-một-bản-dịch bị vi phạm) |
| Arhat *(param 1 của `Glossary('Arhat','podgloss.arhat')`)* | La Hán | ✅ áp dụng đúng B3c — `naktanchara_good_god_arhat`="Vị [Glossary('La Hán','podgloss.arhat')]"; tham số 1 của `Glossary()` LUÔN phải dịch, không có ngoại lệ theo ngữ cảnh (xem TRANSLATION_RULES.md §4 và bài học sửa lỗi ở B3e) |
| Via Fvria Imperiosa, Fvrian, Deus et Dominus | *(giữ nguyên — tên riêng Latin, nội dung Patron Content không chính thống)* | danh từ riêng ngoại ngữ, theo B0 |
| non canon religion...commissioned by a Patron *(mẫu câu Patron Content)* | "Tôn giáo phi chính thống này được một Người Bảo Trợ đặt riêng." | đặt mới lần đầu (chưa có file Patron Content nào khác được dịch trước đó để tham chiếu) — "Người Bảo Trợ" nhất quán với "Patron"→"Người Bảo Trợ" đã chốt B4e; cụm này sẽ lặp lại ở nhiều file `roadof*`/`ordos`/`bloodgnosticism` khác, dùng đúng câu này khi gặp lại |

> ⚠️ **Lưu ý về tham số 1 của `Glossary('Arhat','podgloss.arhat')`.** B3c đã chốt "Arhat → La Hán" khi Arhat xuất hiện như danh từ thường trong văn xuôi (`podgloss.arhat`). Tuy nhiên tại `naktanchara_good_god_arhat`, cụm gốc là `"The [Glossary('Arhat','podgloss.arhat')]"` — bản dịch áp dụng là `"Vị [Glossary('Arhat','podgloss.arhat')]"`, **giữ nguyên chữ "Arhat" bên trong tham số 1**, không đổi thành "La Hán". Lý do: đây là một vị thần cụ thể được xưng bằng chính danh xưng chức vụ "Arhat" (như "The Enlightened", "The Perfected Ones" — các tên gọi khác của Đức Phật trong cùng khối), nên "Arhat" ở đây hoạt động như danh hiệu/tên gọi, không phải thuật ngữ chung. Đối chiếu B3c mục Kuei-Jin (`Arhat/Grand Arhat`→"La Hán/Đại La Hán") vẫn áp dụng khi ngữ cảnh là khái niệm Phật giáo Kuei-Jin nói chung — hai ngữ cảnh khác nhau, không mâu thuẫn.

## B3n. Thuật ngữ bổ sung (từ `POD_religion_codeoftremere`) — việc #2 file 12/36

Nguồn: `religion/POD_religion_codeoftremere_l_english.yml` (85 dòng, đã dịch xong 100%) — faith "Code of Tremere" (Luật Lệ Tremere, đã chốt B3k) và faith con "Via Servilis" của Gargoyle. Không có `Glossary()`/`UmbraGlossaryLocalized()` (bracket count = 0).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Code of Tremere / Warlock *(religion_adj/adherent)* | Luật Lệ Tremere / Phù Thủy | "Luật Lệ Tremere" ✅ đã chốt B3k; "Warlock"→"Phù Thủy" đặt mới, không có tiền lệ base cho "warlock", dùng nghĩa gốc "thầy pháp/phù thủy nam" |
| Magick / The Magick *(high_god_name)* | Huyền Thuật | đặt mới; khái niệm phép thuật trừu tượng Tremere tôn thờ như thần, dùng "Huyền Thuật" để tránh trùng "Huyết Thuật" (Blood Sorcery, B4d) dù phát âm gần nhau — "huyền" (huyền bí) khác "huyết" (máu) |
| Destruction *(death_deity_name)* | Hủy Diệt | trùng độc lập với lựa chọn ở B3m cho cùng dạng key tương tự — xác nhận nhất quán |
| The Beast *(devil_name + witchgodname_the_horned_god)* | Dã Thú | ✅ đã chốt B5/B4i, áp dụng lại cho cả hai key |
| Blood *(good_god_blood, health/water_god_name — danh từ thường dùng làm tên thần)* | Máu | nhất quán "Huyết" chỉ dùng trong từ ghép Hán Việt (Huyết Thuật, Huyết Tộc), còn đứng riêng làm tên thần thì dùng "Máu" thuần Việt, theo mẫu base `taoism_devil_name`="sự bất hòa" (danh từ thường làm tên thần, dẫn ở B3g) |
| chantry / chantries *(house_of_worship)* | Chantry *(giữ nguyên, đề xuất mới)* | Không có tiền lệ base. Trong WoD/POD đây là tên riêng chỉ pháo đài-trường phái thuật của Tremere, xuất hiện lặp lại làm building name thật ở `buildings/building_grand_city_POD_l_english.yml` ("Tremere Chantry", "Minor Chantry"...). Dịch nghĩa "nhà nguyện" sẽ đánh mất bản sắc thuật ngữ và lệch khi tới lượt dịch `buildings/`. Theo B0, chốt **giữ nguyên "Chantry"** — áp dụng khi dịch `buildings/` sau này |
| pyramid *(religious_symbol, danh từ thường — biểu tượng vật lý, KHÁC "Pyramid" viết hoa = hệ thống chính trị Tremere trong holy_order)* | kim tự tháp | dịch nghĩa vì là biểu tượng phổ thông, theo mẫu base dịch `christianity_religious_symbol`="thánh giá" |
| regent *(religious_head_title/devotee/priest/bishop — chức sắc Tremere, không phải "Regent" chính thể)* | Regent *(giữ nguyên, đề xuất mới)* | ⚠️ **Không dùng "Nhiếp chính"** — đó là cơ chế vanilla `game_concept_regent` (người cai trị thay quân vương chưa đủ tuổi), khác hẳn nghĩa "Regent" giáo chức Tremere (đứng đầu Chantry), dùng chung sẽ gây hiểu lầm. Xác nhận: `culture_titles_POD_l_english.yml` (chưa dịch, việc #11) đã có sẵn `duke_tremere: "Regent"` — bản gốc POD tự coi đây là danh xưng tiếng Anh riêng của văn hóa Tremere. Giữ nguyên theo B0, nhất quán với "Quaesitor(i)" |
| Tapestry *(divine_realm — cõi thần thánh trừu tượng của thuật sĩ, KHÁC "Tapestry" = Dệt Cảnh của Chi Art Kuei-Jin ở B4g)* | Tấm Thảm Dệt | đặt mới; không dùng lại "Dệt Cảnh" (B4g) vì đó là tên một Chi Art hành động, còn đây là danh từ chỉ một *cõi giới* trừu tượng — khác đối tượng biểu thị, không vi phạm quy tắc một-thuật-ngữ-một-bản-dịch |
| Umbra *(positive_afterlife)* | Umbra *(giữ nguyên)* | đã có tiền lệ giữ nguyên trong mod |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ đã chốt B3h/B3m, áp dụng lại |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ đã chốt B3h, áp dụng lại |
| Via Servilis *(tên faith con, tiếng Latin — "Con Đường của Nô Bộc")* | Via Servilis *(giữ nguyên)* | tên Latin riêng, giữ nguyên theo mẫu các thuật ngữ Latin khác (Antediluvian, Prana...); "Road of Service" (trong `_desc`) dịch là "Con Đường Phụng Sự" theo mẫu "Road"→"Con Đường" đã chốt B3f/B3k |
| Servant(s) *(viaservilis_adherent — tín đồ Gargoyle phụng sự đấng tạo hóa)* | Nô Bộc | đặt mới; chọn "Nô Bộc" thay vì "Đầy tớ" để giữ giọng cổ trang trọng hơn, hợp ngữ cảnh tôn giáo |
| Guardians of Traditions *(holy_order)* | Những Người Gìn Giữ Truyền Thống | dịch nghĩa thường, không có tiền lệ base riêng |
| Children of the Pyramid *(holy_order)* | Con Cái của Kim Tự Tháp | dịch nghĩa, nhất quán "pyramid"→"kim tự tháp" ở trên |
| Quaesitori *(holy_order + tên chức danh, xuất hiện lặp lại ở `POD_court_positions_l_english.yml`, `POD_dynasty_names_l_english.yml`, `event_localization/`)* | Quaesitori *(giữ nguyên)* | ✅ xác nhận qua tra cứu: mọi nơi khác trong mod hiện dùng nguyên "Quaesitor"/"Quaesitori" tiếng Anh — giữ nguyên theo B0 |
| The Pyramid's Elite *(holy_order)* | Tinh Anh của Kim Tự Tháp | dịch nghĩa; "Tinh Anh" cho "Elite", từ Hán Việt phổ thông, không có tiền lệ base riêng |
| The Covenant *(holy_order)* | Giao Ước | dịch nghĩa thường; "Giao Ước" là từ phổ thông cho "Covenant" (tôn giáo/lời thề) |
| The Astors *(holy_order — tên riêng bịa của POD)* | Astors *(giữ nguyên)* | danh từ riêng không rõ gốc, không có nghĩa từ điển để dịch, theo B0 |

## B3l. Thuật ngữ bổ sung (từ `POD_religion_bloodgnosticism`) — việc #2 file 10/36

Nguồn: `religion/POD_religion_bloodgnosticism_l_english.yml` (236 dòng, đã dịch xong 100%) — faith "Huyết Ngộ Đạo Luận" (đã chốt B3k) và 9 faith con theo Ngộ đạo luận Cơ Đốc (Cainite Heresy, Via Pura/Katharoi, Calomena's Chosen, Eschatologists, Black Magdalene, Swarm of Samael, Red Temptation, Third Caine + Apostles, Sancta Mater). Đối chiếu trực tiếp với `base_game_vh/localization/english/religion/religion_dualism_l_english.yml` (Nhị Nguyên Luận — cùng gốc Ngộ đạo/nhị nguyên Cơ Đốc thời Trung Cổ) và `religion_christianity_l_english.yml` (Bogomil, Cathar, Ecumenical Patriarch, Apostle, Synod).

| English | Tiếng Việt | Nguồn / ghi chú |
|---|---|---|
| Demiurge | Demiurge *(giữ nguyên)* | ✅ tiền lệ base trực tiếp: `dualism_devil_name`="Đấng Demiurge" (nhưng ở đây đứng một mình làm tên khái niệm thần học, không kèm "Đấng" vì key `bloodgnosticism_evil_god_demiurge` chỉ là danh xưng ngắn) |
| Ialdabaoth | Ialdabaoth *(giữ nguyên)* | danh từ riêng Ngộ đạo luận (tên gọi khác của Demiurge trong thần thoại Gnostic), không có bản dịch tự nhiên |
| 30th Aeon of God | Vô Lượng Kỷ Thứ 30 của Thần | đặt mới; "Aeon" trong vũ trụ luận Ngộ đạo là một cấp bậc/thời kỳ phát xuất thần linh — dùng "Vô Lượng Kỷ" (mượn Phật giáo, có tiền lệ `Wuliang`="Vô Lượng" trong `base_game_vh/names/chinese_character_names`) để giữ sắc thái siêu hình, tránh nhầm với "Kỷ Nguyên" thường (Wheel of Ages, B3c) |
| Destruction *(death_deity_name)* | Hủy Diệt | dịch nghĩa thường, danh từ trừu tượng làm tên thần |
| chapel *(house_of_worship)* | nhà nguyện | đặt mới; phân biệt với `christianity_house_of_worship`="nhà thờ" (nhà thờ lớn) — "nhà nguyện" nhỏ hơn, hợp giáo phái bí mật |
| principle of faith *(religious_head_title/devotee/priest)* | Nguyên Tắc Đức Tin | ⚠️ đã chốt trước ở `calomenasforsaken` (xem mục ngay dưới, "đã chốt trước") — **KHÔNG** phải "nguyên lý đức tin" (bản dịch ban đầu của đợt này, đã sửa lại cho khớp). Số ít/số nhiều gộp làm một theo mục 7 TRANSLATION_RULES.md |
| the abyss *(negative_afterlife, nhắc lại)* | vực thẳm | ✅ đã chốt B3h/B3m, áp dụng lại |
| heaven/thiên đàng *(divine_realm/positive_afterlife, danh từ thường)* | thiên đàng | ✅ theo `christianity_positive_afterlife`="thiên đàng" (chữ thường); khác "Thiên Đường" viết hoa đã dùng ở `POD_religion_ghoul` (B3g) — file đó không phải tiền lệ khóa cứng, ở đây bám sát dạng base hơn |
| Cainite Heresy | Dị Giáo Hậu Duệ Cain | ghép "Hậu duệ Cain" (đã chốt B2, `pod_cainite`) với "Heresy"→"Dị Giáo" (đã chốt B3k) |
| Katharoi / Kathar / Cathar(s) | Katharoi / Kathar / Cathar *(giữ nguyên)* | ✅ tiền lệ base trực tiếp: `cathar`="Cathar" (giữ nguyên tên riêng dị giáo) |
| Bogomil (heresy) | Bogomil *(giữ nguyên)* | ✅ tiền lệ base: `bogomilist`="Bogomil" |
| Neoplatonism | Chủ nghĩa Tân Plato | đặt mới; theo mẫu tên trường phái triết học phổ biến trong tiếng Việt |
| Zealot(s) *(viapura_desc, không phải trait/chức danh có sẵn)* | Zealot *(giữ nguyên)* | danh từ riêng chỉ nhóm tín đồ Via Pura trong văn cảnh này, không dịch để tránh nhầm "zealot" nghĩa thường ("kẻ cuồng tín") |
| Calomena | Calomena *(giữ nguyên)* | danh từ riêng — Em Gái Song Sinh của Caine trong thần thoại POD |
| Clanless *(calomenaschosen_desc — nhóm ma cà rồng không Clan)* | Vô Clan | đặt mới; ghép tiền tố "Vô" (đã có tiền lệ B3g: Vô Chủ, Vô Minh) với "Clan" (giữ nguyên, đã chốt B2) |
| martyr(ed) | tử đạo | ✅ tiền lệ base rộng rãi (`nick_the_apostle_desc`, `historical_character.thomas_becket`…) |
| Eschatologist(s) | Nhà Mạt Thế Luận | đặt mới; "mạt thế luận" (eschatology) là thuật ngữ thần học phổ thông trong tiếng Việt, ghép "Nhà" theo mẫu "Nhà Quỷ Học" (Demonologist, B3c/B4j) |
| Blood Communion | Thánh Thể Máu | đặt mới; ghép "Thánh Thể" (Eucharist/Communion — chưa có key base riêng nhưng là thuật ngữ Công giáo phổ thông) với "Máu" |
| Church of the Black Magdalene | Giáo Hội Magdalene Đen | "Giáo Hội" dịch nghĩa thường cho "Church" khi đứng đầu tên riêng giáo phái (khác "nhà thờ" là house_of_worship vật lý) |
| Swarm of Samael | Bầy Đàn Samael | đặt mới, "Bầy Đàn" dịch nghĩa "Swarm" |
| Crimson Curia | Triều Đình Đỏ Thẫm | đặt mới; "Curia" (triều đình Giáo hoàng) dịch là "Triều Đình" theo nghĩa hành chính tôn giáo, "Crimson"→"Đỏ Thẫm" phân biệt với "Đỏ" thường (Red Temptation/Red Cainite) |
| infernalism | thuyết thờ quỷ | đặt mới, dịch nghĩa mô tả |
| Red Temptation / Red Cainite(s) | Cám Dỗ Đỏ / Hậu Duệ Cain Đỏ | dịch nghĩa; "Cainite" ghép tính từ màu vẫn dùng "Hậu Duệ Cain" nhất quán (khác lệ thường chỉ dùng khi đứng riêng, ở đây là tên phe) |
| Ecumenical Patriarchate | Tòa Thượng Phụ Đại Kết | ✅ tiền lệ base: `ecumenical_patriarch`="Thượng phụ Đại kết" (`culture_titles_l_english.yml`); thêm "Tòa" cho tên định chế theo mẫu `orthodox_religious_head_title_name`="Tòa Thượng phụ" |
| Synod | Công Đồng | ✅ tiền lệ base (`historical_character.gemistus_pletho`="Công đồng Florence") |
| Eastern Orthodoxy / Orthodox Christianity | Chính Thống giáo Đông phương | ✅ tiền lệ base cho "Orthodox"→"Chính Thống" (nhiều nơi, vd. `historical_character.basilios_bessarion`) |
| non canon *(thirdcaine_desc)* | phi chính thống | dịch nghĩa thường, mô tả tôn giáo không thuộc chính thống Kuei-Jin/vampire lore gốc |
| Apostle(s) | Tông Đồ | ✅ tiền lệ base (`nick_the_apostle`="Tông Đồ") |
| See of Nod *(tòa thánh Cainite Heresy)* | Tòa Nod | dịch "See" (tòa giám mục) theo mẫu "Tòa Thượng Phụ"/"Tòa Thượng phụ" ở trên |
| Sancta Mater, Sancta *(tên riêng Latin — "Mẹ Thánh")* | Sancta Mater, Sancta *(giữ nguyên)* | theo B0, tên riêng tiếng Latin của giáo phái, dịch nghĩa sẽ phá vỡ tính trang trọng/bí ẩn |
| holder of Sophia (the wisdom) | người nắm giữ Sophia (trí tuệ) | Sophia giữ nguyên (đã chốt B3c/dualism precedent = nữ thần Trí Tuệ Ngộ đạo), "wisdom" dịch "trí tuệ" |
| corrupted warden *(ám chỉ Giáo Hội La Mã, chưa phải danh xưng chính thức)* | vị lãnh chúa băng hoại | dịch nghĩa; "warden" trong văn cảnh Ngộ đạo (kẻ cai quản/giam giữ linh hồn) dịch "lãnh chúa" để giữ sắc thái cai trị/giam cầm |
| Handmaidens of Sophia | Nữ Tỳ của Sophia | dịch nghĩa "Handmaiden"→"Nữ Tỳ", theo mẫu "của X" đã chốt |

## B3s. Thuật ngữ bổ sung (từ `POD_religion_roadofblood`) — việc #2 file 17/36

Nguồn: `religion/POD_religion_roadofblood_l_english.yml` (90 dòng, đã dịch xong 100%) — faith chính "Con Đường Máu" (tên đã khóa cứng ở B3k, dùng lại ở `roadofblood_religion`) và 3 faith con: Tariq el-Haqim (Sentinel gốc), Path of Righteousness (Watcher), Sisterhood of Erinyes (Sister). File không có `Glossary()`/`UmbraGlossaryLocalized()` nào (bracket count = 0).

| English | Tiếng Việt | Nguồn / ghi chú |
|---|---|---|
| Sentinel(s) *(tên tín đồ Con Đường Máu/Tariq el-Haqim)* | Vệ Binh / Các Vệ Binh | đặt mới; số ít/số nhiều gộp bằng tiền tố "Các" theo mẫu base (`islam_religion_adherent_plural`="Các tín đồ Hồi giáo") |
| Watcher(s) *(tên tín đồ Path of Righteousness)* | Người Canh Giữ / Các Người Canh Giữ | ✅ tiền lệ trực tiếp `trait_salubri_watcher`="Salubri Người Canh Giữ" (`traits_POD_l_english.yml:775`) |
| Sister(s) *(tên tín đồ Sisterhood of Erinyes)* | Chị Em / Các Chị Em | dịch nghĩa thường, nhất quán với tên hội "Hội Chị Em Erinyes" |
| Path of Righteousness | Con Đường Chính Nghĩa | đặt mới; "Path" ở đây cùng vai trò với "Road" (Con Đường, đã chốt B3f) trong hệ thống đạo đức ma cà rồng — không nhầm với "Path" của Éntomos/Ananasi (đã chốt B4c = "Đạo Lộ", hệ thống khác hẳn của Fera) |
| Righteousness | Chính Nghĩa | tính từ gốc của Path of Righteousness |
| Tariq el-Haqim, Banu Haqim, Haqim, Alamut, da'i, ace, Fortuna, vizir, Caine, Sisterhood of Erinyes/Erinyes | *(giữ nguyên)* | danh từ riêng/chức danh WoD hoặc gốc Ả Rập-Hy Lạp có sẵn trong bản gốc, theo B0; "Fortuna" và possessive "của Fortuna" khớp tiền lệ B3h |
| The Beast *(devil_name và witchgodname_the_horned_god)* | Dã Thú | ✅ đã chốt B5 |
| Destruction *(death_deity_name, danh từ trừu tượng làm tên thần)* | Hủy Diệt | dịch nghĩa thường, cùng cách xử lý với `bloodgnosticism_evil_god_name`="Hủy Diệt" (B3l) |
| blood *(health_god_name/water_god_name, danh từ thường)* | máu | chữ thường, theo mẫu đã chốt B3g (`taoism_devil_name` kiểu danh từ thường làm tên thần) — khác "Máu"/"Dòng Máu" viết hoa của `high_god_name`/`high_god_name_alternate` |
| dagger *(religious_symbol)* | dao găm | dịch nghĩa thường |
| vein *(divine_realm)* | huyết quản | đặt mới, tránh trùng "vực thẳm" (the abyss) |
| The Sentinels of Haqim / The Knives in the Dark / The Judges / The Warriors of Alamut *(4 holy order)* | Vệ Binh của Haqim / Những Lưỡi Dao Trong Bóng Tối / Các Quan Tòa / Chiến Binh của Alamut | theo mẫu base bỏ mạo từ "The" khi dịch tên holy order (`holy_order_knights_hospitaller`="Hiệp sĩ Cứu Tế", không giữ "The") |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ áp dụng nhất quán theo B3e/B3g/B3h/B3k, kể cả khi giá trị gốc không viết hoa "The" (`"the Beast's"` → "của Dã Thú") |

## B3t. Thuật ngữ bổ sung (từ `POD_religion_roadofset`) — việc #2 file 18/36

Nguồn: `religion/POD_religion_roadofset_l_english.yml` (90 dòng, đã dịch xong 100%) — faith chính "Road of Set" (đã khóa cứng ở B3k = "Con Đường Set") và 4 faith con: Via Set (nhánh chính clan Setite), Via Apep (thờ Apep — rắn hỗn loạn), Path of Subversion (Corrupter), Path of Heliopolis (Typhonian/Theophidian). 2 lần `Glossary('Antediluvian','game_concept_antediluvian_desc')` — param 1 giữ nguyên "Antediluvian" theo B0/B2b (đã chốt là thuật ngữ giữ tiếng Anh), không phải lỗi bỏ sót dịch param 1.

| English | Tiếng Việt | Nguồn / ghi chú |
|---|---|---|
| Setite(s) *(religion_adj/adherent/devotee/priest)* | Setite *(giữ nguyên)* | ✅ đã chốt B2b — tên clan/giáo phái, số ít/số nhiều gộp làm một |
| Osiris *(devil_name + witchgodname_the_horned_god)* | Osiris *(giữ nguyên)* | thần Ai Cập có thật, danh từ riêng — nhất quán với `glossary_osirian_league`/`glossary_children_of_osiris` đã chốt B2 |
| Destruction *(death_deity_name)* | Hủy Diệt | ✅ nhất quán với B3l/B3m/B3s cùng dạng key |
| temple *(house_of_worship, số ít = số nhiều trong bản gốc)* | đền thờ | theo tiền lệ base (`religion_l_english.yml` `doctrine_parameter_theocracy_temple_*`="Đền thờ") và tiền lệ POD B3n (`secret temple(s)`="đền thờ bí mật") |
| ankh *(religious_symbol)* | ankh *(giữ nguyên)* | không có tiền lệ base cho biểu tượng Ai Cập cổ này; giữ nguyên theo B0 vì là tên riêng của một vật thể tôn giáo cụ thể, không phải danh từ chung dịch được như "cross"→"thánh giá" |
| Hierophant *(religious_head_title)* | Đại Tư Tế | đặt mới; tra base thấy "High Priest"→"Đại Tư tế" (`decisions_l_english.yml:597`, `jewish_restore_high_priesthood_decision`) — Hierophant là chức tư tế tối cao trong tôn giáo huyền bí Hy Lạp/Ai Cập cổ, tương đương chức năng "Đại Tư Tế" |
| Priest *(bishop, chức sắc thường dưới Hierophant)* | Tư Tế | ghép cặp với "Đại Tư Tế" ở trên thành hệ thống phân cấp Tư Tế/Đại Tư Tế; khác "giám mục" (dành riêng cho từ gốc "bishop", B3j) vì giá trị gốc ở đây là chữ "Priest" |
| Set's Embrace *(divine_realm/positive_afterlife)* | Vòng Tay của Set | đặt mới; "Embrace" ở đây là vòng tay/cõi thiên đường ẩn dụ của thần Set, KHÔNG phải "Embrace"=Nghi lễ Trao truyền (B2, nghi thức biến thành ma cà rồng) — hai nghĩa khác hẳn của cùng một từ tiếng Anh, dùng "Vòng Tay" cho nghĩa cõi giới ở đây để tránh lẫn với nghi lễ Trao truyền |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ đã chốt B3h/B3m/B3s, áp dụng lại |
| Antediluvian | Antediluvian *(giữ nguyên)* | ✅ đã chốt B0/B2b, param 1 của `Glossary()` ở đây |
| Via Set *(tên faith con — nhánh chính clan Setite, tiếng Latin "Con Đường Set")* | Con Đường Set | cùng dịch với `roadofset`/`viaset` — cả hai key đều hiển thị "Road of Set" trong bản gốc, dùng chung một bản dịch |
| Apep *(via Apep — rắn hỗn loạn, hóa thân của Set)* | Apep *(giữ nguyên)* | ✅ đã chốt B3 (`glossary_wyrm_apep`) |
| Apepite(s) *(viaapep_adj/adherent)* | Apepite *(giữ nguyên)* | đặt mới theo mẫu "Setite" — demonym WoD gốc từ "Apep", không có từ Việt tương đương, giữ nguyên theo B0 |
| Path of Subversion | Con Đường Lật Đổ | đặt mới; "Path" đồng vai trò "Road" (Con Đường, B3f/B3k) trong hệ đạo đức ma cà rồng, khác "Đạo Lộ" của Éntomos/Ananasi (B4c) |
| Corruption *(pathofsubversion_adj — sự tha hóa định chế xã hội, KHÁC "Corruption" của Wyrm)* | Tha Hóa | đặt mới; tránh trùng "Ô Uế"/"Bôi Nhọ" đã chốt cho `glossary_wyrm_corruption` (B3/B3b) vì đây là khái niệm chính trị-xã hội, không phải Wyrm học thuyết Fera |
| Corrupter(s) *(pathofsubversion_adherent)* | Kẻ Tha Hóa | theo "Corruption"→"Tha Hóa" ở trên |
| Path of Heliopolis | Con Đường Heliopolis | "Heliopolis" là địa danh Ai Cập cổ có thật (trung tâm thờ thần mặt trời), giữ nguyên tên riêng theo B0 |
| Typhonian *(pathofheliopolis_adj)* | Typhonian *(giữ nguyên)* | tính từ WoD gốc từ "Typhon" (tên Hy Lạp của Set), không có bản dịch tương đương gọn, giữ nguyên theo B0 |
| Theophidian(s) *(pathofheliopolis_adherent)* | Theophidian *(giữ nguyên)* | demonym WoD tự đặt (theo + ophidian = rắn-thần), không có tiền lệ base, giữ nguyên theo B0 |
| Cohort of Set *(holy_order)* | Đội Cấm Vệ của Set | đặt mới; "Cohort" = đơn vị quân đội La Mã, dịch theo tinh thần "Đội" (mẫu `holy_order_enoch_peacekeepers`="Đội Gìn Giữ Hòa Bình Enoch", B3o) + possessive "của X" |
| The Medjay *(holy_order)* | Medjay *(giữ nguyên)* | tên lực lượng cảnh vệ/chiến binh Ai Cập cổ có thật trong lịch sử, danh từ riêng — bỏ mạo từ "The" theo mẫu base dịch holy order (B3s) |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ áp dụng nhất quán theo B3e/B3g/B3h/B3k/B3s |

## B3v. Thuật ngữ bổ sung (từ `POD_religion_roadoflilith`) — việc #2 file 20/36

Nguồn: `religion/POD_religion_roadoflilith_l_english.yml` (96 dòng, đã dịch xong 100%) — faith chính "Con Đường Lilith" (tên đã khóa cứng ở B3k, dùng lại ở `roadoflilith_religion`) và 5 faith con/tổ chức: Derech Lilit (nhóm Lilin gốc), Via Faciendi (Con Đường Tạo Tác), Via Spinae (Con Đường Gai Nhọn), Via Calantica (Con Đường Màn Che), Daughters of Gorgo. File không có `Glossary()`/`UmbraGlossaryLocalized()` nào (bracket count = 0, chỉ có 1 icon `@vampire_icon!`).

| English | Tiếng Việt | Nguồn / ghi chú |
|---|---|---|
| Road of Lilith *(tên faith chính)* | Con Đường Lilith | ✅ đã khóa cứng B3k, áp dụng ở `roadoflilith_religion` |
| Lilin *(tên tín đồ Con Đường Lilith)* | Lilin *(giữ nguyên)* | danh từ riêng WoD, theo B0; số ít/số nhiều gộp làm một theo mục 7 TRANSLATION_RULES.md |
| The Dark Mother *(high_god_name_alternate — biệt danh của Lilith)* | Mẹ Bóng Tối | dịch nghĩa, ghép "Mẹ" + "Bóng Tối" (đã có tiền lệ `pod_wod`="Thế Giới Bóng Tối") |
| Destruction *(death_deity_name)* | Hủy Diệt | ✅ khớp tiền lệ B3s (`roadofblood`) — cùng cách dịch danh từ trừu tượng làm tên thần |
| coven / covens *(house_of_worship)* | hội phù thủy / các hội phù thủy | đặt mới; tiền lệ gần base `witch_coven`="Hội Phù Thủy" (`event_modifiers_l_english.yml`), hạ chữ thường theo mẫu clergy/house_of_worship (base dùng "tu sĩ", "linh mục" viết thường) |
| ashen crown *(religious_symbol)* | vương miện tro tàn | dịch nghĩa thường |
| Cycle of Lilith *(religious_text)* | Chu Kỳ Lilith | dịch nghĩa, viết hoa theo tên tác phẩm tôn giáo |
| grandmother *(religious_head_title/-name, chức sắc nữ tối cao)* | bà | dịch nghĩa, chữ thường theo mẫu base cho chức sắc tôn giáo (`christianity_bishop`="giám mục") |
| brother(s)/sister(s) *(devotee)* | anh/các anh, chị/các chị | dịch nghĩa thường, xưng hô huynh đệ tôn giáo kiểu Kindred; số nhiều thêm "các" theo mẫu base |
| father(s)/mother(s) *(priest_male/bishop, chức sắc)* | cha/các cha, mẹ/các mẹ | dịch nghĩa thường, giữ tương phản với "bà" (chức sắc tối cao) |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ đã chốt B3h/B3m/B3s, áp dụng lại |
| the Beast *(witchgodname_the_horned_god)* | Dã Thú | ✅ đã chốt B5/B3s, áp dụng lại cho cả hai key (`witchgodname_the_horned_god` và `_possessive`) |
| blood *(health_god_name, danh từ thường làm tên thần)* | máu | ✅ khớp mẫu B3s/B3g — chữ thường |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ đã chốt B3h, áp dụng lại kèm possessive "của Fortuna" |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ áp dụng nhất quán theo B3e/B3g/B3h/B3k/B3s |
| Derech Lilit, Via Faciendi, Via Spinae, Via Calantica, Ba'ham, Bahari, Ki-sikil-lil-la-ke, Lhaka, Gorgo, Gorgon(s) | *(giữ nguyên)* | danh từ riêng/thuật ngữ Latin-Hebrew-Sumer của giáo phái, theo B0 |
| Via Faciendi *(tên hiển thị, nghĩa "Path of Making")* | Con Đường Tạo Tác | dịch nghĩa faith con, cùng mẫu "Road/Path"→"Con Đường" (B3f/B3k/B3s) |
| Maker(s) *(tên tín đồ Via Faciendi)* | Kẻ Tạo Tác / Những Kẻ Tạo Tác | dịch nghĩa thường, gắn với "Via Faciendi"→"Con Đường Tạo Tác" |
| Via Spinae *(tên hiển thị, nghĩa "Path of Thorns")* | Con Đường Gai Nhọn | dịch nghĩa faith con |
| Via Calantica *(tên hiển thị, nghĩa "Path of Veils")* | Con Đường Màn Che | dịch nghĩa faith con |
| rabbinical figure *(mô tả Lilith trong `derechlilit_desc`)* | nhân vật trong truyền thống Do Thái giáo | ✅ tra base (`religion_judaism_l_english.yml` giữ nguyên "Rabbinism"/"Rabbinic" không dịch) — dịch thoát ý "rabbinical" thành cụm mô tả thay vì gượng ép một tính từ Hán-Việt, tránh đặt ra một thuật ngữ mới không cần thiết |
| demon-children *(viafaciendi_desc)*, Mother of Monsters | những đứa con quỷ dữ, Mẹ của Quái Vật | dịch nghĩa thường |
| Abrahamic God *(viacalantica_desc)* | Thượng Đế của Abraham | dịch nghĩa, "Abrahamic" ghép possessive "của Abraham" theo mẫu "của X" |
| Daughters of Gorgo *(tên tổ chức)* | Con Gái của Gorgo | dịch nghĩa, mẫu possessive "của X" |
| neonate(s) *(daughtersofgorgo_desc, ma cà rồng mới được Trao truyền)* | kẻ mới được Trao truyền | đặt mới, ghép với "Nghi lễ Trao truyền/được Trao truyền" đã chốt B2 (`pod_Embrace(d)`) thay vì dịch từng chữ "neonate" tách biệt |

## B3r. Thuật ngữ bổ sung (từ `POD_religion_raktasadhus`) — việc #2 file 16/36

Nguồn: `religion/POD_religion_raktasadhus_l_english.yml` (97 dòng, đã dịch xong 100%) — nhóm faith ma cà rồng Ấn Độ "Rakta-sadhus" và 5 faith con (Mayaparisatya, Path of Paradox/Deceivers, Path of Devaraja, Path of Daitya, Samsara/Rakshasa). Đối chiếu trực tiếp với `base_game_vh/localization/english/religion/religion_hinduism_l_english.yml` cho mẫu possessive, house_of_worship, tên thần. Chỉ có **một** `Glossary()` trong toàn file (`raktasadhus_religion_desc`), tham số 1 `'Wan Kuei'` xác nhận **giữ nguyên tiếng Anh** — tra toàn mod thấy "Wan Kuei" chưa từng được dịch ở bất kỳ file nào khác, kể cả file đã xong (`POD_religion_kueijin_l_english.yml` dòng 103, 308 đều giữ "Wan Kuei" nguyên trong cả tham số 1 của Glossary lẫn văn xuôi thường).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Wan Kuei *(tham số 1 của `Glossary('Wan Kuei','game_concept_kuei_jin_desc')`, và trong văn xuôi thường)* | Wan Kuei *(giữ nguyên)* | ✅ xác nhận tiền lệ toàn mod — không dịch, kể cả khi là tham số 1 dịch được của Glossary (ngoại lệ với quy tắc "luôn dịch tham số 1", vì đây là danh từ riêng WoD đã chốt giữ nguyên ở mọi nơi khác trong repo, giống "Kuei-Jin") |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ tiền lệ base_game_vh (`religion_hinduism_l_english.yml`: "của Brahman", "của Vishnu"…), áp dụng cho toàn bộ god-name possessive trong file |
| temple(s) *(house_of_worship)* | đền thờ / các đền thờ | ✅ tiền lệ base (`hinduism_house_of_worship`="đền thờ") |
| rose *(religious_symbol)* | hoa hồng | dịch nghĩa thường |
| Destruction *(death_deity_name)* | Hủy Diệt | nhất quán với B3m/B3n/B3q (cùng key `death_deity_name` dùng "Destruction"→"Hủy Diệt" ở nhiều faith khác) |
| blood *(health_god_name, danh từ thường dùng làm tên thần)* | máu | ✅ nhất quán mẫu B3g/B3n (danh từ thường làm tên thần → chữ thường thuần Việt) |
| the Beast *(witchgodname_the_horned_god)* | Dã Thú | ✅ đã chốt B4i/B3n, áp dụng lại |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ đã chốt B3h, áp dụng lại |
| Blood-Brahmin *(religious_head_title/bishop)* | Brahmin Máu | đặt mới; "Brahmin" giữ nguyên theo B4g (thuật ngữ Ấn Độ giáo có thật đã chốt), ghép với "Máu" (thuần Việt) theo mẫu compound chấp nhận được của B0 (`Clan Curse`→`Lời nguyền Clan`) — thứ tự "Danh từ riêng + tính từ Việt" nhất quán với "Wyrm Ô Uế", "Wyrm Tai Ương" |
| Mahakala, Kali, Ravana, Shilmulo, Atharva-Veda, Swarga Loka, Naraka, Sadhana, Asura, Devaraja, Rakshasa | *(giữ nguyên)* | tên riêng/thuật ngữ Ấn Độ giáo có thật hoặc thuật ngữ WoD gốc Phạn ngữ, theo B0 và tiền lệ base (Naraka đã có ở `hinduism_negative_afterlife`) |
| Rakta-sadhus / Rakta-sadhu | Rakta-sadhus / Rakta-sadhu *(giữ nguyên)* | tên nhóm faith, biến thể chính tả của "Raktasadhus" — giữ dạng gốc có gạch nối vì đây là key/tên hiển thị riêng biệt trong bản gốc |
| Cathayan *(tính từ, "ma cà rồng vùng Cathay")* | Cathay *(giữ nguyên tên địa danh, ghép thành "ma cà rồng Cathay")* | "Cathay" là tên gọi cổ của Trung Hoa trong tiếng Anh trung đại — không có tiền lệ base, giữ nguyên tên riêng địa danh như cách base giữ tên địa danh ngoại lai khác (Jerusalem, Rome ở B3k) |
| Court *(Infinite Thunders Court, Scarlet Phoenix Court — tổ chức Kuei-Jin)* | Triều Đình | ✅ nhất quán B3e (Kuei-Jin Courts = "Triều Đình") |
| Infinite Thunders Court | Triều Đình Vạn Lôi vô hạn | đặt mới; "Vạn Lôi" (vạn tiếng sấm) dịch nghĩa Hán-Việt "Infinite Thunders", theo giọng các tên tổ chức Kuei-Jin khác |
| Scarlet Phoenix Court | Triều Đình Phượng Hoàng Đỏ Thẫm | đặt mới; "Đỏ Thẫm" nhất quán với "Crimson"→"Đỏ Thẫm" đã chốt B3l (`Crimson Curia`), phân biệt "Scarlet" khỏi "Đỏ" thường |
| Path of Paradox / Deceiver(s) *(viaparadox)* | Con Đường Nghịch Lý / Kẻ Lừa Dối | "Path"→"Con Đường" nhất quán B3f/B3k/B3q (Path dùng đồng nghĩa Road trong các faith `pathof*`); "Nghịch Lý" dịch nghĩa "Paradox" |
| Divine(s) *(pathofdevaraja_adherent)* | Đấng Thần Thánh | dịch nghĩa; số nhiều thêm "Các" vì ngữ cảnh liệt kê nhóm người theo mục 7 TRANSLATION_RULES.md (không gộp trơn vì câu văn cần phân biệt số ít/nhiều rõ) |
| Snake-Charmer(s) *(pathofdaitya_adherent)* | Kẻ Dụ Rắn / Những Kẻ Dụ Rắn | dịch nghĩa trực tiếp |
| Brahminism *(mortal Brahminism — hệ tôn giáo, KHÁC "Brahmin" danh xưng đẳng cấp)* | Bà-la-môn giáo | ✅ tiền lệ base xác nhận: `hinduism_priest_term_plural`="Bà-la-môn" — dùng "giáo" cho hệ thống tôn giáo, giữ "Brahmin" nguyên khi là danh xưng đẳng cấp/cá nhân trong cùng đoạn văn (hai từ tiếng Anh khác nhau biểu thị hai khái niệm khác nhau, không vi phạm một-thuật-ngữ-một-bản-dịch) |
| Kindred *(mayaparisatya_desc/viaparadox_desc, chỉ ma cà rồng nói chung)* | Huyết Tộc | ✅ đã chốt B3k, áp dụng lại |
| neonate(s) *(samsara_desc — ma cà rồng mới hóa)* | ma cà rồng mới hóa | đặt mới; chưa có tiền lệ base/POD nào dịch từ này trước đây (tra toàn mod chỉ thấy các file chưa dịch dùng "neonate"), đặt theo nghĩa đen "mới được Trao truyền/mới hóa thành ma cà rồng", đối lập ngầm với "Elder" (chưa gặp, sẽ đặt khi tới lượt) |
| Ethics *(samsara_desc — giáo lý đạo đức của Path)* | Đạo Lý | đặt mới, không có tiền lệ base/POD riêng cho nghĩa hệ thống đạo đức tôn giáo này |
| Hierarchy of Sins *(samsara_desc)* | Thang Tội Lỗi | đặt mới; "Thang" (bậc thang) gợi ý hệ thống phân cấp tội lỗi có thứ bậc, không có tiền lệ base/POD |
| sect *(raktasadhus_desc, danh từ thường "giáo phái/môn phái")* | giáo phái | dịch nghĩa thường |
| Hinduism *(mayaparisatya_desc)* | Ấn Độ giáo | ✅ tiền lệ base (`hinduism_religion`="Ấn Độ giáo") |

## B3w. Thuật ngữ bổ sung (từ `POD_religion_roadofbones`) — việc #2 file 21/36

Nguồn: `religion/POD_religion_roadofbones_l_english.yml` (99 dòng, đã dịch xong 100%) — tôn giáo "Road of Bones" (Con Đường Xương Cốt, đã khóa cứng ở B3k), ma cà rồng nghiên cứu về cái chết, chủ yếu Cappadocian. File không có `Glossary()`/`UmbraGlossaryLocalized()` nào (bracket count = 0). 4 faith con dùng mẫu "Road/Path of X" → "Con Đường X" đã có sẵn từ B3f/B3k/B3s.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Road of Bones *(roadofbones_religion)* | Con Đường Xương Cốt | ✅ đã khóa cứng B3k, áp dụng lại |
| Scholar(s) *(religion_adj/adherent/devotee/priest/bishop, tên tín đồ)* | Học Giả | đặt mới, không có tiền lệ base cho "Scholar" ở nghĩa tên tín đồ tôn giáo; dùng nhất quán cho toàn bộ các biến thể chức sắc trong file |
| Death *(high_god_name)* | Cái Chết | ✅ tiền lệ base (`christianity_death_deity_name`="Cái Chết") — dùng cho danh từ trừu tượng làm tên thần |
| The Death *(high_god_name_alternate)* | Tử Thần | biến thể thứ hai của cùng vị thần "Cái Chết", tránh lặp từ, "Tử Thần" là cách gọi nhân cách hóa phổ biến trong tiếng Việt |
| the Beast *(devil_name/witchgodname_the_horned_god)* | Dã Thú | ✅ đã chốt B5, áp dụng lại |
| Destruction *(death_deity_name)* | Hủy Diệt | ✅ khớp tiền lệ đã dùng nhiều lần cho cùng dạng key ở B3m/B3n/B3p/B3q (`death_deity_name`="Destruction"→"Hủy Diệt") — không nhầm với "Entropy"="Hoại Diệt" (B3b) |
| refuge(s) *(house_of_worship)* | chốn nương thân | đặt mới, không có tiền lệ base trực tiếp; phù hợp giọng văn ma cà rồng ẩn dật nghiên cứu cái chết |
| skull *(religious_symbol)* | đầu lâu | dịch nghĩa thường |
| Sargon Codex *(religious_text)* | Sargon Codex *(giữ nguyên)* | ✅ tiền lệ POD xác nhận: xuất hiện nguyên dạng ở `modifiers/1230objectives_POD_modifiers_l_english.yml` và `POD_journeys_l_english.yml` (tên hiện vật/nhiệm vụ riêng, chưa dịch — giữ nguyên tên riêng tránh lệch với các file đó) |
| first scholar *(religious_head_title)* | học giả đệ nhất | dịch nghĩa, giữ chữ thường như bản gốc (khác các tên chức sắc viết hoa ở các faith khác) |
| Underworld *(divine_realm/positive_afterlife, danh từ thường, KHÔNG phải tham số `UmbraGlossaryLocalized('shadowlands',…)`)* | Âm Giới | đặt mới cho ngữ cảnh này; phân biệt với "Âm Phủ" (B4j, chỉ dành riêng cho tham số 2 của macro `UmbraGlossaryLocalized('shadowlands','Underworld')`) — ở đây "Underworld" là danh từ thường trong key tôn giáo, không đi qua macro đó |
| Oblivion *(negative_afterlife)* | Hư Vô | ✅ khớp tiền lệ đã dùng nhiều lần cho cùng key ở B3q và nơi khác |
| blood *(health_god_name, danh từ thường làm tên thần)* | máu | ✅ khớp mẫu B3g/B3h/B3s — chữ thường |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ đã chốt B3h, áp dụng lại kèm possessive "của Fortuna" |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ áp dụng nhất quán theo B3e/B3g/B3h/B3k |
| Via Ossium, Ossium, Via Primordia, Primordia | *(giữ nguyên — không dịch)* | tên Latin của 2 faith con; khác "Road/Path of X" (là cụm tiếng Anh thường), đây là cụm Latin nguyên bản kiểu "Tal'Mahe'Ra"/"Manus Nigrum" (B3q) — giữ nguyên theo B0. **Chưa hoàn toàn chắc chắn, cần xác nhận thêm nếu gặp lại "Via X" ở file khác** |
| Followers of Lazarus *(followersoflazarus, tên faith con)* | Tín Đồ của Lazarus | dịch nghĩa "Followers of" + giữ nguyên tên riêng Kinh Thánh "Lazarus", mẫu possessive "của X" |
| Lazarene *(followersoflazarus_adj)*, Infitiore(s) *(followersoflazarus_adherent)* | *(giữ nguyên — không dịch)* | tính từ/danh xưng ngoại lai phái sinh từ tên riêng, không dịch được tự nhiên sang tiếng Việt, theo mẫu B0 (giống "Rathmonicusi", B3q) |
| Path of the Wheel *(pathofthewheel)* | Con Đường Bánh Xe | dịch nghĩa theo mẫu "Road/Path of X"→"Con Đường X" |
| Scientist(s) *(pathofthewheel_adherent)* | Nhà Khoa Học | dịch nghĩa thường |
| Road of the Abyss *(roadoftheabyss)* | Con Đường Vực Thẳm | dịch nghĩa, "vực thẳm" đã có tiền lệ base/POD (B3h/B3m/B3s) |
| Mystic(s) *(roadoftheabyss_adherent)* | Nhà Huyền Học | đặt mới, không có tiền lệ base cho "Mystic" ở nghĩa danh xưng tín đồ; "Huyền Học" gợi nghiên cứu bí ẩn/siêu hình, phù hợp mô tả file |
| The Harbingers *(holy_order_harbringers_cappa)* | Điềm Báo Giả | ✅ tiền lệ base (`adventurer_name_sections_l_english.yml`: `harbingers`="Điềm báo giả") — viết hoa theo quy ước tên riêng holy order |
| Guardians of the Erciyes *(holy_order_erciyes)* | Vệ Binh Erciyes | "Erciyes" là địa danh có thật (núi lửa Thổ Nhĩ Kỳ) → giữ nguyên theo mẫu giữ tên địa danh (B3k); "Guardians" dịch "Vệ Binh", khác "Defenders"→"Hộ Vệ" (đã dùng cho `holy_order_defenders_ashirra`, B3i) để tránh trùng từ giữa hai holy order khác nhau |
| Via Primordia *(viaprimordia)*, Primordian(s) *(viaprimordia_adherent)* | Via Primordia *(giữ nguyên)*, Primordian *(giữ nguyên)* | xem dòng "Via Ossium/Primordia" ở trên; "Primordian" là danh xưng phái sinh từ tên Latin, không dịch |
| the 'Three' *(viaprimordia_desc, ba linh hồn Creation/Destruction/Preservation)* | 'Tam Vị' | dịch nghĩa, giữ dấu nháy đơn như bản gốc |
| Creation / Destruction / Preservation *(3 linh hồn của viaprimordia_desc)* | Sáng Tạo / Hủy Diệt / Bảo Tồn | dịch nghĩa thường; "Destruction" ở đây khớp lại "Hủy Diệt" như trên dù ngữ cảnh khác (tên thần vs. một trong ba linh hồn) — cùng từ tiếng Anh, cùng bản dịch, đúng nguyên tắc một-thuật-ngữ-một-bản-dịch |
| Avatar *(viaprimordia_desc)* | Hóa Thân | dịch nghĩa thường, không nhầm với "Avatar" gốc của Cappadocius trong `POD_journeys_l_english.yml` (chưa dịch, sẽ đồng bộ khi tới việc #11/#12) |
| Lupine(s) *(viaprimordia_desc, cách gọi người sói của phe khác)* | Lupine *(giữ nguyên)* | danh từ tiếng Latin chỉ "người sói" dùng như biệt danh ngoại lai trong văn cảnh WoD, không có tiền lệ base, giữ nguyên vì là cách gọi đặc thù (khác `trait_werewolf`="Người sói" chính thức) |

## B3u. Thuật ngữ bổ sung (từ `POD_religion_vampirespecialdoctrines`) — việc #2 file 19/36

Nguồn: `religion/POD_religion_vampirespecialdoctrines_l_english.yml` (92 dòng, đã dịch xong 100%) — các giáo lý đặc biệt (`special_doctrine_*`) gắn với sự kiện/tổ chức ma cà rồng cụ thể (Undead Aesir, Restored Republic Roma cổ đại, Carthage, Anda Mông Cổ, Inquisition, Wu Feng, Hunter Schism, Piyau Payung Đông Nam Á…), không phải tên faith gốc.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Aesir *(Undead Aesir)* | Aesir *(giữ nguyên)* | danh từ riêng thần thoại Bắc Âu, theo B0 |
| Einherjar *(tham số 1 của `Glossary('Einherjar',...)`)* | Einherjar *(giữ nguyên)* | thuật ngữ Bắc Âu nguyên tác (chiến binh tử trận được Odin chọn), không có tiền lệ base — giữ nguyên như các thuật ngữ ngoại lai khác theo B0 |
| Canarl *(warriors of Canarl)* | Canarl *(giữ nguyên)* | danh từ riêng địa danh/tổ chức POD |
| Senate / Senatorial | Viện Nguyên Lão / Nguyên Lão | không có tiền lệ base; đặt theo Hán-Việt "Nguyên Lão" (nghị viên cấp cao) cho hệ thống chính trị La Mã cổ đại của ma cà rồng |
| Republic | Cộng Hòa | ✅ tra base (`republic_government`="Cộng Hòa") |
| Carthage | Carthage *(giữ nguyên)* | ✅ tiền lệ base giữ nguyên tên địa danh (`e_carthage`="Carthaginian Empire", `b_cartaghe`="Carthage") |
| Utopia | Không Tưởng | đặt mới, không có tiền lệ base dịch nghĩa trực tiếp (base chỉ dùng "utopia" giữ nguyên 1 lần trong văn cảnh khác); dịch nghĩa Hán-Việt phổ biến "Không Tưởng" |
| Prometheans | Prometheus *(giữ nguyên, số nhiều gộp)* | danh từ riêng thần thoại Hy Lạp làm tên nhóm, không có tiền lệ base; giữ nguyên theo B0 |
| Curia | Giáo Triều | ✅ tra base (`christianity_religious_head_title_name`="Giáo triều") — dùng cho "Crimson Curia" |
| See *(Restored See of Nod, khác "Holy See"="Tòa Thánh" của base)* | Tòa *(ghép "Tòa Nod")* | phỏng theo mẫu base "Tòa Thánh" nhưng đối tượng là "Nod" (Sách Nod, đã chốt B2b) chứ không phải Rome, nên không dùng "Tòa Thánh" nguyên xi |
| Church of the Third Caine | Giáo Hội Caine Đệ Tam | "Caine" giữ nguyên (B2b), "Đệ Tam" theo lối Hán-Việt số thứ tự đã dùng cho "Thế Hệ Thứ N" (B4e) |
| Warden(s) | Quản Giáo | ✅ tra base (`relation_warden`="quản giáo") |
| Order of Moloch | Order of Moloch *(giữ nguyên)* | tên tổ chức riêng, không có tiền lệ base cho "Moloch"; giữ nguyên theo B0 vì dịch nghĩa "Hội/Dòng Moloch" không thêm rõ ràng và tên tổ chức WoD thường giữ nguyên |
| Eyes and Ears | Tai Mắt Khắp Nơi | ✅ tra base, thành ngữ "tai mắt" xác nhận qua nhiều key (`prelude_events.0020.b`, `councillor_spouse_stewardship.2001.c`) |
| Acre *(Knights of Acre)* | Acre *(giữ nguyên)* | ✅ tiền lệ base giữ nguyên tên địa danh (`b_acre`="Acre", `c_acre`="Acre") — không dịch |
| Oculi Dei | Oculi Dei *(giữ nguyên)* | tên tổ chức Latin, không dịch (nhất quán với cách các tên Latin khác trong `traits_POD` B4g được giữ nguyên) |
| St. John *(Sisters of St. John)* | Thánh John | dịch "St." thành "Thánh", giữ tên riêng "John" |
| Red Order | Hội Đỏ | đặt mới, "Order" (tổ chức tôn giáo/hội kín) dịch "Hội" theo văn phong POD, nhất quán với cách các tổ chức Inquisition khác trong file này được dịch |
| House von Murnau | Gia Tộc Von Murnau | "House" ở nghĩa dòng họ quý tộc — dùng "Gia Tộc" theo A10 (`House`="Gia tộc"); "von Murnau" viết hoa "Von" theo quy ước tên riêng đầu câu |
| Hounds of God | Chó Săn của Chúa | dịch nghĩa; "hounds"→"chó săn" có tiền lệ base (`hounds`="Chó săn") |
| Wu Feng | Wu Feng *(giữ nguyên)* | danh từ riêng, tên một giáo phái/nhân vật Kuei-Jin, không dịch |
| Hunter Schism | Ly Giáo Thợ Săn | "Schism"→"Ly Giáo" (tiền lệ base `mend_the_great_schism_decision`="Hàn gắn Đại Ly giáo"); "Hunter"="Thợ săn" đã chốt B4 |
| Shadow Inquisition | Shadow Inquisition *(giữ nguyên)* | "Inquisition" giữ nguyên xuyên suốt file (không có tiền lệ base dịch nghĩa, tổ chức WoD riêng), ghép "Shadow" giữ nguyên theo tên tổ chức đầy đủ |
| Holy Arts | Thánh Thuật | đặt mới, "Holy"→"Thánh" theo văn phong POD, "Arts" ở nghĩa hệ thống phép thuật dịch "Thuật" (nhất quán cách B4g dịch "Arts Mastery"→"Tinh Thông Nghệ Thuật", nhưng ở đây ghép ngắn gọn hơn vì là tên giáo lý) |
| Theurgist / Theurgy | Nhà Thần Thuật / Thần Thuật | ⚠️ SỬA LẠI: `trait_theurgist` **đã dịch** thành "Nhà Thần Thuật" trong `traits/traits_POD_l_english.yml:1285` (B4h) — đây KHÔNG phải khái niệm chưa chốt. Một agent dịch `POD_religion_vampirespecialdoctrines` từng nhầm là chưa dịch và giữ nguyên tiếng Anh trong văn xuôi thường (không phải trong `[GetTrait(...)]`) — đã sửa lại thành "Nhà Thần Thuật"/"Thần Thuật" cho khớp. `[GetTrait('theurgist').GetName(...)]` tự động hiển thị đúng, không cần và không được viết "Theurgist" trần trong câu văn nữa. |
| Ordination | Lễ Tấn Phong | đặt mới, dịch nghĩa nghi lễ tôn giáo phổ thông |
| Sorcerer Ordination | Lễ Tấn Phong Pháp Sư | "Sorcerer"→"Pháp Sư" đã chốt B4h (phân biệt khỏi "Pháp sư"=Mage bằng viết hoa) |
| Psychic(s) | Người Có Năng Lực Ngoại Cảm | đặt mới, không có tiền lệ base; dịch nghĩa đầy đủ vì không có thuật ngữ ngắn tương đương trong tiếng Việt phổ thông |
| Devil *(mark from the Devil, ngữ cảnh Cơ Đốc chung, khác witchgodname riêng)* | Quỷ Dữ | ✅ nhất quán B3g (`witchgodname_the_horned_god`="Quỷ Dữ") |
| Piyau Payung | Piyau Payung *(giữ nguyên)* | danh từ riêng (giáo chủ/nhà tiên tri) Đông Nam Á, không dịch |

> Lưu ý kỹ thuật: dòng `undead_aesir_doctrine_name` gốc là `"Rejuvenated [Glossary('Einherjar','game_concept_einherjar_desc')]"`. Vì tham số 1 của `Glossary()` là "Einherjar" (giữ nguyên, không phải chữ tiếng Anh thường cần dịch), toàn bộ phần dịch được nằm ở chữ "Rejuvenated" đứng ngoài — dịch thành `"[Glossary('Einherjar','game_concept_einherjar_desc')] Được Hồi Sinh"` (đảo vị trí tính từ ra sau cho đúng ngữ pháp tiếng Việt, cụm Glossary giữ nguyên vị trí đầu vì đó là chủ ngữ).

## B3y. Thuật ngữ bổ sung (từ `POD_religion_roadofheaven`) — việc #2 file 23/36

Nguồn: `religion/POD_religion_roadofheaven_l_english.yml` (169 dòng, đã dịch xong 100%) — faith chính "Road of Heaven" (Con Đường Thiên Đường, đã khóa cứng ở B3k) và 15 faith con Noddist (Via Caeli, Via Divinitatis, Via Penaculum, Via Vindicta, Via Dolorosa, Via Christi, Derech Chaim, Code of Samiel, Via Archangeli, Consumptionism, Divisionism, Via Aesigard, Via Noctis, Path of the Heavenly Abode, Via Redemptio). Đây là faith "neo" mà `bloodgnosticism`/`calomenasforsaken` đã trỏ tới khi chốt "principle of faith"→"Nguyên Tắc Đức Tin" (11/11 dòng đã áp dụng đúng, khớp tuyệt đối với số lần xuất hiện gốc). File không có `UmbraGlossaryLocalized()`; chỉ 1 `Glossary('Diablerize','game_concept_diablerie_desc')` — tham số 1 giữ nguyên "Diablerize" (chưa có tiền lệ dịch verb này ở bất kỳ file POD nào khác tính đến nay, nhất quán với "Diablerie" giữ nguyên tiếng Anh đã chốt B2).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| God *(high_god_name, tổng quát nhiều nhánh Cơ Đốc/Do Thái/Bắc Âu)* | Thượng Đế | ✅ tra base (`dualism_high_god_name`="Thượng Đế") — dùng bản trung tính, không dùng "Thiên Chúa" (đặc thù Công giáo) vì faith này bao trùm cả Do Thái giáo (Derech Chaim) và ngoại giáo Bắc Âu (Via Aesigard) |
| The Devil *(devil_name/witchgodname_the_horned_god)* | Ác Quỷ | đặt mới cho ngữ cảnh chung; khác "Quỷ Dữ" đã dùng ở B3u cho ngữ cảnh khác — cả hai đều hợp lệ tùy file, không phải xung đột vì không cùng nguồn |
| Destruction *(death_deity_name)* | Hủy Diệt | đặt mới, dịch nghĩa trực tiếp |
| chapel *(house_of_worship)* | nhà nguyện | ✅ tra base_game_vh (`building_vihara_halls_03_desc` dùng "nhà nguyện"; phân biệt với `christianity_house_of_worship`="nhà thờ" quy mô lớn hơn) |
| cross *(religious_symbol)* | thánh giá | ✅ tra base (`christianity_religious_symbol`="thánh giá") |
| Gospel of Laodice | Phúc Âm Laodice | ✅ tra base, "Gospel"→"Phúc Âm" là thuật ngữ Cơ Đốc phổ biến; "Laodice" giữ nguyên tên riêng |
| bishop | giám mục | dịch nghĩa phổ thông, phân biệt với `councillor_court_chaplain`="Giáo sĩ Triều đình" (chức sắc hội đồng khác) |
| heaven *(divine_realm/positive_afterlife)* | thiên đàng | ✅ tra base (`christianity_positive_afterlife`="thiên đàng") |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ tra base (`christianity_negative_afterlife_2`="Vực Thẳm") và tiền lệ POD đã dùng ở nhiều file `roadof*`/`codeoftremere`/`calomenasforsaken` khác |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ tiền lệ base y hệt (`christianity_trickster_god_name`="Fortuna") |
| Noddist(s) *(religion_adherent, tự xưng tín đồ Road of Heaven nói chung)* | Tín đồ Nod | đặt mới, ghép "Tín đồ" + "Nod" (Sách Nod đã chốt B2b); dùng thống nhất số ít/số nhiều theo mục 7 TRANSLATION_RULES.md |
| Divinist(s) *(viadivinitatis_adherent)* | Tín đồ Thần Thánh | đặt mới, "Divinity"→"Thần Thánh" cho nhánh Via Divinitatis |
| Penitent(s) *(viapenaculum_adherent)* | Kẻ Sám Hối | đặt mới, dịch nghĩa "penitent" (người sám hối) |
| Crusader(s) *(viavindicta_adherent)* | Thập Tự Quân | ✅ tra base — "Crusade"/"Crusader" thường dịch "Thập Tự Chinh"/"Thập Tự Quân" trong văn cảnh trung cổ |
| Martyr(s) *(viadolorosa_adherent)* | Kẻ Tuẫn Đạo | đặt mới, "martyr" (người tử vì đạo) dịch "kẻ tuẫn đạo", nhất quán dùng lại cho `codeofsamiel_desc` ("the martyred founder"→"vị sáng lập tuẫn đạo") |
| Christian(s) *(viachristi_adherent)* | Tín Đồ Cơ Đốc | dịch nghĩa phổ thông |
| Code of Samiel | Luật Lệ Samiel | nhất quán mẫu "Code of X"→"Luật Lệ X" đã chốt B3k (`Code of Tremere`→"Luật Lệ Tremere") |
| Redeemer(s) *(vianoctis_adherent)* | Kẻ Cứu Chuộc | đặt mới, dịch nghĩa "redeemer" |
| Avenger(s) *(pathoftheheavenlyabode_adherent)* | Kẻ Báo Oán | đặt mới, dịch nghĩa "avenger" |
| Redeemed *(viaredemptio_adherent, tính từ dùng như danh từ)* | Kẻ Được Cứu Chuộc | phân biệt với "Redeemer" (Kẻ Cứu Chuộc) ở trên — "Redeemed" là thể bị động, dịch "Kẻ Được Cứu Chuộc" để tránh trùng nghĩa |
| Order of X *(12 holy order)* | Hội X | đặt mới, "Order"→"Hội" theo văn phong tổ chức tôn giáo POD, nhất quán với B3u (`Red Order`→"Hội Đỏ") |
| Path of Tears *(tên khác của Via Dolorosa)* | Con Đường Nước Mắt | dịch nghĩa, "Path"→"Con Đường" nhất quán B3f/B3k |
| Path of the Heavenly Abode | Con Đường Nơi Ở Thiên Đàng | dịch nghĩa đầy đủ tên faith con |
| Kindred *(viacaeli_desc, chỉ ma cà rồng nói chung)* | Huyết Tộc | ✅ đã chốt B3k (`rf_kindred`), áp dụng lại |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ áp dụng nhất quán theo B3e/B3g/B3h/B3k/B3s, kể cả `"Fortuna's"`→"của Fortuna" |

> ⚠️ Baseline trailing-whitespace: file gốc có 9 dòng với khoảng trắng thừa cuối dòng trước CRLF (dòng 1 `l_english: `, dòng 37-38 sau `"the Devil"`/`"the Devil's"`, và 6 dòng trống 64/100/106/118/138/144 với 1-4 space). Đã khôi phục đúng y hệt số lượng space ở từng dòng sau khi dịch — đây là bẫy "Formatter" (mục 6 TRANSLATION_RULES.md) suýt bị bỏ sót vì các công cụ đọc/ghi text mode thường tự động strip trailing whitespace.

## B3x. Thuật ngữ bổ sung (từ `POD_religion_roadofbeast`) — việc #2 file 22/36

Nguồn: `religion/POD_religion_roadofbeast_l_english.yml` (147 dòng, đã dịch xong 100%) — faith chính "Road of the Beast" (**Con Đường Dã Thú**, đã khóa cứng ở B3k) cho ma cà rồng Gangrel/hoang dã, cùng 9 faith con (Via Praedator, Via Erronis, Via Feritas, Via Venator Umbra, Via Liberatio, Einherjar, Yasaq, Path of the Noiad, Via Tantabus) và 1 faith yêu cầu riêng (Jötunns Väg). Chỉ có **một** `Glossary()` trong toàn file (`viayasaq_desc`, tham số 1 `'Anda'` — danh từ riêng đã có tiền lệ giữ nguyên ở B5/`traits_POD`, không dịch).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Road of the Beast / Via Bestiae *(faith chính)* | Con Đường Dã Thú | ✅ đã khóa cứng B3k, áp dụng ở `roadofbeast_religion`/`viabestiae` |
| Feral(s) *(tín đồ Con Đường Dã Thú nói chung)* | Dã Thú / Những Kẻ Dã Thú | đặt mới; số ít dùng "Dã Thú" (khớp tính từ `_adj`), số nhiều thêm "Những Kẻ" theo mẫu base (`game_concept_vassal`→"Chư hầu" số ít/nhiều gộp, nhưng ở đây cần phân biệt vì "Feral" vừa là danh từ vừa là tính từ) |
| Lorekeeper(s) *(chức sắc tôn giáo)* | Người Giữ Cổ Tích | đặt mới; "lore" (văn bản tôn giáo, `religious_text`) dịch "cổ tích" (kho tri thức truyền miệng cổ xưa), "Lorekeeper" ghép thành "Người Giữ Cổ Tích" |
| the Hunger *(devil_name + witchgodname_the_horned_god)* | Cơn Đói Khát | đặt mới; "Hunger" (cơn đói khát máu, khác "Rage"=Phẫn Nộ B3b) dịch nghĩa trực tiếp, không có tiền lệ base do khái niệm riêng WoD |
| Destruction *(death_deity_name)* | Hủy Diệt | dịch nghĩa thường, không có tiền lệ base đối lập cần tránh |
| wild(s) *(house_of_worship, divine_realm, positive_afterlife)* | hoang địa | đặt mới; nơi thờ tự/cõi giới của Con Đường Dã Thú là hoang dã, dịch "hoang địa" (đất hoang) để tránh lặp từ "Dã Thú" quá nhiều lần trong cùng nhóm key |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ theo tiền lệ POD đã dùng ở B3h/B3m/B3s (`roadoftheabyss`→"Con Đường Vực Thẳm") |
| Via Praedator / Hunter *(faith con)* | Via Praedator / Thợ Săn | tên faith giữ nguyên tiếng Latin, "Hunter" (tín đồ) dịch "Thợ Săn" — khác "Sentinel"→"Vệ Binh" (B3s), đây là nghĩa săn bắt trực tiếp |
| Via Erronis / Wanderer *(Path of the Nomad)* | Via Erronis / Kẻ Lang Thang | "Wanderer"→"Kẻ Lang Thang"; "Path of the Nomad" (tên khác trong mô tả) dịch "Con Đường Kẻ Du Mục" — hai từ tiếng Anh khác nhau (Wanderer/Nomad) cùng chỉ một nhóm, giữ 2 cách dịch riêng theo đúng ngữ cảnh gốc, không gộp |
| Via Feritas / Savage *(Path of the Savage)* | Via Feritas / Kẻ Man Dã | "Savage"→"Kẻ Man Dã" (khác "Kẻ Lang Thang", "Man Rợ") |
| Via Venator Umbra / Grey Hunter *(Path of the Grey Hunter)* | Via Venator Umbra / Thợ Săn Xám | tên Latin giữ nguyên, "Grey Hunter" dịch nghĩa |
| Via Liberatio / Liberator *(Furores — nhắc tới nhưng không phải tên faith)* | Via Liberatio / Kẻ Giải Phóng | "Furores" (tên khác/biệt danh, xuất hiện trong mô tả) giữ nguyên tiếng Latin theo B0, không có key riêng để dịch |
| Einherjar *(faith Bắc Âu)* | Einherjar *(giữ nguyên)* | ✅ đã chốt B3u (thuật ngữ Bắc Âu nguyên tác, chiến binh tử trận được Odin chọn) |
| All-Father | Đấng Toàn Phụ | đặt mới; danh hiệu Odin trong thần thoại Bắc Âu, dịch nghĩa Hán-Việt "Toàn Phụ" (cha của tất cả) theo văn phong trang trọng của base |
| Yasaq / Yasa / Anda *(faith Mông Cổ)* | Yasaq / Yasa / Anda *(giữ nguyên)* | "Anda" đã chốt giữ nguyên B5 (huyết thống Gangrel Mông Cổ, trùng tên `podgloss.anda`); "Yasaq"/"Yasa" là danh từ riêng luật tục Mông Cổ, giữ nguyên theo B0 |
| yasa *(warrior-brotherhoods, thường, khác tên faith)* | yasa (huynh đệ chiến binh) | giữ nguyên từ gốc kèm chú thích trong ngoặc như bản Anh, không viết hoa vì đây là danh từ chung trong câu |
| Barbarians *(cách người phương Tây gọi tín đồ Yasaq)* | Man Rợ | dịch nghĩa, phân biệt với "Savage"→"Kẻ Man Dã" (khái niệm khác — đây là góc nhìn bên ngoài gọi tên, không phải tên faith) |
| Path of the Noiad / Noiad(s) | Noiad *(giữ nguyên, số ít/nhiều gộp)* | danh từ riêng dân tộc/pháp sư Sámi, không có tiền lệ base; tên faith "Path of the Noiad" giữ nguyên tiếng Anh vì không có bản dịch tên riêng phù hợp (khác các "Path of X" khác vốn dịch nghĩa được) |
| Sámi | Sámi *(giữ nguyên)* | danh từ riêng dân tộc bản địa Bắc Âu, không dịch |
| guovssahas | guovssahas *(giữ nguyên)* | từ tiếng Sámi (cực quang), giữ nguyên như bản gốc, không có bản dịch |
| Embraced *(động từ thường, KHÁC `$pod_Embrace$`)* | được Trao truyền | ⚠️ bẫy: câu gốc `"...and Embraced exclusively from this population"` là động từ tiếng Anh thường, KHÔNG phải `$pod_Embrace$`. Dịch bằng thuật ngữ đã chốt B2 ("Trao truyền") nhưng viết thành chữ thường, KHÔNG được thay bằng `$pod_Embrace$` — làm vậy sẽ tạo thêm một `$ref$` không có trong bản gốc (vi phạm quy tắc không thêm string reference mới) |
| Baba Yaga / the Hag of Russia | Baba Yaga / Mụ Phù Thủy của nước Nga | "Baba Yaga" giữ nguyên tên riêng thần thoại Slav; "Hag"→"Mụ Phù Thủy" dịch nghĩa, mẫu possessive "của X" cho "of Russia"→"của nước Nga" |
| Grandmother *(biệt danh của Baba Yaga trong ngữ cảnh này)* | Grandmother *(giữ nguyên)* | giữ nguyên vì đứng như danh xưng riêng thay thế tên, dịch "Bà Ngoại"/"Bà Nội" sẽ mất sắc thái trang trọng-đáng sợ của bản gốc |
| Via Tantabus | Via Tantabus *(giữ nguyên)* | tên Latin faith con, giữ nguyên theo mẫu các "Via X" khác |
| Jötunn(s) / Jötunns Väg | Jötunn / Jötunns Väg *(giữ nguyên)* | danh từ riêng thần thoại Bắc Âu (người khổng lồ) và tên faith tiếng Thụy Điển cổ, giữ nguyên theo B0; `jotunnsvag_desc` dịch câu văn thường ("Con đường của Người Khổng Lồ") nhưng tên faith tự thân giữ nguyên |
| Giants *(cách gọi khác của Jötunn trong mô tả)* | Người Khổng Lồ | dịch nghĩa câu mô tả cuối `jotunnsvag_desc`, khác tên riêng "Jötunn" giữ nguyên ở trên — cùng khái niệm, hai cách viết do ngữ cảnh (tên riêng vs. danh từ chung) |
| Patron *(nhà tài trợ nội dung, không phải chức sắc tôn giáo)* | Patron *(giữ nguyên)* | thuật ngữ ngoài lề (ghi chú của nhà phát triển về nội dung theo yêu cầu người ủng hộ), không dịch vì không phải khái niệm World of Darkness |
| World of Darkness *(bare English trong `jotunnsvag_desc`, không phải qua `$pod_wod$`)* | Thế Giới Bóng Tối | ✅ đã chốt B2, áp dụng lại làm chữ thường trong câu văn — KHÔNG thay bằng `$pod_wod$` vì bản gốc không có string reference này, thêm vào sẽ vi phạm quy tắc không tạo `$ref$` mới |
| Anda *(param 1 của `Glossary('Anda','podgloss.anda')`)* | Anda *(giữ nguyên)* | ✅ xác nhận lại: tham số 1 của Glossary giữ nguyên "Anda" vì đây là danh từ riêng đã chốt giữ tiếng Anh (B5, trùng khớp nội dung `podgloss.anda` đã dịch sẵn ở `glossary_POD`), KHÔNG phải lỗi bỏ sót dịch tham số 1 |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ đã chốt B3h, áp dụng lại kèm possessive "của Fortuna" |
| Ennoia *(high_god_name_alternate)* | Ennoia *(giữ nguyên)* | danh từ riêng WoD (tên gốc của "the Beast" trong thần thoại Gangrel), theo B0 |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ áp dụng nhất quán theo B3e/B3g/B3h/B3k/B3s, kể cả các dòng viết `"blood's"`, `"Fortuna's"` chữ thường |
| Frenzy *(nhắc tới trong `viaferitas_desc`: "fits of rage" dịch bằng thuật ngữ Phẫn Cuồng đã chốt)* | Phẫn Cuồng | ✅ đã chốt B4d; câu gốc dùng "fits of rage" (cơn phát tác của Dã Thú) — dịch bằng "cơn Phẫn Cuồng" cho khớp thuật ngữ cơ chế WoD đã khóa, thay vì dịch "rage" trần thành "phẫn nộ" (vốn dành cho Garou, B3b) |
| holy_order_the_valkyrie *(Companions of the Valkyrie)* | Bạn Đồng Hành của Valkyrie | "Valkyrie" giữ nguyên tên riêng thần thoại Bắc Âu; "Companions"→"Bạn Đồng Hành", mẫu possessive "của X" |
| holy_order_scions_of_itugen *(The Scions of Itugen)* | Hậu Duệ của Itugen | "Itugen" giữ nguyên (địa mẫu thần Mông Cổ, đã có tiền lệ B3c dòng 377); "Scions"→"Hậu Duệ" |

## B5. Xung đột cần giải quyết trước khi dịch

| Từ POD | Vanilla đã chiếm | Hướng xử lý |
|---|---|---|
| **Clan** | `House` = "Gia tộc" | ✅ **Giữ nguyên `Clan`** — đã chốt |
| **Prince** (chức sắc Camarilla) | `Duke` = "Công tước", `King` = "Quốc vương" | ✅ **Giữ nguyên `Prince`** — dịch sẽ đụng tước vị phong kiến, mà nghĩa hoàn toàn khác |
| **Bloodline** | `Dynasty` = "Triều đại" | "Huyết thống" — không đụng, dịch được |
| **Discipline** | không xung đột | "Dị năng" |
| **Generation** | không xung đột | "Thế hệ" |
| **Beast** | không xung đột | "Dã Thú" |
| **Masquerade** | không xung đột | "Luật Che Giấu" |
| **Resonance** | không xung đột | "Cộng hưởng" |

---

## B4k. Thuật ngữ bổ sung (từ `POD_religion_roadofkings`) — việc #2 file 25/36

Nguồn: `religion/POD_religion_roadofkings_l_english.yml` (185 dòng, đã dịch xong 100%) — faith chính "Road of Kings" (Con Đường Quân Vương, đã khóa cứng B3k) và nhiều faith con "Via X" (nhóm Scion): Via Regalis, Via Equitum, Via Mercator, Via Tyrannus, Via Consuasor, Via Mithras, Via Entelechia, cộng thêm Codex of Legacies, Cleopatrans of Yima, Path of Carnal Desire, Via Officii, Shattered Spear, Path of Leviathan (nhóm Patron Content phi chính thống). File không có `Glossary()`/`UmbraGlossaryLocalized()` nào (bracket count = 0).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Road of Kings *(tên faith chính)* | Con Đường Quân Vương | ✅ đã khóa cứng B3k, áp dụng ở `roadofkings_religion` |
| Scion(s) *(religion_adj/adherent — tín đồ Road of Kings nói chung)* | Hậu Duệ | đặt mới; dùng "Hậu Duệ" (đã có tiền lệ ghép "Hậu Duệ Cain"=pod_cainite ở B2, nhưng ở đây là danh xưng ngắn gọn riêng của tín đồ Road of Kings, không phải viết tắt của Hậu Duệ Cain) — số ít/số nhiều gộp làm một theo mục 7 TRANSLATION_RULES.md |
| Power *(high_god_name, khái niệm trừu tượng tín đồ tôn thờ)* | Quyền Lực | dịch nghĩa danh từ trừu tượng, nhất quán xuyên suốt file (kể cả dạng thường "power"→"quyền lực") |
| Destruction *(death_deity_name)* | Hủy Diệt | dịch nghĩa thường |
| principle of faith | Nguyên Tắc Đức Tin | ✅ đã chốt trước ở `calomenasforsaken`/`bloodgnosticism` (B3q/B3r) — áp dụng lại cho toàn bộ 12 lần xuất hiện trong file này (`religious_head_title`, `devotee_*`, `priest_*`, `bishop*`) |
| Via Regalis / Via Equitum / Via Mercator / Via Tyrannus / Via Consuasor / Via Mithras / Via Entelechia *(tên Latin của 7 faith con nhóm Scion)* | *(giữ nguyên tiếng Latin)* | danh từ riêng Latin, theo B0 — chỉ dịch phần `_adherent`/`_desc` mô tả, không dịch tên hiển thị Latin |
| Luminary/Luminaries *(viaregalis_adherent)* | Đấng Sáng Soi | đặt mới; "Luminary" nghĩa đen "người soi sáng/gương mẫu", dịch theo tinh thần cai trị bằng gương mẫu của Via Regalis |
| Paladin(s) *(viaequitum_adherent — hiệp sỹ nhóm Road of Kings, KHÁC "Paladins of Chivalry"/"Paladins of Duty" holy order)* | Hiệp Sỹ Thánh | "Hiệp Sỹ" viết y theo A4 (giữ nguyên chính tả base); thêm "Thánh" để phân biệt với "Hiệp sỹ" vanilla (`game_concept_knight`) và nhấn mạnh sắc thái tôn giáo của danh xưng Scion |
| Path of Chivalry *(viaequitum_desc, tên khác của Via Equitum)* | Con Đường Hiệp Nghĩa | "Path"→"Con Đường" nhất quán B3f/B3k/B3s; "Chivalry" dịch "Hiệp Nghĩa" (tinh thần hiệp sỹ + nghĩa khí) |
| Merchant(s) *(viamercator_adherent)* | Thương Nhân | dịch nghĩa thường, không có tiền lệ base riêng |
| Path of the Merchant | Con Đường Thương Nhân | mẫu "Path"→"Con Đường" |
| Tyrant(s) *(viatyrannus_adherent)* | Bạo Chúa | dịch nghĩa; "Bạo Chúa" là từ Hán-Việt phổ thông cho "kẻ cai trị tàn bạo", không có tiền lệ base riêng |
| Path of the Tyrant | Con Đường Bạo Chúa | mẫu "Path"→"Con Đường" |
| Vizier(s) *(viaconsuasor_adherent, KHÁC "vizir" của `roadofblood`/B3s giữ nguyên tiếng Anh)* | Cố Vấn | ⚠️ chọn dịch nghĩa ở đây thay vì giữ nguyên "Vizier" như `roadofblood_bishop`="vizir" — vì ngữ cảnh khác nhau: ở `roadofblood` "vizir" là chức danh tôn giáo cụ thể của đạo Hồi/Ba Tư giữ nguyên theo B0, còn ở đây "Vizier" là danh xưng ẩn dụ chung ("người cố vấn quyền lực") của một nhóm Scion, dịch nghĩa hợp lý hơn giữ nguyên; không xem là vi phạm một-thuật-ngữ-một-bản-dịch vì đây là hai khái niệm khác nhau dùng chung gốc từ tiếng Anh |
| Path of the Vizier | Con Đường Cố Vấn | mẫu "Path"→"Con Đường" |
| Mithraism/Mithraist(s) *(viamithras_adj/adherent — giáo phái thờ thần Mithras)* | Giáo Phái Mithras / Tín Đồ Mithras | "Mithras" giữ nguyên tên thần La Mã cổ (danh từ riêng, không có tiền lệ base); "Giáo Phái"/"Tín Đồ" dịch nghĩa thường |
| Dedicated *(viaentelechia_adherent — tín đồ theo triết lý Entelechy Hy Lạp cổ)* | Kẻ Tận Hiến | đặt mới; "tận hiến" (hết lòng cống hiến) khớp tinh thần "Dedicated" trong bối cảnh triết học khắc kỷ/anh hùng |
| Entelechy *(khái niệm triết học Aristotle, trong `viaentelechia_desc`)* | Entelechy *(giữ nguyên)* | thuật ngữ triết học Hy Lạp cổ chuyên biệt, không có bản dịch tiếng Việt phổ thông tương xứng, giữ nguyên theo B0 |
| Codex of Legacies *(tên faith con)* | Codex of Legacies *(giữ nguyên tên hiển thị chính)* | tên riêng, không dịch dòng `codexoflegacies:` |
| Legacy Codex *(codexoflegacies_adj)* | Codex Di Sản | dịch "Legacy"→"Di Sản", giữ "Codex" nguyên theo mẫu Latin/tên riêng đã dùng trong file (Sargon Codex, B3s) |
| Dreamer(s) *(codexoflegacies_adherent)* | Kẻ Mộng Mơ | dịch nghĩa thường |
| Trinity *(codexoflegacies_desc — Tam Vị cai trị Constantinople gồm Toreador/Tzimisce/Ventrue, KHÁC "Triat" của Fera=Tam Vị B3)* | Tam Vị Nhất Thể | dùng cụm đầy đủ hơn "Tam Vị" (B3, dành riêng cho Fera Triat) để tránh trùng thuật ngữ hai khái niệm khác hẳn nhau |
| Quaesitor(s) *(codexoflegacies_desc)* | Quaesitor *(giữ nguyên, số ít/nhiều gộp)* | ✅ đã chốt B3u (`Quaesitori`), áp dụng lại dạng số ít |
| Scions of Caine/Enoch/Veddhartha/Tyranny/Mithras *(5 holy order mẫu "Scions of X")* | Hậu Duệ của Caine/Enoch/Veddhartha/Bạo Chúa/Mithras | ghép "Hậu Duệ" (đã đặt ở trên) + "của X" theo mẫu possessive chuẩn; "Veddhartha" giữ nguyên tên riêng (biến thể chính tả của "Veddartha" xuất hiện trong bản gốc, giữ đúng key gốc `veddhartha` không sửa) |
| Paladins of Chivalry/Duty *(2 holy order)* | Hiệp Sỹ Thánh của Hiệp Nghĩa / Hiệp Sỹ Thánh của Bổn Phận | ghép "Hiệp Sỹ Thánh" (đã đặt ở trên) + "của X" |
| The Condottieri *(holy_order — tên lính đánh thuê Ý thời Phục Hưng có thật)* | Condottieri *(giữ nguyên, bỏ mạo từ "The")* | danh từ riêng lịch sử Ý, theo mẫu base bỏ "The" khi dịch tên holy order (B3s); không có bản dịch tiếng Việt tương xứng |
| The Vizirs' Contingency | Kế Sách của Các Cố Vấn | "Vizirs"→"Cố Vấn" (nhất quán Vizier ở trên); "Contingency" dịch "Kế Sách" (phương án dự phòng/mưu lược), bỏ mạo từ "The" theo mẫu base |
| Lions of Mithras / Miles of Mithras | Sư Tử của Mithras / Chiến Binh của Mithras | "Lions" dịch nghĩa; "Miles" ở đây là từ Latin nghĩa "chiến binh/lính" (không phải đơn vị dặm Anh) — dịch "Chiến Binh" theo đúng nghĩa Latin gốc |
| Spears of Artemis Orthia | Ngọn Giáo của Artemis Orthia | "Artemis Orthia" giữ nguyên tên nữ thần Hy Lạp cổ (danh từ riêng); "Spears" dịch "Ngọn Giáo" |
| Cleopatrans of Yima *(tên faith)* | Tín Đồ Cleopatra của Yima | đặt mới; "Cleopatrans" (tín đồ giáo phái tôn thờ Cleopatra) dịch thành "Tín Đồ Cleopatra", giữ tên riêng "Cleopatra"/"Yima" |
| Non canon religion...commissioned by a Patron *(mẫu câu Patron Content, nhắc lại B3q)* | "Tôn giáo phi chính thống này được một Người Bảo Trợ đặt riêng." | ✅ đã chốt B3q, áp dụng lại cho path_of_carnal_desire/viaofficii/pathofleviathan |
| Desire/Desired *(path_of_carnal_desire_adj/adherent)* | Dục Vọng / Kẻ Được Khao Khát | "Desire"→"Dục Vọng" dịch nghĩa thường; "Desired" (bị động, "kẻ được ham muốn") dịch "Kẻ Được Khao Khát" để giữ sắc thái bị động khác với "Kẻ Khao Khát" (chủ động) |
| Order of Babylon / Order of Desire / Lure of Desire *(3 holy order Path of Carnal Desire)* | Hội Babylon / Hội Dục Vọng / Cám Dỗ của Dục Vọng | "Order"→"Hội" nhất quán B3u (Red Order→Hội Đỏ); "Babylon" giữ nguyên tên riêng; "Lure"→"Cám Dỗ" dịch nghĩa |
| Sworn *(viaofficii_adherent, adj — số ít/nhiều gộp)* | Kẻ Đã Thề | dịch nghĩa "người đã tuyên thệ", theo tinh thần "Silence of Blood"/"Masquerade" trong mô tả |
| Road of Duty *(tên khác của Via Officii)* | Con Đường Bổn Phận | mẫu "Road"→"Con Đường"; "Duty"→"Bổn Phận" nhất quán với "Paladins of Duty"→"...của Bổn Phận" ở trên |
| Silence of Blood | Sự Im Lặng của Máu | dịch nghĩa thường, cụm đặc trưng của Via Officii (tương đương khái niệm Masquerade) |
| Masquerade *(nhắc tới trong viaofficii_desc, KHÔNG phải key riêng)* | Màn Che | đặt mới; "Masquerade" (bí mật che giấu thân phận ma cà rồng trước phàm nhân) — dùng "Màn Che" ngắn gọn, tránh nhầm với "Mặt Nạ" nếu sau này gặp key khác |
| Carnal Desire *(tenet_carnal_desire_name)* | Dục Vọng Xác Thịt | dịch nghĩa đầy đủ hơn (khác "Desire" ngắn ở `path_of_carnal_desire_adj`) vì đây là tên giáo lý (tenet) đứng độc lập |
| Shattered Spear *(tên faith)* | Ngọn Giáo Gãy | dịch nghĩa; nhất quán "Spear"→"Ngọn Giáo" dùng trong cả `holy_order_spears_of_artemis_orthia` và `holy_order_teeth_of_the_leviathan`-adjacent |
| Spartan(s) *(shatteredspear_adherent)* | Người Sparta | dịch nghĩa, giữ tên riêng địa danh "Sparta" |
| childer *(thuật ngữ WoD chỉ "con cháu" ma cà rồng do một Sire Trao truyền, xuất hiện dạng thường trong `shatteredspear_desc`)* | childer *(giữ nguyên)* | thuật ngữ WoD nguyên tác không có bản dịch tiếng Việt tương xứng ngắn gọn, giữ nguyên theo B0 (tương tự Sire/Childe thường thấy giữ nguyên trong các bản dịch WoD khác) |
| civilized Cainite society *(cụm tính từ thường trong `shatteredspear_desc`, KHÔNG phải `$pod_cainite$` reference trong bản gốc)* | xã hội Hậu Duệ Cain văn minh | dịch "Cainite" bằng bản dịch đã chốt của `pod_cainite` (B2, "Hậu Duệ Cain") nhưng viết thành chữ thường/plain text — KHÔNG dùng `$pod_cainite$` vì bản gốc không có string reference ở vị trí này, chỉ là từ tiếng Anh trần; thêm token `$ref$` mới ở đây sẽ vi phạm quy tắc bảo toàn tập hợp `$ref$` |
| Path of Leviathan *(tên faith)* | Con Đường Leviathan | mẫu "Path"→"Con Đường"; "Leviathan" giữ nguyên tên quái vật biển trong Kinh Thánh, không có bản dịch tiếng Việt phổ thông tương xứng |
| Mind *(pathofleviathan_religious_head_title)* | Tâm Trí | dịch nghĩa thường, phù hợp ẩn dụ "cơ thể tập thể" của Leviathan |
| Will of Leviathan | Ý Chí của Leviathan | dịch nghĩa + possessive "của X" |
| Body of the Leviathan *(devotee)* | Thân Thể của Leviathan | dịch nghĩa, tiếp nối ẩn dụ cơ thể tập thể (Mind/Body) |
| Blood Lord(s)/Lady/Ladies of the Leviathan *(priest)* | Chúa Huyết / Nữ Chúa Huyết của Leviathan | "Lord"→"Chúa" (tránh trùng "Lãnh chúa"=Liege của A4), ghép "Huyết" (Blood) làm tính từ, nhất quán mẫu "Danh từ riêng Việt + Latin/tên riêng" |
| Blood Ministers of the Leviathan *(priest_alternate_plural — bản gốc viết sai chính tả "Minsiters")* | Các Bộ Trưởng Huyết của Leviathan | sửa lỗi đánh máy "Minsiters"→hiểu là "Ministers" khi dịch sang tiếng Việt (bản dịch tiếng Việt không mang theo lỗi chính tả tiếng Anh vì không phải danh từ riêng thuộc diện phải giữ nguyên lỗi theo mục 6 quy tắc lỗi chính tả — lỗi đó chỉ áp dụng cho tên riêng/dấu tiếng Việt, không áp dụng cho lỗi gõ phím tiếng Anh thường) |
| Marrow Lord(s)/Lady/Ladies of the Leviathan *(bishop)* | Chúa Tủy / Nữ Chúa Tủy của Leviathan | "Marrow"→"Tủy" (tủy xương, cấp bậc cao hơn "Blood" trong hệ thống cấp bậc cơ thể ẩn dụ) |
| Teeth of Leviathan *(holy_order)* | Răng Nanh của Leviathan | "Teeth"→"Răng Nanh" (nhấn mạnh sắc thái nguy hiểm/chiến binh hơn "Răng" trơn) |
| Council of Rulers/Reconciliation/Executioners *(3 holy order)* | Hội Đồng Các Nhà Cai Trị / Hội Đồng Hòa Giải / Hội Đồng Đao Phủ | "Council"→"Hội Đồng" (✅ tra base `game_concept_council`="Nội các" không phù hợp ngữ cảnh non-vanilla này, dùng "Hội Đồng" phổ thông hơn theo tiền lệ B3u "Viện Nguyên Lão"); "Executioners"→"Đao Phủ" dịch nghĩa Hán-Việt phổ thông |

---

## B3z. Thuật ngữ bổ sung (từ `POD_religion_roadofhumanity`) — việc #2 file 24/36

Nguồn: `religion/POD_religion_roadofhumanity_l_english.yml` (130 dòng, đã dịch xong 100%) — faith chính "Road of Humanity" (Con Đường Nhân Tính, đã khóa cứng B3k) và các faith con nhóm "Prodigal" (Via Humanitatis/Anima/Communitas/Luminis/Vireo), cùng 3 tổ chức không phải "Via X" (Eternal Senate, Inconnu, Children of Osiris, Amaranthans). Chỉ có **một** `Glossary()` trong toàn file (`inconnu_desc`, tham số 1 `'Antediluvians'` giữ nguyên theo B0/B2b). Không có `UmbraGlossaryLocalized()`. File có 8 dòng trailing-whitespace-trước-CRLF ở bản gốc (dòng 1, 37, 38, và 5 dòng trống 93/99/105/119/125 chứa 1-3 khoảng trắng) — đã khôi phục đúng y hệt.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Road of Humanity *(roadofhumanity_religion)* | Con Đường Nhân Tính | ✅ đã khóa cứng B3k, áp dụng ở đây |
| principle of faith *(religious_head_title/_name/devotee/priest, số ít/nhiều gộp)* | Nguyên Tắc Đức Tin | ✅ đã chốt B3m, áp dụng đúng như yêu cầu — xuất hiện **11 lần** trong file này (`religious_head_title`, `religious_head_title_name`, `devotee_male/_male_plural/_female/_female_plural/_neuter/_neuter_plural`, `priest_male/_male_plural/_alternate_plural`), tất cả đều dịch thành "Nguyên Tắc Đức Tin" |
| the Blood *(high_god_name_alternate)* | Dòng Máu | đặt mới; phân biệt "Nhân Tính" (high_god_name chính) với biến thể "the Blood" — dùng "Dòng Máu" (không phải "Máu" trơn) vì đây là danh xưng thay thế cho một vị thần trừu tượng, cần trang trọng hơn "máu" thường (dùng cho `health_god_name`) |
| the Beast *(devil_name/witchgodname_the_horned_god)* | Dã Thú | ✅ đã chốt B5/B3n/B3s, áp dụng lại cho cả `devil_name` và `witchgodname_the_horned_god` + possessive |
| Destruction *(death_deity_name)* | Hủy Diệt | ✅ nhất quán với B3m/B3n/B3p/B3q (cùng key `death_deity_name`) |
| refuge(s) *(house_of_worship)* | nơi ẩn náu / những nơi ẩn náu | đặt mới; khác "chốn nương thân" (roadofbones, và dùng lại ở roadofmetamorphosis) dù nghĩa gần nhau — chọn từ khác để tránh lặp y hệt giữa các faith riêng biệt, vẫn cùng trường nghĩa "nơi trú ẩn" |
| rose *(religious_symbol)* | hoa hồng | ✅ tiền lệ POD đã dùng cho `raktasadhus_religious_symbol` (B3r) — cùng giá trị tiếng Anh, dùng lại bản dịch giống hệt |
| scriptures *(religious_text)* | kinh sách | đặt mới; danh từ tôn giáo phổ thông, chưa có tiền lệ base trực tiếp cho dạng số nhiều này (base có "kinh thánh" cho Ignorance B3j, ở đây dùng "kinh sách" để tránh trùng khái niệm Ki-tô giáo cụ thể) |
| heaven *(divine_realm/positive_afterlife)* | thiên đàng | ✅ tiền lệ base (`christianity_positive_afterlife`="thiên đàng"), áp dụng theo B3m |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ đã chốt B3h/B3m/B3n, áp dụng lại |
| blood *(health_god_name/water_god_name, danh từ thường)* | máu | ✅ nhất quán mẫu B3g/B3n (danh từ thường làm tên thần → chữ thường thuần Việt) |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ đã chốt B3h, áp dụng lại kèm possessive "của Fortuna" |
| bishop(s) *(bishop/bishop_plural, chức sắc thường — KHÁC "principle of faith")* | giám mục | ✅ tiền lệ base (`christianity_bishop`="giám mục"), số ít/nhiều gộp |
| Prodigal(s) *(religion_adherent, ám chỉ ẩn dụ Kinh Thánh "Đứa Con Hoang Đàng" — ma cà rồng lạc lối tìm đường quay về nhân tính)* | Kẻ Hoang Đàng / Những Kẻ Hoang Đàng | đặt mới; dịch theo tinh thần ẩn dụ gốc (Prodigal Son = "đứa con hoang đàng", cách dịch Kinh Thánh phổ biến trong tiếng Việt — xác nhận qua `base_game_vh` dùng "đứa con hoang" cho khái niệm con rơi/con hoang tương tự), rút gọn thành danh xưng "Kẻ Hoang Đàng" cho vừa UI |
| Via Humanitatis, Via Anima, Via Communitas, Via Luminis, Via Vireo *(tên 5 faith con, tiếng Latin)* | *(giữ nguyên)* | tên Latin riêng của faith, theo B0/mẫu Via Servilis/Via Ossium — chỉ dịch phần mô tả "commonly called the Path of X" thành "Con Đường X", không đổi tên hiển thị chính |
| Path of Breath / Community / Illumination / Vigor *(tên mô tả "commonly called the Path of X" trong _desc, KHÁC tên hiển thị chính "Via X")* | Con Đường Hơi Thở / Con Đường Cộng Đồng / Con Đường Khai Sáng / Con Đường Sức Sống | dịch nghĩa theo mẫu "Road/Path"→"Con Đường" đã chốt B3f/B3k/B3q, áp dụng cho phần văn xuôi mô tả (không phải key tên faith) |
| Inspired *(viaanima_adherent)* | Kẻ Được Truyền Cảm Hứng | dịch nghĩa; "inspired" đã có tiền lệ dùng làm khái niệm khác trong base (`[inspired\|E]` = trạng thái "Cảm Hứng" của nhân vật), nhưng ở đây là danh xưng tín đồ riêng của POD nên dịch cụm đầy đủ để tránh lẫn với concept-link vanilla |
| Civilised *(viacommunitas_adherent)* | Kẻ Khai Hóa | đặt mới; "văn minh hóa" rút gọn thành "Khai Hóa" cho vừa danh xưng ngắn |
| Illuminated *(vialuminis_adherent)* | Kẻ Được Khai Sáng | đặt mới, nhất quán "Illumination"→"Khai Sáng" |
| Rover(s) *(viavireo_adherent)* | Kẻ Lang Bạt / Những Kẻ Lang Bạt | đặt mới; "lang bạt" (phiêu du, không cố định) phù hợp tinh thần "Path of Vigor" (di chuyển, mở rộng chân trời) |
| Golconda *(concept link `[golconda\|E]`)* | Golconda *(giữ nguyên — key, không đổi)* | ✅ đã chốt B4i, key concept-link không dịch theo quy tắc chung |
| Golconda Seeker(s) *(holy_order_seekers_of_golconda)* | Kẻ Tầm Golconda | ✅ đã chốt B4i, áp dụng lại nguyên văn |
| Salubri *(nhắc tới trong `vialuminis_desc`)* | Salubri *(giữ nguyên)* | tên clan ma cà rồng, danh từ riêng theo B0 (danh sách clan) |
| Eternal Senate *(tên tổ chức, giữ nguyên tiếng Anh theo bản gốc)* | Eternal Senate *(giữ nguyên)* | tên tổ chức WoD gốc (Thượng Nghị Viện Ventrue cổ đại Rome), không dịch vì không có tiền lệ base và giữ đúng bản sắc tên riêng lịch sử giả tưởng |
| Senator(s) *(eternalsenate_adherent, số ít=số nhiều trong bản gốc)* | Nghị Sĩ | dịch nghĩa thông thường, không có tiền lệ base riêng cho "Senator" nhưng "Nghị Sĩ" là từ Hán-Việt phổ thông |
| methuselah(s) *(nhắc tới trong `inconnu_desc`, KHÁC tên riêng viết hoa)* | methuselah *(giữ nguyên, chữ thường theo bản gốc)* | thuật ngữ WoD chỉ ma cà rồng cực kỳ cổ xưa, không có tiền lệ base; giữ nguyên tiếng Anh theo B0 vì là thuật ngữ chuyên môn phổ biến trong cộng đồng WoD |
| Jyhad *(nhắc tới trong `inconnu_desc`)* | Jyhad *(giữ nguyên)* | thuật ngữ riêng WoD (cuộc chiến ngầm giữa các Antediluvian), danh từ riêng theo B0 |
| Camarilla, Sabbat *(nhắc tới trong `inconnu_desc`)* | Camarilla, Sabbat *(giữ nguyên)* | ✅ đã chốt B3k, danh từ riêng tổ chức WoD |
| Antediluvian(s) *(tham số 1 của `Glossary('Antediluvians','game_concept_antediluvian_desc')`)* | Antediluvian *(giữ nguyên, kể cả dạng số nhiều)* | ✅ đã chốt B0/B2b — giữ nguyên tiếng Anh dù là tham số 1 dịch được của `Glossary()`, vì đây là thuật ngữ riêng đã khóa "giữ nguyên tiếng Anh" ở mọi nơi khác trong repo (giống "Wan Kuei") |
| holy_order_order_of_prodigals *(Order of Prodigals)* | Hội Dòng Kẻ Hoang Đàng | ghép "Hội Dòng" (mẫu holy_order tổ chức tôn giáo, đặt mới) + "Kẻ Hoang Đàng" đã chốt ở trên |
| holy_order_order_of_anima *(The Anima Order)* | Giáo Đoàn Anima | "Anima" giữ nguyên tên faith con, "Order"→"Giáo Đoàn" (khác "Hội Dòng" ở trên để tránh lặp từ giữa các holy order liền kề trong cùng file) |
| holy_order_order_of_commumnitas *(Community of Warriors — lưu ý key gốc viết sai chính tả "commumnitas", giữ nguyên key)* | Cộng Đồng Chiến Binh | dịch nghĩa trực tiếp "Community of Warriors"; **giữ nguyên lỗi chính tả trong tên key** theo quy tắc 6 (WORKLIST.md) — chỉ sửa chữ hiển thị, không sửa key |
| holy_order_order_of_illuminated *(Order of Illumination)* | Hội Dòng Khai Sáng | nhất quán "Illumination"→"Khai Sáng" |
| holy_order_order_of_rovers *(Rovers of War)* | Những Kẻ Lang Bạt Chiến Tranh | dịch nghĩa, nhất quán "Rover"→"Kẻ Lang Bạt" |
| holy_order_legio_mortuum *(Legio Mortuum, tiếng Latin — "Đội Quân Tử Thần")* | Legio Mortuum *(giữ nguyên)* | tên Latin riêng của tổ chức Giovanni/Cappadocian, theo B0, không dịch nghĩa vì đã là danh xưng cố định trong nguyên tác |
| holy_order_phalanx_of_entelechia / _heracleitus / _praedicanda *(Phalanx of X, tên Hy Lạp/Latin)* | Phalanx của Entelechia / Heracleitus / Praedicanda | "Phalanx" giữ nguyên (đội hình quân sự Hy Lạp cổ, không có tiền lệ base), tên riêng giữ nguyên, ghép possessive "của X" |
| holy_order_monitors *(Monitors)* | Những Người Giám Sát | dịch nghĩa thông thường |
| holy_order_ignoti *(Ignoti, tiếng Latin — "những kẻ vô danh")* | Ignoti *(giữ nguyên)* | tên Latin riêng tổ chức, theo B0 |
| holy_order_the_unknown *(The Unknown)* | Kẻ Vô Danh | dịch nghĩa; khác "Ignoti" (giữ nguyên Latin) dù nghĩa gần nhau — hai tên tổ chức khác nhau trong cùng bản gốc, không gộp |
| Children of Osiris *(childofosiris)* | Con Cái Osiris | ✅ đã chốt B2b, áp dụng lại nguyên văn cho toàn bộ key hiển thị tên faith trong file này |
| Osirian *(childofosiris_adj/_adherent, số ít/nhiều gộp)* | Người Osiris | đặt mới; "Osirian" (tín đồ Osiris) dịch "Người Osiris" thay vì phiên âm "Osiris-ian", nhất quán tên thần "Osiris" giữ nguyên |
| Egyptian folklore *(childofosiris_desc)* | truyền thuyết Ai Cập | dịch nghĩa thông thường |
| Setites *(childofosiris_desc, nhắc tới clan đối địch)* | người Setite | ✅ tên clan "Setite" giữ nguyên theo B0 (danh sách clan), ghép "người" cho tự nhiên trong câu văn xuôi |
| "darkness" / "light" *(childofosiris_desc, dấu ngoặc kép lồng KHÔNG escape trong bản gốc)* | "bóng tối" / "ánh sáng" | ⚠️ **giữ nguyên lỗi cú pháp gốc** — bản gốc dùng `"darkness"`/`"light"` với dấu `"` lồng nhau không escape bằng `\"` (khác các file khác dùng `#weak \"...\"#!`). Không tự ý thêm `\` để "sửa" vì sẽ đổi tổng số ký tự `"` thô của file — chỉ dịch chữ bên trong, giữ đúng kiểu dấu ngoặc kép y hệt bản gốc |
| Amaranthans *(tên tổ chức, giữ nguyên theo bản gốc)* | Amaranthans *(giữ nguyên)* | tên riêng nhóm săn kẻ phạm tội diablerie, không có tiền lệ base, giữ nguyên tiếng Anh theo B0 |
| Amaranthan *(amaranthans_adherent, số ít)* | Amaranthan *(giữ nguyên)* | đồng dạng số ít của tên tổ chức ở trên |
| diablerists *(amaranthans_desc, danh từ thường — KHÁC `$pod_diablerie$` là ref)* | kẻ phạm tội diablerie | đặt mới; "diablerie" giữ nguyên theo B2 (`pod_diablerie`), "-ist" (người làm hành vi đó) dịch thành cụm mô tả "kẻ phạm tội diablerie" vì tiếng Việt không có hậu tố tương đương trực tiếp |

---

## Cách thêm mục mới

Khi gặp thuật ngữ chưa có ở đây:

1. Tra `base_game_vh` bằng **key tiếng Anh** — nếu có, dùng đúng bản đó, thêm vào Phần A.
2. Nếu không có, tìm khái niệm vanilla tương đương về văn phong.
3. Nếu vẫn không, đặt từ mới theo giọng của `base_game_vh` → thêm vào Phần B **ngay lập tức**, kèm key nguồn.
4. Không bao giờ để một thuật ngữ có hai bản dịch trong repo.

## B4l. Thuật ngữ bổ sung (từ `POD_religion_roadofmetamorphosis`) — việc #2 file 26/36

Nguồn: `religion/POD_religion_roadofmetamorphosis_l_english.yml` (125 dòng, đã dịch xong 100%). Faith chính "Road of Metamorphosis" (đã khóa cứng B3f/B3k = "Con Đường Biến Hóa") và 6 faith con: Via Mutationis, Path of the Flesh, Path of the Spirit, Via Apotheosis (phi chính thống, Patron-commissioned), Path of Asakku (phi chính thống), Path of Stars. Không có `Glossary()`/`UmbraGlossaryLocalized()` nào trong file (bracket count = 0) — không có bẫy tham số Glossary ở file này.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Metamorphosism / Metamorphosist(s) *(religion_adj và các biến thể devotee/priest/bishop/koldun)* | Biến Hóa Luận / kẻ theo Biến Hóa Luận | đặt mới, ghép hậu tố "-Luận" nhất quán với các "-ism" tôn giáo khác trong POD (so `Blood Gnosticism`→"Huyết Ngộ Đạo Luận", B3f) |
| Seeker(s) *(religion_adherent chính của Road of Metamorphosis, khác "Golconda Seeker" đã chốt B4i)* | Kẻ Tầm Đạo | đặt mới; không dùng lại "Kẻ Tầm Golconda" vì đó là cụm ghép riêng cho ngữ cảnh Golconda — ở đây "Seeker" đứng một mình chỉ tín đồ đi tìm tri thức nói chung |
| Flesh *(high_god_name)* | Thân Xác | đặt mới; "Flesh" là danh xưng thần của tôn giáo này (đối tượng thờ phụng, không phải "flesh" nghĩa đen mô tả Vicissitude) |
| The Flesh *(high_god_name_alternate)* | Cái Thân Xác | biến thể có mạo từ, theo mẫu base xử lý alternate god name (thêm "Cái" như định ngữ nhấn mạnh) |
| The Eldest *(good_god_eldest)* | Kẻ Trưởng Lão Nhất | đặt mới, dịch nghĩa "the eldest" theo giọng trang trọng cổ |
| Destruction *(death_deity_name)* | Hủy Diệt | đặt mới, dịch nghĩa thông thường |
| refuge(s) *(house_of_worship)* | chốn nương thân | ✅ tiền lệ POD đã dùng cùng cụm này ở B3n (`roadofbones_house_of_worship`) cho cùng khái niệm nơi thờ tự ẩn dật của ma cà rồng nghiên cứu/độc cư |
| Master Metamorphosist *(religious_head_title)* | Đại Sư Biến Hóa | đặt mới, "Master"→"Đại Sư" (ghép với "Biến Hóa" thay vì lặp "Biến Hóa Luận" cho gọn chức danh) |
| master seeker *(priest_alternate_plural)* | bậc thầy tầm đạo | đặt mới, ghép "bậc thầy" + "tầm đạo" (từ Kẻ Tầm Đạo) |
| Macrolepidoptera *(religious_symbol, tên khoa học nhóm bướm/ngài lớn)* | Macrolepidoptera *(giữ nguyên)* | thuật ngữ phân loại sinh học Latin, không dịch, theo B0 |
| tomes of flesh *(religious_text)* | những cuốn sách về da thịt | dịch nghĩa |
| Via Apotheosis, Via Mutationis *(tên faith con Latin)* | Via Apotheosis, Via Mutationis *(giữ nguyên)* | tên Latin riêng, theo mẫu các "Via X" khác đã giữ nguyên (Via Servilis, Via Set — B3o/B3q) |
| Apotheosist(s) *(viaapotheosis_adj/adherent)* | Kẻ theo Apotheosis | "Apotheosis" giữ nguyên (danh từ riêng khái niệm thần thánh hóa gốc Hy Lạp không có bản dịch tự nhiên gọn), ghép "Kẻ theo" như các faith khác |
| God-King *(viaapotheosis_religious_head_title)* | Thần-Vương | đặt mới, ghép "Thần" + "Vương" bằng gạch nối theo đúng cấu trúc ghép của bản gốc "God-King" |
| lector(s) / archlector(s) *(viaapotheosis priest/bishop)* | giảng sư / đại giảng sư | đặt mới; "lector" (người đọc kinh/giảng dạy) dịch "giảng sư", "archlector" thêm tiền tố "đại" theo mẫu cấp bậc tôn giáo khác trong POD (vd. Arhat/Đại La Hán, B3c) |
| novice(s) *(viaapotheosis_devotee)* | tân đồ | ✅ tra base, "novice" thường dịch "tân đồ"/"người mới" trong ngữ cảnh tôn giáo; chọn "tân đồ" cho gọn và trang trọng |
| Path of Asakku *(pathofasakku, phi chính thống)* | Con Đường Asakku | "Asakku" là danh từ riêng (linh hồn ác quỷ Lưỡng Hà cổ chiếm hữu Dragastes), giữ nguyên; "Path of X"→"Con Đường X" theo mẫu B3f/B3k |
| Corrupted *(pathofasakku_adj/adherent)* | Kẻ Bị Tha Hóa | đặt mới, dịch nghĩa "corrupted" (bị tha hóa/hủ hóa) — dùng "Tha Hóa" thay vì "Ô Uế" (đã dùng riêng cho Wyrm Corruption, B3b) để tránh trùng thuật ngữ giữa hai splat khác nhau (ma cà rồng vs Fera) |
| Watcher(s) *(pathofasakku_desc — linh hồn/thực thể bí ẩn khống chế Asakku)* | Watcher *(giữ nguyên)* | danh từ riêng WoD chưa xác định rõ gốc (có thể liên hệ tới các thực thể "Watcher" trong thần thoại Enoch/Nephilim đã có ở B4h), tạm giữ nguyên tiếng Anh theo B0 vì không đủ ngữ cảnh để định nghĩa lại |
| Hierophant *(pathofasakku_desc, chức sắc giáo phái Asakku)* | Hierophant *(giữ nguyên)* | danh từ riêng chức sắc Hy Lạp cổ (tư tế cấp cao Eleusinian Mysteries), không có bản dịch tự nhiên ngắn gọn, giữ nguyên theo B0 |
| Path of Stars *(pathofstars, biến dị của Road of Metamorphosis)* | Con Đường Vì Sao | đặt mới, dịch nghĩa "stars"→"Vì Sao"; theo mẫu "Path of X"→"Con Đường X" |
| suffering *(pathofstars_desc, khái niệm triết lý trừu tượng)* | đau khổ | dịch nghĩa phổ thông |

## B4m. Thuật ngữ bổ sung (từ `POD_religion_roadofsin`) — việc #2 file 27/36

Nguồn: `religion/POD_religion_roadofsin_l_english.yml` (186 dòng, đã dịch xong 100%). Faith chính "Road of Sin" (đã khóa cứng B3k = "Con Đường Tội Lỗi", `roadofsin_hostility_doctrine_name`) và 13 faith con/tổ chức: Via Peccati, Via Voluptarius, Via Crudelitas, Via Adversarius, Via Diabolis, Via Prometheus (Firebringers), Via Furores, Via Quiritare, Path of the Eightfold Wheel (Druid, Celtic), Via Deorum Vigilans (Vaticinator), Via Hyron (Abelene, Baali/Order of Moloch), Via Tártaros (phi chính thống), Deimosianism, Servitors of Irad, Baobhan Sith (phi chính thống), Path of Tevoro (phi chính thống), Blood Tribe (Anarch). 2 lần `Glossary()`: `[Glossary('Sire','game_concept_Sire_desc')]` (2 lần trong `viahyron_desc`) và `[Glossary('Antediluvians','game_concept_antediluvian_desc')]` (1 lần trong `servitorsofirad_desc`) — cả hai tham số 1 giữ nguyên tiếng Anh (xem ghi chú "Sire" dưới). 1 lần `[GetTrait('bushi').GetName(GetNullCharacter)]` trong `bloodtribe_desc` — `trait_bushi` đã dịch là "Bushi" (giữ nguyên tiếng Anh) ở `traits_POD_l_english.yml:235`, không có bare-mention nào khác của Bushi trong file cần đồng bộ.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Road of Sin *(roadofsin_religion)* | Con Đường Tội Lỗi | ✅ đã khóa cứng B3k, áp dụng ở đây lần đầu cho file riêng |
| Sinner(s) *(religion_adj/adherent/devotee/priest, số ít/nhiều gộp một theo mục 7 TRANSLATION_RULES.md)* | Tội Nhân (danh xưng/tên gọi) / tội nhân (chức sắc thường, viết thường) | đặt mới; viết hoa khi là tên gọi tín đồ chính (`religion_adherent`), viết thường khi là chức sắc lặp lại nhiều lần (`devotee_*`, `priest_*`) theo mẫu base phân biệt danh xưng và chức sắc |
| Sin *(high_god_name, danh từ trừu tượng được thờ)* | Tội Lỗi | đặt mới, viết hoa vì là tên vị thần trừu tượng |
| The Adversary *(devil_name/witchgodname_the_horned_god)* | Kẻ Nghịch Thù | đặt mới; khác "Quỷ Dữ" đã dùng cho witchgodname khác ở B3k — mỗi witchgodname một tên riêng theo tiền lệ base |
| Destruction *(death_deity_name)* | Hủy Diệt | dịch nghĩa thông thường, nhất quán với cách dùng ở B4l (`roadofmetamorphosis_death_deity_name` cùng giá trị gốc) |
| den(s) *(house_of_worship)* | sào huyệt | đặt mới; phù hợp giọng văn tội lỗi/ẩn nấp của faith này, khác "chốn nương thân" (B4l, faith ẩn dật/nghiên cứu) |
| eternity *(divine_realm/positive_afterlife)* | vĩnh hằng | dịch nghĩa phổ thông |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ đã chốt B3h/B3m/B3s/B3t/B3v/B3r, áp dụng lại |
| Firebringer(s) *(tên khác của Via Prometheus/Promethean)* | Kẻ Mang Lửa | đặt mới, dịch nghĩa |
| Kine *(danh từ WoD chỉ phàm nhân dưới góc nhìn ma cà rồng, xuất hiện trong `viaprometheus_desc`)* | Kine *(giữ nguyên)* | đặt mới theo B0 — từ cổ/phương ngữ tiếng Anh (số nhiều cổ của "cow"), dùng làm biệt ngữ WoD chỉ loài người; chưa có bản dịch nào trong toàn mod (từ này xuất hiện untranslated ở nhiều file `religion/`, `buildings/`, `event_localization/` chưa dịch) — giữ nguyên để nhất quán khi các file đó tới lượt dịch |
| High Clans *(viaprometheus_desc, nhóm clan quyền lực Camarilla)* | Clan Thượng Đẳng | đặt mới; "Clan" giữ nguyên theo B0/B2, "High"→"Thượng Đẳng" theo giọng phân cấp trang trọng |
| Sire *(chức danh "cha/mẹ" ma cà rồng tạo ra childe, param 1 của `Glossary('Sire','game_concept_Sire_desc')`)* | Sire *(giữ nguyên, CHƯA dịch)* | ⚠️ quyết định có ý thức: `game_concept_Sire`/`game_concept_Sire_desc` (nơi định nghĩa gốc) vẫn còn là tiếng Anh "Sire" chưa dịch (`game_POD_concepts_l_english.yml`, chưa tới lượt trong WORKLIST). ⚠️ **ĐÍNH CHÍNH (2026-07-27):** một agent từng báo cáo nhầm rằng `religion/POD_religion_docrtineandtenets_l_english.yml` "đã hoàn tất 100%" và dùng nó làm tiền lệ — đã kiểm tra lại, **file đó vẫn 100% tiếng Anh, CHƯA dịch dòng nào** (nằm trong danh sách 10 file còn lại của việc #2, xem mục "Tình hình" phía trên). Cùng cụm `Glossary('Sire',...)` xuất hiện y nguyên tiếng Anh ở dòng 123/636/682 của file đó — không phải bản dịch, chỉ là bản gốc. Giữ nguyên "Sire" ở đây (`roadofsin`) là quyết định đúng nhưng **không dựa trên tiền lệ đã dịch nào cả**, chỉ đơn thuần vì `game_concept_Sire` gốc chưa có bản Việt để tham chiếu; **khi `game_POD_concepts_l_english.yml` được dịch và chốt bản Việt cho "Sire", phải quay lại sửa mọi file religion/ đã dùng "Sire" giữ nguyên, gồm cả `docrtineandtenets` khi tới lượt nó**. Ghép cặp với "childe/childer" cũng đang được giữ nguyên tiếng Anh trong `traits_POD_l_english.yml` (dòng 79, 178, 206) — cùng lý do cặp thuật ngữ đi liền nhau. **Bài học: một agent tự nhận file X "đã hoàn tất" không phải bằng chứng — luôn tự grep nội dung thật của file đó để xác nhận trước khi tin.** |
| Antediluvian(s) *(param 1 của `Glossary('Antediluvians',...)`)* | Antediluvian *(giữ nguyên)* | ✅ đã chốt B0/B2b, áp dụng lại (số nhiều gộp về cùng dạng giữ nguyên) |
| Great Works *(viahyron_desc)* | Đại Công Trình | đặt mới, dịch nghĩa trang trọng |
| Swarm *(viahyron_desc, thực thể Wyrm bên trong Baali)* | Bầy Đàn | ✅ đã chốt B3l (`Swarm of Samael`→"Bầy Đàn Samael"), áp dụng lại cho từ đứng một mình |
| Outer Darkness *(viahyron_desc)* | Bóng Tối Ngoại Vực | đặt mới, dịch nghĩa "Outer"→"Ngoại Vực" (ngoài rìa) + "Darkness"→"Bóng Tối" |
| Order of Moloch *(viahyron_desc, tổ chức Baali)* | Order of Moloch *(giữ nguyên)* | ✅ đã chốt B3x, áp dụng lại |
| non canon religion...commissioned by a Patron *(mẫu câu Patron Content, lặp lại ở `viatartaros_desc`/`baobhansith_desc`/`pathoftevoro_desc`)* | "Tôn giáo phi chính thống này được một Người Bảo Trợ đặt riêng." | ✅ đã chốt B3m, áp dụng lại nguyên câu |
| Internalists *(viatartaros_desc, triết phái nội tại luận hư cấu)* | người theo nội tại luận | đặt mới, dịch nghĩa theo hậu tố "-luận" nhất quán các trường phái triết học khác trong POD |
| The Sinful, Order of Pustula, Brothers of the Black Mountain, Legio Peccati, Order of the Most Exquisite Aconia, The Voluptuaries, Daughters of Venus, The Heartless, The Adversaries, The Firebringers, The Outlaws, The Screamers, Order of Abelene, Order of Ibilis, Cult of Augurs, Order of Vaticinators, Ancient Order of Druids, Order of the Morrigan, Order of Tartaros *(18 `holy_order_*` của roadofsin)* | Những Kẻ Tội Lỗi / Order of Pustula / Huynh Đệ Núi Đen / Legio Peccati / Order of the Most Exquisite Aconia / Những Kẻ Truy Hoan / Con Gái của Venus / Những Kẻ Vô Tâm / Những Kẻ Nghịch Thù / Những Kẻ Mang Lửa / Những Kẻ Ngoài Vòng Pháp Luật / Những Kẻ Gào Thét / Order of Abelene / Order of Ibilis / Giáo Phái Augur / Order of Vaticinators / Cổ Hội Druid / Order of the Morrigan / Order of Tartaros | Tên "The X" mô tả thường (số nhiều danh từ tiếng Anh phổ thông: Sinful, Voluptuaries, Heartless, Adversaries, Firebringers, Outlaws, Screamers) → dịch nghĩa với "Những Kẻ". Tên la-tinh/riêng (Pustula, Legio Peccati, Aconia, Abelene, Ibilis, Vaticinators, Morrigan, Tartaros) → giữ nguyên "Order of X"/"Legio X" theo B0, tránh dịch nửa vời. "Cult of Augurs"→"Giáo Phái Augur" (Augur = chức sắc bói điềm La Mã cổ, giữ nguyên danh từ riêng, chỉ dịch "Cult of"→"Giáo Phái"). "Ancient Order of Druids"→"Cổ Hội Druid" ("Ancient"→"Cổ", "Order of"→"Hội", "Druids" giữ nguyên vì đã là danh từ riêng English trong bản gốc `pathoftheeightfoldwheel_adj`). |
| Host of the Broken Heart, Host of the Unseelie *(2 holy_order của Baobhan Sith)* | Đoàn Quân Trái Tim Tan Vỡ, Đoàn Quân Unseelie | "Host" (đoàn quân/đạo binh thiên thần-yêu tinh) dịch "Đoàn Quân"; "Unseelie" (triều đình tiên hắc ám) giữ nguyên theo B0 (thuật ngữ Fae chuyên biệt, không có bản dịch tự nhiên) |
| Deimosianism / Deimosian(s) | Deimosianism / Deimosian *(giữ nguyên)* | đặt mới; tên phái tự tạo từ "deimos" (nỗi sợ Hy Lạp) không có tiền lệ base, giữ nguyên nguyên dạng theo B0 vì dịch nghĩa ("chủ nghĩa sợ hãi") sẽ mất tính danh xưng riêng |
| Mankind / humanity *(deimosianism_desc)* | Nhân Loại / nhân loại | dịch nghĩa phổ thông, viết hoa khi là danh xưng trừu tượng đầu câu, thường khi là danh từ chung |
| Servitors of Irad | Servitors of Irad *(giữ nguyên)* | tên tổ chức riêng gốc Kinh Thánh (Irad, hậu duệ Cain trong Sáng Thế Ký), giữ nguyên theo B0, nhất quán với "Nod"/"Enoch" (B2b/B3q) |
| Baobhan Sith | Baobhan Sith *(giữ nguyên)* | tên riêng truyền thuyết Scotland (ma cà rồng nữ quyến rũ Cao Nguyên), giữ nguyên theo B0 |
| Path of Tevoro / Timonian / Timoni | Path of Tevoro / Timonian / Timoni *(giữ nguyên)* | tên riêng phi chính thống không rõ gốc ngôn ngữ, giữ nguyên theo B0; "Con Đường Tevoro" chỉ dùng trong văn xuôi mô tả (`pathoftevoro_desc`), còn tên hiển thị chính thức của faith (`pathoftevoro:`) giữ dạng gốc "Path of Tevoro" vì đây là tên riêng do Patron đặt, không thuộc hệ `roadof*`/`viaof*` chuẩn |
| Blood Tribe / Anarch(s) | Blood Tribe / Anarch | "Blood Tribe" giữ nguyên (tên tổ chức riêng, không phải "Road of X" chuẩn nên không áp khuôn "Con Đường"); "Anarch" đã là tên phe phái WoD phổ biến, giữ nguyên theo B0 |
| Night World *(bloodtribe_desc)* | Thế Giới Đêm Tối | đặt mới, dịch nghĩa; khác "World of Darkness"→"Thế Giới Bóng Tối" (B2, `pod_wod`) để không trùng hai khái niệm khác nhau trong nguyên bản |
| Traditionless *(bloodtribe_desc, tính từ mô tả Furores không theo truyền thống)* | Vô Truyền Thống | đặt mới, ghép tiền tố "Vô" (đã có tiền lệ base: Vô Số, Vô Sợ, Vô Danh — dùng lại ở B3m cho "Vô Chủ") + "Truyền Thống" |

## B4n. Thuật ngữ bổ sung (từ `POD_religion_mummy`) — việc #2, faith Xác Ướp

Nguồn: `religion/POD_religion_mummy_l_english.yml` (119 dòng, đã dịch xong 100%). Faith nhóm Mummy: Amenti (Ai Cập), Wu T'ian/Wu Kuei (Trung Hoa), và các faith con: Code of Horus (Shemsu-Heru), Ishmaelite, Faces of Apophis (Bane Mummy), Cabiri, Ten Mandates of Heaven, Ten Mandates of Hell (Slaves of the Yama Kings), cộng 8 `holy_order_*`. Chỉ có 2 `Glossary()` (`August Personage of Jade`/`podgloss.augustpersonageofjade`, `Yama Kings`/`podgloss.yamaking` — cả hai đã chốt B3c, dùng lại nguyên tham số, không đổi) và 2 ref `$glossary_wyrm_apep$`/`$glossary_wyrm_apophis$` (đã chốt B3, giữ nguyên).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Amun-Re, Re-Horakhty, Horus, Osiris, Hathor, Taweret, Bes, Ptah, Montu, Nephthys, Hapi, Ammit | *(giữ nguyên)* | tên thần Ai Cập cổ có thật, danh từ riêng theo B0; không có tiền lệ base (CK3 vanilla không có tôn giáo Ai Cập cổ) |
| `X's` *(sở hữu cách tên thần, mọi `_possessive` key)* | "của X" | ✅ theo đúng khuôn mẫu đã dùng ở mọi file `religion/` khác (kueijin, roadofkings, roadofsin…) — tiếng Việt không có 's, luôn đảo thành "của + tên riêng" |
| Temple *(mummies_house_of_worship)* | Đền Thờ | đặt mới; phân biệt với "nhà thờ" (Christianity, base) và "giáo đường" (Judaism, base) — nơi thờ phụng phong cách Ai Cập cổ |
| Wadjet *(mummies_religious_symbol)* | Wadjet *(giữ nguyên)* | tên riêng biểu tượng Con Mắt Wadjet trong thần thoại Ai Cập, không dịch nghĩa |
| scriptures *(mummies_religious_text)* | kinh văn | ✅ theo tiền lệ `kueijin_religious_text`="kinh văn" |
| High Priest / High Priesthood | Đại Tư Tế / Đại Tư Tế Đoàn | đặt mới; "Đại Tư Tế" = chức sắc tôn giáo cao cấp cổ đại, "Đoàn" hậu tố cho tổ chức tập thể |
| devotee *(mọi giới tính)* | tín đồ | dịch nghĩa phổ thông, theo mẫu base (Judaism `bosnian_devotee_male`="tín đồ") |
| priest / bishop *(mummies_priest_*, mummies_bishop_*)* | tư tế | dịch nghĩa phổ thông, phù hợp giọng văn tôn giáo cổ đại thay vì "linh mục" (Christianity) |
| Duat | Duat *(giữ nguyên)* | cõi giới thần thoại Ai Cập có thật (dùng cho cả divine_realm và positive_afterlife), theo tiền lệ base giữ nguyên tên cõi giới ngoại lai (Araboth, Takamagahara, Gangging Siring) |
| Nun *(mummies_negative_afterlife)* | Nun *(giữ nguyên)* | vực hỗn mang nguyên thủy trong thần thoại Ai Cập, danh từ riêng, không dịch |
| Code of Horus / Wat Hor | Luật Lệ Horus / Wat Hor *(giữ nguyên)* | "Code"→"Luật Lệ" dịch nghĩa, "Wat Hor" là tên bản địa (Ai Cập cổ) giữ nguyên theo B0 |
| Ishmaelite(s) | Ishmaelite *(giữ nguyên)* | tên nhóm đặt theo nhân vật riêng "Ishmael", theo B0 giữ nguyên danh từ riêng |
| Faces of Apophis | Diện Mạo của Apophis | "Faces"→"Diện Mạo" dịch nghĩa, "Apophis" giữ nguyên (đã chốt B3 `glossary_wyrm_apophis`) |
| Isfret, Ma'at | Isfret, Ma'at *(giữ nguyên)* | khái niệm triết học/tôn giáo Ai Cập cổ có thật (hỗn mang/trật tự vũ trụ), không có bản dịch tự nhiên, giữ nguyên theo B0 |
| Cabiri / Cabirus | Cabiri / Cabirus *(giữ nguyên)* | tên riêng nhóm/nhân vật sáng lập, theo B0 |
| Ten Mandates of Heaven | Mười Điều Răn của Thiên Đình | dịch nghĩa; "Thiên Đình" đã chốt B3c (`kueijin_divine_realm`) |
| Ten Mandates of Hell / Slaves of the Yama Kings | Nô Lệ của các Diêm Ma Vương | tên hiển thị chính (`ten_mandates_of_hell`) dùng luôn bản dịch của tên gọi khác "Slaves of the Yama Kings" vì đây mới là tên thực tế xuất hiện trong game; "Diêm Ma Vương" đã chốt B3c |
| Undying *(danh xưng chung của Mummy, "a newly created Undying", "their own Undying slaves")* | Xác Ướp | dùng lại bản dịch đã chốt B4 cho `trait_mummy`="Xác Ướp" — "Undying" là cách gọi khác của Mummy trong văn xuôi, không phải thuật ngữ riêng biệt cần dịch khác |
| Family of Heaven *(ten_mandates_of_hell_desc)* | Gia Tộc Thiên Đình | đặt mới, dịch nghĩa, ghép với "Thiên Đình" đã chốt |
| Hand of Thoth | Bàn Tay Thoth | dịch nghĩa "Hand of"→"Bàn Tay", "Thoth" (thần trí tuệ Ai Cập) giữ nguyên |
| Judges of Ma'at | Các Phán Quan của Ma'at | dịch nghĩa, "Ma'at" giữ nguyên như trên |
| Children of Apophis *(holy_order, khác `holy_order_children_of_apophis` dùng ref `$glossary_wyrm_apophis$`)* | Con Cái của $glossary_wyrm_apophis$ | dịch nghĩa "Children of"→"Con Cái của", giữ nguyên ref |
| Celestial Arrows | Mũi Tên Thiên Giới | dịch nghĩa |
| Righteous Peach Blossoms | Đào Hoa Chính Trực | dịch nghĩa; "Chính Trực" đã chốt B4g (Integrity) nhưng ở đây dùng nghĩa tính từ thông thường "ngay thẳng", không phải hệ thống đức hạnh Mummy — ngữ cảnh khác nhau nhưng từ vựng trùng hợp lý |
| Brotherhood of the Scarlet Lantern | Huynh Đệ Hội Đèn Lồng Đỏ | dịch nghĩa |
| White Lotus Society | Hội Bạch Liên | dịch nghĩa, "Bạch Liên" (hoa sen trắng) là cụm Hán Việt quen thuộc |
| Twilight Scholars | Học Giả Hoàng Hôn | dịch nghĩa |
| Jade Sentinels | Vệ Binh Ngọc Bích | dịch nghĩa |

## B4q. Thuật ngữ bổ sung (từ `POD_religion_ordos`) — việc #2, faith Ordos (Malkavian)

Nguồn: `religion/POD_religion_ordos_l_english.yml` (119 dòng, đã dịch xong 100%). Faith chính "Ordos" (giáo phái bí ẩn Malkavian, giữ nguyên tên — đã liệt kê là danh từ riêng ở dòng tra cứu B0 "tên riêng giáo phái/tổ chức WoD") và 8 faith con/tổ chức: Ordo Aenigmatis, Ordo Ecstasis, Ordo Maleficus, Jocastian, Mnemosyne, Ordo Vaticinii (phi chính thống), Daughters of the Sun, Eyes of Malakai. 1 lần `[Glossary('Ashirra','game_concept_ashirra_desc')]` trong `daughtersofthesun_desc` — tham số 1 giữ nguyên "Ashirra" (đã chốt B2b, danh từ riêng giáo phái Hồi giáo ma cà rồng), tham số 2 giữ nguyên là key. Dùng `$pod_clan$`, `$pod_cainites$`, `$pod_diablerie$` đúng như bản gốc, không thêm/bớt ref.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Ordos *(tên faith chính)* | Ordos *(giữ nguyên)* | đã liệt kê sẵn trong B0 (dòng tra cứu "tên riêng giáo phái/tổ chức WoD: ...Ordos..."), áp dụng lần đầu vào văn xuôi thật |
| Mystai *(religion_adj/adherent/devotee/priest/bishop)* | Mystai *(giữ nguyên)* | đặt mới theo B0: danh từ Hy Lạp cổ chỉ "người được điểm đạo vào bí pháp" (mystes/mystai), không có bản dịch tự nhiên tương xứng registrer cổ; dùng cho cả số ít/số nhiều/mọi giống theo đúng bản gốc (bản gốc cũng dùng "mystai" cho mọi ô) |
| Mystery *(high_god_name, thực thể trừu tượng được thờ)* | Bí Ẩn | đặt mới, dịch nghĩa; "The Mystery" (high_god_name_alternate) → "Đấng Bí Ẩn" theo mẫu thêm "Đấng" cho biến thể trang trọng, nhất quán cách base xử lý alternate name (vd. `dualism_high_god_name_alternate`) |
| Mysteries *(religious_text, kinh sách)* | Những Điều Bí Ẩn | dịch nghĩa, số nhiều của "Mystery"/"Bí Ẩn" ở trên nhưng đứng vai trò tên kinh sách nên thêm "Những Điều" cho tự nhiên, khác hẳn ngữ pháp so với tên thần |
| The Beast *(devil_name, witchgodname_the_horned_god)* | Dã Thú | ✅ đã chốt B4i (`The Beast/Frenzy`→`Dã Thú/Phẫn Cuồng`), áp dụng lại |
| Destruction *(death_deity_name)* | Hủy Diệt | dịch nghĩa thông thường; nhất quán với cách dùng ở B4l/B4m (`roadofmetamorphosis`/`roadofsin` cùng giá trị gốc "Destruction"→"Hủy Diệt") |
| labyrinth(s) *(house_of_worship)* | mê cung | dịch nghĩa; có tiền lệ tra được trong `base_game_vh/localization/english/adventurer_name_sections_l_english.yml:401` (`labyrinth: "Mê cung"`) |
| skull *(religious_symbol)* | đầu lâu | đặt mới, dịch nghĩa phổ thông; base dùng "sọ" ở một số nơi nhưng "đầu lâu" tự nhiên hơn cho biểu tượng tôn giáo/tử vong |
| Deacon *(religious_head_title/_name)* | Phó Tế | đặt mới; không có tiền lệ base cho từ này (base chỉ có Giáo hoàng/Thượng phụ/Tổng giám mục... cho các chức sắc Cơ Đốc khác) nhưng "Phó Tế" là thuật ngữ tôn giáo tiếng Việt phổ biến, đúng nghĩa "deacon" (chức sắc cấp dưới linh mục) |
| Mind *(divine_realm)* | Tâm Trí | đặt mới, dịch nghĩa; phù hợp lore Ordos (giáo phái tập trung vào tâm trí/sự điên loạn của Malkavian) |
| Underworld *(positive_afterlife, không qua UmbraGlossaryLocalized ở đây — chỉ là chữ thường trong key faith)* | Âm Giới | dùng "Âm Giới" (khác "Âm Phủ" đã dành riêng cho tham số 2 `UmbraGlossaryLocalized('shadowlands','Underworld')` ở B4j) vì đây là ngữ cảnh khác — giá trị trực tiếp của `positive_afterlife`, không qua macro; chọn "Âm Giới" để tránh đụng "Âm Phủ" đã có nghĩa cố định khác |
| Oblivion *(negative_afterlife)* | Hư Vô | ✅ nhất quán với `roadofbones_negative_afterlife`/`talmahera_negative_afterlife` đã dịch "Hư Vô" cho cùng khái niệm hư vô/tận diệt |
| blood *(health_god_name, chữ thường)* | máu | dịch nghĩa phổ thông, giữ chữ thường như bản gốc |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ có tiền lệ base: `christianity_trickster_god_name:0 "Fortuna"` — giữ nguyên tên nữ thần La Mã |
| Ordo Aenigmatis, Ordo Ecstasis, Ordo Maleficus, Ordo Vaticinii *(4 tên faith con dạng "Ordo + tính từ Latin")* | *(giữ nguyên toàn bộ)* | tên riêng Latin, theo B0; phần `_adj` cũng giữ nguyên tính từ Latin (Aenigmatis, Ecstasis, Maleficus, Vaticinii) |
| Jocastian(s) | Jocastian *(giữ nguyên)* | tên riêng giáo phái tự đặt theo "Jocasta" (nhân vật thần thoại Hy Lạp), không có tiền lệ base, giữ nguyên theo B0; số nhiều tiếng Anh "Jocastians" giữ nguyên ở `adherent_plural` vì đây là danh xưng tự thân bằng tiếng Anh, không phải văn xuôi tiếng Việt cần áp quy tắc gộp số nhiều |
| Mnemosyne | Mnemosyne *(giữ nguyên)* | tên nữ thần Hy Lạp của ký ức, danh từ riêng, giữ nguyên theo B0; văn xuôi mô tả dịch nghĩa "Memory-Seekers"→"những Kẻ Tầm Ký Ức" |
| diablerized/diablerise *(động từ mượn từ "Diablerie", 2 lần trong `jocastian_desc`/`mnemosyne_desc`)* | hành Diablerie *(ai đó)* | đặt mới: thay vì chia động từ tiếng Anh trần trụi kiểu "diablerize", dùng cụm động từ tiếng Việt "hành Diablerie [đối tượng]" — "Diablerie" giữ nguyên danh từ đã chốt B2, "hành" là động từ tiếng Việt nghĩa "thực hiện/tiến hành" |
| The Harbingers of Malkav, The Lamia Mystery, The Order of Argaeus, The Cult of Hecate, Sworn to Cecil *(5 `holy_order_*` của Ordos)* | Những Kẻ Báo Điềm của Malkav, Bí Ẩn Lamia, Dòng tu Argaeus, Giáo phái Hecate, Thề Trung với Cecil | dịch nghĩa theo mẫu chung của các `holy_order_*` khác (B4m): "The Harbingers of X"→"Những Kẻ Báo Điềm của X"; "The X Mystery"→"Bí Ẩn X"; "The Order of X"→"Dòng tu X"; "The Cult of X"→"Giáo phái X"; "Sworn to X"→"Thề Trung với X". Tên riêng (Malkav, Lamia, Argaeus, Hecate, Cecil) giữ nguyên |
| Daughters of the Sun / Daughter(s) | Những Người Con Gái của Mặt Trời / Người Con Gái, Những Người Con Gái | dịch nghĩa; faith con thờ ba "Nữ Thần" Hậu duệ Cain, tiền Hồi giáo |
| Eyes of Malakai / Eye(s) | Những Con Mắt của Malakai / Con Mắt, Những Con Mắt | dịch nghĩa; "Malakai" là tên riêng (chị em song sinh huyền thoại của Malkav), giữ nguyên |

## B4o. Thuật ngữ bổ sung (từ `POD_religion_roadofzarathustra`) — việc #2 file 28/36

Nguồn: `religion/POD_religion_roadofzarathustra_l_english.yml` (117 dòng, đã dịch xong 100%). Faith chính "Road of Zarathustra" (đã khóa cứng B3f/B3k = "Con Đường Zarathustra") cho Ma cà rồng theo đạo đức phỏng theo Bái Hỏa giáo (Zoroastrianism), và 3 faith con: Road of Angra Mainyu (Corrupter), Road of Ahura Mazda (Penitent), Path of Daena (Behdin), cộng 1 faith riêng biệt không theo mẫu "Road of X": Cult of Zilah (dòng dõi Thế Hệ Thứ Hai). File không có `Glossary()`/`UmbraGlossaryLocalized()` nào (bracket count = 0). 21 ref, toàn bộ là tự tham chiếu nội bộ file (`$roadofzarathustra_*$`, `$cultofzilah_*$`) và `$pod_cainites$` — không có ref nào cần dịch.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Road of Zarathustra *(roadofzarathustra_religion)* | Con Đường Zarathustra | ✅ đã khóa cứng B3f/B3k, áp dụng ở đây lần đầu cho file riêng |
| Zarathustrian *(religion_adj/adherent)* | Zarathustrian *(giữ nguyên)* | danh xưng phái sinh từ tên riêng "Zarathustra" (đã giữ nguyên theo B0); khác với "Zoroastrian" của vanilla CK3 (`zoroastrianism_religion_adj`="Bái Hỏa", có bản dịch riêng) — đây là demonym tự chế của POD cho faith ma cà rồng, không phải cùng thực thể nên không dùng "Bái Hỏa" |
| Destruction *(death_deity_name)* | Hủy Diệt | ✅ nhất quán với B4l/B4m (`roadofmetamorphosis`/`roadofsin` cùng giá trị gốc "Destruction") |
| refuge(s) *(house_of_worship)* | nơi trú ẩn / những nơi trú ẩn | đặt mới; cùng trường nghĩa "nơi ẩn náu" với B3w (`roadofbones`="chốn nương thân") và B3z (`roadofhumanity`="nơi ẩn náu/những nơi ẩn náu") nhưng chọn biến thể riêng để tránh trùng lặp y hệt giữa các faith khác nhau — lưu ý: cụm "nơi ẩn náu" (không "những") trùng với B3z, "những nơi trú ẩn" là biến thể số nhiều mới |
| Farahavar *(religious_symbol)* | Farahavar *(giữ nguyên)* | biến thể chính tả POD của "faravahar" — biểu tượng thiêng liêng Zoroastrian có thật; base giữ nguyên "faravahar" (`zoroastrianism_religious_symbol`), áp dụng cùng cách xử lý (giữ nguyên tên gốc, không sửa chính tả POD) |
| Avesta *(religious_text)* | Avesta *(giữ nguyên)* | ✅ tra base (`zoroastrianism_religious_text`="Avesta") |
| dastur *(religious_head_title/devotee/priest/bishop)* | dastur *(giữ nguyên)* | ✅ tra base (`zoroastrianism_bishop_male`="dastur") — chức sắc tôn giáo Zoroastrian có thật, giữ nguyên theo B0 giống "mobed" |
| heaven *(divine_realm/positive_afterlife)* | thiên đường | theo base "thiên đường" (`zoroastrianism_positive_afterlife`, chữ thường) và tiền lệ POD (`roadofblood_positive_afterlife`="thiên đường"); không dùng "Thiên Giới" của base vì đó là bản dịch cho `divine_realm` cụ thể của vanilla Zoroastrianism, còn ở đây một key "heaven" dùng chung cho cả hai trường |
| the abyss *(negative_afterlife)* | vực thẳm | ✅ tiền lệ POD đã dùng thống nhất ở nhiều file `roadof*`/`codeoftremere`/`bloodgnosticism`/`calomenasforsaken` |
| blood *(health/water_god_name, danh từ thường làm tên thần)* | máu | ✅ theo B3q — "Blood" đứng riêng làm tên thần dùng "Máu"/"máu" thuần Việt, không dùng "Huyết" (dành cho từ ghép Hán Việt) |
| Fortuna *(trickster_god_name)* | Fortuna *(giữ nguyên)* | tên nữ thần may mắn La Mã có thật, danh từ riêng theo B0 |
| Corrupter(s) *(roadofagramainyu_adherent)* | Kẻ Tha Hóa | ✅ tiền lệ B3t (`roadofset`/`pathofsubversion_adherent`="Kẻ Tha Hóa") cho cùng từ gốc "Corrupter" |
| Penitent(s) *(roadofahuramazda_adherent)* | Kẻ Sám Hối | ✅ tiền lệ B3y (`roadofheaven`/`viapenaculum_adherent`="Kẻ Sám Hối") cho cùng từ gốc "Penitent" |
| Path of Daena *(pathofdaena)* | Con Đường Daena | "Path" dùng như đồng nghĩa "Road" (đã chốt B3h/B3y), "Daena" (khái niệm lương tâm/tôn giáo trong Zoroastrianism) giữ nguyên vì không có bản dịch tự nhiên ngắn gọn |
| Behdin(s) *(pathofdaena_adherent)* | Behdin *(giữ nguyên)* | thuật ngữ tôn giáo Zoroastrian có thật (tín đồ "Đạo Tốt"), không có tiền lệ base nhưng theo B0 giữ nguyên vì là danh xưng tôn giáo chuyên biệt, giống cách xử lý "dastur"/"mobed" |
| Cult of Zilah *(cultofzilah)* | Giáo Phái Zilah | ✅ mẫu "Cult of X (danh từ riêng)" → "Giáo Phái X", theo tiền lệ B4m (`roadofsin`, "Cult of Augurs"→"Giáo Phái Augur") |
| Cultist(s) *(cultofzilah_adherent)* | Tín Đồ | đặt mới, dịch nghĩa phổ thông phù hợp với "Giáo Phái" ở trên |
| The Weeping Stone / The Weeping Master *(cultofzilah_house_of_worship/good_god_weeping_master)* | The Weeping Stone / The Weeping Master *(giữ nguyên)* | tên riêng chuyên biệt của cốt truyện (thánh tích + chức sắc sáng lập giáo phái), xuất hiện đồng nhất bằng tiếng Anh ở các file POD khác chưa dịch (`struggle_POD_l_english.yml`, `bookmark/bookmarks_POD_l_english.yml`, `event_localization/schemes/POD_investigate_l_english.yml`) — giữ nguyên để nhất quán khi các file đó tới lượt dịch, tránh tạo hai tên cho cùng thực thể |
| Second Generation *(pantheon_term)* | Thế Hệ Thứ Hai | dịch nghĩa theo mẫu "Thế Hệ Thứ N" đã chốt B4e (Generation), áp dụng cho văn xuôi thay vì tên trait |
| evil_god_* (Zapathustra, Set, Ventru, Arikel, Ennoia, Ashur, Absimilliard, Malkav, Lasombra, Tzimisce) | *(giữ nguyên toàn bộ)* | tên các Antediluvian bị bóp méo qua góc nhìn dị giáo Cult of Zilah — danh từ riêng, giữ nguyên theo B0, khớp tên clan gốc đã giữ nguyên ở `traits_POD` (B4d) |
| Zilah, Anosh, Irad, Haqim, Caine, Enoch | *(giữ nguyên)* | danh từ riêng — nhân vật/tên thần gốc Kinh Thánh hoặc lore VtM, theo B0 |

## B4p. Thuật ngữ `religion/POD_religion_demons_l_english.yml` — faith Demon (Sin), việc #2 file 29/36

File 141/141 dòng, dịch xong 100%. Faith này là ác quỷ (`trait_demon`="Ác quỷ", đã chốt B4) tôn thờ "Sin" được nhân cách hóa. Không nhầm với `religion/POD_religion_roadofsin_l_english.yml` (faith ma cà rồng "Road of Sin/Con Đường Tội Lỗi") — hai faith khác nhau cùng dùng ý niệm "Sin"/"Tội Lỗi", đã tra để tránh xung đột nhưng không có key trùng nhau.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Sin *(demons_religion/high_god_name/health_god_name, danh xưng vị thần tối cao ác quỷ thờ)* | Tội Lỗi | nhất quán với cách `roadofsin_high_god_name`="Tội Lỗi" đã dịch cùng khái niệm trừu tượng ở faith khác |
| Corruption *(high_god_name_alternate)* | Sự Sa Đọa | đặt mới, tên gọi khác của "Sin" khi nhân cách hóa |
| Archduke *(good_god_archduke, danh hiệu quỷ vương cai trị Địa Ngục)* | Đại Công Tước | đặt mới; không có tiền lệ base (tra không thấy "Archduke"); dùng thang bậc quý tộc dịch nghĩa, cao hơn "Công Tước"=Duke (A7); áp dụng cho các nơi khác nhắc "Infernal Archduke" sau này |
| the Great Betrayer *(devil_name)* | Kẻ Phản Bội Vĩ Đại | dịch nghĩa |
| Lucifer, Malhim, Elohim, Michael *(evil_god_*, tên riêng thiên thần/nhóm Kinh Thánh-WoD)* | *(giữ nguyên)* | danh từ riêng Kinh Thánh/WoD theo B0; "Elohim"/"Malhim" là tên nhóm thiên thần trong lore Demon (`Bene Elohim`), không dịch |
| Death *(death_deity_name)* | Cái Chết | ✅ tiền lệ base (`religion_christianity_l_english.yml`: `christianity_death_deity_name`="Cái Chết") |
| church/churches *(house_of_worship)* | nhà thờ | theo tiền lệ base (`christianity_house_of_worship`="nhà thờ") |
| pentagram *(religious_symbol)* | ngôi sao năm cánh | đặt mới, không có tiền lệ base; mô tả trực quan biểu tượng thay vì phiên âm |
| scriptures *(religious_text)* | thánh kinh | đặt mới, dịch nghĩa chung chung phù hợp giáo phái thờ quỷ không có kinh sách cụ thể được đặt tên |
| Leader *(religious_head_title)* | Thủ Lĩnh | dịch nghĩa thông thường |
| Faction *(religious_head_title_name)* | Phe Phái | ✅ dùng lại bản dịch đã chốt ở A6 (`game_concept_faction`) |
| Heart *(divine_realm, cõi giới ác quỷ hướng về)* | Trái Tim | đặt mới, dịch nghĩa đen; không đủ ngữ cảnh khác trong repo để xác định đây có phải danh từ riêng của một địa danh cụ thể hay không, tạm dịch nghĩa theo B0 (chỉ giữ nguyên khi là danh từ riêng xác nhận được) |
| Redemption *(positive_afterlife)* | Sự Cứu Rỗi | đặt mới, dịch nghĩa |
| Abyss *(negative_afterlife)* | Vực Thẳm | ✅ tiền lệ base (`religion_christianity_l_english.yml`: `christianity_negative_afterlife_2`="Vực Thẳm"; `religion_paganism_l_english.yml`: `basque_negative_afterlife_3`="Vực Thẳm") |
| God *(creator_god_name, Thượng Đế nguyên thủy — khác "Sin" mà quỷ thờ)* | Thượng Đế | dịch nghĩa chung, nhất quán với cách gọi "Thượng Đế" đã dùng ở B3 cho "Abrahamic God" |
| Fortuna *(fate_god_name/trickster_god_name)* | Fortuna *(giữ nguyên)* | ✅ đã chốt B3h, áp dụng lại kèm possessive "của Fortuna" |
| Avarice / Envy / Gluttony / Lust / Pride / Sloth / Wrath *(7 mối tội đầu, tên splat con của faith Demon)* | Tham Lam / Đố Kỵ / Háu Ăn / Dục Vọng / Kiêu Ngạo / Lười Biếng / Thịnh Nộ | đặt mới; không có tiền lệ base (7 mối tội đầu không xuất hiện dưới dạng key religion trong `base_game_vh`); dùng từ tiếng Việt phổ thông mô tả tội lỗi, tính từ và danh từ trừu tượng dùng chung một từ (theo cách gốc tiếng Anh cũng dùng chung, ví dụ `avarice`/`avarice_adj` đều "Avarice") |
| Demon of Greed/Envy/Gluttony/Lust/Pride/Sloth/Wrath *(adherent của từng splat tội lỗi)* | Ác quỷ của Lòng Tham / Sự Đố Kỵ / Sự Háu Ăn / Dục Vọng / Sự Kiêu Ngạo / Sự Lười Biếng / Sự Thịnh Nộ | ghép "Ác quỷ của" + danh từ trừu tượng tội lỗi tương ứng ở trên |
| `_possessive` (`"X's"`) | mẫu `"của X"` | ✅ áp dụng nhất quán theo B3e/B3g/B3h/B3k/B3s, kể cả tên riêng (`"Lucifer's"`→"của Lucifer") |

> Dòng 111-142 (splat `faustian`, `cryptic`, `luciferan` + 3 holy order liên quan, `ravener`, `reconciler`) đều là **key bị comment** (`#` ở đầu dòng) trong bản gốc — giữ nguyên hoàn toàn, không dịch, theo mục 5 TRANSLATION_RULES.md.

## B4r. Thuật ngữ `religion/POD_religion_modern_l_english.yml` — Anarch/Camarilla/Sabbat hiện đại, việc #2 file 30/36

File 125/125 dòng, dịch xong 100%. Nhóm faith ma cà rồng hiện đại: Modern Anarch, Camarilla, và 13 "Path of Enlightenment" thuộc Sabbat. Phần lớn dùng lại thuật ngữ đã chốt (Path of X → Con Đường X theo B3f/B3k, Camarilla/Sabbat/Anarch giữ nguyên B0, Kindred → Huyết Tộc B3k, Masquerade → Màn Che, Antediluvians/Caine/Priscus giữ nguyên B0/B2b, Book of Nod → Sách Nod B2b).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| status quo | hiện trạng | dịch nghĩa thường, không có khái niệm WoD riêng |
| Traditions *(7 Luật Camarilla)* | Luật | số ít/nhiều gộp theo mục 7 TRANSLATION_RULES.md |
| Sword of Caine | Thanh Kiếm của Caine | dịch nghĩa cụm mô tả, chưa có tiền lệ ở file khác |
| Gehenna | Gehenna *(giữ nguyên)* | biến cố tận thế ma cà rồng, danh từ riêng WoD gốc Kinh Thánh, chưa có tiền lệ dịch ở bất kỳ file POD nào |
| Convention of Thorns | Công Ước Thorns | "Convention"→"Công Ước", giữ tên riêng "Thorns"; lần đầu xuất hiện trong mod |
| Blood Bond | Ràng Buộc Máu | dịch nghĩa thông thường |
| pack *(đơn vị tổ chức Sabbat)* | pack *(giữ nguyên)* | danh từ tổ chức lõi WoD, theo B0, không có tiền lệ dịch |
| ritae, ritus | *(giữ nguyên)* | danh từ nghi lễ Latin của Sabbat, không có tiền lệ |
| War Parties | các đoàn chinh chiến | dịch nghĩa thường |
| Dark Ages *(bối cảnh lịch sử, không phải game-concept)* | thời Trung Cổ Đen Tối | dịch nghĩa tự nhiên |
| the Damned | Những Kẻ Bị Nguyền Rủa | cách gọi ma cà rồng, dịch nghĩa |
| Demiurge, Jyhad, vinculum | *(giữ nguyên)* | thuật ngữ lore VtM không có bản dịch tự nhiên |
| Patriot(s) / Necronomist(s) / Unifier(s) / Metamorphosist(s) / Albigensian(s) / Noddist(s) / Harmonist(s) / Nihilist(s) / Martyr(s) *(tên tín đồ 9 Path Sabbat trong file này)* | Người Ái Quốc / Người Nghiên Cứu Tử Vong / Người Hợp Nhất / Người Biến Hóa / Người Albigensia / Người Theo Sách Nod / Người Hài Hòa / Người Hư Vô / Kẻ Tuẫn Đạo | mẫu "Người/Kẻ + tính chất", nhất quán văn phong gothic |

> Dòng `camahumanity_desc` có cặp dấu `"Path"` không escape (`\"`) ngay trong bản gốc tiếng Anh (lỗi cú pháp có sẵn của POD, không phải `\"`) — bản dịch giữ nguyên byte-for-byte cặp dấu bare-quote đó quanh cụm dịch "Con Đường", đúng theo quy tắc giữ nguyên lỗi gốc.

## B4s. Thuật ngữ `religion/POD_religion_wyrm_l_english.yml` — faith Wyrm (Garou sa ngã), 243/243 dòng

File faith thờ Wyrm và các camp/sub-tribe Garou đã ngả theo nó (Black Spiral Dancers, Bone Gnawer/Shadowlord/Silent Strider/Star Gazer/Ceilican/Warders-of-Men camp bị nhiễm độc). Wyrm/Wyld/Weaver giữ nguyên tiếng Anh xuyên suốt theo B3 (bắt buộc, không phải tùy chọn). Tên camp/tribe là danh từ riêng, giữ nguyên hoặc dịch nghĩa tùy trường hợp — xem bảng dưới.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Litany *(bộ luật Garou)* | Litany *(giữ nguyên)* | Chưa có bản dịch nào tồn tại trong repo (file gốc chứa khái niệm này — `POD_religion_docrtineandtenets`, `POD_religion_gaia` — đều chưa dịch tại thời điểm này). Xử lý theo B0: danh từ riêng WoD lõi, tránh đụng "Masquerade"→"Luật Che Giấu" đã có tiền lệ (khác khái niệm) |
| caern | caern *(giữ nguyên)* | Đã có tiền lệ nhiều nơi trong POD dùng "Caern" nguyên dạng làm tên công trình/địa điểm linh thiêng Garou (`buildings_fera_POD_l_english.yml`, `POD_court_positions_l_english.yml`) — chưa dịch, giữ nguyên để nhất quán với các key khác |
| glyph *(biểu tượng tôn giáo Wyrm)* | phù văn | dịch nghĩa theo mẫu `religious_symbol` của base (thường là danh từ vật lý ngắn gọn, ví dụ "thánh giá", "hiža") |
| lore *(kinh sách Wyrm)* | cổ thư | dịch nghĩa theo mẫu `religious_text` của base |
| High Priest *(chức sắc tôn giáo Wyrm)* | Đại Tư Tế | theo tiền lệ `dualism_religious_head_title`="Đại Tư Tế" trong base_game_vh cho một giáo phái ngoại giáo tương tự |
| Cultist *(tín đồ Wyrm, khác `predatortype_cultist`="Giáo Chủ Tà Giáo")* | Tín đồ | theo mẫu `_devotee_male` phổ biến của base (thường là danh từ chung viết thường) |
| Priest / Bishop *(Wyrm)* | Tư Tế | gộp chung vì bản gốc cũng dùng "Priest" cho cả hai key |
| the wilds *(cõi chết tiêu cực của tín đồ Wyrm)* | vùng hoang dã | dịch nghĩa, không phải tên riêng |
| Black Spiral Dancers | Vũ Công Xoáy Đen | tên bộ tộc Garou sa ngã, dịch nghĩa vì là cụm mô tả tiếng Anh thường, không phải danh xưng ngoại lai kiểu Ahroun/Sidhe |
| Princes of Ruin | Chúa Tể Diệt Vong | tên camp, dịch nghĩa (đổi "Princes"→"Chúa Tể" cho hợp giọng gothic, tránh trùng "Hoàng tử" của vanilla) |
| Seekers of the Ancient | Kẻ Tìm Kiếm Đấng Cổ Xưa | dịch nghĩa |
| Wyrm-bound | Kẻ Bị Wyrm Ràng Buộc | tên camp/trạng thái, dịch nghĩa, giữ "Wyrm" |
| Man-eaters (Bone Gnawer camp) | Kẻ Ăn Thịt Người | dịch nghĩa |
| Masks (Shadowlord camp) | Mặt Nạ | dịch nghĩa |
| Society of Nidhogg | Hội Nidhogg | dịch nghĩa, giữ tên riêng "Nidhogg" |
| Ebon Centipede (Hakken camp) | Rết Đen | dịch nghĩa |
| Eaters of the Dead (Silent Strider camp) | Kẻ Ăn Xác | dịch nghĩa |
| Metastic Birth (Star Gazer camp) | Sinh Nở Di Căn | dịch nghĩa |
| Ouroboroans | Ouroboroan | giữ nguyên dạng danh từ riêng (tên phái gốc Hy Lạp "Ouroboros"), chỉ bỏ hậu tố số nhiều "-s" theo mục 7 TRANSLATION_RULES.md |
| Boli Zouhisze (Warders of Men offshoot) | Boli Zouhisze *(giữ nguyên)* | tên riêng Trung Hoa, không dịch |
| Hellcats (Ceilican camp) | Hellcat | giữ nguyên danh từ riêng, chỉ bỏ số nhiều |
| Mnetics (Mokolé camp) | Mnetic | giữ nguyên danh từ riêng, chỉ bỏ số nhiều; "Eaters of Secrets" (tên gọi khác) → "Kẻ Ăn Bí Mật" dịch nghĩa |
| camp *(đơn vị xã hội con trong một bộ tộc Garou)* | trại | dịch nghĩa thường, theo tiền lệ base dùng "Trại" cho danh từ camp vật lý/tổ chức (`lifestyle_adventurers`, `msg_domicile_moved`) |
| `_possessive` *(mẫu ngữ pháp sở hữu cách)* | "của [Tên]" | **Xác nhận lại quy ước đã có ở các file religion trước** (`POD_religion_talmahera`, `POD_religion_naktanchara`): key `X_possessive: "Name's"` trong tiếng Anh dịch thành `"của Name"` — bỏ hậu tố `'s`, thêm giới từ "của" phía trước, **không giữ `'s` nguyên văn**. Đã tự phát hiện và sửa lỗi này trong quá trình tự kiểm tra trước khi hoàn tất |
| Glossary('Centipede'/'Dissolver'/'Cahlash', 'glossary_wyrm_tt') | Glossary('Rết'/'Kẻ Hòa Tan'/'Cahlash', 'glossary_wyrm_tt') | tham số 1 dịch ("Centipede"→"Rết", "Dissolver"→"Kẻ Hòa Tan", "Cahlash" giữ nguyên vì là tên riêng phát âm lạ), tham số 2 `glossary_wyrm_tt` giữ nguyên |

> Toàn bộ tên god (`wyrm_trickster_god_name`="Pseulak", `wyrm_night_god_name`="Foebok", `wyrm_water_god_name`="Wakshaa", `wyrm_fertility_god_name`="Karnala", `wyrm_wealth_god_name`="Vorus") là danh từ riêng WoD, giữ nguyên hoàn toàn.

## B4t. Thuật ngữ `religion/POD_religion_fae_l_english.yml` — faith Fae/Changeling, việc #2 file 31/36

Nguồn: `religion/POD_religion_fae_l_english.yml` (566 dòng, 381 key) — faith chính "Fae" cùng 5 sub-faith Triều đình Mùa (Winter/Spring/Summer/Autumn/Solstice Court), sub-faith Eshu (Ojo/Iku), và sub-faith Shinma (Mu Courts, Daityas, Kura Sau, Shu Shen, Li Shen, Tu Shen, Xian Mo, Xian Mun, Yellow Lotus, Yü, Wu Hsien). Áp dụng B0/B4b: danh từ WoD lõi của Fae giữ nguyên tiếng Anh.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Death *(fae_death_deity_name — thực thể thần chết, khác `Death` chung chung)* | Tử Thần | dịch nghĩa như danh xưng thần, theo mẫu base đặt tên riêng cho mỗi witchgodname/death_deity |
| glyph *(fae_religious_symbol, khác `glyph` Wyrm đã dịch "phù văn" ở B4s)* | hình khắc | đặt mới cho ngữ cảnh Fae — "glyph" ở đây mô tả biểu tượng khắc trên đá/gỗ của tổ ấm Changeling, không phải phù chú Wyrm, nên tách nghĩa |
| legends *(fae_religious_text)* | truyền thuyết | nhất quán với "Lorekeeper"→"Người Giữ Truyền Thuyết" bên dưới, theo tiền lệ B3g/B3h (không dùng "Người Giữ Cổ Tích" của B4c/B4j — đó là ngữ cảnh roadofbeast/`religious_text`="cổ tích", khác file) |
| Lorekeeper(s) | Người Giữ Truyền Thuyết | tái sử dụng bản dịch đã chốt ở B3g (`POD_religion_ghoul`) và B3h (`POD_religion_roadoflaibon`), áp dụng cho mọi biến thể `devotee_*`/`priest_*`/`bishop*` |
| Dream *(fae_divine_realm)* | Cõi Mộng | nhất quán với "Dreaming"→"Cõi Mộng" đã chốt ở B4b (áp dụng cho cả `Dream` số ít và `[UmbraGlossary('dreaming')]`/`[UmbraGlossary('deep_dreaming')]` — tag giữ nguyên, chỉ dịch văn xuôi nhắc "the Dreaming") |
| Militants *(phe phái chính trị Fae)* | Phe Hiếu Chiến | đặt mới; các phe chính trị Fae (Militants/Truce-Bearers/Humanists/Constantinians) là khái niệm riêng của POD, không trùng "Militant" nào trong base |
| Truce-Bearers | Phe Người Mang Đình Chiến / Truce-Bearer *(giữ nguyên khi ghép sau tên Triều đình, ví dụ "Winter-kin Truce-Bearer")* | đặt mới; "Oath-Truce"→"Hiệp ước Đình chiến" |
| Humanists | Phe Nhân Đạo / Humanist *(giữ nguyên khi ghép, ví dụ "Ojo Humanist")* | đặt mới |
| Constantinians | Phe Constantine / Constantinian *(giữ nguyên khi ghép)* | đặt mới; tên phe bắt nguồn từ "Emperor Constantine I" — dịch tên hoàng đế thành "Hoàng đế Constantine Đệ Nhất" khi văn xuôi nhắc đến, còn danh từ phe phái giữ dạng ghép "Constantinian" khi đứng sau tên Triều đình (ví dụ "Winter Court Constantinian" → giữ dạng gốc trong key, chỉ dịch mô tả) |
| Oath-Truce | Hiệp ước Đình chiến | đặt mới, thuật ngữ chính trị trung tâm của lore Fae POD (100 năm hòa hoãn giữa Chiến tranh Mùa) |
| War of Seasons | Chiến tranh Mùa | đặt mới |
| Season Courts / Winter/Spring/Summer/Autumn Court | Triều đình Mùa Đông/Mùa Xuân/Mùa Hạ/Mùa Thu | dịch nghĩa tên mùa, "Court"→"Triều đình" nhất quán với B2 (Courts of Love→"Tòa Ái Tình" dùng "Tòa"; ở đây dùng "Triều đình" vì đây là triều đình cai trị theo nghĩa đen, không phải tòa án) |
| Solstice Court / Solstice fae | Triều đình Mùa Giao / fae Mùa Giao | đặt mới — "Solstice" ở đây chỉ phe fae Courtless/trung lập không thuộc 4 mùa chính, dịch "Mùa Giao" (thời điểm giao mùa) để phân biệt với 4 Triều đình Mùa thật; tránh dịch "Chí" (Đông Chí/Hạ Chí) vì gây nhầm với các ngày lễ `Winter Solstice Festival` |
| *-kin (hậu tố dân cư Triều đình, vd. Winter-kin, Spring-kin, Autumn-kin, Solstice-kin)* | *-kin (giữ nguyên)* | theo B0 — giữ nguyên hậu tố tiếng Anh gắn với tên mùa, vì dịch nghĩa "-kin" (dòng dõi/thân tộc) sẽ phá vỡ tính nhất quán khi ghép với tên riêng mùa (Winter, Spring...) |
| Courtless / unSained | Vô Triều đình / unSained *(giữ nguyên "unSained")* | "Courtless" dịch nghĩa ("không triều đình"); "unSained" là biến thể phủ định của nghi lễ "Saining" (xem dưới) nên giữ nguyên theo B0 |
| Sained / Saining | Sained / Saining *(giữ nguyên)* | nghi lễ tôn giáo cốt lõi biến một người phàm/changeling thành thành viên chính thức của một Triều đình; danh từ riêng WoD không có khái niệm vanilla tương đương, giữ nguyên theo B0 |
| oathcircle | oathcircle *(giữ nguyên)* | thuật ngữ WoD chuyên biệt (nhóm lời thề ràng buộc fae-người phàm), không có tiền lệ base |
| Battle of Stone | Trận Đá | đặt mới, sự kiện lịch sử trung tâm của lore Fae POD (trận chiến lớn 800 năm trước mốc thời gian game) |
| the Mists | Sương Mù | đặt mới, khái niệm ẩn dụ cho sự lãng quên/mất kết nối giữa fae và loài người (khác "Cõi Mộng"/Dreaming) |
| Patrons / Patron *(tổ chức chính trị Fae, khác "Patron Council"→"Hội đồng Bảo Trợ" B4b)* | Những Người Bảo Trợ / Người Bảo Trợ | tái dùng gốc từ "Bảo Trợ" đã chốt ở B4b cho nhất quán |
| Seekers, Vanguard, Austere Conclave *(3 nhánh của Patrons)* | Seeker, Vanguard, Austere Conclave *(giữ nguyên)* | tên riêng tổ chức con, không dịch theo B0 |
| Empire of Seeds/Stones/Flames/Tears/Skies/Dolls *(6 đế chế Inanimae)* | Đế Chế Hạt Giống/Đá/Ngọn Lửa/Nước Mắt/Bầu Trời/Búp Bê | dịch nghĩa tên đế chế theo mẫu "Empire of X" → "Đế Chế X", nhất quán với cách B4b dịch "Empire of Seeds" chưa có tiền lệ — đặt mới ở đây |
| Kubera, Glome, Solimond, Ondine, Paroseme, Mannikin *(6 Phyla Inanimae, cai trị 6 đế chế trên)* | *(giữ nguyên)* | tên riêng chủng loài Inanimae, đã có trong danh sách giữ nguyên B4b |
| Dryad, Nymph, Sylph, Nereid, Salamander, Silfar, Sprite *(biệt danh dân gian cho các Phyla/thành viên đế chế)* | *(giữ nguyên)* | danh từ thần thoại phương Tây dùng làm biệt danh, không dịch để khớp văn phong gothic-cổ điển; ngoại lệ "Sylph" dùng làm adherent của Empire of Skies vẫn giữ nguyên dạng số ít/số nhiều gộp chung theo mục 7 TRANSLATION_RULES.md |
| Homeland *(quê hương nguyên thủy trong Cõi Mộng của mỗi đế chế Inanimae)* | Quê Hương | dịch nghĩa, viết hoa vì là danh xưng địa danh riêng trong lore |
| War of Making | Chiến tranh Tạo Tác | đặt mới, sự kiện lịch sử của Inanimae (Salamander phản bội, gây chia rẽ 6 đế chế) |
| Anchor *(vật neo giữ Inanimae với thế giới vật chất)* | Neo | dịch nghĩa ngắn gọn, nhất quán với "Glade" dịch "Khu Rừng Thưa" khi ghép ("Anchors of the Glade"→"Neo của Khu Rừng Thưa") |
| Moot *(lễ hội thường niên của Kubera)*, Spring Equinox/Autumn Equinox/Summer Solstice/Winter Solstice Festival *(4 lễ hội mùa)* | Moot *(giữ nguyên tên riêng lễ hội)*; Xuân Phân/Thu Phân/Hạ Chí/Lễ Hội Đông Chí | dịch nghĩa các lễ hội theo mùa (thuật ngữ thiên văn phổ thông), "Moot" giữ nguyên vì là danh xưng riêng không dịch được sát nghĩa |
| Eshu, Ojo, Iku *(sub-faith châu Phi của Fae, tương ứng Sidhe/Season Courts)* | *(giữ nguyên)* | danh từ riêng dân tộc/triết lý châu Phi, theo B0 và danh sách B4b đã có "Elegbara" |
| Uhuru *(bộ quy tắc danh dự chung của Eshu)* | Uhuru *(giữ nguyên)* | thuật ngữ tiếng Swahili, danh từ riêng không dịch |
| Seelie Code *(bộ luật của Triều đình Seelie)* | Luật Seelie | dịch nghĩa "Code"→"Luật" (nhất quán `Litany`→giữ nguyên B4s là ngoại lệ khác, ở đây "Code" là từ tiếng Anh thường không phải danh xưng WoD), giữ "Seelie" theo B0 |
| Hsien Court, Shinma *(tổng danh xưng fae Đông Á, tương đương Season Courts phương Tây)* | *(giữ nguyên)* | đã có trong danh sách kith giữ nguyên B4b (Hsien) |
| Mu Courts, Daityas, Kura Sau, Shu Shen, Li Shen, Tu Shen, Xian Mo, Xian Mun, Yellow Lotus, Yü, Wu Hsien *(11 giáo phái/triều đình Hsien-Shinma)* | *(giữ nguyên)* | tên riêng giáo phái Đông Á theo B0, không có tiền lệ base; áp dụng cho cả dạng số ít/số nhiều |
| Yama Kings, August Personage of Jade, Demon Emperor, Tao Te Hsien, Fourth Age, Sixth Age *(6 khái niệm lõi Hsien, xuất hiện qua `Glossary()`)* | *(giữ nguyên tham số 1 hiển thị — đã có sẵn trong file gốc bằng tiếng Anh, không đổi)* | các khái niệm này được định nghĩa & dịch tại `glossary_POD_l_english.yml` (khối Kuei-Jin/lịch sử `podgloss.*`) — file này chỉ **tham chiếu** qua `[Glossary('Tên Hiển Thị','podgloss.key')]`, tham số 1 giữ nguyên y hệt bản gốc vì đó là chữ hiển thị đã được định nghĩa nơi khác, không tự dịch lại ở đây để tránh lệch với bản dịch gốc (thời điểm dịch file này, `glossary_POD` các key `podgloss.yamaking` v.v. chưa được xác nhận đã dịch hay chưa — giữ nguyên tiếng Anh là lựa chọn an toàn, không tự sáng tác bản dịch mới) |
| Middle Kingdom | Trung Nguyên | đặt mới, thuật ngữ địa lý-thần thoại Trung Hoa quen thuộc |
| Kamuii, Hirayanu | Kamuii, Hirayanu *(giữ nguyên)* | tên riêng phân loại Hsien theo mức độ giác ngộ, không có tiền lệ base |
| Tongs, Triads | Bang Hội, Tam Hoàng | dịch nghĩa (tổ chức tội phạm Hoa kiều lịch sử), thuật ngữ phổ thông trong văn học/phim ảnh tiếng Việt |
| Dragon Nests | Tổ Rồng | dịch nghĩa |
| holy_order_winters_teeth/green_blades/sun_guard/crunch_of_leaves/sunset_mercenaries/grey_monks *(6 holy order của các Triều đình Mùa)* | Răng Mùa Đông / Lưỡi Kiếm Xanh / Vệ Binh Mặt Trời / Tiếng Lá Vỡ Vụn / Lính Đánh Thuê Hoàng Hôn / Tu Sĩ Xám | dịch nghĩa theo mẫu base (`holy_orders_l_english.yml` dịch nghĩa toàn bộ tên holy order); "Green Blades" dịch "Lưỡi Kiếm Xanh" nhất quán với cách văn xuôi trong cùng file nhắc "Seigfreid Hein's Green Blade" |
| `_possessive` (`"X's"`) | mẫu `"của X"` | tiếp tục áp dụng quy ước đã chốt xuyên suốt các file `religion/` trước (B3g/B3h/B3s...) |

## B4u. Thuật ngữ `religion/POD_religion_wraiths_l_english.yml` — faith Oan hồn (Wraith), 750/750 dòng

Nguồn: file neo faith Wraith (750 dòng, 657 key) — faith chính "Hierarchy" (hiển thị "Legion"), 4 nhóm con "Legion" (Iron/Skeletal/Grim/Penitent/Emerald/Silent/Legion of Paupers/Legion of Fate), 10 Guild Arcanoi (Artificers/Masquers/Pardoners/Usurers/Chanteurs/Harbingers/Oracles/Sandmen/Haunters/Monitors/Spooks/Proctors/Puppeteers/Alchemists/Mnemoi/Solicitors), faith "Renegade" và 4 sub-faith chính trị (Drop-Outs/Idealists/Outlaws/Protesters), faith "Ferrymen" (+ Shining Ones, Fishers), faith "Yellow Springs" (Wraith Đông Á), và faith "Spectre" (+ Malfean, Grand Maw). Áp dụng B0/B4h: danh từ WoD lõi giữ nguyên tiếng Anh.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Stygia, Charon | *(giữ nguyên)* | danh từ riêng WoD — xác nhận qua tiền lệ có sẵn `e_stygia: "Stygia"` (`titles_POD_l_english.yml`, chưa dịch nhưng cho thấy quy ước không phiên âm) |
| Hierarchy *(tên nội bộ của faith chính, giá trị hiển thị thực tế là "Legion")* | Quân Đoàn | `hierarchy_religion: "@wraith_icon! Legion"` — dịch giá trị hiển thị, không dịch tên biến |
| Legion *(tổ chức nói chung + hậu tố tên 8 Legion con)* | Quân Đoàn | dịch nghĩa nhất quán cho mọi Legion: Iron→Sắt, Skeletal→Xương, Grim→U Ám, Penitent→Sám Hối, Emerald→Lục Bảo, Silent→Câm Lặng, Legion of Paupers→Quân Đoàn Kẻ Bần Cùng, Legion of Fate→Quân Đoàn Số Mệnh |
| Legionnaire(s) | Quân Đoàn Binh | lính/tín đồ thường của mọi Legion, số ít/số nhiều gộp theo mục 7 TRANSLATION_RULES.md |
| Deathlord / Deathlady | Tử Chủ / Nữ Tử Chủ | chức sắc cao nhất của Hierarchy |
| Centurion(s) | Bách Phu Trưởng | cấp bậc quân sự La Mã, thuật ngữ Hán Việt lịch sử quen thuộc |
| Anacreon(s) | Đại Bách Phu Trưởng | cấp trên Centurion, đặt theo thang bậc quân sự nhất quán |
| Seat *(house_of_worship của Hierarchy — tổng hành dinh mỗi Legion)* | Bản Doanh | |
| Shadow *(hierarchy/renegade/ferrymen_devil_name, witchgodname)* | Bóng | tái dùng bản dịch đã chốt B4h cho "Shadow" (khía cạnh đen tối của oan hồn) |
| Underworld *(hierarchy/renegade/ferrymen/yellow_springs_divine_realm)* | Âm Phủ | tái dùng bản dịch đã chốt B4j |
| Transcendence *(positive_afterlife)* | Siêu Thoát | đặt mới, mượn thuật ngữ Phật giáo phù hợp phong cách kiếp sau/giải thoát, ngắn gọn cho UI |
| Oblivion *(negative_afterlife của Hierarchy/Renegade/Ferrymen; positive_afterlife của Spectre)* | Hư Vô | tái dùng bản dịch đã chốt B3q/B4n cho cùng khái niệm hư vô/tận diệt |
| Tempest *(water_god_name dùng chung mọi faith trong file)* | Bão Tố | dịch nghĩa, không phải danh từ riêng lõi hệ thống Wraith |
| Renegade(s) | Kẻ Nổi Loạn | tên faith ly khai khỏi Hierarchy |
| Ferryman / Ferrymen | Ferryman / Ferrymen *(giữ nguyên)* | đã chốt B4h |
| Shining Ones, Fishers, Spectre(s), Malfean, Grandmother, Grand Maw | *(giữ nguyên)* | tên riêng faith/thực thể WoD, theo B0; "Grand Maw" là biệt danh của Grandmother — giữ nguyên vì gắn với lối chơi chữ "Grand Maw" ≈ "Grandma" trong nguyên bản tiếng Anh, không thể tái tạo bằng tiếng Việt nên không dịch nghĩa (tránh mất nghĩa gốc) |
| Yu Huang, Kuei, Ti Yu | *(giữ nguyên)* | tên riêng phiên âm vũ trụ luận Đạo giáo của faith "Yellow Springs" — cố ý KHÔNG dùng "Ngọc Hoàng" (đã dùng cho vũ trụ luận Kuei-Jin ở B3e) để tránh lẫn hai hệ thống thần thoại Trung Hoa khác nhau trong POD |
| P'eng Lai *(positive_afterlife của Yellow Springs)* | Bồng Lai | địa danh thần thoại Đạo giáo quen thuộc trong tiếng Việt |
| Yellow Springs | Suối Vàng | dịch nghĩa trực tiếp, tên faith Wraith Đông Á |
| Jade Wraith(s) | Oan Hồn Ngọc Bích | adherent của Yellow Springs |
| Psyche *(spectre_devil_name/witchgodname)* | Tâm Thức | tái dùng bản dịch đã chốt B4h |
| Labyrinth *(spectre_divine_realm)* | Labyrinth *(giữ nguyên)* | địa danh riêng WoD (mê cung giam giữ Spectre), theo B0, không có tiền lệ base |
| Hive / Hive Mind | Tổ Ong / Tâm Trí Bầy Đàn | house_of_worship và religious_head_title của Spectre — dịch nghĩa, "Hive Mind" ghép "Tâm Trí"+"Bầy Đàn" để truyền tải khái niệm ý thức tập thể |
| Arcanoi, Arcanos *(và tên riêng: Argos/Fatalism/Flux/Inhabit/Intimation/Keening/Lifeweb/Mnemosynis/Moliate/Outrage/Pandemonium/Phantasm/Puppetry/Usury)* | *(giữ nguyên)* | tái xác nhận B4h, xuất hiện dày đặc trong mọi mô tả Guild |
| Guildmaster, Guild | Hội Trưởng, Hội | chức danh/tổ chức chung |
| Artificers, Masquers, Pardoners, Usurers, Chanteurs, Harbingers, Oracles, Sandmen, Haunters, Monitors, Spooks, Proctors, Puppeteers, Alchemists, Mnemoi, Solicitors *(15 Guild Arcanoi)* | Thợ Chế Tác, Thợ Nhào Nặn, Người Xá Tội, Người Cho Vay Nặng Lãi, Ca Sĩ, Sứ Giả, Nhà Tiên Tri, Người Ru Mộng, Kẻ Ám Ảnh, Người Giám Sát, Bóng Ma, Giám Thị, Múa Rối, Nhà Giả Kim, Mnemoi *(giữ nguyên)*, Người Chào Mời | dịch nghĩa theo chức năng của mỗi Guild; "Mnemoi" giữ nguyên vì là danh xưng tự nhận không có nghĩa dịch tự nhiên rõ ràng trong tiếng Việt |
| Fetters | Fetters *(giữ nguyên)* | tái xác nhận B4h qua `[Fetters\|E]` concept-link |
| Skinlands | Skinlands *(giữ nguyên)* | tái xác nhận B4h qua `[Glossary('Skinlands','game_concept_skinlands_desc')]` — tham số 1 KHÔNG dịch vì là danh từ lõi Wraith |
| Dark Kingdom *(tham số 1 của `Glossary('Dark Kingdom','game_concept_dark_kingdom_desc')`, mô tả Yellow Springs)* | Vương Quốc Bóng Tối | dịch nghĩa vì đây là cụm tính từ mô tả thường, không phải danh từ riêng lõi hệ thống |
| Ritual of Severance | Nghi Lễ Cắt Đứt | tái dùng bản dịch đã chốt B4h |

> ⚠️ **Bẫy đã tránh:** bản gốc dùng `[UmbraGlossaryLocalized('shadowlands','Underworld')]` **6 lần** trong file này (dòng `ferrymen_religion_desc`, `ferrymen_desc`, `fishers_religion_desc`, `fishers_desc`, `yellow_springs_religion_desc`, `yellow_springs_desc`). Theo B4j đã chốt, tham số 2 ("Underworld") của macro này phải dịch → đã dịch thành `'Âm Phủ'` ở cả 6 chỗ, giữ tham số 1 (`'shadowlands'`) nguyên vẹn. Bản nháp đầu tiên đã bỏ sót bẫy này (chỉ giữ "Underworld" tiếng Anh) — phát hiện và sửa khi đối chiếu bracket giữa bản gốc/bản dịch trước khi ghi file.

## B4v. Thuật ngữ `religion/POD_religion_gaia_l_english.yml` — faith Gaia (Garou/Fera chính thống), 860/860 dòng

Nguồn: file faith trung tâm của Garou/Fera thờ Gaia, cùng vô số camp/tribe con (13 bộ tộc Garou, Bastet, Mokolé, Gurahl…). File này dùng hậu tố `:0` (1 trong 6 file đặc biệt của mod, xem TRANSLATION_RULES.md mục 6) — chỉ ở 12 dòng cuối (`holy_site_*` của Gurahl). Đối chiếu trực tiếp với B4s (`POD_religion_wyrm`, faith đối lập thờ Wyrm) vì hai file dùng chung khuôn mẫu cấu trúc (`_house_of_worship`, `_religious_symbol`, `_religious_text`, `_devotee_*`, `_priest_*`, `_bishop*`) — tái sử dụng gần như toàn bộ bản dịch đã chốt ở B4s cho các key tương ứng.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| caern / caerns *(house_of_worship)* | caern *(giữ nguyên số ít lẫn số nhiều)* | ✅ tái dùng B4s; khác B4s ở chỗ B4s giữ hậu tố `-s` tiếng Anh cho số nhiều (`"caerns"`) — ở đây áp dụng đúng mục 7 TRANSLATION_RULES.md (tiếng Việt không biến đổi số nhiều) nên số ít = số nhiều = "caern", coi là sửa nhất quán chứ không phải sai khác |
| glyph *(religious_symbol)* | phù văn | ✅ tái dùng B4s nguyên văn |
| lore *(religious_text)* | truyền thuyết | ✅ tái dùng mẫu B3g/B3h (không dùng "cổ tích" của B3x vì đó là ngữ cảnh riêng `roadofbeast`) |
| Lorekeeper(s) *(religious_head_title + mọi biến thể devotee/priest/bishop)* | Người Giữ Truyền Thuyết | ✅ tái dùng B3g/B3h, khớp với "truyền thuyết" ở trên |
| earth *(divine_realm)* | đất | dịch nghĩa thường, khác "Trái Đất" viết hoa (tên hành tinh, `gaia_good_god_earth`) |
| wilds *(positive_afterlife)* | hoang địa | đặt mới; khác "vùng hoang dã" của B4s (Wyrm's `negative_afterlife`) — chọn từ ngắn hơn "hoang địa" vì đây là cõi giới tích cực của Gaia, cần sắc thái trung tính hơn "hoang dã" |
| the spiral *(negative_afterlife)* | xoáy trôn ốc | đặt mới; mô tả cõi chết tiêu cực của tín đồ Gaia — hình ảnh xoáy ốc lặp lại vô nghĩa, dịch nghĩa trực tiếp |
| spirit *(health_god_name — danh từ thường dùng làm tên thần)* | linh hồn | ✅ tái dùng B4s nguyên văn (`wyrm_health_god_name`="linh hồn") |
| `_possessive` (`"X's"` / `"$ref$'s"`) | mẫu `"của X"` / `"của $ref$"` | ✅ tái dùng quy ước đã chốt xuyên suốt `religion/` — bỏ hậu tố `'s`, thêm "của" phía trước, kể cả khi X là một `$ref$` |
| Beast Courts | Thú Triều | ✅ tái dùng B4c, 6/6 lần dùng nhất quán |
| Changing Breeds | Chủng Biến Hình | ✅ tái dùng B4c/B4, 4/4 lần dùng nhất quán |
| Litany | Litany *(giữ nguyên)* | ✅ tái dùng B4s, 6 lần trong file này |
| Impergium | Impergium *(giữ nguyên)* | danh từ riêng WoD (sự kiện lịch sử — cuộc thanh trừng nhân loại thời tiền sử của Garou); đã xuất hiện chưa dịch ở `buildings_fera_POD`, `event_localization` — giữ nguyên nhất quán với các file đó |
| Harano | Harano *(giữ nguyên)* | danh từ riêng WoD (dạng trầm cảm/tuyệt vọng đặc thù của Garou), không có tiền lệ |
| Wyrmsign | Wyrmsign *(giữ nguyên)* | ghép "Wyrm" (bắt buộc giữ nguyên, B3) + "sign"; giữ nguyên cả cụm vì đây là thuật ngữ chuyên biệt chỉ dấu hiệu/điềm báo về Wyrm, tách "sign" ra dịch riêng sẽ phá vỡ từ ghép |
| kuklos / kukloi *(đơn vị xã hội con của Black Furies, không phải "camp" thường)* | kuklos *(giữ nguyên)* | danh từ Hy Lạp riêng của Black Furies, khác "camp"→"Trại" (B4s) dùng cho các bộ tộc khác; giữ nguyên vì là thuật ngữ chuyên biệt không có tương đương tự nhiên |
| Astral Umbra *(tham số 2 của `UmbraGlossaryLocalized('astral_reaches', …)`)* | Umbra Thiên Giới | ✅ mới đặt — lần đầu dịch giá trị này của flag `astral_reaches` (giá trị khác `'High Umbra'` gặp ở file khác chưa dịch, sẽ đặt khi tới lượt); giữ "Umbra" nguyên theo tiền lệ B3b, "Astral"→"Thiên Giới" theo tiền lệ "Celestial Arrows"→"Mũi Tên Thiên Giới" đã có trong repo |
| Nun *(orderofourmercifulmother_adherent, tín đồ nữ tu Kitô giáo trong Black Furies)* | Nữ Tu | ✅ tra base_game_vh (`nick_the_nun`="Nữ Tu") |
| Vật Tổ *(totem)* | Vật Tổ | dịch nghĩa thường, dùng cho các lần nhắc "Totem"/"totem" của Griffon, Crow, Sable trong mô tả camp; không có tiền lệ base nhưng "vật tổ" là từ tiếng Việt phổ thông sẵn có, không cần đặt thuật ngữ WoD riêng |
| sept *(đơn vị lãnh thổ/cộng đồng Garou lớn hơn caern)* | sept *(giữ nguyên)* | danh từ riêng WoD, không có tương đương tự nhiên; xuất hiện nhiều lần xuyên suốt mô tả camp |
| Balance / Trimurti / Rta *(vũ trụ luận Ấn Độ giáo của Mokolé Cosmic Order)* | Sự Cân Bằng / Trimurti / Rta | "Balance" dịch nghĩa vì là danh từ trừu tượng thường; "Trimurti", "Rta" giữ nguyên phiên âm Sanskrit gốc, không có tiền lệ base tương đương |
| Astral/Wani/Bushidō/samurai | Astral *(chỉ trong tên ghép "Umbra Thiên Giới" ở trên)* / Wani *(giữ nguyên)* / Bushidō *(giữ nguyên)* / samurai *(giữ nguyên, có tiền lệ base)* | tên riêng văn hóa Nhật Bản trong mô tả Hakken/Zhong Guo, giữ nguyên theo B0 |

> ⚠️ **Sửa sót khi tự kiểm tra:** bản nháp đầu tiên bỏ sót dịch `gaia_health_god_name: "spirit"` → "linh hồn" (đã có tham chiếu `$gaia_health_god_name$` ở 4 dòng khác cần khớp) và bỏ sót dịch tham số 2 của `UmbraGlossaryLocalized('astral_reaches','Astral Umbra')`. Cả hai phát hiện và sửa khi đối chiếu `git diff -U0` các lệnh `Glossary()`/`UmbraGlossaryLocalized()` trước khi hoàn tất, đúng quy trình mục 4 TRANSLATION_RULES.md.

## B4w. Thuật ngữ `religion/POD_religion_docrtineandtenets_l_english.yml` — toàn bộ doctrine/tenet của mọi splat, 1652/1652 dòng, việc #2 file 36/36 (HOÀN TẤT `religion/`)

Nguồn: file lớn nhất `religion/` (1652 dòng, 1121 bracket — nhiều `Glossary()`/`UmbraGlossaryLocalized()` nhất trong thư mục). Không phải 1 faith mà là **kho doctrine/tenet dùng chung cho mọi splat** (Vampire mọi Clan, Fera mọi breed/tribe, Kuei-Jin, Mummy, Demon, Wraith, Hunter, Mage, Fae) — mỗi khối là bản mẫu lặp `_name/_crime_name/_shunned_name/_accepted_name/_evil_name` + `doctrine_parameter_*_illegal/shunned/accepted`. Dịch bằng 6 agent song song theo 6 đoạn dòng (1-279, 280-560, 561-838, 839-1120, 1121-1400, 1401-1652), mỗi agent ghi ra file scratch riêng (không ghi trực tiếp vào file thật để tránh race condition khi nhiều agent cùng sửa 1 file — bài học rút ra sau khi phát hiện thiết kế ban đầu cho 3 agent đầu ghi đè trực tiếp lên cùng 1 file, đã dừng kịp trước khi mất dữ liệu), rồi điều phối viên tự ghép + đối chiếu thuật ngữ chéo giữa các đoạn trước khi hợp nhất vào file thật.

**✅ Nhãn trạng thái doctrine (bắt buộc dùng thống nhất, xuất hiện hàng trăm lần xuyên suốt religion/ từ đây về sau nếu còn gặp mẫu `_crime_name/_shunned_name/_accepted_name/_evil_name`):**

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Criminal *(`_crime_name`)* | Tội Phạm | ✅ khớp tiền lệ base `game_concept_criminal`="Tội phạm" (chỉ khác viết hoa — ở đây dùng Title Case vì là tên nhãn hiển thị độc lập, không phải câu văn) |
| Shunned *(`_shunned_name`)* | Bị Xa Lánh | ✅ base `game_concept_shunned`="Xa lánh"; thêm "Bị" theo tiền lệ đã có sẵn trong chính `religion/POD_religion_vampirespecialdoctrines_l_english.yml` (`psychic_shunned_name`="...Bị Xa Lánh") |
| Accepted *(`_accepted_name`)* | Được Chấp Nhận | đặt mới (không có tiền lệ base "Accepted" độc lập), ghép "Được" cho đối xứng với "Bị Xa Lánh" |
| Evil *(`_evil_name`)* | Tà Ác | đặt mới, dùng cho nhãn thù địch tuyệt đối (thường đi kèm câu "We will destroy them all, or die trying") |

> ⚠️ 3 trong 6 agent ban đầu tự chọn biến thể khác nhau cho "Shunned"/"Accepted" (`"Xa Lánh"` không "Bị", `"Chấp Nhận"` không "Được", `"Bị Ruồng Bỏ"` thay vì "Bị Xa Lánh") — điều phối viên đã chuẩn hóa toàn bộ về bảng trên trước khi hợp nhất. Từ nay nếu gặp mẫu này ở file `religion/` khác (không còn file nào theo WORKLIST.md, nhưng có thể tái sử dụng cho `interactions/`/`decisions/` sau này), dùng đúng 4 nhãn trên.

**Thuật ngữ mới đặt / xác nhận trong file này:**

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Masquerade *(doctrine ma cà rồng, khác `[the_masquerade\|E]` khái niệm game)* | Màn Che | đặt mới, dùng riêng cho tên doctrine; "Silence of Blood" (cụm lặp lại nhiều lần trong văn phong Kinh Litany) → "Sự Im Lặng của Máu" |
| The Veil *(doctrine tương đương của Garou/werewolf, `doctrine_werewolf_veil_*`)* | Tấm Màn | tách riêng khỏi "Màn Che" (Masquerade) dù cùng cơ chế game, vì đây là 2 khái niệm lore khác nhau ở 2 splat khác nhau |
| Oathbreaking | Phản Thệ | ghép từ Hán Việt, khớp "Kẻ Phản Thệ" (Oathbreaker trait, B4e) |
| Prodigal(s) *(cụm "X-Prodigal Pacts", "a conclave of early Prodigals")* | Kẻ Hoang Đàng | ✅ tái dùng B3z nguyên văn — 2/6 agent ban đầu dịch sai thành giữ nguyên "Prodigal" tiếng Anh hoặc phiên âm hóa thành tính từ ("Cainite Ấn Độ" thay vì "Hậu Duệ Cain người Ấn" cho `"Indian Cainites"`), điều phối viên đã sửa cả hai về đúng thuật ngữ đã khóa |
| Justicar | Justicar *(giữ nguyên)* | vì `game_concept_justicar` (nguồn `Glossary()` tham số 2 trỏ tới) trong `game_POD_concepts_l_english.yml` **bản thân nó cũng chưa dịch** — giữ nguyên nhất quán, sẽ đổi đồng loạt nếu sau này `game_POD_concepts` được dịch |
| Blush of Life, Auctoritas Ritae, Monomacy, Enkrateia, Legacy of Trinity/Ashes/Shadow *(thuật ngữ Sabbat/Tzimisce gốc WoD)* | *(giữ nguyên tên riêng, chỉ dịch câu mô tả xung quanh)* | theo B0 — thuật ngữ WoD người chơi quen đọc tiếng Anh |
| Osirian League, Cabiri, Shemsu-Heru, Apophis, Ishmaelite *(faction Mummy)* | Liên minh Osiris ✅ tái dùng B2; các tên khác giữ nguyên | không có tiền lệ dịch nghĩa cho Cabiri/Shemsu-Heru/Ishmaelite, giữ nguyên theo B0 |
| "X Hostility" *(nhãn nhóm doctrine thù địch, mẫu `<faction>_hostility_name` KHÁC `<faction>_hostility_doctrine_name`)* | "Thù Địch với X" | đặt mới, tái dùng nhất quán ở mọi lần gặp mẫu này trong file (Anda, Yomi Wan, Oblivion, Apophis, Stygia…) |
| "X-Y Pacts" *(mẫu liên minh Fae Seelie/Unseelie/Wyrm/Garou, `special_doctrine_*_pact_hostility_name`)* | "Hiệp Ước X-Y" | đặt mới, giữ nguyên thứ tự 2 vế X-Y như bản gốc |
| "Characters with the/a [trait] are [criminals\|E]/[shunned\|E]/fully accepted" *(mẫu điều kiện `doctrine_parameter_*_illegal/shunned/accepted`, ~165 dòng trong file)* | "Nhân vật có [trait] là/bị [criminals\|E]/[shunned\|E] / được chấp nhận hoàn toàn" | ⚠️ **3/6 agent (132/165 dòng) để nguyên tiếng Anh hoàn toàn** ở mẫu câu này, tưởng nhầm đây là chuỗi script nội bộ không cần dịch — thực ra đây là tooltip hiển thị cho người chơi trong UI giáo lý đức tin. Điều phối viên phát hiện qua bước rà `grep` từ tiếng Anh còn sót sau khi hợp nhất (không phải qua báo cáo của agent), rồi viết script Python thay thế mẫu câu hàng loạt (không giao lại cho agent, vì mẫu đã đủ đều để làm tay an toàn hơn) |
| Can recruit / Can employ *(mẫu tuyển quân MAA, chức vụ triều đình)* | Có thể chiêu mộ / Có thể tuyển dụng một | áp dụng cùng lúc với sửa mẫu "Characters with..." ở trên |

> ⚠️ **Bài học quy trình quan trọng nhất rút ra từ file này:** khi giao nhiều agent song song dịch các đoạn của **cùng một file**, KHÔNG được để agent ghi trực tiếp vào file thật (dù chỉ sửa đúng đoạn dòng được giao) — mỗi agent đọc-toàn file-rồi-ghi-toàn file để splice đúng đoạn của mình, nên 2 agent ghi gần như đồng thời sẽ ghi đè lẫn nhau, mất bản dịch của agent kia mà không có cảnh báo lỗi nào. Quy trình an toàn: mỗi agent chỉ ghi ra 1 file scratch riêng (đường dẫn ngoài repo), điều phối viên tự đọc tất cả file scratch, đối chiếu thuật ngữ chéo, rồi tự ghép + ghi 1 lần duy nhất vào file thật.
>
> Bài học thứ hai: **3 lớp kiểm tra kỹ thuật (đếm token/bracket/ref, kiểm tra BOM/CRLF, diff ID) đều PASS 100%** dù có ~165 dòng bị bỏ sót hoàn toàn (không dịch 1 chữ nào) — vì các dòng đó vẫn giữ nguyên cấu trúc bracket/ref hợp lệ, không "hỏng" theo nghĩa kỹ thuật. Chỉ phát hiện được nhờ bước `grep` riêng tìm từ tiếng Anh thông dụng (`the/and/of/with/are/is...`) loại trừ script ID, đúng như cảnh báo ở TRANSLATION_RULES.md mục 8 rằng đếm token không đủ — nhưng ở quy mô lớn hơn nhiều so với các lỗi lẻ tẻ 1-2 dòng đã gặp trước đây.

## B4x. Thuật ngữ Resonance intensity (từ `custom_localization/POD_resonance_custom_loc_l_english.yml`)

File chỉ có 4 dòng chữ thật; 16 dòng `POD_<temperament>_N_i` là tooltip-ID/icon thuần (không dịch), 4 dòng `POD_resonance_flavor_*` là concept-link thuần (không dịch). Không có tiền lệ dịch 4 tính từ mức độ Resonance (`negligible/fleeting/intense/acute`) trong `base_game_vh` hay TERMINOLOGY.md, nên đặt mới theo nghĩa dễ hiểu (ưu tiên hơn thuật ngữ y học cổ Hy Lạp gốc của 4 temperament Choleric/Phlegmatic/Melancholy/Sanguine mà các tính từ này mô tả mức độ):

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| negligible *(POD_resonance_intensity_1)* | không đáng kể | mức thấp nhất |
| fleeting *(POD_resonance_intensity_2)* | thoáng qua | mức 2 |
| intense *(POD_resonance_intensity_3)* | mạnh mẽ | mức 3 |
| acute *(POD_resonance_intensity_4)* | gay gắt | mức cao nhất |

Ghi chú: đây chỉ là các tính từ mức độ dùng chung cho cả 4 temperament (ví dụ "acute Sanguine Resonance"); tên riêng 4 temperament (Choleric/Phlegmatic/Melancholy/Sanguine) và ID `#TOOLTIP:*_RESONANCE_0N_TT` không thuộc phạm vi dịch của file này — nội dung tooltip thật nằm ở file khác ngoài `custom_localization/`.

**Cập nhật (file `gui/POD_see_resonance_l_english.yml`, nội dung tooltip thật nói ở trên):** 20 dòng, cấu trúc `#bold <Temperament> Resonance#!\nThis character has blood with <intensity> [<temperament>_lifestyle|E]`. Đã dịch bằng 4 bảng cường độ B4x (`negligible→không đáng kể`, `fleeting→thoáng qua`, `intense→mạnh mẽ`, `acute→gay gắt`) và câu khung `This character has blood with → Nhân vật này có máu với`. **Quyết định mới:** giữ nguyên tiếng Anh "Choleric/Phlegmatic/Melancholy/Sanguine Resonance" trong cả `#bold...#!` header — áp dụng cùng logic B0 (thuật ngữ WoD giữ nguyên, chưa có tiền lệ dịch nghĩa, và concept nguồn `game_concept_choleric_lifestyle` v.v. trong `game_POD_concepts_l_english.yml` **bản thân cũng chưa dịch** — giữ nguyên nhất quán chờ file gốc dịch trước, theo đúng tiền lệ "Justicar" ở bảng trên). `[choleric_lifestyle|E]` v.v. là concept-link tới `game_concept_choleric_lifestyle` = "Choleric Resonance" — không đổi tham số trong bracket. Nếu sau này `game_POD_concepts_l_english.yml` dịch tên 4 temperament sang tiếng Việt, phải quay lại đổi đồng loạt ở đây và ở `focuses_POD_l_english.yml`, `POD_discipline_lifestyle_l_english.yml` cho khớp.

## B4y. "Reweaving" (từ `gui/POD_reweaving_l_english.yml`), việc #2

File 19 dòng: tên và các nhãn con của cửa sổ GUI đổi đặc tính nhân vật (`TRAIT_CHANGE_WINDOW_*`), mở ra từ interaction Fae `POD_reweaving_interaction` (thuật thuật của Changeling dùng Truename để sửa lại đặc tính cốt lõi của một người/vật — xem `lifestyles/POD_fae_lifestyle_l_english.yml` key `reweaving_perk_name`/`REWEAVING_PERK_EFFECT` khi tới lượt). Đây **không phải** danh từ riêng "Weaver" của Garou/Wyrm (đã chốt giữ nguyên tiếng Anh ở B3/B4s) — không áp dụng quy tắc "Wyld/Weaver/Wyrm giữ nguyên". "Reweaving" ở đây là **động từ thường** mô tả hành động dệt lại true-name/đặc tính, nên dịch nghĩa.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Reweaving *(TRAIT_CHANGE_WINDOW_TITLE, tên cửa sổ)* | Dệt Lại | dịch nghĩa; đối chiếu `simp_chinese` dùng "再织造" (Tái Dệt/Dệt Lại) cho cùng key — xác nhận đây là ẩn dụ "dệt lại" thông thường của thuật Fae, không phải danh xưng Weaver splat |
| Change Trait *(TRAIT_CHANGE_WINDOW_CHANGE, nút hành động)* | Đổi Đặc Tính | ngắn gọn cho nút UI |
| Trait *(trong các nhãn `TRAIT_CHANGE_WINDOW_*`)* | Đặc Tính | dùng "Đặc Tính" thay "Trait" xuyên suốt file này cho ngắn gọn (UI chật); nếu file khác đã có tiền lệ dịch "trait" khác (ví dụ "Tính Trạng") cần đối chiếu lại khi gặp |

Áp dụng lại khi tới `POD_reweaving_interaction`/`POD_reweaving_interaction_desc` (`interactions/POD_character_interactions_fae_l_english.yml`) và `reweaving_perk_name`/`REWEAVING_PERK_EFFECT` (`lifestyles/POD_fae_lifestyle_l_english.yml`): dùng cùng "Dệt Lại" cho tên interaction/perk, giữ nhất quán với tên cửa sổ GUI ở đây.

## B4z. "Hideout" (Vampire domicile type, từ `gui/POD_mod_compatibility_l_english.yml`), việc #2

Chưa có tiền lệ dịch trước khi file này được dịch (kiểm tra `TERMINOLOGY.md`, `buildings/`, `common/buildings/` đều không có). Key gốc `haven_landed_domicile_type` (`buildings/building_domicile_POD_l_english.yml`, chưa dịch) dùng "Hideout" cho loại công trình domicile của Vampire.

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Hideout *(building/domicile type của Vampire)* | Nơi Ẩn Náu | dịch nghĩa, phù hợp lore (chỗ trú ẩn ma cà rồng); áp dụng lại khi dịch `buildings/building_domicile_POD_l_english.yml` (key `haven_landed_domicile_type` và các key liên quan) để giữ nhất quán |

## B5a. "Quincunx" (từ `gui/POD_quincunx_l_english.yml`), 37/37 dòng

File 37 dòng, toàn bộ đã bị comment-out trong bản gốc tiếng Anh (mỗi dòng dạng ` #key: "..."` — dấu `#` ngay sau 1 space đầu dòng, không phải cú pháp key thường ` key: "..."`). Đã dịch giữ đúng định dạng comment này (không bỏ `#`, không tự bật lại). Nội dung: hệ thống chính trị/tài nguyên "Zeal" (Nhiệt Thành) của tổ chức Kuei-jin cấp cao gọi là "Quincunx" — hoàn toàn khác Tremere Pyramid (đã tra `TERMINOLOGY.md` xác nhận không liên quan; Quincunx chỉ xuất hiện cùng `August Court`, `August Ancestor`, `Kuei-jin` — thuộc nhóm thuật ngữ Kuei-jin B3c/B3e, không phải nhóm Tremere B3n).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Quincunx *(tổ chức chính trị cấp cao của Kuei-jin, tab_quincunx)* | Ngũ Hành Hội | không có tiền lệ base (danh từ riêng WoD hiếm); dịch nghĩa vì "quincunx" = hình sắp xếp 5 điểm kiểu hoa mai, hợp nghĩa "ngũ hành" trong văn hóa Hán mà Kuei-jin lấy cảm hứng; đối chiếu `simp_chinese/gui/POD_quincunx_l_simp_chinese.yml` dùng "五行宗" (Ngũ Hành Tông) xác nhận hướng dịch nghĩa theo ngũ hành là hợp lý; dùng "Hội" thay "Tông" vì đây là hội đồng/triều đình chính trị, không phải môn phái tu luyện |

## B5e. "Unburden" (Grand City character interaction, từ `interactions/POD_character_interactions_grand_city_l_english.yml`), việc #5

Không có tiền lệ trong `base_game_vh` (không phải khái niệm vanilla) và chưa có trong `TERMINOLOGY.md`. Interaction cho phép nhân vật từ bỏ một stress trait tiêu cực (thông qua `POD_unburden_*`, mỗi key ứng với một trait vanilla đã có bản dịch sẵn trong `traits_l_english.yml`: Bợm Rượu/drunkard, Tự Hành Xác/flagellant, Ăn Uống Giải Sầu/comfort_eater, Ăn Năn/contrite, Hoang Tán/improvident, Chán Ăn/inappetetic, Ẩn Dật/reclusive, Cáu Kỉnh/irritable, Trác Táng/rakish, Phung Phí/profligate, Cường Tráng/athletic, Viết Nhật Ký/journaller, Tâm Sự/confider). `hashishiyah` là trait POD-specific, không có tiền lệ base; giữ "hashish" nguyên như base_game_vh đã làm (`stress_hashish_habit` → "Thói Quen Hút Hashish").

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Unburden *(character interaction, POD_grand_city_unburden_interaction)* | Trút Bỏ Gánh Nặng | dịch nghĩa ("un-" + "burden" = trút bỏ gánh nặng), không có tiền lệ; áp dụng nhất quán nếu key `unburden` xuất hiện lại ở file khác |
| hashish *(trait `hashishiyah`, chỉ dùng trong `POD_unburden_hashishiyah`)* | hashish *(giữ nguyên)* | theo tiền lệ base `stress_hashish_habit` = "Thói Quen Hút Hashish" — không dịch thành "cần sa"/"thuốc phiện" |
| Zeal *(quincunx_influence, tài nguyên/điểm ảnh hưởng của Quincunx)* | Nhiệt Thành | tái dùng nghĩa "Zeal"→"Nhiệt thành" đã có trong `base_game_vh` (`modifiers_l_english.yml` key `player_facing_ai_zeal`), viết hoa "Nhiệt Thành" khi dùng như tên tài nguyên riêng |
| August Court *(chính thể/triều đình cai trị Kuei-jin, quincunx_county_mod)* | Thượng Triều | đặt mới; "August" ở đây là tính từ tôn xưng ("cao quý, tôn kính") giống trong `August Personage of Jade`→"Ngọc Hoàng" (B3c) chứ không dịch chữ-đối-chữ; "Thượng" ngắn gọn mang nghĩa cao quý/tối cao, hợp UI chật |
| August Ancestor *(cấp bậc Kuei-jin cao nhất, thành viên Quincunx)* | Thượng Tổ | ghép "Thượng" (như August Court) + gốc "Tổ" từ "Ancestor"→"Tổ Tiên" (đã chốt B3, dòng 614) để nhất quán và ngắn gọn |
| Ancestor *(ancestor_kueijin, cấp bậc Kuei-jin thường)* | Tổ Tiên | ✅ tái dùng tiền lệ đã chốt (dòng 614 TERMINOLOGY.md, hệ đẳng cấp Kuei-jin) |
| Twilight War / Promote Twilight War | Chiến Tranh Hoàng Hôn / Cổ Vũ Chiến Tranh Hoàng Hôn | ✅ tái dùng gốc "Twilight War(s)"→"Hoàng Hôn" đã chốt (dòng 680, từ cặp Midnight/Twilight Warrior-General-Master) |
| Midnight War / Promote Midnight War | Chiến Tranh Nửa Đêm / Cổ Vũ Chiến Tranh Nửa Đêm | ✅ tái dùng gốc "Midnight War(s)"→"Nửa Đêm" đã chốt (dòng 680) |
| Edicts *(QUINCUNX_WINDOW_TAB_EDICTS, tab sắc lệnh)* | Sắc Lệnh | dịch nghĩa phổ thông, không có tiền lệ base riêng cần đối chiếu |

Áp dụng lại khi gặp lại các khái niệm này ở file khác (nếu có): `Quincunx`→"Ngũ Hành Hội", `August Court`→"Thượng Triều", `August Ancestor`→"Thượng Tổ", `Zeal` (nghĩa tài nguyên Kuei-jin, không phải tính từ chung)→"Nhiệt Thành".

## B5b. "Ephorate" và cấp bậc nội bộ Ventrue (từ `gui/POD_ventrue_ephorate_l_english.yml`), 151/151 dòng

File 151 dòng, mô tả tổ chức chính trị nội bộ của clan Ventrue: Ephorate (12 elder quyền lực nhất) và các cấp bậc dưới quyền — Ephor, Lictor, Tribune, Strategoi — cùng 5 phe phái (Patricians, Eternal Senate, Sinner Rome, Merchant Princes, Ashen Knights).

**Quyết định: giữ nguyên toàn bộ các danh xưng Hy Lạp/La Mã cổ, không dịch nghĩa.**

| English | Xử lý | Ghi chú |
|---|---|---|
| Ephorate *(tổ chức 12 elder Ventrue quyền lực nhất)* | Giữ nguyên "Ephorate" | không có tiền lệ base_game_vh; đây là danh từ riêng lịch sử (ephor = quan chức giám sát ở Sparta cổ đại), không phải danh từ chung có thể dịch nghĩa gọn; dịch thành "Hội Đồng Giám Sát" sẽ làm mất sắc thái cổ điển Hy Lạp mà lore World of Darkness cố tình dùng, và không ngắn hơn bản gốc |
| Ephor(s) *(thành viên Ephorate)* | Giữ nguyên "Ephor" | cùng nhóm danh xưng lịch sử với Ephorate |
| Lictor(s) *(cảnh sát ngầm/phản ứng nhanh của Ephorate)* | Giữ nguyên "Lictor" | danh xưng La Mã cổ (cận vệ mang bó gậy fasces); không có tiền lệ base, nhưng cùng nhóm với Strategos/Strategoi mà base_game_vh đã giữ nguyên (`dlc_ep3_game_concepts_l_english.yml` dòng 14-17, game_concept chính thức không dịch) |
| Tribune(s) *(mật vụ/thông tin viên cấp thấp nhất của Ephorate)* | Giữ nguyên "Tribune" | danh xưng La Mã cổ (quan bảo dân); base_game_vh cũng giữ nguyên "tribunes" khi xuất hiện trong bối cảnh tương tự (`dlc_ep2_locale_events_l_english.yml` dòng 448, không dịch) |
| Strategoi / Strategos *(đặc vụ trực tiếp của các Ephor)* | Giữ nguyên "Strategoi"/"Strategos" | ✅ tái dùng tiền lệ base_game_vh đã chốt — giữ nguyên trong game_concept chính thức (`dlc_ep3_game_concepts_l_english.yml` dòng 14-17: `game_concept_strategos: "Strategos"`, `game_concept_strategoi: "Strategoi"`) và trong tên riêng (`bookmark_call_of_the_empire_1178_l_english.yml`: "Strategos Andronikos") |
| Patricians / Patriarchs, Eternal Senate / Antasians, Sinner Rome, Merchant Princes, Ashen Knights *(5 phe phái Ephorate)* | Giữ nguyên tên tiếng Anh | tên riêng phe phái trong lore, giữ nguyên như POD giữ nguyên tên clan/dòng máu; không dịch nghĩa để tránh dài dòng trong UI chật |
| Road of Kings, Road of Humanity, Road of Sin, Path of the Merchant *(hệ thống đạo lý/Road trong WoD, xuất hiện dạng chú giải song ngữ)* | Dịch nghĩa kèm tên gốc trong ngoặc | "Con Đường Đế Vương (Road of Kings)", "Con Đường Nhân Tính (Road of Humanity)", "Con Đường Tội Lỗi (Road of Sin)", "Con Đường Con Buôn (Path of the Merchant)" — đặt mới, dịch nghĩa vì đây là mô tả lore cho người đọc chưa biết WoD, giữ tên gốc trong ngoặc để tra cứu chéo với các file khác nhắc đến cùng khái niệm |

Áp dụng lại khi gặp lại các khái niệm này ở file khác (nếu có): `Ephorate`/`Ephor`/`Lictor`/`Tribune`/`Strategoi`/`Strategos` đều giữ nguyên tiếng Anh, không dịch.

## B5c. Thuật ngữ `gui/POD_craft_l_english.yml` — UI chế tác (Craft/Alchemy/Smith/Forge/Enhance/Automaton), 1187/1187 dòng, việc #4 file 27/30

File giao diện chế tác hiện vật. Dịch qua 4 agent chia đoạn (1-403, 404-825, 826-1049, 1050-1187), coordinator hợp nhất thủ công + chuẩn hóa thuật ngữ lệch giữa các đoạn trước khi ghi vào file thật.

**⚠️ Độ hiếm Artifact Piece — chốt cứng cho toàn repo (sẽ tái xuất hiện ở `artifacts/`, `lifestyles/`, nhiều file khác dùng `POD_rarity_*`):**

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Common *(độ hiếm hiện vật)* | Thường | |
| Masterwork *(độ hiếm hiện vật)* | Tinh xảo | 2 agent khác nhau ban đầu dùng "Chế Tác Bậc Thầy" và "Tuyệt Tác" ở vài chỗ — đã chuẩn hóa thống nhất về "Tinh xảo" (chữ thường, viết hoa đầu câu tùy ngữ cảnh UI) trên toàn file |
| Famed *(độ hiếm hiện vật)* | Danh tiếng | tương tự, đã sửa từ "Nổi Danh"/"Trứ Danh" |
| Illustrious *(độ hiếm hiện vật)* | Lừng lẫy | tương tự, đã sửa từ "Lẫy Lừng"/"Tuyệt Tác" |

**Artifact Piece** → "Mảnh Hiện vật"/"Mảnh Cổ vật" (2 cách gọi cùng khái niệm xuất hiện trong file — "Hiện vật" ở nhóm `GAINS/LOSES/HAS_..._ARTIFACT_PIECES`, "Cổ vật" ở nhóm `material_*_artifact_piece`; chưa thống nhất 1 từ duy nhất, cân nhắc rà lại khi gặp `artifacts/` việc #11).

**Reweave/Reweaving** → "Dệt Lại" ✅ tái dùng B4y, áp dụng cho `reweave_*_method`, `node_reweave_*_loca`.

**Tên hiện vật riêng (Mokolé/Garou, dòng 1033-1042, 1067-1071):**

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Lungin | Lungin *(giữ nguyên)* | không rõ từ nguyên, không dịch được — cần xác nhận lại nếu gặp ngữ cảnh khác |
| Arrows of the Sun | Mũi Tên Mặt Trời | đã chuẩn hóa (2 agent ra 2 biến thể "Mũi Tên Của Mặt Trời"/"Những Mũi Tên Mặt Trời") |
| Thunder Dart | Phi Tiêu Sấm Sét | |
| Edge of the Sun | Lưỡi Kiếm Mặt Trời | bản gốc gọi là "machete"; chọn "Lưỡi Kiếm" cho gọn, không dịch sát "mã tấu" |
| Blade of the Kings | Lưỡi Kiếm Của Các Vương | "Kings" = "Lizard Kings"/Vương Thằn Lằn của Mokolé, không phải vua người |
| Archid | Archid *(giữ nguyên)* | dạng biến hình lớn nhất của Mokolé, không có tiền lệ dịch |

**Vũ khí/áo giáp/đồ vật chế tác (forge_name, dòng ~911-938)** — tra `base_game_vh` theo key vanilla tương đương: Axe→Rìu chiến, Hammer→Búa chiến, Spear→Giáo, Mace→Chùy, Dagger→Dao găm, Sword→Kiếm, Plate/Scale/Lamellar/Brigandine/Mail Armor→Giáp tấm/vảy/phiến/phân đoạn/xích, Crown→Vương miện, Regalia→Nghi trượng, Throne→Ngai vàng, Amulet→Bùa hộ mệnh (từ `adventurer_name_sections_l_english.yml`), Durability→Độ bền (từ `dlc_ep1_game_concepts_l_english.yml`).

**Elixir/Potion/Tonic/Philtre** — 4 loại "thuốc" khác nhau trong hệ crafting POD, phân biệt: Potion→Thuốc, Elixir→Linh dược, Tonic→Bổ dược, Philtre→Mê dược. Intrigue→"Mưu kế" (áp dụng cho cả lỗi chính tả gốc `node_alchemy_skill_intrigue_loca: "Elixir of Intiruge"` — dịch đúng nghĩa "Intrigue", không giữ lỗi chính tả vì đây là chữ hiển thị không phải key).

Áp dụng lại 4 bảng thuật ngữ trên khi gặp lại ở `artifacts/` (việc #11), `modifiers/` (việc #7 — các `*_modifier` như `divine_elixir_diplomacy_modifier` định nghĩa tên thật của elixir, chưa dịch).

## B5d. Thuật ngữ `gui/POD_umbra_window_l_english.yml` — cửa sổ cõi giới Umbra, 1572/1572 dòng, việc #4 file 28/30 (HOÀN TẤT `gui/`, 30/30)

File lớn nhất `gui/`. Dịch qua 6 agent chia đoạn (1-160, 161-324, 325-540, 541-798, 799-1189, 1190-1572), coordinator hợp nhất + phát hiện/sửa 17 dòng sót tiếng Anh (13 dòng `court_of_*_effect_desc` giống hệt nhau + 4 dòng `*_duchy_effect_desc`, các agent nhầm tưởng đây là dòng script-only vì đứng cạnh dòng `$ref$`-only khác) + chuẩn hóa 4 thuật ngữ lệch giữa các đoạn.

**Chuẩn hóa thuật ngữ `Glossary()` tham số 1 xuyên suốt file (tái dùng tiền lệ đã chốt B3c/dòng 1736, không tự đặt mới):**

| English (tham số 1 gốc) | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Dark Kingdom(s) | Vương Quốc Bóng Tối | ✅ tái dùng tiền lệ dòng 1736; 1/24 agent để sót tiếng Anh, đã sửa |
| Home Realm | Cõi Giới Gốc | đặt mới nhất quán, 2/6 lần lệch đã sửa |
| Yama King(s) | Diêm Ma Vương / Các Diêm Ma Vương | ✅ tái dùng tiền lệ B3c dòng 342; 3/7 lần agent dịch nhầm "Vua Yama", đã sửa |
| Stable Point(s) | Điểm Ổn Định / Các Điểm Ổn Định | đặt mới nhất quán |
| Nightmare Realm(s), Dream Realm(s), Shard Realm, Shade Realm, Skinlands | *(giữ nguyên tiếng Anh)* | chưa có tiền lệ dịch nghĩa, giữ nguyên nhất quán theo B0 |

**Umbra Realm — quy tắc chung đã áp dụng:** tên cõi giới ngắn/mô tả rõ nghĩa → dịch (Goblin Market→Chợ Yêu Tinh, Sea of Silver→Biển Bạc, Abyss→Vực Thẳm, Oblivion→Hư Vô…); tên riêng/phiên âm ngoại lai khó dịch → giữ nguyên (Mahâraurava, Chakravada, Malfeas, Kakuri…, kể cả tên có dấu Latin trông giống tiếng Việt như "â" trong Mahâraurava — KHÔNG được sửa/bỏ dấu); tên Tribe Garou (Black Furies, Get of Fenris, Silver Fangs…) giữ nguyên tiếng Anh xuyên suốt (khác với `wyrm`/`gaia` trước đây chưa nhất quán, xem cảnh báo cũ trong WORKLIST.md — file này áp dụng "giữ nguyên" làm chuẩn); "Court of X"/"Homeland of X" (X = tên thần Garou Astrology hoặc Tribe) giữ nguyên cụm tiếng Anh trong tên hiển thị, chỉ dịch phần mô tả văn xuôi.

**Tên hành tinh (Mage lore):** Mercury/Venus/Mars/Jupiter/Saturn/Uranus/Neptune/Pluto/Sun/Moon → Sao Thủy/Kim/Hỏa/Mộc/Thổ/Thiên Vương/Hải Vương/Diêm Vương/Mặt Trời/Mặt Trăng.

**Wyld/Weaver/Wyrm** → giữ nguyên tiếng Anh xuyên suốt kể cả trong tên cõi giới ghép ("Weaver Reaches", "Wyld Reaches", "Wyrm Reaches") — ✅ tái dùng B3.

**Fetish** (đồ vật ràng buộc linh hồn của Fera/Garou, khác nghĩa "witch's fetish" thông thường) → đặt mới **"Bùa Chú"** (3/6 đoạn dùng nhất quán, không xung đột). Chưa có trong TERMINOLOGY.md trước đây — ghi nhận tại đây. Cần đối chiếu lại khi dịch `game_POD_concepts_l_english.yml` (`game_concept_fetish: "Fetish"`, chưa dịch) và `[fetish|E]`/`[fetish_smithing|E]` concept link ở các file khác để xem có nên thống nhất hay giữ khác biệt theo splat.

Áp dụng lại các bảng trên khi gặp lại ở `game_POD_concepts_l_english.yml` (việc #9, nguồn định nghĩa gốc nhiều khái niệm `game_concept_*` file này tham chiếu qua `Glossary()`), `religion/` (đã xong, không cần sửa lại), và các file `event_localization/POD_umbra/` (việc #13, chưa tới lượt).

## B5f. "Coterie" (từ `interactions/POD_character_interactions_coterie_l_english.yml`), việc #5 file 1

File 27/27 dòng, dịch xong 100%. Cụm tương tác tạo/mời/đuổi/giải tán Coterie (nhóm ma cà rồng thân cận, khái niệm gốc VtM).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Coterie | Coterie *(giữ nguyên)* | danh từ tổ chức lõi VtM, chưa có tiền lệ dịch ở bất kỳ file POD nào; áp dụng B0 tương tự tiền lệ `pack` (B4r dòng 1611) — nhóm ma cà rồng Camarilla, cộng đồng quen đọc tiếng Anh, dịch nghĩa ("bang hội", "nhóm") sẽ đụng nghĩa chung và dài dòng hơn UI cho phép |

`PODCoterie`/`PODGetCoterieName`/`PODCoterieNoTooltip` là hàm data-binding (`GetPlayer.Custom(...)`), không phải chữ hiển thị trực tiếp — tự thay bằng "Coterie" (kèm/không kèm tên riêng) khi hiển thị trong game; không có gì để dịch ở tham số `'...'` của các hàm này.

## B4cat1. Thuật ngữ category menu tương tác (từ `interactions/POD_categories_l_english.yml`, 32/32 dòng, việc #5)

Nguồn: file định nghĩa tên category hiển thị trong menu tương tác nhân vật + key `*_ACTIONS` nội bộ tương ứng (đối chiếu `base_game_vh/localization/english/interactions/categories_l_english.yml` dùng mẫu "hành động X" chữ thường cho các key `*_ACTIONS`, đã áp dụng lại mẫu này).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Grand City *(category, không phải `game_concept_grand_city` — file gốc chưa dịch)* | Đại Thành | đặt mới, chưa có tiền lệ; đối chiếu lại khi dịch `game_POD_concepts_l_english.yml` (`game_concept_grand_city: "Grand City"`, 5 Grand City: Eternal Rome, Constantinople, Paris, Cairo, Jerusalem) để thống nhất |
| Journey(s) | Hành Trình | tái dùng cách gọi đã xuất hiện ở `religion/POD_religion_roadofbeast_l_english.yml` ("Con Đường Hành Trình") và `gui/POD_achievement_l_english.yml` ("Hành Trình Vatican"); áp dụng lại cho `game_concept_journey`/`game_concept_journeys` khi tới file đó |
| Coterie | Coterie *(giữ nguyên)* | danh từ WoD lõi, không có khái niệm vanilla tương đương, theo B0; xuất hiện lặp lại qua `[GetPlayer.Custom('PODCoterie')]`/`PODCoterieNoTooltip` ở nhiều file khác — giữ nguyên nhất quán |
| Sect | Giáo phái | tái dùng B4e (`sect`→"giáo phái", đã chốt ở `raktasadhus_desc`) |
| Spirit *(category, danh từ splat)* | Linh thể | tái dùng `trait_spirit`="Linh thể" (B4c) |
| Psychic | Người Có Năng Lực Ngoại Cảm | tái dùng tiền lệ đã đặt trước đó (dòng ~1193) |
| Fae *(category ngắn cho splat `trait_fae`)* | Fae Chân Chính | tái dùng `trait_fae`="Fae Chân Chính" (đã chốt, KHÔNG dịch trơn "Fae") |
| Vampire/Wraith/Ghoul/Mummy/Demon/Mage/Possessed/Fera/Holy Arts | Ma cà rồng/Oan hồn/Bộc huyết/Xác ướp/Ác quỷ/Pháp sư/Bị Chiếm Hữu/Fera/Thánh Thuật | tái dùng nguyên trạng các bảng đã chốt ở B4/B4h (`trait_*`) và Holy Arts đã đặt trước |

Key `*_ACTIONS` (nội bộ, dùng mẫu vanilla "hành động X" chữ thường): tất cả 16 key dịch theo mẫu "hành động " + tên splat/category số ít không viết hoa (`VAMPIRE_ACTIONS`→"hành động ma cà rồng", `GRAND_CITY_ACTIONS`→"hành động đại thành", `JOURNEYS_ACTIONS`→"hành động hành trình", `COTERIE_ACTIONS`→"hành động coterie", v.v.), trừ `HOLYARTS_ACTIONS` giữ "Thánh Thuật" viết hoa (bản gốc tiếng Anh cũng viết hoa "Holy Arts" khác các key khác toàn chữ thường, giữ theo cách viết gốc).

## B5g. Thuật ngữ `interactions/POD_character_interactions_spirits_l_english.yml`, 29/29 dòng, việc #5

File tương tác Garou/Fera với Linh hồn (Spirit): học Ngôn ngữ Linh hồn, triệu hồn Linh hồn, lập Hiệp ước, Cống Vật, tăng cường Tà Linh, chịu chiếm hữu.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Summon Spirit *(tên tương tác)* | Triệu hồn Linh hồn | đặt mới; `spirit`="linh hồn" đã chốt (B4/B4s, dùng 20+ lần trong base); "Triệu hồn" khác "Gọi hồn" (đã dùng cho Necromancy, `trait_necromancy`="Thuật Gọi Hồn") — tránh trùng với thuật gọi hồn ma cà rồng, vì đây là Garou/Fera triệu tập một thực thể linh hồn sống, không phải thuật gọi hồn người chết |
| Spiritual Pact / `[spirit_pact\|E]` | Hiệp ước Linh hồn | đặt mới; concept link `[spirit_pact\|E]` giữ nguyên (key), chỉ dịch tên tương tác hiển thị trực tiếp |
| Chiminage | Cống Vật | tái dùng nguyên trạng bản dịch đã có ở `gui/sorcery_POD_l_english.yml` (`spell_false_chiminage_name`="Cống Vật Giả") — nghi thức Garou/Fera hiến tặng linh hồn để đổi lấy sự giúp đỡ |
| Bane (Spirit) | Tà Linh | tái dùng B4c (`Bane`="Tà Linh", linh thể bị Wyrm làm ô uế) |
| Gaian *(tính từ splat, "Gaian Spirit")* | Gaian *(giữ nguyên)* | chưa có bản dịch nghĩa nào cho tính từ này ở bất kỳ file POD nào (kể cả `religion/POD_religion_gaia_l_english.yml` — file này chưa dịch); theo B0 giữ nguyên tên riêng/tính từ gốc cho đến khi file gaia được dịch và chốt cách xử lý chung |
| Submit to [possession\|E] | Khuất phục trước [possession\|E] | đặt mới; concept link `[possession\|E]` giữ nguyên; "possess" (động từ, "to possess you") → "chiếm hữu", tái dùng B4 (`Possessed`="Bị Chiếm Hữu") |
| "Is busy" *(lý do tương tác không khả dụng)* | "Đang bận" | đặt mới, không có tiền lệ tương tự trong base_game_vh; dịch tự nhiên cho tooltip lý do bị khóa |

## B5h. Thuật ngữ `interactions/POD_character_interactions_debug_l_english.yml` — tương tác debug (dev tool), 61/61 dòng, việc #5

File tương tác debug (menu dev tool, người chơi bật debug mode để test): dịch chuyển, giết nhân vật, ép vào ngục, hoàn tất hành trình, nạp trait XP, nạp năng lượng, phát hiện Umbra, hiện Võ Dũng thật, sửa tư thế/màu trang phục/shader/chân dung Vicissitude, thêm Nửa-Splat, dạy Chú Thuật Sự Sống, tạo bản đồ Umbra, biến thành Nhà Phiêu Lưu Vô Địa.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Squared Distance | Khoảng Cách Bình Phương | đặt mới, thuật ngữ hình học thường, không có tiền lệ WoD/CK3 |
| Kill Character | Giết Nhân Vật | đặt mới; `slay_character_interaction` (vanilla, không dịch được vì thuộc `base_game_vh` chỉ còn key) được nhắc tới nguyên trạng qua `$slay_character_interaction$`, không đổi |
| Force into Prison | Ép vào Ngục | đặt mới; "prison"→"ngục" theo cách dùng thường của base cho nhà tù CK3 |
| Teleport | Dịch Chuyển | đặt mới, dịch nghĩa thường |
| "wheeee" *(placeholder desc vui của dev)* | "hoooo" | dòng debug đùa của tác giả mod, không có nghĩa thật; dịch tự do giữ tính hài hước tương đương, không dịch sát nghĩa |
| Journey (tên tương tác/hành động) | Hành Trình | tái dùng B4cat1 đã chốt (`Journey(s)`→"Hành Trình"); áp dụng cho `POD_debug_instacomplete_journey_interaction` |
| Trait Experience / Trait XP | Kinh Nghiệm Trait | đặt mới; giữ "Trait" nguyên (chưa có bản dịch nghĩa thống nhất cho "trait" nói chung trong repo — các file đã dịch chỉ dịch tên trait cụ thể, không dịch từ "trait" chung); "Experience"→"Kinh Nghiệm" dịch nghĩa thường |
| Refill Energy / energy vessels / "mana bar" | Nạp Đầy Năng Lượng / bình năng lượng / "thanh mana" | đặt mới; "mana" giữ nguyên trong dấu ngoặc kép lồng (thuật ngữ game phổ biến, đã có tiền lệ giữ nguyên ở nhiều RPG Việt hóa); "vessel"→"bình" theo nghĩa vật chứa |
| Gain [umbra\|E] Discovery | Nhận Phát Hiện [umbra\|E] | đặt mới; `[umbra\|E]` là concept link giữ nguyên key, "Umbra" hiển thị của nó giữ nguyên theo B0/B4v (`Umbra`→giữ nguyên) |
| Prowess (uncapped) | Võ Dũng (không giới hạn) | tái dùng `game_concept_prowess`="Võ dũng" (base, `game_concepts_l_english.yml:735`), viết hoa theo quy ước tên nút giao diện |
| Idle Pose | Tư Thế Nghỉ | đặt mới, dịch nghĩa thường cho pose mặc định của nhân vật khi đứng yên |
| Clothing Colors / Personal Colors / Coterie Colors / House Colors | Màu Trang Phục / Màu Cá Nhân / Màu Coterie / Màu Gia Tộc | "Coterie" giữ nguyên theo B5f/B4cat1 đã chốt; "House"→"Gia Tộc" theo cách base dùng cho `house|E` (khác `dynasty`="Triều đại") |
| Portrait Shader Playground / Event Shader Test / Toggle Portrait Modifiers | Khu Thử Nghiệm Shader Chân Dung / Thử Nghiệm Shader Sự Kiện / Bật/Tắt Hiệu Ứng Chân Dung | đặt mới; "Shader" giữ nguyên (thuật ngữ kỹ thuật đồ họa, không có bản dịch tiếng Việt phổ biến, tương tự cách các mod Việt hóa khác giữ nguyên "shader"); "Modifier"→"Hiệu Ứng" (khác `game_concept_modifier` nếu có, nhưng ở đây ngữ cảnh là hiệu ứng hình ảnh chân dung, không phải modifier gameplay) |
| Vicissitude Portrait Editor | Bộ Sửa Chân Dung Vicissitude | "Vicissitude" giữ nguyên theo tiền lệ đã chốt (`trait_vicissitude`, `traits_POD_l_english.yml:430`) |
| Half-Splat | Nửa-Splat | đặt mới; "Splat" giữ nguyên theo B4 (khung phân loại chủng loài WoD, không dịch), ghép tiền tố "Nửa-" dịch nghĩa "Half-" |
| Spell of Life | Chú Thuật Sự Sống | đặt mới, dịch nghĩa; "Spell"→"Chú Thuật" (chưa có tiền lệ thống nhất cho "spell" chung trong repo, chọn từ Hán-Việt phù hợp giọng gothic/huyền thuật, tương tự "Thuật Gọi Hồn" cho Necromancy) |
| Umbra Map Generation Prototype | Nguyên Mẫu Tạo Bản Đồ Umbra | đặt mới; "Umbra" giữ nguyên (B0/B4v) |
| Landless Adventurer | Nhà Phiêu Lưu Vô Địa | tái dùng `lifestyle_adventurers_l_english.yml` (base, "Nhà Phiêu Lưu"), thêm "Vô Địa" dịch nghĩa "Landless" (khác `landless_adventurer_government`, chưa có bản dịch tên chính phủ, dùng tạm cụm mô tả) |
| Gallivanter *(trait, chỉ xuất hiện trong `[GetTrait('gallivanter').GetName(...)]`, không dịch trực tiếp ở đây)* | *(không dịch — tên trait nằm trong script function, sẽ dịch khi tới `traits/` chứa `trait_gallivanter`)* | trait chưa có key `trait_gallivanter` trong bất kỳ file `traits/*.yml` nào đã dịch; khi dịch file traits tương ứng cần đối chiếu lại dòng này |
| "prevents inheriting landed titles" | "ngăn kế thừa tước vị có đất" | đặt mới; "landed titles"→"tước vị có đất" (khác tước vị của landless adventurer), dịch nghĩa thường cho tooltip `#weak` |

## B5i. Thuật ngữ `interactions/POD_character_interactions_journeys_l_english.yml` — tương tác Hunt/Torpor/Heist dùng cơ chế Journey, 41/41 dòng, việc #5

File định nghĩa 4 nhóm tương tác dùng [journey|E]/[infiltration_mission|E] (concept link, giữ nguyên key, KHÔNG dịch — chỉ file định nghĩa `game_concept_journey` mới dịch chữ hiển thị): Hunt (rút máu/ăn thịt mục tiêu), Find Hiding Place (tìm ma cà rồng đang Miên trạng), Find Lair (tìm sào huyệt quái vật), Heist (trộm Vàng/Hiện vật).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Hunt *(tên tương tác `POD_hunt_target_interaction`)* | Săn Đuổi | đặt mới, dịch nghĩa thường cho hành động truy lùng mục tiêu để rút máu/ăn thịt |
| Find Hiding Place | Tìm Nơi Ẩn Náu | đặt mới; tương tác tìm ma cà rồng đang $pod_torpor$ (Miên trạng, B3-đã chốt "Torpor"→"Miên trạng") |
| torpid vampire *(cụm tính từ, KHÔNG dùng shortcut `$pod_torpor$` để tránh lệch ref-count baseline)* | ma cà rồng đang Miên trạng | tái dùng "Torpor"→"Miên trạng" (đã chốt, dòng 265) ở dạng tính từ; `game_concept_torpid` (`game_POD_concepts_l_english.yml:49`) vẫn còn tiếng Anh, đối chiếu lại khi dịch file đó |
| Find Lair | Tìm Sào Huyệt | đặt mới; "lair"→"sào huyệt" dịch nghĩa thường cho hang ổ quái vật |
| fiend *(chỉ mục tiêu cần săn, không phải ác quỷ theo nghĩa tôn giáo)* | quái vật | KHÔNG tái dùng `fiend`="ác quỷ" của `base_game_vh` (`insult_custom_loc_l_english.yml:13`) vì ngữ cảnh khác — ở đây là mục tiêu chung (có thể là bất kỳ splat nào), dịch nghĩa rộng hơn "quái vật" |
| Steal Gold | Trộm Vàng | đặt mới, dịch nghĩa thường |
| Artifact Heist | Trộm Hiện Vật | đặt mới; "Heist"→"Trộm" (gộp vào động từ, không dịch riêng "cuộc trộm") cho gọn theo UI CK3 |
| Prepare quickly / Scout thoroughly | Chuẩn bị nhanh / Trinh sát kỹ càng | đặt mới, hai lựa chọn tương phản trước khi vào [infiltration_mission|E] |
| "mortal enemies" | "kẻ tử địch" | đặt mới, dịch nghĩa thường, giữ giọng trung cổ (tránh "kẻ thù không thể hòa giải" dài dòng) |
| vault *(nơi giấu mục tiêu heist)* | hầm chứa | đặt mới, dịch nghĩa thường |

## B5j. Thuật ngữ `interactions/POD_character_interactions_ghoul_l_english.yml` — tương tác quản lý/tạo Bộc huyết, 65/65 dòng, việc #5

File xoay quanh domitor điều khiển Nô Bộc/[ghoul|E] của mình: tạo ghoul (`ghoulify`), rút vitae, các nhiệm vụ (`ghoul_mission_*`) domitor giao cho bound ghoul, và tương tác trốn khỏi blood bond.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Thrall(s) *(đồng nghĩa với `[ghoul\|E]` trong ngữ cảnh domitor-ghoul, khác `game_concept_thrall` của Demon-cultist chưa dịch)* | Nô Bộc | tái dùng "Nô Bộc" đã chốt cho `viaservilis_adherent` (dòng 963) và khớp cách `trait_ghoul_desc`/`DHARMA_PASSIVE_5_GHOUL` mô tả ghoul là "nô bộc"; áp dụng cho các nút UI `Heal Thrall`→"Chữa lành Nô Bộc", `Reward/Release Thrall`… |
| Manipulate [ghoul\|E] *(tên tương tác `POD_ghoul`/`POD_manipulate_bound_ghouls`)* | Điều khiển [ghoul\|E] | đặt mới, dịch nghĩa "manipulate" trong ngữ cảnh domitor sai khiến ghoul, tránh dùng "Lợi dụng" (nặng nghĩa xấu hơn ý gốc) |
| Ghoulify *(động từ, tên tương tác `POD_ghoulify_mortal_interaction`)* | Biến thành Bộc huyết | đặt mới, dịch nghĩa hành động biến kẻ phàm thành ghoul, dùng lại "Bộc huyết" (Ghoul, đã chốt dòng 437) thay vì để "ghoul" tiếng Anh ở tên tương tác chính (khác các key khác trong file vẫn giữ `[ghoul\|E]` là concept link) |
| Bribe Officials / Indoctrinate a Contact | Hối lộ Quan Chức / Dẫn dụ một Đầu mối | đặt mới, dịch nghĩa thường cho 2 loại nhiệm vụ domitor giao cho bound ghoul |
| master's lair *(nơi domitor gửi ghoul đến)* | hang ổ của chủ nhân | đặt mới, dịch nghĩa thường; "Domitor" giữ nguyên không dịch (theo `game_concept_domitor: "Domitor"`) nên câu văn dùng "chủ nhân" khi không nhắc trực tiếp đến key Domitor |

## B5k. Thuật ngữ `interactions/character_interactions_POD_l_english.yml` — tương tác chung/tổng hợp toàn mod, 287/287 dòng, việc #5

File tổng hợp các tương tác/hiệu ứng dùng chung cho mọi splat: các key `EXECUTION_*` (lựa chọn hành quyết tù nhân của nhiều loại nhân vật siêu nhiên khác nhau — Wraith, Mummy, Kuei-Jin, Soultaker...), tương tác Hook/Friendship/Government/Teleport, và 2 sự kiện quyết định "Knowledge Exchange" của tộc Impundulu (Kuei-Jin). Không có `UmbraGlossaryLocalized()` trong file này, chỉ có 5 lần `Glossary('Sire'/'True Name', ...)` — cả hai vẫn đang giữ nguyên tiếng Anh ở tham số 1 theo tiền lệ toàn mod (xem B3/B5 "Sire" và mọi lần dùng `Glossary('True Name','podgloss.truename')` ở các file khác), không phải quyết định riêng của file này.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Exsanguination *(`EXECUTION_EXSANGUINATION`, tên một lựa chọn hành quyết)* | Rút Cạn Máu | đặt mới, dịch nghĩa thường; chưa có tiền lệ ở file khác (grep toàn mod không thấy) |
| Spirit Eating / Devour Soul / Feed the Caul / Absorb the Mind *(4 tên lựa chọn hành quyết dùng chung, lặp lại trong tooltip cooldown `used_*`/`execution_*_tooltip`)* | Ăn Linh Hồn / Nuốt Linh Hồn / Cho Caul Ăn / Hấp Thụ Tâm Trí | đặt mới, dịch nghĩa thường cho 4 khái niệm riêng biệt (không đồng nghĩa dù cùng nhóm "ăn tâm trí/linh hồn tù nhân"); "Caul" giữ nguyên tiếng Anh (danh từ riêng WoD chỉ thực thể/vật thể đặc biệt, không có bản dịch tương xứng) |
| Erase from Existence *(`EXECUTION_UNMAKING`)* | Xóa Sổ Khỏi Tồn Tại | đặt mới, dịch nghĩa thường |
| Fill Canopic Jars *(`EXECUTION_FILL_JARS`, hành quyết kiểu Mummy Ai Cập)* | Lấp đầy Bình Canopic | đặt mới; "Canopic jar" là thuật ngữ khảo cổ Ai Cập có phiên âm quen dùng "bình Canopic" trong tiếng Việt phổ thông, giữ nguyên "Canopic" |
| Sacrifice to Soultaker *(`EXECUTION_SOULTAKER`; "Soultaker" là tên riêng một thanh kiếm/thực thể WoD, xem `soultaker_betray`)* | Hiến Tế cho Soultaker | đặt mới; "Soultaker" giữ nguyên (danh từ riêng) |
| Feed to wild animals in the Colosseum *(`EXECUTION_COLOSSEUM`)* | Cho Thú Hoang Ăn trong Đấu trường | đặt mới; "Colosseum" ở đây là danh từ chung (đấu trường La Mã kiểu Nhà hát Đấu Sư Tử), dịch nghĩa "Đấu trường" — khác `building_type_rome_colosseum_01: "The Colosseum"` (danh từ riêng chỉ công trình Đại Hí Trường ở Roma, chưa dịch, sẽ cần quyết định riêng khi tới lượt file đó có nên giữ nguyên tên riêng hay không) |
| Eat Sins *(`EXECUTION_SIN_EATING`)* | Ăn Tội Lỗi | đặt mới, dịch nghĩa thường |
| Call the Khaibit *(`EXECUTION_CALL_KHAIBIT`; "Khaibit" là thuật ngữ Ai Cập cổ chỉ "bóng"/hồn phách, xem thêm B4h dòng 643 "Shadow Twin...Separated Khaibit")* | Gọi Khaibit | đặt mới; giữ nguyên "Khaibit" (danh từ riêng WoD/Ai Cập, chưa có bản dịch tương xứng, nhất quán với B4h) |
| Sun's Judgement *(`EXECUTION_EDGE_OF_THE_SUN`)* | Sự Phán Xét của Mặt Trời | đặt mới, dịch nghĩa thường |
| Adopt/Demand Government Conversion *(`convert_to_government_interaction`/`demand_conversion_government_interaction`, dùng chung `[government\|E]`)* | Áp dụng/Yêu cầu Chuyển đổi Chính thể | đặt mới; "Government"→"Chính thể" tái dùng `game_concept_government` (base_game_vh) |
| Demand Payment for all Hooks *(`POD_mass_demand_payment_interaction`, tương tác đòi tiền hàng loạt theo Kiềm chế)* | Yêu cầu Chi trả cho mọi Kiềm chế | đặt mới; "Hook"→"Kiềm chế" tái dùng `game_concept_hook` (base_game_vh) |
| Copy Clothing Colors *(`POD_copy_clothing_colors_interaction`, tương tác sao chép bảng màu trang phục giữa nhân vật)* | Sao chép Màu Trang phục | đặt mới, dịch nghĩa thường |
| Coterie colors | Màu Coterie | tái dùng "Coterie" giữ nguyên tiếng Anh đã chốt B5f |
| End Friendship *(`POD_end_friendship_interaction`)* | Kết thúc Tình bạn | đặt mới, dịch nghĩa thường; "friend"→"bằng hữu"/"tình bạn" tùy ngữ cảnh, tái dùng tinh thần `game_concept_friend`="Bằng hữu" (base_game_vh) nhưng dùng "Tình bạn" cho tên tương tác/toast vì ngắn gọn hơn khi làm tiêu đề UI |
| Teleport your [army\|E] / [travel\|E] entourage *(2 tương tác dịch chuyển quân đội/đoàn lữ hành, dùng phép thuật POD)* | Dịch chuyển [army\|E] của ngài / Dịch chuyển đoàn tùy tùng [travel\|E] của ngài | đặt mới; "Teleport"→"Dịch chuyển" (dịch nghĩa thường, không dùng "Dịch chuyển tức thời" dài dòng); "entourage"→"đoàn tùy tùng" |
| The Cathedral of Flesh Grows Hungry *(`POD_interface_cathedral_hungry`, tên artifact/công trình "Cathedral of Flesh")* | Đại giáo đường Xác Thịt Bắt đầu Đói | đặt mới; "Cathedral"→"Đại giáo đường" (tái dùng cách base_game_vh dịch "cathedral" trong công trình tôn giáo Kitô giáo), ghép với "Xác Thịt" (Flesh) thành danh từ riêng công trình POD |
| Choose Sifu / your Sifu *(`POD_choose_sifu_interaction`, chức danh sư phụ của Kuei-Jin, tương đương "Sire" của vampire)* | Chọn Sifu / Sifu của mình | giữ nguyên "Sifu" không dịch — tiền lệ đã có ở `gui/POD_character_window_l_english.yml:48` (`POD_sidebar_choose_sifu: "@dynasty_icon! Chọn Sifu"`), nhất quán với "Sire" giữ nguyên (danh từ riêng chức danh WoD) |
| Learn/Study True Name(s) *(tên 2 tương tác học/nghiên cứu Chân Danh, khác tham số 1 của `Glossary('True Name',...)` vẫn giữ tiếng Anh)* | Học Chân Danh / Nghiên cứu Chân Danh | dùng "Chân Danh" đã chốt cho `podgloss.truename` (dòng 363) khi câu văn nhắc tới khái niệm bằng chữ thường (không qua `Glossary()`); tên tương tác chính dịch hẳn ra "Chân Danh" dù tham số 1 wrapper vẫn để "True Name" — hai việc độc lập (xem ghi chú đầu mục) |
| Evaluate / Scrutinize *(2 lựa chọn hành động trong minigame gián điệp Kuei-Jin `POD_kueijin_spy`)* | Đánh giá / Xem xét kỹ | đặt mới, dịch nghĩa thường |
| Exchange Necromantic Knowledge *(quyết định Impundulu trao đổi tri thức gọi hồn với vampire khác)* | Trao đổi Tri thức Gọi Hồn | đặt mới; "Necromantic"→"Gọi Hồn" tái dùng `trait_necromancy`="Thuật Gọi Hồn" (traits_POD, dòng 336) |
| scholars of the grave *(cách gọi hoa mỹ các pháp sư gọi hồn trong sự kiện Impundulu)* | học giả của mộ phần | đặt mới, dịch nghĩa thường giữ giọng trung cổ |

## B5l. Thuật ngữ `interactions/POD_demons/POD_character_interactions_demon_arcana_l_english.yml` — tương tác Arcana của Demon (Demon: The Fallen), 45/45 dòng, việc #5

File đầu tiên trong nhóm `interactions/POD_demons/` được dịch. Chứa các tương tác thuộc lifestyle `[arcana_lifestyle|E]` ("Arcana" — giữ nguyên tiếng Anh làm tên lifestyle, xem `lifestyles/POD_arcana_lifestyle_l_english.yml`, chưa dịch, chỉ dùng qua concept link `[arcana_lifestyle|E]` nên không cần quyết định ở đây). Không có `Glossary()`/`UmbraGlossaryLocalized()` trong file này.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Resolve *(chỉ số năng lượng riêng của Demon, nhiên liệu cho quyền năng Arcana — xem `lesson_gain_resolve_desc` ở `POD_important_actions_l_english.yml`, chưa dịch)* | Quyết Tâm | đặt mới; khác "Vitae" (giữ nguyên, B3) và "Rage"/"Phẫn Nộ" (B3b) — đây là từ tiếng Anh thường (không phải danh từ riêng WoD), nên dịch nghĩa theo đúng nghĩa gốc "ý chí/quyết tâm" nuôi dưỡng quyền năng quỷ dữ; áp dụng cho mọi lần xuất hiện "Resolve" của Demon (`resolve0_modifier`...`resolve10_modifier`, `POD_energy_resolve`, `reactive_advice_gain_resolve`... — chưa dịch, cần tái dùng khi tới lượt) |
| Divine Potential *(`POD_divine_potential_interaction`)* | Tiềm Năng Thần Thánh | đặt mới, dịch nghĩa thường |
| Ravage *(`POD_ravage_interaction`, tương tác tiêu thụ Nô Bộc để hồi Quyết Tâm)* | Tàn Phá | đặt mới, dịch nghĩa thường |
| Revelations *(`POD_revelations_interaction`)* | Khải Thị | đặt mới; tái dùng tinh thần tôn giáo của "Revelation" (Khải Thị/Khải Huyền) theo văn phong trung cổ |
| Twist of Fate *(`POD_twist_of_fate_interaction`)* | Bước Ngoặt Định Mệnh | đặt mới, dịch nghĩa thường |
| Tempt to Sin *(`POD_read_the_heart_interaction`, tên hiển thị khác với tên key "read the heart")* | Cám Dỗ Sa Ngã | đặt mới, dịch theo tên hiển thị thực tế (không dịch theo tên key) |
| Contagion Mastery *(`POD_contagion_mastery_interaction`)* | Tinh Thông Bệnh Dịch | đặt mới, dịch nghĩa thường |
| Healing Touch *(`POD_healing_touch_interaction`)* | Bàn Tay Chữa Lành | đặt mới, dịch nghĩa thường |
| Read the Mind *(`POD_read_the_mind_interaction`)* | Đọc Tâm Trí | đặt mới, dịch nghĩa thường |
| Reshape Flesh *(`POD_reshape_flesh_interaction`)* | Tái Tạo Hình Hài | đặt mới, dịch nghĩa thường |
| Command the Eternal Soul *(`POD_command_the_ethereal_soul_interaction`; lưu ý key gốc ghi "ethereal" nhưng chữ hiển thị là "Eternal" — dịch theo chữ hiển thị)* | Sai Khiến Linh Hồn Vĩnh Cửu | đặt mới, dịch nghĩa thường theo chữ hiển thị |
| Portal Mastery *(`POD_portal_mastery_interaction`)* | Tinh Thông Cổng Không Gian | đặt mới, dịch nghĩa thường |
| Raise the Dead *(`POD_raise_the_dead_interaction`, biến mục tiêu thành `[GetTrait('risen')...]`)* | Hồi Sinh Kẻ Chết | đặt mới; tái dùng "Kẻ Hồi Sinh" đã chốt cho `trait_risen` (traits_POD_l_english.yml:1171) làm gốc động từ |
| Beyond Now *(`POD_beyond_now_interaction`)* | Vượt Ngoài Hiện Tại | đặt mới, dịch nghĩa thường |
| Shapeshift *(`POD_arcana_shapeshift_interaction`, tương tác Arcana — khác trait/cơ chế shapeshift của Garou)* | Biến Hình | đặt mới, dịch nghĩa thường |
| Arsenal of the Beast *(`POD_shapeshift_interaction_purchase_arsenal_of_the_beast`, tên một gói mua trong tương tác Shapeshift)* | Binh Khí Khố của Dã Thú | đặt mới; "Arsenal"→"Binh Khí Khố" (kho vũ khí), "Beast"→"Dã Thú" tái dùng thuật ngữ Beast đã chốt (B3) |

## B5m. Thuật ngữ `interactions/POD_fera/POD_character_interactions_bastet_l_english.yml` — tương tác riêng của Bastet (Fera dạng mèo), 49/49 dòng, việc #5

File nhỏ chứa 12 tương tác/năng lực đặc trưng của tộc Bastet (Werecat). Không có `Glossary()`/`UmbraGlossaryLocalized()`. "Bastet" không xuất hiện trực tiếp trong text của file này (chỉ nằm trong đường dẫn thư mục).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Withering Stare | Ánh Nhìn Héo Tàn | đặt mới, dịch nghĩa thường cho năng lực nhìn gây tổn hại |
| Deny the Hungry *(tên tương tác + modifier cùng tên)* | Từ Chối Kẻ Đói Khát | đặt mới, dịch nghĩa thường |
| Madness *(`POD_madness_perk_interaction`, khác `The Madness of Crowds` cùng file)* | Điên Loạn | đặt mới, dịch nghĩa thường |
| Absorb Disease / Release Disease *(cặp tương tác hấp thụ–giải phóng bệnh tật)* | Hấp Thụ Bệnh Tật / Giải Phóng Bệnh Tật | đặt mới, dịch nghĩa thường |
| Ojas Surge *("Ojas" là thuật ngữ Vệ Đà/Ấn Độ giáo chỉ năng lượng sinh lực, gắn với Bastet nhánh Qualmi/Simba gốc Ấn Độ trong WoD)* | Ojas Trào Dâng | giữ nguyên "Ojas" (danh từ riêng ngoại lai, không có bản dịch tương xứng), dịch nghĩa "Surge"→"Trào Dâng" |
| Summons Shadowy Duplicate *(tên tương tác, khác `POD_shadow_brethren_interaction.tt` là tooltip cùng khái niệm)* | Triệu Hồi Bản Sao Bóng Tối | tái dùng "Bản Sao Bóng Tối" đã chốt B4h (dòng 643, "Shadowy Duplicate") |
| Rallying Challenge | Thách Thức Tập Hợp | đặt mới, dịch nghĩa thường |
| Ghost Caress | Vuốt Ve Của Hồn Ma | đặt mới, dịch nghĩa thường |
| Mother's Blessing/Curse *(tên tương tác ghép + 2 modifier riêng `mothers_blessing_perk_modifier`/`mothers_curse_perk_modifier`)* | Phước Lành/Lời Nguyền Của Mẹ *(tên ghép)*, Phước Lành Của Mẹ, Lời Nguyền Của Mẹ | đặt mới, dịch nghĩa thường |
| The Madness of Crowds | Cơn Điên Của Đám Đông | đặt mới, dịch nghĩa thường |
| Reveal Scheme | Vạch Trần Âm Mưu | "Scheme"→"Âm mưu" tái dùng `game_concept_scheme` (base_game_vh, dòng 107) |

## B5o. Thuật ngữ `interactions/POD_fera/POD_character_interactions_mokole_l_english.yml` — tương tác riêng của Mokolé (Fera dạng bò sát), 117/117 dòng, việc #5

File chứa 21 tương tác/năng lực đặc trưng của tộc Mokolé (Werelizard). Không có `Glossary()`/`UmbraGlossaryLocalized()`, 0 string reference. `Garou` (trong `#TOOLTIP:GAME_TRAIT,werewolf,[GetNullCharacter] #L Garou#!`) và `Umbra`, `Gaia`, `Helios` giữ nguyên theo B0/B3. `[innocent|E]` là concept link chưa dịch tại `game_POD_concepts_l_english.yml` (`game_concept_innocent`) — chỉ dịch chữ hiển thị xung quanh, không đổi key.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Stampede *(tên tương tác, triệu hồi khủng long)* | Bầy Thú Xéo Nát | đặt mới, dịch nghĩa hình ảnh đàn thú giẫm đạp thay vì dịch sát "Cuộc Rượt Đuổi Hoảng Loạn" (không hợp bối cảnh gọi khủng long tấn công) |
| Lizard King(s) | Vua Thằn Lằn | tái dùng `Lizard Kings`="Vua Thằn Lằn" đã chốt (dòng 470), số ít giữ nguyên "Vua Thằn Lằn" không thêm "những" |
| Banish Tormentor / `[innocent|E]` (as Tormentor) | Trục Xuất Kẻ Hành Hạ | đặt mới; "Tormentor" (linh thể ám ảnh sinh ra từ ký ức đen tối của Mokolé qua Mnesis, xem `game_concept_innocent_desc`) dịch "Kẻ Hành Hạ" cho tên tương tác, còn `[innocent|E]` giữ nguyên key — khi tới `game_POD_concepts_l_english.yml` cần đối chiếu lại cách gọi "Innocent" cho nhất quán |
| Silver Claws | Vuốt Bạc | đặt mới, dịch nghĩa thường ("silver"→"bạc" theo cách base dịch kim loại bạc, "claws"→"vuốt") |
| Walk Into my Eyes | Bước Vào Mắt Ta | đặt mới, dịch nghĩa thường |
| Nightmare Mnesis *("Mnesis" là năng lực hồi tưởng ký ức tổ tiên đặc trưng của Mokolé)* | Mnesis Ác Mộng | giữ nguyên "Mnesis" (thuật ngữ WoD riêng của Mokolé, chưa có bản dịch nghĩa tương xứng, theo B0), dịch "Nightmare"→"Ác Mộng" |
| View the Seed | Nhìn Vào Hạt Giống | đặt mới, dịch nghĩa thường |
| Dragon Milk / The Dragon's Tongue / A Thousand Secret Faces / Dream Semblance | Sữa Rồng / Lưỡi Rồng / Ngàn Gương Mặt Bí Mật / Dáng Vẻ Trong Mơ | đặt mới, dịch nghĩa thường; "True Dragon" (trong `POD_dream_semblence_interaction_desc`) → "Chân Long" |
| Scream of Gaia / Tame Sunbeam / Open Sun Bridge | Tiếng Thét Của Gaia / Thuần Hóa Tia Nắng / Mở Cầu Mặt Trời | đặt mới, dịch nghĩa thường; "Gaia" và "Helios" giữ nguyên danh từ riêng |
| Fossilize | Hóa Thạch | đặt mới, dịch nghĩa thường |
| Take the True Form / Gorgon's Gaze | Hiện Chân Hình / Ánh Nhìn Của Gorgon | đặt mới; "Gorgon" giữ nguyên (quái vật thần thoại Hy Lạp, danh từ riêng ngoại lai, không có bản dịch tương xứng) |
| Mother's Touch / Strength of the Dominator / Mastery *(`POD_mokole_mastery_interaction`)* | Cái Chạm Của Mẫu Thân / Sức Mạnh Của Kẻ Thống Trị / Uy Quyền | đặt mới, dịch nghĩa thường; "Mastery" ở đây dịch "Uy Quyền" (khác `Realm Actor Mastery`="Tinh Thông Realm Actor" ở B3 — bối cảnh khác, đây là tương tác áp chế đối phương chứ không phải học phép) |
| attribute *(danh từ chung, xuất hiện ở 2 tương tác Ojas Surge/Rallying Challenge: "boost an attribute")* | thuộc tính | đặt mới, dịch nghĩa thường cho danh từ chung chỉ số nhân vật (không phải key riêng, không có tiền lệ base_game_vh dùng key `attribute`) |

## B5-demon-lores. Thuật ngữ `interactions/POD_demons/POD_character_interactions_demon_lores_l_english.yml` — tương tác Lore của Demon (Demon: The Fallen), 74/74 dòng, việc #5

File thứ hai trong nhóm `interactions/POD_demons/`, song song với B5l (`POD_character_interactions_demon_arcana_l_english.yml`). Chứa các tương tác thuộc lifestyle `[lore_lifestyle|E]` ("Lore" — giữ nguyên tiếng Anh làm tên lifestyle/hệ thống quyền năng, cùng cách xử lý "Arcana" ở B5l; xem `lifestyles/POD_lore_lifestyle_l_english.yml`, chưa dịch, chỉ dùng qua concept link `[lore_lifestyle|E]` nên không cần quyết định ở đây). "Lore" ở đây khác nghĩa "truyền thuyết/cổ thư" (`religious_text`, đã chốt B3g/B3h/B3x) — đây là danh từ riêng chỉ hệ thống 7 House quyền năng thiên thần của Demon, viết hoa và giữ nguyên tiếng Anh mỗi lần xuất hiện dạng "Lore of the X"/"Lore X". Có 2 lần `[Glossary('True Name','podgloss.truename')]` (tham số 1 giữ nguyên theo tiền lệ toàn mod, xem dòng 363), không có `UmbraGlossaryLocalized()`.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Demand Knowledge of Lores *(`POD_demand_lore_teaching_interaction`)* | Đòi hỏi Tri thức về các Lore | đặt mới, dịch nghĩa; "Lore" giữ nguyên (xem trên) |
| Lore of the Herald | Lore của Sứ Giả | đặt mới; "Herald" (1 trong 7 House Lore của Elohim/Demon) → "Sứ Giả", dịch nghĩa thường |
| Lore of the Life-Bringer | Lore của Đấng Ban Sự Sống | đặt mới, dịch nghĩa thường |
| Lore of Creation | Lore Sáng Thế | đặt mới; "Creation" → "Sáng Thế" tái dùng nghĩa tôn giáo quen dùng trong repo (vd. "outside Creation" ở cùng file → "bên ngoài Sáng Thế") |
| Lore of the Seer | Lore của Nhà Tiên Tri | đặt mới, dịch nghĩa thường |
| Lore of Beauty | Lore Vẻ Đẹp | đặt mới, dịch nghĩa thường |
| Lore of the Living | Lore của Sự Sống | đặt mới, dịch nghĩa thường |
| Lore of the Ethereal | Lore của Cõi Phi Vật Chất | đặt mới; "Ethereal" → "Phi Vật Chất" (tính từ mô tả cõi giới vô hình/không xác thịt), thêm "Cõi" cho tự nhiên trong cụm "Lore của Cõi X" |
| Manipulate Adhesion *(`POD_lore_world_manipulate_adhesion_interaction`, tăng cường quan hệ)* | Thao túng Sự Gắn Kết | đặt mới, dịch nghĩa thường |
| Manipulate Inertia *(`POD_lore_world_manipulate_inertia_interaction`, phá hủy quan hệ)* | Thao túng Sự Trì Trệ | đặt mới, dịch nghĩa thường |
| Manipulate Cohesion: Personality / Sexuality *(2 tương tác riêng, thao túng tính cách/xu hướng tính dục nhân vật)* | Thao túng Sự Liên Kết: Tính Cách / Thao túng Sự Liên Kết: Xu Hướng Tính Dục | đặt mới, dịch nghĩa thường |
| Fade *(`POD_lore_world_fade_interaction`, khiến mục tiêu "fade into obscurity")* | Phai Mờ | đặt mới, dịch nghĩa thường |
| Summon Outsider *(`POD_lore_corrupption_summon_outsider_interaction`, phá công trình bằng cách gọi thực thể ngoài Sáng Thế)* | Triệu hồi Kẻ Ngoại Lai | đặt mới, dịch nghĩa thường |
| Mark of the Celestials *(`POD_lore_the_mark_of_the_celesitals_interaction`, ban phước/nguyền số phận; lưu ý key gốc gõ sai "celesitals")* | Ấn Ký của các Đấng Thiên Giới | đặt mới; "Celestials" → "các Đấng Thiên Giới" tái dùng "Thiên Giới" đã chốt cho "Celestial" (dòng 825, 1508, 1763) |
| Revelation *(`POD_lore_revelation_interaction`, phơi bày bí mật/âm mưu mục tiêu)* | Khải Thị | tái dùng "Khải Thị" đã chốt B5l cho "Revelations" (`POD_revelations_interaction` của Arcana) — cùng gốc tôn giáo, giữ nhất quán |
| Cleanse *(`POD_lore_cleanse_interaction`, chữa mọi bệnh tật)* | Tẩy Trừ | đặt mới, dịch nghĩa thường |
| Restore Life | Phục Sinh | đặt mới, dịch nghĩa thường |
| Teleport | Dịch Chuyển Tức Thời | đặt mới, dịch nghĩa thường |
| Manipulate Weather | Thao túng Thời Tiết | đặt mới, dịch nghĩa thường |
| Inspire *(2 biến thể `_interaction`/`_no_dlc_interaction`, cùng tên hiển thị "Inspire")* | Khơi Nguồn Cảm Hứng | đặt mới, dịch nghĩa thường |
| Alter Appearance / Enhance Beauty / Wither Beauty | Biến Đổi Dung Mạo / Tôn Vinh Vẻ Đẹp / Làm Tàn Úa Vẻ Đẹp | đặt mới, dịch nghĩa thường |
| Shapechange *(`POD_lore_shapechange_interaction`, khác "Shapeshift" của Arcana ở B5l — cùng nghĩa biến hình nhưng tên tiếng Anh khác nhau theo từng Lore)* | Biến Hình | dịch nghĩa giống "Shapeshift" (B5l) vì cùng khái niệm biến hình thể chất, không có lý do tách nghĩa |
| Command the Wild / Give Life to the Flora / Drain Life from the Flora | Hiệu Lệnh Hoang Dã / Ban Sự Sống cho Thảo Mộc / Rút Cạn Sự Sống từ Thảo Mộc | đặt mới; "Flora" → "Thảo Mộc" (thực vật nói chung, văn phong cổ điển hơn "cây cỏ") |

## B5p. Thuật ngữ `interactions/POD_fera/POD_character_interactions_wyrm_l_english.yml` — tương tác Garou/Fera sa ngã theo Wyrm, 14/14 dòng, việc #5

File nhỏ 4 tương tác của Fera đã ngả theo Wyrm (song song với `POD_religion_wyrm`, B4s). Không có `Glossary()`/`UmbraGlossaryLocalized()`. Có 1 `$glossary_wyrm$` — giữ nguyên ref, không dịch; "Wyrm" trong câu văn `POD_embrace_oblivion_interaction_desc` giữ nguyên tiếng Anh theo B3 (bắt buộc).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Dancing Shadows *(tên tương tác)* | Vũ điệu Bóng tối | đặt mới, dịch nghĩa thường; "shadow" ở đây là cái bóng vật lý của nhân vật (không phải "Shadow" đặc thù Wraith B4h), theo mẫu compound thông thường |
| Splintered Soul *(tên tương tác, tạo bản sao Linh thể của chính mình — cùng khái niệm với `SPLINTERED_SOUL_PERK_EFFECT` ở `POD_urgetaints_lifestyle_l_english.yml`, file đó chưa dịch)* | Linh hồn Phân mảnh | đặt mới; "Soul"→"Linh hồn" (danh từ chung, khác "Spirit"→"Linh thể" đã chốt B4c cho `trait_spirit`) |
| ancestor_spirit *(`[ancestor_spirit\|E]`, concept link)* | *(giữ nguyên key, không dịch)* | key game_concept `game_concept_ancestor_spirit`="Ancestor Spirit" ở `game_POD_concepts_l_english.yml` chưa được dịch — khi file đó tới lượt, đối chiếu lại "Ancestor"="Tổ Tiên" (B0/B3c dòng 614) + "Spirit"="Linh thể" (B4c) để đặt tên hiển thị nhất quán |
| Maniacal Mind *(tên tương tác, whispers của Wyrm dụ dỗ)* | Tâm trí Điên cuồng | đặt mới, dịch nghĩa thường; "Maniacal" dịch "Điên cuồng" thay vì "Điên loạn" (đã dùng cho `Madness`/`The Madness of Crowds` ở B5l Bastet) để tránh trùng hai khái niệm khác nhau |
| Embrace Oblivion *(tên tương tác)* | Ôm lấy Hư Vô | "Oblivion"→"Hư Vô" ✅ tái dùng tiền lệ đã khóa cứng nhiều lần (B3q/B4n/B4u/B4w) |

## B5-demon-thrall. Thuật ngữ `interactions/POD_demons/POD_character_interactions_demon_thrall_l_english.yml` — tương tác Demon/Thrall/Cultist, 53/53 dòng, việc #5

Không có `Glossary()`/`UmbraGlossaryLocalized()`/`Select_CString()`. Điểm mấu chốt: `[thrall|E]` ở đây trỏ tới `game_concept_thrall` (Demon-cultist context, `game_POD_concepts_l_english.yml:251`, chưa dịch) — **khác** "Thrall" đã chốt "Nô Bộc" ở B5j (ngữ cảnh domitor-ghoul, `[ghoul|E]`). Hai khái niệm hoàn toàn khác nhau trong lore WoD (ghoul uống máu vs. người bị ác quỷ thu phục làm tay sai/tín đồ) nên **không thể dùng chung một bản dịch**.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Thrall(s) *(Demon-cultist context, `game_concept_thrall`, khác Nô Bộc B5j)* | Nô Lệ | đặt mới; base_game_vh dịch "thrall" vanilla (`rival_thrall_scapegoat`) là "nô lệ" — tái dùng tiền lệ đó cho nhánh Demon để tách biệt rõ với "Nô Bộc" (ghoul, B5j) |
| Enthrall / Enthrallment | Thu phục | đặt mới, hành động ác quỷ khuất phục một nhân vật thành Nô Lệ |
| Cultist(s) *(`[cultist\|E]`, context Demon; cùng nghĩa với `cultofzilah_adherent`="Tín Đồ" dòng 1565, khác `predatortype_cultist`="Giáo Chủ Tà Giáo")* | Tín Đồ | tái dùng "Tín Đồ" đã có tiền lệ ở dòng 1565/1632, phù hợp nghĩa phổ thông "kẻ sùng bái" |
| Pact *(khế ước giữa Demon và Thrall, `POD_remove_thrall_interaction`="Cancel Pact", khác `demonic_pact`=game concept "Pact" chưa dịch và khác `[spirit_pact\|E]`="Hiệp ước Linh hồn")* | Khế ước | đặt mới; dùng khi file này nhắc "pact" ở câu văn thường (không phải concept link), tránh trùng với "Hiệp ước Linh hồn" đã chốt cho spirit_pact |
| Power behind the Throne *(tên tương tác `POD_demonic_submission_interaction`, thề trung thành đổi lấy quyền lực ngầm)* | Quyền lực Sau Ngai Vàng | đặt mới, dịch nghĩa thường theo idiom "power behind the throne" |

## B5s. Thuật ngữ `interactions/POD_fera/POD_character_interactions_werewolf_l_english.yml` — tương tác Garou/Fera nói chung, 106/106 dòng, việc #5

Không có `Glossary()`/`UmbraGlossaryLocalized()`/`Select_CString()`. 4 dòng cuối (99-102, key `#POD_call_fenris_to_war_interaction*`) bị comment sẵn trong bản gốc — giữ nguyên tiếng Anh, không dịch theo mục 5 TRANSLATION_RULES.md. "gnosis" ở dòng `POD_break_the_bonds_interaction_desc`/`POD_storyteller_interaction_desc` là từ thường trong câu (không phải `$POD_energy_gnosis$`) — giữ nguyên cách viết thường của bản gốc, không viết hoa hay đổi thành ref.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Alpha *(người đứng đầu bầy Garou, `POD_inspiration_interaction`)* | Alpha *(giữ nguyên)* | danh từ tổ chức lõi WoD, theo B0 tương tự tiền lệ "pack"/"Coterie" (B4r/B5f) — cộng đồng quen đọc tiếng Anh, dịch nghĩa ("Đầu Lĩnh") sẽ mất sắc thái |
| pack *(bầy Garou, `pack_tactics_modifier_desc`)* | bầy | ✅ tái dùng tiền lệ B0 dòng 1611 (dịch nghĩa thường "bầy" cho pack Garou, khác pack Sabbat giữ nguyên tiếng Anh) |
| Divide *(tên tương tác reo rắc bất hòa giữa liege/vassal)* | Chia Rẽ | đặt mới, dịch nghĩa thường |
| Primal Song / Song of the Siren | Khúc Ca Nguyên Thủy / Khúc Ca Nàng Tiên Cá | đặt mới, dịch nghĩa thường |
| Break the Bonds *(dùng gnosis buộc đối tượng trả hook)* | Phá Vỡ Ràng Buộc | đặt mới, dịch nghĩa thường |
| Share Strength / Shared Strength | Chia Sẻ Sức Mạnh | đặt mới; các biến thể `_gain`/`_loss` theo 6 chỉ số (Diplomacy/Martial/Stewardship/Intrigue/Learning/Prowess) dịch theo bảng A1 đã chốt (Ngoại Giao/Chỉ Huy/Quản Lý/Mưu Mô/Học Thức/Võ Dũng), ghép "Tăng"/"Giảm" |
| Storm of Mother's Wrath *(phép Garou gây bão tàn phá lãnh thổ đối phương)* | Cơn Thịnh Nộ của Mẫu Thần | đặt mới; "Mother Goddess"="Mẫu Thần" ✅ tái dùng B3b, "Wrath"="Thịnh Nộ" theo văn phong trung cổ, tách khỏi "Rage"="phẫn nộ" (B3b, chỉ số Garou) để tránh trùng hai khái niệm |
| Tagalong *(tương tác nhận phước lành totem)* | Đi Theo | đặt mới, dịch nghĩa thường |
| totem *(vật tổ, `POD_tagalong_interaction_desc`)* | vật tổ | ✅ tái dùng tiền lệ B0 dòng 1765 (dịch nghĩa thường, không cần thuật ngữ WoD riêng) |
| Provoke Riot | Kích Động Bạo Loạn | đặt mới, dịch nghĩa thường |
| Turn into a Crinos Werewolf / Crinos werewolf | Biến thành Người Sói Crinos / người sói Crinos | "Crinos" giữ nguyên (tên hình dạng chiến binh của Fera, đã có tiền lệ giữ nguyên ở `POD_fera_common_l_english.yml`); "Werewolf"→"Người Sói" dịch nghĩa thường |
| Summons Shadowy Duplicate(s) | Triệu Hồi Bản Sao Bóng Tối | đặt mới, dịch nghĩa thường |
| Renew the Cycle | Tái Sinh Chu Kỳ | đặt mới, dịch nghĩa thường |
| Attain True Spiritual Balance *(Kuei-Jin, "Thought Form of the Twelve Ministers")* | Đạt Chân Quân Bình Tâm Linh | đặt mới, dịch nghĩa thường |
| Burning Scars | Sẹo Lửa | đặt mới, dịch nghĩa thường |
| Garbage Diving / Great Trash Heap *(Ratkin, dịch chuyển qua các điện thờ Đống Rác)* | Lục Thùng Rác / Đống Rác Vĩ Đại | đặt mới, dịch nghĩa thường; "Great Trash Heap" là địa danh thiêng liêng của Ratkin trong lore WoD, chưa có tiền lệ trong repo |
| Appear *(`POD_home_in_all_lands_perk_interaction`, dịch chuyển "sideways" tới nơi có sói)* | Xuất Hiện | đặt mới, dịch nghĩa thường |
| Storm Winds Slash *(Hakken/Tribalgifts, chém từ xa bằng Katana)* | Chém Gió Bão | đặt mới, dịch nghĩa thường; "Katana" giữ nguyên (danh từ vũ khí Nhật, đã có tiền lệ giữ nguyên ở `pod_canon_artifacts_events`) |
| Dark of Night / Blindness | Bóng Tối Đêm Trường / Mù Lòa | đặt mới, dịch nghĩa thường |
| Moon Bridge *(dịch chuyển qua caern bằng đường trăng trong Umbra)* | Cầu Trăng | đặt mới, dịch nghĩa thường; "caern" giữ nguyên ✅ tái dùng B4s/B4v |
| Blooding Fury | Cuồng Nộ Huyết Thống | đặt mới, dịch nghĩa thường |
| Pack Tactics / Strength of Will | Chiến Thuật Bầy Đàn / Sức Mạnh Ý Chí | đặt mới, dịch nghĩa thường |

## B5q. Thuật ngữ `interactions/POD_fera/POD_character_interactions_fera_l_english.yml` — tương tác Fera chung (không riêng loài), 54/54 dòng, việc #5

Không có `Glossary()`/`UmbraGlossaryLocalized()`/`Select_CString()`. Tái dùng thuật ngữ Fera đã chốt: Gnosis→`$POD_energy_gnosis$` (ref, không dịch), Willpower→"ý chí" (theo tiền lệ base_game_vh, không viết hoa vì xuất hiện dạng câu văn thường "willpower" chứ không phải chỉ số riêng có key). "Homid" giữ nguyên tiếng Anh theo B4c (tên Dòng Sinh, `trait_homid_born`). "Flaying Plague" tái dùng "Ôn Dịch Lột Da" đã chốt ở dòng 665 (B?, tên bệnh WoD).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Gift *(viết hoa, năng lực tâm linh Garou/Fera học được, tương đương "Discipline" của ma cà rồng nhưng là hệ thống riêng — `POD_train_gift_interaction`, và tên các lifestyle `*gifts_lifestyle_name` như "Breed Gifts", "Planetary Gifts", "Tribal Gifts" đều chưa dịch)* | Thiên Phú | đặt mới; không dùng "Dị năng" (đã khóa cứng cho Discipline, B2) để tránh nhầm hai hệ thống siêu nhiên khác nhau; bản Trung dịch "灵赋" (linh phú) — tham khảo cấu trúc, không có thẩm quyền thuật ngữ; "Thiên Phú" giữ văn phong Hán Việt trang trọng nhất quán base_game_vh |
| Ebon Binding *(tên tương tác + modifier, Gift trói buộc hình phạt siêu nhiên lên mục tiêu)* | Xiềng Xích Bóng Tối | đặt mới, dịch nghĩa thường; "Ebon" (đen tối) ghép "Binding" (trói buộc/xiềng xích) |
| Savagery of the Taloned Hunter *(tên tương tác, đổi Gnosis+ý chí lấy Gnosis)* | Man Rợ Của Kẻ Săn Mồi Móng Vuốt | đặt mới, dịch nghĩa thường |
| Burden of Knowledge *(tên tương tác, gây điên loạn/tự sát cho mục tiêu)* | Gánh Nặng Tri Thức | đặt mới, dịch nghĩa thường |
| Essential Transformation *(tên tương tác, đổi vết thương lấy Gnosis)* | Biến Đổi Cốt Lõi | đặt mới, dịch nghĩa thường |
| Shapeshift *(tương tác đổi hình dạng Fera)* | Biến Hình | đặt mới, dịch nghĩa thường; nhất quán với "Shapechange" (B4l, Lore Demon) đã dịch cùng là "Biến Hình" vì cùng khái niệm biến đổi thể chất |
| Totem form | Hình dạng Vật Tổ | tái dùng "Vật Tổ" đã chốt dòng 1765 cho "totem" |
| Weather Magic *(context Fera, tương tác gây thiên tai)* | Phép Thuật Thời Tiết | đặt mới, dịch nghĩa thường; file `POD_shared_loca`/mummy interactions dùng chung khái niệm này nhưng chưa dịch — khi tới lượt, tái dùng "Phép Thuật Thời Tiết" để nhất quán |

## B5n. Thuật ngữ `interactions/POD_demons/POD_character_interactions_demon_infernalist_l_english.yml` — tương tác Infernalist (thảo Khế ước/triệu hồi/trói buộc Demon), 69/69 dòng, việc #5

File chứa toàn bộ tương tác lối sống Infernalist (Demon: The Fallen): Shapeshift, ký/thực thi Khế ước (`demonic_pact`), Triệu hồi, Trói buộc (Diabolism), các quyền năng cá nhân (Serpent Skin, Devil's Eyes, Apportation, Teleportation, Bond-Breaking, Mammon's Gift, Talons of the Plague-Crow, Army of the Damned, Black Whispers) và 4 tương tác hoàn thành điều khoản Khế ước (`POD_pact_*`). Không có `UmbraGlossaryLocalized()`. Có 4 lần `UmbraGlossary('abyss')` (1 tham số, không dịch gì — tự lấy tên "Vực Thẳm" qua `Localize()`) và 2 lần `Glossary('True Name','podgloss.truename')` / `Glossary('Yama Kings','podgloss.yamaking')` (tham số 1 giữ nguyên tiếng Anh theo tiền lệ toàn mod, xem dòng 363/342).

**Quan trọng:** `POD_request_pact_interaction`="Sign Demonic Pact" dịch là "Ký Khế Ước Ma Quỷ" — tái dùng "Khế ước" đã chốt ở B5q (`interactions/POD_demons/POD_character_interactions_demon_thrall_l_english.yml`, dòng 2181) cho khái niệm Pact giữa Demon và Thrall/Infernalist trong câu văn thường, **không** dùng "Hợp đồng" (đã dành cho `game_concept_contract`/`Vassal Contract` ở vanilla, A9) để tránh lẫn hai khái niệm khác nhau.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Sign Demonic Pact *(`POD_request_pact_interaction`)* | Ký Khế Ước Ma Quỷ | tái dùng "Khế ước" đã chốt B5q cho `demonic_pact` prose context (khác "Hợp đồng" vanilla, khác "Hiệp ước Linh hồn"=`spirit_pact`) |
| Banish Demon / Bind Demon / Weaken Demon | Trục Xuất Ác Quỷ / Trói Buộc Ác Quỷ / Làm Suy Yếu Ác Quỷ | dịch nghĩa thường; "Ác quỷ" tái dùng `trait_demon` (dòng 608); "Trục Xuất" nhất quán với concept `POD_banish`=`game_concept_POD_banish`="Banish" (chưa dịch ở nơi định nghĩa, nhưng dùng khi câu văn nhắc bằng chữ thường) |
| Initiate Demonology / Perform Demonic Summoning | Khai Tâm Quỷ Học / Thực Hiện Nghi Thức Triệu Hồi Ác Quỷ | "Demonology"→"Quỷ Học" tái dùng `trait_demonology` (dòng 1532); "Initiate" dịch "Khai Tâm" (dạy nhập môn) để tránh trùng "Bắt đầu"/"Khởi động" đã dùng nơi khác |
| Serpent Skin | Lột Da Rắn | đặt mới, dịch nghĩa thường |
| Devil's Eyes *(tương tác khơi mào dịch bệnh)* | Mắt Quỷ | đặt mới, dịch nghĩa thường, giữ ngắn gọn như tên gốc |
| Apportation *(thuật lấy trộm hiện vật từ xa, thuật ngữ huyền học có thật)* | Di Vật Thuật | đặt mới, Hán Việt ("di vật" = chuyển dời vật thể + "thuật" = pháp thuật), tránh dịch thô "Thuật Chuyển Vật" |
| Teleportation *(tương tác né tránh khoảng cách, khác `Teleport`="Dịch Chuyển" B5k)* | Dịch Chuyển Tức Thời | thêm "Tức Thời" để phân biệt với tương tác `Teleport` đơn giản (B5k dòng 2061) vốn chỉ dịch "Dịch Chuyển" |
| Bond-Breaking *(tương tác xóa Hook)* | Phá Vỡ Ràng Buộc | đặt mới, dịch nghĩa thường; "Hook"="Kiềm chế" (`game_concept_hook`) giữ nguyên concept link, không đổi |
| Mammon's Gift *(Mammon = Ác quỷ Tham lam trong Kinh Thánh/WoD, danh từ riêng)* | Món Quà của Mammon | "Mammon" giữ nguyên (danh từ riêng ngoại lai, không có tiền lệ base_game_vh) |
| Talons of the Plague-Crow | Móng Vuốt của Quạ Ôn Dịch | đặt mới, dịch nghĩa thường; "Plague"→"Ôn Dịch" nhất quán với "Flaying Plague"→"Ôn Dịch Lột Da" (dòng 665) |
| Army of the Damned | Đội Quân của Kẻ Bị Đọa Đày | đặt mới, dịch nghĩa thường; "the Damned" (số nhiều ẩn, chỉ những linh hồn bị đọa đày ở Địa Ngục) → "Kẻ Bị Đọa Đày" |
| Sacrifice of Gold / Infernal Prayer / Show of Submission / Offering of Artifact *(4 tương tác hoàn thành điều khoản Khế ước, đổi Vàng/Mộ đạo/Uy tín/Hiện vật lấy điểm Investiture)* | Hiến Tế Vàng / Lời Cầu Nguyện Địa Ngục / Màn Thể Hiện Quy Phục / Dâng Hiến Vật | dịch nghĩa thường; "Sacrifice"→"Hiến Tế" (tái dùng B5? `Sacrifice to Soultaker`="Hiến Tế cho Soultaker" dòng 2051); "Gold"/"Piety"/"Prestige"/"Artifact(s)" đều giữ nguyên concept link `[gold\|E]`/`[piety\|E]`/`[prestige\|E]`/`[artifacts\|E]`, không đổi |
| Black Whispers *(tương tác mua tri thức từ Yama Kings để biết bí mật/âm mưu đối phương)* | Những Lời Thì Thầm Đen Tối | đặt mới, dịch nghĩa thường |

---

## B5-mummy. Thuật ngữ `interactions/POD_character_interactions_mummy_l_english.yml` — tương tác Mummy (Shemsu-Heru/Cabiri Ai Cập + Wu Tan Trung Hoa), 157/157 dòng, việc #5

Nguồn: 157 dòng, các tương tác Hekau (pháp thuật Mummy Ai Cập) và Wu Tan (`POD_tan_*`, pháp thuật Mummy Trung Hoa). Không có `UmbraGlossaryLocalized()`; chỉ có `UmbraGlossary('tempest')`/`UmbraGlossary('shadowlands')`/`UmbraGlossary('oblivion')` (1 tham số, không dịch — tự lấy tên qua `Localize()`, đã dịch sẵn "Hư Vô"=oblivion ở B3q/B4n/B4u/B4w/B5p) và 1 `Glossary('True Name','podgloss.truename')` (tham số 1 giữ nguyên theo tiền lệ toàn mod). "Hekau", "Khaibit", "Neteru", "Ma'at", "Asekh-sen", "Shroud", "Tan" (trong `POD_tan_*`) đều giữ nguyên tiếng Anh — danh từ riêng WoD/Ai Cập/Trung Hoa đã có tiền lệ giữ nguyên ở B4h/B0 (Nomenclature Hekau, Judges of Ma'at, Duat…).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Neteru *(danh hiệu "thần" mà Mummy được tín đồ tôn thờ, key `[neteru\|E]`)* | Neteru *(giữ nguyên)* | danh từ riêng Ai Cập, nhất quán với "Nomenclature Hekau" giữ nguyên (B4) |
| Recognize Neteru / Reject Neteru | Công nhận Neteru / Từ chối Neteru | dịch nghĩa động từ, giữ "Neteru" nguyên |
| Command Creature Effigy / Effigy | Điều khiển Effigy Sinh Vật / Effigy | "Effigy" giữ nguyên theo tiền lệ B4h (Golem, Automaton, Effigy, Animantis, Servitor, Manifestation — nhóm danh từ riêng kỹ thuật gọi hồn/pháp thuật giữ nguyên) |
| Command the Crawling Eye / Command Stalking Hound of Typhon | Điều khiển Con Mắt Bò / Điều khiển Chó Săn Rình Rập của Typhon | dịch nghĩa tên effigy cụ thể; "Typhon" giữ nguyên (danh từ riêng thần thoại Hy Lạp) |
| Eye of Sekhmet *(key `sakhmet` nhưng hiển thị "Sekhmet")* | Mắt của Sekhmet | "Sekhmet" giữ nguyên (nữ thần Ai Cập có thật) |
| Spell of Life | Chú Thuật Sự Sống | tái dùng "Chú Thuật" đã có tiền lệ trong mod (Spell of Life là năng lực nổi tiếng nhất của Mummy, cho bất tử) |
| Ma'at *(khái niệm triết học Ai Cập, trật tự vũ trụ)* | Ma'at *(giữ nguyên)* | tái dùng tiền lệ B0/B4h ("Isfret, Ma'at giữ nguyên") |
| Asekh-sen *(vật thế thân/chattel của Mummy)* | Asekh-sen *(giữ nguyên)* | danh từ riêng WoD-Mummy, theo B0 (nhóm tên bộ tộc/thuật ngữ Mummy giữ nguyên) |
| Chattel of [X] *(`POD_copy_artifact_name`)* | Vật Sở Hữu của [X] | đặt mới, dịch nghĩa "chattel" = tài sản/vật sở hữu (hiện vật sao chép) |
| Dragon Line(s) / Dragon Chariot / Tread (Thread) the Dragon Tracks | Long Mạch / Xa Long / Dấn Bước theo Vết Rồng | đặt mới; "Dragon Line"→"Long Mạch" (thuật ngữ phong thủy Hán Việt có sẵn, khớp bối cảnh Mummy Trung Hoa); "Dragon Chariot"→"Xa Long" (Hán Việt, xe rồng); lưu ý bản gốc có 2 key gần giống nhau ở 2 chỗ khác nhau trong file — `POD_tread_the_dragon_tracks_interaction`="Tread the Dragon Tracks" và `POD_tan_tread_the_dragon_tracks_interaction`="Thread the Dragon Tracks" (lỗi chính tả gốc "Thread" thay vì "Tread") — cả hai đều dịch thống nhất "Dấn Bước theo Vết Rồng" |
| Khaibit *(hồn phách/"bóng" trong Mummy lore Ai Cập)* | Khaibit *(giữ nguyên)* | tái dùng tiền lệ B4h ("Separated Khaibit"→"Khaibit Bị Tách Rời") |
| Shroud *(mức độ, level, giữa Skinlands và Shadowlands)* | Shroud *(giữ nguyên)* | tái dùng tiền lệ toàn mod — "Shroud" không dịch xuyên suốt (khác "Màn Che"=Masquerade riêng vampire, B4/B5) |
| Ammut's Scales *(cán cân phán xét linh hồn của nữ thần Ammut)* | Cán Cân của Ammut | "Ammut" giữ nguyên (nữ thần Ai Cập có thật), "Scales" dịch nghĩa "Cán Cân" |
| Wu Tan / Tan *(hệ pháp thuật Mummy Trung Hoa, key `POD_tan_*`)* | Tan *(giữ nguyên)* | tái dùng tiền lệ B4h/B0 (Tieh Tan, Lin Tan, Shui Tan, Hou Tan, Di Tan, Nei Tan — nhóm tên hệ phái Tan giữ nguyên) |
| Servant *(context Apophis/Demon's Servant, `POD_ask_neteru_for_apophis_conversion`/`POD_tan_bind_the_demons_servant`)* | Nô Bộc | tái dùng tiền lệ đã chốt (dòng 963, `viaservilis_adherent`) thay vì "Đầy tớ", giữ giọng cổ trang trọng nhất quán |
| Sweet Dream's Caress / Opening the Third Eye / Scroll of the Mind's Eye / Death's Touch | Sự Vuốt Ve của Giấc Mộng Ngọt Ngào / Khai Mở Con Mắt Thứ Ba / Cuộn Kinh Con Mắt Tâm Trí / Cái Chạm của Cái Chết | dịch nghĩa thường, giữ giọng thơ/huyền bí như tên gốc |
| Shen *(thế giới ẩn giấu, WoD Trung Hoa — linh thể/thần linh nói chung)* | Thần *(giữ nguyên nghĩa Hán Việt, không phiên âm)* | đặt mới; "Shen" trong bối cảnh Kuei-Jin/Wu Tan là khái niệm rộng chỉ linh hồn/thần linh, dịch nghĩa "Thần" cho tự nhiên hơn giữ nguyên phiên âm |

## B5-kuejin. Thuật ngữ `interactions/POD_character_interactions_kuejin_l_english.yml` — 4 nhóm Art của Kuei-Jin (Demon Arts/Soul Arts/Chi Arts/Shintai), 158/158 dòng, việc #5

Nguồn: 158 dòng, tên và mô tả các tương tác Art của Kuei-Jin, chia theo 4 lifestyle chưa dịch (`lifestyles/POD_kueijin/`: `POD_demon_arts_lifestyle`, `POD_soul_arts_lifestyle`, `POD_chi_arts_lifestyle`, `POD_shintai_lifestyle`). Đây là file đầu tiên đụng các tên Art cụ thể — đặt mới toàn bộ, đối chiếu B3c (Dharma=Pháp Môn, Chi=Khí đã chốt) và B4g (Feng Shui/Tzu Wei/Tapestry/Obligation — các Chi Art đã đặt). Chỉ 1 cặp `Glossary()`/`UmbraGlossaryLocalized()` trong file (dòng `POD_soul_arts_graveyard_song_interaction_desc`): `Glossary('Skinlands',...)` giữ nguyên tham số 1 theo tiền lệ B4h/toàn mod; `UmbraGlossaryLocalized('shadowlands','Underworld')` → tham số 2 phải dịch theo B4j đã chốt cứng — sửa thành `'Âm Phủ'` (KHÔNG phải "Âm Giới", "Âm Phủ" dành riêng cho tham số 2 chính xác là "Underworld" của flag `shadowlands`).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Art / Arts *(hậu tố tên nhóm lifestyle Kuei-Jin: Demon Arts, Soul Arts, Chi Arts)* | Pháp Nghệ | đặt mới; khác "Art" giữ nguyên của Changeling (Chicanery…, B4g) — ở Kuei-Jin "Art" là danh từ thường chỉ "thuật/nghệ thuật tu luyện", không phải tên riêng, nên dịch nghĩa; "Nghệ" gợi tinh thông kỹ năng, "Pháp" gợi tu luyện siêu nhiên, khớp giọng Hán Việt của mảng Kuei-Jin |
| Demon Arts *(lifestyle, sức mạnh từ P'o)* | (không dịch tên lifestyle trong file này — chỉ xuất hiện qua tên trait cụ thể: Devil Fist→Ma Quyền, Black Wind→Hắc Phong, Iron Mountain→Thiết Sơn, Demon Regalia→Ma Bào) | tên 4 "Art" cụ thể của Demon Arts được nhắc tới trong mô tả perk (`the Devil Fist Art`, `the Black Wind Art`…) — dịch nghĩa Hán Việt ngắn gọn, khớp phong cách kungfu; "Demon Regalia"→"Ma Bào" (áo bào của ma, gợi trang bị/vẻ ngoài) |
| Soul Arts *(lifestyle, tu luyện Tứ Đức qua P'o/Hun)* | Pháp Nghệ Linh Hồn | ghép "Pháp Nghệ" (B5-kuejin, mới đặt) + "Linh Hồn" (đã có sẵn toàn mod); chỉ dùng trong diễn giải, không phải key dịch trực tiếp trong file này |
| Chi Arts *(lifestyle, điều khiển Khí/phong thủy/tử vi)* | Pháp Nghệ Khí | ghép "Pháp Nghệ" + "Khí" (đã chốt B3c) |
| Shintai *(lifestyle, hóa thân biểu tượng giác ngộ — giữ nguyên tên riêng Nhật ngữ)* | Shintai *(giữ nguyên)* | danh từ riêng WoD-Kuei-Jin gốc Nhật, không có tiền lệ dịch nghĩa tự nhiên; đã xác nhận `shintai_lifestyle_name`/các key `shintai_*_visible` trong `lifestyles/POD_kueijin/POD_shintai_lifestyle_l_english.yml` đều chưa dịch — giữ nguyên nhất quán theo B0 |
| Wisp *(`Like a Wisp`)* | làn khói | dịch nghĩa hình ảnh (làn khói/hơi mỏng tan biến), không phải danh từ riêng |
| Wayward *(`Wayward's Brand`)* | Kẻ Lạc Lối | dịch nghĩa, tính từ chỉ kẻ đi sai đường/bị các thần từ bỏ |
| Familiar *(`Bind an animal as your familiar`, năng lực Goblin Cat)* | linh thú | đặt mới; chưa có tiền lệ base cho "familiar" (thú linh gắn bó/hộ vệ pháp sư) — "linh thú" ngắn gọn, quen thuộc trong văn học kỳ ảo tiếng Việt |
| Goblin Cat | Mèo Yêu Tinh | dịch nghĩa, tên năng lực triệu hồi/trói buộc linh thú của Kuei-Jin |
| Tortoise Shell *(`Crack the Tortoise Shell`)* | Mai Rùa | dịch nghĩa, ẩn dụ "lớp vỏ bảo vệ của sự tồn tại" trong văn hóa Trung Hoa (rùa = biểu tượng trường tồn) |
| Dragon Medicine | Dược Long | Hán Việt "dược" (thuốc/phương thuốc) + "long" (rồng), khớp văn phong Kuei-Jin/Trung Hoa |
| Joss *(vị thần Trickster đã chốt giữ nguyên ở `POD_religion_kueijin_l_english.yml`/`POD_religion_fae_l_english.yml`)* | Joss *(giữ nguyên)* | tái dùng — "Joss Weaving"→"Dệt Joss", "Give/Take Joss"→"Ban/Lấy Joss"; không dịch thành "vận may"/"phước lành" vì đây là danh xưng thần, không phải danh từ thường |
| Middle Kingdom | Trung Nguyên | dùng lại đề xuất đã có ở dòng ~1695 (ngữ cảnh Hsien/Kuei-Jin, gần với file này hơn "Trung Vương Quốc" ở dòng ~464 vốn thuộc ngữ cảnh Fera/Garou); ⚠️ **hai đề xuất khác nhau đang tồn tại trong TERMINOLOGY.md cho "Middle Kingdom", chưa có key nào thực sự đã dịch trong repo tại thời điểm này** — cần thống nhất một trong hai khi dịch tiếp `religion/`, `game_POD_concepts`, `decisions/` (nhiều chục lần xuất hiện) |
| Dragon Nest(s) *(`own at least one Dragon Nest in your realm`)* | Tổ Rồng | tái dùng bản dịch đã có ở dòng ~1698 |
| P'o, Hun *(hai "hồn phách" — bản chất thấp/Ma tính và bản chất cao/giác ngộ của Kuei-Jin)* | P'o, Hun *(giữ nguyên)* | "P'o" đã có tiền lệ giữ nguyên xuyên suốt mod (kể cả trong văn xuôi tiếng Việt đã dịch ở `POD_religion_kueijin_l_english.yml:170`); "Hun" đi cùng cặp, chưa từng dịch ở đâu — giữ nguyên nhất quán theo B0 |
| Rakshasa Blade | Lưỡi Kiếm Rakshasa | "Rakshasa" giữ nguyên (đã chốt B3c-liên-quan, danh từ riêng Ấn Độ giáo/WoD gốc Phạn ngữ) |
| horoscope *(`already has a horoscope [modifier|E]`)* | lá số tử vi | dịch nghĩa thuật ngữ chiêm tinh phổ thông tiếng Việt |

## B5-numina. Thuật ngữ `interactions/POD_character_interactions_numina_l_english.yml` — tương tác các hệ năng lực Numina (Psi/phàm nhân ngoại cảm, Sorcery, Theurgy, Possessed/Fomori), 275/275 dòng, việc #5

Nguồn: file tổng hợp tương tác của "Numina" — hệ năng lực tâm linh dành cho phàm nhân/psychic (không phải splat siêu nhiên riêng), gồm 5 khối: Psi (ngoại cảm), Necro Psi (tử linh), Sorcery (pháp thuật phàm nhân, gồm Cursing/Dowsing/Oneiromancy/Shapeshift/Spirit Chasing/Alchemical Products), Theurgy (Thần Thuật, đã có tiền lệ B4 `trait_theurgist`="Nhà Thần Thuật"), và Possessed/Fomori (linh thể chiếm hữu phàm nhân, tái dùng "Bane"="Tà Linh" đã chốt B4c). Không có `Glossary()` hai tham số trong file; có 2 lần `[UmbraGlossary('shadowlands')]` (1 tham số, không dịch gì — tự lấy tên qua `Localize()`, theo B4). Đã sửa một lỗi tự thêm bracket không có trong bản gốc trước khi lưu (xem ghi chú dưới).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Psi / Psychic (talent/training/testing) | Ngoại Cảm | tái dùng B0/B5 (`Psychic`="Người Có Năng Lực Ngoại Cảm", dòng ~1193/~1965); ở đây "Psi"/"Psychic" đứng trước danh từ khác (Training/Talents/Invisibility…) nên rút gọn thành "Ngoại Cảm" làm tính từ ghép, giữ nhất quán gốc |
| Necro Psi | Ngoại Cảm Tử Linh | đặt mới, ghép "Ngoại Cảm" + "Tử Linh" (linh hồn người chết), phân biệt với Necromancer/Wraith (B4h) — đây là năng lực phàm nhân giao tiếp người chết, không phải hệ thống Wraith |
| Channel / Unchannel / Partial Channel *(năng lực Necro Psi giao tiếp/chiếm hồn ma)* | Triệu Hồn / Ngừng Triệu Hồn / Triệu Hồn Bán Phần | đặt mới; "Channel" ở đây nghĩa "gọi hồn nhập vào mình" — dùng "Triệu Hồn" (khác "Triệu Hồi" dùng cho gọi thực thể đến, xem dưới) để phân biệt hai khái niệm gần nhau trong cùng file |
| Summon (ghost/wraith/animal — gọi thực thể đến chứ không nhập hồn) | Triệu Hồi | dùng lại tiền lệ vanilla/toàn mod "Triệu Hồi", phân biệt với "Triệu Hồn" (Channel, xem trên) |
| Biocontrol | Điều Khiển Cơ Thể | dịch nghĩa thường, đặt mới |
| Psychic Healing / Psychic Treatment | Trị Liệu Ngoại Cảm / Điều Trị Ngoại Cảm | đặt mới; "Healing"="Trị Liệu", "Treatment"="Điều Trị" — hai từ khác nhau trong bản gốc nên giữ hai bản dịch khác nhau theo quy tắc "một thuật ngữ = một bản dịch" áp dụng ngược lại (hai thuật ngữ gốc khác nhau, không gộp) |
| Precognition | Tiên Tri | dịch nghĩa Hán Việt phổ thông, đặt mới |
| Psychometry | Thần Giao Vật Lý | đặt mới; ghép "Thần Giao" (đã dùng cho Telepathy, xem dưới) + "Vật Lý" (đọc được lịch sử của vật thể qua chạm), phân biệt khỏi Telepathy dù cùng gốc "thần giao" |
| Psychoportation | Dịch Chuyển Ngoại Cảm | đặt mới, dịch nghĩa mô tả (di chuyển bằng tâm trí) |
| Telepathy | Thần Giao Cách Cảm | thuật ngữ Hán Việt phổ thông có sẵn trong tiếng Việt cho "telepathy", không cần đặt mới |
| Psychic Hypnosis / Suggestion / Conditioning / Mind Control | Thôi Miên Ngoại Cảm / Gợi Ý / Điều Kiện Hóa / Điều Khiển Tâm Trí | dịch nghĩa thường, đặt mới cho cả bốn, không có tiền lệ base |
| Psychic Vampirism / Leech Emotions / Leech Life Force | Hút Máu Ngoại Cảm / Hút Cạn Cảm Xúc / Hút Cạn Sinh Lực | đặt mới; "Leech" (động từ hút cạn) dịch nhất quán "Hút Cạn" trong cả file, kể cả ở khối Soulstealing dưới |
| Soulstealing | Đánh Cắp Linh Hồn | đặt mới, dịch nghĩa; "Lifeforce"="Sinh Lực", "Willpower"="Ý Chí" (đã có tiền lệ toàn mod), "Health" ở options heading này dịch "Sức Khỏe" (không dùng "Máu" vì context là hút sinh lực/ý chí/sức khỏe, ba khái niệm tách biệt) |
| Gnosis *(năng lực Fera/Garou — ở đây dùng làm một loại "năng lượng" có thể hút của Numina)* | Gnosis *(giữ nguyên)* | tái dùng tiền lệ giữ nguyên tên WoD gốc; chưa tìm thấy bản dịch nghĩa nào trong toàn mod, giữ nguyên theo B0 |
| Sorcerous Artifact Theft / Mark Artifact / Remove Mark | Trộm Hiện Vật Bằng Pháp Thuật / Đánh Dấu Hiện Vật / Xóa Dấu | dịch nghĩa; "Artifact" viết hoa thường trong tên tương tác dịch thành "Hiện Vật" (danh từ thường, không phải concept link `[artifact|E]` — bản gốc các dòng này không dùng bracket, chỉ dùng chữ "Artifact" trần) |
| Conveyance | Vận Chuyển Thuật | đặt mới, ghép "Vận Chuyển" + "Thuật" theo mẫu Hán Việt các phép thuật khác trong file (Dowsing="Thuật Dò Tìm", Oneiromancy="Thuật Nhập Mộng") |
| Cursing (interaction, nghệ thuật bùa chú/lời nguyền/phước lành) | Chú Thuật | đặt mới; khác "Curse of Gaia" (Lời Nguyền của Gaia, dịch nghĩa trực tiếp "curse"="lời nguyền" ở tên riêng đó) — ở đây "Cursing" là tên nhóm năng lực chung nên dùng "Chú Thuật" (thuật bùa chú) |
| Dowsing | Thuật Dò Tìm | dịch nghĩa, đặt mới |
| Fascination | Mê Hoặc | dịch nghĩa thường |
| Oneiromancy / dreamless / Touch Dream / Bad Dreams / Good Dreams | Thuật Nhập Mộng / vô mộng / Chạm Vào Mộng / Ác Mộng / Mộng Đẹp | dịch nghĩa nhất quán chủ đề "mộng" (dream) xuyên suốt khối |
| Saturnal - Manes | Saturnal - Manes *(giữ nguyên)* | tên riêng nghi lễ La Mã cổ (Saturnalia/Manes — vong hồn tổ tiên La Mã), giữ nguyên theo B0 vì không có tiền lệ dịch và là danh từ lịch sử-tôn giáo cụ thể |
| Weathercraft | Thuật Khống Thời Tiết | đặt mới, dịch nghĩa mô tả |
| Ward against Death | Bùa Trừ Tử | đặt mới; "Ward" (bùa hộ/bùa trấn) dịch "Bùa", "against Death"→"Trừ Tử" (Hán Việt, ngắn gọn cho UI) |
| My current knights/councillors/house members/consorts | Các hiệp sĩ/cận thần/thành viên chi tộc/phối ngẫu hiện tại của ta | dịch nghĩa thường theo văn phong vanilla CK3 (Knight/Councillor/House/Consort đã có bản dịch quen thuộc trong `base_game_vh`); KHÔNG dùng concept link `[knight|E]`/`[councillor|E]`/`[house|E]`/`[consort|E]` vì bản gốc các dòng này chỉ dùng chữ thường "knights"/"councillors"/"house members"/"consorts", không có bracket — tự thêm bracket là lỗi (đã phát hiện và sửa trước khi lưu) |
| Theurgical Heal / Discover True Name / Theurgy Training | Trị Liệu Thần Thuật / Tìm Ra Chân Danh / Huấn Luyện Thần Thuật | tái dùng "Thần Thuật" đã chốt B4 (`trait_theurgist`); "True Name" dịch nghĩa "Chân Danh" (tên thật/danh xưng chân thực), đặt mới |
| Rite of Making *(tương tác triệu hồi Bane-spirit chiếm hữu, tạo Fomori)* | Nghi Thức Tạo Tác | đặt mới, dịch nghĩa; "Making" ở đây nghĩa "tạo ra Fomori", không liên quan "Via Faciendi/Maker" của Road of Lilith (B3k) dù cùng gốc từ "make" — ngữ cảnh WoD khác hẳn (Garou/Fera spirit, không phải giáo phái ma cà rồng) nên không dùng lại "Tạo Tác" của khối đó để tránh gây nhầm, nhưng vẫn là dịch nghĩa tự nhiên trùng ngẫu nhiên |
| bane spirit *(chữ thường, mô tả `POD_create_fomori_interaction_desc`)* | Tà Linh | tái dùng B4c/B5j (`Bane`="Tà Linh"), áp dụng cho cả dạng chữ thường "bane spirit" trong câu văn xuôi |
| $glossary_wyld$-spirit Possession / $glossary_weaver$-spirit Possession | Chiếm Hữu bởi Linh hồn $glossary_wyld$ / Chiếm Hữu bởi Linh hồn $glossary_weaver$ | dịch nghĩa, đảo cấu trúc câu tiếng Việt (đưa "Possession" lên đầu) vì tiếng Việt không ghép tính từ-danh từ kiểu "X-spirit" tự nhiên như tiếng Anh; giữ nguyên `$glossary_wyld$`/`$glossary_weaver$` (ref, không đổi) |
| Touch of Gaia / Command the Earth / Curse of Gaia | Cái Chạm của Gaia / Chỉ Huy Đất Đai / Lời Nguyền của Gaia | dịch nghĩa, mẫu possessive "của X" (Gaia) theo tiền lệ toàn mod |
| Homogeneity | Đồng Hóa | dịch nghĩa Hán Việt, đặt mới |
| Stasis Touch | Cái Chạm Bất Động | dịch nghĩa, đặt mới |
| Bless Artifact | Ban Phước Hiện Vật | dịch nghĩa thường |
| Transcendence *(tương tác Holy Arts giúp Wraith siêu thoát)* | Siêu Thoát | tái dùng tiền lệ B3u (`Transcendence`="Siêu Thoát", positive_afterlife) |
| Turn Vampire / the Embrace / Golconda | Hóa Ma Cà Rồng / Sự Ôm Ấp / Golconda *(giữ nguyên)* | "the Embrace" dùng lại bản dịch quen thuộc toàn mod cho nghi thức biến người thành ma cà rồng; "Golconda" giữ nguyên theo B4i đã chốt |
| Flagrum of the Passion *(tên Hiện vật/artifact cụ thể)* | Cây Roi của Đam Mê | đặt mới, dịch nghĩa; "Flagrum" (roi La Mã cổ dùng tra hình) dịch "Cây Roi" cho dễ hiểu, giữ possessive "của X" |
| Alchemical Product(s) | Sản Phẩm Giả Kim | đặt mới, dịch nghĩa; "Alchemical"→"Giả Kim" (thuật ngữ giả kim thuật quen thuộc tiếng Việt), dùng nhất quán cho cả khối Use/Offer/Sell/Buy/Poison |
| Via Medicamenti *(tên con đường Theurgy cụ thể, tiếng Latin "đường thuốc chữa")* | Via Medicamenti *(giữ nguyên)* | tên Latin riêng của một con đường Theurgy, giữ nguyên theo mẫu "Via Faciendi"/"Via Spinae"/"Via Calantica" đã chốt B3k (không dịch các tên "Via X" trong toàn mod) |
| Hedge magic *(Numina dùng "hedge magic" mô tả Sorcery/Shapeshift của phàm nhân)* | thuật huyền bí dân gian | dịch nghĩa mô tả; "hedge magic/witch" trong văn hóa dân gian phương Tây chỉ phép thuật truyền miệng/nghiệp dư, không phải trường phái chính thống — dùng "dân gian" để truyền tải sắc thái đó, không dùng "Huyền Thuật" (đã dành riêng cho Tremere Magick, B4) |

## B5-hunter. Thuật ngữ `interactions/POD_character_interactions_hunter_l_english.yml` — sự kiện Inquisition Hunt + Holy Arts + Chi Exorcism, 369/369 dòng, việc #5

Nguồn: file lớn dịch qua 4 agent chia đoạn dòng (1-92, 93-183, 184-276, 277-369 — chú ý file thật có 369 dòng dù `wc -l` báo 368 do dòng cuối không có newline). Nội dung: chuỗi sự kiện tường thuật "Inquisition Hunt" (`POD_inquihunt.*`, có biến thể `.fera` khi mục tiêu là Garou/Fera thay vì ma cà rồng), nhóm tương tác Holy Arts (`POD_ha_*`), danh sách tật/bệnh bị Holy Arts chữa (`POD_exorcism_*`), và 1 dòng lẻ cuối file `gotchiweapon_notification` (Kuei-Jin Chi weapon).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| leech *(danh từ miệt thị Fera gọi ma cà rồng, khác nghĩa "hút cạn" đã có)* | con đỉa | đặt mới, dịch nghĩa hình ảnh cho ngữ cảnh miệt thị; áp dụng nhất quán nếu gặp lại ở event_localization/ |
| witch hunt *(loại crime, `INQUIHUNT_DISCOVERY_DESC`)* | săn lùng tà thuật | đặt mới, chưa có tiền lệ `crime_witch_hunt` trong base_game_vh |
| Pyrrhic Victory *(tên sự kiện `.6.t`)* | Chiến Thắng Kiểu Pyrros | đặt mới, phiên âm "Pyrros" theo cách base_game_vh phiên âm tên riêng lịch sử |
| Sons against Fathers *(tên sự kiện `.3.t`)* | Con Cái Chống Lại Cha Mẹ | đặt mới, dịch nghĩa thường |
| Lay on Hands *(interaction Holy Arts)* | Đặt Tay Chữa Lành | đặt mới, không có tiền lệ vanilla (CK3 gốc không có tương tác này) |
| Intercession | Cầu Bầu | đặt mới |
| Penance *(interaction Holy Arts, phạt/nguyền — khác "Sám Hối" nghĩa tôn giáo thường)* | Sám Hối | giữ nghĩa gốc, phù hợp văn cảnh trừng phạt của interaction |
| Unwavering Vision | Tầm Nhìn Kiên Định | đặt mới |
| Lifting the Veil | Vén Màn Bí Mật | đặt mới |
| Sunder | Xé Toạc | đặt mới |
| Rod and Staff *(điển tích Thi Thiên 23)* | Trượng Và Gậy | đặt mới, theo điển tích Kinh Thánh |
| Wrath of God | Thịnh Nộ Của Chúa | đặt mới |
| Disrupted Contacts *(modifier)* | Liên Lạc Bị Gián Đoạn | đặt mới |
| Transform Ailing Flesh | Biến Đổi Xác Thịt Bệnh Hoạn | đặt mới |
| Gout *(tiêu đề ngắn trong danh sách chữa bệnh, khác `trait_gout_ridden`="Gút Hành Hạ")* | Gút | rút ngắn cho tiêu đề danh sách, không dùng bản dịch trait đầy đủ |
| Pox | Đậu Mùa | đặt mới, không có `trait_pox` để đối chiếu |
| Plague *(không có `trait_plague` trong base)* | Dịch Bệnh | đặt mới |
| Castration *(mô tả tình trạng bị chữa, khác `trait_eunuch`="Hoạn Quan" là danh xưng nhân vật)* | Thiến | đặt mới, phân biệt danh xưng vs. hành động/tình trạng |
| Touch of Peace | Chạm Tay Bình Yên | đặt mới |
| Judgement of Heaven | Sự Phán Xét Của Thiên Đường | tái dùng "Heaven"="Thiên Đường" đã chốt |
| Spiritual Guidance | Hướng Dẫn Tâm Linh | đặt mới |
| Chi Exorcism *(phân biệt với "Cleanse"="Tẩy Trừ" đã dùng ở nơi khác)* | Trừ Tà Bằng Khí | đặt mới, tránh trùng "Tẩy Trừ" |
| trait_depressed_genetic / trait_lunatic_genetic *(biến thể "genetic" của Trầm Cảm/Loạn Trí)* | U Sầu / Tâm Thần | ✅ tái dùng đúng bản dịch riêng của base_game_vh cho biến thể di truyền, KHÔNG dùng "Trầm Cảm"/"Loạn Trí" thường |
| gotchiweapon_notification *(Got a Chi Enhanced Weapon)* | Đã nhận Vũ Khí Tăng Cường Bằng Khí | đặt mới, dòng lẻ cuối file không thuộc đoạn của agent nào — đã dịch bổ sung khi phát hiện file thật có 369 dòng chứ không phải 368 |

## B5-fae. Thuật ngữ `interactions/POD_character_interactions_fae_l_english.yml` — tương tác Fae (Cantrip/Art/Realm/Solarium/Oath Guardian), 458/458 dòng, việc #5

Nguồn: file lớn dịch qua 4 agent chia đoạn (1-114, 115-229, 230-341, 342-458). Nội dung: tên các Art Fae (Chicanery/Legerdemain/Primal/Soothsay/Wayfare/Aphrodesia/Kryos/Metamorphosis/Pyretics/Chronos/Dream Craft/Naming/Sovereign/Infusion/Tale Craft/Petros/Aquis/Pyros/Stratus/Verdage — giữ nguyên theo B4b), perk/interaction riêng (Ravaging/Rhapsody/Reaving/Musing/Fuddle/Fugue/Haunted Heart/Veiled Eyes — giữ nguyên tạm thời, xem ghi chú), sự kiện Oath Guardian bảo vệ nhân vật, Solarium (naming các loại cây/hoa), True Jade, Changeling. Đã sửa 2 lỗi thật trước khi lưu: đoạn ghép giữa agent 230-341 và 342-458 làm mất 2 script token `[target.GetHerHis]` (dòng 266) và `[oath_guardian.GetHerselfHimself]` (dòng 267) khi agent diễn đạt lại câu — bracket count lệch 264→262 lộ ra lỗi, đã bổ sung lại token vào đúng vị trí ngữ nghĩa.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Oath Guardian | Người Bảo Hộ Lời Thề | đặt mới, danh xưng nhân vật NPC hộ vệ do Fae ràng buộc lời thề bảo vệ |
| Ravaging / Rhapsody / Reaving / Musing *(tên interaction/quyền năng Cantrip-Realm)* | Ravaging / Rhapsody / Reaving / Musing *(giữ nguyên tạm thời)* | `lifestyles/POD_fae_lifestyle_l_english.yml` (chưa dịch) cũng để các perk_name này ở dạng tiếng Anh thô — chưa có tiền lệ chính thức; cần xác nhận lại (dịch nghĩa hay giữ nguyên) khi dịch tới file lifestyle đó, rồi áp dụng ngược lại nếu đổi quyết định |
| Fuddle / Fugue / Haunted Heart / Veiled Eyes *(tên perk Cantrip)* | Fuddle / Fugue / Haunted Heart / Veiled Eyes *(giữ nguyên tạm thời)* | cùng lý do với Ravaging/Rhapsody/Reaving/Musing — chờ đối chiếu `POD_fae_lifestyle_l_english.yml` |
| Reverie *(tên riêng loại triều đình/sự kiện Fae)* | Reverie *(giữ nguyên)* | chưa có tiền lệ dịch nghĩa |
| Mooch (perk) | Trộm Vặt | đặt mới, tránh dùng từ lóng hiện đại |
| Omen / Augury (perk) | Điềm Báo / Điềm Triệu | đặt mới, phân biệt 2 khái niệm gần nghĩa |
| Tattletale (perk) | Kẻ Mách Lẻo | đặt mới |
| Fair is Foul / Foul is Fair *(cặp đối lập hệ Soothsay, chơi chữ Macbeth)* | Dữ / Lành | đặt mới, cần xác nhận lại nếu gặp cụm này ở file khác |
| Dream Time / Dream-Riding | Thời Gian Mộng Cảnh / Cưỡi Mộng | đặt mới, nhất quán với "Cõi Mộng"=Dreaming đã chốt B4b |
| Permanence | Trường Tồn | đặt mới |
| Trait Editor *(nhóm interaction `POD_fae_interactions.200.*`)* | Bộ Chỉnh Sửa Đặc Tính | đặt mới |
| Fancy / Yearn / Covet / Crave / Need *(perk hệ ham muốn)* | Say Mê / Khao Khát / Thèm Muốn / Thèm Khát / Nhu Cầu | đặt mới, 5 mức độ ham muốn khác nhau |
| Cold Shock / Frost Facsimile / Crystal Prison / Coldheart *(perk hệ Kryos)* | Sốc Lạnh / Bản Sao Băng Giá / Ngục Pha Lê / Tim Băng Giá | đặt mới |
| Coalesce / Mold *(interaction hệ Petros/tạo hình)* | Hợp Nhất / Nhào Nặn | đặt mới |
| Transmute Metal / Transmute Earth | Biến Kim Loại / Biến Đất Đá | đặt mới |
| Banish Fae | Trục Xuất Fae | tái dùng "Trục Xuất" đã chốt B4h/B4j |
| Call Patron | Triệu Gọi Người Bảo Trợ | tái dùng "Người Bảo Trợ" đã chốt |
| True Jade *(tên interaction, đã có tiền lệ tại `gui/POD_umbra_window_l_english.yml:543`)* | Ngọc Bích Chân Chính | ✅ tái dùng nguyên trạng |
| Changeling | Đứa Trẻ Bị Tráo | đặt mới, đúng nghĩa gốc dân gian "changeling" |
| naming_the_crop/weed/flower/thorn/tree/mushroom *(Solarium)* | Mùa Vụ/Cỏ Dại/Hoa/Gai/Cây/Nấm | đặt mới, các loại cây trong Solarium |

## B5-vampire-p3. Thuật ngữ `interactions/POD_character_interactions_vampire_l_english.yml` dòng 322-444, việc #5

Đoạn 3/nhiều của file lớn (1187 dòng), chia dịch theo agent riêng từng đoạn. Nội dung: tương tác Infiltrate (Toreador/Court), Rite of Status (Gangrel), Enforce Masquerade, Madness Network (Malkavian), Send Adviser (Cappadocian), Web of Knives bounty (Assamite/Banu Haqim), Choose Parent/Mentor/Sifu, Ask Embrace. `[Glossary('Sire','game_concept_Sire_desc')]` xuất hiện 1 lần — giữ nguyên tham số 1 "Sire" theo tiền lệ toàn mod (B4d/roadofsin, chưa có bản Việt chính thức cho `game_concept_Sire`).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Infiltrate *(POD_infiltrate_interaction, xâm nhập triều đình dưới lốt neonate)* | Xâm nhập | đặt mới; mô tả dùng "kẻ mới được Trao truyền" cho "neonate" theo tiền lệ B2b |
| Rite of Status *(POD_gangrel_challenge_interaction, nghi thức Gangrel giới thiệu bản thân)* | Nghi thức Địa vị | đặt mới, dịch nghĩa; khác "Nghi Lễ"/"Nghi thức" dùng cho các nghi lễ khác trong mod nhưng cùng mẫu |
| Ethic of Succor *(POD_ventrue_succor_interaction, quyền được cứu giúp của Ventrue)* | Đạo lý Cứu giúp | đặt mới; "Ethic" dịch "Đạo lý" (khác "Ethics"="Đạo Lý" B3r — viết hoa khác do đây là cụm thường trong câu văn, không phải tên faith) |
| Madness Network *(Malkavian, mạng lưới tâm linh giữa các Malkavian)* | Mạng lưới Điên loạn | đặt mới, dịch nghĩa trực tiếp |
| Trial by War *(Voivode, thử thách bằng đấu tay đôi/chiến trận)* | Thử thách bằng Chiến trận | đặt mới |
| Web of Knives *(tổ chức sát thủ Banu Haqim, đã có tiền lệ `k_webofknives: "Web of Knives"` ở `titles_POD_l_english.yml:37`, giữ nguyên tiếng Anh toàn mod)* | Mạng lưới Dao găm | ⚠️ **lệch khỏi tiền lệ title đã chốt** — `titles_POD_l_english.yml` giữ nguyên "Web of Knives" như danh xưng vương quốc/tổ chức (tên riêng, B0). Ở đây dịch nghĩa "Mạng lưới Dao găm" cho tự nhiên hơn trong câu văn tương tác (`POD_create_bounty_interaction`, `POD_chase_bounty_interaction`). **CẦN XÁC NHẬN LẠI**: nên thống nhất giữ nguyên "Web of Knives" xuyên suốt mod theo tiền lệ title, hay tách hai ngữ cảnh (tên tổ chức/tước vị giữ nguyên, cách gọi thông tục trong lời thoại thì dịch nghĩa). Đánh dấu nghi vấn — có thể cần sửa lại khi rà soát toàn bộ các file nhắc tới Web of Knives. |
| Ask Embrace *(POD_charjoin_become_vampire_interaction, xin ai đó Trao truyền mình)* | Xin được Trao truyền | tái dùng "Trao truyền" đã chốt B2 (`pod_Embrace`) |
| Choose Parent / Choose Mentor *(chọn quan hệ cha-mẹ/sư phụ ma cà rồng, khác Ask Embrace)* | Chọn Cha/Mẹ / Chọn Sư phụ | đặt mới; `POD_choose_parent_interaction` dùng cho quan hệ huyết thống nói chung (không riêng Sire), tách khỏi "Sifu" (Kuei-Jin, giữ nguyên B5k) và "Sire" (giữ nguyên) |
| One Eyed *(POD_blood_heal_one_eyed, tên một biến thể Blood Heal)* | Chột Mắt | đặt mới, dịch nghĩa thông tục |
| Mimic Face / Give Face / Restore Your Face / Restore Target's Face *(Vampshapeshift, đổi mặt bằng Dị năng)* | Bắt chước Gương mặt / Trao Gương mặt / Khôi phục Gương mặt của Ngươi / Khôi phục Gương mặt của Mục tiêu | đặt mới, dịch nghĩa trực tiếp |
| childer *(recipient_secondary_POD_cappadocian_send_advisor_interaction: "Childe")* | Childe *(giữ nguyên)* | tiền lệ B4d/B5 — chưa có bản Việt chính thức, giữ nguyên tiếng Anh xuyên suốt mod cho tới khi `game_POD_concepts` chốt |

## B5-vampire-p4. Thuật ngữ `interactions/POD_character_interactions_vampire_l_english.yml` dòng 445-592, việc #5

Đoạn 4/nhiều của file lớn (1187 dòng). Nội dung: Ghoul/Herd hóa tù nhân, Blink (Celerity), Vanish/Silence of Death (Obfuscate), Send the Eighth Plague (Animalism), Create Gargoyle (Thaumaturgy), Create Zombu (Necromancy), một loạt perk-interaction đặt theo tên riêng kiểu "X's Y" (Kiss of Lachesis, Clio's Kiss, Pariah's Caress, King David's Blessing, Rayzeel's Song, Sword of the Righteous, Dagon's Call), Dementation/Lunatic Eruption/Touch of the Saints/Melpominee/Calling Song/Madrigal (Malkavian voice powers), artifact-spirit interactions, Purification, Unburden the Bestial Soul, Subsist Breath, Soul Exchange. Không có `Glossary()`/`UmbraGlossaryLocalized()`/`Select_CString()` trong đoạn này (0 lần).

| English | Tiếng Việt | Ghi chú |
|---|---|---|
| Ghoul Prisoner *(POD_ghoulify_prisoner_interaction)* | Biến Tù Nhân thành Bộc huyết | đặt mới; tái dùng "Bộc huyết" (Ghoul, đã chốt) làm động từ hóa, nhất quán tinh thần "Ghoulify"→"Biến thành Bộc huyết" đã có ở B5j |
| undying thrall *(mô tả `ghoulify_prisoner`, ngữ cảnh domitor-ghoul)* | Nô Bộc bất tử | tái dùng "Nô Bộc" đã chốt cho "Thrall" trong ngữ cảnh ghoul (B5j), không nhầm với "Nô Lệ" (Demon-cultist context) |
| Blink *(Celerity power di chuyển quân nhanh, modifier + interaction cùng tên)* | Chớp Dời | đặt mới, dịch nghĩa ngắn gọn cho tốc độ siêu nhiên |
| Drained *(modifier hệ quả của Blink)* | Kiệt Sức | đặt mới, dịch nghĩa |
| Vanish *(Obfuscate power dừng mọi scheme nhắm vào mình)* | Biến Mất | đặt mới, dịch nghĩa trực tiếp |
| Silence of Death *(Obfuscate power cản trở giao tiếp nạn nhân)* | Sự Tĩnh Lặng của Tử Thần | đặt mới, dịch nghĩa |
| Send the Eighth Plague *(Animalism power gieo dịch bệnh lên cả vương quốc)* | Giáng Xuống Tai Ương Thứ Tám | đặt mới; "Eighth Plague" ám chỉ 10 tai ương Ai Cập trong Kinh Thánh, dịch "Plague"→"Tai Ương" theo lối cổ trang |
| Create Gargoyle *(Thaumaturgical Experiment)* | Tạo Gargoyle | tái dùng "Gargoyle" giữ nguyên đã chốt B4d; "Thaumaturgical Experiment"→"Thí Nghiệm Thaumaturgy" (giữ tên riêng Discipline theo B0) |
| gargoyle caste (Stone Dog/Bingmayong/Shade/Blood Guardian/Boyar/Caryatid/Scout/Warrior/Sentinel/Chatterer/Sand Serpent/Rattler/Fairy/Onyx Cat/Golden Manticore/Kintsugi/Rogata/Totai) | đẳng cấp Chó Đá/Bingmayong/Bóng Ma/Vệ Huyết/Boyar/Caryatid/Trinh Sát/Chiến Binh/Lính Canh/Kẻ Lải Nhải/Xà Cát/Rắn Chuông/Tiên/Mèo Onyx/Manticore Vàng/Kintsugi/Rogata/Totai | tái dùng "đẳng cấp" = Caste đã chốt (B4d/B4h); các tên caste có gốc văn hóa cụ thể (Bingmayong = tượng binh mã đất nung Tần Thủy Hoàng, Boyar = quý tộc Slav, Caryatid = tượng cột Hy Lạp, Kintsugi/Rogata/Totai = gốc Nhật) giữ nguyên phiên âm gốc, chỉ dịch phần mô tả tiếng Anh phổ thông (Stone Dog, Shade, Blood Guardian, Scout, Warrior, Sentinel, Chatterer, Sand Serpent, Rattler, Fairy, Onyx Cat, Golden Manticore) |
| Create Zombu *(Necromantic ceremony hồi sinh xác chết bằng hiến tế)* | Tạo Zombu | tái dùng "Zombu" giữ nguyên đã chốt B4j; "Necromantic"→"Thuật Gọi Hồn" theo tiền lệ B4d |
| Kiss of Lachesis / Clio's Kiss *(perk đổi tuổi tác / đổi chủ đất qua thời gian, tên theo nữ thần Hy Lạp)* | Nụ Hôn của Lachesis / Nụ Hôn của Clio | đặt mới; giữ tên riêng thần thoại (Lachesis - một trong ba Moirai/Số Mệnh, Clio - nàng thơ Lịch sử), dịch khung "Kiss of X"→"Nụ Hôn của X" nhất quán |
| Dementation *(tên Discipline/power gieo điên loạn, Malkavian)* | Dementation *(giữ nguyên)* | chưa có tiền lệ dịch nghĩa tên riêng Discipline cụ thể, nhất quán B0 (giống Potence/Celerity/Fortitude giữ nguyên) |
| Lunatic Eruption / Lunatic Invocation *(power khơi dậy phẫn cuồng tập thể)* | Cơn Bộc Phát Điên Cuồng / Sự Triệu Hồi Điên Loạn | đặt mới, dịch nghĩa |
| Touch of the Saints *(power chữa loạn trí)* | Cái Chạm của Các Thánh | đặt mới, dịch nghĩa trực tiếp |
| Melpominee / Calling Song / Madrigal *(các power "tiếng hát" của Malkavian, tên riêng thuật ngữ V:tM)* | Melpominee / Khúc Ca Triệu Gọi / Madrigal | "Melpominee" và "Madrigal" là tên riêng power nguyên tác giữ nguyên; "Calling Song" dịch nghĩa vì là cụm mô tả rõ ràng (triệu tập triều thần/khách khứa) |
| Rouse Artifact Spirit | Đánh Thức Linh Hồn Hiện Vật | đặt mới, dịch nghĩa |
| Upgrade [Skill] Modifier *(6 skill: Prowess/Diplomacy/Martial/Stewardship/Intrigue/Learning)* | Nâng Cấp Hệ Số [Kỹ Năng] | đặt mới; "Modifier"→"Hệ Số" (không phải "Bộ Chỉnh Sửa" dùng cho status effect UI) vì ngữ cảnh nâng cấp thuộc tính hiện vật; Prowess→Vũ Dũng, Martial→Chỉ Huy, Stewardship→Quản Trị, Intrigue→Trù Tính, Learning→Học Thức (nhất quán thuật ngữ kỹ năng nhân vật của base_game_vh) |
| Hunt Spirit | Săn Linh Thể | tái dùng "Linh Thể" (Spirit) đã chốt B4 |
| Purification *(power chữa loạn trí bằng "third eye")* | Thanh Tẩy | đặt mới, dịch nghĩa |
| Pariah's Caress *(perk khiến mục tiêu bị ghét bỏ)* | Cái Vuốt Ve của Kẻ Bị Ruồng Bỏ | đặt mới; "Pariah"→"Kẻ Bị Ruồng Bỏ" dịch nghĩa, khung "X's Caress"→"Cái Vuốt Ve của X" nhất quán các power dạng sở hữu cách khác trong đoạn |
| King David's Blessing *(perk chữa stress trait)* | Phước Lành của Vua David | đặt mới; "David" giữ tên riêng Kinh Thánh, "Blessing"→"Phước Lành" theo lối cổ trang |
| Unburden the Bestial Soul *(perk nâng Virtue/chữa Derangement)* | Trút Bỏ Gánh Nặng của Linh Hồn Thú Tính | tái dùng "Trút Bỏ Gánh Nặng" = Unburden đã chốt B5e; "Bestial Soul"→"Linh Hồn Thú Tính" dịch nghĩa, nhất quán "Beast"→"Dã Thú"/"thú tính" toàn mod |
| Virtue(s) *(Golconda/Salubri, đối lập Derangement)* | Đức Hạnh | tái dùng theo lối dịch nghĩa phổ thông, không có tiền lệ WoD riêng cần giữ nguyên |
| Derangement(s) | Sự Loạn Trí | đặt mới, dịch nghĩa; dùng nhất quán cho mọi chỗ "derangement"/"Cure Derangements" xuất hiện trong đoạn |
| Subsist Breath *(perk hút hơi thở để no Hunger)* | Hơi Thở Duy Sinh | đặt mới; "Subsist"→"Duy Sinh" (duy trì sự sống) dịch thoát ý ngắn gọn cho tên power, mô tả dùng "tiêu thụ hơi thở" |
| Rayzeel's Song *(perk chữa bệnh/vết thương hàng loạt, tên theo Rayzeel — Nagaraja huyền thoại)* | Khúc Ca của Rayzeel | đặt mới, giữ tên riêng "Rayzeel", khung "X's Song"→"Khúc Ca của X" |
| Soul Exchange | Hoán Đổi Linh Hồn | đặt mới, dịch nghĩa trực tiếp |
| Sword of the Righteous *(perk dùng Vitae tăng vũ dũng vũ khí)* | Thanh Kiếm của Kẻ Chính Trực | đặt mới, dịch nghĩa; "Righteous"→"Kẻ Chính Trực" theo lối cổ trang tôn giáo |
| Dagon's Call *(perk gây hại từ xa, tên theo Dagon — thần biển Philistine/Lovecraft)* | Lời Kêu Gọi của Dagon | đặt mới, giữ tên riêng "Dagon", khung "X's Call"→"Lời Kêu Gọi của X" |

Ghi chú kỹ thuật: đoạn 445-592 không chứa `Glossary()`/`UmbraGlossaryLocalized()`. Đã đối chiếu token trước/sau: ref `$...$` 1→1 (chỉ `$pod_vitae$`), bracket 35→35, icon 0→0, `\n` 0→0, `\"` 0→0, em dash `—` 2→2, tổng 148 dòng khớp.

## B5-vampire-p1. Thuật ngữ `interactions/POD_character_interactions_vampire_l_english.yml` dòng 1-155 (Blood Surge/Blood Heal/Find Mortals/Offer Draught/Shapeshift/Animal Dominion), việc #5

File 1186 dòng tổng, đây là đoạn đầu (155 dòng). Nhiều key khác trong cùng file (dòng 156+) dùng lại các thuật ngữ dưới đây — các agent dịch phần sau PHẢI tái sử dụng, không đặt lại.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Blood Surge *(tên interaction, `POD_blood_surge`)* | Kích Huyết | đặt mới; dịch nghĩa "khuấy động/kích hoạt máu", ngắn gọn phù hợp UI, khác "Rouse the Blood" nếu gặp riêng (chưa xuất hiện trong đoạn này) |
| Blood Heal *(tên interaction, `POD_blood_heal`)* | Trị Liệu Huyết | đặt mới; ghép "Trị Liệu" (chữa lành) + "Huyết" (máu, dạng Hán Việt ghép từ, nhất quán văn phong "Huyết Tộc"/"Huyết Thuật" đã chốt B2) |
| Offer Draught / Draught (of Might/Elegance/Endurance) *(`POD_offer_draught`)* | Dâng Rượu Huyết / Rượu Huyết (Sức Mạnh/Thanh Nhã/Bền Bỉ) | đặt mới; "Draught" (một ngụm/liều thuốc uống) dịch thành "Rượu Huyết" — hành động ma cà rồng ban máu tăng cường thể chất cho ghoul/thuộc hạ, tương tự rượu bổ; "Might"→"Sức Mạnh", "Elegance"→"Thanh Nhã", "Endurance"→"Bền Bỉ" (dịch nghĩa tính từ thường) |
| Find Mortals *(`POD_find_mortals`)* | Tìm Người Phàm | đặt mới; "mortal(s)" dùng "người phàm" xuyên suốt đoạn này (peasants/warriors/diplomats/…), khác "con người"/"nhân loại" để giữ sắc thái ma cà rồng nhìn xuống người thường |
| Scoundrels / Peasants / Clergy / Warriors / Diplomats / Merchants *(loại người phàm theo skill)* | Kẻ Bất Lương / Nông Dân / Giáo Sĩ / Chiến Binh / Nhà Ngoại Giao / Thương Nhân | dịch nghĩa thường, nhất quán cách gọi nghề nghiệp/tầng lớp trong base_game_vh |
| Ashen Nobles / Knights / Seneschals / Thieves / Cults *(biến thể "cao cấp" của Find Mortals)* | Quý Tộc / Hiệp Sĩ / Quản Gia / Kẻ Trộm / Giáo Phái Tro Tàn | đặt mới; "Ashen" dịch nghĩa "Tro Tàn" (tính từ mô tả nhóm người phàm đặc biệt/hiếm, không có tiền lệ base) |
| Scry the Soul *(năng lực Auspex, `POD_find_mortals_interaction_*.tt`)* | Thấu Thị Linh Hồn | đặt mới; "Scry" (nhìn thấu qua phép thuật) → "Thấu Thị", "Soul"→"Linh Hồn"; Auspex giữ nguyên tên Discipline (theo B0, chưa có tiền lệ dịch tên Discipline nào — Potence/Celerity/Fortitude/Auspex/Animalism đều giữ nguyên) |
| Choleric/Melancholic/Phlegmatic/Sanguine Humors *(danh từ mô tả máu người phàm, khác "Resonance")* | Thể Dịch Choleric/Melancholic/Phlegmatic/Sanguine | đặt mới; "Humors" (thuyết thể dịch y học cổ) → "Thể Dịch", tên 4 khí chất giữ nguyên tiếng Anh nhất quán với quyết định B4x/gui/POD_see_resonance (chưa dịch tên 4 temperament, chờ `game_POD_concepts_l_english.yml`) |
| resonance *(danh từ thường, khác "Resonance" tên riêng 4 loại)* | resonance *(giữ nguyên, chữ thường)* | nhất quán với quyết định giữ nguyên tên temperament ở B4x — cụm "choleric resonance" trong `.tt` giữ nguyên cả hai từ tiếng Anh vì đây là thuật ngữ chưa chốt dịch nghĩa (concept gốc `game_concept_choleric_lifestyle` chưa dịch) |
| Grand City *(concept link `[grand_city\|E]`)* | *(không đổi, chỉ dịch câu quanh nó)* | tái dùng "Đại Thành" đã chốt B4cat1 nếu cần viết trực tiếp, nhưng ở đây chỉ xuất hiện dạng `[grand_city|E]` nên không có chữ để dịch |
| Shapeshift *(`POD_vampshapeshift`, năng lực Protean/Vicissitude biến hình)* | Biến Hình | đặt mới, dịch nghĩa thường |
| Call Animals / Animal Dominion *(`POD_animaldominion`, năng lực Animalism)* | Triệu Gọi Muông Thú | đặt mới; "Call"→"Triệu Gọi" nhất quán các interaction triệu hồi khác (B5g `Summon Spirit`→"Triệu hồn"; ở đây dùng "Triệu Gọi" cho động vật để phân biệt với triệu hồi linh hồn) |
| Godhead *(`POD_vampshapeshift_interaction_godhead`, hình thái biến hình cấp cao)* | Thần Thể | đặt mới; ghép Hán Việt "Thần" + "Thể" (thân xác), giữ giọng trang trọng/gothic |
| Chiropteran Marauder *(hình dạng biến hình dơi cấp cao)* | Kẻ Cướp Bóc Chiropteran | đặt mới; "Chiropteran" (thuật ngữ sinh học chỉ bộ Dơi, dùng như biệt danh giống loài trong lore) giữ nguyên tiếng Anh vì không có bản dịch phổ thông tương đương, "Marauder"→"Kẻ Cướp Bóc" dịch nghĩa |
| Zulo Shape / Draconic Form / Typhonic Form *(các hình dạng biến hình đặc biệt theo clan)* | Hình Dạng Zulo / Hình Dạng Rồng / Hình Dạng Typhon | "Zulo"/"Typhonic"→"Typhon" giữ tên riêng gốc thần thoại/lore, "Draconic"→"Rồng" dịch nghĩa |
| Aspect of the Beast *(perk mua bằng tương tác)* | Khía Cạnh của Dã Thú | đặt mới; "Beast" dùng "Dã Thú" nhất quán với cách gọi "The Beast" (bản năng thú tính ma cà rồng) trong toàn mod |
| Potence / Celerity / Fortitude *(tên Discipline, xuất hiện trong `MUST_HAVE_MORE_*_THAN_DRINKER`)* | Potence / Celerity / Fortitude *(giữ nguyên)* | chưa có tiền lệ dịch nghĩa tên riêng từng Discipline cụ thể (khác "Discipline" nói chung = "Dị năng" đã chốt B2); giữ nguyên theo B0, nhất quán cách xử lý "Vitae"/"Antediluvian" |
| Feeding on Animals *(`POD_drain_animal_interaction_toast`, dòng toast không bị comment)* | Ăn Thịt Động Vật | đặt mới; các dòng `#POD_drain_animal_*` khác trong đoạn này bị comment (`#` đầu dòng) nên giữ nguyên tiếng Anh, không dịch theo mục 5 TRANSLATION_RULES.md |

## B5-vampire-p6. Thuật ngữ `interactions/POD_character_interactions_vampire_l_english.yml` dòng 727-889, việc #5

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Train / Mass Train (Disciplines) *(`POD_train_disciplines_interaction`, `POD_mass_train_disciplines_interaction`)* | Rèn Luyện / Rèn Luyện Hàng Loạt | đặt mới; "Train" dịch "Rèn luyện" (dạy Dị năng cho người khác), khác "Teach" cùng nghĩa trong câu mô tả dùng động từ "Dạy" |
| Discipline(s) *(trong `Glossary('Disciplines','game_concept_discipline_desc')`)* | Dị năng | tái dùng B2 đã chốt; chỉ dịch tham số 1 hiển thị, giữ nguyên key `game_concept_discipline_desc` ở tham số 2 |
| student *(danh xưng người học Discipline qua Train)* | học trò | dịch nghĩa thường, giọng trung cổ |
| childe *(hậu duệ trực tiếp do Embrace tạo ra, `POD_embrace_prisoner_interaction_desc`)* | hậu duệ | tái dùng cách dịch "childe" đã dùng xuyên suốt các phần trước của file này (không lập bảng riêng vì đã nhất quán) |
| Homunculus *(`POD_create_homunculus_interaction`, bản sao người phàm của chính ma cà rồng)* | Homunculus *(giữ nguyên)* | đặt mới theo B0; thuật ngữ giả kim/huyền học gốc Latin, cộng đồng quen đọc tiếng Anh, không có bản dịch phổ thông tương đương ngắn gọn |
| Mask (of a Thousand Faces) *(`POD_mask_of_a_thousand_faces_interaction`)* | Mặt Nạ | đặt mới; dịch nghĩa ngắn gọn cho tên nút UI, tên đầy đủ "of a Thousand Faces" không xuất hiện trong chuỗi hiển thị (chỉ có trong tên key) |
| Old Friend *(`POD_old_friend_interaction`)* | Bạn Cũ | đặt mới, dịch nghĩa thường |
| Create Name *(`POD_create_name_interaction`, xóa hook/claim/truce/secret/relation)* | Tạo Danh Tính | đặt mới; "Create Name" ở đây nghĩa là xóa sạch lai lịch cũ để tạo danh tính mới, không phải "tạo tên gọi" theo nghĩa đen |
| Horrid Blade of the Demons *(`POD_horrid_blade_of_the_demons_interaction`, năng lực Daimonion)* | Lưỡi Kiếm Kinh Hoàng của Quỷ | đặt mới, dịch nghĩa |
| Mirror's Visage *(`POD_mirror_duplicate_interaction`, năng lực Mytherceria/Chimerstry tạo phân thân)* | Gương Mặt Phân Thân | đặt mới; "Visage" (dung mạo) ghép với "Mirror" (gương) thành "Gương Mặt Phân Thân" để truyền tải ý tạo bản sao ảo ảnh |
| Sensory Deprivation *(`POD_sensory_deprivation_interaction`)* | Tước Đoạt Giác Quan | đặt mới, dịch nghĩa |
| Discern the Aura *(`POD_discern_the_aura_interaction`, năng lực Auspex tìm người phàm theo thuộc tính)* | Thấu Thị Hào Quang | đặt mới; "Aura" → "Hào Quang" (khí/vầng sáng quanh cơ thể theo huyền học), "Discern" → "Thấu Thị" nhất quán với "Scry" đã dịch cùng gốc ở B5-vampire-p5 |
| Reveal Scheme *(`POD_the_mind_revealed_interaction`)* / Reveal Secret *(`POD_omniscience_interaction`)* | Phơi Bày Âm Mưu / Phơi Bày Bí Mật | đặt mới; "Reveal" → "Phơi Bày", "Scheme" → "Âm Mưu" (đã chốt TRANSLATION_RULES mục 4 ví dụ), "Secret" → "Bí Mật" |
| Personality Metamorph / Sexuality Metamorph *(`POD_personality_metamorph_interaction`, `POD_sexuality_metamorph_interaction`)* | Biến Đổi Tính Cách / Biến Đổi Thiên Hướng Tình Dục | đặt mới; "Metamorph" dùng động từ "Biến Đổi" nhất quán với "Shapeshift"→"Biến Hình" ở B5-vampire-p5 nhưng khác đối tượng (tính cách/thiên hướng, không phải hình dạng) |
| Fist of the Titans *(`POD_fist_of_the_titans_interaction`, tấn công niệm động toàn bộ hiệp sĩ)* | Nắm Đấm Titan | đặt mới; "Titans" giữ nguyên tên thần thoại Hy Lạp phiên âm Hán Việt quen thuộc "Titan" |
| The Forger's Hammer *(`POD_the_forgers_hammer_interaction`, tăng sức mạnh vũ khí hiện vật)* | Búa của Người Thợ Rèn | đặt mới, dịch nghĩa |
| Lend the Supernatural Vigor *(`POD_lend_the_supernatural_vigor_interaction`)* | Ban Tặng Sinh Lực Siêu Nhiên | đặt mới; "Vigor" → "Sinh Lực", "Lend" → "Ban Tặng" (nhất quán giọng trang trọng hơn "cho mượn") |
| Quickness (Decision/Scheme) *(`POD_quickness_decision_interaction`, `POD_quickness_scheme_interaction`, xóa cooldown)* | Mau Lẹ (Quyết định/Âm mưu) | đặt mới, dịch nghĩa; giữ tag `#Weak (...)#!` không dịch chữ trong ngoặc đơn của tag (chữ "Decision"/"Scheme" bên trong vẫn dịch vì đó là text hiển thị, không phải tên tag) |
| Time out of Time *(`POD_time_out_of_time_interaction`, đẩy nhanh tiến độ âm mưu)* | Thời Gian Ngoài Thời Gian | đặt mới, dịch sát nghĩa đen giữ chất thơ của tên gốc |
| Between the Ticks *(`POD_between_the_ticks_interaction`)* | Giữa Những Nhịp Khắc | đặt mới; "Ticks" (nhịp đồng hồ/khắc thời gian) → "Nhịp Khắc" |
| Ventrue Weakness / Ventrue Bane *(`POD_drink_herd_ventrue_weakness`, `ventrue_bane_warning`, nhược điểm Clan Ventrue với feeding restrictions)* | Nhược Điểm Ventrue | đặt mới; "Bane" và "Weakness" đều dịch chung "Nhược Điểm" trong ngữ cảnh này (cùng chỉ điểm yếu của Clan) |
| Feeding Restrictions *(concept-link `[feeding_restrictions\|E]`, đã có `game_concept_feeding_restrictions` chưa dịch)* | *(không đổi, chỉ dịch câu quanh nó)* | concept-link giữ nguyên vì key nguồn `game_POD_concepts_l_english.yml` chưa dịch; khi file đó dịch xong, quay lại đồng bộ nếu cần |
| Paradox *(`POD_paradox_perk_interaction`, năng lực Temporis dập tắt phe phái)* | Nghịch Lý | đặt mới, dịch nghĩa; danh từ triết học/vật lý phổ biến trong tiếng Việt |
| Boon of Anubis *(`POD_boon_of_anubis_perk_interaction`)* | Ân Huệ của Anubis | đặt mới; "Boon" → "Ân Huệ", "Anubis" giữ nguyên tên thần Ai Cập |
| Mummification Ritual *(`POD_mummification_ritual_perk_interaction`, khiến mục tiêu vào Torpor)* | Nghi Lễ Ướp Xác | đặt mới, dịch nghĩa; "Torpor" dùng lại "$pod_torpor$" = "Miên trạng" đã chốt B2 |
| Negotiate Vote (Caucus/Abstention) *(`POD_thorns_caucus_interaction`, `POD_thorns_abstention_interaction`, `POD_thorns_negotiate_doctrine_vote_interaction`, cơ chế bỏ phiếu Thorns/giáo phái)* | Thương Lượng Lá Phiếu (Hội Nghị Kín/Bỏ Phiếu Trắng) | đặt mới; "Vote" → "Lá Phiếu", "Caucus" (họp kín trước bỏ phiếu) → "Hội Nghị Kín", "Abstention" → "Bỏ Phiếu Trắng" (thuật ngữ chính trị tiếng Việt chuẩn) |
| Blood Hunt *(`blood_hunt_call_interaction`, giữ nguyên tiếng Anh)* | Blood Hunt *(giữ nguyên)* | tái dùng B4i đã chốt "giữ nguyên tạm thời" chờ `game_concept_blood_hunt` dịch |
| Wild Hunt *(`wild_hunt_call_interaction`, tương đương Blood Hunt nhưng của Sabbat)* | Wild Hunt *(giữ nguyên)* | đặt mới theo cùng logic B4i — "Blood Hunt" của Camarilla giữ nguyên tiếng Anh chờ concept gốc dịch, nên "Wild Hunt" của Sabbat (cùng cơ chế casus belli, chỉ khác phe) cũng giữ nguyên để nhất quán, không dịch lệch một bên |
| Camarilla, Sabbat *(tổ chức, xuất hiện trong `actor.Custom('CamarillaStatus')` mô tả và câu văn)* | Camarilla, Sabbat *(giữ nguyên)* | tái dùng B3k/B4r đã chốt, danh từ riêng tổ chức WoD |
| Justicar *(chức sắc tư pháp Camarilla, `actor_secondary_POD_request_anathema_interaction`, `conclave_debate`)* | Justicar *(giữ nguyên)* | tái dùng B4o đã chốt — `game_concept_justicar` nguồn `Glossary()` chưa dịch, giữ nguyên nhất quán |
| Seize Gold/Artifact/Courtier/Prisoner, Claim Title, Depose *(loạt tương tác lạm quyền Justicar)* | Tịch Thu Vàng/Hiện Vật/Cận Thần/Tù Nhân, Chiếm Đoạt Tước Vị, Phế Truất | đặt mới; "Seize" → "Tịch Thu" nhất quán cho vàng/hiện vật/cận thần/tù nhân, "Claim" → "Chiếm Đoạt" (khác "Yêu Sách" dùng cho claim tước vị theo nghĩa pháp lý thông thường — ở đây là hành vi cưỡng đoạt lạm quyền nên chọn "Chiếm Đoạt"), "Depose" → "Phế Truất" |
| Conclave Petition / Improvised Conclave *(`POD_request_anathema_interaction`, `conclave_debate.t`, hội đồng Justicar xét xử Anathema)* | Thỉnh Cầu Conclave / Conclave Bất Thường | đặt mới; "Conclave" giữ nguyên tiếng Anh (danh từ tổ chức WoD, theo B0 tương tự "pack"/"Coterie"), "Petition" → "Thỉnh Cầu", "Improvised" → "Bất Thường" (tính chất họp gấp, không định kỳ) |
| Anathema *(trait/tội danh ma cà rồng bị Camarilla truy nã, `POD_set_anathema_interaction`…)* | Anathema *(giữ nguyên)* | tái dùng B4i đã chốt, danh từ riêng WoD |
| Alastor *(sát thủ săn Anathema thay mặt Justicar, `POD_send_alastor_interaction`)* | Alastor *(giữ nguyên)* | đặt mới theo B0; danh xưng chức năng gốc WoD (Justicar's Alastor), không có bản dịch phổ thông tương đương, cộng đồng quen đọc tiếng Anh |
| Bounty / Trophy *(`POD_camarilla_add_bounty_interaction`, tiền thưởng săn Anathema)* | Tiền Thưởng / Chiến Lợi Phẩm | đặt mới, dịch nghĩa thường |

## B5-vampire-p7. Thuật ngữ `interactions/POD_character_interactions_vampire_l_english.yml` dòng 890-1033, việc #5

Nguồn: đoạn Sabbat (Wild Hunt/Cardinal/excommunication/Black Hand) + humors + Golconda mentoring + Suspire + Nocturne + Heart of Darkness. Câu `POD_sabbat_excommunicate_interaction_desc` gần như sao chép nguyên văn `excommunicate_interaction_desc` vanilla (`base_game_vh/localization/english/interactions_l_english.yml:658`) — đã tái dùng đúng cụm "Rút Phép Thông Công" / "bị [excommunicated|E]" / "chất độc gặm nhấm" từ bản dịch vanilla có sẵn.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Wild Hunt *(`wild_hunt_call_interaction`, chiến tranh Sabbat)* | Cuộc Săn Hoang Dã | đặt mới; dịch nghĩa "cuộc săn man rợ/không luật lệ" |
| Cardinal (Region) *(`POD_cardinal_*`, chức vụ + đơn vị lãnh thổ Sabbat)* | Hồng y (Khu vực Hồng y) | đặt mới; mượn danh xưng Công giáo "Hồng y" đã quen thuộc, ghép "Khu vực" cho đơn vị lãnh thổ |
| Abuse of Power: Depose | Lạm Quyền: Phế Truất | dịch nghĩa thường, "Depose"→"Phế Truất" nhất quán cách dùng vanilla cho phế truất quân chủ |
| excommunicate/excommunicated/excommunication *(Sabbat, `POD_sabbat_excommunicate*`)* | Rút Phép Thông Công / bị rút phép thông công / Rút Phép Thông Công | ✅ tái dùng nguyên bản dịch vanilla `excommunicate_interaction`/`excommunicate_interaction_desc` (`interactions_l_english.yml`), giữ đúng cụm "chất độc gặm nhấm Đức tin", "khai trừ"/"rút phép thông công" xen kẽ như bản gốc vanilla |
| Black Hand Hunting *(`POD_black_hand_hunting_interaction`)* | Truy Lùng | dịch nghĩa; "Black Hand" (tên tổ chức, đã chốt B4d = "Bàn Tay Đen") chỉ xuất hiện trong câu mô tả, không lặp lại trong tên interaction |
| mesmerized / conditioned *(`mesmerized_or_conditioned`)* | thôi miên / điều kiện hóa | dịch nghĩa thường, "conditioned" theo nghĩa tâm lý học "bị điều kiện hóa" (WoD Dominate/Vicissitude) |
| tenet of Continued Life *(`POD_hunger_risk_increase_tenet_continued_life_tt`)* | giáo lý Sự Sống Tiếp Diễn | đặt mới; "Continued Life" dịch nghĩa thường, ghép "giáo lý" nhất quán cách gọi tenet tôn giáo khác trong mod |
| Meditate on Humors *(`POD_piety_for_perk_interaction`)* | Chiêm Nghiệm về Thể Dịch | dùng lại "Thể Dịch" đã chốt cho `humors`/`humorism` ở đoạn trước trong cùng file; `[humorism\|E]`/`[humors\|E]` là concept link nên giữ nguyên chữ trong ngoặc, chỉ dịch câu quanh |
| Golconda Mentoring *(`POD_golconda_mentoring_interaction`)* | Dẫn Dắt Golconda | đặt mới; "Golconda" giữ nguyên theo B4i đã chốt, "Mentoring"→"Dẫn Dắt" dịch nghĩa |
| Sharing Insights *(`POD_golconda_mentoring_interaction_toast`)* | Chia Sẻ Ngộ Tính | dùng lại "Ngộ Tính" đã chốt cho "Insight" (B4g/B4i, thanh kinh nghiệm Golconda Seeker/Dharma) |
| Suspire *(`POD_guide_through_suspire_interaction`, khái niệm giác ngộ riêng — có thể là biến thể/route khác của enlightenment)* | Suspire *(giữ nguyên)* | đặt mới; danh từ riêng WoD/POD chưa rõ nghĩa Việt tương xứng, giữ nguyên theo B0 tương tự Golconda |
| Nocturne *(`POD_nocturne_*`, năng lực rút sinh lực kẻ địch trong trận)* | Nocturne *(giữ nguyên)* | đặt mới; tên riêng năng lực/Discipline đặc biệt, giữ nguyên tiếng Anh nhất quán cách xử lý Potence/Celerity/Fortitude (B0) |
| Drain the Life *(`POD_drain_the_life_interaction`)* | Rút Cạn Sự Sống | dịch nghĩa thường |
| Shadow Twin *(nhắc lại)* | Song Sinh Bóng Tối | ✅ tái dùng nguyên bản dịch đã chốt B4h (dòng 643 TERMINOLOGY.md) |
| Feed the Darkness *(`POD_feed_the_darkness_interaction`)* | Nuôi Dưỡng Bóng Tối | dịch nghĩa thường |
| Sense the Sin *(`POD_sense_the_sin_interaction`)* | Cảm Nhận Tội Lỗi | dịch nghĩa thường |
| Fear the Void Below *(`POD_fear_the_void_below_interaction`)* | Sợ Hãi Vực Thẳm Bên Dưới | dịch nghĩa thường, "Void Below" gợi Địa Ngục |
| Psychomachia *(`POD_psychomachia_interaction`, thuật ngữ Latin/thần học chỉ cuộc chiến tâm hồn)* | Psychomachia *(giữ nguyên)* | đặt mới; thuật ngữ văn học/thần học Latin đặc thù, không có bản dịch phổ thông tương xứng, giữ nguyên theo B0 |
| Condemnation *(`POD_condemnation_interaction`)* | Nguyền Rủa | dịch nghĩa thường theo ngữ cảnh "đặt lời nguyền suy nhược" |
| Hell-Born Investiture *(`POD_hell_born_investiture_interaction`, liên quan quyền năng Namtaru)* | Sắc Phong Từ Địa Ngục | đặt mới; "Investiture"→"Sắc Phong" (nghi thức trao quyền/phẩm hàm, dùng trong bối cảnh tôn giáo/phong kiến), "Hell-Born"→"Từ Địa Ngục" |
| Namtaru *(tên quỷ/thế lực Setite, `POD_hell_born_investiture_interaction_desc`)* | Namtaru *(giữ nguyên)* | tên riêng thần thoại Lưỡng Hà, giữ nguyên theo B0 |
| Bring the Plague *(`POD_bring_the_plague_interaction`)* | Mang Đến Ôn Dịch | dịch nghĩa thường, "Plague"→"Ôn Dịch" nhất quán cách gọi dịch bệnh kiểu trung cổ trong base_game_vh |
| Daimonion *(quyền năng địa ngục gây hao tổn linh hồn, `POD_non_infernalists_pay`)* | Daimonion *(giữ nguyên)* | tên riêng thế lực/khái niệm ma quỷ, giữ nguyên theo B0 |
| infernalist *(bí mật/trait, nhắc tới trong `POD_non_infernalists_pay`)* | infernalist *(giữ nguyên)* | ✅ nhất quán B5-demon-infernalist đã chốt, thuật ngữ Demon: The Fallen |
| Re-Embrace / Propose Re-Embrace *(`POD_the_re_embrace_*`, biến người thành childe bằng ma thuật quỷ dữ)* | Ôm Ấp Lại / Đề Nghị Ôm Ấp Lại | dùng lại "Ôm Ấp" đã chốt cho "the Embrace" (B5-hunter dòng 2339: "Turn Vampire / the Embrace"→"Hóa Ma Cà Rồng / Sự Ôm Ấp"), ghép tiền tố "Lại" cho "Re-" |
| childe *(nhắc tới trong `POD_the_re_embrace_*_desc`)* | childe *(giữ nguyên)* | ✅ nhất quán B4e/B3s đã chốt giữ nguyên tiếng Anh, đi cặp với "Sire" |
| Heart of Darkness *(cụm interaction quyền năng Serpentis liên quan trái tim, `POD_heart_of_darkness_*`)* | Trái Tim Bóng Tối | đặt mới; dịch nghĩa thường, nhất quán với "Bóng Tối" dùng cho darkness xuyên suốt các interaction khác trong đoạn này |
| Steal Heart (Scheme) *(`POD_heart_of_darkness_steal_interaction`, có `#weak (Scheme)#!`)* | Đánh Cắp Trái Tim (Âm mưu) | "Scheme"→"Âm mưu" theo README Consistency Rules (một thuật ngữ = một bản dịch, không luân phiên Kế hoạch/Mưu kế) |
| Serpentis *(tên Discipline clan Setite, `POD_heart_of_darkness_forcetorpor_option.tt`)* | Serpentis *(giữ nguyên)* | ✅ nhất quán B0/B4d — tên riêng Discipline giữ nguyên như Potence/Celerity/Fortitude/Auspex |
| torpor *(nhắc lại, `$pod_torpor$`/`torpor` chữ thường trong câu văn)* | miên trạng | ✅ tái dùng "Miên trạng" đã chốt B2 (`pod_torpor`), áp dụng cho cả dạng chữ thường đứng một mình trong câu |

## B5-vampire-p8. Thuật ngữ `interactions/POD_character_interactions_vampire_l_english.yml` — đoạn cuối file (dòng 1034-1187/1187), việc #5

| Thuật ngữ gốc | Bản dịch | Ghi chú |
|---|---|---|
| Fortitude / Vicissitude *(tên Discipline)* | Fortitude / Vicissitude *(giữ nguyên)* | tiếp tục B0, khớp `traits_POD_l_english.yml:430` (`trait_vicissitude`) và tiền lệ giữ nguyên tên riêng Discipline ở mục ngay trên |
| Justicar | Justicar *(giữ nguyên)* | tái dùng đúng tiền lệ đã chốt (dòng ~1795 file này): key nguồn `game_concept_justicar_desc` mà tham số 2 của `Glossary()` trỏ tới vẫn chưa dịch, giữ nguyên nhất quán |
| rouse (hunger) check | lượt kiểm tra rouse (đói khát) | đặt mới; "rouse check" là thuật ngữ cơ chế V5 (kiểm tra máu để kích hoạt dị năng) chưa có tiền lệ — giữ "rouse" nguyên tiếng Anh theo lối B0 (thuật ngữ cơ chế WoD/V5 chuyên biệt), dịch "check"→"lượt kiểm tra" |
| Prowess from Pain | Sức Mạnh Từ Cơn Đau | đặt mới, dịch nghĩa; perk Fortitude tăng sức mạnh khi bị thương |
| Resilient Mind | Tâm Trí Kiên Cường | đặt mới, dịch nghĩa; perk Fortitude chống loạn thần |
| soak (damage) | hấp thụ (sát thương) | đặt mới; dịch nghĩa cơ chế "soak" của Fortitude (né/giảm sát thương) |
| Blood Vessel *(item lưu trữ Máu, `POD_store_blood_interaction` nhóm)* | Bình Chứa Máu | đặt mới, dịch nghĩa; "Blood"→"Máu" viết hoa nhất quán vì là tài nguyên đếm được trong game (giống cách vanilla viết hoa tên tài nguyên) |
| Alchemical Product(s) *(Thin-Blood Alchemy)* | Sản Phẩm Giả Kim | tái dùng đúng "Alchemical"→"Giả Kim" đã chốt tại B5-numina |
| Mask of Empathy | Mặt Nạ Đồng Cảm | đặt mới, dịch nghĩa; interaction Presence phá vỡ quan hệ đối phương |
| Perfect World | Thế Giới Hoàn Hảo | đặt mới, dịch nghĩa |
| Ambassadorial Patron | Người Bảo Trợ Ngoại Giao | đặt mới; tái dùng "Người Bảo Trợ" đã chốt (B5-fae `Call Patron`), thêm "Ngoại Giao" vì gắn với vai trò `ashen_ambassador` |
| Book Eating *(Malkavian)* | Ăn Sách | đặt mới, dịch sát nghĩa; interaction Malkavian hấp thụ tri thức từ hiện vật sách |
| Force Frenzy | Ép Buộc Cuồng Nộ | đặt mới; "Frenzy" dịch "Cuồng Nộ" theo lối dịch nghĩa trạng thái mất kiểm soát của ma cà rồng (nhất quán tinh thần B0 — không có tiền lệ khác ghi nhận, để "Cuồng Nộ" thay vì giữ nguyên vì đây là trạng thái phổ thông không phải danh từ riêng) |
| Fleshcraft / fleshcraft / fleshcrafting *(tên Discipline-power Vicissitude, `[fleshcraft\|E]` `[fleshcrafting\|E]`)* | Fleshcraft *(giữ nguyên)* | khớp `game_concept_fleshcraft`/`game_concept_fleshcrafting` trong `game_POD_concepts_l_english.yml:815-817` — các key nguồn này **cũng chưa dịch** (vẫn "Fleshcraft"/"Fleshcrafting" tiếng Anh), nên giữ nguyên nhất quán theo đúng tiền lệ Justicar; nếu sau này `game_POD_concepts` dịch, phải quay lại đổi đồng loạt |
| Liquefy the Mortal Coil | Hóa Lỏng Xác Thân Phàm Tục | đặt mới, dịch nghĩa; "mortal coil" là thành ngữ cổ chỉ thân xác phàm nhân (Shakespeare), dịch thoát ý |
| Study Anatomy | Nghiên Cứu Giải Phẫu | đặt mới, dịch nghĩa |
| Transmogrify *(Tzimisce, biến người thành đồ vật)* | Biến Hóa | đặt mới, dịch nghĩa ngắn gọn cho tên interaction; mô tả (`_desc`) vẫn là placeholder gốc "TODO Tzimisce" chưa có nội dung — giữ nguyên |
| Zmei *(3 dòng bị comment `#POD_call_zmei_to_war_interaction*`)* | *(không dịch)* | giữ nguyên tiếng Anh theo mục 5 TRANSLATION_RULES.md — dòng comment `#` đầu dòng |

Xác nhận: file gốc `POD_character_interactions_vampire_l_english.yml` có đúng 1187 dòng, dòng cuối cùng (1187, `POD_transmogrify_interaction_odious_chalice: ""`) **không có `\r\n` theo sau** (không có newline cuối file). Bản dịch đoạn 1034-1187 xuất ra 154 dòng khớp, đã tự dựng CRLF thủ công (không dùng LF của Write tool) và giữ nguyên việc không có newline thừa ở cuối để khớp byte-for-byte với quy ước gốc.

## B5-vampire-p2. Thuật ngữ đoạn 156-321 `interactions/POD_character_interactions_vampire_l_english.yml` — Bind Famulus / Blood Bond / Cover Masquerade / Drink Herd / Resonance / Herdify / Awaken Torpor, việc #5

Đoạn dịch xoay quanh 5 cụm tương tác: `POD_bind_famulus` (trói buộc thú làm famulus), `POD_bond_prisoner_interaction` (Ràng Buộc Máu tù nhân), `POD_cover_masquerade_interaction` (che đậy Masquerade), `POD_drink_herd`/`POD_resonance_*`/`POD_herdify_*` (quản lý Herd/vessel/Resonance), và chuỗi sự kiện dài `POD_awaketorpor.*` (tìm và đánh thức ma cà rồng đang Miên trạng).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Famulus *(`POD_bind_famulus`, thú vật bị dùng máu trói buộc phục vụ ma cà rồng, khác Ghoul/Thrall người)* | Thú Nô Bộc | đặt mới; tái dùng gốc "Nô Bộc" đã chốt cho Thrall/Ghoul (B5j, dòng 2035) vì famulus về bản chất là "ghoul động vật", thêm "Thú" để phân biệt rõ đối tượng là con vật, không phải người; đối chiếu bản Trung của cùng file dịch nghĩa tương tự ("动物伙伴" = bạn đồng hành động vật) nhưng bản Việt giữ sát tinh thần "bị trói buộc bằng máu" hơn thay vì "bạn đồng hành" |
| blood bind / bloodbind *(động từ, `POD_bind_famulus_interaction_desc` và 3 dòng `.tt`)* | dùng máu trói buộc | dịch nghĩa động từ, nhất quán với danh từ "Thú Nô Bộc" ở trên; không dùng "Ràng Buộc Máu" (dành riêng cho `Blood Bond` ở mục dưới) để tránh lẫn hai cơ chế khác nhau trong cùng file |
| Blood Bond *(`POD_bond_prisoner_interaction` = "Blood Bond Prisoner", cơ chế thao túng tù nhân bằng máu)* | Ràng Buộc Máu | tái dùng đúng bản dịch đã chốt tại B4 (dòng 1610, "Blood Bond"→"Ràng Buộc Máu") |
| hook *(danh từ thường, `POD_bond_prisoner_interaction_growingbloodbond`, khác `game_concept_hook`)* | Kiềm chế | tái dùng "Hook"→"Kiềm chế" đã chốt nhiều lần (B5k dòng 2057/2243) áp dụng cho câu văn thường nhắc tới hook, không riêng concept-link |
| Cover up Masquerade / Masquerade *(danh từ thường trong câu văn, không phải `[the_masquerade\|E]` concept-link)* | Che Đậy Màn Che / Màn Che | tái dùng "Masquerade"→"Màn Che" đã đặt tại B4 (dòng 1332/1791); áp dụng cho toàn bộ cụm `POD_cover_masquerade_*` trong đoạn này vì đều là câu văn thường, không đụng khái niệm `game_concept_the_masquerade` (file gốc chưa dịch, vẫn giữ "The Masquerade" khi xuất hiện dạng concept-link) |
| vessel *(danh từ chỉ nạn nhân/mortal bị hút máu, khác "energy vessel"=bình năng lượng ở B5c)* | vật chứa | đặt mới cho ngữ cảnh này; "vessel" ở đây chỉ một con người/kindred bị biến thành nguồn cấp máu — dùng "vật chứa" (nghĩa đen, giữ sắc thái phi nhân hóa nạn nhân mà nguyên tác VtM cố ý truyền tải), khác nghĩa "bình" đã dùng cho vật phẩm năng lượng ở B5c |
| Herdify *(`POD_herdify_mortal_interaction`/`_vampire_interaction`, tên tương tác đưa mục tiêu vào Herd)* | Đưa vào Herd | đặt mới; giữ nguyên "Herd" tiếng Anh vì `game_concept_POD_herd` (`game_POD_concepts_l_english.yml:199`) **vẫn chưa dịch** (còn "Herd") — áp dụng đúng tiền lệ "Justicar/Fleshcraft" (giữ nguyên khi concept nguồn chưa dịch), kể cả trong câu văn thường như "herd limit", "herd member" |
| kindred *(danh từ thường, `POD_herdify_vampire_interaction_desc`, chỉ ma cà rồng nói chung)* | Huyết Tộc | tái dùng "Kindred"→"Huyết Tộc" đã khóa cứng B3k, áp dụng cho chữ thường "kindred" trong câu văn (không chỉ dạng viết hoa) |
| torpid vampire *(cụm tính từ lặp lại nhiều lần suốt chuỗi `POD_awaketorpor.*`)* | ma cà rồng đang Miên trạng | tái dùng nguyên văn tiền lệ đã chốt tại B5i (dòng 2020) |
| in thrall to *(thành ngữ, `POD_awaketorpor.1.desc`, KHÔNG phải danh từ Thrall/Ghoul)* | bị nô dịch bởi | dịch nghĩa thành ngữ tiếng Anh "in thrall to" (bị khống chế/chi phối bởi), không liên quan tới bản dịch danh từ "Thrall"→"Nô Bộc"/"Nô Lệ" đã chốt ở nơi khác — tránh nhầm lẫn vì đây là idiom tính từ, không phải nhắc tới nhân vật ghoul |

Không có `Glossary()`/`UmbraGlossaryLocalized()`/`Select_CString()` nào khác ngoài 1 lần `Glossary('Disciplines','game_concept_discipline_desc')` tại dòng 172 — dịch tham số 1 thành "Dị năng" (đã chốt B2), giữ nguyên tham số 2.

## B5-vampire-p5. Thuật ngữ `interactions/POD_character_interactions_vampire_l_english.yml` dòng 593-726, việc #5

Nội dung: các perk-interaction Necromancy (Cleansed in Blood, Purification, Thin Blood, Erosion, Aura Absorption, Steal the Mind, Absorb the Mind, Basilisk's Touch, Stone Travel, Curse of the Maelstrom, Wails and Whispers, Intimations of Mortality, Gift of Melancholia, Witch's Fruit, Raise the Green One, Song of the Dead), Degulo/Exchange Attribute/Exchange Discipline (Samedi?), Taming the Beast, Predator's Mastery, và bắt đầu Discipline Training. Không có `Glossary()`/`UmbraGlossaryLocalized()` nào trong đoạn này (bracket count không đổi 53→53, ref 2→2, tất cả đều `$pod_discipline$`).

| Thuật ngữ gốc | Bản dịch | Ghi chú |
|---|---|---|
| Cleansed in Blood | Tẩy Sạch trong Máu | đặt mới, dịch nghĩa; perk gột rửa hiệu ứng biến hình xấu |
| shapeshift *(danh từ thường, `POD_cleansed_in_blood_perk_interaction_desc`)* | dạng Biến Hình | tái dùng "Shapeshift"→"Biến Hình" đã chốt (dòng 2089 file này, `POD_arcana_shapeshift_interaction`) |
| Purification | Thanh Tẩy | đặt mới, dịch nghĩa |
| Erosion | Xói Mòn | đặt mới, dịch nghĩa |
| Aura Absorption | Hấp Thụ Hào Quang | đặt mới, dịch nghĩa; "Aura" dịch "Hào Quang" theo nghĩa hào quang/khí chất huyền bí |
| Resonance *(nhắc lại, `POD_aura_absorption_perk_interaction_desc`)* | Cộng hưởng | ✅ đã chốt B5 (dòng 1286 file này) |
| Steal the Mind / Absorb the Mind | Đánh Cắp Tâm Trí / Nuốt Chửng Tâm Trí | đặt mới; hai perk khác nhau nên dùng hai cách dịch khác nhau dù cùng gốc "the Mind" — "Steal"→"Đánh Cắp" (lấy tạm thời), "Absorb"→"Nuốt Chửng" (hấp thụ vĩnh viễn, ăn luôn cả tâm trí) để phân biệt sắc thái |
| Basilisk's Touch | Cái Chạm của Basilisk | đặt mới; "Basilisk" giữ nguyên tên quái vật thần thoại, không có tiền lệ dịch nghĩa trong repo |
| Stone Travel | Xuyên Đá | đặt mới, dịch thoát ý (đào hầm xuyên đất đá di chuyển) thay vì dịch sát "Du Hành Đá" để ngắn gọn hơn cho UI |
| Necromancy $pod_discipline$ *(nhắc lại)* | Dị năng $pod_discipline$ Thuật Gọi Hồn | ✅ "Necromancy"="Thuật Gọi Hồn" đã chốt (dòng 556 file này); giữ nguyên thứ tự cụm để câu tự nhiên tiếng Việt ("Dị năng ABC Thuật Gọi Hồn của ta, tên X, làm giảm...") |
| Ashes to Ashes / Tend the Body Garden *(tên 2 power Necromancy cụ thể)* | Tro Về Với Tro / Chăm Sóc Khu Vườn Xác Thân | đặt mới, dịch nghĩa; chưa có tiền lệ dịch 2 tên power này trong repo |
| masquerade_exposure\|E *(nhắc lại)* | nguy cơ [masquerade_exposure\|E] | concept-link giữ nguyên bracket, không đổi ID; dùng "nguy cơ ... của ta" bám câu gốc "my risk of" |
| Find Wraith | Tìm Oan Hồn | đặt mới; "Wraith"="Oan Hồn" đã chốt B4/B4u |
| Curse of the Maelstrom | Lời Nguyền Xoáy Lốc | đặt mới, dịch nghĩa; "Maelstrom" (xoáy nước khổng lồ) dịch "Xoáy Lốc" |
| Spectre(s) | Spectre | *(giữ nguyên)* — danh từ riêng WoD (loại thực thể Wraith cấp thấp/hung dữ), chưa có tiền lệ dịch nghĩa trong repo, theo B0 |
| Wails and Whispers | Ai Oán và Thì Thầm | đặt mới, dịch nghĩa |
| Intimations of Mortality | Điềm Báo của Sự Hữu Hạn | đặt mới; "Mortality" dịch "Sự Hữu Hạn" (tính hữu hạn/hữu tử của kiếp người) thay vì "Kiếp Phàm Nhân" để tránh trùng nghĩa với dòng mô tả liền sau ("aspects of mortality"→"kiếp phàm nhân") |
| Blood Surge *(nhắc lại, `POD_intimations_of_mortality_interaction.tt`)* | Bộc Phát Máu | tái dùng thuật ngữ đã dùng nơi khác trong file (dòng B5-vampire-p1, cơ chế đốt máu tăng sức mạnh tạm thời) |
| Gift of Melancholia | Món Quà Sầu Muộn | đặt mới, dịch nghĩa |
| Witch's Fruit | Trái Cây của Phù Thủy | đặt mới, dịch nghĩa |
| "How do you like them apples" *(thành ngữ Mỹ, actor_toast)* | "Ngươi thấy những trái táo đó thế nào" | dịch thoát ý giữ hình ảnh "táo" ăn khớp với "Witch's Fruit", bỏ sắc thái khiêu khích thành ngữ gốc (không có tương đương tiếng Việt) |
| Raise the Green One | Triệu Hồi Kẻ Xanh | đặt mới; "Raise" (triệu hồi/hồi sinh xác chết, Necromancy) dịch "Triệu Hồi" nhất quán với "raise/animate the dead" trong lore Wraith/Necromancy; "the Green One" dịch trực tiếp "Kẻ Xanh" (biệt danh xác chết được thực vật bao phủ) |
| Song of the Dead | Khúc Ca của Kẻ Chết | đặt mới, dịch nghĩa |
| Soul Feasting | Yến Tiệc Linh Hồn | đặt mới, dịch nghĩa |
| Degulo *(tên riêng interaction, không dịch)* | Degulo | *(giữ nguyên)* — không phải từ tiếng Anh thường, có vẻ là danh từ WoD/nghi lễ riêng, không có nghĩa để dịch |
| Exchange Attribute / Exchange Discipline | Trao Đổi Chỉ Số / Trao Đổi Dị Năng | đặt mới; "Attribute"→"Chỉ Số" (thuộc tính nhân vật cơ bản, khác "Skill"), "Discipline"="Dị Năng" đã chốt B2 |
| boiled skull *(nhắc lại 2 lần, Exchange Attribute/Discipline)* | hộp sọ đã luộc | dịch sát nghĩa, gắn với "Degulo" (nghi lễ chặt đầu + luộc sọ) |
| Taming the Beast | Thuần Hóa Dã Thú | đặt mới; "Beast"="Dã Thú" nhất quán B3/B5-vampire-p8 |
| Prowess / Health / Martial skill *(3 lựa chọn Taming the Beast)* | Sức Mạnh / Sức Khỏe / Kỹ năng Quân sự | dịch nghĩa phổ thông theo thuộc tính CK3 vanilla (`prowess`→"Sức Mạnh", `martial`→"Quân sự" theo base_game_vh) |
| Predator's Mastery | Sự Thống Trị của Kẻ Săn Mồi | đặt mới, dịch nghĩa |
| strong hook *(cơ chế game, nhắc lại 3 lần)* | mối liên hệ ràng buộc mạnh mẽ | dịch theo "hook" = cơ chế Hook của CK3 vanilla (tài liệu base dùng "Mối quan hệ ràng buộc"/"Hook" tùy ngữ cảnh); dùng cụm dịch nghĩa đầy đủ vì không có key `hook` ngắn gọn nào xuất hiện riêng trong đoạn này để tra chính xác thuật ngữ base — cần đối chiếu lại khi gặp `game_concept_hook` |
| Incarnate Darkness *(tên 1 dạng shapeshift vampire)* | Hiện Thân Bóng Tối | đặt mới, dịch nghĩa |

Ghi chú phạm vi: đã đọc thêm dòng 727-729 (`POD_train_disciplines_interaction*`) chỉ để nắm ngữ cảnh câu cuối đoạn 726, nhưng KHÔNG dịch/xuất ra file `part5_593-726.yml` — nằm ngoài phạm vi 593-726 được giao, dành cho agent phần tiếp theo.

## B5-wraith-p5. Thuật ngữ `interactions/POD_character_interactions_wraith_l_english.yml` (dòng 496-615)

Nguồn: các tương tác Fetter (Manipulate/Sprout/Resolve/Allocate/Downgrade/Destroy [Fetter|E]), tương tác Transfuse/Reconfigure (chuyển Pathos/Corpus), Contaminate, Fetter Rape, Resist against Shadow, và các tương tác Arcanoi Argos/Castigate/Embody/Keening/Lifeweb/Moliate/Pandemonium (Haunt). Không có `Glossary()`/`UmbraGlossaryLocalized()` trong đoạn này.

| Thuật ngữ gốc | Bản dịch | Ghi chú |
|---|---|---|
| Pathos | Pathos *(giữ nguyên)* | danh từ lõi hệ thống Wraith, không có tiền lệ base tương ứng, theo B0/B4h — nhất quán với "Pathos" đã dùng giữ nguyên ở B5-wraith-p6 |
| Manipulate [Fetter\|E] | Thao Túng [Fetter\|E] | đặt mới, dịch nghĩa |
| Sprout [Fetter\|E] | Gieo Mầm [Fetter\|E] | đặt mới, dịch nghĩa ("sprout" = nảy mầm/gieo mầm) |
| Resolve [Fetter\|E] | Hóa Giải [Fetter\|E] | đặt mới, dịch nghĩa (quá trình buông bỏ Fetter không hối tiếc) |
| Fetter Rape *(tên tương tác biến mục tiêu thành Risen)* | Cưỡng Đoạt Fetter | đặt mới, dịch nghĩa phần động từ, giữ "Fetter" nguyên theo B4h |
| Transfuse / Reconfigure *(tương tác chuyển Pathos/Corpus)* | Truyền Dẫn / Tái Cấu Trúc | đặt mới, dịch nghĩa |
| Contaminate | Vấy Nhiễm | đặt mới, dịch nghĩa |
| Resist against Shadow | Kháng Cự Bóng | đặt mới; "Shadow" = "Bóng" tái dùng tiền lệ B4h (khía cạnh đen tối của Wraith) |
| Angst *(nhắc trong tên/hiệu ứng tương tác Castigate)* | Angst *(giữ nguyên)* | chưa có tiền lệ dịch nghĩa trong repo; thuật ngữ tâm lý-Wraith (Ác cảm/nỗi thống khổ tích tụ), tạm giữ nguyên tiếng Anh theo B0 vì không tìm thấy khái niệm base tương đương; cần rà soát lại nếu gặp key `_desc` giải thích rõ nghĩa |
| Trimming the Black Rose *(tên tương tác Castigate)* | Tỉa Bớt Đóa Hồng Đen | đặt mới, dịch nghĩa trực tiếp |
| Whispers *(tên power Embody)* | Những Lời Thì Thầm | đặt mới, dịch nghĩa, nhất quán với cách dịch "Whispers" ở nơi khác trong mod (Black Whispers, Wails and Whispers — B4x/B5) |
| Mood music / Satire and Requiem / Siren Song *(tên power Keening)* | Nhạc Điệu Tâm Trạng / Châm Biếm và Khúc Cầu Hồn / Khúc Hát Nàng Tiên Cá | đặt mới, dịch nghĩa; "Requiem" = "Khúc Cầu Hồn" |
| Walk the Web *(tên power Lifeweb)* | Dạo Bước Trên Mạng Lưới | đặt mới, dịch nghĩa |
| Pathos heal *(tên power Moliate)* | Chữa Lành bằng Pathos | đặt mới, dịch nghĩa, giữ "Pathos" nguyên |
| Haunt *(tên power Pandemonium, tương tác quấy nhiễu mục tiêu)* | Ám Ảnh | đặt mới, dịch nghĩa |

## B5-wraith-p6. Thuật ngữ đoạn cuối `interactions/POD_character_interactions_wraith_l_english.yml` (dòng 616-738)

Nguồn: các tương tác Arcanoi (Pandemonium/Phantasm/Puppetry/Usury/Intimation/Mnemosynis/Fascinate) và tương tác "Command Bound Wraiths". Không có `UmbraGlossaryLocalized()` trong đoạn này; chỉ có `UmbraGlossary('pod_realm_labyrinth')` (1 tham số, không dịch) và 4 lần `Glossary('Skinlands','game_concept_skinlands_desc')` (giữ nguyên tham số 1 theo tiền lệ B4h — "Skinlands" là danh từ lõi Wraith không dịch).

| Thuật ngữ gốc | Bản dịch | Ghi chú |
|---|---|---|
| Escher's Stair *(tên power Pandemonium)* | Cầu Thang Escher | đặt mới; giữ tên riêng "Escher" (họa sĩ M.C. Escher, ám chỉ cầu thang nghịch lý), dịch phần còn lại |
| Morphean Embrace *(tên power Phantasm)* | Vòng Tay Morphean | đặt mới; giữ "Morphean" (gốc thần Morpheus - thần giấc mộng), dịch "Embrace"="Vòng Tay" |
| Drain Pathos / Stop Dreaming *(tên power Phantasm)* | Rút Cạn Pathos / Chấm Dứt Giấc Mơ | đặt mới, dịch nghĩa; "Pathos" giữ nguyên theo tiền lệ B0/toàn mod |
| Possess / End Possession *(Puppetry)* | Chiếm Hữu / Kết Thúc Chiếm Hữu | đặt mới, dịch nghĩa; nhất quán với "possess/possessed" đã dùng nơi khác trong mod (Bane/Fomori numina) |
| Control Puppet / Cancel Control Puppet / Control Creature *(Puppetry)* | Điều Khiển Con Rối / Hủy Điều Khiển Con Rối / Điều Khiển Sinh Vật | đặt mới, dịch nghĩa |
| Create Conduit / Conduit *(Puppetry/Usury, danh từ vật thể chứa năng lượng)* | Tạo Ống Dẫn / Ống Dẫn | đặt mới; "Conduit" dịch "Ống Dẫn" (vật trung gian truyền Pathos/Corpus) |
| the Risen *(nhắc đến nhóm Wraith gọi hồn động vật, `POD_puppetry_create_conduit_interaction_desc`)* | kẻ Risen | *(giữ nguyên tên riêng "Risen")* — chưa có tiền lệ dịch nghĩa, danh từ riêng nhóm/phe WoD |
| Exchange Rate / Pathos Vessel *(Usury)* | Tỷ Giá Trao Đổi / Bình Chứa Pathos | đặt mới, dịch nghĩa; "Pathos"/"Corpus" giữ nguyên theo B0 |
| Store Pathos / Extract Stored Pathos *(Usury)* | Lưu Trữ Pathos / Rút Pathos Đã Lưu Trữ | đặt mới, dịch nghĩa |
| The Gleaming *(tên power Intimation)* | Ánh Rạng Rỡ | đặt mới, dịch nghĩa |
| Ignite *(tên power Intimation)* | Khơi Mào | đặt mới, dịch nghĩa |
| Erasure / Relation Manipulation / Gray Man *(tên power Mnemosynis)* | Xóa Bỏ / Thao Túng Quan Hệ / Người Xám | đặt mới, dịch nghĩa |
| Driving Urge *(tên power Fascinate)* | Thôi Thúc Nội Tâm | đặt mới, dịch nghĩa |
| Command Bound Wraiths *(tên tương tác chính)* | Ra Lệnh Cho Oan Hồn Bị Ràng Buộc | đặt mới; "Wraith"="Oan Hồn" đã chốt B4/B4u |
| Bound Wraith *(secondary recipient label)* | Oan Hồn Bị Ràng Buộc | đặt mới, nhất quán với dòng trên |

Ghi chú: đoạn này chỉ toàn tên/mô tả tương tác — không phát sinh mâu thuẫn thuật ngữ với các đoạn trước. Ba dòng mô tả bị lặp lại y hệt trong bản gốc tiếng Anh (`POD_phantasm_morphean_embrace_interaction_desc: ""`, và 3 key `_desc` khác nhau đều mang cùng chuỗi `"Intimation: The Gleaming"` dù thuộc Mnemosynis/Fascinate) — đây là lỗi có sẵn trong bản gốc (đặt nhầm text), đã dịch y hệt bản gốc lặp lại tương ứng, không tự sửa nội dung.

## B5-wraith-p2. Thuật ngữ đoạn `interactions/POD_character_interactions_wraith_l_english.yml` dòng 133-246, việc #5

Nguồn: Pathos Heal, Allocate/Resolve/Manipulate Fetter, Ask for Mentoring (Arcanoi), Walk the Web, Remove Caul, Inspire, Drain Energy (Pathos), Stop Dreaming/Awaking, Convert/Control Barghest (Bloodhound), Create Rumor, Enthrall, Upgrade Relation, Create/Gift Foul Food — cùng các biến thể "Command Wraith" (sai khiến oan hồn bị ràng buộc thay mặt). Không có `Glossary()`/`UmbraGlossaryLocalized()` trong đoạn này. Có 3 lần `Select_CString( actor.IsLocalPlayer, 'you', 'the bound wraith' )` — cả hai chuỗi là chữ hiển thị thường (không phải ID) nên đã dịch thành `'ngươi'` / `'oan hồn bị ràng buộc'`.

| Thuật ngữ gốc | Bản dịch | Ghi chú |
|---|---|---|
| Pathos Heal | Chữa Lành bằng Pathos | đặt mới; "Pathos" giữ nguyên theo tiền lệ B4h/B0 (danh từ lõi Wraith) |
| Command Wraith *(nhãn `#weak (...)` cho biến thể sai khiến oan hồn bị ràng buộc)* | Sai khiến Oan hồn | đặt mới, dịch nghĩa ngắn gọn cho vừa UI |
| Allocate [Fetters\|E] | Phân bổ [Fetters\|E] | đặt mới; "Fetter(s)" giữ nguyên theo B4h (concept-link, không dịch chữ trong `[...\|E]`) |
| Resolving/Resolve [Fetters\|E] | Giải Quyết [Fetters\|E] | đặt mới, dịch nghĩa "Resolve/Resolution" nhất quán với `trait_track_fetter_resolved` = "Fetter Đã Giải Quyết" đã có ở `traits_POD_l_english.yml` |
| Ask for Mentoring *(oan hồn xin học Arcanoi từ bạn/người tình/tri kỷ)* | Xin Được Chỉ Dạy | đặt mới; dùng "Chỉ Dạy" thay vì "Dẫn Dắt" (đã dùng cho "Golconda Mentoring" ở B5-vampire) vì ngữ cảnh khác — đây là truyền thụ Arcanoi cụ thể, không phải dẫn dắt hành trình Golconda |
| Walk the Web *(di chuyển nhanh đến Fetter)* | Bước Đi Trên Mạng Lưới | đặt mới, dịch nghĩa |
| Remove Caul / Reaper | Loại Bỏ Caul / Reaper | "Caul" giữ nguyên theo tiền lệ `trait_caul` (traits_POD); "Reaper" giữ nguyên — chưa có tiền lệ dịch nghĩa, danh từ riêng WoD (chuyên gia gỡ Caul cho Enfant) |
| Drain Energy *(rút Pathos từ mục tiêu)* | Rút Cạn Năng Lượng | đặt mới, dịch nghĩa |
| Stop Dreaming / Stop Awaking | Ngừng Mơ Màng / Ngừng Tỉnh Giấc | đặt mới, dịch nghĩa cặp đối lập |
| Create/Control Bloodhound *(`trait_barghest`/`GetTrait('barghest')`)* | Tạo/Điều Khiển Chó Săn Máu | đặt mới; "Barghest" (ID trait giữ nguyên không dịch) hiển thị là "Bloodhound" trong tên tương tác — dịch nghĩa "Chó Săn Máu" cho chữ hiển thị "Bloodhound", còn "Barghest" (tên riêng WoD, đã liệt ở B4h) tiếp tục giữ nguyên trong ngữ cảnh khác |
| Create Rumor | Tạo Tin Đồn | đặt mới, dịch nghĩa |
| Enthrall | Mê Hoặc | đặt mới, dịch nghĩa |
| Upgrade Relation / Relation Target | Nâng Cấp Mối Quan Hệ / Mục Tiêu Quan Hệ | đặt mới, dịch nghĩa |
| Create/Gift Foul Food | Tạo/Tặng Thức Ăn Ôi Thiu | đặt mới, dịch nghĩa |

Ghi chú: `Select_CString( actor.IsLocalPlayer, 'you', 'the bound wraith' )` xuất hiện 3 lần (dòng `POD_mentoring_disciplines.0002.desc`, `POD_learn_arcanos_custom`) — dịch `'you'`→`'ngươi'`, `'the bound wraith'`→`'oan hồn bị ràng buộc'` (chữ thường, vì nằm giữa câu văn xuôi, khác nhãn UI "Oan Hồn Bị Ràng Buộc" viết hoa ở B5-wraith-p6). Dòng `POD_resolve_fetter_interaction_desc` là comment (bắt đầu bằng `#`) — giữ nguyên tiếng Anh theo quy tắc §5 TRANSLATION_RULES.md. Dòng chỉ chứa khoảng trắng (index gốc 10/27/34/46/51/54/57/65/72/77/83/92/94/103/114) giữ nguyên y hệt byte gốc.

## B5-wraith-p4. Thuật ngữ đoạn `interactions/POD_character_interactions_wraith_l_english.yml` dòng 370-495, việc #5

Nguồn: Shadow Offer (6 chỉ số dùng "của Bóng"), Forbidden Arcanoi (Render Relic/Automaton/Gleaming/Ignite/Erasure/Set Relation/Erase from Memory — mỗi tương tác có biến thể "Command Wraith"), Jade Arcanoi (Shackle/Snare/Net/Reap the Hungry Ghost, True/White Jade, Rework/Empower Relic, Gold↔Pathos, Alter Demeanor, Convert Arcanoi Perk, Control/Switch/Stop Control Puppet, Choose a Necromancer, Create Manifestation, Fascinate + Charge of Duty/Driving Urge/Target Lock). Không có `Glossary()`/`UmbraGlossaryLocalized()`/`Select_CString()` trong đoạn này.

| Thuật ngữ gốc | Bản dịch | Ghi chú |
|---|---|---|
| Shadow Offer *(và 6 modifier `shadow_offer_*`)* | Lời Đề Nghị của Bóng / [Ngoại giao/Quân sự/Quản trị/Mưu mô/Học thức/Vũ dũng] của Bóng | đặt mới; "Shadow" = "Bóng" tái dùng tiền lệ B4h (`trait_shadow`) |
| Forbidden Arcanoi *(comment heading)* | *(comment, giữ nguyên `#` đầu dòng)* | không dịch — dòng comment `# Forbidden Arcanoi #` giữ style comment nhưng đã dịch phần chữ trong các comment khác của mod theo tiền lệ; ở đây giữ style nhất quán các heading khối trong file này |
| Render Relic | Hủy Diệt Di Vật | đặt mới; "Relic" dịch "Di Vật" (khác "Relic" trong ngữ cảnh khác đôi khi dịch "Thánh Tích" tùy tôn giáo — ở đây là hiện vật Wraith phá hủy để lấy Pathos, dùng "Di Vật" trung tính) |
| Automaton *(tên interaction, khác trait `automaton` giữ nguyên theo B4h)* | Vận Hành Tự Động | đặt mới; đây là tên tương tác nhận buff từ hiện vật trang bị, dịch nghĩa hành động — không nhầm với danh từ riêng "Automaton" (Golem/Effigy nhóm B4h) vẫn giữ nguyên khi là tên loại thây máy |
| Artifact of Desire *(Gleaming)* | Hiện Vật Khao Khát | đặt mới, dịch nghĩa |
| Land of Obsession *(Ignite)* | Vùng Đất Nỗi Ám Ảnh | đặt mới, dịch nghĩa |
| Erasure | Xóa Bỏ | đặt mới, dịch nghĩa (xóa một ký ức ngẫu nhiên) |
| Create Relation | Tạo Quan Hệ | đặt mới, dịch nghĩa |
| Erase from Memory *(khỏi "ký ức tập thể")* | Xóa Khỏi Ký Ức | đặt mới, dịch nghĩa |
| Command Wraith *(nhãn `#weak (...)`)* | Sai khiến Oan hồn | tái dùng nguyên trạng B5-wraith-p2 |
| Shackle / Snare / Net *(Jade Arcanoi, Puppetry)* | Xiềng Xích / Bẫy Lưới / Lưới Chụp | đặt mới, dịch nghĩa theo hình ảnh trói buộc bằng dây/lưới |
| Reap the Hungry Ghost | Gặt Hái Quỷ Đói | đặt mới; "Hungry Ghost" dịch "Quỷ Đói" theo khái niệm ngạ quỷ phổ biến trong văn hóa Á Đông (phù hợp ngữ cảnh Yellow Springs/Jade Wraith Đông Á) |
| True Jade | Ngọc Bích Chân Chính | tái dùng nguyên trạng tiền lệ `gui/POD_umbra_window_l_english.yml:543` (đã ghi ở B5-fae) |
| White Jade | Bạch Ngọc | đặt mới, dịch nghĩa song song với "True Jade" |
| Rework Relic | Cải Tạo Di Vật | đặt mới, dịch nghĩa |
| Imbue Relic *(key `POD_empower_jade_interaction`)* | Truyền Sức Di Vật | đặt mới, dịch nghĩa (tăng cường hiện vật bằng Pathos, khác "Rework" dùng Jade) |
| Withdraw White Jade | Rút Bạch Ngọc | đặt mới, dịch nghĩa |
| Alter Demeanor | Đổi Dạng Vẻ | đặt mới; "Demeanor" dịch "Dạng Vẻ" (tính cách bề ngoài thể hiện, khác "Nature"/"tính cách" nội tại) |
| Hun *(một trong hai "hồn phách" Kuei-Jin)* | Hun *(giữ nguyên)* | tái xác nhận tiền lệ B5-kuejin (`P'o, Hun` giữ nguyên) |
| Convert Arcanoi Perk Point | Chuyển Đổi Điểm Lợi Thế Arcanoi | đặt mới, dịch nghĩa; "Arcanoi" giữ nguyên theo B4h |
| Manifestation *(key `POD_create_manifestation_interaction`, chữ hiển thị "Manifestation")* | Manifestation *(giữ nguyên)* | tái xác nhận B4h — nhóm danh từ riêng kỹ thuật gọi hồn/pháp thuật (Golem/Automaton/Effigy/Animantis/Servitor/Manifestation) giữ nguyên tiếng Anh; chỉ dịch động từ bao quanh ("Tạo Manifestation") |
| Choose a Necromancer | Chọn Một Nhà Gọi Hồn | đặt mới; "Necromancer" = "Nhà Gọi Hồn" tái dùng tiền lệ `necromancy`/`necromancer` đã dịch ở `traits_POD_l_english.yml` (`Cenotaph Path của [necromancy\|E]`) |
| Black Torc of Carniog *(tên artifact)* | Vòng Cổ Đen của Carniog | đặt mới; "Torc" dịch "Vòng Cổ" (vòng cổ kim loại kiểu Celtic), "Carniog" là tên riêng giữ nguyên |
| Fascinate | Mê Hoặc | đặt mới, dịch nghĩa (cấy ý nghĩ vào mục tiêu trước khi ra lệnh) |
| Charge of Duty | Trọng Trách | đặt mới, dịch nghĩa |
| Driving Urge | Thôi Thúc Mãnh Liệt | đặt mới, dịch nghĩa |
| Target Lock | Khóa Mục Tiêu | đặt mới, dịch nghĩa |
| Puppet *(actor_secondary label của Fascinate-chain)* | Con Rối | tái dùng nguyên trạng B5-wraith-p2 (`Control Puppet` = "Điều Khiển Con Rối") |

Ghi chú: dòng 104 (gốc, trong đoạn 370-495) là dòng trống **hoàn toàn rỗng** (không có space) — khác các dòng trống khác trong đoạn này đều có 1 space — đã giữ nguyên chính xác khi ghi file scratch. Đã đối chiếu số lượng `$ref$` (6), bracket `[...]` (32), tag mở/đóng (5/5), icon (0), `\n` (0), `\"` (0) giữa bản gốc và bản dịch — khớp tuyệt đối.

## B5-wraith-p3. Thuật ngữ đoạn `interactions/POD_character_interactions_wraith_l_english.yml` dòng 247-369, việc #5

Nguồn: tương tác Escher's Stair (Labyrinth), các tương tác artifact (Strengthen/Impress/Reweave Artifact), Corpus Heal, cụm 9 tương tác Transfer/Facilitate Pathos/Corpus/Arcanos In-Out, cụm Angst Vessel (Create/Store/Extract, 12 key biến thể you/they/quá khứ), Shadow Wrack, Purchase Arcanoi, Weaken Dark Passion, Trimming Thorns, Transfer Angst, và khối comment `# Thorn #` mở đầu nhóm Catharsis/Shadow Familiar/Tainted Relic/Pact of Doom/Separate Shadow. Có 3 lần `[UmbraGlossary('pod_realm_labyrinth')]` (1 tham số, không dịch). Không có `Glossary()`/`UmbraGlossaryLocalized()` hai tham số trong đoạn này.

| Thuật ngữ gốc | Bản dịch | Ghi chú |
|---|---|---|
| Command Wraith *(nhãn phụ `#weak (...)#!` sau tên tương tác)* | Sai khiến Oan hồn | khớp theo cách dịch của B5-wraith-p2/p4 (2 đoạn liền kề) — không tự đặt "Ra Lệnh Oan Hồn" dù nghĩa tương đương, để tránh 3 cách dịch khác nhau cho cùng cụm trong 1 file (part1 dùng "Điều Khiển Oan Hồn") |
| actor_secondary label "Wraith" trong các tương tác Command Wraith | Oan hồn *(viết hoa O, chữ sau thường)* | khớp cách viết hoa của B5-wraith-p2/p4; khác cách viết "Oan Hồn" (hoa cả 2 chữ) của phần part1 — ưu tiên khớp 2 đoạn liền kề trực tiếp |
| "Command one of your bound wraiths to..." *(mở đầu câu `_desc` của mọi tương tác Command Wraith)* | "Sai khiến một trong những oan hồn bị ràng buộc của ngươi..." | tái dùng nguyên cụm mở đầu đã dùng ở B5-wraith-p2/p4 (11 lần), thay cho bản dịch ban đầu "Ra lệnh cho một oan hồn bị ràng buộc của ngươi" để nhất quán tại ranh giới ghép file |
| Angst | Angst *(giữ nguyên)* | tái xác nhận quyết định đã chốt ở B5-wraith-p5 — KHÔNG dịch thành "Sầu Muộn"/từ khác; đoạn này có cụm 19 lần Angst (Angst Vessel, Store/Extract/Transfer/Siphon Angst) — bản nháp đầu tiên đã dịch nhầm thành "Sầu Muộn" trước khi đối chiếu B5-wraith-p5 và sửa lại toàn bộ |
| Angst Vessel | Bình Chứa Angst | đặt mới, dịch nghĩa "Vessel"="Bình Chứa", giữ "Angst" nguyên theo trên |
| Escher's Stair *(trùng tên với B5-wraith-p6 dòng 716 khác? không — đây là power riêng của Pandemonium xuất hiện lại)* | Cầu Thang Escher | tái dùng nguyên trạng B5-wraith-p6 (đã đặt "Escher's Stair"="Cầu Thang Escher" ở đoạn dòng 616-738) — cùng power, xuất hiện 2 lần trong file dưới 2 khối khác nhau (thường + Command Wraith) |
| Strengthen Artifact / Impress Artifact | Củng Cố Hiện Vật / In Dấu Hiện Vật | đặt mới, dịch nghĩa; "Impress" = "in dấu/khắc dấu" (đặt ký ức vào vật) |
| Reweave Artifact | Dệt Lại Hiện Vật | nhất quán "Reweave"="Dệt Lại" đã chốt B4y/B5, áp dụng cho "Hiện Vật" thay vì "artifact" chung chung |
| Corpus Heal | Chữa Lành bằng [Corpus\|E] | đặt mới, dịch nghĩa, giữ "Corpus" nguyên theo B4h; nhất quán cấu trúc "Chữa Lành bằng Pathos" đã có ở B5-wraith-p5 (Moliate) |
| Transfer Pathos/Corpus/Arcanos In/Out | Chuyển Pathos/[Corpus\|E]/Arcanos Vào/Ra | đặt mới, dịch nghĩa; "Pathos"/"Corpus"/"Arcanos" đều giữ nguyên theo B0/B4h |
| Facilitate Pathos/Corpus/Arcanos *(tương tác 3 bên, có tù nhân trung gian)* | Hỗ Trợ Chuyển Pathos/[Corpus\|E]/Arcanos | đặt mới, dịch nghĩa ("facilitate" = hỗ trợ/tạo điều kiện cho việc chuyển) |
| Purchase Arcanoi | Mua Arcanoi | đặt mới, dịch nghĩa; "Arcanoi" (số nhiều của Arcanos) giữ nguyên theo B4h/B4u |
| Weaken Dark Passion | Làm Suy Yếu Đam Mê Đen Tối | đặt mới; "Dark Passion(s)"="Đam Mê Đen Tối" tái dùng nguyên trạng B4h |
| Trimming Thorns *(tên tương tác, khác `# Thorn #` là dòng comment)* | Tỉa Gai | đặt mới, dịch nghĩa; "Thorns" ở đây là danh từ chung (gai/hiệu ứng tiêu cực từ `thorn_lifestyle`), khác "Thorns" danh từ riêng phe phái Giáo phái đã giữ nguyên ở B4h/nơi khác — ngữ cảnh này rõ ràng là nghĩa đen "cái gai" nên dịch nghĩa |
| Transfer Angst *(khác "Transfer Pathos/Corpus/Arcanos" ở trên — đây là đổi "coping trait" sang stress, không phải chuyển tài nguyên giữa 2 nhân vật)* | Chuyển Hóa Angst | dịch "Transfer" thành "Chuyển Hóa" thay vì "Chuyển" đơn thuần để phân biệt rõ với nhóm Transfer Pathos/Corpus/Arcanos (chuyển tài nguyên qua lại giữa người), vì bản chất cơ chế khác nhau (đổi loại đặc điểm, không chuyển giữa 2 nhân vật) |
| Instigate Catharsis | Khơi Mào Tịnh Hóa | đặt mới, dịch nghĩa; đặt "Catharsis"="Tịnh Hóa" — LƯU Ý: đây là lần đầu "Catharsis" được dịch trong repo (chưa có tiền lệ ở B5-wraith-p1/p2/p4/p5/p6), cần rà soát lại nếu gặp mô tả khác của Catharsis mâu thuẫn nghĩa (bản chất game: Shadow thắng thế/chiếm quyền kiểm soát, không phải "thanh lọc" tích cực — "Tịnh Hóa" chọn theo nghĩa "được giải phóng/bộc lộ hoàn toàn" của Shadow, gần nghĩa gốc "catharsis" tâm lý học hơn là nghĩa tôn giáo) |
| Resist Catharsis | Kháng Cự Tịnh Hóa | nhất quán với trên |
| Tainted Relic | Thánh Tích Nhiễm Độc | đặt mới, dịch nghĩa |
| Pact of Doom | Khế Ước Diệt Vong | đặt mới, dịch nghĩa |
| Shadow Familiar | linh thú của Bóng *(thường, trong câu văn xuôi)* / Linh Thú của Bóng *(hoa, trong tên tương tác)* | "Familiar"="linh thú" tái dùng tiền lệ đã chốt (Kuei-Jin Goblin Cat, dòng ~2289) — áp dụng cách viết hoa/thường theo vị trí (tiêu đề UI vs câu mô tả), "Bóng" tái dùng B4h |
| Siphon Angst | Rút Cạn Angst | đặt mới, dịch nghĩa |
| Materialize (your Shadow) *(tên tương tác `POD_separate_shadow_interaction`, key có "separate" nhưng chữ hiển thị dùng "Materialize")* | Hiện Hình (Bóng của Ngươi) | dịch theo chữ hiển thị thực tế "Materialize", không dịch theo tên key "separate" |

Ghi chú: dòng 108 (`artifact_tainted_relic_description`) chứa cặp dấu ngoặc kép kiểu Unicode cong `"..."` (U+201C/U+201D, KHÔNG phải escape `\"`) quanh "lost"/"destroyed" — đã giữ nguyên đúng ký tự Unicode gốc trong bản dịch (`"mất"`/`"hủy diệt`), không đổi thành `\"` hay bỏ dấu. Dòng 369 (gốc) là dòng trống chứa 1 space — giữ nguyên. Bản nháp đầu tiên có 2 lỗi đã tự phát hiện và sửa trước khi ghi file: (1) dịch "Angst" thành "Sầu Muộn" thay vì giữ nguyên (mâu thuẫn B5-wraith-p5), (2) dùng "Ra Lệnh Oan Hồn"/"Oan Hồn" thay vì "Sai khiến Oan hồn"/"Oan hồn" (mâu thuẫn B5-wraith-p2/p4 liền kề). Đã đối chiếu số lượng `$ref$` (17), bracket `[...]` (47), tag mở/đóng (6/6), icon (0), `\n` (1), `\"` (0), tổng dòng (123) giữa bản gốc và bản dịch — khớp tuyệt đối. Không có BOM trong file scratch output.

## B6-decisions-sorcery. Thuật ngữ 14 trường phái Sorcery (`decisions/POD_numina_sorcery_decisions_l_english.yml`), việc #6

Lần đầu dịch tên đầy đủ 14 trường phái pháp thuật (lifestyle Sorcery của phàm nhân), xuất hiện dạng `sorcery_<school>_tier_6_unlock_decision`. Tái dùng 4 tên đã chốt sẵn ở B5-numina (`interactions/POD_character_interactions_numina_l_english.yml`): Conveyance, Cursing, Fascination, Oneiromancy. Đặt mới 10 tên còn lại theo mẫu hậu tố "Thuật" nhất quán với các tên đã chốt (Thuật Dò Tìm, Thuật Nhập Mộng, Thuật Khống Thời Tiết).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Alchemy | Giả Kim Thuật | đặt mới; tái dùng gốc Hán Việt "Giả Kim" đã có ở B5-numina (Alchemical Product=Sản Phẩm Giả Kim) |
| Conjuration | Triệu Hoán Thuật | đặt mới, dịch nghĩa (gọi/triệu ra qua ma pháp), khác "Triệu Hồi" (Summon) và "Triệu Hồn" (Channel) đã chốt B5-numina — 3 khái niệm riêng biệt |
| Conveyance | Vận Chuyển Thuật | ✅ tái dùng B5-numina |
| Cursing | Chú Thuật | ✅ tái dùng B5-numina |
| Divination | Bói Toán Thuật | đặt mới, dịch nghĩa Hán Việt phổ thông |
| Enchantment | Phù Chú Thuật | đặt mới, dịch nghĩa; tránh trùng "Chú Thuật" (Cursing) bằng cách thêm "Phù" (bùa/phù phép) |
| Ephemera | Linh Thể Thuật | đặt mới; "Ephemera" trong ngữ cảnh Sorcery/Numina WoD chỉ các linh thể/vật thể phù du liên quan tinh linh nhỏ, dịch nghĩa mô tả |
| Fascination | Mê Hoặc Thuật | ✅ tái dùng B5-numina (`Fascination`="Mê Hoặc"), thêm hậu tố "Thuật" cho nhất quán tên trường phái ở file này |
| Healing | Trị Liệu Thuật | đặt mới; "Trị Liệu" tái dùng từ B5-numina (Psychic Healing), thêm "Thuật" |
| Hellfire | Hỏa Ngục Thuật | đặt mới, dịch nghĩa |
| Mana Manipulation | Thao Túng Mana | đặt mới; "Mana" giữ nguyên (thuật ngữ ma pháp phổ thông không có bản dịch tự nhiên), "Manipulation"="Thao Túng" |
| Oneiromancy | Thuật Nhập Mộng | ✅ tái dùng B5-numina |
| Shadow Casting | Chú Bóng Thuật | đặt mới, dịch nghĩa (đọc chú thuật qua bóng tối), khác "Shadowcasting" của Wraith (không xuất hiện trong file này) |
| Shapeshifting *(trường phái Sorcery của phàm nhân, khác trait biến hình của Garou/Fera)* | Biến Hình Thuật | đặt mới, dịch nghĩa; thêm "Thuật" để phân biệt ngữ cảnh với trait `shapeshifter` (Fera) |
| Summoning Warding and Binding | Triệu Hồi, Trấn Ải và Trói Buộc | đặt mới; tách 3 khái niệm ghép trong tên gốc — "Summoning"="Triệu Hồi" (tái dùng tiền lệ toàn mod), "Warding"="Trấn Ải" (bùa trấn/phòng ngự), "Binding"="Trói Buộc" (tái dùng "Oan Hồn Bị Ràng Buộc"→ ở đây dùng "Trói Buộc" cho động từ) |
| Weather Control | Khống Chế Thời Tiết | đặt mới, dịch nghĩa; khác "Weathercraft"="Thuật Khống Thời Tiết" đã chốt B5-numina (tên khác cho khái niệm tương tự, giữ 2 bản dịch riêng vì 2 key gốc khác nhau) |

Lỗi gốc đã giữ nguyên (không sửa "bug" của game): `sorcery_shapeshifting_tier_6_unlock_decision_desc`/`_confirm` bị đảo lẫn nội dung so với format chuẩn của 13 trường phái còn lại (desc chứa câu đáng lẽ ở confirm, và ngược lại) — dịch đúng theo nội dung tiếng Anh thực tế ở đúng vị trí, không hoán đổi lại.

## B6-decisions-l. Thuật ngữ `decisions/POD_decisions_l_english.yml` (1972/1972 dòng, file lớn nhất trong decisions/), việc #6

Nguồn: file lớn nhất `decisions/`, dịch qua 6 agent chia đoạn (1-415, 416-773, 774-988, 989-1319, 1320-1649, 1650-1972). Nội dung chính: mục tiêu thống nhất từng clan Vampire (`X_victory_objective_decision`), khôi phục các tổ chức/tước vị lịch sử đã sụp đổ (`restore_X`), Inquisition/Hunter/Web of Knives, các quyết định Kuei-Jin (Hun/P'o, Wheel of Ages, Fourth/Fifth/Sixth Age), Demon (Ma Hoàng), Wraith/Fera rải rác.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Web of Knives | Web of Knives *(giữ nguyên)* | tên tổ chức sát thủ Banu Haqim, danh từ riêng WoD, không dịch theo B0 (agent ban đầu tự đặt "Mạng Lưới Dao Găm" nhưng đã sửa lại giữ nguyên để nhất quán với các key `restore_web`/`k_webofknives` khác trong cùng file dùng nguyên "Web of Knives") |
| Sword of St James, Sisters of St John/Sisters of St. John, Knights of Acre, Oculi Dei, House Murnau/Gia Tộc Murnau | *(tên riêng dòng tu/tổ chức Inquisition giữ nguyên tiếng Anh, trừ "House"→"Gia Tộc" theo A10)* | tái dùng tiền lệ B4g (Acre, Oculi Dei giữ nguyên), "St."→"Thánh" khi đứng trước tên (Thánh John) |
| Little Death *(trạng thái ngủ đông của Kuei-Jin, khác Torpor của ma cà rồng phương Tây)* | Tiểu Tử | đặt mới, dịch sát nghĩa Hán Việt, phân biệt với "Miên trạng" (Torpor) đã chốt |
| Kaja *(văn tự biểu ý của Kuei-Jin)* | Kaja *(giữ nguyên)* | danh từ riêng hệ thống chữ viết, không có tiền lệ dịch |
| Demiurge *(heretic_victory, thuật ngữ Ngộ đạo)* | Đấng Sáng Tạo Giả | đặt mới, dịch nghĩa triết học Ngộ đạo, không có tiền lệ vanilla |
| Underworld *(tham số 2 của `UmbraGlossaryLocalized('shadowlands',...)`)* | Âm Phủ | ✅ tái xác nhận B4j — 2 agent ban đầu dịch sai thành "Địa Ngục Giới"/giữ nguyên tiếng Anh, đã sửa khi merge |
| Second Age / Third Age | Kỷ Nguyên Thứ Hai / Kỷ Nguyên Thứ Ba | đặt mới, nối tiếp "Kỷ Nguyên Thứ Tư/Năm/Sáu" đã chốt B3c/B6-decisions-sorcery, hoàn thiện chuỗi 6 kỷ nguyên Kuei-Jin |
| Blood Bond / Blood Bonded | Khế Ước Máu | tái dùng `game_concept_bloodbond_desc` đã có bản dịch, áp dụng cho cả 2 dạng danh từ/tính từ |
| Demon Emperor | Ma Hoàng | ✅ tái xác nhận B3c (`podgloss.demonemperor`) — 3/4 agent ban đầu bỏ sót không dịch tham số 1, đã sửa khi merge |
| The Beast | Dã Thú | ✅ tái xác nhận tiền lệ toàn mod (B4/B5), áp dụng cho tham số 1 của `Glossary('The Beast',...)` |

## B7-modifiers-houses. Thuật ngữ `modifiers/houses_POD_modifiers_l_english.yml` (770/770 dòng — file lớn nhất `modifiers/`), việc #7 hoàn tất

Nguồn: danh sách "House" (chi hệ/dòng dõi/gia tộc) của mọi splat — Vampire (mọi clan), Mummy Dynasty, Fae House, Gangrel/Tzimisce/Tremere Revenant families, Kuei-Jin House Nhật Bản/Đông Nam Á, custom bloodline theo skill. Dịch qua 4 agent chia đoạn (1-197, 198-465, 466-680, 681-770).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| House *(chi hệ vampire/gia tộc Revenant/gia tộc Fae)* | Gia Tộc | ✅ tái xác nhận tiền lệ đã chốt từ trước (TERMINOLOGY.md A10 dòng 179, "House"="Gia tộc") — 2/4 agent ban đầu tự đặt "Chi Hệ" (không tra TERMINOLOGY.md trước), đã sửa lại "Gia Tộc" khi merge để nhất quán toàn mod |
| Dynasty *(Mummy — Shemsu-Heru, Ishmaelites, Apepnu, Cabiri, Wu Feng, Xian Lung, và các "House" Demon Asharu/Rabisu/Halaku/Namaru/Lammasu/Annunaki/Neberu)* | Triều đại | ✅ tái xác nhận tiền lệ A10 (`game_concept_dynasty`) |
| Beast *(tham số 1 của `Glossary('Beast','game_concept_beast_desc')`)* | Dã Thú | ✅ tái xác nhận tiền lệ toàn mod |
| Demon Emperor *(4 lần, các House Kuei-Jin Hell Tigers/Emperor's Vanguard/Wise Spiders/Scorching Devils)* | Ma Hoàng | ✅ tái xác nhận B3c, agent dịch đủ cả 4 lần ngay từ đầu (không bỏ sót) |
| "Dominant House X" *(13 House Kuei-Jin Nhật Bản phiên bản nâng cấp)* | "Gia Tộc X Chiếm Ưu Thế" | đặt mới, áp dụng công thức nhất quán cho cả 13 dòng + "Dominant Uji"→"Uji Chiếm Ưu Thế" |
| Bloodline of Warriors/Killers/Plotters/Diplomats/Seekers/Rulers *(6 custom bloodline theo skill, `dynn_custom_bloodline_*`)* | Dòng Máu Chiến Binh / Sát Thủ / Mưu Sĩ / Ngoại Giao / Cầu Tri / Quân Vương | đặt mới, dịch nghĩa theo skill tương ứng (martial/prowess/intrigue/diplomacy/learning/stewardship) |
| Purebloods *(`dynn_custom_bloodline_secret_modifier`, tự xưng hậu duệ thật của Caine)* | Huyết Thống Thuần Chủng | đặt mới, dịch nghĩa |
| Initiated Family / Knightly Order / Mendicant Order / Contemplative Order *(4 phân loại holy order chung Tzimisce Revenant, không phải tên riêng)* | Gia Tộc Nhập Môn / Hiệp Sĩ Đoàn / Khất Sĩ Đoàn / Đan Viện Chiêm Niệm | đặt mới, không tìm thấy tiền lệ vanilla base_game_vh cho 4 cụm này, dịch nghĩa theo phong cách tôn giáo trung cổ |
| Revenant(s) *(tham số 1 của `Glossary('Revenant(s)','game_concept_revenant_desc')`, các gia tộc phàm nhân phục vụ 1 clan vampire)* | giữ nguyên tiếng Anh "Revenant"/"Revenants" khi là tham số 1 của Glossary; "Huyết tộc Hồi sinh" (tiền lệ A) khi xuất hiện tự nhiên trong câu văn xuôi | agent phân biệt 2 ngữ cảnh: giữ nguyên khi glossary hiển thị đúng từ gốc, dịch nghĩa khi câu văn tự nhiên hơn (ví dụ `dynn_bima_modifier_disc`) |
| Ahriman *(giá trị hiển thị của key `house_ahrimane_modifier`, KHÔNG phải "Ahrimane")* | Ahriman *(giữ nguyên)* | chú ý key và giá trị hiển thị khác nhau — key có "e" cuối nhưng giá trị hiển thị không có, giữ đúng giá trị gốc |

**Lỗi merge phát hiện và sửa ở file này (đáng chú ý — xác nhận cần key-matching cẩn thận dù đã chia đoạn theo ranh giới có vẻ rõ ràng):**
1. **Dòng 681 (`dynn_horus_modifier: "Shemsu-Heru"`) bị bỏ sót hoàn toàn** — nằm đúng ranh giới giữa đoạn 3 (466-680) và đoạn 4 (681-770): đoạn 3 dừng đúng ở 680, nhưng đoạn 4 lại bắt đầu nhầm từ dòng 682 (`dynn_horus_modifier_desc`) thay vì 681. Cả 2 agent đều tự tin báo cáo đúng phạm vi nhưng lệch nhau đúng 1 dòng ở điểm nối. Phát hiện nhờ so sánh tổng số dòng 4 đoạn (197+267+215+89=768, thiếu 2 so với 770) rồi dò từng ranh giới bằng `awk 'NR==...'` trên bản gốc.
2. **Đoạn 2 (198-465) thiếu đúng 1 dòng trống ở cuối (dòng 465)** — agent tự tin báo "268 dòng khớp" nhưng thực tế thiếu dòng trống cuối đoạn (dòng đầu đoạn — dòng trống 198 — đã có đúng). Phát hiện nhờ so khớp key-sequence + vị trí dòng trống giữa bản gốc và bản dịch bằng script `sed -E 's/^(key):.*/\1/'` áp dụng cho toàn file, không chỉ đếm số lượng dòng trống.
3. Đoạn 1 (1-197): agent tự đặt "House"→"Chi Hệ" dù được nhắc "tra TERMINOLOGY.md trước" — không tra nên bỏ lỡ tiền lệ đã chốt từ lâu (A10). Đoạn 2 và các đoạn khác tự tra và phát hiện đúng "Gia Tộc", cho thấy việc nhắc tra cứu không đảm bảo agent luôn làm theo — **luôn tự grep đếm số lần thuật ngữ nghi ngờ xuất hiện ở mỗi đoạn trước khi merge, không chỉ tin báo cáo.**
4. Dòng 151 (`house_ananke_modifier_desc`) mất 1 dấu cách thừa cuối dòng so với bản gốc — lỗi quen thuộc dạng "dòng có khoảng trắng cuối bị agent cắt gọn", khôi phục thủ công khi merge.

**Bài học lặp lại (đợt thứ N với ≥4 agent song song dịch cùng 1 file lớn chia đoạn):**
1. Khi 1 khái niệm lặp lại nhiều lần xuyên suốt CẢ file (ví dụ "Age" 28 lần, "Demon Emperor" 4 lần), một agent phụ trách 1 đoạn có thể dịch đúng còn agent khác phụ trách đoạn khác lại bỏ sót hoàn toàn — không phải lỗi ngẫu nhiên 1-2 chỗ mà có thể là **toàn bộ một đoạn 300+ dòng bỏ sót một mẫu Glossary cụ thể**. Lệnh gom nhóm theo tham số 2 của `Glossary()` (đã dùng ở các đợt trước) vẫn là cách duy nhất bắt được loại lỗi này.
2. **Lỗi line-ending LF thay vì CRLF lần này xảy ra ở quy mô lớn hơn nhiều so với các đợt trước**: 2/6 đoạn (653/1972 dòng, tức 1/3 toàn file) bị ghi bằng LF thuần dù prompt đã dặn rất kỹ "dùng CRLF, không dùng LF". Đáng chú ý: lệnh `file <path>` báo **"CRLF line terminators"** cho cả file dù 2/6 đoạn bên trong là LF thuần — `file` chỉ lấy mẫu, không quét toàn bộ. Chỉ lệnh đếm "lone LF" (`perl -0777 -ne '$c=()=/(?<!\r)\n/g; print $c'`) trên TOÀN FILE mới bắt được chính xác. Cảnh báo bổ sung: **lệnh `sed -i` trên Git Bash/MinGW cũng tự ý strip CR** khi sửa nội dung 1 file CRLF tại chỗ (đã tự gây ra lỗi này 1 lần trong chính đợt merge này khi dùng `sed -i` để sửa hàng loạt tham số Glossary) — dùng `perl -pi -e` thay vì `sed -i` khi cần sửa tại chỗ trên file CRLF, hoặc convert LF→CRLF lại ngay sau mỗi lần `sed -i`.

## B8-lifestyles-p1. Thuật ngữ đợt nhỏ 1 việc #8 `lifestyles/` — 6 file rất nhỏ (fera_common, hengeyokai, demon_arts, urgetaints, theurgy, qiao)

Nguồn: 6 file ≤93 dòng, dịch trực tiếp không qua agent. Đây là lần đầu dịch mảng `lifestyles/` — nhiều thuật ngữ nền tảng lặp lại xuyên suốt cả 27 file được chốt ở đây.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Gift(s) *(năng lực siêu nhiên Garou/Fera nhận từ tổ tiên/totem, danh từ nền tảng của toàn bộ `lifestyles/POD_fera/`)* | Ân Huệ | đặt mới theo quyết định người dùng 2026-07-27; áp dụng nhất quán cho mọi biến thể ghép: "Breed Gifts"="Ân Huệ Dòng Sinh", "Common Gifts"="Ân Huệ Chung", "Lunar Gifts"/"Lunar Auspice Gifts"="Ân Huệ Trăng"/"Ân Huệ Tương Trăng", "Stream Gifts"="Ân Huệ Dòng Chảy" |
| Homid / Lupus *(2 dạng "Breed" của Garou — người/sói, đã chốt B4c `Breed`="Dòng Sinh")* | Homid / Lupus *(giữ nguyên)* | danh từ riêng WoD, không có tiền lệ dịch nghĩa; xuất hiện dạng key thuần (`homidgifts_visible`) và chữ hiển thị "Homid"/"Lupus" |
| Auspice *(Lunar Auspice — 5 tuần trăng Garou: Ragabash/Theurge/Philodox/Galliard/Ahroun)* | Tướng Trăng | đặt mới; "Auspice" gốc nghĩa "điềm báo/chức phận theo mệnh trời" — dịch "Tướng" (như tướng số) + "Trăng" gợi đúng cơ chế 5 pha trăng quyết định vai trò Garou khi sinh ra |
| Ragabash / Theurge / Philodox / Galliard / Ahroun *(5 Tướng Trăng Garou, danh từ riêng)* | Ragabash / Theurge / Philodox / Galliard / Ahroun *(giữ nguyên)* | danh từ riêng WoD, không dịch nghĩa; chỉ xuất hiện trong comment `#Gifts: Ahroun` ở file `POD_werewolf_lifestyle` — không phải chữ hiển thị người chơi thấy |
| Hengeyokai *(Beast Courts Á Đông — cáo/rắn/rồng biến hình, nhóm Fera khác Garou)* | Hengeyokai *(giữ nguyên)* | danh từ riêng WoD gốc Nhật ngữ, không có tiền lệ dịch nghĩa |
| Beast Courts | Beast Courts *(giữ nguyên)* | tên riêng tổ chức Hengeyokai, đặt mới giữ nguyên theo B0 (chưa có tiền lệ dịch, ghép 2 từ thường thành danh xưng riêng) |
| Mindspeak / Create Element / Courtly Speech / Blaze Talons / Sense Imbalance / Waking Dream of Unity / Part the Wall / Exorcism / Walking the Bone Road / Way of Ten Thousand Cities *(10 tên Gift Hengeyokai)* | Thần Giao / Tạo Nguyên Tố / Ngôn Ngữ Cung Đình / Bùng Móng Vuốt / Cảm Ứng Mất Cân Bằng / Mộng Thức Tỉnh Hợp Nhất / Xuyên Vách Ngăn / Trừ Tà / Đi Trên Đường Xương / Đạo Vạn Thành | đặt mới, dịch nghĩa Hán Việt/thuần Việt ngắn gọn theo mẫu tên Gift; "Exorcism"="Trừ Tà" tái dùng tiền lệ B5-numina/B5-hunter (Chi Exorcism) |
| P'o *(nhắc lại, `demon_arts_lifestyle_desc`)* | P'o *(giữ nguyên)* | tái xác nhận B5-kuejin |
| Devil Fist / Black Wind / Iron Mountain / Demon Regalia *(4 Demon Art cụ thể Kuei-Jin)* | Ma Quyền / Hắc Phong / Thiết Sơn / Ma Bào | tái xác nhận B5-kuejin, dùng đúng 4 tên đã chốt khi dịch `interactions/POD_character_interactions_kuejin` |
| Dharma *(tham số 2 của `Glossary('Dharma','podgloss.dharma')`, xuất hiện trong perk cost effect)* | Pháp Môn | tái xác nhận B3c/B4f, giữ tham số 1 dịch, tham số 2 (key) không đổi |
| Urge Taints *(lifestyle Garou/Fera sa ngã theo Wyrm, "Urge Wyrms" ban tặng)* | Vết Nhiễm Dục Vọng | đặt mới; "Urge" (dục vọng/xung động nội tâm) + "Taint" (vết nhiễm/ô uế) — khớp chủ đề sa ngã theo Wyrm (đã chốt B3 giữ nguyên "Wyrm") |
| Urge Wyrm(s) *(thực thể ban Urge Taints)* | Wyrm Dục Vọng | ghép "Wyrm" (giữ nguyên B3) + "Dục Vọng", biến thể cùng gốc "Urge" |
| Malformed Flesh / Malformed Muscle / Malformed Bone / Bestial Limbs / Forked Tongue / Reversed Eye / Bane Stomach / Thundering Throat / Profaned Lungs / Unholy Heart *(10 perk nhóm "Physical" Urge Taints)* | Thịt Biến Dạng / Cơ Biến Dạng / Xương Biến Dạng / Tứ Chi Dã Thú / Lưỡi Chẻ / Mắt Đảo Ngược / Dạ Dày Tà Linh / Cổ Họng Sấm Rền / Phổi Ô Uế / Tim Bất Khiết | đặt mới, dịch nghĩa trực tiếp; "Bane"="Tà Linh" tái dùng B4c |
| Dominance / Indulgence / Obsession / Warped Reflection / Dancing Shadows / Fragmented Psyche / Splintered Soul / Maniacal Mind / Sanguine Spirit / Embrace Oblivion *(10 perk nhóm "Mental" Urge Taints)* | Áp Chế / Chiều Dục / Ám Ảnh / Ảnh Phản Chiếu Lệch Lạc / Vũ Điệu Bóng Tối / Tâm Trí Phân Mảnh / Linh Hồn Vỡ Vụn / Tâm Trí Cuồng Loạn / Linh Hồn Đỏ Thẫm / Ôm Lấy Diệt Vong | đặt mới, dịch nghĩa trực tiếp; "Embrace Oblivion" không liên quan "the Embrace" (nghi thức hóa ma cà rồng) — dịch nghĩa thường "ôm lấy sự diệt vong/hư vô" |
| Theurgy *(lifestyle phàm nhân, phép thuật kiểu Cơ Đốc giáo — 5 "Via")* | Thần Thuật | tái xác nhận B4 (`trait_theurgist`)/B5-numina |
| Via Geniorum / Via Ignis / Via Medicamenti / Via Necromantiae / Via Oraculi *(5 con đường Theurgy)* | Via Geniorum / Via Ignis / Via Medicamenti / Via Necromantiae / Via Oraculi *(giữ nguyên)* | tên Latin riêng, giữ nguyên theo B3k/B5-numina (mẫu "Via X" không dịch) |
| Hedge Magic *(nhắc lại, so sánh với Theurgy)* | thuật huyền bí dân gian | tái xác nhận B5-numina |
| Numinum *(tham số 2 của `Glossary('Numinum','game_concept_numina_desc')`)* | *(không đổi — là key, không dịch)* | tái xác nhận quy tắc Glossary() tham số 2 |
| Qiao *(hệ năng lực chiến đấu siêu nhiên của Shih — thầy trừ tà Trung Hoa)* | Qiao *(giữ nguyên)* | danh từ riêng WoD gốc Trung Hoa, không có tiền lệ dịch nghĩa; xuất hiện trong tên file/comment, không phải chữ hiển thị trực tiếp trong file này |
| Shih *(nhắc lại, `GetTrait('shih').GetName`)* | Shih *(giữ nguyên)* | tái xác nhận B4f (Shih's Belief) |
| Mo Kung Qiao *(tên trường phái Qiao cụ thể, `CELESTIAL_EYES_PERK_EFFECT`)* | Mo Kung Qiao *(giữ nguyên)* | danh từ riêng, giữ nguyên nhất quán với "Qiao" |
| I Shen *(nhóm kỹ thuật Qiao chuyên khắc chế shen, `DIVINE_PROHIBITION_PERK_EFFECT`)* | I Shen *(giữ nguyên)* | danh từ riêng WoD, giữ nguyên |
| shen *(danh từ chung WoD chỉ mọi thực thể siêu nhiên/thần linh — Kuei-Jin, demon, spirit...)* | shen *(giữ nguyên)* | danh từ riêng WoD phổ biến xuyên suốt file `POD_qiao_lifestyle`, không dịch nghĩa theo B0 |
| Wan Kuei *(nhắc lại, `CLUTCH_OF_THE_WAN_KUEI_PERK_EFFECT`)* | Wan Kuei *(giữ nguyên)* | tái xác nhận B4f |
| Celestial Punishment / Divine Bindings / Heavenly Flames / Celestial Fires / Heaven's Thunder / Heaven's Judgment / Divine Prohibition *(7 perk nhóm đầu Qiao — lá bùa trấn yểm)* | Thiên Hình / Thiên Trói / Thiên Hỏa / Hỏa Thiên Giới / Thiên Lôi / Thiên Phán / Thiên Cấm | đặt mới, dịch nghĩa Hán Việt ngắn gọn theo motif "Thiên" (trời) xuyên suốt nhóm bùa trấn yểm Đạo giáo |
| Steel Skin / Dragon's Speed / Tiger's Strength / Celestial Eyes / Body of the Dragon / Ten Ox Strength / Diamond Body *(7 perk tăng chỉ số Qiao)* | Da Sắt / Tốc Độ Rồng / Sức Mạnh Hổ / Mắt Trời / Thân Rồng / Sức Mạnh Mười Trâu / Thân Kim Cương | đặt mới, dịch nghĩa trực tiếp theo motif linh vật (rồng/hổ/trâu) |
| Opened Eyes / Divine Perceptions / Wind Talk / Celestial Window / Celestial Doorway / Sight Without Eyes / The Eye of Heaven *(7 perk nhóm cảm ứng/nhìn xuyên Qiao)* | Mắt Mở / Thiên Nhãn / Lời Gió / Cửa Sổ Trời / Cổng Trời / Nhìn Không Cần Mắt / Mắt Trời Cao | đặt mới, dịch nghĩa trực tiếp |
| Yin Realm / Yang Realm(s) *(cõi Âm/Dương chung, Kuei-Jin-Qiao)* | Cõi Âm / Cõi Dương | tái dùng "Yin/Yang"="Âm/Dương" đã chốt B3c, ghép "Cõi" cho "Realm" |
| Yang World(s) *(tham số 1 của `Glossary('Yang World(s)','game_concept_yang_world_desc')`)* | Dương Giới | ✅ **sửa lại theo tiền lệ B3e đã chốt trước đó** (dòng ~691/699, khi dịch `religion/POD_religion_kueijin`) — KHÔNG dùng "Cõi Dương" như bản nháp ban đầu của mục này; áp dụng đúng ở `POD_qiao_lifestyle_l_english.yml` dòng 43 |
| Hungry Dead *(tham số 1 của `Glossary('Hungry Dead','game_concept_kuei_jin_desc')`, biệt danh tự xưng của Kuei-Jin)* | Người Chết Đói Khát | đặt mới, dịch nghĩa; key gốc `game_concept_hungry_dead` (định nghĩa riêng của biệt danh này) vẫn chưa dịch — thuộc `game_POD_concepts_l_english.yml`, việc #9, cần dùng lại đúng "Người Chết Đói Khát" khi tới đó |
| Yomi Hell *(tham số 2 của `UmbraGlossaryLocalized('yomi_wan','Yomi Hell')`)* | Địa Ngục Yomi | tái xác nhận B3c |
| Barrier of Pain / The Closing Wound / Spiritual Healing / Escape from Death / Flames of the Phoenix / The Lizard's Tail / Ashes of the Phoenix *(7 perk trị liệu Qiao)* | Rào Chắn Đau Đớn / Khép Vết Thương / Trị Liệu Linh Thiêng / Thoát Khỏi Cái Chết / Lửa Phượng Hoàng / Đuôi Thằn Lằn / Tàn Tích Phượng Hoàng | đặt mới, dịch nghĩa trực tiếp |
| Thousand Fists / Spear Hand / Burning Ghosts / Steel Body / Thousand Swords / Hundred Warriors Strike / Heaven Thunder Strike *(7 perk chiến đấu Qiao)* | Ngàn Nắm Đấm / Tay Giáo / Ma Cháy / Thân Sắt / Ngàn Kiếm / Đòn Đánh Trăm Chiến Binh / Đòn Sấm Trời | đặt mới, dịch nghĩa trực tiếp |
| Frozen River / Stolen Serpent / Celestial Barrier / Clutch of the Wan Kuei / Bite of the Mu / Righteous Hungry Spirit / Demon Eating Technique *(7 perk kháng/hút Chi Qiao)* | Sông Băng / Rắn Bị Đánh Cắp / Rào Chắn Trời / Nắm Bắt Wan Kuei / Cắn của Mu / Linh Hồn Đói Chính Nghĩa / Kỹ Thuật Nuốt Ma | đặt mới, dịch nghĩa trực tiếp; "the Mu" giữ nguyên (danh từ riêng WoD, chưa rõ nghĩa cụ thể, không ép dịch) |
| Eyes of the Dragon / Dark Reflection / Hunted Eyes / Voice of the Yama Kings / Divine Ordinance / Mantle of Heaven / Divine Mandate *(7 perk uy hiếp/thống trị Qiao)* | Mắt Rồng / Ảnh Phản Chiếu Tối / Mắt Săn Mồi / Tiếng Nói Diêm Ma Vương / Sắc Lệnh Trời / Áo Choàng Trời / Thiên Mệnh | đặt mới, dịch nghĩa trực tiếp; "Yama Kings"="Diêm Ma Vương" tái xác nhận B3c |
| Balance of the Spirit / Focus of the Mind / Nightmare Exorcism / Self Exorcism / Mental Dominion / Mountain Meditation / Walking in Balance *(7 perk tâm linh/thiền Qiao)* | Cân Bằng Linh Hồn / Tập Trung Tâm Trí / Trừ Tà Ác Mộng / Tự Trừ Tà / Thống Trị Tâm Trí / Thiền Núi / Đi Trong Cân Bằng | đặt mới, dịch nghĩa trực tiếp |
| Cloud Walking / Water Treading / Wind Strike / Mountain Stance / Celestial Wind / Arrow Cutting / Wind Racing Prana *(7 perk né/di chuyển Qiao cuối)* | Đi Trên Mây / Đạp Nước / Đòn Gió / Thế Núi / Gió Trời / Cắt Tên / Prana Gió Chạy | đặt mới, dịch nghĩa trực tiếp; "Prana" giữ nguyên (khái niệm năng lượng sống Ấn Độ giáo, không có tiền lệ dịch) |

## B8-lifestyles-p2. Thuật ngữ đợt nhỏ 2 việc #8 `lifestyles/` — 8 file 130-190 dòng (shintai, discipline, lore, investiture, planetarygifts, werewolf, chi_arts, soul_arts)

Nguồn: 8 file dịch qua agent song song (mỗi agent 1 file, ghi scratch riêng). Coordinator merge bằng key-matching + verify 3 lớp. **5 lỗi thật phát hiện khi merge** (agent tự claim đã tra TERMINOLOGY nhưng vẫn lệch tiền lệ đã chốt hoặc bỏ dịch tham số 1 của Glossary — xác nhận lại bài học cũ: luôn tự grep/diff, không tin báo cáo agent):
1. `soul_arts`: agent dịch "Dharma" (tham số 1 của `Glossary('Dharma','podgloss.dharma')`) thành "Đạo Pháp" thay vì "Pháp Môn" đã chốt cứng B3c/B4f — sửa lại đúng 6 chỗ (3 ở `soul_arts`, 1 ở `shintai` cũng agent khác dịch đúng nên không cần sửa).
2. `soul_arts`: agent viết "umbra" chữ thường trần ở dòng `SOUL_ARTS_PERFECT_EYE_OF_HEAVEN_PERK_EFFECT` thay vì giữ bracket `[umbra|E]` — mất 1 bracket, sửa lại.
3. `soul_arts`: agent dùng "Chí Nghiệp" thay "Lối Sống"/"Lối sống" cho "lifestyle" (lệch với toàn bộ 26 file khác của `lifestyles/` đều dùng "Lối sống") — sửa lại 2 chỗ. Cũng dịch "Righteousness" (tên khác của nhóm Art "Heavenly Arts" trong ngữ cảnh Kuei-Jin) thành "Chính Đạo" — dễ nhầm với "Righteousness"="Chính Nghĩa" đã chốt B3s (Path of Righteousness, ngữ cảnh Sabbat/religion khác hẳn) — sửa lại dùng "Thiên Nghệ" (tên hiển thị đã có của nhóm Art này trong cùng file) cho nhất quán nội bộ, tránh xung đột với B3s.
4. `investiture`: agent giữ nguyên tiếng Anh "Yama Kings" ở cả 7 lần xuất hiện `Glossary('Yama Kings','podgloss.yamaking')` (tham số 1) — SAI, phải dịch "Diêm Ma Vương" theo B3c đã chốt cứng (agent nhầm lẫn với vài thuật ngữ khác được phép giữ nguyên tham số 1 như Wan Kuei/Antediluvian). Cũng bỏ dịch 1 chỗ `Glossary('Dharma',...)`. Sửa lại cả 8 chỗ.
5. `lore`: agent quyết định giữ nguyên toàn bộ "Lore" — hợp lý (tên nhóm quyền năng riêng, tương tự Discipline/Gnosis) — nhưng áp dụng sai, giữ nguyên luôn CẢ CỤM "Lore of the World"/"Lore of Corruption"... (9 dòng `lore_of_*_visible`) thay vì chỉ giữ "Lore" và dịch phần "of X". Sửa lại thành "Lore của Thế Giới"/"Lore của Suy Đồi"/v.v — chỉ "Lore" giữ nguyên, phần sau dịch.

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Shintai of Ash and Fire / of Blood / of Bone / of Devotion / of Flesh / of Illusion / of Jade / of Poxes / of Storms / of Smoke *(10 tên Shintai cụ thể, Kuei-Jin)* | Shintai của Tro Tàn và Lửa / của Máu / của Xương / của Sự Sùng Kính / của Da Thịt / của Huyễn Ảnh / của Ngọc Bích / của Ôn Dịch / của Bão Tố / của Khói | đặt mới, giữ "Shintai" nguyên, dịch nghĩa phần "of X" |
| Godling(s) *(Kuei-Jin theo Dharma Sùng Kính/Devotion, WoD)* | Thần Linh | đặt mới |
| Asura | A-Tu-La | đặt mới, thuật ngữ Phật giáo/Hindu phổ biến tiếng Việt |
| Rakshasa *(khi là danh từ chung "the rakshasa can be...", KHÔNG phải tên riêng ghép như "Rakshasa Blade")* | Rakshasa *(giữ nguyên)* | ⚠️ **sửa lại theo tiền lệ B3c dòng ~1107 đã chốt giữ nguyên** — 1 agent (`shintai`) tự dịch "La Sát" không tra trước, đã sửa về giữ nguyên khi merge |
| Vicissitude (Discipline), Choleric/Melancholic/Phlegmatic/Sanguine (4 temperament heading) | giữ nguyên tiếng Anh | tái xác nhận B0/B4d/B4x |
| Fleshcrafting perk cụ thể (Malleable Visage→Dung Nhan Biến Ảo, Transmogrify the Mortal Clay→Biến Hóa Đất Sét Trần Tục, Rend the Osseous Frame→Xé Toạc Khung Xương, v.v — ~50 tên vị trí cơ thể) | đặt mới, dịch nghĩa trực tiếp, xem file `POD_discipline_lifestyle_l_english.yml` | giọng gothic, ví dụ đầy đủ trong git log commit đợt này |
| Lore *(tên nhóm quyền năng siêu nhiên demon "The Fallen"/"The Earthbound", 9 "Lore of X")* | Lore *(giữ nguyên tên nhóm)*, phần "of X" dịch nghĩa | đặt mới; ví dụ: "Lore of the World"→"Lore của Thế Giới", "Lore of Corruption"→"Lore của Suy Đồi", "Lore of the Herald"→"Lore của Sứ Giả", "Lore of the Life-Bringer"→"Lore của Người Mang Sự Sống", "Lore of Creation"→"Lore của Sáng Thế", "Lore of the Seer"→"Lore của Nhà Tiên Kiến", "Lore of Beauty"→"Lore của Vẻ Đẹp", "Lore of the Living"→"Lore của Kẻ Sống", "Lore of the Ethereal"→"Lore của Cõi Thanh Khí" |
| The Fallen *(danh xưng demon, khác `trait_fallen` thiên thần)* | Kẻ Sa Ngã | đặt mới, không mâu thuẫn B4h (`Fallen`=Sa Ngã cho thiên thần — cùng nghĩa gốc, ngữ cảnh khác splat) |
| The Earthbound *(demon cấp cao, WoD Demon: the Fallen)* | The Earthbound *(giữ nguyên)* | chưa có tiền lệ dịch trong base_game_vh, giữ nguyên an toàn |
| Investiture *(lifestyle Fera sa ngã hoàn toàn theo Wyrm)* | Sắc Phong | ✅ tái xác nhận tiền lệ đã có sẵn (`modifiers/POD_infernalism_modifiers_l_english.yml`, `interactions/POD_character_interactions_vampire_l_english.yml` — 6 chỗ đã dùng "Sắc Phong" từ trước) |
| Infernalist *(flavor label của trait `witch` trong ngữ cảnh POD, khác "Phù Thủy" vanilla)* | Tà Đạo Sĩ | đặt mới; "witch"="Phù Thủy" (vanilla) không khớp sắc thái giao kèo ma quỷ của POD nên đặt riêng |
| akuma *(thuộc hạ ma quỷ của Yama Kings/Diêm Ma Vương)* | akuma *(giữ nguyên)* | tái xác nhận tiền lệ đã dùng ở `decisions/POD_decisions_l_english.yml` |
| Planetary Gifts *(lifestyle Fera, Ân Huệ gắn Incarna hành tinh)* | Ân Huệ Chư Tinh | đặt mới |
| Eshtarra, Sokhta, Katankasonnak, Mitanu, Hakahe, Tambiyah, Nerigal, Turog, Zarok, Lubat, Ruatma, Shantar, Meros *(13 Incarna hành tinh, danh từ riêng WoD)* | giữ nguyên tiếng Anh | tên riêng, không dịch |
| Vulcan *(tên hành tinh giả thuyết cổ, `planetarygifts_hakahe_visible`)* | Vulcan *(giữ nguyên, KHÔNG thêm "Sao Hỏa")* | agent ban đầu dịch "Sao Hỏa Vulcan" — sai vì Vulcan là hành tinh giả thuyết riêng biệt (không phải Sao Hỏa/Hỏa Tinh), sửa lại khi merge |
| Auspice (tái xác nhận), Homid/Lupus/Ragabash/Theurge/Philodox/Galliard/Ahroun *(Tướng Trăng Garou)* | Tướng Trăng / giữ nguyên tiếng Anh | tái xác nhận B8-lifestyles-p1; 7 dòng comment `#Gifts: Homid` v.v giữ nguyên tiếng Anh (không phải chữ hiển thị) |
| Axis Mundi, Incarna *(nhắc lại, khái niệm Umbra/vũ trụ học Garou)* | giữ nguyên tiếng Anh | đặt mới, danh từ riêng huyền học không có tiền lệ dịch |
| Chi Arts *(lifestyle Kuei-Jin, tái xác nhận)* | Pháp Nghệ Khí | tái xác nhận B5-kuejin |
| Feng Shui, Tzu Wei, Kiai, Prana *(4 tên Art cụ thể của Chi Arts, nhóm liệt kê cùng nhau)* | giữ nguyên tiếng Anh | đặt mới; giữ nguyên nhất quán cả nhóm vì đều là tên riêng phương Đông, không dịch riêng "Feng Shui"="Phong Thủy" để tránh lệch tông với 3 tên còn lại |
| Obligation *(tên Art cụ thể Chi Arts)* | Nghĩa Vụ | đặt mới, dịch nghĩa |
| Tapestry *(tên Art cụ thể Chi Arts, liên quan vận số/định mệnh)* | Thiên Cơ | đặt mới, dịch nghĩa ẩn dụ "cơ trời/vận số" |
| Soul Arts *(lifestyle Kuei-Jin, tái xác nhận)* | Pháp Nghệ Linh Hồn | tái xác nhận B5-kuejin |
| Ghost Arts / Heavenly Arts / Beast Arts / Devil Arts / Dragon Tear / Hellweaving *(6 nhóm Art con của Soul Arts, tương ứng P'o/Hun)* | Quỷ Nghệ / Thiên Nghệ / Thú Nghệ / Ma Nghệ / Long Lệ / Địa Ngục Chức Pháp | đặt mới, Hán Việt nhất quán giọng huyền bí |
| Devil Soul, Suffering, Fetters, Gauntlet *(thuật ngữ hệ thống WoD trong `soul_arts`, chưa có bản dịch chốt)* | giữ nguyên tiếng Anh | đặt mới, tạm giữ nguyên tương tự P'o/Hun đến khi có tiền lệ dịch rõ hơn ở file khác |

## B8-lifestyles-p3. Thuật ngữ đợt nhỏ 3 việc #8 `lifestyles/` — 4 file 183-298 dòng (bastet, arcana, necro_magic, tribalgifts)

Nguồn: 4 file dịch qua agent song song. **3 lỗi thật phát hiện khi merge** (tiếp tục xác nhận bài học cũ — agent tự claim "không có tiền lệ" cho thuật ngữ THỰC RA đã chốt từ trước, coordinator phải tự grep xác nhận, không tin báo cáo):
1. `tribalgifts`: agent viết "Bane giữ nguyên tiếng Anh — không có tiền lệ dịch" — SAI, "Bane"="Tà Linh" đã chốt nhiều lần (B4c/B5j/B5-numina). Sửa lại 2 chỗ.
2. `arcana`: "True Name" (tham số 1 của `Glossary('True Name','podgloss.truename')` + 2 lần trong văn xuôi thường "true name") giữ nguyên tiếng Anh — SAI, phải dịch "Chân Danh" đã chốt B3c. Sửa lại cả 3 chỗ.
3. `necro_magic`: "Dark Kingdoms" dịch thành "Các Vương Quốc Bóng Tối" — thừa "Các" so với tiền lệ đã chốt "Vương Quốc Bóng Tối" (không thêm "Các" dù số nhiều, theo TRANSLATION_RULES §7). Sửa lại 2 chỗ. Cũng thiếu đúng 1 dòng cuối (dòng 213, gốc kết thúc bằng 1 space không newline) — khôi phục khi merge.
4. `arcana`: agent tự phát hiện và báo cáo (không cần coordinator sửa lỗi merge) — "Ravage" (tên perk gốc, dòng 44) để nguyên tiếng Anh trong khi "Ravage Sinner" (perk khác) dịch "Tàn Sát Kẻ Tội Lỗi" — không nhất quán. Coordinator dịch nghĩa "Ravage"→"Cưỡng Đoạt" (phù hợp nội dung effect: quỷ nuốt linh hồn thrall để lấy sức mạnh).

| English | Tiếng Việt chốt | Ghi chú |
|---|---|---|
| Bastet, Homid, Sokto, Crinos, Juddho *(dạng Breed/biến hình Bastet — Fera hình mèo)* | giữ nguyên tiếng Anh | đặt mới, danh từ riêng WoD |
| Bagheera, Bubasti, Khan, Simba, Swara, Ceilican *(6 bộ tộc Bastet)* | giữ nguyên tiếng Anh | đặt mới |
| Rahjah *(vị thần loài mèo Bastet)*, Unmaker *(thế lực phản-Gaia phía Bastet, tương tự Wyrm phía Garou)* | giữ nguyên tiếng Anh / "Kẻ Hủy Diệt" khi dùng như danh xưng mô tả trong văn xuôi | đặt mới |
| Arcana *(lifestyle Demon: the Fallen, tương tự cách xử lý "Lore")* | Arcana *(giữ nguyên tên hệ thống)* | đặt mới, nhất quán cách xử lý "Lore" |
| Torment *(chỉ số nội tâm Demon)* | Torment *(giữ nguyên)* | đặt mới, chưa có tiền lệ dịch |
| Elohim, Thrall, Yahweh, Metatron *(danh từ riêng thần học/WoD-Demon)* | giữ nguyên tiếng Anh | đặt mới |
| Scry *(tên perk Arcana, hành động bói toán/thấu thị)* | Chiêm Bốc | đặt mới, dịch nghĩa |
| Ravage *(tên perk Arcana, quỷ nuốt linh hồn thrall lấy sức mạnh)* | Cưỡng Đoạt | đặt mới, dịch nghĩa; sửa lại khi merge (agent để nguyên tiếng Anh, không nhất quán với "Ravage Sinner"→"Tàn Sát Kẻ Tội Lỗi") |
| Dark Kingdoms *(tham số 1 của Glossary, tái xác nhận)* | Vương Quốc Bóng Tối | tái xác nhận tiền lệ B4/dòng ~1928, KHÔNG thêm "Các" dù số nhiều |
| Necromancy *(lifestyle pháp sư phàm nhân điều khiển Wraith, khác Necro Psi của Numina)* | Chú Thuật Tử Linh | đặt mới; ghép "Chú Thuật" (đã dùng cho Blood Sorcery) + "Tử Linh" (đã dùng cho Necro Psi), giữ nhất quán gốc "necro-" |
| Fetter(s), Corpus, Skinlands, Spectre *(nhắc lại, thuật ngữ Wraith)* | giữ nguyên tiếng Anh | tái xác nhận B4h |
| Mortuus in Vultus, Algor Mortis, Calvaria Emissicius, Consilium Mortuus, Ammorsus Vicarius, Exedo Animus, Degulo, Ex Nihilo, Benedicto Mortem/Vitae, Rigor Mortis *(tên Latin các perk Necromancy)* | giữ nguyên tiếng Anh (tên riêng Latin, chỉ dịch phần mô tả xung quanh) | đặt mới |
| Tribal Gifts *(lifestyle Garou theo Bộ Tộc, tái xác nhận)* | Ân Huệ Bộ Tộc | tái xác nhận B8-lifestyles-p2 |
| Black Furies, Bone Gnawer(s), Children of Gaia, Fianna, Get of Fenris, Red Talon(s), Shadow Lord, Silent Strider, Silver Fang, Stargazer, Warder(s) of Men, Glass Walker, Black Spiral Dancer(s), White Howler, Hakken *(15 bộ tộc/nhóm Garou)* | giữ nguyên tiếng Anh | ✅ **quyết định coordinator: giữ nguyên toàn bộ tên bộ tộc Garou trong `lifestyles/`**, để nhất quán và tránh lặp lại xung đột đã ghi nhận giữa `religion/POD_religion_wyrm` (dịch nghĩa tên camp) và `religion/POD_religion_gaia` (giữ nguyên) — TERMINOLOGY.md chưa chốt quy tắc chung cho tên camp/tribe, việc rà soát toàn diện để lại sau |
| Maeljin Incarna *(thực thể Wyrm cấp cao)*, Muladhara/Manipura/Anahata/Visuddha/Atma *(5 chakra Stargazer)* | giữ nguyên tiếng Anh/Phạn ngữ | đặt mới |
| Bane *(linh hồn Wyrm-tainted, nhắc lại)* | Tà Linh | tái xác nhận B4c/B5j — agent ban đầu giữ nguyên sai, đã sửa khi merge |
