# Claude Paper Style System

Use this reference when implementing or restyling a page in the Claude paper visual language.

## Palette

Core tokens:

```css
:root {
  --ivory: #FAF9F5;
  --paper: #FFFFFF;
  --paper-warm: #F7F4EC;
  --ink: #171716;
  --muted: #706F68;
  --line: #D8D1C3;
  --line-strong: #C8BBA8;
  --clay: #C86645;
  --clay-dark: #A84D32;
  --clay-soft: #FBEDE6;
  --olive: #74845B;
  --olive-dark: #56663E;
  --olive-soft: #EDF1E7;
  --amber-soft: #FBF1DF;
}
```

Use clay/rust for primary emphasis and selected states. Use olive/sage for healthy status, secondary accents, and completion. Use blue sparingly for links, charts, or technical focus.

## Typography

- Display headings: `ui-serif, Georgia, "Times New Roman", Times, serif`.
- Body and controls: system sans, including `-apple-system`, `BlinkMacSystemFont`, `Segoe UI`, `PingFang SC`, `Microsoft YaHei`.
- Code, IDs, paths: `ui-monospace`, `SF Mono`, Menlo, Consolas.
- Keep letter spacing at `0` for headings unless using small uppercase mono labels.
- Use serif for section rhythm, not for dense tables or form controls.

## Layout

- Use warm page backgrounds with white or warm-white panels.
- Prefer constrained content width for reports and explainers.
- For admin systems, use side navigation plus dense main content; do not force everything into large cards.
- Use fine borders as structure. Shadows should be subtle and secondary.
- Do not place cards inside cards. Panels can contain tables, controls, charts, or lists directly.

## Components

Buttons:

- Primary: near-black or clay fill.
- Secondary: paper background with fine border.
- Selected: clay-soft background with clay border and clay-dark text.

Inputs:

- Paper background, 1.5px warm border, 8px radius.
- Clear focus state using clay border or outline.

Tables:

- Header background can be warm white.
- Rows should support hover and selected states.
- Use badges for status, not long status text.

Charts:

- Clay for primary series, olive for secondary series.
- Use warm grid lines, not cool gray-blue.
- Keep legends compact.

## Pattern Recipes

Admin dashboard:

- Side nav, topbar, filters, KPI row, chart, table, detail panel.
- Keep data dense and scannable while preserving paper warmth.

Report:

- Editorial title, summary strip, evidence table, timeline, filters, copy/export action.

Prototype:

- Main interactive surface first, notes and controls adjacent.
- Use paper framing only where it helps comprehension.

Landing page:

- Use product or offer as first-viewport signal.
- Avoid generic AI-gradient hero layouts.

## Anti-Patterns

- Dark console style for ordinary Claude paper requests.
- Purple-blue gradients as the main identity.
- Beige-only palette with no clay/olive contrast.
- Overlarge hero text inside dashboards.
- Decorative explanation text such as "click the tabs to switch views" when the UI is obvious.
- Static mockups when the task calls for a tool, dashboard, or prototype.
