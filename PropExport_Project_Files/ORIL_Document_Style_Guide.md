# ORIL Document Brand Style Guide
> Upload this file to your Claude project. When generating documents, reference this file for all styling decisions.

---

## Purpose
This style guide defines the exact typography, color, spacing, and layout rules extracted from the ORIL Design Assessment Template. Any document generated in this project must follow these specifications precisely.

---

## 1. Fonts

| Role | Font | Fallback |
|---|---|---|
| Body text | Proxima Nova | Arial |
| All headings | Arial | sans-serif |
| Subheadings (H4–H6) | Trebuchet MS | sans-serif |

**Rule:** Use Proxima Nova for all body/paragraph text. Use Arial for all section headings (H1–H3). Use Trebuchet MS for lower-level labels (H4–H6). In Google Docs, Proxima Nova must be installed; if unavailable, fall back to Arial throughout.

---

## 2. Color Palette

| Token Name | Hex | Usage |
|---|---|---|
| Charcoal Dark | `#404040` | Document title, primary headings |
| Charcoal Mid | `#434343` | Company name on cover page |
| Gray Medium | `#666666` | Subtitles, H4–H6 labels, metadata text |
| Gray Light | `#999999` | Captions, footnotes, secondary labels |
| Brand Blue | `#4a86e8` | Hyperlinks, accent elements |
| Table Header Yellow | `#ffe599` | Table header row background |
| Severity Amber | `#ff9900` | Moderate severity indicators |
| Severity Red | `#ff0000` | Severe/critical severity indicators |
| Border Dark | `#000000` | Table outer borders |
| Border Light | `#d9d9e3` | Table inner dividers |

---

## 3. Typography Scale

### Cover Page
| Element | Font | Size | Weight | Color | Notes |
|---|---|---|---|---|---|
| Company name | Arial | 36pt | Regular | `#434343` | Top of cover, above title |
| Document title | Arial | 48pt | Regular | `#404040` | Main cover title, large |
| Cover metadata (author, date) | Arial | 11pt | Regular | `#666666` | Right-aligned, below title |

### Body Text
| Element | Font | Size | Weight | Color | Line Height |
|---|---|---|---|---|---|
| Body paragraph | Proxima Nova / Arial | 11pt | Regular | `#000000` | 1.25 |
| Italic body (captions, notes) | Proxima Nova / Arial | 11pt | Italic | `#000000` | 1.25 |

### Heading Hierarchy
| Level | Font | Size | Weight | Color | Decoration | Spacing Before |
|---|---|---|---|---|---|---|
| H1 | Arial | 20pt | Regular | `#000000` | None | 20pt |
| H2 | Arial | 14pt | Regular | `#000000` | None | Default |
| H3 | Arial | 12pt | Regular | `#000000` | None | Default |
| H4 | Trebuchet MS | 11pt | Regular | `#666666` | Underline | 8pt |
| H5 | Trebuchet MS | 11pt | Regular | `#666666` | None | 8pt |
| H6 | Trebuchet MS | 11pt | Italic | `#666666` | None | 8pt |

---

## 4. Table Styling

### Structure Rules
- All tables use fixed layout
- Outer borders: 1pt solid `#000000`
- Inner horizontal and vertical borders: 1pt solid `#000000`
- Cell padding: ~2pt on all sides (uniform)
- Minimum row height: ~30pt

### Header Row
- Background fill: `#ffe599` (warm yellow)
- Font: Arial, 11pt, Regular
- Text color: `#000000`

### Body Rows
- Background fill: White (no fill)
- Font: Arial, 10–11pt, Regular
- Text color: `#000000`
- Alternating row shading: Not used — rows differentiated by content only

### Severity Color Coding in Tables
When a table includes a Severity or Status column, use these rules for the cell text color:
- **Low** — `#000000` black, no special color
- **Moderate** — `#ff9900` amber
- **Severe / Critical** — `#ff0000` red

---

## 5. Page Layout

| Setting | Value |
|---|---|
| Page size | US Letter (8.5 × 11 in) |
| Margins | 1 inch all sides |
| Body text alignment | Left |
| Line spacing | 1.25 |
| Space before body paragraph | 10pt |

---

## 6. Cover Page Structure

The cover page follows this layout (top to bottom):

1. **Decorative element** — A short horizontal rule or thin line element (brand accent, ~0.5 inch wide), left-aligned
2. **"Prepared by ORIL"** — Right-aligned, Arial 11pt, `#666666`
3. **Date (MM/DD/YYYY)** — Right-aligned directly below "Prepared by ORIL"
4. *(Large vertical gap)*
5. **Company name "ORIL"** — Left, Arial 36pt, `#434343`
6. **Document title** — Left, Arial 48pt, `#404040`, on its own line (e.g., "PROJECT_NAME Design Assessment")
7. **Page break** before Table of Contents

---

## 7. Table of Contents

- Included on page 2 (after cover page break)
- H1 entries: bold, linked
- H2 entries: indented, not bold, linked
- No page numbers in the TOC (Google Docs auto-generates them)
- TOC title: not shown as a separate heading — TOC starts immediately

---

## 8. Section Structure Pattern

Each major section follows this pattern:

1. **H1 heading** — Section name (Arial 20pt)
2. **Introductory paragraph** — 1–3 sentences providing context for the section (body text)
3. **H2 subsections** — Each subsection covers one finding or topic
4. Within each H2:
   - Numbered observation (bold label "Observation")
     - Bullet points expanding on the finding
   - Numbered recommendation (bold label "Recommendations")
     - Bullet points with proposed improvements
   - *(Optional)* Italic caption referencing screenshots or attachments

---

## 9. Applying This Guide in Google Docs

When generating a document for Google Docs, apply the following Google Docs-native equivalents:

| This guide | Google Docs equivalent |
|---|---|
| H1 (Arial 20pt, black) | Heading 1 — customize to Arial 20pt `#000000` |
| H2 (Arial 14pt, black) | Heading 2 — customize to Arial 14pt `#000000` |
| H3 (Arial 12pt, black) | Heading 3 — customize to Arial 12pt `#000000` |
| Body (Proxima Nova/Arial 11pt) | Normal text — Arial 11pt |
| Table header row | Table row with background `#ffe599` |
| Severity: Moderate | Cell text color `#ff9900` |
| Severity: Severe | Cell text color `#ff0000` |
| Cover title | Title style — Arial 48pt `#404040` |
| Cover subtitle / metadata | Subtitle style — Arial 11pt `#666666`, right-aligned |

The document should be generated as a **Google Apps Script** (`.gs` file) that, when run from script.google.com, creates a fully styled Google Doc in the user's Drive. The script must apply all custom styles inline (font, size, color, background) since Google Apps Script cannot modify built-in Heading styles globally in the same way as a style sheet.
