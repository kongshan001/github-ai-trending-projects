# 🎯 B 站开源项目情报库

> **目标**：从 B 站热门开源项目视频里提炼业务场景可用的工具，按场景快速检索

[![Stars](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Frepos%2Fkongshan001%2Fbilibili-trending-projects&query=%24.stargazers_count&label=stars)](https://github.com/kongshan001/bilibili-trending-projects)
[![Forks](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Frepos%2Fkongshan001%2Fbilibili-trending-projects&query=%24.forks_count&label=forks)](https://github.com/kongshan001/bilibili-trending-projects)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 🚀 30 秒上手

**问：我有一个业务需求，怎么找开源项目？**

```bash
# 1. 打开 topics/ 找你的场景
cat topics/business-rag.md          # 想做业务知识 RAG
cat topics/code-knowledge-graph.md  # 想做代码知识图谱
cat topics/team-skill-hub.md        # 想做团队 Skill 仓库
cat topics/rag-document-qa.md       # 想做 RAG/文档问答
cat topics/agent-coding.md          # 想搭 Claude Code 工作流
...

# 2. 找到项目名后看 projects/ 卡片
cat projects/DeusData-codebase-memory-mcp.md  # 项目详情 + 最佳实践

# 3. 看原始视频解析（深度调研）
cat reports/20260706_analysis.md
```

## 🗂️ 仓库结构

```
.
├── README.md                      # ← 你正在看
├── topics/                        # ★ 业务场景索引（按需检索）
│   ├── README.md                  # 场景总览（14 个场景）
│   ├── rag-document-qa.md         # RAG / 文档问答
│   ├── business-rag.md            # 🆕 业务知识 RAG / 企业知识问答
│   ├── short-video-automation.md  # 短视频自动化
│   ├── agent-coding.md            # Agent Coding / Claude Code
│   ├── code-knowledge-graph.md    # 🆕 代码知识图谱 / 代码理解
│   ├── team-skill-hub.md          # 🆕 团队 Skill 仓库 / 能力沉淀
│   ├── ai-security-audit.md       # 安全审计 / 合规
│   ├── cross-platform-mcp.md      # 跨平台信息获取 (MCP)
│   ├── long-term-memory.md        # 长期记忆 / 知识沉淀
│   ├── llm-cost-optimization.md   # LLM 成本优化
│   ├── code-search.md             # 代码搜索
│   └── gcp-enterprise.md          # GCP / 企业级部署
│
├── projects/                      # ★ 项目卡片（每个项目一张，共 25 张）
│   ├── microsoft-markitdown.md
│   ├── anthropics-skills.md
│   ├── DeusData-codebase-memory-mcp.md       # 🆕 stage3 主推
│   ├── abhigyanpatwari-GitNexus.md           # 🆕
│   ├── AsyncFuncAI-deepwiki-open.md          # 🆕
│   ├── sourcebot-dev-sourcebot.md            # 🆕
│   ├── eosphoros-ai-DB-GPT.md                # 🆕 stage3 主推
│   ├── iflytek-skillhub.md                   # 🆕 stage3 主推
│   ├── Fission-AI-OpenSpec.md                # 🆕 E06 预告
│   ├── obra-superpowers.md                   # 🆕 E06 预告
│   ├── Johnson-Jia-ai-landing-tutorial.md    # 🆕 教程仓库
│   └── ... (共 25 张)
│
├── reports/                       # 原始视频解析报告（深度调研）
│   ├── 20260701_analysis.md
│   └── 20260706_analysis.md       # 🆕 E05 基础设施四件套
│
├── transcripts/                   # 视频转写原文
│   ├── 20260701.txt / .srt
│   └── 20260706.txt / .srt        # 🆕
│
├── stats/                         # ★ Star 数快照（趋势追踪）
│   ├── 20260701_stars.json
│   └── 20260706_stars.json        # 🆕
│
└── docs/                          # 仓库本身的元文档
    ├── CHANGELOG.md
    └── SKILL-rationale.md
```

## 📚 已收录项目（25 个，跨 2 期视频）

### 🆕 2026-07-06 期新增 9 个项目（E05 基础设施四件套 · Star 总计 42.1 万）

#### T1 - 千星+月增过万 / 协议层

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| obra/superpowers 🆕 | [obra/superpowers](projects/obra-superpowers.md) | 24.76 万 | E06 预告 · Skill 框架 |
| Fission-AI/OpenSpec 🆕 | [Fission-AI/OpenSpec](projects/Fission-AI-OpenSpec.md) | 5.90 万 | E06 预告 · SDD |
| abhigyanpatwari/GitNexus 🆕 | [abhigyanpatwari/GitNexus](projects/abhigyanpatwari-GitNexus.md) | 4.37 万 | 代码知识图谱 · 零服务器 |
| DeusData/codebase-memory-mcp ⭐ | [DeusData/codebase-memory-mcp](projects/DeusData-codebase-memory-mcp.md) | 2.72 万 | **stage3 主推** · 代码知识图谱 |
| AsyncFuncAI/deepwiki-open 🆕 | [AsyncFuncAI/deepwiki-open](projects/AsyncFuncAI-deepwiki-open.md) | 1.72 万 | 代码 wiki + RAG |
| eosphoros-ai/DB-GPT ⭐ | [eosphoros-ai/DB-GPT](projects/eosphoros-ai-DB-GPT.md) | 1.94 万 | **stage3 主推** · 业务 RAG |

#### T2 - 垂直领域明星

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| Johnson-Jia/ai-landing-tutorial 🆕 | [Johnson-Jia/ai-landing-tutorial](projects/Johnson-Jia-ai-landing-tutorial.md) | 1 | 教程仓库 · stage3.html |
| iflytek/skillhub ⭐ | [iflytek/skillhub](projects/iflytek-skillhub.md) | 3,774 | **stage3 主推** · Skill 仓库 |
| sourcebot-dev/sourcebot 🆕 | [sourcebot-dev/sourcebot](projects/sourcebot-dev-sourcebot.md) | 3,564 | 自托管代码搜索 |

### 2026-07-01 期已有项目（17 个，E04 全员赋能）

#### T1 - 协议层 / 顶级流量

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| Microsoft MarkItDown | [microsoft/markitdown](projects/microsoft-markitdown.md) | 16.2 万 | RAG |
| Anthropic Skills | [anthropics/skills](projects/anthropics-skills.md) | 15.7 万 | Agent 协议 |
| mattpocock/skills | [mattpocock/skills](projects/mattpocock-skills.md) | 15.4 万 | Agent 协议 |
| cc-switch | [farion1231/cc-switch](projects/farion1231-cc-switch.md) | 11.2 万 | 多账号 |
| Gemini CLI | [google-gemini/gemini-cli](projects/google-gemini-gemini-cli.md) | 10.6 万 | GCP |
| addyosmani/agent-skills | [addyosmani/agent-skills](projects/addyosmani-agent-skills.md) | 6.86 万 | Claude Code |
| Leonxlnx/taste-skill | [Leonxlnx/taste-skill](projects/Leonxlnx-taste-skill.md) | 5.5 万 | 前端设计 |
| MoneyPrinterTurbo | [harry0703/MoneyPrinterTurbo](projects/harry0703-MoneyPrinterTurbo.md) | 9.5 万 | 短视频 |

#### T2 - 垂直领域明星

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| Agent-Reach | [Panniantong/Agent-Reach](projects/Panniantong-Agent-Reach.md) | 4.9 万 | 跨平台 MCP |
| antigravity-skills | [sickn33/antigravity-awesome-skills](projects/sickn33-antigravity-awesome-skills.md) | 4.2 万 | Skills 资源 |
| OpenMontage | [calesthio/OpenMontage](projects/calesthio-OpenMontage.md) | 3.1 万 | 视频生产 |
| SuperMemory | [supermemoryai/supermemory](projects/supermemoryai-supermemory.md) | 2.8 万 | 长期记忆 |
| Mastra | [mastra-ai/mastra](projects/mastra-ai-mastra.md) | 2.6 万 | TS Agent |
| Cybersecurity Skills | [mukul975/Anthropic-Cybersecurity-Skills](projects/mukul975-Anthropic-Cybersecurity-Skills.md) | 2.4 万 | 安全审计 |
| InterviewStreet/hiring-agent | [InterviewStreet/hiring-agent](projects/InterviewStreet-hiring-agent.md) | 4.4k | HR 招聘 |

#### T3 - 基础设施 / 优化层

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| LLMLingua | [microsoft/LLMLingua](projects/microsoft-LLMLingua.md) | 6.4k | 成本压缩 |

## 🎬 已收录视频（2 期）

| 期数 | 日期 | 标题 | UP 主 | 报告 |
|------|------|------|------|------|
| E05 | 2026-07-06 | 给 AI 装上眼睛和记忆：基础设施四件套实操 | [GitHub星探](https://b23.tv/3bLMFxn) | [20260706_analysis.md](reports/20260706_analysis.md) |
| E04 | 2026-07-01 | 每日 github AI / Agent / Skills 热门项目速览 | [前端布洛芬](https://space.bilibili.com/79332967) | [20260701_analysis.md](reports/20260701_analysis.md) |

## 🎯 业务场景速查（14 个场景）

按需求场景找开源项目（按字母排序）：

| 场景 | 文档 | 推荐项目 |
|---|---|---|
| 🤖 Agent Coding / Claude Code | [topics/agent-coding.md](topics/agent-coding.md) | 7 个 |
| 🏢 业务知识 RAG 🆕 | [topics/business-rag.md](topics/business-rag.md) | 3 个 |
| 🔍 代码搜索 / 代码理解 | [topics/code-search.md](topics/code-search.md) | 1 个 |
| 🧠 代码知识图谱 🆕 | [topics/code-knowledge-graph.md](topics/code-knowledge-graph.md) | 4 个 |
| 🌐 跨平台 MCP | [topics/cross-platform-mcp.md](topics/cross-platform-mcp.md) | 4 个 |
| 🎨 前端设计 / Vibe Coding | [topics/frontend-design.md](topics/frontend-design.md) | 1 个 |
| ☁️ GCP / 企业级 | [topics/gcp-enterprise.md](topics/gcp-enterprise.md) | 2 个 |
| 👔 HR 招聘 / 简历评估 | [topics/hr-recruitment.md](topics/hr-recruitment.md) | 1 个 |
| 💰 LLM 成本优化 | [topics/llm-cost-optimization.md](topics/llm-cost-optimization.md) | 1 个 |
| 🧠 长期记忆 | [topics/long-term-memory.md](topics/long-term-memory.md) | 1 个 |
| 📄 RAG / 文档问答 | [topics/rag-document-qa.md](topics/rag-document-qa.md) | 2 个 |
| 🎬 短视频自动化 | [topics/short-video-automation.md](topics/short-video-automation.md) | 3 个 |
| 📚 团队 Skill 仓库 🆕 | [topics/team-skill-hub.md](topics/team-skill-hub.md) | 3 个 |
| 🔒 AI 安全审计 | [topics/ai-security-audit.md](topics/ai-security-audit.md) | 1 个 |

## 📊 项目热度趋势

每期视频解析都会在 [`stats/`](stats/) 留一份 star 快照。

```
20260701: MarkItDown 16.2万 → 20260706: codebase-memory-mcp 2.72万 ↑
                          (新登场的代码图谱项目)
```

## 🪛 解析流程（沉淀的可复用 skill）

完整流程封装为 `devops/bilibili-video-to-projects` skill，7 步：

1. b23.tv 短链 → 302 跳转拿 BV 号
2. WBI 签名调用 B 站 API
3. 下载音频流 → MP3
4. Whisper 转写 → 文本
5. 同音字纠错 + GitHub API 验证
6. 按场景分类生成项目卡片 + 场景索引
7. 写报告 + 提交

## 🔄 数据更新流程

新增一期视频时：

```bash
# 1. 用 skill 解析视频
bilibili-video-to-projects --url https://b23.tv/xxxxx

# 2. 把生成的 reports/ + transcripts/ + projects/ + stats/ 文件
#    按日期归档:
mv 20260708_analysis.md reports/
mv 20260708.txt 20260708.srt transcripts/
# (projects/ 直接合并)

# 3. 更新 README 表格 + stats/

# 4. 提交
git add . && git commit -m "📺 20260708 期: 新增 X 个项目"
git push
```

## 🆕 v0.2.2 增量（20260706 期）

**新增 9 个项目**（[BV1mGT96JERY](reports/20260706_analysis.md)）：

- 🎯 代码知识图谱：DeusData/codebase-memory-mcp（27k ⭐ stage3 主推）、abhigyanpatwari/GitNexus（44k ⭐）、AsyncFuncAI/deepwiki-open（17k ⭐）、sourcebot-dev/sourcebot（3.5k ⭐）
- 🎯 业务知识 RAG：eosphoros-ai/DB-GPT（19k ⭐ stage3 主推）
- 🎯 Skill 仓库：iflytek/skillhub（3.7k ⭐ stage3 主推，Apache 2.0）
- 🎯 E06 预告：Fission-AI/OpenSpec（59k ⭐）、obra/superpowers（248k ⭐）
- 📚 教程：Johnson-Jia/ai-landing-tutorial（stage3.html 教程）

**新增 3 个场景索引**：

- [business-rag.md](topics/business-rag.md) — 业务知识 RAG / 企业知识问答
- [code-knowledge-graph.md](topics/code-knowledge-graph.md) — 代码知识图谱 / 代码理解
- [team-skill-hub.md](topics/team-skill-hub.md) — 团队 Skill 仓库 / 能力沉淀

**更新现有项目**：

- [DeusData/codebase-memory-mcp](projects/DeusData-codebase-memory-mcp.md) — Star 数从 2.4 万 → 2.72 万，加入 stage3 主推定位

## 🤝 贡献

- 业务场景索引 (`topics/`) 欢迎补充新场景
- 项目卡片 (`projects/`) 欢迎修正 star 数/最佳实践
- 期数报告 (`reports/`) 欢迎补完

## 📜 License

MIT