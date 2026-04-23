# Portfolio Website — Brand Guide

Last updated: 23 April 2026

This guide documents the *current* live styles used across the portfolio site (home + case study pages) based on `styles.css`, `case-studies.css`, and the case study page inline overrides.

---

## Brand look & feel

- Minimal, high-contrast monochrome foundation (Charcoal + White/Stone).
- Warm neutral accent (Taupe/Sand) for labels, outlines, and soft surfaces.
- Electric Cyan highlight for interaction/“signal” moments (hover, focus, key metrics).

---

## Typography

### Font family

- Primary: `Inter`
- Fallback stack: `-apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`
- Loaded weights (Google Fonts): `300, 400, 500, 600, 700`
- Used weights (CSS): `400, 500, 600, 700`

**Implementation**

- Google Fonts include (present in `index.html` and case study pages):
  - `family=Inter:wght@300;400;500;600;700`
- CSS variable:
  - `--font: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;`

### Type rules (how to use)

- Headings: `font-weight: 700` with slight negative tracking (`letter-spacing: -0.02em` to `-0.025em`).
- Labels/tags: uppercase with strong tracking (`letter-spacing: 0.1em–0.15em`), typically `font-weight: 600`.
- Body: readable line-height (typically `1.6–1.75`), default weight `400`.
- Links: inherit colour; rely on hover colour shifts rather than underlines.

### Type styles (current site)

Notes:
- Many sizes use `rem`/`clamp()`; `rem` is relative to the browser root font size (usually 16px).
- “Case study overrides” are inline `<style>` rules inside some case study pages.

| Style name | Selector (typical) | Size | Weight | Tracking | Case | Line-height |
|---|---|---:|---:|---:|---|---:|
| Base body | `body` | `12px` | 400 | — | Sentence case | 1.65 |
| Nav logo | `.nav-logo` | `1.1rem` | 700 | `0.12em` | Uppercase | — |
| Nav links | `.nav-links a` | `0.875rem` | 500 | — | Sentence case | — |
| Section label | `.section-label` | `0.75rem` | 600 | `0.15em` | Uppercase | — |
| Section title | `.section-title` | `clamp(1.25rem, 2.2vw, 1.75rem)` | 700 | `-0.02em` | Sentence case | 1.2 |
| Hero label | `.hero-label` | `0.9rem` | 600 | `0.15em` | Uppercase | — |
| Hero headline | `.hero-headline` | `clamp(1.7rem, 3.8vw, 2.55rem)` | 700 | `-0.025em` | Sentence case | 1.1 |
| Hero subheading | `.hero-sub` | `1.03rem` | 400 | — | Sentence case | 1.58 |
| Button text | `.btn` | `0.875rem` | 600 | — | Sentence case | — |
| Capability title | `.cap-title` | `1rem` | 600 | — | Sentence case | — |
| Capability body | `.cap-text` | `0.9rem` | 400 | — | Sentence case | 1.65 |
| Work card tag | `.work-card-tag` | `0.7rem` | 500 | `0.1em` | Uppercase | — |
| Work card title | `.work-card-title` | `1.2rem` | 600 | — | Sentence case | — |
| Work card body | `.work-card-text` | `0.95rem` | 400 | — | Sentence case | 1.7 |
| Footer text | `.footer-text` | `0.8rem` | 400 | — | Sentence case | — |
| Case study title | `.cs-title` | `clamp(1.6rem, 3vw, 2.2rem)` | 700 | `-0.025em` | Sentence case | 1.22 |
| Case study subtitle | `.cs-subtitle` | `1.1rem` | 400 | — | Sentence case | 1.7 |
| Case study metrics value | `.cs-metric-value` | `1.75rem` | 700 | `-0.02em` | — | 1 |
| Case study section title (override) | `.cs-section-title` (inline) | `0.917rem` | — | — | Sentence case | — |
| Case study pilot note (override) | `.cs-pilot-note` (inline) | `0.82rem` | — | — | Sentence case | 1.55 |
| Compact metric value (override) | `.cs-metric-value-compact` (inline) | `calc(1.75rem - 4pt)` | — | — | — | — |

