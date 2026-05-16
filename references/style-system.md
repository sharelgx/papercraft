# PagerCraft Style System

Use this reference when implementing or restyling a page in the Claude paper visual language.

## Palette

Core tokens:

```css
:root {
  /* Backgrounds */
  --ivory:         #FAF9F5;
  --paper:         #FFFFFF;
  --paper-warm:    #F7F4EC;
  --paper-deep:    #F3EEE4;

  /* Text */
  --ink:           #171716;
  --muted:         #706F68;
  --faint:         #A09E96;

  /* Borders */
  --line:          #D8D1C3;
  --line-strong:   #C8BBA8;
  --line-faint:    #EAE5DA;

  /* Clay / Rust — primary accent */
  --clay:          #C86645;
  --clay-dark:     #A84D32;
  --clay-hover:    #B55A3A;
  --clay-active:   #953F28;
  --clay-soft:     #FBEDE6;
  --clay-border:   #E8B49E;

  /* Olive / Sage — secondary / success */
  --olive:         #74845B;
  --olive-dark:    #56663E;
  --olive-hover:   #657650;
  --olive-soft:    #EDF1E7;
  --olive-border:  #B8C9A3;

  /* Amber — warning */
  --amber:         #B87A1A;
  --amber-soft:    #FBF1DF;
  --amber-border:  #DDB96A;

  /* Red — error / destructive */
  --red:           #B83030;
  --red-soft:      #FBEAEA;
  --red-border:    #DDA0A0;

  /* Blue — links / technical focus only */
  --blue:          #2D6BB0;
  --blue-soft:     #E8F0FB;
  --blue-border:   #9DBAE8;

  /* Disabled states */
  --disabled-bg:   #F0EDE6;
  --disabled-text: #B0ADA5;
  --disabled-border:#D8D1C3;
}
```

**Dark mode** (minimal override):

```css
@media (prefers-color-scheme: dark) {
  :root {
    --ivory:       #1C1B18;
    --paper:       #242320;
    --paper-warm:  #2A2825;
    --paper-deep:  #302E29;
    --ink:         #F0EDE6;
    --muted:       #9A9890;
    --faint:       #6E6C65;
    --line:        #3A3830;
    --line-strong: #4A4840;
    --line-faint:  #2E2C28;
    --clay-soft:   #3A201A;
    --olive-soft:  #1E2618;
    --amber-soft:  #2E2210;
    --red-soft:    #2E1414;
    --blue-soft:   #101E30;
  }
}
```

Use clay/rust for primary emphasis and selected states. Use olive/sage for healthy status, completion, and secondary accents. Use blue only for links or technical focus. Use amber for warnings, red for errors.

---

## Typography

Font stacks:

```css
--font-serif: ui-serif, Georgia, "Times New Roman", Times, serif;
--font-sans:  -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC",
              "Microsoft YaHei", "Helvetica Neue", Arial, sans-serif;
--font-mono:  ui-monospace, "SF Mono", Menlo, Consolas, "Courier New", monospace;
```

Font-size scale:

```css
--text-xs:   11px;   /* badges, captions, meta labels */
--text-sm:   13px;   /* table cells, secondary text, helper text */
--text-base: 15px;   /* body copy, form controls */
--text-md:   17px;   /* subheadings, card titles */
--text-lg:   20px;   /* section headings (h3) */
--text-xl:   24px;   /* page headings (h2) */
--text-2xl:  30px;   /* display headings (h1) */
--text-3xl:  38px;   /* editorial hero headings */
```

Line-height: `1.5` for body, `1.25` for headings, `1.4` for UI controls.

Letter spacing: `0` for most headings. Use `0.04em` only for small-caps mono labels (`--text-xs` uppercase).

Use `--font-serif` for section headings (h1–h3) and editorial display. Use `--font-sans` for body copy, data-dense surfaces, and all controls. Use `--font-mono` for paths, code, IDs, and export payloads.

---

## Spacing Scale

```css
--space-1:   4px;
--space-2:   8px;
--space-3:   12px;
--space-4:   16px;
--space-5:   20px;
--space-6:   24px;
--space-8:   32px;
--space-10:  40px;
--space-12:  48px;
--space-16:  64px;
--space-20:  80px;
--space-24:  96px;
```

Prefer multiples of 4. Inner padding for cards and panels: `--space-6` (24px). Row gaps in grids: `--space-4` to `--space-6`. Section vertical rhythm: `--space-12` to `--space-16`.

---

## Layout & Breakpoints

