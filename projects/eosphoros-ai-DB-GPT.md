# eosphoros-ai/DB-GPT

> **仓库**：`eosphoros-ai/DB-GPT`
> **Star**：19,382 (≈1.94 万)
> **梯队**：T1 千星+月增过万
> **来源**：[20260706 期报告](../reports/20260706_analysis.md) · UP 主：GitHub星探

## 🏷️ 标签

- `RAG`
- `多租户`
- `向量库`
- `业务知识`
- `两阶段检索`

## 💎 核心价值

Open-source agentic AI data assistant — 自研业务 RAG 服务的推荐框架，**视频 stage3.html 明确推荐**。

## 📋 业务场景

- 企业内部业务知识库（产品手册、规范、流程）
- 多租户 RAG（A/B 公司知识隔离）
- Agentic AI 数据助手

## 🎯 最佳实践

- **两阶段检索核心代码**（来自 stage3.html）：
  ```python
  with concurrent.futures.ThreadPoolExecutor() as executor:
      future_default = executor.submit(self.similar_search_plus, text, topk, expr, None)
      future_v3      = executor.submit(self.similar_search_plus, text, topk, expr, self.embedding_v3)
      future_new     = executor.submit(self.similar_search_new,   text, topk, new_expr or expr)
  # 三路并发召回 → 按原文去重 → CrossEncoder 重排 → min_score 过滤
  ```
- **多租户隔离**：把租户标识拼进 Milvus 过滤表达式
  ```python
  expr = 'corp_code in ["{0}", "default"] and resource_type in ["knowledge","course"]'.format(body.corp_code)
  ```
- **CrossEncoder 重排**：精度大幅提升
- **Default 共享**：`default = 全租户共享`

## 🔗 关联项目

- 🔗 [DeusData/codebase-memory-mcp](DeusData-codebase-memory-mcp.md) — 代码维度，配合业务 RAG
- 🔗 [AsyncFuncAI/deepwiki-open](AsyncFuncAI-deepwiki-open.md) — 基于代码的 RAG

---

## 元数据

```yaml
repo: eosphoros-ai/DB-GPT
star_count: 19382
star_raw: "1.94 万"
growth: ""
first_seen: 20260706
source_video: BV1mGT96JERY
tags: ['rag', '多租户', '向量库', '业务知识', 'agentic']
```
