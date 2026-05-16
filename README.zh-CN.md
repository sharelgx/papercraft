# PagerCraft

PagerCraft 是一个非官方的 Codex/Cursor Skill，用来设计 Claude paper 风格的网页、后台管理系统、数据看板、交互报告、看板、落地页、PPT 式演示稿、手机端 App 界面和单文件 HTML 原型。

它借鉴的是 Claude 风格交互 HTML 常见的视觉语言：暖纸色背景、serif 编辑感标题、clay/olive 强调色、细边框、克制留白和真实可用的交互控件。它不隶属于 Anthropic，也不复制 Anthropic 或第三方源码。

## 适合做什么

- Claude paper 风格网页和单文件 HTML
- 后台管理系统、内部工具、数据看板
- 交互式 HTML 报告、分析页、对比页
- Kanban / 任务分流板
- 产品落地页、功能解释页、产品原型
- PPT 式演示稿、汇报稿、课程讲义
- 手机端 App 界面、移动端组件原型
- 把已有页面改造成温暖、安静、有编辑感的纸面 UI
- 判断什么时候应该用 HTML 替代 Markdown，并选择合适结构

## 范例

`examples/` 里有 7 个可直接打开的单文件 HTML 范例，全部支持 **中文/英文切换**。

| 文件 | 说明 |
|---|---|
| `examples/dashboard.html` | 后台管理系统：侧边栏、KPI、图表、表格、详情抽屉、toast、CSV 导出 |
| `examples/report.html` | 分析报告：摘要指标、tab、SVG 趋势图、渠道表、时间线、JSON/Markdown 导出 |
| `examples/landing.html` | 产品落地页：hero、功能区、流程、评价、价格、footer |
| `examples/kanban.html` | Kanban 看板：4 列、卡片、标签/负责人/截止日期、移动弹窗、搜索和新增 |
| `examples/presentation.html` | PPT 式演示稿：自适应 16:9 舞台、过渡动画、缩略图、标题/双栏/数据/逻辑关系图/图表/报表/表格/图文混排/代码/引用/时间线组件、演讲备注、全屏 |
| `examples/mobile.html` | 手机端组件库：设备外壳、顶部栏、底部导航、chips、列表、资料卡、表单、开关、步进器、滑杆、底部面板、弹窗、toast、加载和空状态 |
| `examples/components.html` | 组件库展示：色彩、字体、间距、按钮、表单、表格、卡片、PPT/手机端组件和浮层 |

## 安装

Codex：

```bash
mkdir -p ~/.codex/skills
git clone https://github.com/sharelgx/papercraft.git ~/.codex/skills/pagercraft
```

Cursor 或其他本地 agent：把这个文件夹放到对应的 skills/rules 目录。最少需要提供 `SKILL.md`；如果要稳定复用视觉语言，请同时保留 `references/` 和 `examples/`。

## 使用示例

```text
使用 PagerCraft skill，做一个 Claude paper 风格的后台管理系统模板。
```

```text
把这个报告页改造成暖纸色、clay/olive 配色的交互 HTML。
```

```text
做一个 PagerCraft 风格的产品策略 PPT 页面。
```

```text
做一个手机端 App 界面原型，包含底部导航和底部操作面板。
```

## 默认设计语言

这个 Skill 会引导 agent 默认使用：

- `#FAF9F5`、`#F7F4EC`、`#F3EEE4` 这类暖纸色背景
- 白色或暖白色面板，细边框和克制阴影
- serif 编辑感标题 + 系统 sans 正文
- clay/rust 主强调色 + olive/sage 辅助强调色
- 完整 token 系统：色彩、字号、间距、响应式断点、交互态、z-index、动效
- 真实可用的交互控件，而不是静态装饰图
- PPT 与手机端专用组件：16:9 slide canvas、speaker notes、phone shell、bottom tabs、bottom sheet 等
- 范例内置中英切换

## 仓库结构

```text
.
├── SKILL.md
├── LICENSE
├── agents/
│   └── openai.yaml
├── examples/
│   ├── dashboard.html
│   ├── report.html
│   ├── landing.html
│   ├── kanban.html
│   ├── presentation.html
│   ├── mobile.html
│   └── components.html
└── references/
    ├── style-system.md
    └── html-patterns.md
```

`SKILL.md` 是主规则，包含触发场景、设计流程、i18n 模式、页面类型指导和验收标准。

`references/style-system.md` 是具体的配色、字体、布局、组件、PPT 和手机端规范。

`references/html-patterns.md` 说明什么时候该用 HTML 替代 Markdown，以及常用页面结构。

## 声明

这是一个非官方设计 Skill，只是借鉴某种视觉风格；它不隶属于 Anthropic 或 Claude。