```css
--max-content:   1200px;   /* max page content width */
--max-reading:    720px;   /* reports and prose pages */
--sidebar-width:  224px;   /* admin side nav */
--topbar-height:   52px;

/* Breakpoints */
--bp-sm:   480px;   /* large phone */
--bp-md:   768px;   /* tablet */
--bp-lg:  1024px;   /* laptop */
--bp-xl:  1280px;   /* wide desktop */
```

Use warm page backgrounds with white or warm-white panels. Prefer `--max-reading` for reports and explainers, `--max-content` for admin consoles. For admin systems use a fixed side nav plus a scrollable main area — do not collapse everything into oversized cards. Use fine borders as structural dividers; keep `box-shadow` subtle and secondary.

Do not nest cards inside cards. Panels contain tables, controls, charts, or lists directly.

Responsive rules: at `--bp-md` and below, collapse the side nav to a hamburger drawer; stack KPI cards from grid to single-column; convert dense tables to card-list views.

---

## Shape & Elevation

```css
--radius-sm:  6px;   /* badges, chips, tags */
--radius-md:  8px;   /* inputs, buttons, small cards */
--radius-lg: 10px;   /* panels, modals */
--radius-xl: 14px;   /* large feature cards */

--shadow-xs: 0 1px 2px  rgba(23,23,22,0.06);
--shadow-sm: 0 2px 6px  rgba(23,23,22,0.08);
--shadow-md: 0 4px 16px rgba(23,23,22,0.10);
--shadow-lg: 0 8px 32px rgba(23,23,22,0.12);
```

---

## Transitions

```css
--ease-out:    cubic-bezier(0.22, 1, 0.36, 1);
--ease-in-out: cubic-bezier(0.45, 0, 0.55, 1);

--duration-fast: 120ms;   /* hover, focus ring */
--duration-base: 200ms;   /* button states, badge changes */
--duration-slow: 300ms;   /* drawer open/close, modal enter */
```

Standard interactive transition:
```css
transition: background var(--duration-base) var(--ease-out),
            border-color var(--duration-base) var(--ease-out),
            color var(--duration-base) var(--ease-out);
```

---

## Z-Index Scale

```css
--z-base:     0;
--z-raised:  10;   /* sticky table headers, topbar */
--z-dropdown:100;  /* menus, popovers */
--z-drawer:  200;  /* side drawer */
--z-modal:   300;  /* modal overlay */
--z-toast:   400;  /* toast notifications */
--z-tooltip: 500;  /* tooltips */
```

---

## Components

### Buttons

```
Primary:    background --ink (or --clay), color --paper, radius --radius-md
            hover:  background --clay-hover
            active: background --clay-active
Secondary:  background --paper, border 1.5px --line, color --ink
            hover:  background --paper-warm, border-color --line-strong
Destructive:background --red-soft, border 1.5px --red-border, color --red
            hover:  background #F5D8D8
Disabled:   background --disabled-bg, color --disabled-text,
            border --disabled-border, cursor not-allowed
```

Min height: 36px normal, 32px compact, 28px dense table actions.
Padding: `6px 14px` normal, `4px 10px` compact.

### Inputs

```
background --paper, border 1.5px --line, radius --radius-md, padding 8px 12px
focus:    border-color --clay, outline 2px solid --clay-soft (offset 0)
error:    border-color --red-border, background --red-soft
disabled: background --disabled-bg, color --disabled-text
```

Label: `--text-sm`, color `--muted`, margin-bottom `--space-1`.
Helper text: `--text-xs`, color `--muted`.
Error text: `--text-xs`, color `--red`.

### Select / Checkbox / Radio

Select: same visual as input; add custom chevron SVG in `--muted`; `appearance: none`.

Checkbox / Radio:
```
border 1.5px --line, radius 4px (checkbox) or 50% (radio)
checked:       background --clay, border-color --clay, checkmark in --paper
hover (unchecked): border-color --clay-border
focus:         outline 2px solid --clay-soft
```

### Tables

```
Header: background --paper-warm, font --font-sans --text-sm weight 600, color --muted
        border-bottom 1.5px --line-strong
Row:    border-bottom 1px --line-faint
        hover:    background #F5F3ED
        selected: background --clay-soft, left border 3px --clay
Cell:   padding 10px 14px, font --text-sm
```

Use badges for status — not text. Support sort indicators on header cells. Provide a sticky header for tables taller than viewport.

### Badges / Status Chips

