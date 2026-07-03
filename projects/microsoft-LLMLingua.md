# microsoft/LLMLingua

> **仓库**：`microsoft/LLMLingua`
> **Star**：6.4k（系列累计更高） (≈6,400 ⭐)
> **梯队**：T2 垂直领域明星
> **来源**：[20260701 期报告](../reports/20260701_analysis.md) · UP 主：前端布洛芬

## 🏷️ 标签

- `LLM 优化`
- `成本压缩`
- `MCP`

## 💎 核心价值

LLM 提示压缩神器，进大模型前压缩 60-95%

## 📋 业务场景

长文档问答 / 代码仓库 RAG / 成本敏感型 Agent

## 🎯 最佳实践

- **MCP 模式部署**：起一个 `llmlingua-mcp`，所有 Agent 自动获益
  - **保留关键信息**：使用 `force_tokens` 参数保护专有名词
  - **混合策略**：长上下文 → 先压 → 再喂，避免 token 爆

## 🔗 关联项目

<!-- 由 topics/ 索引反向关联，生成时自动填 -->

---

## 元数据

```yaml
repo: microsoft/LLMLingua
star_count: 6400
star_raw: "6.4k（系列累计更高）"
growth: ""
first_seen: 20260701
source_video: BV1puTi6tEoE
tags: ['llm-优化', '成本压缩', 'mcp']
```
