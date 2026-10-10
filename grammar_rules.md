# Making grammar: the rules

Written out by `viewer/tools/grammar_rules.py` from the viewer's own data (`viewer/index.html`); edit the page's data, not this file. The landing page's Rules section shows the same rules as compact tables, with the detail folded.

Rules of the making grammar, written out from the viewer's own data: the interface forms (vocabulary), the rules that combine them into each joint's interfaces, the rules that size them, the rules that link them to assembly, repair and fabrication, and one joint derived by applying them. Nothing here is added to the data the joint pages use. Each rule has an ID, one letter for its kind (C combination; S sizing, per form and per joint; P process, P1 to P32; Q sequence, Q1 to Q7; G general; J joint-level, for the joint as a whole; X context, once the joint is in a building; M machining, the cutter for a CNC pass), so that the derivation can name the rule behind each step. Outcomes have two letters, so they never clash with a rule: AS assembly, DS disassembly, RP repair, HF hand fabrication, DF digital fabrication; every derived or predicted link gives its outcome and its rule, as in “Cross-cutting (HF3), rule P17, predicted”. Inferred rules are marked.

| Rules | Number | Of which inferred |
|---|---|---|
| Combination (C.): interfaces of the five joints | 15 | — (10 hold only with an option or variant) |
| Sizing per form (S.), from the sources | 66 | 1 |
| Sizing per joint (S.), scales | 46 | 7 |
| Sizing per joint (S.), fixed size | 57 | 4 |
| Sizing per joint (S.), partly scales | 5 | 3 |
| Process (P1–P32): rules from a form's geometry | 32 | — |
| Links they give, assembly | 31 | 16 predicted |
| Links they give, disassembly | 5 | 2 predicted |
| Links they give, repair | 25 | 23 predicted |
| Links they give, hand fabrication (手刻み) | 89 | 70 predicted |
| Links they give, digital fabrication (CNC / プレカット) | 85 | 71 predicted |
| General (G) | 4 | — |
| Joint-level (J) | 2 | — |
| Context (X) | 5 | — |
| Machining (M) | 2 | — |

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
| `C.kamatsugi.2` |  | Beam–beam interface, 目違い variant | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | variant: 目違い notch |
| `C.kamatsugi.3` |  | Peg–element interfaces (one peg through both elements) | Peg / peg hole 栓 / 栓穴 | variant: 込栓, driven sideways |
| `C.kanawa.1` | 金輪継 *kanawa tsugi* | Beam–beam interface | Oblique scarf 殺ぎ + Abbreviated gooseneck 略鎌 + Stub tenon / stub mortise 目違い / 目違ほぞ穴 ×2 | every configuration |
| `C.kanawa.2` |  | Peg–element interfaces (one peg in the 腮, between both elements, down from the top) | Peg / peg hole 栓 / 栓穴 | variant: locked |
| `C.okkake.1` | 追掛大栓継 *okkake daisen tsugi* | Beam–beam interface | Oblique scarf 殺ぎ + Abbreviated gooseneck 略鎌 + Stub tenon / stub mortise 目違い / 目違ほぞ穴 ×2 | every configuration |
| `C.okkake.2` |  | Peg–element interfaces (two pegs through both elements, across the width from the side faces) | Peg / peg hole 栓 / 栓穴 | variant: locked |

**Components of each joint**

台持継 *daimochi tsugi*: Lower element (shitaki) and upper element (uwaki), the same part turned end for end. By option: two dowels, two draw pegs, two bolts or two wedges; a post below, a post above or a beam below. Bolts (a locking option for logs) are hardware, not an interface form of the vocabulary.

腰掛蟻継 *koshikake ari tsugi*: Lower element (shitaki) and upper element (uwaki).

腰掛鎌継 *koshikake kama tsugi*: Lower element (shitaki) and upper element (uwaki); by variant, one 込栓 peg.

金輪継 *kanawa tsugi*: Two identical elements; in the locked variant, one 栓 peg.

追掛大栓継 *okkake daisen tsugi*: Two identical elements; in the locked variant, two 込栓 pegs.

## 3. Sizing rules



| ID | Interface form | Sizing | Per-joint dimensions |
|---|---|---|---|
| `S.tsuki` | Butt face 突き付け | not restricted (follows the member) | — |
| `S.sogi` | Oblique scarf 殺ぎ | scales | `S.daimochi.r`, `S.daimochi.t`, `S.kanawa.L`, `S.kanawa.slope`, `S.okkake.L`, `S.okkake.slope` |
| `S.aikaki` | Halving (half-lap) 相欠き | no rule found | — |
| `S.koshi` | Seat 腰掛け | fixed size | `S.aritsugi.sd`, `S.aritsugi.s`, `S.kamatsugi.s` |
| `S.tome` | Mitre 留め | not restricted (follows the member) | — |
| `S.kaki` | Notch 欠き込み | partly scales | — |
| `S.oire` | Housing 大入れ | partly scales | `S.daimochi.sd` |
| `S.wanagi` | Open slot mortise 輪薙ぎ込み | partly scales | — |
| `S.ago` | Cog 渡り腮 | fixed size | `S.daimochi.cd`, `S.daimochi.cw` |
| `S.nuki` | Through mortise 貫通し | partly scales | — |
| `S.hako` | Box housing 箱 | no rule found | — |
| `S.ryaku` | Abbreviated gooseneck 略鎌 | partly scales | `S.daimochi.j`, `S.daimochi.jr`, `S.okkake.c` |
| `S.mechi` | Stub tenon / stub mortise 目違い / 目違ほぞ穴 | partly scales | `S.daimochi.ml`, `S.daimochi.mw`, `S.kanawa.m`, `S.kanawa.mw`, `S.okkake.m` |
| `S.eri` | Collar (term unverified) 襟輪 | partly scales | — |
| `S.hozo` | Tenon / mortise 枘 / 枘穴 | fixed size | `S.daimochi.tw`, `S.daimochi.td`, `S.daimochi.tl` |
| `S.sao` | Rod tenon, keyed 竿 | fixed size | — |
| `S.sanmai` | Bridle 三枚組 | partly scales | — |
| `S.kama` | Gooseneck / gooseneck socket 鎌 / 鎌穴 | partly scales | `S.kamatsugi.L`, `S.kamatsugi.hl`, `S.kamatsugi.b`, `S.kamatsugi.e`, `S.kamatsugi.d`, `S.kamatsugi.k` |
| `S.ari` | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | partly scales | `S.aritsugi.A`, `S.aritsugi.e`, `S.aritsugi.n` |
| `S.yatoi` | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | fixed size | `S.daimochi.p`, `S.daimochi.pl` |
| `S.sen` | Peg / peg hole 栓 / 栓穴 | partly scales | `S.kanawa.pg`, `S.okkake.peg` |
| `S.shachi` | Key 車知 | no rule found | — |
| `S.kusabi` | Wedge 楔 | fixed size | — |