```
Padding: 2px 8px, radius --radius-sm, font --text-xs weight 600
Success:  background --olive-soft, color --olive-dark, border 1px --olive-border
Warning:  background --amber-soft, color --amber,      border 1px --amber-border
Error:    background --red-soft,   color --red,        border 1px --red-border
Neutral:  background --paper-warm, color --muted,      border 1px --line
Info:     background --blue-soft,  color --blue,       border 1px --blue-border
Primary:  background --clay-soft,  color --clay-dark,  border 1px --clay-border
```

### Charts

- Clay (`--clay`) for primary series, olive (`--olive`) for secondary, amber (`--amber`) for tertiary.
- Warm grid lines (`--line-faint`), not cool gray-blue.
- Keep legends compact, placed above or to the right.
- Tooltip: `--paper` background, `--shadow-md`, `--radius-md`, `--text-sm`.
- Prefer SVG or CSS for simple charts when no charting library is present.

### Modal / Dialog

```
Overlay: background rgba(23,23,22,0.40), z-index --z-modal
Panel:   background --paper, radius --radius-lg, shadow --shadow-lg
         max-width 560px (default), padding --space-6
         enter: opacity 0→1 + translateY(8px→0),
                duration --duration-slow, ease --ease-out
Header:  font --font-serif --text-xl, border-bottom 1px --line, padding-bottom --space-4
Footer:  border-top 1px --line, padding-top --space-4,
         flex row gap --space-2, justify-end
```

### Drawer / Side Panel

```
background --paper, border-left 1.5px --line, width 360px (default)
shadow --shadow-lg, z-index --z-drawer
enter: translateX(100%→0), duration --duration-slow, ease --ease-out
```

### Toast / Notification

```
background --paper, border 1px --line, radius --radius-md, shadow --shadow-md
padding --space-3 --space-4, max-width 360px
z-index --z-toast, position fixed bottom-right (24px margin)
icon + text row, dismiss × button
Variants: left border 3px in --olive (success), --amber (warning),
          --red (error), --blue (info)
enter: translateY(8px→0) + opacity, duration --duration-base
```

### Empty State

```
Centered column, padding --space-12 --space-8
Icon:    SVG 40px, color --faint
Heading: --font-serif --text-lg, color --ink, margin-top --space-4
Body:    --text-sm, color --muted, max-width 320px, text-align center
CTA:     secondary button, margin-top --space-5
```

### Loading / Skeleton

```
Skeleton bar:
  background: linear-gradient(90deg,
    var(--line-faint) 25%, var(--paper-warm) 50%, var(--line-faint) 75%)
  background-size: 200% 100%
  animation: shimmer 1.4s ease-in-out infinite
  radius: --radius-sm

Spinner:
  SVG circle with stroke-dasharray, stroke --clay, 20px default size
```

### Breadcrumb

```
font --text-sm, color --muted
separator: › or / in --faint
current page: color --ink, font-weight 500
link hover: color --clay
```

### Pagination

```
Buttons: 32px square, radius --radius-sm, border 1px --line, background --paper
         hover:   background --paper-warm
         current: background --clay-soft, border-color --clay-border,
                  color --clay-dark, font-weight 600
gap: --space-1
```

### Presentation / PPT Components

Use these when creating HTML decks, slide screenshots, or translating the visual system into real PPTX layouts.

```
Slide canvas: 16:9, background --paper, border 1px --line,
              radius 10-14px for HTML preview, no radius for exported PPT
Slide padding: 48-64px desktop, 28-32px compact preview
Title:        --font-serif, 40-56px, line-height 1.04-1.12
Eyebrow:      --font-mono, 11-12px, uppercase, color --clay-dark
Footer:       page number + source/date, --text-xs, color --faint,
              top border 1px --line-faint
```

Core slide components:

- **Title / section slide:** centered claim, short supporting sentence, 2-4 metadata pills.
- **Two-column slide:** left conclusion, right evidence or paired argument blocks.
- **Metric slide:** 2-4 KPI cards plus one SVG/CSS chart; clay for primary series, olive for secondary.
- **Logic relationship map:** 3-stage input/process/output or cause/mechanism/result layout, with restrained arrows and grouped nodes.
- **Trend chart slide:** one large SVG/CSS chart plus compact side stats for anomalies, contributors, or next actions.
- **Report summary slide:** KPI strip, key insights, and risks/actions; do not paste raw backend dashboards into a slide.
- **Data table slide:** 4-6 columns maximum, status chips for health/risk, and only rows that support the claim.
- **Mixed image-text slide:** image/product state/process diagram on one side, 2-3 evidence points on the other; stack cleanly on narrow screens.
- **Code display slide:** dark code panel with monospace text, short side callouts, and 12-18 lines of code maximum.
- **Quote slide:** one large serif quote, quiet attribution, no decorative quotation overload.
- **Timeline / roadmap:** 3-5 milestones on one axis; each milestone gets a short label and one sentence.
- **Presenter notes:** outside the 16:9 canvas in HTML; never visible inside the slide unless requested.
- **Transition effects:** directional slide enter for next/previous, subtle staged entrances for metrics, charts, tables, logic nodes, and code panels; respect `prefers-reduced-motion`.

