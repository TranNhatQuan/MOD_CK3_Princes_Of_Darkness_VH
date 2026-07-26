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

> **Trạng thái: chưa dịch dòng nào.** Toàn bộ 460 file POD vẫn là tiếng Anh. Bảng dưới là **đề xuất cần chốt**, không phải bản dịch đã tồn tại. Chốt xong thì xóa cột "Trạng thái" và coi như bắt buộc.

## B1. Nơi thuật ngữ POD thực sự được định nghĩa

Không đặt từ tùy tiện ở từng file. Ba nơi này là nguồn, dịch ở đây thì tự lan ra toàn mod:

| Nguồn | Điều khiển |
|---|---|
| [glossary_POD_l_english.yml](princesofdarkness/localization/english/glossary_POD_l_english.yml) | 28 shortcut `$pod_*$` / `$glossary_*$` (tham số 1 của `Glossary()` là chữ hiển thị) + 12 key `_tt` chứa nội dung tooltip, cũng phải dịch |
| [custom_localization/POD_misc_custom_loc_l_english.yml](princesofdarkness/localization/english/custom_localization/POD_misc_custom_loc_l_english.yml) | `POD_splat_*` — **không chứa chữ**, chỉ trỏ `[GetTrait('vampire').GetName(...)]` |
| [traits/](princesofdarkness/localization/english/traits/) | Tên thật của mọi splat. Dịch `trait_vampire` là đổi luôn mọi `$POD_splat_vampire$` |

→ Muốn đổi cách gọi "Vampire" toàn mod thì sửa `trait_vampire` trong `traits/`, **không** sửa `POD_splat_vampire`.

## B2. Thuật ngữ ma cà rồng (từ `glossary_POD_l_english.yml`)

| English | Đề xuất | Ghi chú |
|---|---|---|
| World of Darkness | Thế Giới Bóng Tối | `pod_wod` |
| Vampire | Ma cà rồng | `trait_vampire` |
| Cainite / Cainites | Hậu duệ Cain | `pod_cainite(s)` |
| Clan | Gia tộc ⚠️ **xung đột** | `pod_clan` — vanilla đã dùng "Gia tộc" cho *House*. Phải chọn từ khác, ví dụ **Thị tộc** |
| Clan Curse | Lời nguyền Thị tộc | `glossary_clan_curse` |
| Discipline / Disciplines | Dị năng | `pod_discipline(s)` |
| Vitae | Vitae *(giữ nguyên)* | `pod_vitae` — thuật ngữ Latin trong nguyên tác |
| Embrace / Embraced | Nghi lễ Trao truyền / được Trao truyền | `pod_Embrace(d)` |
| Diablerie | Diablerie *(giữ nguyên)* | `pod_diablerie` |
| Torpor | Miên trạng | `pod_torpor` |
| Kuei-Jin | Kuei-Jin *(giữ nguyên)* | `pod_kueijin` |
| Courts of Love | Tòa Ái Tình | `glossary_courts_of_love` |
| Osirian League | Liên minh Osiris | `glossary_osirian_league` |
| Khitta / Khittas | Khitta *(giữ nguyên)* | `glossary_khitta(s)` |

## B3. Thuật ngữ người sói / Fera (từ `glossary_POD_l_english.yml`)

| English | Đề xuất | Ghi chú |
|---|---|---|
| Fera | Fera *(giữ nguyên)* | `glossary_fera` |
| Triat | Tam Vị | `glossary_triat` |
| Wyld | Wyld *(giữ nguyên)* | `glossary_wyld` |
| Weaver | Weaver *(giữ nguyên)* | `glossary_weaver` |
| Wyrm | Wyrm *(giữ nguyên)* | `glossary_wyrm` |
| Triatic Wyrm | Wyrm Tam Vị | `glossary_wyrm_triatic` |
| Apep / Apophis | Apep / Apophis *(giữ nguyên)* | `glossary_wyrm_apep`, `_apophis` |
| Beast of War | Ác Thú Chiến Tranh | `glossary_wyrm_calamity` |
| Eater of Souls | Kẻ Nuốt Linh Hồn | `glossary_wyrm_consumption` |
| Defiler Wyrm | Wyrm Ô Uế | `glossary_wyrm_corruption` |

## B4. Splat (chủng loài) — nguồn: `traits/`

Danh sách đầy đủ lấy từ `POD_splat_*`:

`spirit`, `vampire`, `kueijin`, `werewolf`, `ajaba`, `entomos`, `apis`, `bastet`, `camazotz`, `corax`, `grondr`, `gurahl`, `kitsune`, `mokole`, `nagah`, `nuwisha`, `ratkin`, `rokea`, `fae`, `changeling`, `mage`, `mummy`, `demon`, `wraith`, `supehunter`, `revenant`, `ghoul`, `mortal`

| English | Đề xuất |
|---|---|
| Vampire | Ma cà rồng |
| Werewolf | Người sói |
| Mage | Pháp sư |
| Mummy | Xác ướp |
| Demon | Ác quỷ |
| Wraith | Oan hồn |
| Hunter | Thợ săn |
| Ghoul | Bộc huyết |
| Revenant | Huyết tộc Hồi sinh |
| Mortal | Phàm nhân |
| Spirit | Linh thể |
| Changeling | Đứa Trẻ Bị Tráo |
| Fae | Fae *(giữ nguyên)* |

Tên bộ tộc Fera (`bastet`, `corax`, `kitsune`, `mokole`, `nagah`, `nuwisha`, `ratkin`, `rokea`, `ajaba`, `apis`, `camazotz`, `entomos`, `grondr`, `gurahl`) là **danh từ riêng trong nguyên tác → giữ nguyên**, giống cách base giữ tên riêng vanilla.

## B5. Xung đột cần giải quyết trước khi dịch

| Từ POD | Vanilla đã chiếm | Hướng xử lý |
|---|---|---|
| **Clan** | `House` = "Gia tộc" | Clan → "Thị tộc" |
| **Discipline** | không xung đột | "Dị năng" |
| **Generation** | không xung đột | "Thế hệ" |
| **Beast** | không xung đột | "Dã Thú" |
| **Masquerade** | không xung đột | "Luật Che Giấu" |
| **Resonance** | không xung đột | "Cộng hưởng" |
| **Bloodline** | `Dynasty` = "Triều đại" | "Huyết thống" |
| **Prince** (chức sắc Camarilla) | `Duke/King` đã có | "Vương Đô" hoặc giữ "Prince" — cần chốt |

---

## Cách thêm mục mới

Khi gặp thuật ngữ chưa có ở đây:

1. Tra `base_game_vh` bằng **key tiếng Anh** — nếu có, dùng đúng bản đó, thêm vào Phần A.
2. Nếu không có, tìm khái niệm vanilla tương đương về văn phong.
3. Nếu vẫn không, đặt từ mới theo giọng của `base_game_vh` → thêm vào Phần B **ngay lập tức**, kèm key nguồn.
4. Không bao giờ để một thuật ngữ có hai bản dịch trong repo.
