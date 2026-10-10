# Making grammar: the rules

Written out by `viewer/tools/grammar_rules.py` from the viewer's own data (`viewer/index.html`); edit the page's data, not this file. The landing page's Rules section shows the same rules as compact tables, with the detail folded.

Rules of the making grammar, written out from the viewer's own data: the interface forms (vocabulary), the rules that combine them into each joint's interfaces, the rules that size them, the rules that link them to assembly, repair and fabrication, and one joint derived by applying them. Nothing here is added to the data the joint pages use. Each rule has an ID, one letter for its kind (C combination; S sizing, per form and per joint; P process, P1 to P30; G general; J joint-level, for the joint as a whole; X context, once the joint is in a building; M machining, the cutter for a CNC pass), so that the derivation can name the rule behind each step. Outcomes have two letters, so they never clash with a rule: AS assembly, DS disassembly, RP repair, HF hand fabrication, DF digital fabrication; every derived or predicted link gives its outcome and its rule, as in “Cross-cutting (HF3), rule P17, predicted”. Bauer and Pauli's step labels are kept as printed, as “Bauer A1”. Each sizing rule keeps its source and evidence label; where sources disagree, each rule is listed with its own source. Inferred rules are marked.

| Rules | Number | Of which inferred |
|---|---|---|
| Combination (C.): interfaces of the five joints | 15 | — (10 hold only with an option or variant) |
| Sizing per form (S.), from the sources | 66 | 1 |
| Sizing per joint (S.), scales | 44 | 7 |
| Sizing per joint (S.), fixed size | 57 | 4 |
| Sizing per joint (S.), partly scales | 5 | 3 |
| Process (P1–P30): rules from a form's geometry | 30 | — |
| Links they give, assembly | 31 | 16 predicted |
| Links they give, disassembly | 5 | 2 predicted |
| Links they give, repair | 25 | 23 predicted |
| Links they give, hand fabrication (手刻み) | 89 | 70 predicted |
| Links they give, digital fabrication (CNC / プレカット) | 64 | 50 predicted |
| General (G) | 4 | — |
| Joint-level (J) | 2 | — |
| Context (X) | 4 | — |
| Machining (M) | 1 | — |

## 1. Vocabulary

The 23 interface forms. Where both halves of a mating pair (凸 projecting, 凹 receiving) have names, both are given; the pair is one interface form. Main function after Chaya et al. (1985): bears, interlocks, locks.

| Code | Group | Interface form | Kanji | Romanisation | Main function |
|---|---|---|---|---|---|
| BF1 | Bearing faces | Butt face | 突き付け | *tsukitsuke* | bears |
| BF2 | Bearing faces | Oblique scarf | 殺ぎ | *sogi* | bears |
| BF3 | Bearing faces | Halving (half-lap) | 相欠き | *aikaki* | bears |
| BF4 | Bearing faces | Seat | 腰掛け | *koshikake* | bears |
| BF5 | Bearing faces | Mitre | 留め | *tome* | bears |
| HN1 | Housings and notches | Notch | 欠き込み | *kakikomi* | bears |
| HN2 | Housings and notches | Housing | 大入れ | *ōire* | bears |
| HN3 | Housings and notches | Open slot mortise | 輪薙ぎ込み | *wanagikomi* | bears |
| HN4 | Housings and notches | Cog | 渡り腮 | *watari ago* | bears |
| HN5 | Housings and notches | Through mortise | 貫通し | *nuki tōshi* | bears |
| HN6 | Housings and notches | Box housing | 箱 | *hako* | bears |
| ST1 | Steps and tongues | Abbreviated gooseneck | 略鎌 | *ryakukama* | interlocks |
| ST2 | Steps and tongues | Stub tenon / stub mortise | 目違い / 目違ほぞ穴 | *mechigai / mechigai hozo-ana* | bears |
| ST3 | Steps and tongues | Collar (term unverified) | 襟輪 | *eriwa* | bears |
| TB1 | Tenons and bridles | Tenon / mortise | 枘 / 枘穴 | *hozo / hozo-ana* | bears |
| TB2 | Tenons and bridles | Rod tenon, keyed | 竿 | *sao* | interlocks |
| TB3 | Tenons and bridles | Bridle | 三枚組 | *sanmai gumi* | bears |
| IH1 | Interlocking heads | Gooseneck / gooseneck socket | 鎌 / 鎌穴 | *kama / kama-ana* | interlocks; 凹 term unverified |
| IH2 | Interlocking heads | Dovetail / dovetail socket | 蟻 / 蟻ほぞ穴 | *ari / arihozo-ana* | interlocks |
| AP1 | Added pieces and locks | Loose tenon (dowel, butterfly key; term unverified for yatoi) | 雇い | *yatoi* | interlocks |
| AP2 | Added pieces and locks | Peg / peg hole | 栓 / 栓穴 | *sen / sen-ana* | locks; 凹 term unverified |
| AP3 | Added pieces and locks | Key | 車知 | *shachi* | locks |
| AP4 | Added pieces and locks | Wedge | 楔 | *kusabi* | locks |

## 2. Combination rules

Which interface forms make each interface of each joint. ×2: the form occurs twice (at each tip, on each toe). A rule with an option or variant holds only with it; one without holds in every configuration the viewer models.

| ID | Joint | Interface | = interface forms | Holds |
|---|---|---|---|---|
| `C.daimochi.1` | 台持継 *daimochi tsugi* | Beam–beam interface (lower and upper element) | Oblique scarf 殺ぎ + Abbreviated gooseneck 略鎌 + Stub tenon / stub mortise 目違い / 目違ほぞ穴 ×2 | every configuration |
| `C.daimochi.2` |  | Dowel–element interfaces (two dowels, each in both elements) | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | locking: dowels (blind, set in before the upper element) |
| `C.daimochi.3` |  | Peg–element interfaces (two draw pegs, each through both elements) | Peg / peg hole 栓 / 栓穴 | locking: through draw pegs |
| `C.daimochi.4` |  | Post–element interface (a post below, or a post above) | Tenon / mortise 枘 / 枘穴 + Housing 大入れ | support: post below (tenon through both elements, or a stub) or post above (a stub into the upper element) |
| `C.daimochi.5` |  | Beam–element interface (a beam below) | Cog 渡り腮 | support: beam below |
| `C.daimochi.6` |  | Wedge–tenon interfaces (two wedges beside the post tenon) | Wedge 楔 | locking: wedges, with a post below and a through tenon only |
| `C.aritsugi.1` | 腰掛蟻継 *koshikake ari tsugi* | Beam–beam interface | Seat 腰掛け + Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | every configuration |
| `C.aritsugi.2` |  | Beam–beam interface, 目違い variant | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | variant: 目違い付 (size assumed) |
| `C.kamatsugi.1` | 腰掛鎌継 *koshikake kama tsugi* | Beam–beam interface | Seat 腰掛け + Gooseneck / gooseneck socket 鎌 / 鎌穴 | every configuration |
| `C.kamatsugi.2` |  | Beam–beam interface, 目違い variant | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | variant: Toda's 目違い notch |
| `C.kamatsugi.3` |  | Peg–element interfaces (one peg through both elements) | Peg / peg hole 栓 / 栓穴 | variant: Toda's 込栓, driven sideways |
| `C.kanawa.1` | 金輪継 *kanawa tsugi* | Beam–beam interface | Oblique scarf 殺ぎ + Abbreviated gooseneck 略鎌 + Stub tenon / stub mortise 目違い / 目違ほぞ穴 ×2 | every configuration |
| `C.kanawa.2` |  | Peg–element interfaces (one peg in the 腮, between both elements, from the side) | Peg / peg hole 栓 / 栓穴 | variant: locked |
| `C.okkake.1` | 追掛大栓継 *okkake daisen tsugi* | Beam–beam interface | Oblique scarf 殺ぎ + Abbreviated gooseneck 略鎌 + Stub tenon / stub mortise 目違い / 目違ほぞ穴 ×2 | every configuration |
| `C.okkake.2` |  | Peg–element interfaces (two pegs through both elements, across the width from the side faces) | Peg / peg hole 栓 / 栓穴 | variant: locked |

**Components of each joint**

台持継 *daimochi tsugi*: Lower element (shitaki) and upper element (uwaki), the same part turned end for end. By option: two dowels, two draw pegs, two bolts or two wedges; a post below, a post above or a beam below. Bolts (a locking option for logs) are hardware, not an interface form of the vocabulary.

腰掛蟻継 *koshikake ari tsugi*: Lower element (shitaki) and upper element (uwaki).

腰掛鎌継 *koshikake kama tsugi*: Lower element (shitaki) and upper element (uwaki); by variant, one 込栓 peg.

金輪継 *kanawa tsugi*: Two identical elements; in the locked variant, one 栓 peg.

追掛大栓継 *okkake daisen tsugi*: Two identical elements; in the locked variant, two 込栓 pegs.

## 3. Sizing rules