---

## Colour palette

### Core palette (CSS variables)

| Token | Hex | Use |
|---|---|---|
| `--charcoal` | `#000000` | Primary text, dark surfaces, primary buttons |
| `--taupe` | `#C4B5A5` | Labels, outlines, soft accent blocks (logo band), UI accents |
| `--stone` | `#F6F3F2` | Soft section backgrounds (About, Footer), subtle surfaces |
| `--sand` | `#A89888` | Secondary text, muted links, supporting text |
| `--white` | `#ffffff` | Base surface/background, text on dark sections |
| `--bg` | `#ffffff` | Site background |

### Accent & extended palette (hard-coded in CSS)

| Name | Hex | Use |
|---|---|---|
| Cyan highlight | `#00f5ff` | Hover/focus highlight, hero highlight hover, key metrics, icon strokes |
| Warm gradient tints | `#d9cfc4`, `#cec1b3`, `#c4b5a5` | Contact section background gradient |
| Off-white surface | `#faf8f6` | Contact link cards, tags background |
| Dark banner gradient | `#18111a`, `#2a1f22`, `#402d2e` | Motion banner background gradient |
| Pathfindr deep tones | `#0c141d`, `#182833`, `#101113` | Project card image gradient (Pathfindr) |
| Pathfindr light text | `#dcfbff` | Text on Pathfindr gradient |

### Colour usage rules

- Default text: `--charcoal` on `--white`/`--stone`.
- Muted/supporting text: `--sand` (avoid for small text on light backgrounds if legibility drops).
- Labels: `--taupe` + uppercase tracking (signals hierarchy without visual noise).
- Interaction: use Cyan (`#00f5ff`) for hover/focus and “key result” emphasis; do not use it as a general-purpose brand colour for large surfaces.
- Dark surfaces: `#000000` with `--white` text; reserve Cyan for highlights and metrics.

---

## Layout tokens (CSS variables)

These are the current design tokens used for spacing and rhythm:

- Spacing: `--space-xs: 0.5rem`, `--space-sm: 1rem`, `--space-md: 1.5rem`, `--space-lg: 3rem`, `--space-xl: 5rem`, `--space-2xl: 8rem`
- Content width: `--max-width: 1120px`
- Radius: `--radius: 6px` (with component overrides like 10px portrait, 16px contact cards)
- Motion: `--transition: 0.3s ease`

---

## Component colour rules (current site)

### Navigation / header

| Element | Value | Notes |
|---|---|---|
| Nav background | `rgba(246, 243, 242, 0.92)` | Base hex `--stone` (`#F6F3F2`) at 92% opacity — frosted/translucent effect. See `styles.css:94` |

### Buttons

| Component | Default | Hover |
|---|---|---|
| Primary (`.btn-primary`) | bg `--charcoal`, text `--white` | bg `#00f5ff`, text `--charcoal` |
| Secondary (`.btn-secondary`) | bg transparent, text `--charcoal`, border `--taupe` | bg `--taupe`, text `--white` |
| Ghost (`.btn-ghost`) | text `--sand` | text `--charcoal` |

### Tags/labels

- Section labels: `--taupe`, uppercase, high tracking.
- Case study tags (overrides on some pages): black background + Cyan text for emphasis.

### Dark cards (Capabilities + Case study tiles)

- Surface: `#000000`
- Text: `#ffffff`
- Highlights/icons/metrics: `#00f5ff`

---

## Quick reference (copy/paste)

### CSS colour tokens

```css
:root{
  --charcoal:#000000;
  --taupe:#C4B5A5;
  --stone:#F6F3F2;
  --sand:#A89888;
  --white:#ffffff;
  --bg:#ffffff;
}
```

### Font stack token

```css
:root{
  --font:'Inter',-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;
}
```
