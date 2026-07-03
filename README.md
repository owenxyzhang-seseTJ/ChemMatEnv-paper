# ChemMatEnv-paper: Top Journal Review Cycle

面向材料/化学论文的顶刊故事设计、期刊适配起草、循环审稿与当场修订 skill。它不是普通英文润色器，而是把“故事包锁定、目标期刊要求实时检索、同主题顶刊表达检索、去 AI 味、逻辑修复、编辑审稿循环”做成强制流程，适合从研究材料到英文初稿，也适合投稿前压力测试、返修前重构、Abstract/Introduction 深度修改和整篇 manuscript 审校。

## 一句话用途

给材料、图表或论文草稿，先锁定核心故事，再实时检索目标期刊要求和同主题顶刊表达，按故事包起草英文文本，然后模拟一轮期刊处理编辑和三轮审稿人，每轮审稿后立即修改正文，并在每次写作后强制检查：

- 起草是否符合期刊：实时搜索目标期刊官方 author guidelines、article type、格式限制和模板。
- 表达是否奇怪：实时搜索同主题目标期刊或相邻顶刊，校准英文搭配、动词、hedge 和语篇动作。
- 是否有 AI 味：删除模板腔、泛泛赞美、机械转场和空泛 impact 句。
- 逻辑是否成立：检查句子与句子、段落与段落之间是否有可解释的因果、证据、对比、限定或递进关系。

## 跨平台兼容

本 skill 遵循 **Agent Skills 开放标准**（SKILL.md YAML frontmatter + markdown body），可在以下平台直接使用：

| 平台 | 发现方式 | 插件清单目录 |
|---|---|---|
| **ZCode** | `.zcode-plugin/plugin.json` (优先级 1) | ✅ 已包含 |
| **Claude Code** | `.claude-plugin/plugin.json` 或 `~/.claude/skills/` | ✅ 已包含 |
| **Codex CLI** | `.codex-plugin/plugin.json` 或 `~/.agents/skills/` | ✅ 已包含 |
| **OpenCode** | `.agents/skills/` 或 `~/.opencode/skills/` | ✅ 兼容 |
| **Hermes** | `~/.hermes/skills/` 或 `.agents/skills/` | ✅ 兼容 |
| **Gemini CLI** | 激活 `activate_skill` 工具 | ✅ SKILL.md 格式原生支持 |
| **Cursor / Windsurf / Cline / Copilot** | `.agents/skills/` 共享目录 | ✅ 兼容 |

## 安装

### 方式 1：从 GitHub 克隆（推荐）

```bash
git clone https://github.com/owenxyzhang-seseTJ/ChemMatEnv-paper.git ~/ChemMatEnv-paper
```

**ZCode**：插件市场 → 添加本地插件 → 选择 `~/ChemMatEnv-paper`

**Claude Code / Codex CLI / OpenCode**：将 skill 目录链接到共享技能目录：

```bash
mkdir -p ~/.agents/skills
ln -s ~/ChemMatEnv-paper/skills/top-journal-review-cycle ~/.agents/skills/top-journal-review-cycle
```

**Hermes**：

```bash
mkdir -p ~/.hermes/skills
ln -s ~/ChemMatEnv-paper/skills/top-journal-review-cycle ~/.hermes/skills/top-journal-review-cycle
```

### 方式 2：直接复制 skills 目录

```bash
git clone https://github.com/owenxyzhang-seseTJ/ChemMatEnv-paper.git
cp -r ChemMatEnv-paper/skills/top-journal-review-cycle ~/.agents/skills/
```

### 方式 3：作为 ZCode / Claude Code / Codex 插件安装

整个仓库根目录即为完整插件包。将本地路径或 GitHub URL 添加到对应平台的插件管理器中即可。`skills/`、`agents/`（ZCode 专用）会被自动发现。

## 上传哪个文件夹

上传整个仓库根目录：