Rule types: *scales* (the form's dimensions follow the member by rule); *fixed size* (a set size, usually a tool or 寸 standard); *partly scales* (some dimensions scale, others are fixed or capped); *not restricted (follows the member)* (the form has no sizing rule of its own; its size is set by the members it joins); *no rule found* (no sizing rule found in the sources checked; one may exist). Evidence: *documented* (from a primary source (e.g. Saitō 1904, denmoku-db, AIJ)); *secondary* (from commentary or later sources); *generic* (Western or general woodworking convention, not a Japanese timber-frame rule); *inferred* (a proxy or ratio derived by us); *verify* (read only from a snippet; to be checked against the original); *geometry* (follows from the geometry).

| ID | Interface form | Sizing | Rules from sources | Evidence | Per-joint dimensions |
|---|---|---|---|---|---|
| `S.tsuki` | Butt face 突き付け | not restricted (follows the member) | 2 | documented 2, verify 1 | — |
| `S.sogi` | Oblique scarf 殺ぎ | scales | 4 | documented 3, measured from 第廿圖 (not dimensioned on the plate) 1 | `S.daimochi.r`, `S.daimochi.t`, `S.kanawa.L`, `S.kanawa.slope`, `S.okkake.L`, `S.okkake.slope` |
| `S.aikaki` | Halving (half-lap) 相欠き | no rule found | 0 | — | — |
| `S.koshi` | Seat 腰掛け | fixed size | 1 | secondary 1 | `S.aritsugi.sd`, `S.aritsugi.s`, `S.kamatsugi.s` |
| `S.tome` | Mitre 留め | not restricted (follows the member) | 2 | geometry 1, documented 1 | — |
| `S.kaki` | Notch 欠き込み | partly scales | 3 | documented 3 | — |
| `S.oire` | Housing 大入れ | partly scales | 3 | documented 2, verify 1, secondary 1 | `S.daimochi.sd` |
| `S.wanagi` | Open slot mortise 輪薙ぎ込み | partly scales | 2 | documented 2 | — |
| `S.ago` | Cog 渡り腮 | fixed size | 1 | documented 1 | `S.daimochi.cd`, `S.daimochi.cw` |
| `S.nuki` | Through mortise 貫通し | partly scales | 4 | documented 3, secondary 1 | — |
| `S.hako` | Box housing 箱 | no rule found | 0 | — | — |
| `S.ryaku` | Abbreviated gooseneck 略鎌 | partly scales | 9 | documented 8, secondary 1 | `S.daimochi.j`, `S.daimochi.jr`, `S.okkake.c` |
| `S.mechi` | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | partly scales | 4 | documented 4 | `S.daimochi.ml`, `S.daimochi.mw`, `S.kanawa.m`, `S.kanawa.mw`, `S.okkake.m` |
| `S.eri` | Collar (term unverified) 襟輪 | partly scales | 1 | documented 1 | — |
| `S.hozo` | Tenon / mortise 枘 / 枘穴 | fixed size | 3 | documented 3, verify 1 | `S.daimochi.tw`, `S.daimochi.td`, `S.daimochi.tl` |
| `S.sao` | Rod tenon, keyed 竿 | fixed size | 2 | documented 1, inferred 1 | — |
| `S.sanmai` | Bridle 三枚組 | partly scales | 1 | generic 1 | — |
| `S.kama` | Gooseneck / gooseneck socket 鎌 / 鎌穴 | partly scales | 6 | documented 6 | `S.kamatsugi.L`, `S.kamatsugi.hl`, `S.kamatsugi.b`, `S.kamatsugi.e`, `S.kamatsugi.d`, `S.kamatsugi.k` |
| `S.ari` | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | partly scales | 3 | documented 3 | `S.aritsugi.A`, `S.aritsugi.e`, `S.aritsugi.n` |
| `S.yatoi` | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | fixed size | 3 | documented 3 | `S.daimochi.p`, `S.daimochi.pl` |
| `S.sen` | Peg / peg hole 栓 / 栓穴 | partly scales | 11 | documented 8, secondary 3, conflict 2 | `S.kanawa.pg`, `S.okkake.peg` |
| `S.shachi` | Key 車知 | no rule found | 0 | — | — |
| `S.kusabi` | Wedge 楔 | fixed size | 1 | documented 1 | — |

**Sizing per form (S.): every rule with its source and evidence; a rule names its joint where the source does, and a two-halved form's rules sit under the half they describe**

**`S.tsuki`** Butt face 突き付け: not restricted (follows the member).

- Shoulder (胴付き dōzuki) set 5分 (c. 15 mm) into the receiving member (rafter beam into post) (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]
- Hanging post: shoulder about 1寸 (c. 30 mm) below the beam soffit, with 1寸 clearance (Saitō 1904, 日本家屋構造, via Shimoyama) [documented, verify]
- *Note:* A plain contact face; its size is the section of the members joined.

**`S.sogi`** Oblique scarf 殺ぎ: scales.

- Daimochi: joint length about 2.5 × depth H (Saitō 1904, 日本家屋構造) [documented]
- Daimochi: joint length 2 × H (AIJ 2009 via denmoku-db) [documented]
- Kanawa: the lap centred at half the section across it (denmoku-db kanawa bending specimens) [documented]
- Kanawa: すべり勾配 about 1/24 either side of the 腮 (Saitō 1904, 日本家屋構造, 第廿圖) [measured from 第廿圖 (not dimensioned on the plate)]

**`S.aikaki`** Halving (half-lap) 相欠き: no rule found.

- No rule found in the sources checked.

**`S.koshi`** Seat 腰掛け: fixed size.

- Seat depth 15 mm (5分) (diy-ie, after 大工作業の実技) [secondary]

**`S.tome`** Mitre 留め: not restricted (follows the member).

- Angle 45° (geometry) [geometry]
- Mitre face follows the members, e.g. nageshi 8–9/10 of the post width (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]
- *Note:* Its size is set by the members joined.

**`S.kaki`** Notch 欠き込み: partly scales.

- Notch depth about 5分 (c. 15 mm); length = post width − 1寸 (gate arm through post) (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]
- Eaves beam seated 1–1.5寸 (30–45 mm) on the tie beam (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]
- Cross-halving: depth H/2 (a different case: roof example) (denmoku-db) [documented]

**`S.oire`** Housing 大入れ: partly scales.

- Depth about 1/8 of the post width (beam into through-post, kōnosu) (Saitō 1904, 日本家屋構造, via Shimoyama) [documented, verify]
- Depth 3–4分 (9–12 mm) for secondary members (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]
- Modern standard 15 mm; range 6–15 mm (municipal standard drawings) [secondary]

**`S.wanagi`** Open slot mortise 輪薙ぎ込み: partly scales.

- Slot width = width of the received member (e.g. ridge beam); housing depth about 2分 (c. 6 mm); tenon split-wedged (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]
- Tenon thickness follows the mortise and tenon rule (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]

**`S.ago`** Cog 渡り腮: fixed size.

- Cog where a plate sits on a beam: 1寸 to 1寸5分 (30 to 45 mm) (Saitō 1904, 日本家屋構造) [documented]

**`S.nuki`** Through mortise 貫通し: partly scales.

- Abbreviated gooseneck in a through tie: hook longer than 30 mm, tip 30 mm high, 45° (denmoku-db No. 106) [documented]
- Hook height 1/3 to 2/3 of hook length; wedge allowance 15 mm (denmoku-db No. 106) [documented]
- Nuki about 1/4 of the post width thick (Shimoyama) [secondary]
- Tested 15–60 mm thick in 105–180 mm posts (denmoku-db) [documented]

**`S.hako`** Box housing 箱: no rule found.

- *Note:* No rule found. Proxy: as stub tenon, W/8 to W/7 (inferred).

**`S.ryaku`** Abbreviated gooseneck 略鎌: partly scales.

- Kanawa and okkake: joint length 3 to 3.5 × H (Saitō 1904, 日本家屋構造) [documented]
- Kanawa: the 腮 jogs back against the slope at the centre, as deep as the 栓 (1/8 of the section across the lap) (Saitō 1904, 日本家屋構造, 第廿圖; denmoku-db) [documented]
- Kanawa: 2 to 3 × width W; okkake: 2 to 3 × H (AIJ 2009 via denmoku-db) [documented]
- Okkake: at least 8寸 (240 mm) (Shimoyama) [secondary]
- Daimochi: step H/10, tip H/4 (denmoku-db) [documented]
- Daimochi: step 8分 to 1寸 (24 to 30 mm) (Saitō 1904, 日本家屋構造) [documented]
- Jaw (腮): 15 mm, or L/15 to L/20, never above 15 to 30 mm (denmoku-db) [documented]
- Okkake: the central step (腮), width 15–30 mm (5分 to 1寸) (denmoku-db) [documented]
- Tapered mating faces (suberi kōbai) about 1/10 (Saitō 1904, 日本家屋構造; glossaries) [documented]

**`S.mechi`** Stub tenon / stub mortise 目違い / 目違ほぞ穴: partly scales.

- 凸 stub tenon: Kanawa and okkake: a square of W/8 to W/7 (Saitō 1904, 日本家屋構造) [documented]
- Both halves: Depth 15 mm (AIJ 2009 via denmoku-db) [documented]
- 凸 stub tenon: Daimochi: about W/4 square (Saitō 1904, 日本家屋構造) [documented]
- 凸 stub tenon: Okkake tongue width W/4 to W/3 (denmoku-db) [documented]

**`S.eri`** Collar (term unverified) 襟輪: partly scales.

- Collar cut-out width = width of the post it meets (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]
- *Note:* Depth: no rule found.

**`S.hozo`** Tenon / mortise 枘 / 枘穴: fixed size.

- 凸 tenon: Long tenon in a 120 mm post: 90 × 30 × 117 mm (denmoku-db specimen) [documented]
- 凸 tenon: A 45 mm tenon is about 50% stiffer and stronger than a 30 mm one (Irie and Oto, AIJ 2009) [documented]
- 凸 tenon: Tenon thickness 1/4 to 2/7 of the post width; width 8/10 to 8.5/10 (Saitō 1904, 日本家屋構造, via Shimoyama) [documented, verify]

**`S.sao`** Rod tenon, keyed 竿: fixed size.

- Long tenon with keys at W = 120: tenon 30, jaw 7.5, 18 mm, length 240 (Urakubo et al., AIJ 2024 (one size tested)) [documented]
- Tested D = 30, key 15 at W = 120, i.e. about W/4 and W/16 (AIJ 2024; MLIT 2021) [inferred]

**`S.sanmai`** Bridle 三枚組: partly scales.

- Each part one third of the member width (general woodworking) [generic]

**`S.kama`** Gooseneck / gooseneck socket 鎌 / 鎌穴: partly scales.

- 凸 gooseneck: Gooseneck length 4寸, 5寸 or 6寸 (120, 150, 180 mm), whatever the depth (Araki; denmoku-db) [documented]
- 凸 gooseneck: Head = neck = half the gooseneck length (Kijima and Kumazawa 2019) [documented]
- Both halves: Gooseneck depth H/2 (Kijima and Kumazawa 2019) [documented]
- 凸 gooseneck: Neck width 30 mm (1寸) in every specimen (denmoku-db) [documented]
- 凸 gooseneck: Jaw 7.5 mm each side (5 to 15 tested); head width = neck + 2 × jaw (denmoku-db; Toda 2012) [documented]
- Both halves: Tapered mating faces (suberi kōbai) about 1/10 of the depth (1/8 also used) (Saitō 1904, 日本家屋構造; Kijima) [documented]

**`S.ari`** Dovetail / dovetail socket 蟻 / 蟻ほぞ穴: partly scales.

- 凸 dovetail: Neck W/4 to W/3; length W/4 to W/2, design shear length at most 25 mm (denmoku-db) [documented]
- 凸 dovetail: Flare L/8 to L/16 (denmoku-db) [documented]
- Both halves: All parts as ratios of the top width (Saitō 1904, 日本家屋構造) [documented]

**`S.yatoi`** Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: fixed size.

- Daimochi dowels: 1寸2分 square × 1寸5分 (about 36 × 45 mm) (Saitō 1904, 日本家屋構造) [documented]
- Daimochi dowel 30 × 30 mm (denmoku-db) [documented]
- Dowel 太枘: 1寸–1寸4分 square × 2.5–3分 thick, hardwood (Saitō 1904, 日本家屋構造, via Shimoyama) [documented]

**`S.sen`** Peg / peg hole 栓 / 栓穴: partly scales.

- 凸 peg: Kanawa: central peg = stub tenon = W/8 to W/7 square (Saitō 1904, 日本家屋構造) [documented]
- 凸 peg: Pegs W/8 to W/6 (AIJ 2009 via denmoku-db) [documented]
- 凸 peg: Trade sizes 5分, 6分, 8分, 1寸 (15, 18, 25, 31 mm) (pin catalogues) [secondary]
- Both halves: Okkake: 2 pegs at the quarter points; 4 if H > 300 mm (denmoku-db; Saitō 1904, 日本家屋構造) [documented]
- 凸 peg: Daimochi peg length: 2/3 H in the text, H/2 + 30 in the specimen table (denmoku-db (inconsistent)) [documented]
- 凹 peg hole: Drawbore: peg holes deliberately offset about 2 mm (Kyoto training college) [secondary]
- 凸 peg: Kanawa 栓 at least 15 mm thick (AIJ 2009 via denmoku-db) [documented]
- 凸 peg: Kanawa: tested 栓 15 mm wide (Toda 2012) [documented]
- 凸 peg: Kanawa 栓 tapered, for example 21 to 30 mm (builder (Matsumoto Kensetsu)) [secondary]
- 凸 peg: Kanawa: 栓 W/8 thick along the beam (15 mm at W = 120) and as deep as the 腮 it fills, 15, 30 or 45 mm (W/8 to 3W/8), through the depth; tested (denmoku-db 金輪継ぎ (曲げ) No. 22–26, after 河原・青木・稲山 2016) [documented, conflict]
- 凸 peg: Kanawa: the 栓 a square of 1/8 of the section dimension across the lap, in the 腮 at the centre (H/8 in this model) (Saitō 1904, 日本家屋構造, 第廿圖) [documented, conflict]

**`S.shachi`** Key 車知: no rule found.

- *Note:* No size rule found. Urakubo et al. (AIJ 2024) tested one long tenon with keys at W = 120 (see Rod tenon, keyed); the key and key-slot sizes they report have not been read here. The kanawa tsugi's lock is modelled as a 栓, so its key rules are under Peg / peg hole.

**`S.kusabi`** Wedge 楔: fixed size.

- Wedge allowance 15 mm (denmoku-db No. 106) [documented]

**Sizing per joint (S.): each joint's rule library, every alternative with its source**

Each joint's rule library, as its Proportions panel uses it: for each dimension, the interface form it sizes, then every rule offered, with its type, value, source and evidence; the first is the one the page starts from. Evidence is assigned from each rule's own source note by a fixed rule: a placeholder is *inferred*; a rule of thumb is *generic*; a rule the note calls inferred or unverified is *inferred*; one read from a snippet is *verify*; one read through a paraphrase or commentary is *secondary*; one naming a primary source (denmoku-db, Saitō 1904, AIJ, Toda, HOWTEC, MLIT, Kijima, the dimensioned drawings, Wang) is *documented*; any other is *secondary*. Section dimensions (height, width) are the member's, not rules.

**台持継 *daimochi tsugi***

| ID | Dimension | Interface form | Rule | Type | Source | Evidence |
|---|---|---|---|---|---|---|
| `S.daimochi.r` | Joint length (scarf overlap) | Oblique scarf 殺ぎ | 2 H (denmoku) | scales | DM1 (documented across three sizes) | documented |
|  |  |  | 2 1/2 H (Meiji rule) | scales | NK1904 (single source, read through a paraphrase) | secondary |
|  |  |  | 3 H (project specimen) | scales | WA (one specimen, rule unverified) | inferred |
| `S.daimochi.t` | Tip land | Oblique scarf 殺ぎ | 1/4 H (denmoku) | scales | DM1 (documented across three sizes) | documented |
|  |  |  | ≈ 1/7 H (project specimen) | scales | WA (one specimen, rule unverified) | inferred |
| `S.daimochi.j` | Mid-scarf step height | Abbreviated gooseneck 略鎌 | 1/10 H (denmoku) | scales | DM1 (documented across three sizes) | documented |
|  |  |  | 9分 (Meiji rule: 8分 to 1寸) | fixed size | NK1904 (single source, absolute) | documented |
|  |  |  | 1/10 H, kept within 8分 to 1寸 | partly scales | inferred (inferred reconciliation of the two sources) | inferred |
|  |  |  | 3/10 H (project specimen) | scales | WA (one specimen, rule unverified) | inferred |
| `S.daimochi.jr` | Mid-scarf step run | Abbreviated gooseneck 略鎌 | 3/10 H (project specimen) | scales | WA (one specimen, rule unverified) | inferred |
|  |  |  | 0 (vertical step) | fixed size | DM1 (as drawn in denmoku) | documented |
| `S.daimochi.ml` | Mechigai tongue length | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | scales | NK1904 (single source, read through a paraphrase) | secondary |
|  |  |  | ≈ 1/7 W (project specimen) | scales | WA (one specimen, rule unverified) | inferred |
|  |  |  | no tongue | fixed size | DM1 (not drawn in denmoku) | documented |
| `S.daimochi.mw` | Mechigai tongue width | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | scales | NK1904 (single source, read through a paraphrase) | secondary |
|  |  |  | ≈ 2/7 W (project specimen) | scales | WA (one specimen, rule unverified) | inferred |
| `S.daimochi.p` | Dowel size | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 30 mm, about 1寸 (denmoku) | fixed size | DM1 (documented constant across three sizes) | documented |
|  |  |  | 1寸2分 (Meiji rule) | fixed size | NK1904 (single source) | documented |
|  |  |  | 5分 (Fig. 3.2) | fixed size | WA Fig. 3.2 (single drawing) | documented |
|  |  |  | 1 in (project specimen) | fixed size | WA (one specimen) | documented |
|  |  |  | 1寸 (Saitō 1904, lower) | fixed size | Saitō 1904 (1寸–1寸4分 square × 2.5–3分 thick, hardwood) | documented |
|  |  |  | 1寸4分 (Saitō 1904, upper) | fixed size | Saitō 1904 (1寸–1寸4分 square × 2.5–3分 thick, hardwood) | documented |
| `S.daimochi.pl` | Dowel length | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 1/2 H + 30 mm (fits the denmoku table) | partly scales | DM1 (fits three sizes exactly; inferred, not stated) | inferred |
|  |  |  | 2/3 H (denmoku text) | scales | DM1 (stated, but contradicts the table) | documented |
|  |  |  | 1寸5分 (Meiji rule) | fixed size | NK1904 (single source) | documented |
|  |  |  | 1寸 (Fig. 3.2) | fixed size | WA Fig. 3.2 (single drawing) | documented |
|  |  |  | 2.5 in (project specimen) | fixed size | WA (one specimen) | documented |
| `S.daimochi.sd` | Seat housing depth | Housing 大入れ | placeholder, held absolute | fixed size | none (no evidence for a post seat) | inferred |
|  |  |  | 1寸 (Meiji: 渡り欠き of a 軒桁 on a beam) | fixed size | NK1904 (single Meiji source, neighbouring joint, read through a paraphrase) | secondary |
|  |  |  | 1寸5分 (Meiji, upper value) | fixed size | NK1904 (single Meiji source, neighbouring joint, read through a paraphrase) | secondary |
|  |  |  | 0, shoulder bears flat | fixed size | inferred (no housing; usual for a post shoulder (dōzuki), inferred) | inferred |
| `S.daimochi.cd` | Cog depth (beam below) | Cog 渡り腮 | 1/10 H (inferred from the daimochi step) | scales | inferred (inferred from a neighbouring rule; 渡り腮 tables not yet read) | inferred |
|  |  |  | placeholder, held absolute | fixed size | none (no evidence) | inferred |
| `S.daimochi.cw` | Cog width (beam below) | Cog 渡り腮 | 5分 (okkake daisen 腮幅, lower value) | fixed size | DM2 (neighbouring joint, single source) | documented |
|  |  |  | 1寸 (okkake daisen 腮幅, upper value) | fixed size | DM2 (neighbouring joint, single source) | documented |
| `S.daimochi.tw` | Post tenon thickness (along the beam) | Tenon / mortise 枘 / 枘穴, 凸 | 30 mm, about 1寸 | fixed size | HOWTEC; MLIT 2023; DM roof (documented across sizes: precut practice, HOWTEC test standard, denmoku roof frame) | documented |
|  |  |  | 45 mm (stiffer variant) | fixed size | AIJ T&D 15(29) (tested variant, single source) | documented |
|  |  |  | 1/4 of the post width (Saitō 1904) | scales | Saitō 1904 (tenon thickness 1/4 to 2/7 of the post width; read only from a snippet, verify) | verify |
|  |  |  | 2/7 of the post width (Saitō 1904) | scales | Saitō 1904 (tenon thickness 1/4 to 2/7 of the post width; read only from a snippet, verify) | verify |
| `S.daimochi.td` | Post tenon width (across the beam) | Tenon / mortise 枘 / 枘穴, 凸 | W − 20 mm | partly scales | HOWTEC; MLIT 2023; 富田 1999 (documented across sizes: 85 to 88 mm on 105 mm posts, 105 mm on 120 mm posts) | documented |
|  |  |  | 90 mm (koyatsuka, denmoku roof frame) | fixed size | DM roof (single source) | documented |
|  |  |  | 8/10 of the post width (Saitō 1904) | scales | Saitō 1904 (tenon width 8/10 to 8.5/10 of the post width; read only from a snippet, verify) | verify |
|  |  |  | 8.5/10 of the post width (Saitō 1904) | scales | Saitō 1904 (tenon width 8/10 to 8.5/10 of the post width; read only from a snippet, verify) | verify |
| `S.daimochi.tl` | Stub tenon length | Tenon / mortise 枘 / 枘穴, 凸 | 50 mm (短ほぞ, standard) | fixed size | HOWTEC; MLIT 2023 (documented: HOWTEC test standard and precut practice) | documented |
|  |  |  | 45 mm | fixed size | 富田 1999 (single source) | documented |
|  |  |  | 1寸 (older hand practice) | fixed size | Shimoyama (single source, modern commentary) | secondary |
|  |  |  | 3寸, 90 mm (長ほぞ) | fixed size | Shimoyama (single source) | secondary |
|  |  |  | 120 mm (koyatsuka 長ほぞ, denmoku roof frame) | fixed size | DM roof (single source) | documented |

**腰掛蟻継 *koshikake ari tsugi***

| ID | Dimension | Interface form | Rule | Type | Source | Evidence |
|---|---|---|---|---|---|---|
| `S.aritsugi.A` | Dovetail length 蟻 (shoulder to tip) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴, 凸 | 0.45 W | scales | 105 craft proportions (one carpenter video); denmoku-db (the 105 craft proportions is about 50 (0.48 W); 0.45 W keeps under the 0.55 W cap at every size) | documented |
|  |  |  | W/2 | scales | 105 craft proportions (one carpenter video) (rule of thumb, close to the 105 proportions' 50) | generic |
| `S.aritsugi.e` | Flare e, each side (蟻勾配) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴, 凸 | 1:5 of the dovetail length | scales | 105 craft proportions (one carpenter video) (蟻勾配 1:5; in the 105 proportions (50 long) it gives the 50 head over a 30 neck) | secondary |
|  |  |  | 1:4 of the dovetail length | scales | craft sources (a steeper 蟻勾配) | secondary |
|  |  |  | 7.5 mm, 曲尺幅半分 | fixed size | denmoku 蟻掛け (half the 15 mm width of the carpenter's square (曲尺), set out with the square itself) | documented |
| `S.aritsugi.n` | Neck width 蟻首 | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴, 凸 | 30 mm (1寸) | fixed size | 105 craft proportions; Koshikake-aritsugi.pdf; denmoku-db (held near 30 on both 105 and 120 stock) | documented |
|  |  |  | W/4 | scales | craft rule of thumb (proportional alternative) | generic |
|  |  |  | W/3 | scales | craft rule of thumb (proportional alternative) | generic |
| `S.aritsugi.sd` | Seat depth 腰掛 (locked to H) | Seat 腰掛け | H/2 | scales | craft sources; src/cad.py (locked: the halves meet at mid-height) | secondary |
| `S.aritsugi.s` | Seat length 腰掛 | Seat 腰掛け | 15 mm (5分) | fixed size | 腰掛鎌継 (diy-ie); Koshikake-aritsugi.pdf (not stated for the 蟻 in the sources compiled: taken from the sibling 鎌's seat. The Koshikake-aritsugi.pdf drawing does label a 15 seat) | documented |
|  |  |  | 30 mm (1寸) | fixed size | inferred (a longer seat; inferred, not documented for the 蟻) | inferred |

**腰掛鎌継 *koshikake kama tsugi***

| ID | Dimension | Interface form | Rule | Type | Source | Evidence |
|---|---|---|---|---|---|---|
| `S.kamatsugi.L` | 鎌 length (head + neck) | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 5寸 (150 mm) | fixed size | denmoku-db; Araki; Instructables (documented size, the common one) | documented |
|  |  |  | 4寸 (120 mm) | fixed size | denmoku-db; Araki; Instructables (documented size; also the stated minimum) | documented |
|  |  |  | 6寸 (180 mm) | fixed size | denmoku-db; Araki; Instructables (documented size) | documented |
|  |  |  | 1 1/2 W | scales | Instructables (rule of thumb, not a stated canon) | generic |
|  |  |  | 4寸 (120 mm), Toda | fixed size | TODA2012 Table 1 (tested size; matches the 4/5/6寸 standard sizes, but the paper states no craft rule) | documented |
|  |  |  | 5寸 (150 mm), Toda | fixed size | TODA2012 Table 1 (tested size; matches the 4/5/6寸 standard sizes, but the paper states no craft rule) | documented |
|  |  |  | 6寸 (180 mm), Toda | fixed size | TODA2012 Table 1 (tested size; matches the 4/5/6寸 standard sizes, but the paper states no craft rule) | documented |
| `S.kamatsugi.hl` | Head length | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 1/2 L | scales | kenchikuyogo; Kijima & Kumazawa 2019 (all sources agree) | documented |
|  |  |  | 1/2 L, Toda | scales | TODA2012 Fig. 1 (drawn in Fig. 1 as L/2 + L/2, head and neck) | documented |
| `S.kamatsugi.b` | Neck width 鎌首 | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 30 mm (1寸) | fixed size | denmoku-db; Kijima 2019 (documented constant across sizes) | documented |
|  |  |  | 30 mm, kept at or under W/3 | partly scales | inferred (inferred, for small stock) | inferred |
|  |  |  | 30 mm, Toda | fixed size | TODA2012 Fig. 1 (read from Fig. 1; only one member width was tested (120 mm), so how it scales with W is unknown) | documented |
| `S.kamatsugi.e` | Jaw step, each side | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 7.5 mm | fixed size | Kijima 2019; Toda 2012 (the common value) | documented |
|  |  |  | 15 mm (wide jaw) | fixed size | Kijima 2019; Toda 2012 (documented variant) | documented |
|  |  |  | 5 mm | fixed size | Kijima 2019; Toda 2012 (documented variant) | documented |
|  |  |  | 7.5 mm, Toda | fixed size | TODA2012 Fig. 1 (read from Fig. 1 at the barb; same single-width caveat as the neck) | documented |
| `S.kamatsugi.d` | 鎌せい, depth to the seat | Gooseneck / gooseneck socket 鎌 / 鎌穴 | 1/2 H | scales | kenchikuyogo; hi-ho; diy-ie (all sources agree) | secondary |
|  |  |  | 1/2 H, Toda | scales | TODA2012 Fig. 1 (drawn in Fig. 1 as h/2, at all three tested depths) | documented |
| `S.kamatsugi.s` | Seat 腰掛 length | Seat 腰掛け | 15 mm | fixed size | diy-ie; 大工作業の実技 (single school, stated) | secondary |
| `S.kamatsugi.k` | Tapered mating faces (suberi kōbai) スベリ勾配 | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凹 | 1/10 | fixed size | diy-ie; Kijima; 林建築 (the common value; 1／10程度 on the drawing) | documented |
|  |  |  | 1/8 | fixed size | diy-ie; Kijima; 林建築 (documented variant) | documented |
|  |  |  | 1/27 | fixed size | diy-ie; Kijima; 林建築 (documented variant) | documented |
|  |  |  | 1/10, Toda | fixed size | TODA2012 Fig. 1 (read from Fig. 1; its leader points at the hook's flank, so the slope is a taper through the depth, not a lean along the beam) | documented |

**金輪継 *kanawa tsugi***

| ID | Dimension | Interface form | Rule | Type | Source | Evidence |
|---|---|---|---|---|---|---|
| `S.kanawa.L` | Joint length L | Oblique scarf 殺ぎ | 3 × せい (第廿圖) | scales | 第廿圖; 仕口継手技能 (the short end of 第廿圖's 3–3.5 times the depth) | documented |
|  |  |  | 3.5 × せい | scales | 第廿圖 (the long end of the craft range) | documented |
|  |  |  | 3 × W (AIJ) | scales | AIJ 接合部設計マニュアル 2009 (the short end of the engineering range) | documented |
|  |  |  | 4 × W (AIJ) | scales | AIJ 2009; S&M (the long end of the engineering range) | documented |
| `S.kanawa.slope` | すべり勾配 | Oblique scarf 殺ぎ | 1/24 (measured from 第廿圖) | fixed size | 第廿圖, measured (measured from 第廿圖 (not dimensioned on the plate)) | documented |
| `S.kanawa.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 15 mm (5分) | fixed size | denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); AIJ f = 15 (the 15 dimensioned at each end) | documented |
|  |  |  | 12 mm | fixed size | 林建築 (the small end of the range) | secondary |
|  |  |  | 18 mm | fixed size | 林建築 (the large end of the range) | secondary |
| `S.kanawa.mw` | 目違い (stub tenon), square | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | W/7 (第廿圖) | scales | 第廿圖 (one seventh of the top face) | documented |
|  |  |  | W/8 (第廿圖) | scales | 第廿圖 (one eighth of the top face) | documented |
| `S.kanawa.pg` | 栓, square (and the 腮 it sits in) | Peg / peg hole 栓 / 栓穴, 凸 | H/8 = 22.5 mm at H = 180, across the lap (第廿圖) | scales | 第廿圖 (1/8 of the section dimension across the lap, the dimension the plate measures; the model's default) | documented |
|  |  |  | W/8 = 15 mm at W = 120 (denmoku-db) | scales | denmoku-db 金輪継ぎ No. 22–26 (the 込栓 of denmoku-db's tested specimens, 15 mm at W = 120 (1/8 of their dimension across the lap)) | documented |

**追掛大栓継 *okkake daisen tsugi***

| ID | Dimension | Interface form | Rule | Type | Source | Evidence |
|---|---|---|---|---|---|---|
| `S.okkake.L` | Joint length L | Oblique scarf 殺ぎ | H × 3 (as dimensioned) | scales | denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); 仕口継手技能 (the joint length on the dimensioned drawing) | documented |
|  |  |  | 3.5 × せい | scales | 第廿圖 (the long end of the craft range) | documented |
|  |  |  | 3 × W (AIJ) | scales | AIJ 接合部設計マニュアル 2009 (the short end of the engineering range) | documented |
|  |  |  | 4 × W (AIJ) | scales | AIJ 2009; S&M (the long end of the engineering range) | documented |
| `S.okkake.slope` | すべり勾配 | Oblique scarf 殺ぎ | 1/10 | fixed size | denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); 仕口継手技能; kenchikuyogo (as dimensioned) | documented |
| `S.okkake.c` | Step up at the centre | Abbreviated gooseneck 略鎌 | 15 mm (5分) | fixed size | AIJ (the standard 腮) | documented |
|  |  |  | L/15, within 15–30 mm (5分 to 1寸) | partly scales | denmoku-db (腮 width 5分 to 1寸; wider risks splitting at the stub tenon) | documented |
| `S.okkake.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 15 mm (5分) | fixed size | denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); AIJ f = 15 (the 15 dimensioned at each end) | documented |
|  |  |  | 12 mm | fixed size | 林建築 (the small end of the range) | secondary |
|  |  |  | 18 mm | fixed size | 林建築 (the large end of the range) | secondary |
| `S.okkake.peg` | 込栓 draw pin, square | Peg / peg hole 栓 / 栓穴, 凸 | W/8 | scales | denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); AIJ (15 mm at W = 120, as dimensioned) | documented |
|  |  |  | W/6 | scales | AIJ (the stout end of the range) | documented |

**Where sources disagree**: in 24 dimensions, different sources give different values, or the page notes that they conflict (variants that one source documents are not counted). Each rule is kept with its source; none is merged.

**The dimensions where sources disagree**

| ID | Dimension | Interface form | Rules, each with its source |
|---|---|---|---|
| `S.daimochi.r` | Joint length (scarf overlap) | Oblique scarf 殺ぎ | 2 H (denmoku) (DM1); 2 1/2 H (Meiji rule) (NK1904); 3 H (project specimen) (WA) |
| `S.daimochi.t` | Tip land | Oblique scarf 殺ぎ | 1/4 H (denmoku) (DM1); ≈ 1/7 H (project specimen) (WA) |
| `S.daimochi.j` | Mid-scarf step height | Abbreviated gooseneck 略鎌 | 1/10 H (denmoku) (DM1); 9分 (Meiji rule: 8分 to 1寸) (NK1904); 3/10 H (project specimen) (WA) *(Rise of the reverse-sloped step at the centre. The sources conflict: proportional in denmoku, absolute in the Meiji rule.)* |
| `S.daimochi.jr` | Mid-scarf step run | Abbreviated gooseneck 略鎌 | 3/10 H (project specimen) (WA); 0 (vertical step) (DM1) |
| `S.daimochi.ml` | Mechigai tongue length | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | 1/4 W (Meiji rule) (NK1904); ≈ 1/7 W (project specimen) (WA); no tongue (DM1) |
| `S.daimochi.mw` | Mechigai tongue width | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | 1/4 W (Meiji rule) (NK1904); ≈ 2/7 W (project specimen) (WA) |
| `S.daimochi.p` | Dowel size | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 30 mm, about 1寸 (denmoku) (DM1); 1寸2分 (Meiji rule) (NK1904); 5分 (Fig. 3.2) (WA Fig. 3.2); 1 in (project specimen) (WA); 1寸 (Saitō 1904, lower) (Saitō 1904); 1寸4分 (Saitō 1904, upper) (Saitō 1904) |
| `S.daimochi.pl` | Dowel length | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 1/2 H + 30 mm (fits the denmoku table) (DM1); 2/3 H (denmoku text) (DM1); 1寸5分 (Meiji rule) (NK1904); 1寸 (Fig. 3.2) (WA Fig. 3.2); 2.5 in (project specimen) (WA) *(Dowel length across the cut. Contested: the denmoku text and table disagree.)* |
| `S.daimochi.tw` | Post tenon thickness (along the beam) | Tenon / mortise 枘 / 枘穴 | 30 mm, about 1寸 (HOWTEC; MLIT 2023; DM roof); 45 mm (stiffer variant) (AIJ T&D 15(29)); 1/4 of the post width (Saitō 1904) (Saitō 1904); 2/7 of the post width (Saitō 1904) (Saitō 1904) |
| `S.daimochi.td` | Post tenon width (across the beam) | Tenon / mortise 枘 / 枘穴 | W − 20 mm (HOWTEC; MLIT 2023; 富田 1999); 90 mm (koyatsuka, denmoku roof frame) (DM roof); 8/10 of the post width (Saitō 1904) (Saitō 1904); 8.5/10 of the post width (Saitō 1904) (Saitō 1904) |
| `S.daimochi.tl` | Stub tenon length | Tenon / mortise 枘 / 枘穴 | 50 mm (短ほぞ, standard) (HOWTEC; MLIT 2023); 45 mm (富田 1999); 1寸 (older hand practice) (Shimoyama); 3寸, 90 mm (長ほぞ) (Shimoyama); 120 mm (koyatsuka 長ほぞ, denmoku roof frame) (DM roof) |
| `S.aritsugi.A` | Dovetail length 蟻 (shoulder to tip) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | 0.45 W (105 craft proportions (one carpenter video); denmoku-db); W/2 (105 craft proportions (one carpenter video)) |
| `S.aritsugi.e` | Flare e, each side (蟻勾配) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | 1:5 of the dovetail length (105 craft proportions (one carpenter video)); 1:4 of the dovetail length (craft sources); 7.5 mm, 曲尺幅半分 (denmoku 蟻掛け) |
| `S.aritsugi.n` | Neck width 蟻首 | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | 30 mm (1寸) (105 craft proportions; Koshikake-aritsugi.pdf; denmoku-db); W/4 (craft rule of thumb); W/3 (craft rule of thumb) |
| `S.kamatsugi.L` | 鎌 length (head + neck) | Gooseneck / gooseneck socket 鎌 / 鎌穴 | 5寸 (150 mm) (denmoku-db; Araki; Instructables); 4寸 (120 mm) (denmoku-db; Araki; Instructables); 6寸 (180 mm) (denmoku-db; Araki; Instructables); 1 1/2 W (Instructables); 4寸 (120 mm), Toda (TODA2012 Table 1); 5寸 (150 mm), Toda (TODA2012 Table 1); 6寸 (180 mm), Toda (TODA2012 Table 1) |
| `S.kamatsugi.e` | Jaw step, each side | Gooseneck / gooseneck socket 鎌 / 鎌穴 | 7.5 mm (Kijima 2019; Toda 2012); 15 mm (wide jaw) (Kijima 2019; Toda 2012); 5 mm (Kijima 2019; Toda 2012); 7.5 mm, Toda (TODA2012 Fig. 1) |
| `S.kamatsugi.k` | Tapered mating faces (suberi kōbai) スベリ勾配 | Gooseneck / gooseneck socket 鎌 / 鎌穴 | 1/10 (diy-ie; Kijima; 林建築); 1/8 (diy-ie; Kijima; 林建築); 1/27 (diy-ie; Kijima; 林建築); 1/10, Toda (TODA2012 Fig. 1) |
| `S.kanawa.L` | Joint length L | Oblique scarf 殺ぎ | 3 × せい (第廿圖) (第廿圖; 仕口継手技能); 3.5 × せい (第廿圖); 3 × W (AIJ) (AIJ 接合部設計マニュアル 2009); 4 × W (AIJ) (AIJ 2009; S&M) *(The sources disagree, and the disagreement is real: the craft rule is the longest, AIJ's engineering range is shorter, and Toda measured almost no gain past 360 mm.)* |
| `S.kanawa.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | 15 mm (5分) (denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); AIJ f = 15); 12 mm (林建築); 18 mm (林建築) |
| `S.kanawa.pg` | 栓, square (and the 腮 it sits in) | Peg / peg hole 栓 / 栓穴 | H/8 = 22.5 mm at H = 180, across the lap (第廿圖) (第廿圖); W/8 = 15 mm at W = 120 (denmoku-db) (denmoku-db 金輪継ぎ No. 22–26) *(The sources conflict. 第廿圖 makes the 栓 a square of 1/8 of the section dimension across the lap (the dimension the plate measures; here the depth H, as the lap is horizontal): 22.5 mm at H = 180, the model's default. denmoku-db's tested 金輪継ぎ (No. 22–26) has a 栓 of 15 mm, W/8 at W = 120. Both are 1/8 of the dimension across their own lap, which in denmoku's specimens is 120 and in this model 180, so the sizes differ by the section, not by the fraction. The 腮 at the centre jogs back against the slope by the 栓's size, so the 栓 fills it.)* |
| `S.okkake.L` | Joint length L | Oblique scarf 殺ぎ | H × 3 (as dimensioned) (denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); 仕口継手技能); 3.5 × せい (第廿圖); 3 × W (AIJ) (AIJ 接合部設計マニュアル 2009); 4 × W (AIJ) (AIJ 2009; S&M) *(The sources disagree, and the disagreement is real: the craft rule is the longest, AIJ's engineering range is shorter, and Toda measured almost no gain past 360 mm.)* |
| `S.okkake.c` | Step up at the centre | Abbreviated gooseneck 略鎌 | 15 mm (5分) (AIJ); L/15, within 15–30 mm (5分 to 1寸) (denmoku-db) |
| `S.okkake.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | 15 mm (5分) (denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); AIJ f = 15); 12 mm (林建築); 18 mm (林建築) |
| `S.okkake.peg` | 込栓 draw pin, square | Peg / peg hole 栓 / 栓穴 | W/8 (denmoku-db 追掛け大栓継ぎ sheet (緑の列島ネットワーク, MLIT 2012, pp. 737–742; the dimensioned drawing); AIJ); W/6 (AIJ) |

## 4. Process rules

For each interface form, its links to outcomes, derived by the process rules (P1–P30, listed below) from the form's geometry, and set against the sources. Each link gives its outcome code, its rule and its status: *confirmed* (derived and stated by a source), *predicted* (derived only) or *documented* (stated by a source, not derived). Attributes in brackets: *availability*: standard pre-cut / special machines only / hand only; *set-ups*: one set-up / several set-ups; *sequence*: before assembly / after assembly / last; *component*: integral / separate piece.

| Interface form | Assembly (AS) | Disassembly (DS) | Repair (RP) | Hand (手刻み, HF) | CNC (プレカット, DF) | Stays manual |
|---|---|---|---|---|---|---|
| Butt face 突き付け | — | — | — | Cross-cutting (HF3), rule P17, predicted; Planing (HF6), rule P20, predicted | Cutting to length (DF1), rule P24, predicted; Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted | — |
| Oblique scarf 殺ぎ | Lowered from above (AS2), rule P1, confirmed | — | Needs headroom (RP2), rule P12, predicted | Rip-sawing (HF2), rule P16, confirmed; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, confirmed | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Halving (half-lap) 相欠き | Lowered from above (AS2), rule P1, confirmed | — | Needs headroom (RP2), rule P12, predicted | Rip-sawing (HF2), rule P16, confirmed; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Seat 腰掛け | Set first (AS1), documented; Lowered from above (AS2), rule P1, confirmed; Held by load above (AS6), rule P7, confirmed | — | Needs headroom (RP2), rule P12, predicted; Unload from above (RP3), rule P13, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Mitre 留め | — | — | — | Cross-cutting (HF3), rule P17, predicted; Planing (HF6), rule P20, predicted | Cutting to length (DF1), rule P24, predicted; Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted | — |
| Notch 欠き込み | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Housing 大入れ | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Open slot mortise 輪薙ぎ込み | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Cog 渡り腮 | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Through mortise 貫通し | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Box housing 箱 | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Abbreviated gooseneck 略鎌 | Lowered from above (AS2), rule P1, confirmed; Side, then axial (AS3), documented; Draw tight (AS4), rule P6, confirmed | Lift against friction (DS2), rule P9, confirmed | Needs side clearance (RP1), documented; Needs headroom (RP2), rule P12, confirmed | Rip-sawing (HF2), rule P16, confirmed; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, confirmed; Fitting and finishing (HF8) [last], rule P22, confirmed | Roughing (DF2) [special machines only, standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [special machines only, standard pre-cut, one set-up], rule P25, confirmed; Re-clamping for a new set-up (DF5) [several set-ups], documented; squaring corners and filing (DF6), rule P28, predicted | Fitting and finishing (HF8) [last], rule P22, confirmed; squaring corners and filing (DF6), rule P28, predicted |
| Stub tenon / stub mortise 目違い / 目違ほぞ穴 | Side, then axial (AS3), rule P2, confirmed | Shift, then out sideways (DS3), rule P10, confirmed | Needs side clearance (RP1), rule P11, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, predicted; Planing (HF6), documented; Fitting and finishing (HF8) [last], documented | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; Re-clamping for a new set-up (DF5) [several set-ups], documented; squaring corners and filing (DF6), rule P28, confirmed | Fitting and finishing (HF8) [last], documented; squaring corners and filing (DF6), rule P28, confirmed |
| Collar (term unverified) 襟輪 | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Tenon / mortise 枘 / 枘穴 | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Rod tenon, keyed 竿 | Draw tight (AS4), rule P6, predicted; Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted; Fitting and finishing (HF8) [last], rule P22, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6), rule P28, predicted | Fitting and finishing (HF8) [last], rule P22, predicted; squaring corners and filing (DF6), rule P28, predicted |
| Bridle 三枚組 | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Gooseneck / gooseneck socket 鎌 / 鎌穴 | Lowered from above (AS2), rule P1, confirmed; Held by load above (AS6), rule P7, confirmed | — | Needs headroom (RP2), rule P12, predicted; Unload from above (RP3), rule P13, predicted | Rip-sawing (HF2), documented; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, confirmed | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | Lowered from above (AS2), rule P1, confirmed; Held by load above (AS6), rule P7, confirmed | — | Needs headroom (RP2), rule P12, predicted; Unload from above (RP3), rule P13, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6), rule P28, predicted | squaring corners and filing (DF6), rule P28, predicted |
| Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | Set first (AS1), rule P4, predicted | — | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Chiselling (HF4) [hand only], rule P18, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted | — | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Chiselling (HF4) [hand only], rule P18, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted |
| Peg / peg hole 栓 / 栓穴 | Draw tight (AS4), rule P6, confirmed; Lock goes in last (AS5), rule P5, confirmed | Lock comes out first (DS1), rule P8, confirmed | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted; Boring peg holes (HF7) [hand only], rule P21, predicted; Fitting and finishing (HF8) [last, hand only], rule P22, predicted | Drilling (DF4) [after assembly, special machines only], rule P29, confirmed | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted; Boring peg holes (HF7) [hand only], rule P21, predicted; Fitting and finishing (HF8) [last, hand only], rule P22, predicted |
| Key 車知 | Draw tight (AS4), rule P6, predicted; Lock goes in last (AS5), rule P5, predicted | Lock comes out first (DS1), rule P8, predicted | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Chiselling (HF4) [hand only], rule P18, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted; Fitting and finishing (HF8) [last, hand only], rule P22, predicted | — | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Chiselling (HF4) [hand only], rule P18, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted; Fitting and finishing (HF8) [last, hand only], rule P22, predicted |
| Wedge 楔 | Draw tight (AS4), rule P6, predicted; Lock goes in last (AS5), rule P5, predicted | Lock comes out first (DS1), rule P8, predicted | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted; Fitting and finishing (HF8) [last, hand only], rule P22, predicted | — | Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted; Planing (HF6) [separate piece, hand only], rule P23, predicted; Fitting and finishing (HF8) [last, hand only], rule P22, predicted |

**The process rules (P1–P30): each gives links from a form's geometry**

| Rule | When the geometry shows | Gives |
|---|---|---|
| P1 | lowered into a top-opening half | lowered from above |
| P2 | in from the side then along | side, then axial |
| P3 | entered along the member | pushed in along the axis |
| P4 | a separate piece set into its holes | set first |
| P5 | a separate locking piece | goes in last |
| P6 | a taper, keys or a drawbore | drawn tight |
| P7 | lowered and carrying the load from above | held by the load |
| P8 | a separate lock | it comes out first |
| P9 | lowered and drawn tight | lifted against friction |
| P10 | in from the side then along | shifted, then out sideways |
| P11 | in from the side | needs side clearance |
| P12 | lowered from above | needs headroom |
| P13 | lowered and carrying the load | the load comes off first |
| P14 | entered along the member | needs axial clearance |
| P15 | a separate piece | cheap to replace |
| P16 | long faces along the grain | rip-sawing |
| P17 | cuts across the grain | cross-cutting |
| P18 | square inside corners | chiselling |
| P19 | fit-critical faces inside a recess | paring |
| P20 | long faces along the grain, or an end face with no inside corners | planing |
| P21 | a hole through both members | boring peg holes |
| P22 | drawn tight | fitted by hand, last |
| P23 | a separate piece | made on its own |
| P24 | an end face, no recess | cut to length |
| P25 | open to one face, no undercut | roughed and finished in one set-up |
| P26 | open to more than one face, or through | several set-ups |
| P27 | an undercut | special machines only |
| P28 | square inside corners | the cutter leaves them round, squared by hand |
| P29 | a hole through both members, drawn tight | drilled after assembly |
| P30 | a separate piece | made by hand, not on the line |

**Each form's geometry, as recorded**

| Interface form | Geometry |
|---|---|
| Butt face 突き付け | Assembled: no direction of its own (a contact face: it goes with the parts it belongs to). Opens to: end. Blocks: axial, in compression. Undercut: no. Fit-critical: the end face. Separate piece: no. Features: cuts across the grain. |
| Oblique scarf 殺ぎ | Assembled: lowered from above. Opens to: top. Blocks: down. Undercut: no. Fit-critical: the scarf faces, the lands. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners, sloped faces. |
| Halving (half-lap) 相欠き | Assembled: lowered from above. Opens to: top. Blocks: down, sideways. Undercut: no. Fit-critical: the lap faces, the shoulders. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners. |
| Seat 腰掛け | Assembled: lowered from above. Opens to: top. Blocks: down. Undercut: no. Fit-critical: the seat face. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners, carries the load from above. |
| Mitre 留め | Assembled: no direction of its own (a contact face: it goes with the parts it belongs to). Opens to: end. Blocks: axial, in compression. Undercut: no. Fit-critical: the mitre face. Separate piece: no. Features: cuts across the grain, sloped faces. |
| Notch 欠き込み | Assembled: lowered from above. Opens to: top. Blocks: down, sideways. Undercut: no. Fit-critical: the notch faces. Separate piece: no. Features: cuts across the grain, square inside corners. |
| Housing 大入れ | Assembled: pushed in along the member. Opens to: face. Blocks: into the face, sideways. Undercut: no. Fit-critical: the housing walls. Separate piece: no. Features: cuts across the grain, square inside corners. |
| Open slot mortise 輪薙ぎ込み | Assembled: lowered from above. Opens to: top, end. Blocks: down, sideways. Undercut: no. Fit-critical: the slot cheeks. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners. |
| Cog 渡り腮 | Assembled: lowered from above. Opens to: top. Blocks: down, along the beam. Undercut: no. Fit-critical: the cog faces. Separate piece: no. Features: cuts across the grain, square inside corners. |
| Through mortise 貫通し | Assembled: pushed in along the member. Opens to: through. Blocks: sideways, down. Undercut: no. Fit-critical: the mortise cheeks. Separate piece: no. Features: cuts across the grain, square inside corners. |
| Box housing 箱 | Assembled: pushed in along the member. Opens to: face. Blocks: sideways. Undercut: no. Fit-critical: the four walls. Separate piece: no. Features: square inside corners. |
| Abbreviated gooseneck 略鎌 | Assembled: lowered from above. Opens to: top. Blocks: down, along the beam. Undercut: no. Fit-critical: the hook faces. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners, sloped faces, draws tight. |
| Stub tenon / stub mortise 目違い / 目違ほぞ穴 | Assembled: in from the side, then along. Opens to: end. Blocks: sideways, up. Undercut: no. Fit-critical: the stub's cheeks. Separate piece: no. Features: cuts across the grain, square inside corners. |
| Collar (term unverified) 襟輪 | Assembled: lowered from above. Opens to: top. Blocks: down, sideways. Undercut: no. Fit-critical: the collar faces. Separate piece: no. Features: cuts across the grain, square inside corners. |
| Tenon / mortise 枘 / 枘穴 | Assembled: pushed in along the member. Opens to: face. Blocks: sideways, down. Undercut: no. Fit-critical: the tenon cheeks, the shoulder. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners. |
| Rod tenon, keyed 竿 | Assembled: pushed in along the member. Opens to: through. Blocks: sideways, down, along, by the keys. Undercut: no. Fit-critical: the rod's cheeks, the key slots. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners, draws tight. |
| Bridle 三枚組 | Assembled: pushed in along the member. Opens to: end, through. Blocks: sideways. Undercut: no. Fit-critical: the cheeks. Separate piece: no. Features: long faces along the grain, cuts across the grain, square inside corners. |
| Gooseneck / gooseneck socket 鎌 / 鎌穴 | Assembled: lowered from above. Opens to: top. Blocks: down, along the beam. Undercut: no. Fit-critical: the neck and head flanks. Separate piece: no. Features: cuts across the grain, square inside corners, sloped faces, carries the load from above. |
| Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | Assembled: lowered from above. Opens to: top. Blocks: down, along the beam. Undercut: no. Fit-critical: the dovetail flanks. Separate piece: no. Features: cuts across the grain, square inside corners, carries the load from above. |
| Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | Assembled: set into its holes first. Opens to: face. Blocks: sideways. Undercut: no. Fit-critical: the dowel's faces. Separate piece: yes. Features: square inside corners. |
| Peg / peg hole 栓 / 栓穴 | Assembled: driven in last. Opens to: through. Blocks: the members' separation. Undercut: no. Fit-critical: the peg and its hole. Separate piece: yes. Features: a hole through both members, draws tight. |
| Key 車知 | Assembled: driven in last. Opens to: through. Blocks: along, drawing the joint tight. Undercut: no. Fit-critical: the key and its slot. Separate piece: yes. Features: square inside corners, draws tight. |
| Wedge 楔 | Assembled: driven in last. Opens to: end. Blocks: the tenon's withdrawal. Undercut: no. Fit-critical: the wedge and its kerf. Separate piece: yes. Features: draws tight. |

**The outcomes and their codes; the operations with their tools and machine processings**

- Assembly: **Set first** (AS1).
- Assembly: **Lowered from above** (AS2).
- Assembly: **Side, then axial** (AS3).
- Assembly: **Pushed in along the axis** (AS7).
- Assembly: **Draw tight** (AS4).
- Assembly: **Lock goes in last** (AS5).
- Assembly: **Held by load above** (AS6).
- Disassembly: **Lock comes out first** (DS1).
- Disassembly: **Lift against friction** (DS2).
- Disassembly: **Shift, then out sideways** (DS3).
- Repair: **Needs side clearance** (RP1).
- Repair: **Needs headroom** (RP2).
- Repair: **Needs axial clearance** (RP5).
- Repair: **Unload from above** (RP3).
- Repair: **Cheap part to replace** (RP4).
- Hand fabrication (手刻み): **Marking out (墨付け sumitsuke)** (HF1). Tools: carpenter's square (差金), marking gauge (罫引), ink line (墨壺).
- Hand fabrication (手刻み): **Rip-sawing (縦挽き tatebiki)** (HF2). Tools: rip saw.
- Hand fabrication (手刻み): **Cross-cutting (横挽き yokobiki)** (HF3). Tools: crosscut saw.
- Hand fabrication (手刻み): **Chiselling** (HF4). Tools: striking chisel (叩き鑿) and hammer (玄翁); chisel mortiser (角のみ).
- Hand fabrication (手刻み): **Paring** (HF5). Tools: paring chisel (突き鑿).
- Hand fabrication (手刻み): **Planing** (HF6). Tools: plane (鉋); shoulder plane (際鉋).
- Hand fabrication (手刻み): **Boring peg holes** (HF7). Tools: peg-hole mortiser (込み栓角のみ), gimlet (錐) or chisel.
- Hand fabrication (手刻み): **Fitting and finishing** (HF8). Tools: chisels, planes, hammer.
- Digital fabrication (CNC / プレカット): **Cutting to length** (DF1). Tools: saw unit. BTLx: Cut, JackRafterCut. Pre-cut: 切断.
- Digital fabrication (CNC / プレカット): **Roughing** (DF2). Tools: ½ in end mill. BTLx: Lap, Pocket, Slot, Mortise, Tenon, DovetailMortise, DovetailTenon. Pre-cut: 継手・仕口加工 (荒取り).
- Digital fabrication (CNC / プレカット): **Finishing** (DF3). Tools: ¼ in end mill or ball-nose cutter. BTLx: the same processings, finishing pass. Pre-cut: 継手・仕口加工 (仕上げ).
- Digital fabrication (CNC / プレカット): **Drilling** (DF4). Tools: drill unit. BTLx: Drilling. Pre-cut: 穴あけ.
- Digital fabrication (CNC / プレカット): **Re-clamping for a new set-up** (DF5). Tools: clamps, jig. No BTLx processing: the part is turned or re-clamped between processings.
- Digital fabrication (CNC / プレカット): **Post-processing: squaring corners and filing** (DF6). Tools: chisel, file. No BTLx processing: by hand after the machine.

## 4b. General rules (G)

Rules that hold for every joint, as the viewer applies them in its assembly, take-apart and repair.

| Rule | Rule text | Where the viewer applies it |
|---|---|---|
| G1 | A separate locking piece (pin, peg, wedge, key) goes in last and comes out first. | assembly order; take-apart order; P5, P8 per form |
| G2 | A part comes out when it has a clear straight path out, as measured from the contact between the parts (or a short slide then a turn); what is still held waits for what holds it. | take-apart order (contact limits; imagecad/contact.py) |
| G3 | To replace a part, take out every part that blocks it, and what blocks those; a part it carries (blind dowels set into it) is moved to the new part and reused. | Repair section; BLOCKS and CARRIES in the knowledge graph |
| G4 | Where both elements are one part turned end for end, one spare serves for either. | daimochi, 金輪, 追掛大栓: Repair section |

## 4c. Joint-level rules (J)

Rules for the joint as a whole. Their outcomes are recorded per joint, apart from the form-level links of section 4, which they do not change: a form keeps its own links, and the joint adds its own assembly outcome on the forms of its primary interface.

| Rule | Rule text | Read from |
|---|---|---|
| J1 | A joint's assembly direction comes from its primary interface (the one between its two elements) as a whole: the reverse of the way the upper element was measured to leave, from the contact between the parts. It replaces each of that interface's forms' own direction. | the joint's measured take-apart (G2) |
| J2 | A joint with no driven lock in its configuration (no pin, peg, wedge or bolt) is held by the load from above, on each form of its primary interface. | the joint's components in its configuration |

| Joint | Configuration | The upper element leaves | Joint-level outcomes | On the forms |
|---|---|---|---|---|
| 台持継 *daimochi tsugi* | support: post below, tenon through both pieces; locking: dowels | +z (up) | Lowered from above (AS2), rule J1; Held by load above (AS6), rule J2 | Oblique scarf 殺ぎ, Abbreviated gooseneck 略鎌, Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| 腰掛蟻継 *koshikake ari tsugi* | reinforcement: none | +z (up) | Lowered from above (AS2), rule J1; Held by load above (AS6), rule J2 | Seat 腰掛け, Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 |
| 腰掛鎌継 *koshikake kama tsugi* | variant: plain | +z (up) | Lowered from above (AS2), rule J1; Held by load above (AS6), rule J2 | Seat 腰掛け, Gooseneck / gooseneck socket 鎌 / 鎌穴 |
| 金輪継 *kanawa tsugi* | variant: 栓 pin | +x for 15 mm, then +y or -y | Side, then axial (AS3), rule J1 | Oblique scarf 殺ぎ, Abbreviated gooseneck 略鎌, Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| 追掛大栓継 *okkake daisen tsugi* | variant: 込栓 draw pins × 2 | +z, -z | Lowered from above (AS2), rule J1 | Oblique scarf 殺ぎ, Abbreviated gooseneck 略鎌, Stub tenon / stub mortise 目違い / 目違ほぞ穴 |

## 4d. Context rules (X)

Rules that apply once the joint is placed in a building.

| Rule | Rule text | Joints | Source |
|---|---|---|---|
| X1 | Continue the splice 150–300 mm (柱心から5寸–1尺) past the support and away from mid-span. | 金輪継 *kanawa tsugi*, 追掛大栓継 *okkake daisen tsugi* | 平12建告1460号; AIJ |
| X2 | The daimochi sits over a support: a post below (its tenon through both pieces or a stub), a post above, or a beam below with a cog. | 台持継 *daimochi tsugi* | WA Figs 3.2–3.7 |
| X3 | Before a part that carries load is taken out, shore what it carries (a temporary post, props). | 台持継 *daimochi tsugi*, 腰掛蟻継 *koshikake ari tsugi*, 腰掛鎌継 *koshikake kama tsugi*, 金輪継 *kanawa tsugi*, 追掛大栓継 *okkake daisen tsugi* | practice, as the Repair section lists it |
| X4 | On an eaves beam the 金輪継 is joined before the beam is laid on the posts. | 金輪継 *kanawa tsugi* | 日本家屋構造 p.20 |

## 4e. Machining rules (M)

Which cutter makes a CNC pass, from what the cutter can leave (tool capability). They choose how a digital-fabrication outcome is made; they add no link.

| Rule | Rule text | Outcome | Basis | Time compared |
|---|---|---|---|---|
| M1 | A sloped face is finished with the flat cutter at a fine step-over (1/4 in, 1.5 mm) where the stairs it leaves, step-over × gradient, stay within 0.1 mm, a third of the 0.3 mm fit clearance; a steeper slope with the ball end (1/4 in, 0.635 mm). | Finishing (DF3) | tool capability: on a slope a flat end mill leaves stairs of step-over × gradient, a ball end scallops of r − √(r² − (s/2)²); the limit is a third of the fit clearance (imagecad.fabricate, _ops) | 金輪 1/24 (stairs 0.06 mm): flat, 539.3 min raster / 723.7 min in all, against 947.5 / 1,614.6 with the ball end at 0.635 mm (at 1.13 mm 1,371.6, at 1.59 mm 1,289.8 in all; flat only at 3 mm 644.5, at 1.5 mm 509.5); 追掛大栓 1/10 (0.15 mm) and daimochi 1:3: ball end |

## 5. Derivation example: daimochi tsugi

**Configuration**: post below with its tenon through both elements, locked by dowels, square timber; member H = W = 120 mm (4寸, the section Saitō's fixed sizes assume). Each step applies the rules named on the right; the IDs are those of sections 2–4.

| Step | Result | Rule applied |
|---|---|---|
| 1. Components | lower element, upper element (the same part, turned end for end), two dowels, a post below | the daimochi's components with two options chosen: locking by dowels (`C.daimochi.2`) and a post below (`C.daimochi.4`) |
| 2. Interfaces | beam–beam; dowel–element (each of two dowels in both elements); post–element | `C.daimochi.1`, `C.daimochi.2`, `C.daimochi.4` |
| 3. Interface forms | Oblique scarf 殺ぎ + Abbreviated gooseneck 略鎌 + Stub tenon / stub mortise 目違い / 目違ほぞ穴 ×2; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い (dowels); Tenon / mortise 枘 / 枘穴 + Housing 大入れ | the right-hand sides of `C.daimochi.1`, .2 and .4 |
| 4. Sizes | joint 240, tip land 30, step 12 high and 36 long, tongues 30 × 30, dowels 30 square × 90, housing 5.3 deep, tenon 30 × 100 × 114.7 (mm). Checks: 9 pass, 3 warn | the first rule of each dimension: `S.daimochi.r`, `S.daimochi.t`, `S.daimochi.j`, `S.daimochi.jr`, `S.daimochi.ml`, `S.daimochi.mw`, `S.daimochi.p`, `S.daimochi.pl`, `S.daimochi.sd`, `S.daimochi.tw`, `S.daimochi.td`; the tenon's length from the geometry |
| 5. Assembly | dowels and post below → lower piece → upper piece | form rules, which hold across joints: Oblique scarf 殺ぎ: Lowered from above (AS2), rule P1, confirmed; Abbreviated gooseneck 略鎌: Lowered from above (AS2), rule P1, confirmed, Side, then axial (AS3), documented, Draw tight (AS4), rule P6, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Side, then axial (AS3), rule P2, confirmed; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: Set first (AS1), rule P4, predicted; Tenon / mortise 枘 / 枘穴: Pushed in along the axis (AS7), rule P3, predicted; Housing 大入れ: Pushed in along the axis (AS7), rule P3, predicted; the order itself from the contact between the parts (what blocks what) |
| 6. Disassembly | upper piece and post below → lower piece and dowels | form rules, which hold across joints: Abbreviated gooseneck 略鎌: Lift against friction (DS2), rule P9, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Shift, then out sideways (DS3), rule P10, confirmed; the order from the same contact |
| 7. Repair set | lower piece: take out upper piece; move the dowels to the new piece (reused); upper piece: nothing else comes out; dowels: take out upper piece; post below: nothing else comes out | form rules, which hold across joints: Oblique scarf 殺ぎ: Needs headroom (RP2), rule P12, predicted; Abbreviated gooseneck 略鎌: Needs side clearance (RP1), documented, Needs headroom (RP2), rule P12, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Needs side clearance (RP1), rule P11, predicted; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: Cheap part to replace (RP4), rule P15, predicted; Tenon / mortise 枘 / 枘穴: Needs axial clearance (RP5), rule P14, predicted; Housing 大入れ: Needs axial clearance (RP5), rule P14, predicted; G3: each set from the contact, what must come out before the part can, and what it carries moved to the new part |
| 8. Hand route (手刻み) | prepare the timber (planing) → marking out (sumitsuke) → cut the scarf slope (rip-sawing, cross-cutting) → cut the step at the centre (chiselling) → cut the tongue at the tip, and its cut-out (sawing, chiselling) → cut the dowel holes (chiselling) → make the second piece → fit (paring, planing) → assemble (fitting) | form rules, which hold across joints: Oblique scarf 殺ぎ: Rip-sawing (HF2), rule P16, confirmed, Cross-cutting (HF3), rule P17, confirmed, Chiselling (HF4), rule P18, predicted, Paring (HF5), rule P19, predicted, Planing (HF6), rule P20, confirmed; Abbreviated gooseneck 略鎌: Rip-sawing (HF2), rule P16, confirmed, Cross-cutting (HF3), rule P17, confirmed, Chiselling (HF4), rule P18, confirmed, Paring (HF5), rule P19, predicted, Planing (HF6), rule P20, confirmed, Fitting and finishing (HF8) [last], rule P22, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Cross-cutting (HF3), rule P17, predicted, Chiselling (HF4), rule P18, confirmed, Paring (HF5), rule P19, predicted, Planing (HF6), documented, Fitting and finishing (HF8) [last], documented; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: Rip-sawing (HF2) [separate piece, hand only], rule P23, predicted, Chiselling (HF4) [hand only], rule P18, predicted, Planing (HF6) [separate piece, hand only], rule P23, predicted; Tenon / mortise 枘 / 枘穴: Rip-sawing (HF2), rule P16, predicted, Cross-cutting (HF3), rule P17, predicted, Chiselling (HF4), rule P18, predicted, Paring (HF5), rule P19, predicted, Planing (HF6), rule P20, predicted; Housing 大入れ: Cross-cutting (HF3), rule P17, predicted, Chiselling (HF4), rule P18, predicted, Paring (HF5), rule P19, predicted; in the order of the documented sequence (Wang 2024) |
| 9. CNC route (プレカット) | model → program the toolpaths → mill test pieces (roughing (½ in end mill)) → rough out (roughing (½ in end mill)) → refine (finishing (¼ in end mill)) → finish (finishing (ball-nose cutter)) → second piece (roughing (½ in end mill), finishing (¼ in end mill), finishing (ball-nose cutter)) → post-process (squaring corners and filing) → assemble (fitting) | form rules, which hold across joints: Oblique scarf 殺ぎ: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, squaring corners and filing (DF6), rule P28, predicted; Abbreviated gooseneck 略鎌: Roughing (DF2) [special machines only, standard pre-cut, one set-up], rule P25, confirmed, Finishing (DF3) [special machines only, standard pre-cut, one set-up], rule P25, confirmed, Re-clamping for a new set-up (DF5) [several set-ups], documented, squaring corners and filing (DF6), rule P28, predicted; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, Re-clamping for a new set-up (DF5) [several set-ups], documented, squaring corners and filing (DF6), rule P28, confirmed; Tenon / mortise 枘 / 枘穴: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, squaring corners and filing (DF6), rule P28, predicted; Housing 大入れ: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, squaring corners and filing (DF6), rule P28, predicted; in the order of the documented sequence (Wang 2024) |

**Step 4 in full: each size and the rule that gives it**

| Rule | Dimension | Interface form | Rule applied | Value | Evidence |
|---|---|---|---|---|---|
| `S.daimochi.r` | Joint length (scarf overlap) | Oblique scarf 殺ぎ | 2 H (denmoku) | 240 mm | documented |
| `S.daimochi.t` | Tip land | Oblique scarf 殺ぎ | 1/4 H (denmoku) | 30 mm | documented |
| `S.daimochi.j` | Mid-scarf step height | Abbreviated gooseneck 略鎌 | 1/10 H (denmoku) | 12 mm | documented |
| `S.daimochi.jr` | Mid-scarf step run | Abbreviated gooseneck 略鎌 | 3/10 H (project specimen) | 36 mm | inferred |
| `S.daimochi.ml` | Mechigai tongue length | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | 30 mm | secondary |
| `S.daimochi.mw` | Mechigai tongue width | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | 30 mm | secondary |
| `S.daimochi.p` | Dowel size | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 30 mm, about 1寸 (denmoku) | 30 mm | documented |
| `S.daimochi.pl` | Dowel length | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 1/2 H + 30 mm (fits the denmoku table) | 90 mm | inferred |
| `S.daimochi.sd` | Seat housing depth | Housing 大入れ | placeholder, held absolute | 5.3 mm | inferred |
| `S.daimochi.tw` | Post tenon thickness (along the beam) | Tenon / mortise 枘 / 枘穴, 凸 | 30 mm, about 1寸 | 30 mm | documented |
| `S.daimochi.td` | Post tenon width (across the beam) | Tenon / mortise 枘 / 枘穴, 凸 | W − 20 mm | 100 mm | documented |
| geometry | Through tenon length | Tenon / mortise 枘 / 枘穴, 凸 | H − housing depth: through both elements | 114.7 mm | geometry |

Checked against the page's own checks: 9 pass, 3 warn (Halves share the scarf, not the seat; Mechigai tongues (T-shaped); Machinable with a 6 mm cutter).

**Steps 5 to 9 in full: the assembly steps, repair sets and routes**

- Post below: The roof post (koyatsuka) stands under the joint; its tenon (hiragara) projects upwards above the shoulder (dōzuki).
- Lower piece: The lower piece (shitaki) is set down over the post tenon, which passes through its mortise; the post shoulder (dōzuki) seats in the housing on its underside.
- Set dowels: The dowels (太枘 dabo) are set into their mortises in the lower piece before the upper piece goes on.
- Upper piece: The upper piece (uwaki), the same part turned end over end, is lowered straight down onto the scarf and over the dowels, over the post tenon.
- Taking apart: upper piece and post below → lower piece and dowels.
- Replace the lower piece: take out upper piece; shore the beam ends it carries. Stays: dowels, post below.
- Replace the upper piece: nothing else comes out; relieve the 小屋束 above it: prop the roof locally. Stays: lower piece, dowels, post below.
- Replace the dowels: take out upper piece. Stays: lower piece, post below.
- Replace the post below: nothing else comes out; shore the beam above it first (temporary post). Stays: lower piece, upper piece, dowels.
- Hand (手刻み): prepare the timber (planing) → marking out (sumitsuke) → cut the scarf slope (rip-sawing, cross-cutting) → cut the step at the centre (chiselling) → cut the tongue at the tip, and its cut-out (sawing, chiselling) → cut the dowel holes (chiselling) → make the second piece → fit (paring, planing) → assemble (fitting).
- CNC: model → program the toolpaths → mill test pieces (roughing (½ in end mill)) → rough out (roughing (½ in end mill)) → refine (finishing (¼ in end mill)) → finish (finishing (ball-nose cutter)) → second piece (roughing (½ in end mill), finishing (¼ in end mill), finishing (ball-nose cutter)) → post-process (squaring corners and filing) → assemble (fitting). Stays manual: squaring the corners and filing (post-processing), fitting.
