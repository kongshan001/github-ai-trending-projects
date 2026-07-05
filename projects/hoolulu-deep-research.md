# hoolulu/deep-research

> **仓库**：`hoolulu/deep-research`
> **Star**：432 ⭐（2026-07-05 实时）
> **梯队**：T2 垂直领域明星
> **来源**：Hermes Agent 调研（2026-07-05）
> **原仓库**：[github.com/hoolulu/deep-research](https://github.com/hoolulu/deep-research)

## 🏷️ 标签

- `Deep Research`
- `中文券商级`
- `19 种语言`
- `多 Agent`
- `离线模式`

## 💎 核心价值

**中文友好 + 券商级深度调研报告生成 skill**。一条命令十分钟出对标券商结构的深度报告：结论先行、来源可追溯、反方视角、置信度分级。**19 种语言自动识别**（非翻译，原生撰写）。

## 📋 业务场景

- 中文行业研究、趋势前瞻、竞品扫描
- 政策解读、技术专题、投研备忘
- 多语言跨国调研（俄语/日语/韩语/英语等）
- 离线模式：读本地 PDF/DOCX/TXT/MD 做调研（不联网）

## 🎯 最佳实践

- **一句话跑完**：`/research 中国新能源汽车产业发展现状` → 全自动出报告
- **多 Agent 并行撰写**：所有章节同时撰写（事实直接嵌入 prompt，不做工具调用），比串行快得多
- **五层并行搜索**：
  ```
  Layer 0 — CLI 内置引擎（如 OpenCode 的 Exa websearch）
  Layer 1 — 大纲建议源（按主题定向推荐）
  Layer 2 — SearXNG（作者部署，70+ 引擎）
  Layer 3 — sources.json（skill 内置 30+ 优质源）
  Layer 4 — 免费源补强（仅在独立来源 < 8 时触发）
  ```
- **数据防坑机制**：自动识别常见数据错误（单位搞混、数据造假、张冠李戴），不让有问题的数据混进报告
- **正反观点并存**：每章呈现争议和反对角度，不回避矛盾
- **本地浏览页**：`reports-browser/index.html` 自动生成，支持搜索/筛选/排序/弹窗预览/PDF/DOCX 导出
- **极低成本**：DeepSeek v4 Flash 跑 Standard 模式仅 < 0.4 元

## 🔗 关联项目

<!-- 由 topics/ 索引反向关联，生成时自动填 -->

---

## 元数据

```yaml
repo: hoolulu/deep-research
star_count: 432
star_raw: "432 ⭐ (2026-07-05)"
growth: "快速增长（2026-06-05 创建）"
first_seen: 20260705
source_video: null
source: Hermes Agent 调研
tags: ['deep-research', '中文', '券商级', '19-语言', '多-agent']
license: MIT
```

## 补全说明

> 本卡片在 **v0.2.2** 版本新增。来源：用户手动调研 + Hermes Agent 通过 GitHub API 验证。
>
> **示例报告可在线预览**：[H33研报· 深度调研报告集](https://www.h33.top)
>
> **典型产出（Standard 模式）**：
> - 报告长度：500-700 行 / 12,000-20,000 字
> - 数据表：15-25 张
> - 引用机构：15-25 家
> - 反方观点：3-8 处
> - 总耗时：~10-20 分钟