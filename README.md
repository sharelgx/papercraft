# Claude Paper Web Design Skill

An unofficial Codex/Cursor skill for designing web pages, dashboards, admin systems, reports, and prototypes in a Claude paper visual style.

It is inspired by the warm editorial visual language often seen in Claude-style interactive HTML artifacts: paper backgrounds, serif headings, clay and olive accents, fine borders, calm spacing, and practical controls. It is not affiliated with Anthropic, and it does not copy any Anthropic or third-party source code.

## What It Is For

- Claude paper-style web pages
- Admin dashboards and internal tools
- Interactive HTML reports
- Product prototypes
- Feature explainers
- Data-heavy pages that still need a warm editorial feel
- Restyling an existing page into a calm paper UI

## Installation

For Codex:

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/sharelgx/claude-paper-web-design.git ~/.codex/skills/claude-paper-web-design
```

For Cursor or another local agent, add this folder to the agent's skills or rules directory. At minimum, provide `SKILL.md`; keep `references/style-system.md` available when the agent needs concrete palette and component rules.

## Usage

Example prompts:

```text
Use the claude-paper-web-design skill to create a Claude paper-style admin dashboard template.
```

```text
Restyle this report page into a warm Claude paper UI with clay and olive accents.
```

```text
Create a single-file HTML prototype for this product workflow in Claude paper style.
```

## Design Defaults

The skill guides the agent to use:

- Warm paper backgrounds such as `#FAF9F5` and `#F7F4EC`
- White or warm-white panels
- Serif editorial headings with system sans body text
- Clay/rust/orange primary accents
- Olive/sage secondary accents
- Fine borders and restrained shadows
- Real interactive controls, not decorative static mockups

## Repository Contents

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── style-system.md
```

`SKILL.md` contains the core workflow and trigger rules. `references/style-system.md` contains concrete palette, typography, layout, and component guidance.

## Related Skill

For deciding when to use interactive single-file HTML instead of Markdown, see [`sharelgx/html-skill`](https://github.com/sharelgx/html-skill).

## Disclaimer

This is an unofficial design skill inspired by a visual style. It is not affiliated with Anthropic or Claude.
