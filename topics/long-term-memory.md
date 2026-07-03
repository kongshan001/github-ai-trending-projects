# 🧠 长期记忆 / 知识沉淀 场景

> 目标：解决 Agent "每次启动都失忆" 的核心痛点

## 推荐方案

### 🏆 唯一推荐

**🎯 [supermemoryai/supermemory](../../projects/supermemoryai-supermemory.md)**

- **Star**：2.8 万（月增 5,193，增长强劲）
- **架构**：知识图谱 + 向量检索双引擎
- **优势**：
  - 本地全量运行（数据主权）
  - 跨会话记忆持久化
  - 图谱+向量混合检索召回率高

## 何时需要

- ✅ Agent 每天多次启动，每次都要重新熟悉上下文
- ✅ 业务涉及大量客户/项目/文档历史
- ✅ 需要"沉淀型企业知识库"
- ❌ 单次任务（一次性 prompt）不需要

## 部署方式

### 本地优先（推荐）

```bash
# 部署到自己服务器
docker run -p 8080:8080 supermemoryai/supermemory
```

### MCP 模式（Agent 自动调用）

```json
// ~/.claude/settings.json
{
  "mcp_servers": {
    "supermemory": {
      "command": "npx",
      "args": ["-y", "@supermemory/mcp-server"]
    }
  }
}
```

## 与其他记忆方案的对比

| 方案 | 优势 | 劣势 |
|------|------|------|
| **supermemory** | 图谱+向量混合，本地化 | 项目较新 |
| mem0 | 成熟稳定 | 仅向量检索 |
| LangChain Memory | 集成度高 | 仅单会话 |
| 自建向量库 | 完全可控 | 工作量大 |

## 关联项目

- 🔗 [supermemoryai/supermemory](../../projects/supermemoryai-supermemory.md)