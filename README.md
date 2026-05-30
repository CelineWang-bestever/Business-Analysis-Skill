# Business Analysis Skill

A CodeBuddy AI skill that turns your vague feature ideas into structured, reviewable requirement documents — powered by Stephen Wang's **Visual Requirements Analysis** methodology.

---

## What It Does

Drop a sentence like *"我们需要一个会员积分兑换功能"* into your AI coding assistant, and this skill transforms it into a complete analysis including:

- **Stakeholder map** — who's affected and who's missing from the conversation
- **Unified glossary** — so devs, PMs, and business teams use the same words
- **Swimlane diagrams** — cross-role process flow, marking online vs. offline steps
- **Decision matrices** — every state×action combination enumerated (blank cells = future bugs)
- **Boundary table** — every threshold expressed as `>=`, `<=`, `[]`, `()` — no "around," "roughly," "later"
- **Exception handling** — business errors vs. system failures, each with a response plan
- **Validation matrix** — field-level UI rules ready for implementation
- **Quality checklist** — 8 dimensions, 8 common pitfalls, graded before you start coding

The output: a **12-section report** your team can immediately use for PRD writing, sprint planning, or technical design.

---

## How It Works

### Trigger Keywords

Mention any of the following in your prompt and the skill activates automatically:

`需求分析` · `PRD` · `功能设计` · `业务流程` · `需求评审` · `用户故事` · `验收标准` · `业务优化` · `产品方案` · `梳理需求` · `分析一下需求`

### The 6-Step Workflow

| Step | Phase | Output |
|------|-------|--------|
| 1 | **Understand** | Demand type + stakeholders + glossary |
| 2 | **Analyze** | Apply 8 thinking modes to surface hidden scenarios |
| 3 | **Structure** | Pick the right tool (matrix, swimlane, timeline, etc.) |
| 4 | **Express** | Write in precise, testable language — no fuzzy words |
| 5 | **Quality-check** | 8-dimension audit + common pitfalls checklist |
| 6 | **Future-proof** | Map change types to architectural responses |

### The 8 Thinking Modes (Step 2)

| Mode | The Question It Asks |
|------|---------------------|
| **Closed-loop** | Did we walk the full user journey end-to-end? |
| **Symmetry** | What's the reverse of every action? (apply↔cancel, buy↔refund) |
| **Boundary** | Are every threshold and range expressed mathematically? |
| **Exception** | What breaks — and is it a business error or a system error? |
| **Diversity** | Different devices, roles, combos — any blind spots? |
| **Lifecycle** | What fields, functions, and external deps exist at each object stage? |
| **Concurrency** | What happens when two users click at the same time? |
| **Security** | Permissions, data protection, anti-abuse — covered? |

---

## Why It Matters in Team Collaboration

### 1. Kills Ambiguity Before It Spreads

Most requirement bugs originate from a single fuzzy sentence passed between PM, designer, and developer. This skill enforces precise language — `>= 3 days` instead of "a few days later" — so everyone interprets the spec identically.

### 2. A Shared Visual Vocabulary

Swimlane diagrams and decision matrices are universally readable across roles. A business stakeholder, a QA tester, and a backend engineer can all point at the same matrix cell and say *"this one is missing."*

### 3. Catches What One Brain Misses

Individual domain experts have blind spots. The 8 thinking modes act as a systematic second brain — forcing the team to consider reverse operations, boundary values, and hidden stakeholders (finance, compliance, the boss) that typically surface only after launch.

### 4. PRD-Ready Output, Zero Friction

The skill output follows a rigid 12-section template. No hunting for the right document structure — the AI handles formatting, the team reviews content. An analysis that once took 2 days of meetings becomes a 10-minute AI conversation.

### 5. Tests Fall Out Naturally

Decision matrices and boundary tables double as acceptance test cases. A cell marked `√` becomes a Given-When-Then scenario. QA no longer needs to reverse-engineer test cases from prose.

---

## Installation

**Global** (available in all projects):
```bash
# Copy the folder to your global skills directory
cp -r business-analysis ~/.codebuddy/skills/
```

**Per-project**:
```bash
cp -r business-analysis your-project/.codebuddy/skills/
```

Restart CodeBuddy, and the skill will auto-activate whenever you discuss requirements.

---

## Credits

Based on **《可视化需求分析》** (Visual Requirements Analysis) by Stephen Wang. All 8 thinking modes, structural analysis tools, and quality standards originate from this methodology.
