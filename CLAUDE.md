# CLAUDE.md

Hướng dẫn cho Claude Code khi làm việc trong repo này. Đọc kỹ trước khi đề xuất bất kỳ thay đổi nào.

---

## Repo này là gì

**Đây là REFERENCE REPO, không phải project đang phát triển.**

- Tên: Mr. Panda's Psychologically Safe Portfolio (gọi tắt là **V2**).
- Tác giả gốc: Andrew Woan. Repo gốc đã thắng FWA of the Day và Awwwards SOTD.
- Live: https://www.mr-pandas-psychologically-safe-portfolio.com/
- Tutorial YouTube: https://www.youtube.com/watch?v=zyWD2E8AHCg

User (zenasharp) clone repo này về để **học cách làm site cùng style cho riêng mình**, KHÔNG phải để đóng góp/sửa repo này. Repo gốc chỉ đọc — coi như tài liệu tham khảo.

---

## Repo sibling V1 (cũng là reference)

User đã clone repo cũ hơn của cùng tác giả về cùng cấp:

- Path: `../aimee-weis-papercraft-world/`
- Tên: Aimee Wei's Papercraft World (**V1**).
- Tutorial YouTube: https://www.youtube.com/watch?v=AD01pTr3gvw

**Quan hệ V1 ↔ V2:**

- V1 ra đời trước. Tác giả tự thừa nhận một số design choice trong V1 là "lười" (4 plane riêng thay vì spritesheet, transition curve gây giật khi looping).
- V2 là refactor sạch hơn của cùng concept. Tác giả nói trong transcript V2: *"this project is just a better version of this project"*.
- **Code stack V1 đơn giản hơn V2** (không react-router, không MIDI audio, không troika 3D text, không react-transition-group).

**Khi user vibe-code project mới, ưu tiên reference theo bảng sau:**

| Topic | Repo dùng | Lý do |
|---|---|---|
| Project structure, App.jsx, Lenis setup | V1 | Đơn giản, dễ đọc |
| `raw_assets/` + `npm run gen:models` pipeline | V1 only | V2 không có |
| Camera curve looping | **V2** | V1 clunky, V2 refactored |
| Aesthetic, paper texture quality | V2 | V2 polish hơn |
| Audio MIDI sync, 3D text | V2 only | V1 không có (skip ở MVP) |
| Spritesheet UV offset cho variant outfit | Tự làm theo gợi ý transcript Part 2 ~3:15 | Cả 2 repo đều dùng cách "lười" |

---

## User profile (quan trọng — chỉnh tone phản hồi theo)

- **Không biết code.** Đã vibe-code vài site portfolio đơn giản với Claude Code. Hiểu khái niệm cơ bản (file là gì, thư mục là gì, npm là gì) nhưng KHÔNG đọc được code Three.js / R3F.
- **Không có kinh nghiệm 3D.** Sẽ học Blender từ đầu cho project này.
- **Không có kinh nghiệm vẽ.** Sẵn sàng vẽ style đơn giản (stick figure, hình khối) bằng chuột/trackpad.
- **Pace:** Sprint mode 1–2 tuần.
- **Ngôn ngữ:** Tiếng Việt (user viết tiếng Việt + xưng "t/b"). Phản hồi mặc định bằng tiếng Việt.
- **Division of labor:**
  - User làm: **vẽ Krita + dựng Blender + bake textures + concept**.
  - Claude làm: **toàn bộ code** (React, R3F, Three.js, GSAP, Lenis, Zustand, scripts).
  - Khi user paste error/screenshot → Claude debug.

---

## Roadmap chính

Roadmap đầy đủ ở [roadmap.md](roadmap.md) — 7 phases, 40–60 giờ tổng:

0. Setup môi trường (chạy được V1 + V2 local)
1. Concept + mood board
2. Krita: vẽ assets 2D (PNG transparent)
3. Blender: scene + bake + camera curve
4. **Vibe-code khung site** ← Claude vào việc từ đây
5. **Vibe-code camera scroll-driven loop**
6. **Polish: hover, animation, intro, audio**
7. Deploy lên Vercel

Khi user nói "tới phase X rồi", đọc lại section tương ứng trong `roadmap.md` để biết context.

---

## Quy tắc khi Claude làm việc trong project NÀY (V2 reference)

1. **KHÔNG sửa file trong repo này** trừ khi user yêu cầu rõ. Repo này là tham khảo, không phải code base đang dev.
2. **File hợp lệ để tạo/sửa trong repo này:**
   - `roadmap.md` (đã có)
   - `CLAUDE.md` (file này)
   - Notes / scratch của user nếu user yêu cầu.
3. **Khi user hỏi "làm sao mà site này làm được X?"** → đọc code repo này (V2) hoặc V1, giải thích bằng tiếng Việt đơn giản.
4. **Khi user bắt đầu Phase 4 trở đi** → user sẽ tạo project mới ở `../my-portfolio` (hoặc tên khác) sibling với 2 repo này. Code thật viết ở đó. Hai repo V1+V2 chỉ để Claude đọc khi user nhờ adapt pattern.

---

## Quy tắc vibe-code khi user qua project mới (Phase 4+)

Khi user đã tạo project mới và work ở đó, áp dụng những điều sau:

### Mindset

