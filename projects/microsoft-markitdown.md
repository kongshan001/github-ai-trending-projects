# Microsoft MarkItDown

> **仓库**：`microsoft/markitdown`
> **Star**：16.2 万（月增 3.4 万，视频时点 16.1 万） (≈162,000 ⭐)
> **梯队**：T1 千星+月增过万
> **来源**：[20260701 期报告](../reports/20260701_analysis.md) · UP 主：前端布洛芬

## 🏷️ 标签

- `RAG`
- `文档预处理`
- `数据管道`

## 💎 核心价值

微软万能文档预处理工具，PDF / Word / PPT / Excel / 音频等数十种格式一键转 Markdown

## 📋 业务场景

企业知识库、PDF 问答、合同解析

## 🎯 最佳实践

- **RAG 预处理必备**：先把非结构化文档统一成 Markdown，再切片喂给 embedding
  - **命令行优先**：`markitdown file.pdf > out.md`，比脚本解析稳定 10 倍
  - **保留图片**：`--keep-data-uris` 选项，让图也能进 RAG
  - **批量处理**：`find . -name "*.pdf" | xargs -I {} markitdown {}`

## 🔗 关联项目

<!-- 由 topics/ 索引反向关联，生成时自动填 -->

---

## 元数据

```yaml
repo: microsoft/markitdown
star_count: 162000
star_raw: "16.2 万（月增 3.4 万，视频时点 16.1 万）"
growth: "月增 3.4 万"
first_seen: 20260701
source_video: BV1puTi6tEoE
tags: ['rag', '文档预处理', '数据管道']
```
