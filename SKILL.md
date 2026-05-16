---
name: pagercraft
description: Design and implement web pages, dashboards, admin systems, interactive HTML reports, product prototypes, kanban boards, landing pages, PPT-style presentations, mobile app screens, and interactive artifacts using a Claude paper visual language. Use when the user asks for PagerCraft, Claude style, Claude paper style, warm paper UI, editorial web UI, calm dashboard/admin templates, interactive HTML artifacts, visual reports, analysis pages, comparison explorers, triage boards, slide decks, mobile UI, app screens, or wants an existing page restyled into that look. Also activates when the user asks to turn a Markdown document, data table, or analysis into an interactive single-file HTML page, or wants to create a presentation/slideshow in Claude paper style.
---

# PagerCraft

## Purpose

Create web interfaces that feel like the Claude/Anthropic paper-style UI family: warm, editorial, calm, readable, and still fully usable as a product surface. This skill covers two related tasks:

1. **Visual design** — applying the Claude paper visual language to any web surface.
2. **HTML artifact creation** — deciding when to produce an interactive single-file HTML page instead of a Markdown document, and selecting the right structural pattern.

Use it for websites, internal tools, dashboards, admin systems, reports, prototypes, onboarding flows, feature explainers, kanban boards, landing pages, PPT-style decks, mobile app screens, and single-file HTML demos.

---

## Before You Start: Read the References

Before writing any code, read the relevant files:

1. **`references/style-system.md`** — Complete palette tokens, spacing scale, font-size scale, breakpoints, shape/elevation, transition tokens, z-index, and component specs for every UI element.

2. **`references/html-patterns.md`** — HTML vs Markdown decision rule and 13 structural patterns (reports, dashboards, kanban, comparison explorers, landing pages, design systems, flow explainers, review boards, implementation plans, prototype sandboxes, prompt tuners, presentation decks, mobile app prototypes). Read this when you need to select a structure.

3. **`examples/`** — Runnable HTML demos as visual anchors. Read the closest match before generating:
   - `examples/dashboard.html` — Admin dashboard: side nav, KPI row, bar chart, sortable/filterable table, drawer, toasts, CSV export. *(EN/ZH)*
   - `examples/report.html` — Analysis report: summary strip, tabs, SVG trend chart, channel table, timeline, JSON export. *(EN/ZH)*
   - `examples/landing.html` — Product landing page: hero, features, how-it-works, testimonials, pricing, footer. *(EN/ZH)*
   - `examples/kanban.html` — Kanban board: columns, cards with labels/assignee/due date, move modal, filters. *(EN/ZH)*
   - `examples/presentation.html` — PPT-style deck: adaptive 16:9 slides, animated transitions, thumbnails, logic maps, charts, report summaries, data tables, mixed-media and code slides, keyboard navigation, presenter notes, fullscreen. *(EN/ZH)*
   - `examples/mobile.html` — Mobile component kit: phone shell, app bar, bottom tabs, chips, lists, profile card, forms, switches, steppers, slider, bottom sheets, modal, toast, loading and empty states. *(EN/ZH)*
   - `examples/components.html` — Full design system showcase: all tokens, all component states, PPT/mobile components, live demos. *(EN/ZH)*

Do not generate from description alone when a matching example exists.

---

## HTML vs Markdown Decision Rule

**Choose interactive HTML** when at least one is true:
- The user needs to compare, filter, sort, toggle, or explore information.
- The deliverable includes charts, diagrams, boards, or status views.
- The answer will be browsed by others, not just read as a note.
- The content would produce a Markdown document longer than ~80 lines that is hard to scan.
- The user explicitly asks for interactive HTML, visual report, prototype, dashboard, or kanban.

**Stay with Markdown** when the answer is short, mostly prose, or the user wants a plain document.

When HTML is appropriate, read `references/html-patterns.md` and select the closest pattern before building.

---

## i18n (Bilingual Output)

When the user's content is Chinese, or when they ask for bilingual output, include a Chinese/English language toggle in every HTML artifact:

```js
const I18N = { zh: { key: '中文' }, en: { key: 'English' } };
let LANG = 'zh';
function t(key) { return (I18N[LANG] && I18N[LANG][key]) ? I18N[LANG][key] : key; }
function setLang(l) {
  LANG = l;
  document.querySelectorAll('[data-t]').forEach(el => {
    const v = I18N[LANG][el.dataset.t]; if (v) el.textContent = v;
  });
  document.querySelectorAll('[data-tp]').forEach(el => {
    const v = I18N[LANG][el.dataset.tp]; if (v) el.placeholder = v;
  });
  document.querySelectorAll('.lang-btn').forEach(b =>
    b.classList.toggle('active', b.dataset.lang === l));
  if (typeof rerenderAll === 'function') rerenderAll();
}
```

