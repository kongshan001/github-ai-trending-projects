# 📄 RAG / 文档问答 场景

> 目标：把 PDF / Word / PPT / Excel / 图片等异构文档喂给 LLM 做检索增强问答

## 推荐组合

### 1️⃣ 文档预处理（必选）

**🎯 首选：[microsoft/markitdown](../../projects/microsoft-markitdown.md)**

- **为什么**：微软官方，16.2 万 star，数十种格式一键转 Markdown
- **核心能力**：集成 Azure Document Intelligence，行业事实标准
- **何时用**：任何需要把非结构化文档统一成文本的 RAG 项目

**快速开始**：

```bash
pip install markitdown[all]
markitdown contract.pdf > contract.md
markitdown --keep-data-uris report.pdf > report_with_images.md
```

### 2️⃣ Token 压缩（可选，长上下文场景）

**🎯 配合：[microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md)**

- **为什么**：喂 LLM 前压 60-95%，月成本可砍一半
- **何时用**：上下文长（>32K token）、喂整本书/整个代码库时

```bash
# 起 LLMLingua MCP server，所有 Agent 自动获益
llmlingua-mcp
```

## 完整 RAG 流水线参考

```
PDF/Word/PPT/Excel
       ↓
[1] MarkItDown → 统一 Markdown
       ↓
[2] 切片 (LangChain / LlamaIndex)
       ↓
[3] Embedding (OpenAI / BGE / M3E)
       ↓
[4] 向量库 (Chroma / Qdrant / Milvus)
       ↓
[5] (可选) LLMLingua 压缩 query
       ↓
   LLM 问答
```

## 不要做的事

- ❌ 直接把 PDF 文本抽出来就喂 LLM（图片、表格全丢）
- ❌ 不切片整段喂（超 32K token 上下文爆掉）
- ❌ 跳过 Markdown 预处理（结构性丢失导致检索召回率低）

## 关联项目

- 🔗 [microsoft/markitdown](../../projects/microsoft-markitdown.md)
- 🔗 [microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md)