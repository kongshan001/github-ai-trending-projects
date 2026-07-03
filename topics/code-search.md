# 🔍 代码搜索 / 代码理解 场景

> 目标：替代 grep，让 Agent 用语义理解代码

## 推荐方案

### 🏆 唯一推荐

**🎯 [DeusData/codebase-memory-mcp](../../projects/DeusData-codebase-memory-mcp.md)**

- **Star**：2.4 万（月增 1.6 万，热度高）
- **支持语言**：158 种
- **效果**：
  - Token 消耗减少 99%
  - 百万行代码秒级响应
  - 1 秒部署

## 何时用

- ✅ 大型代码仓库（百万行级）
- ✅ Agent 需要跨项目理解代码
- ✅ 新人快速上手项目
- ❌ 小项目（grep 反而更快）

## 部署

```bash
# MCP 一键接入
npx codebase-memory-mcp

# 然后 ~/.claude/settings.json
{
  "mcp_servers": {
    "codebase-memory": {
      "command": "npx",
      "args": ["codebase-memory-mcp"]
    }
  }
}
```

## 实战示例

```
开发者: "找一下所有调用用户认证接口的地方"

Agent (传统 grep):
  → grep -r "user_auth" → 50 个结果 → 全字符串匹配

Agent (codebase-memory-mcp):
  → 语义理解"用户认证" → 15 个相关调用点
  → 包含调用上下文（被谁调用、调用方是谁）
  → 输出可视化调用图
```

## 与传统工具对比

| 工具 | 检索方式 | 适合 |
|------|----------|------|
| **codebase-memory-mcp** | 语义+图谱 | 大仓，跨项目 |
| Sourcegraph | 语义 | 企业级 |
| Aider | 单文件 | 小项目 |
| ripgrep | 字符串 | 简单查找 |

## 关联项目

- 🔗 [DeusData/codebase-memory-mcp](../../projects/DeusData-codebase-memory-mcp.md)