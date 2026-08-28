# Contributing to BAAN/ING Landing Page

Thank you for your interest in contributing to **BAAN/ING**! We welcome contributions from designers, architects, and frontend developers.

---

## 🏛️ Guiding Principles

1. **Measured, Never Approximated**:
   - All spatial dimensions must be mathematically and architecturally accurate.
   - Design tokens must strictly adhere to [`DESIGN.md`](../DESIGN.md).
2. **No Unverified Claims**:
   - Never state a performance figure, render time, or accuracy percentage the product cannot currently demonstrate. Fabricated figures are why the interactive BOQ estimator was removed.
   - Features that have not shipped are presented as **Coming Soon** / **In Development**, never in the present tense.
   - Never imply a supplier, catalog, or partner relationship that does not exist, and never label third-party geometry as `1:1` or dimensionally verified.
3. **Performance**:
   - The landing page targets fast loads on edge networks (Cloudflare Pages).
   - Keep assets optimized. Compress 3D `.glb` models and textures aggressively.
   - ⚠ The `≤ 1.5 MB` Draco budget in [`docs/asset-sourcing.md`](../docs/asset-sourcing.md) governs the **application's** asset pipeline. The placeholder models in `public/assets/` predate that gate being enforced here and exceed it substantially; they are demo-only and are not catalog assets.
4. **Strict Zero-BOQ Policy**:
   - Do **not** introduce any mentions of "BOQ" or "Bill of Quantities" into landing or marketing copy.

---

## 🛠️ Development Workflow

1. **Fork and Clone**:
   ```bash
   git clone https://github.com/naiiytom/baan-ing-landing.git
   cd baan-ing-landing
   ```

2. **Branching Strategy**:
   - Create a descriptive feature branch from `main`:
     ```bash
     git checkout -b feat/my-new-feature
     ```

3. **Install Dependencies & Start Dev Server**:
   ```bash
   npm install
   npm run dev
   ```

4. **Verify Production Build**:
   ```bash
   npm run build
   npm run preview
   ```

---

## 🎨 Design System & Code Style

- **HTML / CSS**: Semantic HTML5 and Tailwind CSS utility classes.
- **Glassmorphism**: Use the canonical styling:
  ```css
  background: rgba(255, 255, 255, 0.72);
  backdrop-filter: blur(18px);
  border: 1px solid rgba(196, 199, 199, 0.30);
  ```
- **Contrast**: On the light page surfaces, text in gold tones must use `thai-gold-text` (`#8A6A28`, 4.78:1) rather than accent gold (`#C5A059`, 2.34:1) to pass WCAG AA. **On charcoal (`#262626`) this inverts** — use `#C5A059` (6.16:1); `#8A6A28` is only 3.01:1 there and fails. See `plan/decisions.md` **D30**.
- **Typography**:
  - `font-display-lg` / `Manrope` for display headers.
  - `font-body-md` / `Hanken Grotesk` for prose and descriptions.
  - `font-data-mono` / `JetBrains Mono` for dimensions, coordinates, and telemetry.

---

## 📦 Pull Request Process

1. Ensure `npm run build` succeeds without warnings or errors.
2. Submit a Pull Request targeting the `main` branch.
3. Provide a clear description of the visual and technical changes made, including screenshots for UI modifications.
4. Maintainers will review and merge your PR once approved.

Thank you for building the future of tropical architecture with us!
