# Contributing to BAAN/ING Landing Page

Thank you for your interest in contributing to **BAAN/ING**! We welcome contributions from designers, architects, and frontend developers.

---

## 🏛️ Guiding Principles

1. **Measured, Never Approximated**:
   - All spatial dimensions must be mathematically and architecturally accurate.
   - Design tokens must strictly adhere to [`DESIGN.md`](../DESIGN.md).
2. **Sub-150ms Performance**:
   - The landing page is engineered for instant load times on edge networks (Cloudflare Pages).
   - Keep assets optimized. Compress 3D `.glb` models and textures according to the $\le 1.5\text{ MB}$ Draco asset budget where possible.
3. **Strict Zero-BOQ Policy**:
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
- **Contrast**: Text in gold tones must use `thai-gold-text` (`#8A6A28`) rather than accent gold (`#C5A059`) to pass WCAG AA 4.5:1 contrast requirements.
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
