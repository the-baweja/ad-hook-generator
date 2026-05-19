# Baweja Media Branding Reference for DOCX Output

All skills in this suite output branded DOCX files using the `docx` npm package (docx-js). Use this reference for consistent branding across all deliverables.

## Brand Colors

```javascript
const BM_PRIMARY = "23B323";   // Primary green
const BM_TEAL = "24B27C";      // Teal-green (links, accents)
const BM_OFFWHITE = "E7F1E6";  // Light green background (callout boxes)
const BM_DARK_GREEN = "1B5E20"; // Dark green (table headers)
const BM_BLACK = "1A1A1A";     // Body text
const BM_GRAY = "6B7280";      // Secondary text
const BM_LIGHT_GRAY = "9CA3AF"; // Tertiary text, dividers
const WHITE = "FFFFFF";
const CW = 9360;                // Content width in DXA (twips)
```

## Typography

- **Headings**: Arial, bold
  - H1: 48 half-points (24pt), color BM_BLACK
  - H2: 32 half-points (16pt), color BM_BLACK
  - H3: 24 half-points (12pt), color BM_BLACK
- **Body**: Arial, 21 half-points (10.5pt), color BM_BLACK, line spacing 276
- **Labels**: Arial, bold, 17 half-points (8.5pt), color BM_PRIMARY, UPPERCASE
- **Code/Prompts**: Courier New, 17 half-points (8.5pt), color BM_BLACK

## Required Document Structure

Every output DOCX must include:

### Header
```
BAWEJA MEDIA    [tab]    [Document Title]
```
- "BAWEJA MEDIA" in BM_PRIMARY, bold, 17 half-points
- Document title in BM_GRAY, 17 half-points
- Bottom border: thin line in BM_LIGHT_GRAY

### Footer
```
Â© Baweja Media Â· bawejamedia.com    [tab]    Page [number]
```
- All text in BM_LIGHT_GRAY, 15 half-points

### Cover Page
1. Spacer (600 twips)
2. "BAWEJA MEDIA" label (BM_PRIMARY, bold, 26 half-points)
3. Green divider (6px border in BM_PRIMARY)
4. Spacer (200 twips)
5. Document title (bold, 56 half-points, BM_BLACK)
6. Subtitle (BM_PRIMARY, 32 half-points)
7. Description paragraph
8. Metadata labels (PREPARED FOR, DATE, etc.)

### Closing Page
1. Thin divider (BM_LIGHT_GRAY)
2. "BAWEJA MEDIA" (bold, 24 half-points, BM_PRIMARY)
3. Tagline: "Clear thinking. Disciplined systems. Growth decisions grounded in signal." (italic)
4. Link: bawejamedia.com (BM_TEAL)

### CTA Button (when applicable)
Green button (BM_PRIMARY background) with white bold text, centered, links to:
`https://webinar.sannidhyabaweja.com/vsl-lp-ind`

## Component Library (docx-js Helper Functions)

Include these helpers in every generation script:

```javascript
const noBorder = { style: BorderStyle.NONE, size: 0, color: WHITE };
const noBorders = { top: noBorder, bottom: noBorder, left: noBorder, right: noBorder };

function h1(t) { /* HeadingLevel.HEADING_1, size: 48, bold, BM_BLACK */ }
function h2(t) { /* HeadingLevel.HEADING_2, size: 32, bold, BM_BLACK */ }
function h3(t) { /* size: 24, bold, BM_BLACK */ }
function body(t) { /* size: 21, line: 276, BM_BLACK */ }
function greenLabel(t) { /* UPPERCASE, bold, size: 17, BM_PRIMARY */ }
function spacer(p) { /* Empty paragraph with spacing */ }
function greenDivider() { /* Bottom border in BM_PRIMARY */ }
function thinDivider() { /* Bottom border in BM_LIGHT_GRAY */ }

function calloutBox(label, bodyText) {
  /* Table with BM_OFFWHITE background, no borders, with optional label */
}

function promptBlock(text) {
  /* Table with BM_OFFWHITE background, Courier New font */
}

function brandedTable(headers, rows, colWidths) {
  /* Table with BM_DARK_GREEN header row, white text, data rows with light borders */
}

function ctaButton(text, url) {
  /* Table with BM_PRIMARY background, white bold text, centered, hyperlinked */
}
```

## Design Principles

- **Whitespace = confidence.** Generous spacing between sections. Never crowd content.
- **Green for structure, not decoration.** Use BM_PRIMARY for labels, dividers, table headers, and CTAs. Not for backgrounds or decorative elements.
- **Premium restraint.** No rounded corners, no badges, no colored cover blocks. Clean pages, minimal elements.
- **Every page should breathe.** If content feels dense, add a page break.