**Sizing per form (S.): every rule with its source and evidence; a rule names its joint where the source does, and a two-halved form's rules sit under the half they describe**

**`S.tsuki`** Butt face 突き付け: not restricted (follows the member).

- Shoulder (胴付き dōzuki) set 5分 (c. 15 mm) into the receiving member (rafter beam into post)
- Hanging post: shoulder about 1寸 (c. 30 mm) below the beam soffit, with 1寸 clearance
- *Note:* A plain contact face; its size is the section of the members joined.

**`S.sogi`** Oblique scarf 殺ぎ: scales.

- Daimochi: joint length about 2.5 × depth H
- Daimochi: joint length 2 × H
- Kanawa: the lap centred at half the section across it
- Kanawa: すべり勾配 about 1/24 either side of the 腮

**`S.aikaki`** Halving (half-lap) 相欠き: no rule found.

- No rule found in the sources checked.

**`S.koshi`** Seat 腰掛け: fixed size.

- Seat depth 15 mm (5分)

**`S.tome`** Mitre 留め: not restricted (follows the member).

- Angle 45° (geometry) [geometry]
- Mitre face follows the members, e.g. nageshi 8–9/10 of the post width
- *Note:* Its size is set by the members joined.

**`S.kaki`** Notch 欠き込み: partly scales.

- Notch depth about 5分 (c. 15 mm); length = post width − 1寸 (gate arm through post)
- Eaves beam seated 1–1.5寸 (30–45 mm) on the tie beam
- Cross-halving: depth H/2 (a different case: roof example)

**`S.oire`** Housing 大入れ: partly scales.

- Depth about 1/8 of the post width (beam into through-post, kōnosu)
- Depth 3–4分 (9–12 mm) for secondary members
- Modern standard 15 mm; range 6–15 mm (municipal standard drawings)

**`S.wanagi`** Open slot mortise 輪薙ぎ込み: partly scales.

- Slot width = width of the received member (e.g. ridge beam); housing depth about 2分 (c. 6 mm); tenon split-wedged
- Tenon thickness follows the mortise and tenon rule

**`S.ago`** Cog 渡り腮: fixed size.

- Cog where a plate sits on a beam: 1寸 to 1寸5分 (30 to 45 mm)

**`S.nuki`** Through mortise 貫通し: partly scales.

- Abbreviated gooseneck in a through tie: hook longer than 30 mm, tip 30 mm high, 45°
- Hook height 1/3 to 2/3 of hook length; wedge allowance 15 mm
- Nuki about 1/4 of the post width thick
- Tested 15–60 mm thick in 105–180 mm posts

**`S.hako`** Box housing 箱: no rule found.

- *Note:* No rule found. Proxy: as stub tenon, W/8 to W/7 (inferred).

**`S.ryaku`** Abbreviated gooseneck 略鎌: partly scales.

- Kanawa and okkake: joint length 3 to 3.5 × H
- Kanawa: the 腮 jogs back against the slope at the centre, as deep as the 栓 (1/8 of the section across the lap)
- Kanawa: 2 to 3 × width W; okkake: 2 to 3 × H
- Okkake: at least 8寸 (240 mm)
- Daimochi: step H/10, tip H/4
- Daimochi: step 8分 to 1寸 (24 to 30 mm)
- Jaw (腮): 15 mm, or L/15 to L/20, never above 15 to 30 mm
- Okkake: the central step (腮), width 15–30 mm (5分 to 1寸)
- Tapered mating faces (suberi kōbai) about 1/10

**`S.mechi`** Stub tenon / stub mortise 目違い / 目違ほぞ穴: partly scales.

- 凸 stub tenon: Kanawa and okkake: a square of W/8 to W/7
- Both halves: Depth 15 mm
- 凸 stub tenon: Daimochi: about W/4 square
- 凸 stub tenon: Okkake tongue width W/4 to W/3

**`S.eri`** Collar (term unverified) 襟輪: partly scales.

- Collar cut-out width = width of the post it meets
- *Note:* Depth: no rule found.

**`S.hozo`** Tenon / mortise 枘 / 枘穴: fixed size.

- 凸 tenon: Long tenon in a 120 mm post: 90 × 30 × 117 mm
- 凸 tenon: A 45 mm tenon is about 50% stiffer and stronger than a 30 mm one
- 凸 tenon: Tenon thickness 1/4 to 2/7 of the post width; width 8/10 to 8.5/10

**`S.sao`** Rod tenon, keyed 竿: fixed size.

- Long tenon with keys at W = 120: tenon 30, jaw 7.5, 18 mm, length 240
- Tested D = 30, key 15 at W = 120, i.e. about W/4 and W/16

**`S.sanmai`** Bridle 三枚組: partly scales.

- Each part one third of the member width (general woodworking)

**`S.kama`** Gooseneck / gooseneck socket 鎌 / 鎌穴: partly scales.

- 凸 gooseneck: Gooseneck length 4寸, 5寸 or 6寸 (120, 150, 180 mm), whatever the depth
- 凸 gooseneck: Head = neck = half the gooseneck length
- Both halves: Gooseneck depth H/2
- 凸 gooseneck: Neck width 30 mm (1寸) in every specimen
- 凸 gooseneck: Jaw 7.5 mm each side (5 to 15 tested); head width = neck + 2 × jaw
- Both halves: Tapered mating faces (suberi kōbai) about 1/10 of the depth (1/8 also used)

**`S.ari`** Dovetail / dovetail socket 蟻 / 蟻ほぞ穴: partly scales.

- 凸 dovetail: Neck W/4 to W/3; length W/4 to W/2, design shear length at most 25 mm
- 凸 dovetail: Flare L/8 to L/16
- Both halves: All parts as ratios of the top width

