# 📚 深度调研报告生成场景

> 目标：让 AI Agent 替代「搜索+总结」式浅层调研，产出**有结构、有引用、有反方观点**的专业级深度调研报告

## 🎯 选型速查

按你的需求挑一个：

| 你的场景 | 推荐 | 理由 |
|---------|------|------|
| Claude Code 日常技术/行业调研 | 🥇 **Weizhena/Deep-Research-skills** | 结构化两阶段 + 人机协同，最稳 |
| 企业级报告（投融资/尽调） | 🥈 **199-biotech/claude-deep-research-skill** | 8 阶段 + 自动校验，最严 |
| 中文券商级报告 + 多语种 | 🥉 **hoolulu/deep-research** | 中文友好、19 语种、券商结构 |
| 学术论文全流程（综述→投稿） | 🏅 **lingzhi227/agent-research-skills** | 31 个 skills 覆盖学术全流程 |

---

## 🏆 核心枢纽：Weizhena/Deep-Research-skills

[Weizhena/Deep-Research-skills](../../projects/Weizhena-Deep-Research-skills.md) · 1498 ⭐ · MIT

**结构化两阶段 + 人机协同**，理论来自 arXiv 论文 RhinoInsight。**三平台通用**：
- Claude Code（≥2.1.0）
- OpenCode（默认 gpt-5.4）
- Codex

### 5 个命令（完整流水线）

```
/research           → 生成研究大纲（17 个项目 + 字段定义）
/research-add-items → 追加研究项目
/research-add-fields → 追加字段
/research-deep     → 并行 Agent 深度调研
/research-report   → JSON → Markdown 报告
```

### 最佳实践

- **结构化优于随机**：先 `/research` 跑出大纲 → 人工审 → `/research-add-items/fields` 补充 → 再 `/research-deep`
- **可扩展设计**：大纲阶段产出 JSON，可被外部脚本进一步处理

---

## 🥈 企业级方案：199-biotech/claude-deep-research-skill

[199-biotech/claude-deep-research-skill](../../projects/199-biotechnologies-claude-deep-research-skill.md) · 814 ⭐

**8 阶段流水线 + 多 persona red team + 磁盘持久化引用**，自称"超越 OpenAI/Gemini/Claude Desktop"。

### 4 档模式

| 模式 | 阶段 | 时长 | 适用 |
|------|------|------|------|
| Quick | 3 | 2-5 分钟 | 初步摸底 |
| Standard | 6 | 5-10 分钟 | 日常调研 |
| Deep | 8 | 10-20 分钟 | 复杂主题、关键决策 |
| UltraDeep | 8+ | 20-45 分钟 | 尽调级报告 |

### 8 阶段流水线

```
Scope → Plan → Retrieve（并行搜索+子 Agent） → Triangulate
     → Outline Refinement → Synthesize → Critique（带回环） → Refine → Package
```

### 核心亮点

- **Step 0 关键**：先取当前日期再搜索（防 AI 用旧年份瞎编）
- **Critique Loop-back**：第 6 阶段可自动回到第 3 阶段补查询
- **多 persona red team**：Skeptical Practitioner / Adversarial Reviewer / Implementation Engineer
- **磁盘持久化引用**：`sources.json` 跨上下文压缩不丢
- **三步验证**：`validate_report.py`（9 项结构）+ `verify_citations.py`（DOI/URL/幻觉）+ 验证循环

---

## 🥉 中文场景方案：hoolulu/deep-research

[hoolulu/deep-research](../../projects/hoolulu-deep-research.md) · 432 ⭐ · MIT

**中文券商级深度调研报告生成 skill**。一条命令十分钟出报告，**19 种语言自动识别**（非翻译，原生撰写）。

### 4 阶段流程

```
① 分析大纲 → ② 五层并行采集 → ③ 并行撰写 → ④ 验收装配
```

### 五层并行搜索（关键差异化）

```
Layer 0 — CLI 内置引擎（如 OpenCode 的 Exa websearch）
Layer 1 — 大纲建议源（按主题定向推荐）
Layer 2 — SearXNG（作者部署，70+ 引擎）
Layer 3 — sources.json（skill 内置 30+ 优质源）
Layer 4 — 免费源补强（仅在独立来源 < 8 时触发）
```

