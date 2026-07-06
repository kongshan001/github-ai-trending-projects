# DeusData/codebase-memory-mcp

> **仓库**：`DeusData/codebase-memory-mcp`
> **Star**：27,197 (≈2.72 万)
> **梯队**：T1 千星+月增过万（**stage3 主推**）
> **来源**：
> - [20260701 期报告](../reports/20260701_analysis.md) · UP 主：前端布洛芬
> - [20260706 期报告](../reports/20260706_analysis.md) · UP 主：GitHub星探 ⭐

## 🏷️ 标签

- `代码知识图谱`
- `MCP`
- `Tree-sitter`
- `158 语言`

## 💎 核心价值

高性能代码智能 MCP 服务器，毫秒级索引代码库为持久知识图谱，14 个 MCP 工具覆盖理解/变更/查询全场景。

## 📋 业务场景

- 大仓代码检索 / 跨项目重构 / 新人上手
- 改前看爆炸半径（impact 工具）
- 提交前变更检查（detect_changes 工具）
- 跨仓库定位调用链（实测：累计排查 144 个生产 bug，覆盖率 80.4%）

## 🎯 最佳实践

- **MCP 一键接入**：单文件静态二进制，零依赖
  ```bash
  curl -fsSL https://raw.githubusercontent.com/DeusData/codebase-memory-mcp/main/install.sh | bash
  ```
- **替代 grep**：代码搜索从字符串匹配升级为语义+图谱
- **14 个 MCP 工具**：理解类（context）、变更类（impact / detect_changes）、查询类（Cypher）
- **两条铁律**：改任何符号前必跑 impact；提交前必跑 detect_changes
- **arXiv 论文**：2603.27277（83% 答案质量、10x 节省 token、2.1x 减少工具调用）
- **大型仓库必备**：百万行级代码也能秒级响应；Linux 内核（28M LOC、75K 文件）3 分钟索引完

## 🔗 关联项目

- 🔗 [abhigyanpatwari/GitNexus](abhigyanpatwari-GitNexus.md) — 零服务器本地代码图谱
- 🔗 [AsyncFuncAI/deepwiki-open](AsyncFuncAI-deepwiki-open.md) — 仓库 wiki + RAG
- 🔗 [sourcebot-dev/sourcebot](sourcebot-dev-sourcebot.md) — 自托管代码搜索

---

## 元数据

```yaml
repo: DeusData/codebase-memory-mcp
star_count: 27197
star_raw: "2.72 万（2026-07-06 实测）"
growth: ""
first_seen: 20260701
source_video: BV1puTi6tEoE, BV1mGT96JERY
addendum: "2026-07-06 stage3.html 视频主推代码图谱方案"
tags: ['代码搜索', 'mcp', '知识图谱', 'tree-sitter', '158-语言']
```