```text
.zcode-plugin/plugin.json
.claude-plugin/plugin.json
.codex-plugin/plugin.json
skills/top-journal-review-cycle/
agents/
README.md
LICENSE
```

把本仓库 clone 到本地后，在 ZCode 里将该目录作为本地插件添加即可。`skills/`、`agents/` 目录会被自动发现，无需在 `plugin.json` 里逐个声明。

## 适用范围

推荐用于：

- 多孔材料、材料化学、能源材料、环境化学、催化、吸附/分离、膜材料论文。
- 从数据、图表、figure legends 或初稿中设计论文故事。
- 按 locked story package 起草 Title、Abstract、Introduction、Results and Discussion skeleton、Conclusion。
- Abstract、Introduction、Results and Discussion、Conclusion、cover letter 修改。
- 投稿前自查、返修前压力测试、审稿意见预演、英文表达和逻辑重建。
- Nature family、Science family、JACS、Angewandte Chemie、Advanced Materials、Energy & Environmental Science、Environmental Science & Technology 等目标期刊风格校准。

不建议用于：

- 没有任何数据、图表或研究摘要的空白写作。
- 需要编造实验、补不存在文献或强行拔高结论的任务。
- 泛泛英语润色而不关心证据、claim 强度和投稿逻辑的任务。

## 准备输入材料

效果最好时，建议提供：

- 目标期刊或期刊层级，例如 `Nature Communications`, `JACS`, `Angewandte`, `Advanced Materials`。
- 论文题目、摘要、Introduction 或完整 manuscript。
- 图表说明、figure legends、主要数据表或结果摘要。
- 已有 story package，如果没有，skill 会先帮助锁定。
- 你最担心的问题，例如“AI 味重”“逻辑跳”“claim 太大”“像中文直译”“审稿人会抓机制证据”。

最小输入也可以很简单：

```text
Use $top-journal-review-cycle to revise this abstract for a JACS submission. Check odd expressions with live top-journal literature search, remove AI-like prose, and repair sentence logic.

[paste abstract]
```

## 核心工作流

### 1. 设计并锁定 story package

正式起草或大修前，skill 会先锁定 8 个字段：

- `core_problem`
- `specific_bottleneck`
- `design_principle`
- `main_claims`
- `evidence_map`
- `mechanism_position`
- `scope_limits`
- `target_journal_profile`

这样可以避免边写边改变核心故事，导致论文看起来流畅但逻辑失控。

### 2. 实时检索目标期刊要求

只要用户指定目标期刊，起草前必须实时搜索官方来源：

- author guidelines
- article type
- title limit
- abstract format and word limit
- main text limit
- display item limit
- reference or citation style
- graphical abstract、TOC graphic、SI、reporting summary 等要求
- Word/LaTeX/template 链接

不能凭记忆写期刊限制；找不到的字段必须标注 `not found in checked sources`。

### 3. 实时检索同主题顶刊表达和搭配

起草前必须搜索同主题目标期刊或相邻顶刊论文，提取：

- 常见搭配
- 证据动词
- hedge 强度
- gap 句写法
- results 小节开头方式
- mechanism 和 implication 的表达边界

这些内容进入 `pre_draft_literature_expression_audit`，然后才能起草正文。

### 4. 按故事包和期刊要求起草正文

起草必须同时满足：

- 不改变 locked story package。
- 不创造 evidence map 没有的新贡献。
- 符合目标期刊官方要求。
- 使用同主题顶刊表达和搭配作为语言证据。
- 每段有明确功能：`context`, `gap`, `move`, `evidence`, `mechanism`, `scope`, `implication`。

### 5. 每次写作后运行质量闸门

闸门分两档，按改动规模匹配，避免每次小修都重跑一遍实时文献检索：

**完整闸门（Full gate）** —— 新起草、结构性大改、审稿前最终轮后使用，包含三项：

