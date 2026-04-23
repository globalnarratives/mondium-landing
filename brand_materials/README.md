# Handoff: Mondium Brand System

## Overview

This handoff contains the Mondium brand lockups and tokens — the identity system for **mondium.ai**, a structured-encoding infrastructure company. Implement this system anywhere the Mondium brand appears: the landing site, the product UI chrome, app icons, favicons, signature blocks, printed materials.

The tagline is **"The world, encoded."** A backup Latin motto — *Omnia Vincit Veritas* ("Truth conquers all") — is used for formal / signature contexts.

## About the design files

The files in this bundle are **design references**, not production code to copy directly. The HTML previews (in `reference/`) are showing what the marks and lockups should look like. Your job is to recreate this system in the target codebase's native patterns — React + CSS Modules, Tailwind, Vue, Svelte, plain HTML/CSS, SwiftUI, etc.

The **`assets/` folder** contains the canonical artifacts you can drop in directly:
- `mondium-mark.svg` — the bracket mark, color-agnostic via `currentColor` and two CSS vars
- `mondium-mark-cyan.svg`, `mondium-mark-mint.svg` — pre-colored marks
- `mondium-favicon.svg` — bracket mark in a square, safe for browser favicon usage
- `mondium-lockup-primary.svg` — full primary lockup (mark + rule + wordmark + tagline)
- `mondium-lockup-backup.svg` — stacked backup lockup with Latin motto
- `tokens.css` — CSS custom properties for color + type
- `tokens.json` — same tokens, JSON for tooling / Style Dictionary

## Fidelity

**High-fidelity.** Colors, typography, weights, tracking, stroke widths, and proportions are final. Recreate pixel-perfectly.

## The mark

A three-level nested bracket set collapsing onto a single core token. Metaphor: discrete political events (prose) compressed into a structured, machine-parseable record.

- **Intrinsic aspect ratio:** 180 × 80 (9 : 4). Preserve this; do not stretch.
- **Anatomy** — three levels of angle brackets + a solid core rectangle:
  - Outer brackets: `ink`, opacity 0.35, stroke 1.2
  - Mid brackets: `ink`, opacity 0.65, stroke 1.2
  - Inner brackets: `teal`, opacity 1, stroke 1.4
  - Core: solid `teal` rectangle, 6 × 12
- **Clear space:** at least 1× bracket-height (i.e. 1× the viewBox 80-unit dimension, scaled) around the mark on all sides.
- **Minimum size:** 24px tall for the mark alone; 40px tall when locked up with the wordmark.
- **Do not:** recolor the brackets individually beyond the provided palettes; rotate or skew the mark; apply shadows, gradients, or outlines; swap the core shape for an icon.

## Typography

Two families. Nothing else.

### Space Grotesk

- **Wordmark (primary):** `Space Grotesk`, weight **300**, `letter-spacing: 0.18em`, **uppercase** — "MONDIUM".
- **Wordmark (backup / signature):** `Space Grotesk`, weight **300**, tracking 0.01em, cased — "Mondium".
- **Headings:** `Space Grotesk`, weight 400, `letter-spacing: -0.02em`. For large hero (56px+), italicize key nouns at weight 500 in `--teal` for emphasis.
- **Body:** `Space Grotesk`, weight 300, tracking 0.

Google Fonts: `https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&display=swap`

### JetBrains Mono

- **Tagline ("The world, encoded"):** `JetBrains Mono`, weight 400, `letter-spacing: 0.30em`, **uppercase**, color `--teal`.
- **Small captions / micro-labels:** `JetBrains Mono`, weight 400, `letter-spacing: 0.18–0.22em`, uppercase, color at ~45% ink opacity.
- **Code / CIE snippets:** `JetBrains Mono`, weight 400–500.

Google Fonts: `https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500&display=swap`

### Latin motto

- `Space Grotesk`, weight 400, `letter-spacing: 0.44em`, uppercase, color `--teal`.
- Rendered as `OMNIA · VINCIT · VERITAS` (middots between words).

## Palette

Two official palettes — **Cold Cyan** is the canonical hero palette, **Mint** is the secondary / alternate palette. Do not mix cyan and mint in the same view.

### Cold Cyan (canonical)

| Token        | Value                         | Notes                              |
|--------------|-------------------------------|------------------------------------|
| `--bg`       | `#090D10`                     | Near-black with cool cast          |
| `--teal`     | `oklch(0.78 0.10 220)`        | Primary accent — links, rule, core |
| `--ink`      | `#E6EBEF`                     | Foreground text                    |

### Mint (alternate)

| Token        | Value                         |
|--------------|-------------------------------|
| `--bg`       | `#0D1413`                     |
| `--teal`     | `oklch(0.80 0.10 170)`        |
| `--ink`      | `#EAEFEC`                     |

### Safety palettes

For single-color reproduction (print, signatures, favicons against unknown surfaces):

| Context    | bg        | ink/teal  |
|------------|-----------|-----------|
| Black      | `#000000` | `#FFFFFF` |
| White      | `#FFFFFF` | `#000000` |
| Parchment  | `#EFEAE0` | `#17140F` |

