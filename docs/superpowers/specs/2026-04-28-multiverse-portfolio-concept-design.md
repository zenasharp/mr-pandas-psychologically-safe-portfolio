# Multiverse Portfolio — Concept & Mood Board (Phase 1 Output)

**Date:** 2026-04-28
**Owner:** zenasharp (quangcan207@gmail.com)
**Phase:** 1 — Concept & Mood Board (theo [roadmap.md](../../../roadmap.md))
**Type:** Personal showcase / "about me" site — KHÔNG nhắm đến hiring.

---

## 1. Concept (1 câu)

> *"Một phiên bản cười toe trong quần đùi Perry, du hành qua 6 vũ trụ ký ức và đam mê — từ bảng đen tuổi thơ tới khoảnh khắc phi thăng tiên giới — kể câu chuyện về một con người được làm nên bởi những thế giới hắn từng yêu."*

**Vibe:** paper-craft scrapbook + multiverse hopping + nostalgic.

**Title (tạm — chốt sau ở Phase 6 polish):** "Quangverse" / "Multiverse of Me" / "6 Worlds I've Lived In" / TBD bởi user.

---

## 2. Avatar (nhân vật chính)

**Avatar = chính user**, vẽ side view, đi/đứng hướng phải (cùng hướng camera đi dọc curve).

**Cố định xuyên suốt 6 scenes (vẽ 1 lần, copy + paste):**
- Mặt cười cố định — chấm mắt + miệng cười hình chữ U.
- **Quần đùi Perry the Platypus** — xanh lá, pattern argyle/caro nhỏ. Đây là signature.
- Áo trắng/cream làm base layer.
- Tay chân style đơn giản (que/ống, tỉ lệ paper-craft).

**Flexible parts (đổi mỗi scene):**
- Tóc (kiểu/màu)
- Mũ / accessory đầu
- Vật cầm tay (prop)
- Outfit phụ thêm (áo khoác / armor / áo dài...)

**Lưu ý vẽ Krita:**
- Body base + mặt + quần Perry vẽ 1 file `.kra` master, mỗi flex part ở **layer riêng** để Blender swap/spritesheet được (transcript V2 ~3:15 và Phase 2 step 4 trong roadmap).
- Canvas size giữ nguyên cho mọi outfit (KHÔNG adjust to layer content) — để Blender swap texture không lệch.

---

## 3. Hành trình — 6 scenes dọc camera curve

**Pattern energy curve:** chill nostalgia → cute wonder → magical wonder → energetic peak → intense battle → epic finale → loop về start.

**Loop logic:** Scene 6 (kiếm hiệp phi thăng → bay lên mây) → camera fly up → wrap về Scene 1 (mây tan ra thành phấn bảng đen). Thematic: vòng luân hồi.

| # | Scene | Energy | Accent color direction |
|---|---|---|---|
| 1 | **Trường học** (start) | chill nostalgia | đỏ gạch + xanh bảng |
| 2 | **Doraemon's pocket** | cute wonder | xanh dương Doraemon |
| 3 | **Disney world** | magical wonder | hồng pastel + vàng cổ tích |
| 4 | **Pop music stage** | energetic peak | tím neon + hồng |
| 5 | **Summoner's Rift (LoL)** | intense battle | xanh team + tím nexus |
| 6 | **Kiếm hiệp — phi thăng** (finale → loop) | epic | đen mực + xanh tre |

**Chi tiết outfit + props per scene:** TBD bởi user trong quá trình vẽ Krita ở Phase 2. User tự brainstorm khi cầm bút lên vẽ — design doc chỉ chốt skeleton (tên scene, thứ tự, accent direction).

**Constraint quan trọng (đã chốt):**
- Đồng nhất visual style "paper craft đơn giản" xuyên suốt 6 scenes — KHÔNG vẽ mỗi scene 1 style riêng (Doraemon manga ≠ ink wash kiếm hiệp...). Chỉ đổi **outfit + props iconic** để nhận diện vũ trụ.
- 3-5 prop iconic / scene là đủ. Đừng vẽ quá nhiều.

---

## 4. Bảng màu

### Base palette (xuyên suốt mọi scene — KHÔNG đổi)

| Token | Hex | Mục đích |
|---|---|---|
| `paper-cream` | `#F4EDE0` | Background paper texture (giấy notebook ngả vàng nhẹ) |
| `outline-ink` | `#1A1A1A` | Outline tất cả mọi thứ vẽ (NOT pure black, hơi mềm) |
| `pencil-shadow` | `#8B7E6E` | Shading nhẹ, kiểu chì 2B |
| `notebook-line` | `#B8C5D0` | Line kẻ ngang giấy notebook (paper texture overlay) |

