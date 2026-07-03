# 🌐 跨平台信息获取 (MCP) 场景

> 目标：让 Agent 像人一样跨平台读取信息（Twitter / Reddit / B 站 / 小红书等）

## 推荐组合

### 🏆 核心枢纽

**🎯 首选：[Panniantong/Agent-Reach](../../projects/Panniantong-Agent-Reach.md)**

- **覆盖**：6 平台（Twitter / Reddit / B 站 / 小红书等）
- **协议**：原生 MCP
- **优势**：
  - 零 API 费用
  - 国内环境友好（B 站/小红书直接读，无需 VPN）
  - Cookie 注入一次配置

### 🔌 配合：代码 MCP

[DeusData/codebase-memory-mcp](../../projects/DeusData-codebase-memory-mcp.md) - 158 种语言代码检索

### 🧠 配合：长期记忆 MCP

[supermemoryai/supermemory](../../projects/supermemoryai-supermemory.md) - 跨会话知识沉淀

### 💰 配合：成本压缩 MCP

[microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md) - MCP 模式起 server 自动压缩

## 统一协议：MCP

所有项目都遵循 MCP（Model Context Protocol）标准：

```
Claude Code / Cursor / Cline
  ↓
MCP 协议 (USB-C 式标准)
  ↓
┌─────────────┬──────────────┬─────────────┐
│ Agent-Reach │ codebase-mem │ supermemory │
│ (社交平台)  │ (代码)       │ (记忆)      │
└─────────────┴──────────────┴─────────────┘
```

**优势**：
- 一次接入，全平台通用
- 迁移 Agent 工具时无缝
- 不会被单一平台锁定

## 实战组合示例

```yaml
mcp_servers:
  agent-reach:        # 跨平台读 Twitter/Reddit/B 站
  codebase-memory:    # 读代码仓库
  supermemory:        # 写长期记忆
  llmlingua:          # 压上下文

# Agent 工作流:
# 调研阶段: agent-reach 拉社交平台热点
# 分析阶段: codebase-memory 检索相关代码
# 总结阶段: supermemory 沉淀进知识库
# 优化阶段: llmlingua 压缩长上下文
```

## 关联项目

- 🔗 [Panniantong/Agent-Reach](../../projects/Panniantong-Agent-Reach.md)
- 🔗 [DeusData/codebase-memory-mcp](../../projects/DeusData-codebase-memory-mcp.md)
- 🔗 [supermemoryai/supermemory](../../projects/supermemoryai-supermemory.md)
- 🔗 [microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md)