**`S.yatoi`** Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: fixed size.

- Daimochi dowels: 1寸2分 square × 1寸5分 (about 36 × 45 mm)
- Daimochi dowel 30 × 30 mm
- Dowel 太枘: 1寸–1寸4分 square × 2.5–3分 thick, hardwood

**`S.sen`** Peg / peg hole 栓 / 栓穴: partly scales.

- 凸 peg: Kanawa: central peg = stub tenon = W/8 to W/7 square
- 凸 peg: Pegs W/8 to W/6
- 凸 peg: Trade sizes 5分, 6分, 8分, 1寸 (15, 18, 25, 31 mm)
- Both halves: Okkake: 2 pegs at the quarter points; 4 if H > 300 mm
- 凸 peg: Daimochi peg length: 2/3 H in the text, H/2 + 30 in the specimen table
- 凹 peg hole: Drawbore: peg holes deliberately offset about 2 mm
- 凸 peg: Kanawa 栓 at least 15 mm thick
- 凸 peg: Kanawa: tested 栓 15 mm wide
- 凸 peg: Kanawa 栓 tapered, for example 21 to 30 mm
- 凸 peg: Kanawa: 栓 W/8 thick along the beam (15 mm at W = 120) and as deep as the 腮 it fills, 15, 30 or 45 mm (W/8 to 3W/8), through the depth; tested
- 凸 peg: Kanawa: the 栓 a square of 1/8 of the section dimension across the lap, in the 腮 at the centre (W/8 in this model, which stands)

**`S.shachi`** Key 車知: no rule found.

- *Note:* No size rule found. Urakubo et al. tested one long tenon with keys at W = 120 (see Rod tenon, keyed); the key and key-slot sizes they report have not been read here. The kanawa tsugi's lock is modelled as a 栓, so its key rules are under Peg / peg hole.

**`S.kusabi`** Wedge 楔: fixed size.

- Wedge allowance 15 mm

**Sizing per joint (S.): each joint's rule library, every alternative with its source**

Section dimensions (height, width) are the member's, not rules.

**台持継 *daimochi tsugi***

| ID | Dimension | Interface form | Rule | Type |
|---|---|---|---|---|
| `S.daimochi.r` | Joint length (scarf overlap) | Oblique scarf 殺ぎ | 2 H | scales |
|  |  |  | 2 1/2 H (Meiji rule) | scales |
|  |  |  | 3 H (project specimen) | scales |
| `S.daimochi.t` | Tip land | Oblique scarf 殺ぎ | 1/4 H | scales |
|  |  |  | ≈ 1/7 H (project specimen) | scales |
| `S.daimochi.j` | Mid-scarf step height | Abbreviated gooseneck 略鎌 | 1/10 H | scales |
|  |  |  | 9分 (Meiji rule: 8分 to 1寸) | fixed size |
|  |  |  | 1/10 H, kept within 8分 to 1寸 | partly scales |
|  |  |  | 3/10 H (project specimen) | scales |
| `S.daimochi.jr` | Mid-scarf step run | Abbreviated gooseneck 略鎌 | 3/10 H (project specimen) | scales |
|  |  |  | 0 (vertical step) | fixed size |
| `S.daimochi.ml` | Mechigai tongue length | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | scales |
|  |  |  | ≈ 1/7 W (project specimen) | scales |
|  |  |  | no tongue | fixed size |
| `S.daimochi.mw` | Mechigai tongue width | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | scales |
|  |  |  | ≈ 2/7 W (project specimen) | scales |
| `S.daimochi.p` | Dowel size | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 30 mm, about 1寸 | fixed size |
|  |  |  | 1寸2分 (Meiji rule) | fixed size |
|  |  |  | 5分 (Fig. 3.2) | fixed size |
|  |  |  | 1 in (project specimen) | fixed size |
|  |  |  | 1寸 | fixed size |
|  |  |  | 1寸4分 | fixed size |
| `S.daimochi.pl` | Dowel length | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 1/2 H + 30 mm | partly scales |
|  |  |  | 2/3 H | scales |
|  |  |  | 1寸5分 (Meiji rule) | fixed size |
|  |  |  | 1寸 (Fig. 3.2) | fixed size |
|  |  |  | 2.5 in (project specimen) | fixed size |
| `S.daimochi.sd` | Seat housing depth | Housing 大入れ | placeholder, held absolute | fixed size |
|  |  |  | 1寸 (Meiji: 渡り欠き of a 軒桁 on a beam) | fixed size |
|  |  |  | 1寸5分 (Meiji, upper value) | fixed size |
|  |  |  | 0, shoulder bears flat | fixed size |
| `S.daimochi.cd` | Cog depth (beam below) | Cog 渡り腮 | 1/10 H (inferred from the daimochi step) | scales |
|  |  |  | placeholder, held absolute | fixed size |
| `S.daimochi.cw` | Cog width (beam below) | Cog 渡り腮 | 5分 (okkake daisen 腮幅, lower value) | fixed size |
|  |  |  | 1寸 (okkake daisen 腮幅, upper value) | fixed size |
| `S.daimochi.tw` | Post tenon thickness (along the beam) | Tenon / mortise 枘 / 枘穴, 凸 | 30 mm, about 1寸 | fixed size |
|  |  |  | 45 mm (stiffer variant) | fixed size |
|  |  |  | 1/4 of the post width | scales |
|  |  |  | 2/7 of the post width | scales |
| `S.daimochi.td` | Post tenon width (across the beam) | Tenon / mortise 枘 / 枘穴, 凸 | W − 20 mm | partly scales |
|  |  |  | 90 mm | fixed size |
|  |  |  | 8/10 of the post width | scales |
|  |  |  | 8.5/10 of the post width | scales |
| `S.daimochi.tl` | Stub tenon length | Tenon / mortise 枘 / 枘穴, 凸 | 50 mm (短ほぞ, standard) | fixed size |
|  |  |  | 45 mm | fixed size |
|  |  |  | 1寸 (older hand practice) | fixed size |
|  |  |  | 3寸, 90 mm (長ほぞ) | fixed size |
|  |  |  | 120 mm | fixed size |

**腰掛蟻継 *koshikake ari tsugi***

