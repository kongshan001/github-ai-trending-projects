# lingzhi227/agent-research-skills

> **仓库**：`lingzhi227/agent-research-skills`
> **Star**：182 ⭐（2026-07-05 实时）
> **梯队**：T2 垂直领域明星
> **来源**：Hermes Agent 调研（2026-07-05）
> **原仓库**：[github.com/lingzhi227/agent-research-skills](https://github.com/lingzhi227/agent-research-skills)

## 🏷️ 标签

- `学术全流程`
- `31 个 skills`
- `Claude Code`
- `论文写作`
- `从文献综述到投稿`

## 💎 核心价值

**学术论文全生命周期 skill 集**——31 个 skill 覆盖从「文献搜索」到「投稿幻灯片」的完整学术流程。提炼自 17 个 LLM-agent 自动化研究仓库的设计规范。

## 📋 业务场景

- 学术研究：文献综述、Idea 生成、新颖性评估
- 论文写作：方法/实验/正文各章节
- 评审：自审、修改、Rebuttal
- 衍生：论文→Beamer 幻灯片、论文→可运行代码仓库

## 🎯 最佳实践

### 7 阶段 × 31 skills 完整流水线

| 阶段 | 关键 skills |
|------|-------------|
| 0 发现/规划 | github-research, deep-research, literature-search/review, idea-generation, novelty-assessment, research-planning |
| 1 方法设计 | atomic-decomposition, algorithm-design, math-reasoning, symbolic-equation |
| 2 实验流水线 | experiment-design, experiment-code, code-debugging, data-analysis |
| 3 论文写作 | paper-writing-section, related-work-writing, survey-generation, paper-to-code |
| 4 图/表/引用 | figure-generation, table-generation, citation-management, backward-traceability |
| 5 LaTeX | latex-formatting, paper-compilation, excalidraw-skill |
| 6 评审/成品 | self-review, paper-revision, rebuttal-writing, slide-generation, paper-assembly |

- **一装全有**：`npx skills add lingzhi227/agent-research-skills -g -a claude-code`
- **多源学术搜索**：Semantic Scholar / arXiv / OpenAlex / CrossRef 一站式
- **可追溯引用**：每个 PDF 数字都能反向链接到产生它的代码行（backward-traceability）
- **多 persona 自审**：3 人评审（NeurIPS 表单）+ 反思 + meta-review
- **会议模板内置**：ICML / ICLR / NeurIPS / AAAI / ACL

## 🔗 关联项目

<!-- 由 topics/ 索引反向关联，生成时自动填 -->

---

## 元数据

```yaml
repo: lingzhi227/agent-research-skills
star_count: 182
star_raw: "182 ⭐ (2026-07-05)"
growth: "稳定增长"
first_seen: 20260705
source_video: null
source: Hermes Agent 调研
tags: ['学术', '论文写作', 'claude-code-skills', '31-skills']
license: null  # 仓库未声明
```

## 补全说明

> 本卡片在 **v0.2.2** 版本新增。来源：用户手动调研 + Hermes Agent 通过 GitHub API 验证。
>
> **适用 vs 不适用**：
> - ✅ 适用：学术研究者、博士生、ML 研究员
> - ❌ 不适用：纯行业调研/产品调研（用 Weizhena 或 hoolulu 更合适）
>
> **可选配置**：
> - Semantic Scholar API Key（更高频次限制）→ `~/keys.md` 写 `S2_API_Key: your-key`
> - PyMuPDF（PDF 解析）：`pip install PyMuPDF`
> - numpy + scipy（统计检验）：`pip install numpy scipy`