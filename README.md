# BAAN/ING - Landing Page

The official standalone landing page for **BAAN/ING** (Smart Design. Real Spaces.), powered by **Vite** and ready for deployment to **Cloudflare Workers / Pages**.

## Features
- **Vite Build System**: Fast dev server, instant HMR, and optimized static production builds.
- **Cloudflare Ready**: Includes `wrangler.toml` pre-configured for Cloudflare Pages / Workers deployment.
- **Design System Integration**: Matches the precision architectural aesthetic with custom Tailwind tokens, glassmorphism, drafting grid background, and Material Symbols.

## Local Development

```bash
# Install dependencies
npm install

# Start Vite dev server
npm run dev

# Build production bundle (outputs to dist/)
npm run build

# Preview production build locally
npm run preview
```

## Deploying to Cloudflare

```bash
# Deploy directly via Wrangler
npm run deploy
```