Toggle button HTML (place in topbar):
```html
<div class="lang-toggle">
  <button class="lang-btn active" data-lang="zh" onclick="setLang('zh')">中文</button>
  <button class="lang-btn" data-lang="en" onclick="setLang('en')">EN</button>
</div>
```

All examples in `examples/` demonstrate this pattern.

---

## Default Visual System

Start with this style unless the user asks for another direction:

- **Background:** warm ivory or paper — `#FAF9F5`, `#F7F4EC`, `#F3EEE4`.
- **Panels:** white or warm white with fine 1–1.5px borders.
- **Text:** near-black slate `#171716`; muted warm gray `#706F68` for secondary.
- **Accents:** clay/rust `#C86645` for primary; olive/sage `#74845B` for secondary status; blue `#2D6BB0` for links only.
- **Typography:** `ui-serif` / Georgia for headings; system sans for body and controls; monospace for code/IDs.
- **Shape:** 8–10px radius; restrained shadows; no glossy gradients.
- **Composition:** editorial document clarity + real interactive controls.

For all token values, see `references/style-system.md`.

---

## Workflow

1. Read `references/style-system.md`.
2. If building HTML: read `references/html-patterns.md`, pick a pattern, read the closest `examples/` file.
3. Identify the surface type and first-screen job.
4. Apply the Claude paper visual system. Adapt density to the task.
5. Build practical controls: tabs, filters, search, sortable tables, drawers, copy/export, sliders.
6. Add bilingual toggle if the user's content is Chinese or they ask for it.
7. Make the layout responsive. Validate at desktop and mobile widths.

---

## Surface Guidance

- **Admin / dashboard:** scan-friendly, data-dense. Side nav + topbar + table + drawer. Preserve filters and clear states.
- **Report / analysis:** lead with the conclusion. Summary strip → tabs → evidence table → export actions.
- **Kanban / triage board:** columns + cards. Meaningful move interaction. Label and search filters.
- **Landing page:** editorial warmth, confident hierarchy. No generic SaaS gradients.
- **Prototype:** the product surface is the main object. Paper framing is secondary.
- **PPT / presentation:** one claim per slide. Use an adaptive 16:9 canvas, slide thumbnails, presenter notes, clear page numbers, directional slide transitions, restrained component entrance animation, and keyboard navigation when building HTML decks. For actual PPTX work, translate the same components into title, section, two-column, metric/chart, logic relationship map, trend chart, report summary, data table, mixed image-text, code display, quote, timeline, and closing slides.
- **Mobile app:** design the actual app screen first. Use safe-area spacing, thumb-friendly controls, bottom tabs or bottom sheets when appropriate, and avoid shrinking desktop cards into a phone frame.
- **Teaching / explainer:** progressive disclosure, diagrams, step-by-step, examples.
- **Design system:** full token showcase + all component states + live demos.

---

## Interaction Standards

The style must not flatten the product into a static poster. Add interactions when they help the user inspect, compare, edit, or export:

- Search and filters for lists, tables, boards, and reports.
- Tabs or segmented controls for modes and datasets.
- Expand/collapse for evidence, explanations, and raw records.
- Copy/export buttons for summaries, prompts, JSON, CSV, or Markdown.
- Detail panels or drawers for selected items.
- Sliders/toggles for prototypes and configuration tools.
- Toast notifications for user actions.

---

## Implementation Rules

- Standalone: create a single `.html` file with all CSS and JS inline. No external dependencies.
- Existing projects: follow the repo stack; apply this visual language through the existing component system.
- Use semantic HTML and accessible labels (`aria-label`, `role`, `for`/`id` pairs).
- Apply transitions from the `--duration-*` and `--ease-*` tokens.
- Prefer SVG or CSS for charts when no library is already present.
- Use real user data, filenames, statuses, and labels when available.
- Preserve raw data — always include a way to inspect or export the source records.

---

## Avoid

- Dark developer-console styling unless explicitly requested.
- Purple/blue gradient SaaS defaults.
- Oversized decorative cards or hero sections inside dashboards or admin tools.
- Nested cards inside cards.
- Ornamental blobs, bokeh, or mesh gradients.
- Controls that do nothing meaningful.
- Explanation text that describes how to use obvious UI controls.
- Skipping the `examples/` reference when a matching surface type exists.

---

## Validation

Before final delivery:

- Open the page locally.
- Check desktop and mobile widths.
- Exercise all meaningful controls (filters, tabs, search, export, drawer, modal).
- Confirm no overflow or layout shift.
- Confirm the palette reads as Claude paper: warm paper, clay/rust, olive/sage, serif headings, fine borders.
- If bilingual: confirm both language modes render correctly.

---

## Delivery

Return the local file path or URL, state what was validated, and mention whether the output is standalone HTML or part of an existing app. If bilingual, confirm both languages work.