- User sẽ paste prompt brief → Claude code → user test → user paste lỗi/screenshot → Claude fix. Lặp lại.
- **Đừng giải thích nhiều dòng code.** User không đọc được. Nói **cái gì sẽ xảy ra trên màn hình** sau khi chạy, không nói "tôi đã add useEffect với dependency array...".
- **Đừng over-engineer.** Roadmap nói rõ MVP — không add feature ngoài scope phase hiện tại.

### Khi adapt code từ V1/V2

1. Đọc file gốc (`Read` tool) trước khi adapt — đừng đoán.
2. Nói rõ "đang adapt từ `<path>`" để user trace được.
3. Loại bỏ những gì project mới không cần (ví dụ V2 có `react-router` nhưng project mới chỉ 1 page → bỏ).
4. **Khi 2 repo có cách làm khác nhau, default theo bảng so sánh ở trên.** Đặc biệt: camera looping LUÔN theo V2.

### Khi user stuck với Blender (không phải code)

- Bảo user paste screenshot Blender (Claude có thể nhìn ảnh).
- KHÔNG đoán/bịa hotkey hay menu nếu không chắc — bảo user search transcript hoặc xem video.
- Phase 3 (Blender) là phase Claude hỗ trợ ÍT NHẤT, đừng giả vờ biết hết.

### Pipeline `gen:models` (cốt lõi của vibe-code workflow)

V1 có pattern này, sẽ port sang project user ở Phase 4:

- User drop `.glb` mới vào `raw_assets/` → gõ `npm run gen:models` → script tự sinh component React load model + textures dựa trên tên mesh.
- Claude phải maintain pattern này: mỗi khi user add asset mới, hướng dẫn drop file + chạy command, KHÔNG hardcode path.

### Naming convention bắt buộc

Mesh trong Blender + texture file trong project mới phải theo: `<scene>_<object>_<variant>` (ví dụ `scene1_bike_default`, `scene1_bike_samurai`). Nếu user đặt tên lung tung, NHẮC user rename trong Blender trước khi export.

---

## Anti-patterns Claude PHẢI tránh

- ❌ Sửa file random trong repo V2 này không có lý do.
- ❌ Copy nguyên file từ V1/V2 sang project mới mà không adapt (deps khác, structure khác).
- ❌ Copy logic looping của V1 (transition curve + scroll multiplier hack) — V1 admit clunky.
- ❌ Dùng nhiều plane riêng cho mỗi outfit thay vì spritesheet — V1+V2 đều "lười", đừng lặp lại.
- ❌ Generate code dùng package chưa cài (`npm install` trước khi import).
- ❌ Thêm TypeScript / testing framework / Storybook — out of scope cho MVP.
- ❌ Polish/refactor tự ý ngoài scope phase hiện tại của roadmap.
- ❌ Mock data / placeholder asset — luôn dùng asset thật của user (`raw_assets/`).

---

## Critical files map (cheat sheet)

### Trong repo NÀY (V2):

- [src/main.jsx](src/main.jsx), [src/App.jsx](src/App.jsx) — entry + root
- [src/Experience/](src/Experience/) — **3D scene logic, camera looping refactored** (reference quan trọng nhất)
- [src/components/](src/components/) — intro, loading, UI
- [src/styles/](src/styles/) — SCSS
- [Blender File and Addon/curve_to_points.py](Blender%20File%20and%20Addon/curve_to_points.py) — export curve sang JS
- [Blender File and Addon/First Round Baking for vid6.blend](Blender%20File%20and%20Addon/First%20Round%20Baking%20for%20vid6.blend) — Blender file gốc
- [Mr Pand Website Tutorial Youtube Transcript.md](Mr%20Pand%20Website%20Tutorial%20Youtube%20Transcript.md) — transcript dài V2 (~300KB)
- [Youtube Tutorial Part 2.md](Youtube%20Tutorial%20Part%202.md) — transcript ngắn V1 (~17KB)
- [package.json](package.json), [vite.config.js](vite.config.js), [vercel.json](vercel.json)

### Trong repo SIBLING V1 (`../aimee-weis-papercraft-world/`):

- `src/main.jsx`, `src/App.jsx` — entry, có Lenis setup
- `src/Experience/`, `src/components/`, `src/store/` — code đơn giản hơn V2
- **`scripts/process_models.js`** — AI-generated, auto-hook texture với mesh dựa trên tên ⭐
- **`raw_assets/`** — folder pattern cho assets thô
- `Blender Files and Addon/Camera_Curve.blend` — file curve riêng (camera + character path)
- `Blender Files and Addon/curve_to_points.py`
- `package.json` — note `"gen:models"` script

---

## Khi user nói "stuck", hỏi 3 câu trước khi fix

1. **Đang ở phase nào của roadmap?** (Để biết scope.)
2. **Lỗi cụ thể là gì?** (Paste error message, screenshot, hoặc mô tả "đáng ra nó X nhưng nó Y".)
3. **Đã thử gì rồi?** (Tránh lặp lại cùng giải pháp.)

Sau đó mới đọc code/file liên quan và fix.

---

## Tóm tắt 1 dòng

> Repo này là REFERENCE. User vibe-code project mới ở thư mục sibling. V1 (Aimee Wei) là code reference dễ; V2 (Mr. Panda, repo này) là aesthetic + camera looping refactored reference. Roadmap đầy đủ ở `roadmap.md`. Phản hồi tiếng Việt, tone đơn giản, không giả định user đọc được code.
