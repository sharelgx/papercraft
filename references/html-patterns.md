# HTML Artifact Patterns

Use this file when deciding what structure to give an interactive HTML artifact.
Select **one dominant pattern** — do not mix all patterns into a single page.

This reference integrates guidance from the [`html-skill`](https://github.com/sharelgx/html-skill) project.
Default every pattern to the Claude paper visual system (warm ivory background, clay/olive accents, serif headings, fine borders) unless the user asks otherwise.

---

## When to Use HTML Instead of Markdown

Choose a **single-file HTML artifact** when at least one of the following is true:

- The user needs to **compare** options, designs, files, risks, timelines, or records side-by-side.
- The user needs to **explore** information via filtering, sorting, toggling, expanding, or searching.
- The deliverable includes **charts, diagrams, mockups, workflows, boards, or status views**.
- The answer will be **handed to someone else** and should be browsable rather than read as a long note.
- The user explicitly asks for **interactive HTML, visual report, prototype, dashboard, or kanban**.
- The content would produce a Markdown document **longer than ~80 lines** that is hard to scan.

**Stay with Markdown** when the answer is short, mostly prose, or the user wants a normal document.

---

## Pattern 1 — Comparison Explorer

**Use for:** technical approaches, vendors, product options, design alternatives, papers, risk trade-offs.

Structure: side-by-side columns, trade-off tags, risk levels, recommendation lane at the bottom.

Useful controls: filter by priority/tag, toggle detail level, compare selected items, copy recommendation as Markdown.

Example from this skill: `examples/report.html` (Channels tab — side-by-side channel comparison with share bars).

---

## Pattern 2 — Status Report / Analysis Report

**Use for:** weekly reports, project health, incident follow-ups, Q1/Q2 growth summaries, operational reviews.

Structure: editorial serif title, summary KPI strip, tabbed sections (Overview / Detail / Raw), evidence table, timeline of key events, copy/export actions.

Useful controls: tab switching, search/filter within tables, copy as Markdown, export as JSON/CSV, date range picker.

Example from this skill: `examples/report.html` — full bilingual report with summary strip, insight cards, SVG trend chart, channel table, timeline, raw JSON.

---

## Pattern 3 — Admin Dashboard

**Use for:** internal tools, operational consoles, order management, analytics overview, SaaS admin panels.

Structure: fixed side nav + topbar + scrollable main area. KPI row, chart, dense sortable table, detail drawer on row click.

Useful controls: search, status filter tabs, sortable columns, drawer for row detail, CSV export, pagination, toast feedback.

Example from this skill: `examples/dashboard.html` — full admin dashboard with all of the above.

---

## Pattern 4 — Triage Board / Kanban

**Use for:** issue sorting, backlog grooming, sprint planning, editorial planning, task management.

Structure: columns (Backlog / Todo / In Progress / Done), cards with labels/assignee/due date, filters, search.

Useful controls: move cards between columns (modal or click), filter by label, search card titles, add new card inline, drag simulation.

Example from this skill: `examples/kanban.html` — project board with 16 cards, label filters, move modal, add-card form.

---

## Pattern 5 — Landing / Marketing Page

**Use for:** product pages, feature announcements, onboarding explainers, pitch pages.

Structure: sticky nav, editorial hero (serif headline + sub + CTAs + HTML mockup), feature grid, how-it-works steps, testimonials, pricing tiers, CTA banner, footer.

Useful controls: smooth scroll, hover states, pricing tier toggle (monthly/annual), CTA buttons that trigger toasts or link out.

Example from this skill: `examples/landing.html` — PaperMind landing page with all sections.

---

## Pattern 6 — Design System Sheet

**Use for:** token documentation, component states, UI inventory, visual QA, style guides.

Structure: full-page scrollable guide. Sections for colors, typography, spacing, every component variant and state.

Useful controls: language toggle, copy tokens button, collapsible "variables used" per section, live interactive component demos (modal, drawer, toast triggers).

Example from this skill: `examples/components.html` — complete Claude Paper design system with 11 sections.

---

## Pattern 7 — Flow Explainer / Diagram

**Use for:** architecture, API paths, pipelines, algorithms, process education, onboarding flows.

Structure: diagram area (SVG or CSS-positioned elements) + step list + callouts + examples.

Useful controls: stepper (click through steps), highlight active path, show/hide code snippets, FAQ accordion.

---

## Pattern 8 — Code Review Board

**Use for:** PR reviews, refactor plans, migration diffs, implementation audits.

Structure: findings summary with severity badges, file list with expand/collapse, snippets, owner, status, next action.

Useful controls: severity filter, file filter, expand/collapse details, copy review summary as Markdown.

---

## Pattern 9 — Implementation Plan

**Use for:** development handoff docs, task breakdowns, roadmap slices, sprint planning packets.

Structure: milestones, data flow, file list, risk table, test plan. Phase tabs for multi-stage work.

Useful controls: priority filter, phase tabs, dependency view, copy task list as Markdown/CSV.

---

## Pattern 10 — Prototype Sandbox

**Use for:** microinteractions, layout explorations, small app concepts, configurator UIs.

Structure: the prototype surface IS the main content. Supporting notes stay secondary (sidebar or panel).

Useful controls: mode switcher (segmented buttons), sliders/toggles for variants, reset, state switcher, live preview pane.

---

## Pattern 11 — Prompt Tuner / Config Editor

**Use for:** prompt templates, rubric tuning, instruction editing, feature flag inspection, JSON config editing.

Structure: editable source on one side, live preview / diff on the other.

Useful controls: editable text area, variable chips, sample selector, diff preview, copy final output, reset.

---

## Pattern 12 — Presentation / PPT Deck

**Use for:** product strategy decks, lesson slides, investor/storytelling decks, project reviews, feature launch briefings.

Structure: 16:9 slide canvas, thumbnail rail, active slide stage, presenter notes, page number/progress, directional slide transitions, optional fullscreen mode.

Useful controls: previous/next buttons, keyboard navigation, language toggle, fullscreen/presenter mode, copy/export slide outline.

Core components: title slide, section divider, two-column argument slide, metric/chart slide, logic relationship map, trend chart slide, report summary slide, data table slide, mixed image-text slide, code display slide, quote slide, timeline/roadmap slide, closing slide.

Example from this skill: `examples/presentation.html` — bilingual adaptive deck viewer with animated transitions, thumbnails, speaker notes, keyboard navigation, fullscreen mode, logic maps, charts, reports, tables, mixed-media slides, code slides, and reusable slide components.

---

## Pattern 13 — Mobile App Prototype

**Use for:** phone-first app screens, app onboarding, mobile admin tasks, content apps, mobile workflow demos.

Structure: optional phone shell for demo framing, native app surface, status bar, top app bar, primary content screen, bottom tabs, modal/bottom sheet.

Useful controls: bottom navigation, segmented controls, search, list filtering, bottom sheet actions, toast feedback.

Core components: app bar, bottom tab bar, mobile hero card, metric pair, list card, profile card, segmented control, search field, chips, inputs, textarea, select, switch, stepper, slider, bottom sheet, modal, toast, skeleton, progress, empty state.

Example from this skill: `examples/mobile.html` — bilingual mobile component kit with phone shell, tabs, forms, selectors, bottom sheets, modal, toast, loading states, and empty states.

---

## Implementation Checklist

Before delivering any HTML artifact:

- [ ] First screen is immediately useful — the object of work, not a marketing hero
- [ ] All controls do something meaningful (no decorative buttons)
- [ ] Claude paper palette: warm ivory bg, clay/olive accents, serif headings, fine borders
- [ ] Language toggle wired up if bilingual output is needed
- [ ] Validates at desktop width; checks narrow/mobile where relevant
- [ ] Export/copy actions produce clean Markdown, JSON, or CSV
- [ ] No external dependencies unless the repo already provides them
- [ ] Self-contained: all CSS and JS inline in one `.html` file