| ID | Dimension | Interface form | Rule | Type |
|---|---|---|---|---|
| `S.aritsugi.A` | Dovetail length 蟻 (shoulder to tip) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴, 凸 | 0.45 W | scales |
|  |  |  | W/2 | scales |
| `S.aritsugi.e` | Flare e, each side (蟻勾配) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴, 凸 | 1:5 of the dovetail length | scales |
|  |  |  | 1:4 of the dovetail length | scales |
|  |  |  | 7.5 mm, 曲尺幅半分 | fixed size |
| `S.aritsugi.n` | Neck width 蟻首 | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴, 凸 | 30 mm (1寸) | fixed size |
|  |  |  | W/4 | scales |
|  |  |  | W/3 | scales |
| `S.aritsugi.sd` | Seat depth 腰掛 (locked to H) | Seat 腰掛け | H/2 | scales |
| `S.aritsugi.s` | Seat length 腰掛 | Seat 腰掛け | 15 mm (5分) | fixed size |
|  |  |  | 30 mm (1寸) | fixed size |

**腰掛鎌継 *koshikake kama tsugi***

| ID | Dimension | Interface form | Rule | Type |
|---|---|---|---|---|
| `S.kamatsugi.L` | 鎌 length (head + neck) | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 5寸 (150 mm) | fixed size |
|  |  |  | 4寸 (120 mm) | fixed size |
|  |  |  | 6寸 (180 mm) | fixed size |
|  |  |  | 1 1/2 W | scales |
|  |  |  | 4寸 (120 mm) | fixed size |
|  |  |  | 5寸 (150 mm) | fixed size |
|  |  |  | 6寸 (180 mm) | fixed size |
| `S.kamatsugi.hl` | Head length | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 1/2 L | scales |
|  |  |  | 1/2 L | scales |
| `S.kamatsugi.b` | Neck width 鎌首 | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 30 mm (1寸) | fixed size |
|  |  |  | 30 mm, kept at or under W/3 | partly scales |
|  |  |  | 30 mm | fixed size |
| `S.kamatsugi.e` | Jaw step, each side | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凸 | 7.5 mm | fixed size |
|  |  |  | 15 mm (wide jaw) | fixed size |
|  |  |  | 5 mm | fixed size |
|  |  |  | 7.5 mm | fixed size |
| `S.kamatsugi.d` | 鎌せい, depth to the seat | Gooseneck / gooseneck socket 鎌 / 鎌穴 | 1/2 H | scales |
|  |  |  | 1/2 H | scales |
| `S.kamatsugi.s` | Seat 腰掛 length | Seat 腰掛け | 15 mm | fixed size |
| `S.kamatsugi.k` | Tapered mating faces (suberi kōbai) スベリ勾配 | Gooseneck / gooseneck socket 鎌 / 鎌穴, 凹 | 1/10 | fixed size |
|  |  |  | 1/8 | fixed size |
|  |  |  | 1/27 | fixed size |
|  |  |  | 1/10 | fixed size |

**金輪継 *kanawa tsugi***

| ID | Dimension | Interface form | Rule | Type |
|---|---|---|---|---|
| `S.kanawa.L` | Joint length L | Oblique scarf 殺ぎ | 3 × せい | scales |
|  |  |  | 3.5 × せい | scales |
|  |  |  | 1.75 + 1.75 | scales |
|  |  |  | 3 × W | scales |
|  |  |  | 4 × W | scales |
| `S.kanawa.slope` | すべり勾配 | Oblique scarf 殺ぎ | 1/24 | fixed size |
| `S.kanawa.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 15 mm (5分) | fixed size |
|  |  |  | 12 mm | fixed size |
|  |  |  | 18 mm | fixed size |
| `S.kanawa.mw` | 目違い (stub tenon), square | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | W/7 | scales |
|  |  |  | W/8 | scales |
|  |  |  | A/7 × 1/7 | scales |
| `S.kanawa.pg` | 栓, square (and the 腮 it sits in) | Peg / peg hole 栓 / 栓穴, 凸 | W/8 = 15 mm at W = 120, across the lap | scales |
|  |  |  | W/7 = 17.1 mm at W = 120 | scales |

**追掛大栓継 *okkake daisen tsugi***

| ID | Dimension | Interface form | Rule | Type |
|---|---|---|---|---|
| `S.okkake.L` | Joint length L | Oblique scarf 殺ぎ | H × 3 (as dimensioned) | scales |
|  |  |  | 3.5 × せい | scales |
|  |  |  | 3 × W | scales |
|  |  |  | 4 × W | scales |
| `S.okkake.slope` | すべり勾配 | Oblique scarf 殺ぎ | 1/10 | fixed size |
| `S.okkake.c` | Step up at the centre | Abbreviated gooseneck 略鎌 | 15 mm (5分) | fixed size |
|  |  |  | L/15, within 15–30 mm (5分 to 1寸) | partly scales |
| `S.okkake.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 15 mm (5分) | fixed size |
|  |  |  | 12 mm | fixed size |
|  |  |  | 18 mm | fixed size |
| `S.okkake.peg` | 込栓 draw pin, square | Peg / peg hole 栓 / 栓穴, 凸 | W/8 | scales |
|  |  |  | W/6 | scales |



**The dimensions where sources disagree**

