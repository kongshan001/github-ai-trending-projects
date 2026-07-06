# 🎯 业务场景索引

> **快速找答案**：你想做什么业务？翻对应目录，列出可用的开源项目。

## 索引列表

| 场景 | 一句话描述 | 推荐项目数 |
|------|------------|------------|
| [📄 RAG / 文档问答](./rag-document-qa.md) | 文档预处理 + 切片 + 检索 | 2 |
| [🏢 业务知识 RAG / 企业知识问答](./business-rag.md) | 两阶段检索 + 多租户隔离 | 3 |
| [🎬 短视频自动化生产](./short-video-automation.md) | 文案→配音→剪辑一条龙 | 3 |
| [🤖 Agent Coding / Claude Code](./agent-coding.md) | 协议 + 多账号 + Skills 生态 | 7 |
| [🧠 代码知识图谱 / 代码理解](./code-knowledge-graph.md) | 14 MCP 工具 + 两条铁律 | 4 |
| [📚 团队 Skill 仓库 / 能力沉淀](./team-skill-hub.md) | 两层架构 + RAG 联动 | 3 |
| [🔒 AI 安全审计 / 合规](./ai-security-audit.md) | 垂直 Skills + 合规框架 | 1 |
| [🌐 跨平台信息获取 (MCP)](./cross-platform-mcp.md) | Agent 跨平台读取 | 4 |
| [🧠 长期记忆 / 知识沉淀](./long-term-memory.md) | Agent 跨会话记忆 | 1 |
| [💰 LLM 成本优化](./llm-cost-optimization.md) | Token 压缩 / 提示工程 | 1 |
| [🔍 代码搜索 / 代码理解](./code-search.md) | MCP 代码检索 | 1 |
| [☁️ GCP / 企业级 Agent 部署](./gcp-enterprise.md) | Google 生态 | 2 |
| [🎨 前端设计 / Vibe Coding](./frontend-design.md) | 给 AI 加设计品味，对抗 AI Slop | 1 |
| [👔 HR 招聘 / 简历评估](./hr-recruitment.md) | 简历初筛 + JD 匹配 | 1 |

## 横向对比表

| 场景 | 核心项目 | 替代方案 | 成熟度 |
|------|----------|----------|--------|
| 文档→Markdown | microsoft/markitdown | pandoc, unstructured | ⭐⭐⭐ |
| 业务知识 RAG | eosphoros-ai/DB-GPT | LangChain, LlamaIndex | ⭐⭐⭐ |
| AI 短视频 | harry0703/MoneyPrinterTurbo | OpenMontage (视频工作室级) | ⭐⭐ |
| Agent Skills 协议 | anthropics/skills | mattpocock/skills (TS派) | ⭐⭐⭐ |
| Claude Code 多账号 | farion1231/cc-switch | 自建配置切换 | ⭐⭐⭐ |
| 跨平台读取 MCP | Panniantong/Agent-Reach | 官方各平台 API | ⭐⭐ |
| 代码知识图谱 | DeusData/codebase-memory-mcp | GitNexus, grep | ⭐⭐⭐ |
| 团队 Skill 仓库 | iflytek/skillhub | obra/superpowers | ⭐⭐⭐ |
| 长期记忆 | supermemoryai/supermemory | mem0, vector DB 自建 | ⭐⭐ |
| 安全审计 Skills | mukul975/Anthropic-Cybersecurity-Skills | 自建规则库 | ⭐⭐ |

## 使用方法

### 1. 我有明确业务需求

直接点对应场景，例如：
- "我想做业务知识问答" → [business-rag.md](./business-rag.md)
- "我想让 AI 改代码前看到爆炸半径" → [code-knowledge-graph.md](./code-knowledge-graph.md)
- "我想沉淀团队 Skill 仓库" → [team-skill-hub.md](./team-skill-hub.md)
- "我想做 RAG 文档问答" → [rag-document-qa.md](./rag-document-qa.md)

### 2. 我想了解某个项目的所有应用场景

翻 [projects/](../projects/) 找项目卡片，看"业务场景"字段

### 3. 我想知道最新趋势

翻 [reports/](../reports/) 看原始视频解析（含 UP 主提炼的 3 大趋势）

### 4. 我想对比 Star 数变化

翻 [stats/](../stats/) 有各期快照 JSON

---

## 标签云（按出现频次）

```
Agent Skills (5) · MCP (6) · Claude Code (3) · 文档处理 (1) · 
视频生产 (2) · 长期记忆 (1) · 安全审计 (1) · 代码搜索 (2) ·
跨平台 (1) · 成本优化 (1) · TypeScript (2) · Google 生态 (1) ·
知识图谱 (4) · 业务 RAG (2) · 多租户 (1) · Skill 仓库 (2) ·
CrossEncoder (1) · Tree-sitter (1) · 158 语言 (1)
```

## 🆕 v0.2.2 增量

**新增 3 个场景索引**：
- 🏢 **业务知识 RAG** — 两阶段检索 + 多租户隔离
- 🧠 **代码知识图谱** — 14 MCP 工具 + 两条铁律
- 📚 **团队 Skill 仓库** — 两层架构 + RAG 联动

**新增 9 个项目**：
- [DeusData/codebase-memory-mcp](../projects/DeusData-codebase-memory-mcp.md)（27k ⭐，stage3 主推）
- [abhigyanpatwari/GitNexus](../projects/abhigyanpatwari-GitNexus.md)（44k ⭐，零服务器图谱）
- [AsyncFuncAI/deepwiki-open](../projects/AsyncFuncAI-deepwiki-open.md)（17k ⭐）
- [sourcebot-dev/sourcebot](../projects/sourcebot-dev-sourcebot.md)（3.5k ⭐）
- [eosphoros-ai/DB-GPT](../projects/eosphoros-ai-DB-GPT.md)（19k ⭐，stage3 主推）
- [iflytek/skillhub](../projects/iflytek-skillhub.md)（3.7k ⭐，stage3 主推）
- [Fission-AI/OpenSpec](../projects/Fission-AI-OpenSpec.md)（59k ⭐，E06 预告）
- [obra/superpowers](../projects/obra-superpowers.md)（248k ⭐，E06 预告）
- [Johnson-Jia/ai-landing-tutorial](../projects/Johnson-Jia-ai-landing-tutorial.md)（教程仓库）
