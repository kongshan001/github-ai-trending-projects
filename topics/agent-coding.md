# 🤖 Agent Coding / Claude Code 场景

> 目标：搭建 Claude Code / Cursor / Cline 等 AI 编程助手的工作流

## 分层架构

```
协议层 (Skill 协议)
  ↓
运行时 (Claude Code + 多账号)
  ↓
增强层 (代码 MCP + 长期记忆)
  ↓
应用层 (具体项目 Skills)
```

## 各层推荐

### 📜 协议层

| 项目 | 仓库 | 适用 |
|------|------|------|
| **anthropics/skills** | [查看](../../projects/anthropics-skills.md) | 官方协议，所有 Agent 通用 |
| mattpocock/skills | [查看](../../projects/mattpocock-skills.md) | TypeScript 工程师派 |

### 🚀 运行时层

| 项目 | 仓库 | 适用 |
|------|------|------|
| **farion1231/cc-switch** | [查看](../../projects/farion1231-cc-switch.md) | 多账号并行 Claude Code |
| google-gemini/gemini-cli | [查看](../../projects/google-gemini-gemini-cli.md) | GCP 用户首选 |

### 🔌 增强层

| 项目 | 仓库 | 适用 |
|------|------|------|
| **DeusData/codebase-memory-mcp** | [查看](../../projects/DeusData-codebase-memory-mcp.md) | 百万行代码秒级检索 |
| supermemoryai/supermemory | [查看](../../projects/supermemoryai-supermemory.md) | 跨会话长期记忆 |
| microsoft/LLMLingua | [查看](../../projects/microsoft-LLMLingua.md) | 长上下文压缩 |

### 📦 资源层

| 项目 | 仓库 | 适用 |
|------|------|------|
| sickn33/antigravity-awesome-skills | [查看](../../projects/sickn33-antigravity-awesome-skills.md) | 1800+ Skills 集合 |
| mukul975/Anthropic-Cybersecurity-Skills | [查看](../../projects/mukul975-Anthropic-Cybersecurity-Skills.md) | 安全垂直 Skills |

## 推荐起步配置（个人开发者）

```yaml
# ~/.claude/settings.json
mcp_servers:
  codebase-memory:    # 代码检索
  supermemory:        # 长期记忆

# Skills 选择原则
skills_install:       # 不要超过 15 个
  - anthropic-official/core-3   # 官方核心
  - mattpocock/typescript-toolkit
  - 你的领域垂直包
```

## 推荐配置（团队）

```yaml
# 用 cc-switch 多账号
accounts:
  - alice@company.com   # 前端任务
  - bob@company.com     # 后端任务
  - ci@company.com      # CI/CD 自动审查

# 任务分发
task_routing:
  *.ts,*.tsx  → alice
  *.py        → bob
  *.yml,*.tf  → ci
```

## 不要做的事

- ❌ 全装 1800+ antigravity Skills（上下文污染）
- ❌ 不看官方直接抄社区版（质量参差）
- ❌ 跨平台不接 MCP（未来迁移成本高）

## 关联项目

- 🔗 [anthropics/skills](../../projects/anthropics-skills.md)
- 🔗 [mattpocock/skills](../../projects/mattpocock-skills.md)
- 🔗 [farion1231/cc-switch](../../projects/farion1231-cc-switch.md)
- 🔗 [google-gemini/gemini-cli](../../projects/google-gemini-gemini-cli.md)
- 🔗 [DeusData/codebase-memory-mcp](../../projects/DeusData-codebase-memory-mcp.md)
- 🔗 [supermemoryai/supermemory](../../projects/supermemoryai-supermemory.md)
- 🔗 [microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md)
- 🔗 [sickn33/antigravity-awesome-skills](../../projects/sickn33-antigravity-awesome-skills.md)