| ID | Dimension | Interface form |
|---|---|---|
| `S.daimochi.r` | Joint length (scarf overlap) | Oblique scarf 殺ぎ |
| `S.daimochi.t` | Tip land | Oblique scarf 殺ぎ |
| `S.daimochi.j` | Mid-scarf step height | Abbreviated gooseneck 略鎌 |
| `S.daimochi.jr` | Mid-scarf step run | Abbreviated gooseneck 略鎌 |
| `S.daimochi.ml` | Mechigai tongue length | Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| `S.daimochi.mw` | Mechigai tongue width | Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| `S.daimochi.p` | Dowel size | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い |
| `S.daimochi.pl` | Dowel length | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い |
| `S.daimochi.tw` | Post tenon thickness (along the beam) | Tenon / mortise 枘 / 枘穴 |
| `S.daimochi.td` | Post tenon width (across the beam) | Tenon / mortise 枘 / 枘穴 |
| `S.daimochi.tl` | Stub tenon length | Tenon / mortise 枘 / 枘穴 |
| `S.aritsugi.A` | Dovetail length 蟻 (shoulder to tip) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 |
| `S.aritsugi.e` | Flare e, each side (蟻勾配) | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 |
| `S.aritsugi.n` | Neck width 蟻首 | Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 |
| `S.kamatsugi.L` | 鎌 length (head + neck) | Gooseneck / gooseneck socket 鎌 / 鎌穴 |
| `S.kamatsugi.e` | Jaw step, each side | Gooseneck / gooseneck socket 鎌 / 鎌穴 |
| `S.kamatsugi.k` | Tapered mating faces (suberi kōbai) スベリ勾配 | Gooseneck / gooseneck socket 鎌 / 鎌穴 |
| `S.kanawa.L` | Joint length L | Oblique scarf 殺ぎ |
| `S.kanawa.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| `S.kanawa.mw` | 目違い (stub tenon), square | Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| `S.kanawa.pg` | 栓, square (and the 腮 it sits in) | Peg / peg hole 栓 / 栓穴 |
| `S.okkake.L` | Joint length L | Oblique scarf 殺ぎ |
| `S.okkake.c` | Step up at the centre | Abbreviated gooseneck 略鎌 |
| `S.okkake.m` | L toe (目違い) | Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| `S.okkake.peg` | 込栓 draw pin, square | Peg / peg hole 栓 / 栓穴 |

## 4. Process rules

Attributes in brackets: *availability*: standard pre-cut / special machines only / hand only; *set-ups*: one set-up / several set-ups; *sequence*: before assembly / after assembly / last; *component*: integral / separate piece; *route*: rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them) / machined off-line (lathe, saw, planer, CNC) or bought ready-made; *still manual*: final fitting, where it draws tight / fitting and driving the separate piece / paring, where the fit needs it / a square hole, unless a hollow chisel or chisel unit cuts it.

| Interface form | Assembly (AS) | Disassembly (DS) | Repair (RP) | Hand (手刻み, HF) | CNC (プレカット, DF) | Stays manual |
|---|---|---|---|---|---|---|
| Butt face 突き付け | — | — | — | Cross-cutting (HF3), rule P17, predicted; Planing (HF6), rule P20, predicted | Cutting to length (DF1), rule P24, predicted; Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted | — |
| Oblique scarf 殺ぎ | Lowered from above (AS2), rule P1, confirmed | — | Needs headroom (RP2), rule P12, predicted | Rip-sawing (HF2), rule P16, confirmed; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, confirmed | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Halving (half-lap) 相欠き | Lowered from above (AS2), rule P1, confirmed | — | Needs headroom (RP2), rule P12, predicted | Rip-sawing (HF2), rule P16, confirmed; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Seat 腰掛け | Set first (AS1), documented; Lowered from above (AS2), rule P1, confirmed; Held by load above (AS6), rule P7, confirmed | — | Needs headroom (RP2), rule P12, predicted; Unload from above (RP3), rule P13, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Mitre 留め | — | — | — | Cross-cutting (HF3), rule P17, predicted; Planing (HF6), rule P20, predicted | Cutting to length (DF1), rule P24, predicted; Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted | — |
| Notch 欠き込み | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Housing 大入れ | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Open slot mortise 輪薙ぎ込み | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Cog 渡り腮 | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Through mortise 貫通し | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Box housing 箱 | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Abbreviated gooseneck 略鎌 | Lowered from above (AS2), rule P1, confirmed; Side, then axial (AS3), documented; Draw tight (AS4), rule P6, confirmed | Lift against friction (DS2), rule P9, confirmed | Needs side clearance (RP1), documented; Needs headroom (RP2), rule P12, confirmed | Rip-sawing (HF2), rule P16, confirmed; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, confirmed; Fitting and finishing (HF8) [last], rule P22, confirmed | Roughing (DF2) [special machines only, standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [special machines only, standard pre-cut, one set-up], rule P25, confirmed; Re-clamping for a new set-up (DF5) [several set-ups], documented; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [final fitting, where it draws tight, paring, where the fit needs it], rule P31, P31, predicted | Fitting and finishing (HF8) [last], rule P22, confirmed; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [final fitting, where it draws tight, paring, where the fit needs it], rule P31, P31, predicted |
| Stub tenon / stub mortise 目違い / 目違ほぞ穴 | Side, then axial (AS3), rule P2, confirmed | Shift, then out sideways (DS3), rule P10, confirmed | Needs side clearance (RP1), rule P11, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, predicted; Planing (HF6), documented; Fitting and finishing (HF8) [last], documented | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; Re-clamping for a new set-up (DF5) [several set-ups], documented; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, confirmed; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | Fitting and finishing (HF8) [last], documented; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, confirmed; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Collar (term unverified) 襟輪 | Lowered from above (AS2), rule P1, predicted | — | Needs headroom (RP2), rule P12, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Tenon / mortise 枘 / 枘穴 | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted; Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Rod tenon, keyed 竿 | Draw tight (AS4), rule P6, predicted; Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted; Fitting and finishing (HF8) [last], rule P22, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [final fitting, where it draws tight, paring, where the fit needs it], rule P31, P31, predicted | Fitting and finishing (HF8) [last], rule P22, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [final fitting, where it draws tight, paring, where the fit needs it], rule P31, P31, predicted |
| Bridle 三枚組 | Pushed in along the axis (AS7), rule P3, predicted | — | Needs axial clearance (RP5), rule P14, predicted | Rip-sawing (HF2), rule P16, predicted; Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, predicted; Paring (HF5), rule P19, predicted; Planing (HF6), rule P20, predicted | Roughing (DF2), rule P26, predicted; Finishing (DF3), rule P26, predicted; Re-clamping for a new set-up (DF5) [several set-ups], rule P26, predicted; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Gooseneck / gooseneck socket 鎌 / 鎌穴 | Lowered from above (AS2), rule P1, confirmed; Held by load above (AS6), rule P7, confirmed | — | Needs headroom (RP2), rule P12, predicted; Unload from above (RP3), rule P13, predicted | Rip-sawing (HF2), documented; Cross-cutting (HF3), rule P17, confirmed; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, confirmed | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 | Lowered from above (AS2), rule P1, confirmed; Held by load above (AS6), rule P7, confirmed | — | Needs headroom (RP2), rule P12, predicted; Unload from above (RP3), rule P13, predicted | Cross-cutting (HF3), rule P17, predicted; Chiselling (HF4), rule P18, confirmed; Paring (HF5), rule P19, predicted | Roughing (DF2) [standard pre-cut, one set-up], rule P25, confirmed; Finishing (DF3) [standard pre-cut, one set-up], rule P25, confirmed; squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted | squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted |
| Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | Set first (AS1), rule P4, predicted | — | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece], rule P23, predicted; Chiselling (HF4), rule P18, predicted; Planing (HF6) [separate piece], rule P23, predicted | Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made, a square hole, unless a hollow chisel or chisel unit cuts it], rule P30, P32, predicted | Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made, a square hole, unless a hollow chisel or chisel unit cuts it], rule P30, P32, predicted |
| Peg / peg hole 栓 / 栓穴 | Draw tight (AS4), rule P6, confirmed; Lock goes in last (AS5), rule P5, confirmed | Lock comes out first (DS1), rule P8, confirmed | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece], rule P23, predicted; Planing (HF6) [separate piece], rule P23, predicted; Boring peg holes (HF7), rule P21, predicted; Fitting and finishing (HF8) [last], rule P22, predicted | Drilling (DF4) [after assembly, special machines only], rule P29, confirmed; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made, a square hole, unless a hollow chisel or chisel unit cuts it], rule P30, P32, predicted | Fitting and finishing (HF8) [last], rule P22, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made, a square hole, unless a hollow chisel or chisel unit cuts it], rule P30, P32, predicted |
| Key 車知 | Draw tight (AS4), rule P6, predicted; Lock goes in last (AS5), rule P5, predicted | Lock comes out first (DS1), rule P8, predicted | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece], rule P23, predicted; Chiselling (HF4), rule P18, predicted; Planing (HF6) [separate piece], rule P23, predicted; Fitting and finishing (HF8) [last], rule P22, predicted | Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made, a square hole, unless a hollow chisel or chisel unit cuts it], rule P30, P32, predicted | Fitting and finishing (HF8) [last], rule P22, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made, a square hole, unless a hollow chisel or chisel unit cuts it], rule P30, P32, predicted |
| Wedge 楔 | Draw tight (AS4), rule P6, predicted; Lock goes in last (AS5), rule P5, predicted | Lock comes out first (DS1), rule P8, predicted | Cheap part to replace (RP4), rule P15, predicted | Rip-sawing (HF2) [separate piece], rule P23, predicted; Planing (HF6) [separate piece], rule P23, predicted; Fitting and finishing (HF8) [last], rule P22, predicted | Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made], rule P30, predicted | Fitting and finishing (HF8) [last], rule P22, predicted; Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made], rule P30, predicted |

**The process rules (P1–P32): each gives links from a form's geometry**

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
| P23 | a separate piece | made on its own, rip-sawn and planed by hand (or off-line, P30) |
| P24 | an end face, no recess | cut to length |
| P25 | open to one face, no undercut | roughed and finished in one set-up |
| P26 | open to more than one face, or through | several set-ups |
| P27 | an undercut | special machines only |
| P28 | square inside corners, where only rotating cutters are used (a rotating cutter leaves them round, to its radius; a hollow chisel, chisel-mortising unit or robot chisel cuts them square, or a relief or a rounded mating part accepts them) | squared by hand |
| P29 | a hole through both members, drawn tight | drilled after assembly |
| P30 | a separate piece (dowel, peg, key, wedge), machined off-line (lathe, saw, planer, CNC) or bought ready-made | fitted and driven by hand |
| P31 | a form that draws tight, or fit-critical faces inside a recess | final fitting and paring stay manual on every route |
| P32 | a square hole for a separate piece (pin, dowel, key) | squared by hand unless a hollow chisel or chisel unit cuts it |

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
- Digital fabrication (CNC / プレカット): **Post-processing: squaring corners and filing** (DF6). Tools: chisel, file. No BTLx processing: by hand after the machine; only where the route has rotating cutters only.
- Digital fabrication (CNC / プレカット): **Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach** (DF7). Tools: chisels, planes, mallet. No BTLx processing: by hand, whatever the machine.

## 4b. General rules (G)

Rules that hold for every joint, as the viewer applies them in its assembly, take-apart and repair.

| Rule | Rule text |
|---|---|
| G1 | A separate locking piece (pin, peg, wedge, key) goes in last and comes out first. |
| G2 | A part comes out when it has a clear straight path out, as measured from the contact between the parts (or a short slide then a turn); what is still held waits for what holds it. |
| G3 | To replace a part, take out every part that blocks it, and what blocks those; a part it carries (blind dowels set into it) is moved to the new part and reused. |
| G4 | Where both elements are one part turned end for end, one spare serves for either. |

## 4c. Joint-level rules (J)

Rules for the joint as a whole. Their outcomes are recorded per joint, apart from the form-level links of section 4, which they do not change: a form keeps its own links, and the joint adds its own assembly outcome on the forms of its primary interface.

| Rule | Rule text |
|---|---|
| J1 | A joint's assembly direction comes from its primary interface (the one between its two elements) as a whole: the reverse of the way the upper element was measured to leave, from the contact between the parts. It replaces each of that interface's forms' own direction. |
| J2 | A joint with no driven lock in its configuration (no pin, peg, wedge or bolt) is held by the load from above, on each form of its primary interface. |

| Joint | Configuration | The upper element leaves | Joint-level outcomes | On the forms |
|---|---|---|---|---|
| 台持継 *daimochi tsugi* | support: post below, tenon through both pieces; locking: dowels | +z (up) | Lowered from above (AS2), rule J1; Held by load above (AS6), rule J2 | Oblique scarf 殺ぎ, Abbreviated gooseneck 略鎌, Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| 腰掛蟻継 *koshikake ari tsugi* | reinforcement: none | +z (up) | Lowered from above (AS2), rule J1; Held by load above (AS6), rule J2 | Seat 腰掛け, Dovetail / dovetail socket 蟻 / 蟻ほぞ穴 |
| 腰掛鎌継 *koshikake kama tsugi* | variant: plain | +z (up) | Lowered from above (AS2), rule J1; Held by load above (AS6), rule J2 | Seat 腰掛け, Gooseneck / gooseneck socket 鎌 / 鎌穴 |
| 金輪継 *kanawa tsugi* | variant: 栓 pin | +x for 15 mm, then -y | Side, then axial (AS3), rule J1 | Oblique scarf 殺ぎ, Abbreviated gooseneck 略鎌, Stub tenon / stub mortise 目違い / 目違ほぞ穴 |
| 追掛大栓継 *okkake daisen tsugi* | variant: 込栓 draw pins × 2 | +z, -z | Lowered from above (AS2), rule J1 | Oblique scarf 殺ぎ, Abbreviated gooseneck 略鎌, Stub tenon / stub mortise 目違い / 目違ほぞ穴 |

## 4d. Context rules (X)

Rules that apply once the joint is placed in a building.

| Rule | Rule text | Joints |
|---|---|---|
| X1 | Continue the splice 150–300 mm (柱心から5寸–1尺) past the support and away from mid-span. | 金輪継 *kanawa tsugi*, 追掛大栓継 *okkake daisen tsugi* |
| X2 | The daimochi sits over a support: a post below (its tenon through both pieces or a stub), a post above, or a beam below with a cog. | 台持継 *daimochi tsugi* |
| X3 | Before a part that carries load is taken out, shore what it carries (a temporary post, props). | 台持継 *daimochi tsugi*, 腰掛蟻継 *koshikake ari tsugi*, 腰掛鎌継 *koshikake kama tsugi*, 金輪継 *kanawa tsugi*, 追掛大栓継 *okkake daisen tsugi* |
| X4 | On an eaves beam the 金輪継 is joined before the beam is laid on the posts. | 金輪継 *kanawa tsugi* |
| X5 | A member longer or heavier than the machine takes is cut by hand, whatever the route (DF7). | 台持継 *daimochi tsugi*, 腰掛蟻継 *koshikake ari tsugi*, 腰掛鎌継 *koshikake kama tsugi*, 金輪継 *kanawa tsugi*, 追掛大栓継 *okkake daisen tsugi* |

## 4e. Machining rules (M)

Which cutter makes a CNC pass, from what the cutter can leave (tool capability). They choose how a digital-fabrication outcome is made; they add no link.

| Rule | Rule text | Outcome |
|---|---|---|
| M1 | A sloped face is finished with the flat cutter at a fine step-over (1/4 in, 1.5 mm) where the stairs it leaves, step-over × gradient, stay within 0.1 mm, a third of the 0.3 mm fit clearance; a steeper slope with the ball end (1/4 in, 0.635 mm). | Finishing (DF3) |
| M2 | A pocket deeper than the cutter reaches (its flute length) is left for the hand (DF7), unless a longer-reach cutter or a further set-up reaches it. | Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) |

## Sequence rules (Q)

The order of the making steps. For each joint and route they give a precedence graph; one sequence is chosen by tie-breaks: by hand, one feature at a time from the datum outward; on the CNC, fewest set-ups, then fewest tool changes, then travel. Steps no rule orders are in any order; separate pieces are a parallel branch.

| Rule | Rule text |
|---|---|
| Q1 | Datum faces are prepared and centre lines marked before any feature is laid out; all marking comes before cutting. |
| Q2 | By hand, the saw kerfs that bound a recess or a shoulder come before chiselling out the waste between them. |
| Q3 | Rough before finish: by hand, rough chopping inside the line before paring to it; on the CNC, the roughing tool before the finishing tool. |
| Q4 | Fit-critical faces are finished last, before fitting; paring and fitting may alternate. |
| Q5 | Assembly comes after both mating parts are complete; locks go in last and come out first (as G1). |
| Q6 | On the CNC, one set-up per direction the tool approaches from; within a set-up, the cuts are grouped by tool. |
| Q7 | Separate pieces (dowels, pegs, wedges, keys) are made on an independent branch, before assembly. |

## 5. Derivation example: daimochi tsugi

Each step applies the rules named on the right; the IDs are those of sections 2–4.

| Step | Result | Rule applied |
|---|---|---|
| 1. Components | lower element, upper element (the same part, turned end for end), two dowels, a post below | the daimochi's components with two options chosen: locking by dowels (`C.daimochi.2`) and a post below (`C.daimochi.4`) |
| 2. Interfaces | beam–beam; dowel–element (each of two dowels in both elements); post–element | `C.daimochi.1`, `C.daimochi.2`, `C.daimochi.4` |
| 3. Interface forms | Oblique scarf 殺ぎ + Abbreviated gooseneck 略鎌 + Stub tenon / stub mortise 目違い / 目違ほぞ穴 ×2; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い (dowels); Tenon / mortise 枘 / 枘穴 + Housing 大入れ | the right-hand sides of `C.daimochi.1`, .2 and .4 |
| 4. Sizes | joint 240, tip land 30, step 12 high and 36 long, tongues 30 × 30, dowels 30 square × 90, housing 5.3 deep, tenon 30 × 100 × 114.7 (mm). Checks: 9 pass, 3 warn | the first rule of each dimension: `S.daimochi.r`, `S.daimochi.t`, `S.daimochi.j`, `S.daimochi.jr`, `S.daimochi.ml`, `S.daimochi.mw`, `S.daimochi.p`, `S.daimochi.pl`, `S.daimochi.sd`, `S.daimochi.tw`, `S.daimochi.td`; the tenon's length from the geometry |
| 5. Assembly | dowels and post below → lower piece → upper piece | form rules, which hold across joints: Oblique scarf 殺ぎ: Lowered from above (AS2), rule P1, confirmed; Abbreviated gooseneck 略鎌: Lowered from above (AS2), rule P1, confirmed, Side, then axial (AS3), documented, Draw tight (AS4), rule P6, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Side, then axial (AS3), rule P2, confirmed; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: Set first (AS1), rule P4, predicted; Tenon / mortise 枘 / 枘穴: Pushed in along the axis (AS7), rule P3, predicted; Housing 大入れ: Pushed in along the axis (AS7), rule P3, predicted; the order itself from the contact between the parts (what blocks what) |
| 6. Disassembly | upper piece and post below → lower piece and dowels | form rules, which hold across joints: Abbreviated gooseneck 略鎌: Lift against friction (DS2), rule P9, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Shift, then out sideways (DS3), rule P10, confirmed; the order from the same contact |
| 7. Repair set | lower piece: take out upper piece; move the dowels to the new piece (reused); upper piece: nothing else comes out; dowels: take out upper piece; post below: nothing else comes out | form rules, which hold across joints: Oblique scarf 殺ぎ: Needs headroom (RP2), rule P12, predicted; Abbreviated gooseneck 略鎌: Needs side clearance (RP1), documented, Needs headroom (RP2), rule P12, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Needs side clearance (RP1), rule P11, predicted; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: Cheap part to replace (RP4), rule P15, predicted; Tenon / mortise 枘 / 枘穴: Needs axial clearance (RP5), rule P14, predicted; Housing 大入れ: Needs axial clearance (RP5), rule P14, predicted; G3: each set from the contact, what must come out before the part can, and what it carries moved to the new part |
| 8. Hand route (手刻み) | prepare the timber (planing) → marking out (sumitsuke) → cut the scarf slope (rip-sawing, cross-cutting) → cut the step at the centre (chiselling) → cut the tongue at the tip, and its cut-out (sawing, chiselling) → cut the dowel holes (chiselling) → make the second piece → fit (paring, planing) → assemble (fitting) | form rules, which hold across joints: Oblique scarf 殺ぎ: Rip-sawing (HF2), rule P16, confirmed, Cross-cutting (HF3), rule P17, confirmed, Chiselling (HF4), rule P18, predicted, Paring (HF5), rule P19, predicted, Planing (HF6), rule P20, confirmed; Abbreviated gooseneck 略鎌: Rip-sawing (HF2), rule P16, confirmed, Cross-cutting (HF3), rule P17, confirmed, Chiselling (HF4), rule P18, confirmed, Paring (HF5), rule P19, predicted, Planing (HF6), rule P20, confirmed, Fitting and finishing (HF8) [last], rule P22, confirmed; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Cross-cutting (HF3), rule P17, predicted, Chiselling (HF4), rule P18, confirmed, Paring (HF5), rule P19, predicted, Planing (HF6), documented, Fitting and finishing (HF8) [last], documented; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: Rip-sawing (HF2) [separate piece], rule P23, predicted, Chiselling (HF4), rule P18, predicted, Planing (HF6) [separate piece], rule P23, predicted; Tenon / mortise 枘 / 枘穴: Rip-sawing (HF2), rule P16, predicted, Cross-cutting (HF3), rule P17, predicted, Chiselling (HF4), rule P18, predicted, Paring (HF5), rule P19, predicted, Planing (HF6), rule P20, predicted; Housing 大入れ: Cross-cutting (HF3), rule P17, predicted, Chiselling (HF4), rule P18, predicted, Paring (HF5), rule P19, predicted; in the order of the documented sequence |
| 9. CNC route (プレカット) | model → program the toolpaths → mill test pieces (roughing (½ in end mill)) → rough out (roughing (½ in end mill)) → refine (finishing (¼ in end mill)) → finish (finishing (ball-nose cutter)) → second piece (roughing (½ in end mill), finishing (¼ in end mill), finishing (ball-nose cutter)) → post-process (squaring corners and filing) → assemble (fitting) | form rules, which hold across joints: Oblique scarf 殺ぎ: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted, Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted; Abbreviated gooseneck 略鎌: Roughing (DF2) [special machines only, standard pre-cut, one set-up], rule P25, confirmed, Finishing (DF3) [special machines only, standard pre-cut, one set-up], rule P25, confirmed, Re-clamping for a new set-up (DF5) [several set-ups], documented, squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted, Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [final fitting, where it draws tight, paring, where the fit needs it], rule P31, P31, predicted; Stub tenon / stub mortise 目違い / 目違ほぞ穴: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, Re-clamping for a new set-up (DF5) [several set-ups], documented, squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, confirmed, Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted; Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い: Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [fitting and driving the separate piece, machined off-line (lathe, saw, planer, CNC) or bought ready-made, a square hole, unless a hollow chisel or chisel unit cuts it], rule P30, P32, predicted; Tenon / mortise 枘 / 枘穴: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted, Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted; Housing 大入れ: Roughing (DF2) [standard pre-cut, one set-up], rule P25, predicted, Finishing (DF3) [standard pre-cut, one set-up], rule P25, predicted, squaring corners and filing (DF6) [rotating cutters only (a chisel unit cuts the corners square; a relief or a rounded mating part accepts them)], rule P28, predicted, Still manual on every route: final fitting, fitting and driving locks, paring where the fit needs it, square holes, what the cutter cannot reach (DF7) [paring, where the fit needs it], rule P31, predicted; in the order of the documented sequence |

**Step 4 in full: each size and the rule that gives it**

| Rule | Dimension | Interface form | Rule applied | Value |
|---|---|---|---|---|
| `S.daimochi.r` | Joint length (scarf overlap) | Oblique scarf 殺ぎ | 2 H | 240 mm |
| `S.daimochi.t` | Tip land | Oblique scarf 殺ぎ | 1/4 H | 30 mm |
| `S.daimochi.j` | Mid-scarf step height | Abbreviated gooseneck 略鎌 | 1/10 H | 12 mm |
| `S.daimochi.jr` | Mid-scarf step run | Abbreviated gooseneck 略鎌 | 3/10 H (project specimen) | 36 mm |
| `S.daimochi.ml` | Mechigai tongue length | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | 30 mm |
| `S.daimochi.mw` | Mechigai tongue width | Stub tenon / stub mortise 目違い / 目違ほぞ穴, 凸 | 1/4 W (Meiji rule) | 30 mm |
| `S.daimochi.p` | Dowel size | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 30 mm, about 1寸 | 30 mm |
| `S.daimochi.pl` | Dowel length | Loose tenon (dowel, butterfly key; term unverified for yatoi) 雇い | 1/2 H + 30 mm | 90 mm |
| `S.daimochi.sd` | Seat housing depth | Housing 大入れ | placeholder, held absolute | 5.3 mm |
| `S.daimochi.tw` | Post tenon thickness (along the beam) | Tenon / mortise 枘 / 枘穴, 凸 | 30 mm, about 1寸 | 30 mm |
| `S.daimochi.td` | Post tenon width (across the beam) | Tenon / mortise 枘 / 枘穴, 凸 | W − 20 mm | 100 mm |
| geometry | Through tenon length | Tenon / mortise 枘 / 枘穴, 凸 | H − housing depth: through both elements | 114.7 mm |

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
