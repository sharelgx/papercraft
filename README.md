# PagerCraft

An unofficial Codex/Cursor skill for designing web pages, dashboards, admin systems, reports, kanban boards, landing pages, PPT-style presentations, mobile app screens, and interactive HTML artifacts in a Claude paper visual style.

Inspired by the warm editorial visual language seen in Claude-style interactive HTML artifacts: paper backgrounds, serif headings, clay and olive accents, fine borders, calm spacing, and practical controls. Integrates HTML artifact decision logic from [`sharelgx/html-skill`](https://github.com/sharelgx/html-skill). Not affiliated with Anthropic.

## What It Is For

- Claude paper-style web pages and single-file HTML artifacts
- Admin dashboards and internal tools
- Interactive HTML reports and analysis pages
- Kanban / triage boards
- Product landing pages
- Presentation / slide decks (HTML or PowerPoint-style)
- Feature explainers and prototypes
- Data-heavy pages that still need a warm editorial feel
- Restyling an existing page into a calm paper UI
- Deciding when to use HTML instead of Markdown, and selecting the right structural pattern

## Examples

The `examples/` folder contains seven runnable single-file HTML demos — all support **Chinese/English language switching**.

| File | Description |
|---|---|
| `examples/dashboard.html` | Admin dashboard — side nav, KPI row, bar chart, sortable/filterable table, detail drawer, toast notifications, CSV export |
| `examples/report.html` | Analysis report — summary KPI strip, tabbed sections (overview/channels/timeline/raw), SVG trend chart, export to JSON/Markdown |
| `examples/landing.html` | Product landing page — hero with HTML mockup, features, how-it-works, testimonials, pricing tiers, footer |
| `examples/kanban.html` | Kanban board — 4 columns, 16 cards with labels/assignee/due date, move modal, label filter, search, add card |
| `examples/presentation.html` | PPT-style deck viewer — adaptive 16:9 stage, thumbnails, title/two-column/data/mixed-media/code/quote/timeline components, keyboard navigation, presenter notes, fullscreen |
| `examples/mobile.html` | Mobile app prototype — phone shell, app bar, bottom tabs, segmented control, list cards, bottom sheet, toast |
| `examples/components.html` | Design system showcase — all 29 color tokens, typography scale, spacing scale, every component with all states, PPT/mobile component sections, live modal/drawer/toast demos |

Open any file directly in a browser to preview the visual system.

## Installation

For Codex:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/sharelgx/papercraft.git ~/.codex/skills/pagercraft
```

For Cursor or another local agent, add this folder to the agent's skills or rules directory. At minimum, provide `SKILL.md`; keep the `references/` and `examples/` folders available for concrete visual anchors.

## Usage

Example prompts:

```text
Use the PagerCraft skill to create a Claude paper-style admin dashboard.
```

```text
Turn this data into an interactive HTML analysis report with filters and export.
```

```text
Create a bilingual (Chinese/English) kanban board for my product roadmap.
```

```text
Restyle this page into a warm Claude paper UI with clay and olive accents.
```

```text
Make a single-file HTML prototype for this feature in Claude paper style.
```

```text
Create a PagerCraft presentation deck for this product strategy.
```

```text
Create a mobile app screen with PagerCraft components.
```

## Design Defaults

The skill guides the agent to use:

- Warm paper backgrounds: `#FAF9F5`, `#F7F4EC`, `#F3EEE4`
- White or warm-white panels with fine 1–1.5px borders
- Serif editorial headings (`ui-serif`, Georgia) + system sans body
- Clay/rust primary accents (`#C86645`) + olive/sage secondary (`#74845B`)
- Complete token system: spacing scale, font-size scale, state colors (hover/active/disabled/error), responsive breakpoints, z-index, transitions
- Real interactive controls — not decorative static mockups
- Bilingual (ZH/EN) language toggle built into every example

## Repository Contents

```text
.
├── SKILL.md                          ← Core skill: visual system + HTML decision rules + i18n pattern
├── LICENSE
├── agents/
│   └── openai.yaml
├── examples/
│   ├── dashboard.html                ← Admin dashboard (EN/ZH)
│   ├── report.html                   ← Analysis report (EN/ZH)
│   ├── landing.html                  ← Product landing page (EN/ZH)
│   ├── kanban.html                   ← Kanban board (EN/ZH)
│   ├── presentation.html             ← PPT-style deck viewer (EN/ZH)
│   ├── mobile.html                   ← Mobile app prototype (EN/ZH)
│   └── components.html               ← Design system showcase (EN/ZH)
└── references/
    ├── style-system.md               ← All design tokens + component specs
    └── html-patterns.md              ← HTML vs Markdown decision + 13 structural patterns
```

`SKILL.md` — master skill file: visual system defaults, HTML artifact decision rule, i18n toggle pattern, all surface guidance, and workflow steps.

`references/style-system.md` — complete palette (including dark mode, hover/active/disabled/error states), spacing scale, font-size scale, responsive breakpoints, shape & elevation, transition tokens, z-index scale, and component specs for every UI element.

`references/html-patterns.md` — when to use HTML over Markdown, and 13 structural patterns including reports, dashboards, kanban, comparison explorers, landing pages, design systems, implementation plans, prompt tuners, presentation decks, and mobile app prototypes.

`examples/` — seven runnable demos serving as visual anchors. Agents should read the closest match before generating output.

## Related Skill

HTML artifact decision logic is also available standalone at [`sharelgx/html-skill`](https://github.com/sharelgx/html-skill). PagerCraft integrates and extends those patterns with presentation and mobile components.

## License

MIT — see [LICENSE](LICENSE).

## Disclaimer

This is an unofficial design skill inspired by a visual style. It is not affiliated with Anthropic or Claude.
