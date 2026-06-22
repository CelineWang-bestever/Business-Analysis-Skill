# Business Analysis Skill

> **工具无关的 AI 业务分析提示词** — 适用于 CodeBuddy、TRAE、Cursor、Windsurf、Cline、GitHub Copilot 等主流 AI 编码工具。

把一句 *"我们需要一个会员积分兑换功能"* 丢给你的 AI 编码助手，它会自动将其转化为一份结构化、可评审的需求分析报告 — 基于 Stephen Wang 的**《可视化需求分析》**方法论。

---

## What It Does

分析覆盖以下内容：

- **干系人地图** — 谁受影响、谁被遗漏了
- **统一术语表** — 开发、产品、业务方用同一套词汇
- **泳道图** — 跨角色流程，标注线上/线下操作
- **决策矩阵** — 每个状态×动作组合穷举（空白格 = 未来的 Bug）
- **边界值清单** — 所有阈值用 `>=`、`<=`、`[]`、`()` 表述，拒绝"大概""之后""左右"
- **异常处理** — 区分业务错误 vs 系统异常，各有应对方案
- **校验矩阵** — 字段级 UI 校验规则，开发可直接使用
- **质量检查清单** — 8 个维度 + 常见错误，编码前过一遍

输出：一份 **12 节结构化的需求分析报告**，可直接用于 PRD 撰写、Sprint 规划或技术设计。

---

## How It Works

### 六步工作流

| Step | 阶段 | 产出 |
|------|------|------|
| 1 | **需求理解** | 需求类型 + 干系人 + 术语表 |
| 2 | **场景分析** | 八大思维模式穷举隐藏场景 |
| 3 | **结构化** | 选用泳道图/判定矩阵/决策矩阵等工具 |
| 4 | **需求表达** | 精确的、可测试的语言 — 杜绝模糊词 |
| 5 | **质量检查** | 八维度审计 + 常见错误清单 |
| 6 | **弹性设计** | 变更类型 → 架构应对策略 |

### 八大思维模式（Step 2）

| 思维 | 核心问题 |
|------|----------|
| **闭环思维** | 从头到尾走完用户全流程了吗？ |
| **对称思维** | 每个正向操作的逆向是什么？（申请↔取消、购买↔退货） |
| **边界思维** | 所有阈值和范围都用数学符号表达了吗？ |
| **异常思维** | 什么会出问题 — 业务错误还是系统异常？ |
| **多样性思维** | 不同设备、角色、组合 — 有盲区吗？ |
| **生命周期思维** | 每个对象阶段有哪些字段、功能、外部依赖？ |
| **并发思维** | 两人同时点击会发生什么？ |
| **安全思维** | 权限、数据保护、防恶意操作 — 覆盖了吗？ |

### 触发关键词

对话中包含以下关键词即可激活分析：

`需求分析` · `PRD` · `功能设计` · `业务流程` · `需求评审` · `用户故事` · `验收标准` · `业务优化` · `产品方案` · `梳理需求` · `分析一下需求`

---

## Why It Matters in Team Collaboration

### 1. 在歧义扩散之前消灭它

绝大多数需求 Bug 源自 PM、设计师、开发者之间传来传去的一句模糊表述。这份提示词强制精确语言 — `>= 3 天` 而不是 "过几天" — 所有人对规格的理解完全一致。

### 2. 跨角色通用的视觉语言

泳道图和决策矩阵对所有角色都是可读的。业务方、QA、后端工程师可以指着同一个矩阵单元格说 *"这个漏了。"*

### 3. 一个人的盲区，系统来补

个人领域专家总有盲区。八大思维模式充当系统性"第二大脑" — 迫使团队考虑逆向操作、边界值、隐藏干系人（财务、合规、老板）这些通常上线后才浮现的问题。

### 4. 开发即测试

决策矩阵和边界值清单可直接作为验收测试用例。标了 `√` 的格子就是一个 Given-When-Then 场景。QA 不用再从长篇描述中反推测试用例。

### 5. PRD 就绪，零摩擦

输出遵循固定的 12 节模板。无需纠结文档结构 — AI 处理格式，团队审核内容。原本需要 2 天会议的分析，变成 10 分钟的 AI 对话。

---

## Installation — 选择你的工具

该项目是**工具无关**的。核心提示词在根目录 `SKILL.md`，各工具的专属配置在 `tool-configs/` 目录下。

