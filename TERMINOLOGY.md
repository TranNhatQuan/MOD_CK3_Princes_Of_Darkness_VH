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

## B4q. Thuật ngữ `religion/POD_religion_modern_l_english.yml` — Anarch/Camarilla/Sabbat hiện đại, việc #2 file 30/36

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
