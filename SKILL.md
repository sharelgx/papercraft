---
name: claude-paper-web-design
description: Design and implement web pages, dashboards, admin systems, interactive HTML artifacts, product prototypes, reports, and app screens using a Claude paper visual language inspired by thariqs/html-effectiveness. Use when the user asks for Claude style, Claude paper style, Anthropic-like visual design, warm paper UI, editorial web UI, calm dashboard/admin templates, interactive HTML with Claude aesthetics, or wants an existing page restyled into that look.
---

# Claude Paper Web Design

## Purpose

Create web interfaces that feel like the Claude/Anthropic paper-style UI family: warm, editorial, calm, readable, and still fully usable as a product surface. This skill is about visual language and interaction composition, not about copying any existing page source.

Use it for websites, internal tools, dashboards, admin systems, reports, prototypes, onboarding flows, feature explainers, and single-file HTML demos when the user wants a Claude-style result.

## Default Visual System

Start with this style unless the user asks for another direction:

- Background: warm ivory or paper, such as `#FAF9F5`, `#F7F4EC`, `#F3EEE4`.
- Panels: white or warm white with fine borders, usually `#FFFFFF` or `#FFFDF8`.
- Text: near-black slate, such as `#171716`, with muted warm gray secondary text.
- Accents: clay/rust/orange for primary emphasis; olive/sage for secondary status; blue only for links or technical focus.
- Typography: serif display headings, usually `ui-serif`, Georgia, or Times fallback; system sans for body, controls, and data-dense surfaces; monospace for paths, code, IDs, and exports.
- Shape: 8-10px radius for panels and controls; fine 1-1.5px borders; restrained shadows.
- Composition: editorial document clarity combined with real app controls. The interface should look designed, but it must still behave like a useful tool.

For detailed values and component rules, read [style-system.md](references/style-system.md).

## Workflow

1. Identify the product surface: landing page, admin console, dashboard, report, prototype, explainer, or editor.
2. Decide the first-screen job. Do not default to a marketing hero when the user asked for an app, tool, admin system, or report.
3. Use the Claude paper visual system as the skin, then adapt density to the task.
4. Build practical controls: tabs, filters, segmented buttons, toggles, menus, search, sortable tables, drawers, copy/export actions, sliders, or preview panes.
5. Make the layout responsive with stable dimensions for fixed-format UI elements.
6. Validate at desktop and mobile widths. Check that controls work and text does not overflow.

## Surface Guidance

- Admin/dashboard: keep it scan-friendly and efficient. Use warm paper styling, but preserve data density, tables, filters, side navigation, and clear states.
- Report/analysis: lead with the conclusion, then provide tabs, filters, timelines, evidence, and export/copy actions.
- Product prototype: make the product surface the main object. Use paper-style framing for supporting notes, not as a decorative shell around everything.
- Landing page: use editorial warmth and confident hierarchy. Avoid generic SaaS gradients, dark-blue dashboards, or fluffy AI copy.
- Teaching/explainer: use progressive disclosure, diagram-like layouts, examples, and short checks for understanding.

## Interaction Standards

The style must not flatten the product into a static poster. Add interactions when they help the user inspect, compare, edit, or export:

- Search and filters for lists, tables, boards, and reports.
- Tabs or segmented controls for modes and datasets.
- Expand/collapse for evidence, explanations, and raw records.
- Copy/export buttons for summaries, prompts, JSON, CSV, or Markdown.
- Detail panels or drawers for selected table/list items.
- Sliders/toggles for prototypes and configuration tools.

## Avoid

- Copying `thariqs/html-effectiveness` source, fictional content, or exact page layouts.
- Dark developer-console styling unless explicitly requested.
- Purple/blue gradient SaaS defaults.
- Oversized decorative cards that reduce information density.
- Nested cards inside cards.
- Ornamental blobs, bokeh, or gradients used only as decoration.
- In-app text explaining obvious UI behavior.
- Controls that do nothing meaningful.

## Implementation Rules

- For standalone demos, create a single `.html` file with inline CSS and JavaScript.
- For existing frontend projects, follow the repo stack and component conventions while applying this visual language.
- Use semantic HTML and accessible labels.
- Use stable grid tracks, min/max widths, and aspect ratios so controls and text do not shift the layout.
- Prefer SVG or CSS for simple charts and diagrams when no chart library is already present.
- Use real user data, filenames, statuses, dates, and labels when available.

## Validation

Before final delivery:

- Open the page locally or run the app.
- Check desktop and mobile widths.
- Exercise meaningful controls.
- Confirm no incoherent overlap or horizontal overflow.
- Confirm the palette still reads as Claude paper: warm paper, clay/rust, olive/sage, serif headings, fine borders.

## Delivery

Return the local file path or URL, state what was validated, and mention whether the output is standalone HTML or part of an existing app.