| 闸门 | 检查什么 | 修什么 |
| --- | --- | --- |
| 顶刊表达检索 | 表达、搭配、动词、hedge、转折方式是否像真实顶刊论文 | 用检索到的表达模式改写，不复制长句 |
| 去 AI 味 | 泛泛赞美、模板转场、机械段落、空泛 impact | 删除或换成数据、机制、比较和限定 |
| 逻辑链检查 | 句间和段间是否有清楚关系 | 在 `unsupported_jump` / `unsupported_shift` 处补桥、重排、删句或降级 claim |

**轻量闸门（Light gate）** —— 小修措辞、收紧 hedge、调整段落形状（不引入新 claim）时使用，只跑后两项（去 AI 味 + 逻辑链），复用本 session 已有的表达检索结果，不再重复实时搜索。

同一稿件同一主题的表达检索结果在 session 内可复用；只有当章节类型或核心概念真正变化时才需要重新搜索。

### 6. 模拟 handling editor

先模拟一轮期刊处理编辑，判断：

- 是否有 desk reject 风险。
- 是否符合目标期刊 scope。
- novelty 和 general significance 是否够。
- 是否存在致命证据缺口。
- 是否值得送外审。

### 7. 三轮审稿，每轮三位 reviewer

每轮包含：

- Reviewer A, Methods and Evidence：方法、证据链、对照、baseline、claim ladder。
- Reviewer B, Field and Novelty：新颖性、文献定位、期刊匹配、贡献尺度。
- Reviewer C, Logic and Style：句间逻辑、段间逻辑、AI 味、表达自然度。

每轮结束后，所有意见进入 `review_action_matrix`，然后立即修改正文。不能只列意见不改稿。

### 8. 最终输出

最终会输出：

- 修订后的 manuscript 或 section。
- locked story package。
- 目标期刊要求检索结果。
- 起草前同主题顶刊表达检索结果。
- handling editor verdict。
- 三轮 reviewer 历史。
- `review_action_matrix`。
- `quality_gate_report`。
- 未解决风险清单。

如果某个问题必须靠新实验或新数据解决，skill 会直接标注，不会用语言包装假装解决。

## 常用 Prompt

### 从材料设计故事并起草

```text
Use $top-journal-review-cycle to build a story package and draft a manuscript for [target journal]. Before drafting, search the official journal requirements and search same-topic top-journal papers for expressions and collocations. Then draft the Title, Abstract, Introduction, Results and Discussion skeleton, and Conclusion from the locked story package.

Target journal: [journal name]
Evidence summary / figures / legends: [paste materials]
```

### 完整审稿循环

```text
Use $top-journal-review-cycle to run one handling-editor pass and three rounds of three simulated reviewers on my materials chemistry manuscript. Before any new drafting, search official target-journal requirements and same-topic top-journal expressions/collocations. After each writing pass, remove AI-like prose and repair sentence/paragraph logic before continuing.

Target journal: [journal name]
Manuscript: [paste text or attach file]
Figures/evidence summary: [paste summary]
```

### 只改 Abstract

```text
Use $top-journal-review-cycle to revise this abstract for [target journal]. Focus on top-journal phrasing, anti-AI style, claim strength, and sentence-to-sentence logic. Search recent papers from the target journal or adjacent journals before revising awkward expressions.

[paste abstract]
```

### 只改 Introduction

```text
Use $top-journal-review-cycle to rebuild this Introduction. First identify the core problem, bottleneck, design principle, and evidence limits. Then revise the prose, remove AI-like transitions, and make every paragraph-to-paragraph link explicit.

Target journal: [journal name]
Introduction: [paste text]
Evidence summary: [paste evidence]
```

### 投稿前压力测试

```text
Use $top-journal-review-cycle to pressure-test this manuscript before submission. Simulate a handling editor and three rounds of reviewers. For every criticism, decide whether it can be solved by writing, requires claim downgrading, or needs new data.
```

### 返修前预演