When building a real PPTX, keep a consistent master: title area, body grid, footer baseline, page number, and reusable color tokens. Avoid shrinking dense dashboard cards onto slides.

### Mobile App Components

Use these when designing phone-first app screens or mobile HTML prototypes.

```
Phone preview: 390px wide reference frame, safe-area top/bottom padding
Top app bar:   52-56px, title --font-serif 20-24px, icon buttons 34-40px
Bottom tabs:   64-76px, 3-5 items, selected background --clay-soft
Touch target:  minimum 40px height, 44px preferred for primary actions
Cards:         radius 14-18px in app surfaces, border 1px --line
Bottom sheet:  radius 20-24px top corners, shadow --shadow-lg,
               handle 44x4px in --line
```

Core mobile components:

- **Phone shell:** only for demos and screenshots; the actual app surface should still be usable without it.
- **App bar:** one title, one primary action, one optional navigation icon.
- **Bottom navigation:** use for top-level app areas; keep labels short and icons simple.
- **Segmented control:** use for local mode switching inside one screen.
- **Mobile list card:** icon/status mark + title + one-line detail; avoid desktop table compression.
- **Profile card:** avatar, status line, and one compact progress or membership indicator.
- **Form controls:** input, textarea, select, switch, stepper, slider, and validation states sized for touch.
- **Bottom sheet:** use for filters, quick create, confirmation, and secondary actions.
- **Modal:** reserve for destructive or high-importance confirmation.
- **Toast:** short confirmation near the bottom, above the tab bar.
- **State blocks:** skeleton loading, progress, empty state, success/warning list rows.

Mobile layouts should be designed natively for the narrow viewport. Do not simply stack every desktop panel or nest cards inside larger cards.

---

## Pattern Recipes

**Admin dashboard:**
Side nav (`--sidebar-width`) + topbar (`--topbar-height`) + scrollable main area. KPI row (4-column grid, gap `--space-4`). Chart panel + sortable table below. Detail drawer on row click. Filters above the table, search in topbar. Keep data dense and scannable while preserving paper warmth.

**Report / Analysis:**
Editorial serif title, summary strip (key metrics inline), tabbed sections (Overview / Detail / Raw), evidence table with export/copy action, timeline or chart in the Overview tab.

**Prototype:**
Main interactive surface fills the viewport. Supporting notes and controls sit adjacent in a sidebar or bottom tray. Use paper framing only where it aids comprehension — not as decoration around everything.

**Landing page:**
First viewport: product signal + clear CTA. Serif heading at `--text-2xl` or `--text-3xl`. Avoid generic AI-gradient hero layouts. Use editorial warmth and confident hierarchy.

**Presentation / PPT:**
One slide = one claim. Use title, two-column, metric/chart, logic map, trend chart, report summary, data table, mixed image-text, code display, quote, timeline, and closing layouts rather than one giant mixed slide. Keep presenter notes and thumbnails outside the slide canvas in HTML demos. Use restrained transition effects to clarify movement between slides, not to decorate. The slide canvas must be constrained by both available width and height so the deck never clips content in normal browser chrome.

**Mobile app:**
Start from the phone workflow: top app bar, primary content, bottom navigation or bottom sheet. Replace dense tables with list cards and detail sheets. Validate at 390px and at a narrower 360px width.

---

## Anti-Patterns

- Dark console style for ordinary Claude paper requests.
- Purple-blue gradients as the main identity color.
- Beige-only palette with no clay/olive contrast.
- Oversized decorative hero text inside dashboards or admin tools.
- Decorative explanation text such as "click the tabs to switch views" when the UI is obvious.
- Static mockups when the task calls for a working tool, dashboard, or prototype.
- Cards nested inside cards.
- Ornamental blobs, bokeh, or mesh gradients used only as decoration.
- Shadows heavier than `--shadow-md` on flat document surfaces.
