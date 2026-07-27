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
