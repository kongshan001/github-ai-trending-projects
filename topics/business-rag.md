# 🏢 业务知识 RAG / 企业知识问答场景

> 目标：让 AI 懂你的私有业务（产品手册、内部规范），从"开卷考试"代替"概率性盲读"
> **来源**：BV1mGT96JERRY（E05 基础设施四件套 · stage3.html 第一件套）

## 核心理念

**不懂业务**——通用大模型没读过产品手册、内部规范，问业务细节就幻觉。

**业务知识 RAG** 的做法是：先检索知识库片段 → 再喂给模型 → 让 AI "开卷考试"。

## 核心机制：两阶段检索

```
第一阶段：多路召回（召回率优先）
  ↓  按原文去重
第二阶段：CrossEncoder 重排（精度提升）
  ↓  min_score 过滤
最终结果（高质量片段）
```

**为什么两阶段？**
- 第一阶段召回率高 → 避免漏掉相关内容
- 第二阶段重排精度高 → 避免噪音干扰
- 两阶段配合 → 召回率 + 精度双优

## 多租户隔离（企业必备）

把租户标识拼进 Milvus 过滤表达式：

```python
expr = 'corp_code in ["A", "default"] and resource_type in ["knowledge","course"]'
all_docs = client.similar_search(body.current_question, 5, expr)
# A 公司的知识跟 B 公司查不到
# Default = 全租户共享
```

## 🏆 推荐框架

**🎯 [eosphoros-ai/DB-GPT](../../projects/eosphoros-ai-DB-GPT.md)**（⭐19,382）

- 视频 stage3.html 明确推荐
- open-source agentic AI data assistant
- 核心代码（两阶段检索）：
  ```python
  with concurrent.futures.ThreadPoolExecutor() as executor:
      future_default = executor.submit(self.similar_search_plus, text, topk, expr, None)
      future_v3      = executor.submit(self.similar_search_plus, text, topk, expr, self.embedding_v3)
      future_new     = executor.submit(self.similar_search_new,   text, topk, new_expr or expr)
  # 三路并发召回 → 按原文去重 → CrossEncoder 重排 → min_score 过滤
  ```

## 推荐组合

### 完整业务 RAG 流水线

```
企业知识源（产品手册/内部规范/培训资料）
       ↓
[1] 文档预处理（[microsoft/markitdown](../../projects/microsoft-markitdown.md)）
       ↓
[2] 切片（LangChain / LlamaIndex）
       ↓
[3] Embedding（BGE / OpenAI / M3E）
       ↓
[4] 向量库（Milvus / Qdrant）  ← 含租户标识
       ↓
[5] 多路召回（默认 embedding + v3 embedding + new expr）
       ↓
[6] CrossEncoder 重排
       ↓
[7] min_score 过滤 + 租户过滤
       ↓
   LLM 问答
```

## 何时用

- ✅ 企业内部业务知识库（产品手册、规范、流程）
- ✅ 多租户 SaaS（A/B 公司知识严格隔离）
- ✅ 需要给 PM 写需求提供事实基础
- ❌ 个人/小团队（CLAUDE.md 就够）
- ❌ 单租户公开知识（直接用 [microsoft/markitdown](../../projects/microsoft-markitdown.md) 就行）

## 关键指标

- **召回率**：第一阶段能找回多少相关内容（不要漏）
- **精度**：第二阶段排序后前 N 条有多准（不要乱）
- **幻觉率**：基于检索结果回答，能下降多少
- **响应时延**：两阶段检索的总耗时

## 与通用 RAG 框架对比

| 框架 | 定位 | 适合 |
|---|---|---|
| **DB-GPT** | agentic AI data assistant | 企业业务知识 + 多租户 |
| LangChain | 通用 LLM 应用框架 | 自定义 RAG 流水线 |
| LlamaIndex | 文档问答专用 | 文档类型丰富 |
| Dify | 低代码 RAG 平台 | 非工程团队 |

## 不要做的事

- ❌ 不做租户隔离就上生产（数据泄漏事故）
- ❌ 只用单路召回（召回率不够）
- ❌ 跳过 CrossEncoder 重排（精度不够）
- ❌ 把业务知识塞进 LLM 上下文而不是 RAG（上下文爆炸）
- ❌ 不量化幻觉率（无法证明 RAG 有效）

## 推广路径

1. **试点**：1 个核心业务域（如"客服知识库"），量化幻觉下降率
2. **多租户化**：上线租户过滤，A/B 公司先做
3. **完整化**：补全 CrossEncoder 重排 + min_score 过滤
4. **PM 提效**：PM 写需求基于 RAG 事实，减少"凭印象写需求"

## 关联项目

- 🔗 [eosphoros-ai/DB-GPT](../../projects/eosphoros-ai-DB-GPT.md) — **视频 stage3 主推**
- 🔗 [microsoft/markitdown](../../projects/microsoft-markitdown.md) — 文档预处理
- 🔗 [microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md) — Token 压缩
- 🔗 [supermemoryai/supermemory](../../projects/supermemoryai-supermemory.md) — Agent 长期记忆
- 🔗 [Johnson-Jia/ai-landing-tutorial](../../projects/Johnson-Jia-ai-landing-tutorial.md) — stage3.html 教程
