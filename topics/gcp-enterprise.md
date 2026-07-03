# ☁️ GCP / 企业级 Agent 部署 场景

> 目标：Google Cloud 生态 / 企业级 SLA / Vertex AI 用户

## 推荐组合

### 🚀 核心 Agent CLI

**🎯 [google-gemini/gemini-cli](../../projects/google-gemini-gemini-cli.md)**

- **Star**：10.6 万
- **生态**：Google 官方
- **优势**：
  - GCP 原生集成
  - SLA 保障
  - 支持 Vertex AI Agents Builder

### 🛠️ Agent 开发框架

**🎯 [mastra-ai/mastra](../../projects/mastra-ai-mastra.md)**

- **Star**：2.6 万
- **定位**：TypeScript 原生 Agent 框架
- **优势**：
  - Agent 优先范式
  - 内置工具调度、状态管理、记忆系统
  - 配合 Vercel AI SDK 一站式前端 Agent

## 何时用

- ✅ 你已经在 GCP 上跑业务
- ✅ 需要企业级 SLA 保障
- ✅ 团队以 TypeScript / Node.js 为主
- ✅ 想用 Vertex AI Agents Builder 全家桶

## 典型组合

```yaml
基础设施:
  - GCP Cloud Run / GKE (跑 Agent)
  - Vertex AI (LLM 推理)
  - Gemini CLI (Agent 编排)

开发框架:
  - Mastra (TS Agent 应用层)
  - Vercel AI SDK (Web 前端集成)

部署:
  - 内部 API 走 VPC
  - 外部 API 走 Apigee
```

## 与其他 Agent 框架对比

| 框架 | 语言 | 生态 | 适合 |
|------|------|------|------|
| **Mastra** | TypeScript | Vercel + GCP | Web/前端嵌入 |
| LangChain | Python | 全生态 | Python 为主 |
| AutoGen | Python | 微软 | 学术研究 |
| Gemini CLI | 多语言 | Google | GCP 重度 |

## 关联项目

- 🔗 [google-gemini/gemini-cli](../../projects/google-gemini-gemini-cli.md)
- 🔗 [mastra-ai/mastra](../../projects/mastra-ai-mastra.md)