# Branding Reference for DOCX Output

All skills in this suite output branded DOCX files using the `docx` npm package (docx-js). Customize the values below to match your agency or brand. Replace every placeholder marked with `[YOUR_...]` before running.

## Brand Colors

```javascript
// ââ CUSTOMIZE THESE FOR YOUR BRAND ââ
const BRAND_PRIMARY = "23B323";       // Your primary accent color (used for labels, dividers, table headers, CTAs)
const BRAND_SECONDARY = "24B27C";     // Secondary accent (links, highlights)
const BRAND_LIGHT_BG = "E7F1E6";      // Light background tint for callout boxes
const BRAND_DARK = "1B5E20";          // Dark accent (table header backgrounds)
const BRAND_BLACK = "1A1A1A";         // Body text color
const BRAND_GRAY = "6B7280";          // Secondary text
const BRAND_LIGHT_GRAY = "9CA3AF";    // Tertiary text, dividers
const WHITE = "FFFFFF";
const CW = 9360;                       // Content width in DXA (twips) â standard US Letter with 1" margins
```

## Typography

- **Headings**: Arial, bold
  - H1: 48 half-points (24pt), color BRAND_BLACK
  - H2: 32 half-points (16pt), color BRAND_BLACK
  - H3: 24 half-points (12pt), color BRAND_BLACK
- **Body**: Arial, 21 half-points (10.5pt), color BRAND_BLACK, line spacing 276
- **Labels**: Arial, bold, 17 half-points (8.5pt), color BRAND_PRIMARY, UPPERCASE
- **Code/Prompts**: Courier New, 17 half-points (8.5pt), color BRAND_BLACK

## Required Document Structure

Every output DOCX must include:

### Header
```
[YOUR_BRAND_NAME]    [tab]    [Document Title]
```
- Brand name in BRAND_PRIMARY, bold, 17 half-points
- Document title in BRAND_GRAY, 17 half-points
- Bottom border: thin line in BRAND_LIGHT_GRAY

### Footer
```
Â© [YOUR_BRAND_NAME] Â· [YOUR_WEBSITE]    [tab]    Page [number]
```
- All text in BRAND_LIGHT_GRAY, 15 half-points

### Cover Page
1. Spacer (600 twips)
2. "[YOUR_BRAND_NAME]" label (BRAND_PRIMARY, bold, 26 half-points)
3. Colored divider (6px border in BRAND_PRIMARY)
4. Spacer (200 twips)
5. Document title (bold, 56 half-points, BRAND_BLACK)
6. Subtitle (BRAND_PRIMARY, 32 half-points)
7. Description paragraph
8. Metadata labels (PREPARED FOR, DATE, etc.)

### Closing Page
1. Thin divider (BRAND_LIGHT_GRAY)
2. "[YOUR_BRAND_NAME]" (bold, 24 half-points, BRAND_PRIMARY)
3. Tagline: "[YOUR_TAGLINE]" (italic)
4. Link: [YOUR_WEBSITE] (BRAND_SECONDARY)

### CTA Button (when applicable)
Colored button (BRAND_PRIMARY background) with white bold text, centered, links to:
`[YOUR_CTA_URL]`

## Component Library (docx-js Helper Functions)

Include these helpers in every generation script:

```javascript
const noBorder = { style: BorderStyle.NONE, size: 0, color: WHITE };
const noBorders = { top: noBorder, bottom: noBorder, left: noBorder, right: noBorder };

function h1(t) { /* HeadingLevel.HEADING_1, size: 48, bold, BRAND_BLACK */ }
function h2(t) { /* HeadingLevel.HEADING_2, size: 32, bold, BRAND_BLACK */ }
function h3(t) { /* size: 24, bold, BRAND_BLACK */ }
function body(t) { /* size: 21, line: 276, BRAND_BLACK */ }
function greenLabel(t) { /* UPPERCASE, bold, size: 17, BRAND_PRIMARY */ }
function spacer(p) { /* Empty paragraph with spacing */ }
function greenDivider() { /* Bottom border in BRAND_PRIMARY */ }
function thinDivider() { /* Bottom border in BRAND_LIGHT_GRAY */ }

function calloutBox(label, bodyText) {
  /* Table with BRAND_LIGHT_BG background, no borders, with optional label */
}

function promptBlock(text) {
  /* Table with BRAND_LIGHT_BG background, Courier New font */
}

function brandedTable(headers, rows, colWidths) {
  /* Table with BRAND_DARK header row, white text, data rows with light borders */
}

function ctaButton(text, url) {
  /* Table with BRAND_PRIMARY background, white bold text, centered, hyperlinked */
}
```

## Design Principles

- **Whitespace = confidence.** Generous spacing between sections. Never crowd content.
- **Accent color for structure, not decoration.** Use BRAND_PRIMARY for labels, dividers, table headers, and CTAs. Not for backgrounds or decorative elements.
- **Premium restraint.** No rounded corners, no badges, no colored cover blocks. Clean pages, minimal elements.
- **Every page should breathe.** If content feels dense, add a page break.

## Quick Setup Checklist

Replace these values before first use:

| Placeholder | Example | Where it appears |
|---|---|---|
| `BRAND_PRIMARY` | `"23B323"` | Labels, dividers, CTA buttons |
| `BRAND_SECONDARY` | `"24B27C"` | Links, accents |
| `BRAND_LIGHT_BG` | `"E7F1E6"` | Callout box backgrounds |
| `BRAND_DARK` | `"1B5E20"` | Table header backgrounds |
| `[YOUR_BRAND_NAME]` | `"ACME Agency"` | Header, footer, cover, closing |
| `[YOUR_WEBSITE]` | `"acmeagency.com"` | Footer, closing page |
| `[YOUR_TAGLINE]` | `"Growth through data."` | Closing page |
| `[YOUR_CTA_URL]` | `"https://acme.com/book"` | CTA button link |
