# BAAN/ING — Official Landing Page & 3D Web Showcase

> **Smart Design. Real Spaces.**  
> The architectural CAD & cloud raytracing platform engineered specifically for Thai spaces.

[![Vite](https://img.shields.io/badge/Vite-6.4.3-646CFF?logo=vite&logoColor=white)](https://vitejs.dev/)
[![Cloudflare Pages](https://img.shields.io/badge/Deploy-Cloudflare%20Pages-F38020?logo=cloudflare&logoColor=white)](https://pages.cloudflare.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Design System](https://img.shields.io/badge/Design%20System-DESIGN.md-C5A059)](../DESIGN.md)

---

## 🏛️ Overview

This repository contains the standalone, high-performance static landing page for **BAAN/ING** (`baan.ing`). Built with **Vite**, **Tailwind CSS**, and Google's **`<model-viewer>`**, it delivers a sub-150ms static bundle with interactive vector CAD viewports, tropical solar simulations, 4K raytracing comparison sliders, and real-time 3D WebGL furniture models.

---

## ✨ Key Features & Interactive Modules

### 1. Interactive CAD Studio Viewport (`#studio-viewport`)
- **2D Floorplan Canvas**: High-precision SVG architectural drawing with live coordinate telemetry tracking, interactive room nodes, column grid bubbles (A/B/C, 1/2/3), and dynamic dimension strings.
- **3D Solar Study**: Axonometric solar path simulator illustrating Bangkok's tropical solar altitude (78° June Solstice) and 1.8m cantilever eave shading.
- **4K Cloud Raytrace Slider**: Draggable Before/After comparison slider demonstrating vector CAD wireframe geometry versus serverless edge-GPU 4K global illumination.
- **1:1 Material Matrix Specifier**: Itemized specification inspector with verified Thai manufacturers (SCG, TOA, Hafele, COTTO, AGC Glass).

### 2. Live 3D Spatial Furniture Models (`#furniture`)
- **Google `<model-viewer>` WebGL Engine**: 360° mouse/touch orbit, pinch-to-zoom, turntable auto-rotation, and camera angle resets (Front, 3D Isometric, Top View).
- **Physical Geometry Telemetry**: Real-time bounding box dimensions ($W \times D \times H\text{ in mm}$) and vertex counts computed directly from mesh accessors.
- **5 Featured Real Models** (served statically from `/assets/`):
  1. `Modern Plywood Rocking Chair` (13.0 MB · $668 \times 1,003 \times 874\text{ mm}$)
  2. `Scalloped Upholstered Bed` (12.0 MB · $1,003 \times 893 \times 436\text{ mm}$)
  3. `Compact Studio Refrigerator` (0.64 MB · $421 \times 417 \times 1,001\text{ mm}$)
  4. `Tropical Rattan Plant Planter` (21.0 MB · $700 \times 610 \times 1,003\text{ mm}$)
  5. `Natural Wood Ladder Bookshelf` (14.6 MB · $558 \times 201 \times 1,002\text{ mm}$)

### 3. Canonical 5-Tier Stacked Pricing Matrix (`#pricing`)
- Transparent pricing reflecting platform monetization:
  - **Free (฿0)** — Prosumers & students (3 project slots, 2 4K renders/mo)
  - **Creator (฿490/mo or ฿408/mo)** — Individual creators (10 projects, CAD DXF export)
  - **Professional (฿1,490/seat/mo or ฿1,242/seat/mo)** — Practicing architects (Unlimited projects, IFC BIM, solar sim)
  - **Team (฿2,990/mo or ฿2,492/mo)** — Design studios (5 included seats, pooled 4K queue)
  - **Enterprise (Custom)** — Developers & large firms (Dedicated GPU cluster, SSO)
- Interactive Monthly / Annually toggle displaying the effective monthly rate stacked cleanly above the yearly billed total.

### 4. Zero-BOQ Strict Policy
- Per product guidelines, all preliminary estimation / BOQ (Bill of Quantities) terminology has been strictly removed across all customer-facing pages until the formal procurement engine ships.

---

## 🎨 Design System Tokens

The page strictly implements the design tokens specified in [`DESIGN.md`](../DESIGN.md):

| Token | Hex / Value | Usage |
| :--- | :--- | :--- |
| **Surface** | `#fdf8f8` | Primary warm paper background |
| **Drafting Canvas** | `#F5F5F4` | Technical CAD viewport background with dual 16px/64px grid |
| **Charcoal Accent** | `#262626` | Primary action buttons and structural vector lines |
| **Architectural Blue**| `#0057FF` | Interactive CAD highlights, dimension ticks, active badges |
| **Thai Gold Accent** | `#C5A059` | Visual borders, sun rays, architectural badges |
| **Thai Gold Text** | `#8A6A28` | Accessible text typography (passes WCAG AA 4.5:1 contrast) |
| **Glassmorphism** | `rgba(255,255,255,0.72)` | Canonical frosted glass cards with `backdrop-filter: blur(18px)` |

**Typography**:
- **Display**: `Manrope` (500, 600, 700, 800)
- **Body**: `Hanken Grotesk` (400, 500, 600, 700)
- **Data / Telemetry**: `JetBrains Mono` (400, 500, 600, 700)

---

## 🛠️ Local Development

### Prerequisites
- Node.js 18+ or 20+
- npm or pnpm

### Getting Started

```bash
# 1. Clone repository
git clone https://github.com/naiiytom/baan-ing-landing.git
cd baan-ing-landing

# 2. Install dependencies
npm install

# 3. Start local development server
npm run dev

# 4. Build optimized production bundle
npm run build

# 5. Preview production build locally
npm run preview
```

---

## 🚀 Deployment to Cloudflare Pages

The landing page is pre-configured with `wrangler.toml` for zero-configuration Cloudflare Pages deployment:

```bash
# Deploy to Cloudflare Pages directly
npm run deploy
```

Alternatively, connect your GitHub repository to Cloudflare Pages with the following build settings:
- **Build command**: `npm run build`
- **Build output directory**: `dist`
- **Root directory**: `landing` (or `/` if standalone repository)

---

## 📁 Repository Structure

```text
landing/
├── public/                     # Static assets served at root
│   ├── assets/                 # 3D GLB Models (.glb)
│   │   ├── Fridge.glb
│   │   ├── Modern Plywood Rocking Chair 3D Model.glb
│   │   ├── Natural Wood Ladder Bookshelf 3D Model.glb
│   │   ├── Scalloped Upholstered Bed 3D Model.glb
│   │   └── Tropical Rattan Plant 3D Model.glb
│   ├── robots.txt              # Search crawler directives
│   └── sitemap.xml             # Canonical sitemap
├── index.html                  # Main landing page
├── privacy.html                # PDPA Privacy Policy
├── terms.html                  # Architectural Terms of Service
├── security.html               # Security & Isolation Architecture
├── wrangler.toml               # Cloudflare Pages / Workers configuration
├── package.json                # Project scripts & dependencies
├── README.md                   # Repository documentation
├── LICENSE                     # MIT License
├── CODE_OF_CONDUCT.md          # Contributor Covenant Code of Conduct
├── CONTRIBUTING.md             # Contribution guidelines
└── SECURITY.md                 # Vulnerability disclosure policy
```

---

## 📄 License & Governance

- **Source Code**: Released under the [MIT License](LICENSE).
- **Design Specifications**: Governed by [`DESIGN.md`](../DESIGN.md).
- **Code of Conduct**: [Contributor Covenant v2.1](CODE_OF_CONDUCT.md).
- **Security Policy**: [Vulnerability Disclosure Guidelines](SECURITY.md).