# 🎯 业务场景索引

> **快速找答案**：你想做什么业务？翻对应目录，列出可用的开源项目。

## 索引列表

| 场景 | 一句话描述 | 推荐项目数 |
|------|------------|------------|
| [📄 RAG / 文档问答](./rag-document-qa.md) | 文档预处理 + 切片 + 检索 | 2 |
| [🏢 业务知识 RAG / 企业知识问答](./business-rag.md) | 两阶段检索 + 多租户隔离 | 1 |
| [🎬 短视频自动化生产](./short-video-automation.md) | 文案→配音→剪辑一条龙 | 3 |
| [🤖 Agent Coding / Claude Code](./agent-coding.md) | 协议 + 多账号 + Skills 生态 | 7 |
| [🧠 代码知识图谱 / 代码理解](./code-knowledge-graph.md) | 14 MCP 工具 + 两条铁律 | 4 |
| [📚 团队 Skill 仓库 / 能力沉淀](./team-skill-hub.md) | 两层架构 + RAG 联动 | 1 |
| [🔒 AI 安全审计 / 合规](./ai-security-audit.md) | 垂直 Skills + 合规框架 | 1 |
| [🌐 跨平台信息获取 (MCP)](./cross-platform-mcp.md) | Agent 跨平台读取 | 4 |
| [🧠 长期记忆 / 知识沉淀](./long-term-memory.md) | Agent 跨会话记忆 | 1 |
| [💰 LLM 成本优化](./llm-cost-optimization.md) | Token 压缩 / 提示工程 | 1 |
| [🔍 代码搜索 / 代码理解](./code-search.md) | MCP 代码检索 | 1 |
| [☁️ GCP / 企业级 Agent 部署](./gcp-enterprise.md) | Google 生态 | 2 |
| [🎨 前端设计 / Vibe Coding](./frontend-design.md) | 给 AI 加设计品味，对抗 AI Slop | 1 |
| [👔 HR 招聘 / 简历评估](./hr-recruitment.md) | 简历初筛 + JD 匹配 | 1 |
| [📚 深度调研报告生成](./deep-research-report.md) | 结构化报告 + 引用追溯 + 反方观点 | 4 |

## 横向对比表

| 场景 | 核心项目 | 替代方案 | 成熟度 |
|------|----------|----------|--------|
| 文档→Markdown | microsoft/markitdown | pandoc, unstructured | ⭐⭐⭐ |
| AI 短视频 | harry0703/MoneyPrinterTurbo | OpenMontage (视频工作室级) | ⭐⭐ |
| Agent Skills 协议 | anthropics/skills | mattpocock/skills (TS派) | ⭐⭐⭐ |
| Claude Code 多账号 | farion1231/cc-switch | 自建配置切换 | ⭐⭐⭐ |
| 跨平台读取 MCP | Panniantong/Agent-Reach | 官方各平台 API | ⭐⭐ |
| 代码 MCP | DeusData/codebase-memory-mcp | Sourcegraph, grep | ⭐⭐⭐ |
| 长期记忆 | supermemoryai/supermemory | mem0, vector DB 自建 | ⭐⭐ |
| 安全审计 Skills | mukul975/Anthropic-Cybersecurity-Skills | 自建规则库 | ⭐⭐ |
| 深度调研报告（结构化两阶段） | Weizhena/Deep-Research-skills | 199-biotech（更严）, hoolulu（中文更优） | ⭐⭐⭐ |
| 深度调研报告（企业级 8 阶段） | 199-biotech/claude-deep-research-skill | Weizhena（更轻量）, hoolulu（中文更优） | ⭐⭐⭐ |
| 深度调研报告（中文券商级） | hoolulu/deep-research | Weizhena, 199-biotech | ⭐⭐⭐ |
| 学术论文全流程 | lingzhi227/agent-research-skills | 自拼 skill 集 | ⭐⭐ |
| 业务知识 RAG | eosphoros-ai/DB-GPT | LangChain, LlamaIndex | ⭐⭐⭐ |
| 代码知识图谱（生产） | DeusData/codebase-memory-mcp | GitNexus, grep | ⭐⭐⭐ |
| 代码知识图谱（轻量） | abhigyanpatwari/GitNexus | codebase-memory-mcp | ⭐⭐ |
| 团队 Skill 仓库（企业自托管） | iflytek/skillhub | obra/superpowers | ⭐⭐⭐ |

## 使用方法

### 1. 我有明确业务需求

直接点对应场景，例如"我想做 RAG 文档问答" → [rag-document-qa.md](./rag-document-qa.md)

### 2. 我想了解某个项目的所有应用场景

翻 [projects/](../projects/) 找项目卡片，看"业务场景"字段

### 3. 我想知道最新趋势

翻 [reports/](../reports/) 看原始视频解析（含 UP 主提炼的 3 大趋势）

### 4. 我想对比 Star 数变化

翻 [stats/](../stats/) 有各期快照 JSON

---

## 标签云（按出现频次）

```
Agent Skills 协议 (3) · MCP (4) · Claude Code (2) · 文档处理 (1) · 
视频生产 (2) · 长期记忆 (1) · 安全审计 (1) · 代码搜索 (1) ·
跨平台 (1) · 成本优化 (1) · TypeScript (2) · Google 生态 (1) ·
深度调研 (4) · 中文场景 (1) · 多语种 (1) · 学术 (1)
```