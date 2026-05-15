# Claude Paper 网页设计 Skill

这是一个非官方的 Codex/Cursor skill，用来设计 Claude paper 风格的网页、后台管理系统、数据看板、交互报告和产品原型。

它借鉴的是 Claude 风格交互 HTML 常见的视觉语言：暖纸色背景、serif 编辑感标题、clay/olive 强调色、细边框、克制留白和真实可用的交互控件。它不隶属于 Anthropic，也不复制 Anthropic 或第三方源码。

## 适合做什么

- Claude paper 风格网页
- 后台管理系统和内部工具
- 交互式 HTML 报告
- 产品原型
- 功能解释页
- 数据密度较高但仍希望温暖、编辑感强的页面
- 把已有页面改造成 Claude paper 风格

## 安装

Codex：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/sharelgx/claude-paper-web-design.git ~/.codex/skills/claude-paper-web-design
```

Cursor 或其他本地 agent：把这个文件夹放到对应的 skills/rules 目录。最少需要提供 `SKILL.md`；如果需要具体配色和组件规则，请同时保留 `references/style-system.md`。

## 使用示例

```text
使用 claude-paper-web-design skill，做一个 Claude paper 风格的后台管理系统模板。
```

```text
把这个报告页改造成暖纸色、clay/olive 配色的 Claude paper UI。
```

```text
做一个单文件 HTML 产品流程原型，使用 Claude paper 风格。
```

## 默认设计语言

这个 skill 会引导 agent 默认使用：

- `#FAF9F5`、`#F7F4EC` 这类暖纸色背景
- 白色或暖白色面板
- serif 编辑感标题 + 系统 sans 正文
- clay/rust/orange 主强调色
- olive/sage 辅助强调色
- 细边框和克制阴影
- 有真实用途的交互控件，而不是静态装饰图

## 仓库结构

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── style-system.md
```

`SKILL.md` 是主规则，包含触发场景、设计流程和验收标准。`references/style-system.md` 是具体的配色、字体、布局和组件参考。

## 相关 Skill

如果你想解决的是“什么时候该用交互 HTML 替代 Markdown”，请看 [`sharelgx/html-skill`](https://github.com/sharelgx/html-skill)。

## 声明

这是一个非官方设计 skill，只是借鉴某种视觉风格；它不隶属于 Anthropic 或 Claude。
