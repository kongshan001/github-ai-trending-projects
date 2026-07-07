---
project: topoteretes/cognee
github: https://github.com/topoteretes/cognee
stars: 27258
license: Apache-2.0
language: Python
created: 2023-08-16
category: agent-memory
tags: [agent-memory, knowledge-graph, graph-rag, vector-database, mcp, cognitive-architecture]
analyzed: 2026-07-07
---

# cognee — 开源 AI Agent 持久记忆平台

## 一句话定位
把向量检索、知识图谱、认知科学融合成"AI Agent 记忆控制平面",四行 API 给 Agent 装上会自我进化的长期记忆。

## 核心数据
- **Star**: 27,258 (4 个月内从 18,800 增长 45%)
- **Fork**: 2,533
- **License**: Apache 2.0
- **最新 release**: v1.2.2.dev2 (2026-07-07)
- **Pip 下载**: 100万+ 月(从 2025 初 200 次增长 500 倍)

## 架构创新
- **ECL Pipeline**: Extract (38+ 数据源) → Cognify (自动本体推断) → Load (三层混合存储)
- **三层混合存储**: SQLite (元数据) / LanceDB (向量) / Kuzu+Neo4j (图)
- **认知科学基础**: 人类记忆模型 → 编码→存储→检索→遗忘四循环

## 核心 API
- `remember()` — 永久存入知识图谱
- `recall()` — 自动路由最优检索策略(混合模式准确率 92.5%)
- `forget()` — 精确删除(GDPR/HIPAA 合规)
- `improve()` — 反馈更新图边权重(记忆会进化)

## 企业级能力
- Agent 级租户物理隔离
- 全链路审计追溯(金融/医疗/法律刚需)
- OpenTelemetry 内置
- GitHub Secure Open Source Program 认证

## 集成生态
- Agent 框架: OpenAI Agents SDK / LangGraph / Google ADK
- 图数据库: Kuzu (默认本地) / Neo4j / Amazon Neptune
- 工作流: n8n 原生支持
- MCP: 标准协议(Claude Desktop/Cursor/Cline 可用)
- 客户端: TypeScript / Rust / Claude Code 插件 / OpenClaw 插件

## 适用场景
✅ 多会话长期记忆 Agent / 多租户 SaaS / 企业知识管理 / 法规严格行业
❌ 一次性 RAG / 没有 Agent / 极简检索

## 视频定位
B站"前端布洛芬"《cognee深度解析》(BV1m2TS66Eor) — 全方位科普型介绍,适合作为 cognee 入门视频

## 关键引用
- arXiv 论文: https://arxiv.org/abs/2505.24478 (Markovic et al., 2025)
- 创始人: Vasilije Markovic (CEO), Lazar Obradovic (CTO)
- 总部: Berlin Kreuzberg + San Francisco

## 注意事项
- 需 Docker 跑 MCP Server
- 默认 LLM Key 必须配置
- 默认分支是 `dev`,README 用 `main`