### 报告独特亮点

| 维度 | 说明 |
|------|------|
| 多语言专业行文 | 自动检测主题语言，以 19 种语言直接撰写报告，非翻译模式 |
| 每个数字有来源 | 正文标注 `(N)` 可点击引用，文末附参考来源列表。找不到来源的数字不写 |
| 正反观点并存 | 每章呈现争议和反对观点，不回避矛盾 |
| 置信度分级 | 末章汇总表（高/中/低），什么可靠什么有争议一目了然 |
| 数据防坑机制 | 自动识别常见数据错误——单位搞混、数据造假、张冠李戴 |
| 段落重于行数 | 每章 8-12 段正文为核心，表格和空行灌不了水 |

### 成本（DeepSeek v4 Flash）

- Quick: ~10-15 万 token / < 0.2 元
- Standard: ~15-30 万 / < 0.4 元
- Deep: ~30-50 万 / < 0.7 元

### 输出

- `~/Documents/[Topic]_Research_[Date]/` 下 Markdown + HTML（麦肯锡风格）+ PDF
- 内置 `reports-browser/index.html` 本地浏览页（搜索/筛选/弹窗预览/PDF/DOCX 导出）

---

## 🏅 学术全流程：lingzhi227/agent-research-skills

[lingzhi227/agent-research-skills](../../projects/lingzhi227-agent-research-skills.md) · 182 ⭐

**31 个 skills 覆盖学术论文全生命周期**——从文献搜索到投稿幻灯片。

### 7 阶段 × 31 skills

| 阶段 | 关键 skills |
|------|-------------|
| 0 发现/规划 | github-research, deep-research, literature-search/review, idea-generation, novelty-assessment, research-planning |
| 1 方法设计 | atomic-decomposition, algorithm-design, math-reasoning, symbolic-equation |
| 2 实验流水线 | experiment-design, experiment-code, code-debugging, data-analysis |
| 3 论文写作 | paper-writing-section, related-work-writing, survey-generation, paper-to-code |
| 4 图/表/引用 | figure-generation, table-generation, citation-management, backward-traceability |
| 5 LaTeX | latex-formatting, paper-compilation, excalidraw-skill |
| 6 评审/成品 | self-review, paper-revision, rebuttal-writing, slide-generation, paper-assembly |

### 安装

```bash
npx skills add lingzhi227/agent-research-skills -g -a claude-code
```

### 适用 vs 不适用

- ✅ 适用：学术研究者、博士生、ML 研究员
- ❌ 不适用：纯行业调研/产品调研（用 Weizhena 或 hoolulu 更合适）

---

## 🔧 与其他 MCP 类项目的关系

```
Claude Code / Cursor / Codex
  ↓
┌──────────────────────────────────────┐
│ Deep Research Skill（场景化报告生成） │
│ Weizhena / 199-biotech / hoolulu     │
└──────────────────────────────────────┘
  ↓ 依赖
┌──────────────────────────────────────┐
│ 跨平台 MCP（数据采集）              │
│ Panniantong/Agent-Reach              │
└──────────────────────────────────────┘
  ↓
┌──────────────────────────────────────┐
│ 长期记忆 MCP（沉淀）                │
│ supermemoryai/supermemory             │
└──────────────────────────────────────┘
```

**实战组合**：
- 用 Agent-Reach 拉社交平台/全网数据
- 用 Deep Research Skill 整理成专业报告
- 用 supermemory 把报告沉淀进知识库

## 关联项目

- 🔗 [Weizhena/Deep-Research-skills](../../projects/Weizhena-Deep-Research-skills.md)
- 🔗 [199-biotech/claude-deep-research-skill](../../projects/199-biotechnologies-claude-deep-research-skill.md)
- 🔗 [hoolulu/deep-research](../../projects/hoolulu-deep-research.md)
- 🔗 [lingzhi227/agent-research-skills](../../projects/lingzhi227-agent-research-skills.md)
- 🔗 [Panniantong/Agent-Reach](../../projects/Panniantong-Agent-Reach.md)（数据源）
- 🔗 [supermemoryai/supermemory](../../projects/supermemoryai-supermemory.md)（沉淀）