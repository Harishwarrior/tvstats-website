# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static marketing website for TVStats, an Apple TV system monitoring application. The site showcases the app's ability to track CPU usage, memory statistics, and other performance metrics on Apple TV devices.

## Architecture

**Static site** - Two HTML pages (`index.html` and `privacy-policy.html`) with no build process or dependencies. Self-contained HTML files with inline CSS and JavaScript.

**Pages:**
- `index.html` - Main landing page with carousel
- `privacy-policy.html` - Privacy policy page emphasizing offline operation and no data collection
- `copyright.html` - Copyright and licensing information

**Key components (index.html):**
- **Content section** (left): Logo, tagline, description, download button, and footer links (Privacy Policy, Copyright)
- **Carousel section** (right): Auto-rotating image carousel displaying app screenshots
- **Screenshots**: Located in `screenshots/` directory with naming convention `light_1.png`, `light_2.png`, `light_3.png`, `dark_1.png`, `dark_2.png`, `dark_3.png`

## Design System

**Typography**: Uses Inter font family from Google Fonts (weights: 300, 400, 600, 700)

**Color scheme**:
- Background: Pure white (#ffffff)
- Primary text: Dark gradients (#1a1a1a to #4a4a4a)
- Secondary text: #2c3e50
- Tertiary text: #6c757d

**Button styling**:
- Uses Apple-style continuous borders (50px border-radius for pill shape)
- Dark gradient background with smooth animations

**Carousel controls**:
- Auto-hide after 3 seconds of inactivity
- Reappear on mouse hover/movement or keyboard navigation
- Small circular buttons (36px) with subtle shadows

## Running the Site

Simply open `index.html` in a browser:
```bash
open index.html
```

No build process, dependencies, or server required.

## Deployment

The site automatically deploys to GitHub Pages via GitHub Actions on every push to `main`.

**Workflow file**: `.github/workflows/deploy.yml`

**Manual deployment**: You can also trigger deployment manually from the Actions tab in GitHub.

**Setup requirements** (one-time):
1. Go to repository Settings → Pages
2. Set Source to "GitHub Actions"
3. The workflow will deploy on the next push

## Making Changes

**Updating screenshots**: Replace files in `screenshots/` directory maintaining the naming convention (light_1-3.png, dark_1-3.png), then update image src paths in the carousel HTML if filenames change.

**Styling**: All CSS is inline in the `<style>` tag within `index.html`.

**Carousel behavior**: JavaScript at the bottom of `index.html` controls auto-rotation (4 second interval) and hide/show logic for controls.

**Download link**: Update the `href` attribute on the `.download-btn` link when the actual download URL is available.