In safety palettes, all three mark elements collapse to the single ink color.

## Lockups

### Primary lockup — `mondium-lockup-primary.svg`

Horizontal. Left → right:

1. **Mark** — 140px wide (scales proportionally)
2. **Vertical rule** — 1px, `--ink` at 20% opacity, 60px tall, 26px gap on each side
3. **Stack:**
   - "MONDIUM" — Space Grotesk 300, 36px, tracking 0.18em, uppercase, `--ink`
   - "The world, encoded" — JetBrains Mono 400, 10px, tracking 0.30em, uppercase, `--teal`

Gap between wordmark and tagline: 10px. Use this lockup for nav bars, email signatures, page headers.

### Backup lockup — `mondium-lockup-backup.svg`

Stacked, centered. Top → bottom:

1. **Mark** — 170px wide
2. **"Mondium"** — Space Grotesk 300, 44px, tracking 0.01em, cased, `--ink`. 10px below mark.
3. **"OMNIA · VINCIT · VERITAS"** — Space Grotesk 400, 12px, tracking 0.44em, uppercase, `--teal`. 4px below wordmark.

Use this lockup for formal contexts: signature pages, about, contact, document footers.

## Hero / landing-page treatment

The canonical hero uses the Cold Cyan palette at weight 400.

- Page bg `--bg`, with an optional 80×80px grid overlay at 3% `--ink` opacity for texture.
- Nav: primary lockup inline with mono nav links (`Home`, `The Problem`, `What Is CIE`, `Examples`, `Contact`), tracked 0.20em, 10px.
- H1: Space Grotesk 400, 56–60px, line-height 1.08, letter-spacing −0.02em, `text-wrap: pretty`.
  - Italicize key nouns (e.g. *news*, *intelligence*) at weight 500 in `--teal`.
- Sub-lead: Space Grotesk 300, 17px, `--ink` at ~72% opacity, max-width ~680px.
- Primary button: 13px × 24px padding, 1px `--teal` border, text `--teal`, JetBrains Mono 10px tracked 0.24em uppercase.
- Secondary button: same geometry, 1px `--ink` at 20% opacity border, text `--ink` at 75% opacity.
- Footer caption: JetBrains Mono 9px, tracking 0.3em, `--ink` at 33% opacity.

See `reference/Mondium Brand Sheet.html` — the "Hero — Cyan 400" artboard is the pixel reference.

## Favicon / app icon

- Square; rounded corners at 48px / ~22% radius for iOS-style, or 0 for square.
- Background: `--bg` (Cyan preferred; Mint acceptable).
- Centered mark at ~68% width of the icon.
- For small sizes (≤ 32px) the mid-bracket opacity layer can be dropped — just use the two outer-opacity + the teal inner brackets to preserve legibility.
- `assets/mondium-favicon.svg` ships as the canonical SVG favicon.

## Do / don't

**Do**
- Use `--teal` sparingly. It is for accent — rules, the mark core, the tagline, italicized emphasis words, primary CTA borders.
- Keep backgrounds near-black (`--bg`), not pure black.
- Keep tracking generous on small uppercase type (0.18em minimum).

**Don't**
- Don't set body copy in JetBrains Mono — it's strictly for technical/tagline/code use.
- Don't use Space Grotesk below 300 or above 500 for brand text (300 for wordmark, 400–500 for UI).
- Don't add new accent colors. If you need state color, derive from `--teal` (e.g. reduced opacity) or `--ink`.
- Don't add drop shadows, gradients, glows, or 3D effects to the mark.
- Don't use the Latin motto on every page; reserve it for signature / formal moments.

## Files in this handoff

- `README.md` — this document
- `assets/mondium-mark.svg` — generic mark using CSS variables
- `assets/mondium-mark-cyan.svg` — mark pre-colored for Cold Cyan bg
- `assets/mondium-mark-mint.svg` — mark pre-colored for Mint bg
- `assets/mondium-favicon.svg` — square favicon mark
- `assets/mondium-lockup-primary.svg` — primary horizontal lockup
- `assets/mondium-lockup-backup.svg` — backup stacked lockup w/ Latin motto
- `assets/tokens.css` — design tokens as CSS custom properties
- `assets/tokens.json` — design tokens as JSON
- `reference/Mondium Brand Sheet.html` — visual reference; open in a browser
- `reference/design-canvas.jsx` — required for the reference HTML to render

## Typography quick-copy

```css
/* HTML <head> */
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
```

```css
/* usage */
.mondium-wordmark {
  font-family: "Space Grotesk", system-ui, sans-serif;
  font-weight: 300;
  letter-spacing: 0.18em;
  text-transform: uppercase;
  color: var(--ink);
}
.mondium-tagline {
  font-family: "JetBrains Mono", ui-monospace, monospace;
  font-weight: 400;
  font-size: 10px;
  letter-spacing: 0.30em;
  text-transform: uppercase;
  color: var(--teal);
}
```