```text
Use $top-journal-review-cycle to simulate reviewer pushback before I write the response letter. Build a review action matrix, revise the manuscript text where possible, and list issues that require additional data.

Reviewer concerns: [paste comments]
Manuscript section: [paste text]
```

## 如何读输出

常见输出字段含义：

| 字段 | 含义 |
| --- | --- |
| `literature_expression_audit` | 哪些表达被检索、参考了什么顶刊表达模式、最终怎么改 |
| `pre_draft_literature_expression_audit` | 起草前同主题顶刊表达、搭配和语篇动作检索结果 |
| `target_journal_requirements` | 目标期刊官方要求、限制和模板来源 |
| `anti_ai_audit` | 哪些 AI 味或模板腔被删除或重写 |
| `logic_link_map` | 句间和段间关系是否成立，哪里补了逻辑桥 |
| `review_action_matrix` | 编辑和审稿人意见如何逐条转化为修订动作 |
| `claim_safety` | 哪些 claim 被降级、收窄或保留 |
| `final_risk_register` | 仅靠写作无法解决、需要数据或实验支撑的问题 |

## 使用建议

- 目标期刊越明确，表达检索和尺度判断越准。
- 给出 figure legends 或 evidence summary，会显著降低过度宣称风险。
- 起草任务必须允许实时搜索；否则只能先做故事包和证据整理，不能产出目标期刊适配的 polished prose。
- 如果只想快速润色，请明确说“只做轻量修改”；否则默认会按严格顶刊审稿流程执行。
- 如果你不希望改动核心故事，请明确提供 locked story package。
- 如果 reviewer 指出需要新数据，优先补数据；不补数据时应降级 claim。

## 不做什么

- 不编造实验、数据或文献。
- 不把 correlation 写成 mechanism。
- 不用顺滑转场掩盖证据跳跃。
- 不在 story package 未锁定时直接写 polished prose。
- 不在未实时搜索期刊要求和同主题顶刊表达时进行目标期刊适配起草。
- 不复制顶刊论文长句，只学习搭配、语篇动作和 claim 强度。

## 目录结构

```text
.
├── .zcode-plugin/
│   └── plugin.json
├── .claude-plugin/
│   └── plugin.json
├── .codex-plugin/
│   └── plugin.json
├── agents/
│   ├── chief-editor.md
│   ├── handling-editor.md
│   ├── journal-requirements-researcher.md
│   ├── literature-expression-auditor.md
│   ├── manuscript-drafter.md
│   ├── reviewer-field-novelty.md
│   ├── reviewer-logic-style.md
│   ├── reviewer-methods-evidence.md
│   ├── revision-editor.md
│   └── story-architect.md
├── skills/
│   └── top-journal-review-cycle/
│       ├── SKILL.md
│       └── references/
│           ├── anti-ai-style-rules.md
│           ├── claim-evidence-ladder.md
│           ├── live-literature-expression-audit.md
│           ├── logic-link-audit.md
│           ├── manuscript-drafting-protocol.md
│           ├── multi-round-review-protocol.md
│           ├── review-action-matrix-schema.md
│           ├── story-architecture-protocol.md
│           ├── story-package-schema.md
│           └── target-journal-requirements.md
├── LICENSE
└── README.md
```

## 故障排查

### 平台要求上传文件夹

上传仓库根目录，确保 `.zcode-plugin/plugin.json` 一起上传。

### 校验提示 YAML frontmatter 错误

检查 `SKILL.md` 顶部 `---` 之间的 `description` 是否被英文双引号包住。包含冒号、中文标点或长句时建议加引号。

### 没有实时联网检索能力

可以做故事包、证据整理和非期刊适配的诊断；但不能做目标期刊适配起草。起草前必须启用实时检索，或由用户提供官方期刊要求和同主题顶刊参考材料。

### 输出只审稿不改稿

这是不完整执行。正确流程必须在每轮审稿后更新 `review_action_matrix` 并给出修订后的正文。
