# 199-biotechnologies/claude-deep-research-skill

> **仓库**：`199-biotechnologies/claude-deep-research-skill`
> **Star**：814 ⭐（2026-07-05 实时）
> **梯队**：T1 千星+月增过万
> **来源**：Hermes Agent 调研（2026-07-05）
> **原仓库**：[github.com/199-biotechnologies/claude-deep-research-skill](https://github.com/199-biotechnologies/claude-deep-research-skill)

## 🏷️ 标签

- `Deep Research`
- `Claude Code Skills`
- `企业级`
- `8 阶段流水线`
- `源可信度评分`
- `自动校验`

## 💎 核心价值

**企业级**深度研究 skill，自称"在质量和验证上超越 OpenAI / Gemini / Claude Desktop"。8 阶段流水线 + 多 persona red team + 磁盘持久化引用 + 自动验证（DOI/URL/幻觉检测）。

## 📋 业务场景

- 企业级研究报告（投融资决策、并购尽调、技术战略评估）
- 关键决策前的尽调材料生成
- 多源信息三角化验证（避免单源偏差）
- 需要严格引用追溯的学术/合规场景

## 🎯 最佳实践

- **UltraDeep 模式才是真家伙**：标准模式 6 阶段（5-10 分钟）够日常用，但关键决策必须上 UltraDeep 模式（8+ 阶段、20-45 分钟），才能触发多 persona red team 校验
- **Step 0 关键**：先取当前日期再搜索——避免 AI 用训练数据里旧的年份瞎编数据
- **Critique Loop-back**：第 6 阶段可自动回到第 3 阶段补查询（无需人工），最终报告质量更稳
- **sources.json 持久化**：所有引用写到磁盘 → 上下文压缩/续接 Agent 时不丢，>18K 字长报告自动递归续写
- **三步验证**：`validate_report.py`（9 项结构校验）+ `verify_citations.py`（DOI/URL/幻觉）+ 验证循环（最多 3 轮 fix→retry）

## 🔗 关联项目

<!-- 由 topics/ 索引反向关联，生成时自动填 -->

---

## 元数据

```yaml
repo: 199-biotechnologies/claude-deep-research-skill
star_count: 814
star_raw: "814 ⭐ (2026-07-05)"
growth: "稳定月增"
first_seen: 20260705
source_video: null
source: Hermes Agent 调研
tags: ['deep-research', 'claude-code-skills', '企业级', '8-阶段', '源可信度']
license: null  # 仓库未声明
```

## 补全说明

> 本卡片在 **v0.2.2** 版本新增。来源：用户手动调研 + Hermes Agent 通过 GitHub API 验证。
>
> **模式选择指南**：
> - Quick（3 阶段 / 2-5 分钟）：初步摸底
> - Standard（6 阶段 / 5-10 分钟）：日常调研
> - Deep（8 阶段 / 10-20 分钟）：复杂主题、关键决策
> - UltraDeep（8+ 阶段 / 20-45 分钟）：尽调级报告
>
> **依赖**：可选 `brew install search-cli` 接入多 provider 搜索（Brave/Serper/Exa/Jina/Firecrawl），无 Key 也能用 Claude Code 内置 WebSearch 兜底。