### 快速选择指南

不确定看哪一节？对照下表直接跳转：

| 你用的是... | 安装说明 |
|------------|----------|
| **TRAE**（腾讯 AI IDE） | → [TRAE 安装](#trae) |
| **CodeBuddy** | → [CodeBuddy 安装](#codebuddy) |
| **Cursor** | → [Cursor 安装](#cursor) |
| **Windsurf** | → [Windsurf 安装](#windsurf) |
| **Cline**（VS Code 插件） | → [Cline 安装](#cline) |
| **GitHub Copilot** | → [Copilot 安装](#github-copilot) |
| **其他工具**（通义灵码、Aider 等） | → [通用安装](#其他-ai-编码工具) |

### 项目文件结构

```
├── SKILL.md                    # 核心提示词（工具无关）
├── README.md
├── references/                 # 人类阅读的进阶参考资料
│   ├── quality-checklist.md    #   完整质量检查清单（44项）
│   ├── thinking-modes.md       #   八大思维模式详解
│   └── tools-reference.md      #   44种分析工具速查表
└── tool-configs/               # 各 AI 工具的专属配置
    ├── codebuddy/SKILL.md
    ├── trae/business-analysis.md
    ├── cursor/business-analysis.mdc
    ├── windsurf/.windsurfrules
    ├── cline/.clinerules
    └── generic/system-prompt.md
```

> **说明**：`references/` 目录是给人类深入阅读的进阶资料，**无需复制到工具中**。核心分析逻辑已完整包含在 `SKILL.md` 及 `tool-configs/` 的配置文件中。

---

### CodeBuddy

**全局安装**（所有项目生效）：
```bash
cp tool-configs/codebuddy/SKILL.md ~/.codebuddy/skills/business-analysis/
```

**单项目安装**：
```bash
cp tool-configs/codebuddy/SKILL.md your-project/.codebuddy/skills/business-analysis/
```

重启 CodeBuddy，讨论需求时关键词自动激活。

---

### TRAE

**单项目安装**：
```bash
mkdir -p your-project/.trae/rules/
cp tool-configs/trae/business-analysis.md your-project/.trae/rules/
```

TRAE 会自动加载 `.trae/rules/` 下的 `.md` 文件。配置为 `alwaysApply: true`，每次对话均生效。

> 也可在 TRAE 设置中心 → 规则 → 创建项目规则 → 粘贴 `tool-configs/trae/business-analysis.md` 内容。

---

### Cursor

**单项目安装**：
```bash
mkdir -p your-project/.cursor/rules/
cp tool-configs/cursor/business-analysis.mdc your-project/.cursor/rules/
```

Cursor 会自动加载 `.cursor/rules/` 下的 `.mdc` 文件。配置为 `alwaysApply: true`，每次对话均生效。

---

### Windsurf

**单项目安装**：
```bash
cp tool-configs/windsurf/.windsurfrules your-project/
```

Windsurf 自动加载项目根目录的 `.windsurfrules` 文件。

---

### Cline

**单项目安装**：
```bash
cp tool-configs/cline/.clinerules your-project/
```

Cline 自动加载项目根目录的 `.clinerules` 文件。

---

### GitHub Copilot

**单项目安装**：
```bash
mkdir -p your-project/.github/
cp tool-configs/generic/system-prompt.md your-project/.github/copilot-instructions.md
```

Copilot 自动加载 `.github/copilot-instructions.md`。

> 也可以将 `SKILL.md` 的核心内容粘贴到 VS Code 设置中的 `github.copilot.chat.codeGeneration.instructions`。

---

### 其他 AI 编码工具

大多数 AI 编码工具都支持"自定义指令 / System Prompt / Rules"功能。通用做法：

1. 打开 `SKILL.md`（项目根目录）或 `tool-configs/generic/system-prompt.md`
2. 复制全部内容
3. 粘贴到该工具的 **自定义指令 / 系统提示词 / 规则** 配置中

支持此方式的工具包括但不限于：**通义灵码**、**文心快码**、**Aider**、**Continue.dev**、**Amazon Q Developer** 等。

---

## Credits

Based on **《可视化需求分析》** (Visual Requirements Analysis) by Stephen Wang. All 8 thinking modes, structural analysis tools, and quality standards originate from this methodology.
