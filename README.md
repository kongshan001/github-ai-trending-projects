# 🎯 B 站开源项目情报库

> **目标**：从 B 站热门开源项目视频里提炼业务场景可用的工具，按场景快速检索

[![Stars](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Frepos%2Fkongshan001%2Fbilibili-trending-projects&query=%24.stargazers_count&label=stars)](https://github.com/kongshan001/bilibili-trending-projects)
[![Forks](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fapi.github.com%2Frepos%2Fkongshan001%2Fbilibili-trending-projects&query=%24.forks_count&label=forks)](https://github.com/kongshan001/bilibili-trending-projects)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 🚀 30 秒上手

**问：我有一个业务需求，怎么找开源项目？**

```bash
# 1. 打开 topics/ 找你的场景
cat topics/rag-document-qa.md        # 想做 RAG/文档问答
cat topics/short-video-automation.md  # 想做短视频自动化
cat topics/agent-coding.md           # 想搭 Claude Code 工作流
...

# 2. 找到项目名后看 projects/ 卡片
cat projects/microsoft-markitdown.md  # 项目详情 + 最佳实践

# 3. 看原始视频解析（深度调研）
cat reports/20260701_analysis.md
```

## 🗂️ 仓库结构

```
.
├── README.md                      # ← 你正在看
├── topics/                        # ★ 业务场景索引（按需检索）
│   ├── README.md                  # 场景总览
│   ├── rag-document-qa.md         # RAG / 文档问答
│   ├── short-video-automation.md  # 短视频自动化
│   ├── agent-coding.md            # Agent Coding / Claude Code
│   ├── ai-security-audit.md       # 安全审计 / 合规
│   ├── cross-platform-mcp.md      # 跨平台信息获取 (MCP)
│   ├── long-term-memory.md        # 长期记忆 / 知识沉淀
│   ├── llm-cost-optimization.md   # LLM 成本优化
│   ├── code-search.md             # 代码搜索
│   └── gcp-enterprise.md          # GCP / 企业级部署
│
├── projects/                      # ★ 项目卡片（每个项目一张）
│   ├── microsoft-markitdown.md
│   ├── harry0703-MoneyPrinterTurbo.md
│   ├── anthropics-skills.md
│   └── ... (共 14 张)
│
├── reports/                       # 原始视频解析报告（深度调研）
│   └── 20260701_analysis.md
│
├── transcripts/                   # 视频转写原文
│   ├── 20260701.txt
│   └── 20260701.srt
│
├── stats/                         # ★ Star 数快照（趋势追踪）
│   └── 20260701_stars.json
│
└── docs/                          # 仓库本身的元文档
    ├── CHANGELOG.md
    └── SKILL-rationale.md
```

## 📚 已收录项目（17 个，含 v0.2.1 补全 3 个）

### T1 - 协议层 / 顶级流量

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| Microsoft MarkItDown | [microsoft/markitdown](projects/microsoft-markitdown.md) | 16.2 万 | RAG |
| Anthropic Skills | [anthropics/skills](projects/anthropics-skills.md) | 15.7 万 | Agent 协议 |
| mattpocock/skills | [mattpocock/skills](projects/mattpocock-skills.md) | 15.4 万 | Agent 协议 |
| cc-switch | [farion1231/cc-switch](projects/farion1231-cc-switch.md) | 11.2 万 | 多账号 |
| Gemini CLI | [google-gemini/gemini-cli](projects/google-gemini-gemini-cli.md) | 10.6 万 | GCP |
| addyosmani/agent-skills 🆕 | [addyosmani/agent-skills](projects/addyosmani-agent-skills.md) | 6.86 万 | Claude Code |
| Leonxlnx/taste-skill 🆕 | [Leonxlnx/taste-skill](projects/Leonxlnx-taste-skill.md) | 5.5 万 | 前端设计 |
| MoneyPrinterTurbo | [harry0703/MoneyPrinterTurbo](projects/harry0703-MoneyPrinterTurbo.md) | 9.5 万 | 短视频 |

### T2 - 垂直领域明星

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| Agent-Reach | [Panniantong/Agent-Reach](projects/Panniantong-Agent-Reach.md) | 4.9 万 | 跨平台 MCP |
| antigravity-skills | [sickn33/antigravity-awesome-skills](projects/sickn33-antigravity-awesome-skills.md) | 4.2 万 | Skills 资源 |
| OpenMontage | [calesthio/OpenMontage](projects/calesthio-OpenMontage.md) | 3.1 万 | 视频生产 |
| SuperMemory | [supermemoryai/supermemory](projects/supermemoryai-supermemory.md) | 2.8 万 | 长期记忆 |
| Mastra | [mastra-ai/mastra](projects/mastra-ai-mastra.md) | 2.6 万 | TS Agent |
| Cybersecurity Skills | [mukul975/Anthropic-Cybersecurity-Skills](projects/mukul975-Anthropic-Cybersecurity-Skills.md) | 2.4 万 | 安全审计 |
| codebase-memory-mcp | [DeusData/codebase-memory-mcp](projects/DeusData-codebase-memory-mcp.md) | 2.4 万 | 代码搜索 |
| InterviewStreet/hiring-agent 🆕 | [InterviewStreet/hiring-agent](projects/InterviewStreet-hiring-agent.md) | 4.4k | HR 招聘 |

### T3 - 基础设施 / 优化层

| 项目 | 仓库 | Star | 场景 |
|------|------|------|------|
| LLMLingua | [microsoft/LLMLingua](projects/microsoft-LLMLingua.md) | 6.4k | 成本压缩 |

## 🎬 已收录视频

| 期数 | 日期 | 标题 | 报告 |
|------|------|------|------|
| 28 | 2026-07-01 | 每日 github AI / Agent / Skills 热门项目速览 | [20260701_analysis.md](reports/20260701_analysis.md) |

**视频源**：
- UP 主：[前端布洛芬](https://space.bilibili.com/79332967)
- 合集：[每日AI/Skills热门项目速览](https://www.bilibili.com/video/BV1puTi6tEoE)

## 📊 项目热度趋势

每期视频解析都会在 [`stats/`](stats/) 留一份 star 快照。未来可对比：

```
20260701: MarkItDown 16.2万 → 20260708: ? 万  (增长曲线)
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

## 🤝 贡献

- 业务场景索引 (`topics/`) 欢迎补充新场景
- 项目卡片 (`projects/`) 欢迎修正 star 数/最佳实践
- 期数报告 (`reports/`) 欢迎补完

## 📜 License

MIT