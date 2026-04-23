# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static portfolio website for Saurabh Sharma, a Government & Public Sector professional. The site is built with semantic HTML, inline CSS, and vanilla JavaScript—no build tools or frameworks.

**Deployed to**: GitHub Pages (automatic on push to `main`)  
**Main file**: `Html/index.html`

## Architecture

### Layout & Design System
- **Two-column hero**: Dark forest green left side (name, intro) + sand/cream right side (stats, image)
- **Color palette**: CSS variables defined in `:root` (forest, moss, gold, sand, cream, ink)
- **Typography**: Playfair Display (headings), Source Serif 4 (body), DM Mono (labels/monospace)
- **Responsive**: Grid breakpoint at 900px; single-column below

### Sections (all in single HTML file)
1. **Navigation** — Fixed, with scroll shadow effect
2. **Hero** — Name, intro, contact info, stats, profile image
3. **About** — Biography, skill tags, expertise/sectors/organizations
4. **Impact** — 5-column grid with numbered achievements (animated counters)
5. **Experience** — Timeline with 7 jobs (KPMG, PwC, Grant Thornton, UPSRLM, Aisses, UNDP, EDII)
6. **Education** — 2-card grid (EDII diploma, BMS)
7. **Contact** — 3-column contact grid, CTA buttons
8. **Footer** — Copyright info

### JavaScript Features
- **Intersection Observer**: Fade-in animations on scroll for timeline items and content blocks
- **Animated counters**: Numbers count up when section enters viewport
- **Scroll shadow**: Nav bar gets shadow on scroll
- **CSS transitions**: Hover effects throughout (buttons, links, stat cards)

## Common Tasks

### Editing Content
- Update text, jobs, education in `Html/index.html` (lines are clearly labeled)
- Add/remove sections by duplicating and modifying existing section blocks
- Update years, titles, achievements without touching CSS

### Styling Changes
- All CSS is inline in `<style>` block (lines 8–506)
- Modify color variables in `:root` (lines 9–20) to change palette globally
- Responsive rules are in `@media (max-width: 900px)` (line 558+)

### Adding Images
- Place image files in `Html/` folder
- Reference them as relative paths (e.g., `src="image.jpeg"`)
- Example: Profile image at line 581 uses `saurabh image.jpeg`

### Testing Locally
- Open `Html/index.html` directly in a browser (no server needed)
- Or use any local server: `python -m http.server` in the `Html/` folder, then visit `localhost:8000`

### Deployment
- Push to `main` branch → GitHub Actions (`.github/workflows/deploy.yml`) builds & deploys to GitHub Pages automatically
- Workflow uploads `Html/` folder as the site root

## Key Points for Future Work

- **No build step**: Changes are live when committed. Keep file sizes and performance in mind.
- **Accessibility**: Currently uses semantic HTML and keyboard-accessible links. Test with screen readers if adding complex interactions.
- **Performance**: Inline CSS avoids extra HTTP requests. Keep scripts minimal to maintain fast loads.
- **Image optimization**: Profile image and others should be optimized (compressed) before adding—GitHub Pages has limited bandwidth.
- **Animation smoothness**: Intersection Observer threshold is `0.12` (line 937); adjust if animations trigger too early/late.
