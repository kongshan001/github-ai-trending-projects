# 💰 LLM 成本优化 场景

> 目标：在不损失质量的前提下，压缩 token 用量，省钱

## 推荐方案

### 🏆 唯一推荐

**🎯 [microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md)**

- **效果**：提示压缩 60-95%
- **模式**：三种部署方式

| 模式 | 何时用 |
|------|--------|
| Python 库 | 单次脚本调用 |
| HTTP 代理 | 所有请求自动压缩 |
| **MCP Server** | Agent 生态自动获益 ⭐ |

## 实战：MCP 模式部署

```bash
# 起一个 LLMLingua MCP server
llmlingua-mcp --port 8000
```

```json
// 所有 Agent 配置
{
  "mcp_servers": {
    "llmlingua": {"url": "http://localhost:8000"}
  }
}
```

效果：Agent 喂给 LLM 前自动压缩，省一半成本

## 关键参数

```python
from llmlingua import PromptCompressor

compressor = PromptCompressor()
compressed = compressor.compress_prompt(
    context,
    target_token=500,          # 目标 token 数
    force_tokens=["专有名词", "API_key"],  # 必保留
    drop_consecutive=True      # 去重
)
```

## 关联项目

- 🔗 [microsoft/LLMLingua](../../projects/microsoft-LLMLingua.md)