### Paper texture pipeline

Layer overlay notebook lines + grain, **Multiply** blend mode trong Blender (theo V2 transcript ~22:00–24:00, nhóm node `paper_combined`).

### Accent color mỗi scene

User tự pick chính xác lúc vẽ — đây là **direction**, không phải hex cứng:

- Scene 1 trường học → đỏ gạch + xanh bảng
- Scene 2 Doraemon → xanh dương đặc trưng
- Scene 3 Disney → hồng pastel + vàng
- Scene 4 Pop music → tím neon + hồng
- Scene 5 LoL → xanh team + tím nexus
- Scene 6 Kiếm hiệp → đen mực + xanh tre

**Rule cứng:** Mỗi scene chỉ dùng **base palette + 1-2 accent color**. KHÔNG dùng quá 2 accent/scene để không loè.

---

## 5. Text content

Mỗi scene có **1 câu / đoạn ngắn personal** về user (option C — diary scrolling vibe).

**Kỹ thuật:** Phase 6 polish sẽ add `troika-three-text` (theo V2). Tốn ~1-2h ở phase đó. KHÔNG add ở Phase 4-5.

**Content TBD:** User viết 6 câu này trong Phase 6, một câu/scene. Gợi ý content (chỉ là ví dụ):
- Scene 1: gì đó về tuổi thơ trường học VN
- Scene 5: gì đó về peak rank / vai trò chơi LoL
- ...

User tự fill, không phải task của Claude.

---

## 6. Mood board references

### Aesthetic anchors (3 sites)

1. **Mr. Panda** (V2 — repo hiện tại) — paper texture quality, camera looping refactored.
2. **Aimee Wei** (V1 — `../aimee-weis-papercraft-world/`) — cute paper craft simplicity, code reference dễ.
3. **1 site Awwwards** — user browse [awwwards.com](https://awwwards.com) ở Phase 2, pick 1 site có mood gần nhất, note URL vào file mood board.

### Style references (user tự fill ở Phase 2)

- 3-5 ảnh Pinterest về paper craft / scrapbook style → save vào folder `mood/style/`
- 3-5 ảnh per scene về mỗi vũ trụ (Doraemon classic art, kiếm hiệp ink wash painting, LoL map screenshot, Disney castle silhouette, ...) → save vào `mood/scenes/<scene-name>/`

### Mood board không block Phase 2

User có thể vừa fill mood vừa vẽ scene tương ứng. Trước khi vẽ scene N, fill mood của scene N. Tránh fill mood toàn bộ 6 scene 1 lượt rồi mới vẽ — risk scope creep.

---

## 7. Output Phase 1 (acceptance criteria)

Phase 1 hoàn tất khi user có:

- [x] 1 câu concept (section 1).
- [x] List 6 scenes có thứ tự + accent direction (section 3).
- [x] Bảng màu base hex (section 4).
- [x] Avatar base + flex parts định nghĩa (section 2).
- [ ] Folder `mood/style/` + `mood/scenes/<scene>/` với references (user fill ở Phase 2 — không block).
- [ ] 1 site Awwwards anchor URL (user fill ở Phase 2).

**Phase 2 dependency:** chỉ cần section 1-4 + avatar base định nghĩa là đủ vào Phase 2. Mood references có thể fill song song.

---

## 8. Out of scope (Phase 1)

- KHÔNG vẽ Krita (Phase 2).
- KHÔNG vào Blender (Phase 3).
- KHÔNG code (Phase 4+).
- KHÔNG chốt 6 câu text content (Phase 6).
- KHÔNG chốt title cuối cùng (Phase 6).

---

## 9. Anti-patterns (đã agreed)

- ❌ Mỗi scene 1 visual style riêng (x3 effort Phase 2 — đã reject ở Câu 4).
- ❌ Bảng màu mỗi scene full màu riêng (rối, đã reject ở Câu 5 — chọn option B base + accent).
- ❌ Vẽ avatar 6 lần với face khác nhau (đã chốt face cố định ở Câu 7).
- ❌ Vẽ avatar 3/4 view (khó nhất quán — chốt side view).
- ❌ Pure black outline `#000000` (cứng, không match paper feel — chốt `#1A1A1A`).

---

## 10. Next steps

1. User confirm spec này.
2. Claude invoke `superpowers:writing-plans` skill để viết implementation plan cho Phase 2 (Krita drawing schedule + asset list cụ thể).
3. Sau khi plan xong → user vào Phase 2 thực thi (vẽ Krita).
