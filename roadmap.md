# Roadmap: Học làm Creative 3D Website theo style Mr. Panda

## Context

Bạn (zenasharp) muốn học cách tự build một creative portfolio website theo style của [Mr. Panda's Psychologically Safe Portfolio](https://www.mr-pandas-psychologically-safe-portfolio.com/) — site đã thắng FWA of the Day và Awwwards SOTD. Repo gốc và transcript YouTube tutorial của tác giả đã có sẵn trong working directory.

**Profile của bạn:**
- Không biết code, đã từng vibe-code các site portfolio/creative đơn giản với Claude Code.
- Không có kinh nghiệm 3D, không có kinh nghiệm vẽ, nhưng sẵn sàng vẽ style đơn giản (stick figure, hình khối) bằng chuột/trackpad hoặc tablet rẻ.
- **Division of labor đã chốt:** Bạn học **3D + Blender + Krita đầy đủ** (vì AI không vẽ/model thay bạn được — đó là phần craft của bạn). **Phần code** thì vibe với Claude — chỉ cần hiểu đủ để chỉ đạo Claude, debug khi vỡ, và biết gọi tên thứ mình muốn.
- **Pace:** Sprint mode — 1–2 tuần heavy focused work. Ưu tiên ship một site chạy được, cắt mọi thứ "nice to learn".
- **Concept:** Chưa có — sẽ là Step 1 của roadmap.

**Stack bạn sẽ vibe-code (theo V1 = đơn giản hơn):**
- React 19 + Vite (build tool)
- Three.js + `@react-three/fiber` + `@react-three/drei` (3D engine trong React)
- GSAP + `@gsap/react` (animation)
- **Lenis** (smooth scroll — V1 có, V2 không, nhưng Lenis làm scroll mượt hơn rõ rệt → giữ)
- Zustand (state), CSS hoặc SCSS (styling)
- Asset pipeline: **Krita** (vẽ 2D PNG transparent) → **Blender** (đặt lên plane, bake texture) → export `.glb` → load vào R3F
- **Bonus pipeline (V1-only, rất hợp vibe-code):** folder `raw_assets/` + script `scripts/process_models.js` để Claude tự generate component từ `.glb` mới.

**Stack V2 thêm (skip ở MVP, add sau nếu còn thời gian):**
- `@tonejs/midi` (sync nhạc với animation), `troika-three-text` (3D text), `react-router` (multi-page), `react-transition-group`, `normalize-wheel`.

**Tutorial nguồn (2 video, 2 repo):**
- **V2 (mới, "better version")** = Mr. Panda's Psychologically Safe Portfolio
  - Repo: thư mục hiện tại
  - Transcript dài: [Mr Pand Website Tutorial Youtube Transcript.md](Mr%20Pand%20Website%20Tutorial%20Youtube%20Transcript.md) (~300KB, ~3 tiếng video)
- **V1 (cũ, đơn giản hơn)** = Aimee Wei's Papercraft World
  - Repo: `../aimee-weis-papercraft-world/` (đã clone về)
  - Transcript ngắn: [Youtube Tutorial Part 2.md](Youtube%20Tutorial%20Part%202.md) (~17KB, ~14 phút video)

**Quan hệ giữa 2 dự án:**
- V1 ra đời **trước**. Tác giả thừa nhận một số thứ làm "lười" trong V1 (4 plane riêng thay vì spritesheet, transition curve clunky cho looping...).
- V2 là *refactor sạch hơn* của V1 với cùng concept. Trong tutorial dài (V2), tác giả nói *"this project is just a better version of this project. I'm going to refer to this one a lot"*.
- **Code stack V1 đơn giản hơn nhiều** (không có react-router, audio MIDI, custom text rendering). → **V1 là reference dễ hiểu hơn cho vibe-coder; V2 là target nâng cao.**

**Strategy của roadmap này:**
- **V1 = primary reference khi vibe-code** (code dễ đọc, structure gọn).
- **V2 = aesthetic + refactor reference** (kỹ thuật mới, asset đẹp hơn).
- Đọc cả 2 transcript để hiểu *tại sao* V2 cải tiến — tránh lặp lỗi V1.

---

## Reality Check (đọc trước khi bắt đầu)

Trước khi vào roadmap, cần nói thẳng vài điều để bạn không bỏ cuộc giữa chừng:

1. **Đây không phải vibe-code thuần.** Three.js + custom camera curve + Blender baking là genuinely phức tạp. Sẽ có lúc Claude đưa code sai và bạn phải biết *đủ* để nói "không, cái camera bị flip ngược, cần fix lookAt vector" — chứ không thể chỉ copy-paste mãi.
2. **Phần khó nhất KHÔNG phải code.** Là **Blender + vẽ**. Code thì Claude làm 80%. Blender thì bạn làm 100% (Claude không nhìn được viewport của bạn).
3. **Sprint 1–2 tuần là khả thi nhưng intense.** Realistic time: **40–60 giờ tập trung**. Nếu bạn làm 6–8h/ngày trong 7–10 ngày, ship được. Đừng kỳ vọng polish bằng Mr. Panda — site của bạn sẽ là phiên bản "MVP" của ý tưởng đó.
4. **Asset của bạn = giá trị của site.** Mr. Panda đẹp vì panda dễ thương. Style vẽ của bạn (dù vụng) + consistency = charm. Đừng cố vẽ đẹp — cố vẽ **nhất quán** và **đơn giản**.

---

## The Roadmap — 7 Phases

Mỗi phase có:
- **Goal** (xong phase này bạn có gì)
- **Time budget** (sprint mode)
- **Steps** (làm gì cụ thể)
- **Output** (cái gì cầm đi tiếp được)
- **Vibe-code prompt mẫu** (khi tới phần code, đây là prompt bạn paste cho Claude)

### Phase 0 — Setup môi trường (2–3 giờ)

**Goal:** Máy bạn chạy được repo gốc của Mr. Panda. Đây là "ground truth" để bạn so sánh khi xây bản của mình.

**Steps:**
1. Cài [Node.js LTS](https://nodejs.org/) (cần cho `npm`).
2. Cài [Git](https://git-scm.com/) (đã có vì bạn đang ở repo này rồi — verify bằng `git --version` trong terminal).
3. Cài [VSCode](https://code.visualstudio.com/) + extension: **ES7+ React/Redux snippets**, **SCSS IntelliSense**.
4. Cài **Claude Code** (bạn đang dùng rồi).
5. Cài [Blender](https://www.blender.org/download/) (4.x, free).
6. Cài [Krita](https://krita.org/en/download/) (free).
7. Chạy **cả 2 repo** local để có ground truth so sánh:
   ```bash
   # V2 — Mr. Panda
   cd mr-pandas-psychologically-safe-portfolio
   npm install
   npm run dev    # → http://localhost:5173

   # V1 — Aimee Wei (mở terminal mới)
   cd ../aimee-weis-papercraft-world
   npm install
   npm run dev    # → http://localhost:5174 (hoặc port khác)
   ```
   Mở cả 2 trên 2 tab browser. Nếu lỗi, paste lỗi cho Claude fix.
8. Mở Blender, mở thử:
   - V2: `mr-pandas-psychologically-safe-portfolio/Blender File and Addon/First Round Baking for vid6.blend`
   - V1: `aimee-weis-papercraft-world/Blender Files and Addon/For_Baking.blend` và `Camera_Curve.blend`
   - Click vài object, hiểu mỗi cái là 1 plane có image texture.

**Output:**
- 2 site chạy local song song trên máy bạn (dùng để so sánh khi vibe-code).
- Mở được Blender, Krita.

**Ghi chú so sánh V1 vs V2 khi xem:**
- V1 (Aimee Wei) UI/animation đơn giản, dễ đọc code → reference chính khi vibe-code.
- V2 (Mr. Panda) polished hơn, code phức tạp hơn → tham khảo aesthetic.

---

### Phase 1 — Concept & Mood Board (3–5 giờ)

**Goal:** Có một concept 1-câu rõ ràng + mood board để dẫn đường cho mọi asset bạn sẽ làm.

**Steps:**
1. Trả lời 3 câu này (viết ra giấy/Notion):
   - **Site này dùng để làm gì?** (Portfolio cho ai xem? Khoe kỹ năng gì? Hay chỉ là project học?)
   - **"Nhân vật chính" là gì?** (Mr. Panda dùng panda. Bạn dùng gì? Một con vật? Một avatar đại diện bạn? Một object như cuốn sách, cái máy ảnh?)
   - **"Hành trình" là gì?** (Mr. Panda đạp xe qua các "outfits" thể hiện các creative skill khác nhau. Bạn? Đi bộ qua các project? Chèo thuyền qua các phase cuộc đời? Bay qua các interest?)
2. Viết **1 câu concept** theo format: *"Một [nhân vật] [hành động] qua [setting], thể hiện [thông điệp/nội dung của bạn]."*
3. **Mood board:** Lập 1 file Pinterest/Figma/folder ảnh với:
   - 5–10 ảnh reference style vẽ bạn thích (đơn giản, cute, doable bằng chuột).
   - 3–5 ảnh reference 3D scene (có thể là các award-winning site khác trên Awwwards).
   - 1 bảng màu (3–5 màu chính). Dùng [Coolors.co](https://coolors.co/) generate cho nhanh.
4. **List 5–7 "scenes/outfits"** mà nhân vật của bạn sẽ đi qua. Mỗi scene = một asset bạn sẽ vẽ. Giữ ÍT — Mr. Panda có nhiều scene vì làm cả tháng. Bạn có 1–2 tuần. **5 là vừa đủ.**

**Output:**
- 1 câu concept.
- 1 mood board.
- List 5–7 scenes/outfits đặt tên rõ ràng.

**⚠️ Đừng skip phase này.** Concept không rõ → vẽ lung tung → site không thống nhất → không ai khen.

---

### Phase 2 — Krita: vẽ assets 2D (8–12 giờ)

**Goal:** Có toàn bộ PNG transparent cho mọi nhân vật + scene element trong list ở Phase 1.

**Tutorial bám theo:** Transcript section "Basic Krita Tutorial" và "Exporting Image Assets from Krita" (timestamp ~4:31 đến ~12:00).

**Steps:**
1. Xem section tương ứng trong YouTube video gốc (hoặc đọc transcript).
2. Học các thao tác cơ bản trong Krita:
   - Tạo canvas (3000×3000 px là đủ, không cần 30000).
   - Brush tool (B) + Fill tool (F) + Eraser.
   - **Layers** — đây là key. Mỗi part chuyển động (bánh xe, tay, cánh) phải ở layer riêng để Blender animate được.
   - Save file `.kra`, export PNG transparent.
3. Vẽ:
   - 1 nhân vật chính + 4–6 "outfits"/biến thể (mỗi cái 1 file `.kra`).
   - 5 scene element (cây, tòa nhà, đồ vật...).
   - Bất kỳ part nào cần animate (bánh xe, tay vẫy...) → layer riêng.
4. **Trick từ tutorial:** Dùng `Tools → Scripts → Export Layers` để export tất cả layer ra PNG cùng lúc. Khi nhân vật có nhiều outfit cùng kích thước canvas, **giữ nguyên canvas size** (không adjust to layer content) để Blender swap texture không lệch.

**Output:**
- Folder `assets/2d/` chứa tất cả PNG transparent.
- File `.kra` gốc lưu lại để chỉnh sửa sau.

**⚠️ Time-box nghiêm.** Cứ 2 giờ thì stop dù chưa xong. "Đủ tốt" > "hoàn hảo". Bạn có thể quay lại tô lại sau.

---

### Phase 3 — Blender: scene + bake textures (10–15 giờ)

**Goal:** Một file `.blend` với toàn bộ scene 3D, một curve làm camera path, và một file `.glb` export ra để dùng ở web.

**Đây là phase khó nhất.** Nếu chỉ kham được 1 phase, kham phase này.

**Tutorial bám theo:** Transcript từ "Basic Blender scene modeling with textures" (~12:30) đến hết phần Blender (khoảng 1/3 đầu video).

**Steps:**
1. **Học Blender basics** trước khi bắt tay (~2 giờ):
   - Xem 1 video "Blender 4.x for absolute beginners" trên YouTube (~30 phút).
   - Học: navigate viewport (middle mouse), select (click), move (G), rotate (R), scale (S), delete (X), shift+A để add object.
2. **Setup scene:**
   - `Shift+A → Mesh → Plane` → File browse PNG → Blender auto-tạo material với alpha cutout (xem transcript ~12:30).
   - Đặt nhiều plane cho nhân vật + scene element. Offset Z nhẹ để không Z-fight.
   - Parent các part chuyển động (bánh xe → "stick" cha) bằng `Ctrl+P`.
3. **Lighting:** Sky texture (xem ~12:53). Đừng phức tạp.
4. **Paper texture:** Mix image PNG với notebook paper texture bằng Mix Color node mode "Multiply" (xem ~22:00–24:00). Nhóm thành node group `paper_combined` để reuse.
5. **Camera curve (CỐT LÕI của site này):**
   - `Add → Curve → Bezier` — vẽ đường đi của camera.
   - Add empty `Track To` constraint để camera luôn nhìn vào nhân vật khi chạy dọc curve.
   - Method này được giải thích chi tiết trong transcript phần "updated methodology for creating custom camera path curves" (~0:26 và sâu hơn về sau). **Khi tới đây, mở transcript ra đọc kỹ section đó.**
   - File `Blender File and Addon/curve_to_points.py` là script tác giả dùng để export curve thành array of points cho Three.js — đọc nó, hiểu rồi adapt cho curve của bạn.
6. **Bake textures:**
   - Select all → Properties → Render → Bake (Diffuse + Lighting → texture).
   - Bake giúp web load nhanh (không cần realtime lighting).
   - Section transcript "for the people that do want to bake" (~28:00) nói chi tiết.
7. **Export:** `File → Export → glTF (.glb)`. Chọn "Selected Only" hoặc Visible Objects. Lưu vào `raw_assets/yourscene.glb` (tên folder theo convention V1, sẽ dùng ở Phase 4).
8. **Export camera curve:** Có sẵn 2 phiên bản script Python:
   - V2: `mr-pandas-psychologically-safe-portfolio/Blender File and Addon/curve_to_points.py`
   - V1: `aimee-weis-papercraft-world/Blender Files and Addon/curve_to_points.py`
   - Đọc cả 2 với Claude (`"đọc 2 file này, giải thích sự khác biệt và recommend tôi nên dùng cái nào"`), pick cái dễ hơn.
   - Output: file JS hoặc JSON với array of `[x,y,z]` points. Lưu vào `src/curves/cameraCurve.js`.

**📌 Important — naming convention (theo V1):**

Tác giả V1 dùng AI tự sinh script `process_models.js` để auto-hook texture với geometry **dựa trên tên trùng**. Ví dụ: mesh tên `panda_001` sẽ tự link với texture `panda_001.webp`. Đây là **vibe-coder's best friend**.

Khi đặt tên trong Blender, theo pattern: `<scene>_<object>_<variant>` (ví dụ `scene1_bike_default`, `scene1_bike_samurai`). Nhất quán = sau này Claude generate code dễ ăn.

**Output:**
- File `.blend` master.
- `yourscene.glb` (model + texture đã bake).
- `camera_path.json` (curve points).

**⚠️ Khi stuck:** Paste screenshot Blender vào Claude (qua Claude Desktop hoặc hỏi trực tiếp Claude Code có context). Hoặc Discord của tác giả Mr. Panda — link trong README repo gốc.

---

### Phase 4 — Vibe-code khung website (4–6 giờ)

**Goal:** Một React + Vite + R3F project mới, load được `yourscene.glb`, hiển thị trong browser. **Adopt ngay pattern `raw_assets/` + `gen:models` từ V1.**

**Đây là lúc Claude Code tỏa sáng.** Bạn không viết code — bạn ra brief, Claude code, bạn test.

**Steps:**
1. Tạo project mới sibling với 2 repo reference (KHÔNG sửa repo gốc):
   ```bash
   cd ..   # ra ngoài thư mục hiện tại, đứng cùng cấp với 2 repo reference
   npm create vite@latest my-portfolio -- --template react
   cd my-portfolio
   npm install three @react-three/fiber @react-three/drei gsap @gsap/react zustand lenis
   mkdir raw_assets scripts
   npm run dev
   ```

2. **Vibe-code prompt mẫu #1 — setup khung scene** (paste vào Claude Code ở thư mục `my-portfolio`):

   ```
   Tôi đang build một creative portfolio R3F site, có 2 repo reference cùng cấp:
   - ../aimee-weis-papercraft-world (V1, đơn giản, dùng làm primary reference)
   - ../mr-pandas-psychologically-safe-portfolio (V2, polished, reference aesthetic)

   Đọc qua structure src/ của V1 (App.jsx, components/, Experience/) để hiểu pattern họ dùng. Sau đó setup giúp tôi:
   1. Canvas R3F full-screen ở App.jsx
   2. Component <Scene> load file raw_assets/yourscene.glb (tôi sẽ drop file vào sau) bằng useGLTF
   3. Camera perspective FOV 50
   4. OrbitControls để debug (sẽ tắt sau)
   5. Ambient + directional light cơ bản
   6. Smooth scroll bằng Lenis (xem cách V1 setup Lenis trong main.jsx hoặc App.jsx)

   Tôi muốn THẤY scene 3D xoay được trước, rồi mới làm tiếp. Đừng add camera curve hay scroll-driven gì cả ở step này.
   ```

3. **Vibe-code prompt mẫu #2 — adopt pipeline `gen:models` từ V1** (sau khi step 2 chạy ổn):

   ```
   Đọc file ../aimee-weis-papercraft-world/scripts/process_models.js và package.json của họ.
   Adapt script đó cho project của tôi: drop .glb vào raw_assets/ → npm run gen:models → tự sinh component React load model + textures (texture file đặt cùng tên với mesh).

   Sau khi xong, hướng dẫn tôi cách dùng: tôi drop file mới, gõ command gì, xuất ra đâu, import như thế nào.
   ```

4. Test: Mở `http://localhost:5173` — phải thấy scene 3D xoay được bằng chuột.
5. Nếu lỗi: copy paste error vào Claude Code, để Claude fix.

**Output:**
- Project React mới chạy được, hiển thị scene 3D của bạn.
- Pipeline `npm run gen:models` hoạt động → từ giờ add asset mới chỉ cần drop file + gõ 1 command.

---

### Phase 5 — Vibe-code camera curve + scroll (6–8 giờ)

**Goal:** Camera đi dọc theo curve khi user scroll. Đây là "magic" của site này.

**⚠️ Pitfall đã biết từ V1 → V2:**

Trong Part 2 transcript (~9:20), tác giả V1 thừa nhận cách looping của họ là "weird" — dùng "transition curve" giữa các điểm shift, gây giật khi scroll nhanh. Họ "vá" bằng `scroll speed multiplier × 6` ở transition, rồi đổi về 1 ngay trước khi exit. Tác giả nói rõ: *"What I should have done instead was actually a lot easier... just multiply the new progress value itself rather than play with the scroll speed multiplier."* — và V2 đã refactor.

**→ Đừng copy V1 mù quáng cho looping. Hỏi Claude xem V2 làm thế nào, ưu tiên cách V2.**

**Steps:**
1. **Vibe-code prompt mẫu:**

   ```
   Bây giờ tôi muốn implement scroll-driven camera path:

   - File src/curves/cameraCurve.js chứa array các điểm [x,y,z] (curve export từ Blender).
   - Tạo một CatmullRomCurve3 (closed=true) từ Three.js từ các điểm này.
   - Khi user scroll qua Lenis, camera position di chuyển dọc curve (scroll 0% = điểm đầu, 100% = điểm cuối).
   - Site phải LOOP vô hạn — scroll xuống hết thì wrap về đầu mượt mà.

   Quan trọng: Có 2 implementation reference:
   - V1: ../aimee-weis-papercraft-world/src/ (tác giả tự nhận transition curve method là "clunky", scroll giật khi nhanh)
   - V2: ../mr-pandas-psychologically-safe-portfolio/src/Experience/ (refactor sạch hơn, là cách làm đúng)

   Đọc cách V2 làm camera looping, adapt cho project của tôi. KHÔNG copy V1 cho phần looping.

   Camera nhìn vào target — có thể là một empty point hoặc một curve thứ 2 cho character path (xem cách V1 dùng 2 curves: cameraCurve và pandaCurve, V2 cũng tương tự).

   Tắt OrbitControls sau khi camera curve hoạt động.
   ```

2. **Khi Claude bí**, paste link cụ thể file: *"Đọc `../mr-pandas-psychologically-safe-portfolio/src/Experience/<file>.jsx` và adapt logic camera của họ."*
3. **Test loop:** Scroll xuống xa nhất + scroll nhanh xem có wrap mượt + không giật ở transition. Đây là phần dễ bug nhất.

**Output:**
- Website có camera scroll-driven đi dọc curve, loop vô hạn, mượt cả khi scroll nhanh.

---

### Phase 6 — Polish: animation, hover, audio, intro (4–6 giờ)

**Goal:** Site cảm giác "sống" — không chỉ là camera bay qua scene tĩnh.

**Steps (làm theo thứ tự ưu tiên — nếu hết thời gian, dừng đâu cũng OK):**

1. **Hover interactions** (vibe-code):
   ```
   Khi user hover vào một mesh trong scene (ví dụ object tên "panda_bike"), GSAP scale nó lên 1.1, rồi về 1.0 khi unhover. Cursor đổi thành pointer.
   ```
2. **Spinning wheels / part animations:**
   ```
   Object tên "bike_front_wheel" và "bike_back_wheel" phải xoay liên tục quanh trục Z trong useFrame. Tốc độ tỉ lệ với scroll velocity.
   ```
3. **Intro screen** (loading + click-to-enter):
   ```
   Trước khi vào scene chính, hiện một intro screen full-screen với tên site + nút "Enter". Dùng CSS animation đơn giản. Click "Enter" thì fade out và unlock scroll.
   ```
4. **Background music** (optional, Mr. Panda dùng `@tonejs/midi` để sync — bạn có thể skip, dùng `<audio>` HTML là đủ).
5. **Mobile responsive:** Site này khó mobile thật. Mr. Panda cũng admit trong README "Adjust curve for mobile devices" là TODO. Bạn có thể chỉ show một message "Best viewed on desktop" cho mobile và xong. Đừng tốn tuần thứ 2 cho mobile.

**Output:**
- Site hoàn chỉnh, có cảm giác "wow".

---

### Phase 7 — Deploy (1–2 giờ)

**Goal:** Site live trên internet, có URL gửi được.

**Steps:**
1. Push code lên GitHub (Claude Code làm được: *"commit hết và push lên một repo GitHub mới tên `my-portfolio`"*).
2. Vào [Vercel](https://vercel.com/), connect GitHub, import repo. Vercel auto-detect Vite → deploy free.
3. Repo gốc đã có `vercel.json` — copy vào project bạn.
4. Tùy chọn: mua domain rẻ ($10/năm) trên Namecheap, point về Vercel.

**Output:**
- URL public.
- Optional: gửi link cho tác giả Mr. Panda trên Discord khoe.

---

## Critical Files to Reference (cả 2 repo)

Khi vibe-code với Claude, hay reference những file này:

### V1 — Aimee Wei (`../aimee-weis-papercraft-world/`) — đọc trước, đơn giản hơn

- `src/main.jsx`, `src/App.jsx` — entry + root, có Lenis setup.
- `src/Experience/` — 3D scene logic.
- `src/components/`, `src/store/` — UI + zustand state.
- **`scripts/process_models.js`** — AI-generated script tự sinh component từ `.glb`. Pipeline cực hợp vibe-code.
- **`raw_assets/`** — folder drop `.glb` vào, output ra `src/Experience/models/`.
- **`Blender Files and Addon/Camera_Curve.blend`** — file Blender riêng cho 2 curves (camera + character path).
- `Blender Files and Addon/curve_to_points.py` — Python script export curve sang JS.
- `package.json` — note dòng `"gen:models"`.

### V2 — Mr. Panda (thư mục hiện tại) — refactor sạch hơn, reference khi V1 không có pattern

- [src/main.jsx](src/main.jsx), [src/App.jsx](src/App.jsx).
- [src/Experience/](src/Experience/) — **camera looping refactored, là cách làm đúng**.
- [src/components/](src/components/) — intro screen, loading.
- [src/styles/](src/styles/) — SCSS.
- [Blender File and Addon/curve_to_points.py](Blender%20File%20and%20Addon/curve_to_points.py).
- [vercel.json](vercel.json) — config deploy.

### So sánh khi cần choice nào dùng cái nào

| Topic | Theo repo nào | Lý do |
|---|---|---|
| Project structure, App.jsx | V1 | Code đơn giản, dễ đọc cho người mới |
| Lenis smooth scroll | V1 | V2 không có Lenis |
| `gen:models` pipeline | V1 only | V2 không có |
| Camera curve looping | **V2** | V1 tự admit clunky, V2 refactored |
| Spritesheet / texture optimization | V2 hoặc tự làm | Cả 2 đều dùng cách "lười" — nếu muốn tối ưu, làm theo gợi ý của tác giả trong Part 2 transcript |
| Aesthetic, paper texture, asset quality | V2 | V2 polish hơn |
| Audio sync, MIDI | V2 only | V1 không có (skip ở MVP) |
| Bulk image compression (KTX2/WEBP) | V1 transcript Part 2 | Có command line PowerShell + ImageMagick — đáng add cuối phase 6 |

---

## Verification — làm sao biết bạn đã xong?

Cuối roadmap, site của bạn phải pass checklist này:

- [ ] Mở URL → thấy intro screen → click → vào scene 3D.
- [ ] Scroll → camera bay dọc curve, nhìn vào nhân vật chính.
- [ ] Scroll xuống hết → loop về đầu mượt mà.
- [ ] Hover lên ít nhất 1 object → có animation phản hồi.
- [ ] Bánh xe / part animate được khi scroll.
- [ ] Asset có paper texture (notebook lines lờ mờ) — đặc trưng style.
- [ ] Mỗi "scene" theo curve hiển thị một biến thể nhân vật / outfit khác nhau.
- [ ] Site deploy live, có URL.
- [ ] (Bonus) Người lạ xem mà thốt "wow đẹp vậy".

---

## Khi stuck — escalation path

1. **Đọc transcript** [Mr Pand Website Tutorial Youtube Transcript.md](Mr%20Pand%20Website%20Tutorial%20Youtube%20Transcript.md) phần liên quan.
2. **Hỏi Claude Code** với context cụ thể (paste error message, paste code đoạn liên quan, paste screenshot nếu là Blender).
3. **Tham khảo file tương ứng** trong repo gốc — bảo Claude đọc rồi adapt.
4. **Discord của tác giả** — link trong README repo gốc.
5. **Awwwards / FWA forum** — xem case study của Mr. Panda.

---

## Anti-patterns — ĐỪNG làm

- ❌ Đừng skip Phase 1 (concept). Vẽ trước concept = vẽ lại 3 lần.
- ❌ Đừng cố vẽ đẹp. Cố vẽ **nhất quán + đơn giản**.
- ❌ Đừng cố làm mobile-perfect. Desktop-first, mobile = "best viewed on desktop".
- ❌ Đừng vibe-code Phase 3 (Blender). Claude không nhìn được viewport.
- ❌ Đừng copy nguyên scene Mr. Panda rồi đổi tên file. Site sẽ vô hồn vì nó không phải bạn.
- ❌ Đừng bỏ lưng chừng ở Phase 5. Camera curve là cốt lõi — không có nó, site chỉ là một scene 3D xoay được, không phải Mr. Panda style.
- ❌ **Đừng copy logic looping của V1** (transition curve + scroll multiplier × 6). Tác giả tự nói nó clunky. V2 đã fix — học V2.
- ❌ **Đừng dùng nhiều plane riêng cho mỗi outfit** như V1. Dùng spritesheet với UV offset (tác giả Part 2 transcript ~3:15 thừa nhận đây là đúng). Hỏi Claude implement giúp.
- ❌ Đừng đặt tên mesh trong Blender lung tung (`Cube.001`, `Plane.045`). Theo convention `<scene>_<object>_<variant>` để pipeline `gen:models` chạy được.
