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

## Cách thêm mục mới

Khi gặp thuật ngữ chưa có ở đây:

1. Tra `base_game_vh` bằng **key tiếng Anh** — nếu có, dùng đúng bản đó, thêm vào Phần A.
2. Nếu không có, tìm khái niệm vanilla tương đương về văn phong.
3. Nếu vẫn không, đặt từ mới theo giọng của `base_game_vh` → thêm vào Phần B **ngay lập tức**, kèm key nguồn.
4. Không bao giờ để một thuật ngữ có hai bản dịch trong repo.
