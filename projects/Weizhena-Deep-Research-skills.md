# Weizhena/Deep-Research-skills

> **仓库**：`Weizhena/Deep-Research-skills`
> **Star**：1498 ⭐（2026-07-05 实时）
> **梯队**：T1 千星+月增过万
> **来源**：Hermes Agent 调研（2026-07-05）
> **原仓库**：[github.com/Weizhena/Deep-Research-skills](https://github.com/Weizhena/Deep-Research-skills)

## 🏷️ 标签

- `Deep Research`
- `Claude Code Skills`
- `人机协同`
- `结构化两阶段`
- `OpenCode`
- `Codex`

## 💎 核心价值

基于 arXiv 论文 [RhinoInsight](https://arxiv.org/abs/2511.18743) 的结构化深度研究 skill，把"研究"拆成**两阶段**：大纲生成（可扩展）+ 深度调研。每步都有人机协同检查点，确保研究方向不跑偏。

**5 个命令 = 完整流水线**：
```
/research           → 生成研究大纲（17 个项目 + 字段定义）
/research-add-items → 追加研究项目
/research-add-fields → 追加字段
/research-deep     → 并行 Agent 深度调研
/research-report   → JSON → Markdown 报告
```

## 📋 业务场景

- 学术调研（论文综述、基准对比、文献分析）
- 技术调研（技术对比、框架评估、工具选型）
- 市场调研（竞品分析、行业趋势、产品对比）
- 尽调（公司研究、投资分析、风险评估）

## 🎯 最佳实践

- **结构化优于随机**：先 `/research` 跑出大纲 → 人工审 → `/research-add-items/fields` 补充 → 再 `/research-deep`，避免一上来就让 Agent 自由发挥跑偏
- **三平台通用**：同一套 skill 同时支持 Claude Code（≥2.1.0）/ OpenCode（默认 gpt-5.4，需 `OPENCODE_ENABLE_EXA=1`）/ Codex
- **可扩展设计**：大纲阶段产出的是 JSON，可被外部脚本进一步处理（生成表格、写报告模板、塞数据库）
- **人在回路**：每个阶段产出物都可被打断 + 修改，而不是黑盒运行到底

## 🔗 关联项目

<!-- 由 topics/ 索引反向关联，生成时自动填 -->

---

## 元数据

```yaml
repo: Weizhena/Deep-Research-skills
star_count: 1498
star_raw: "1498 ⭐ (2026-07-05)"
growth: "稳定月增"
first_seen: 20260705
source_video: null  # 调研类，非视频提取
source: Hermes Agent 调研
tags: ['deep-research', 'claude-code-skills', '人机协同', 'opencode', 'codex']
license: MIT
```

## 补全说明

> 本卡片在 **v0.2.2** 版本新增。来源：用户手动调研 + Hermes Agent 通过 GitHub API 验证。
>
> 与其他 deep-research skill 的差异化定位：
> - **Weizhena** = 结构化 + 两阶段 + 人机协同（最稳）
> - **199-biotech** = 企业级 8 阶段 + 自动校验（最严）
> - **hoolulu** = 中文券商级 + 19 语种（最懂中文）
> - **lingzhi227** = 学术全流程 31 skills（最学术）