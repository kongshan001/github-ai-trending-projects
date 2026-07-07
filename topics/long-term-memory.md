# AI Agent 长期记忆 (long-term-memory)

## 一句话定位
给 AI Agent 装上跨会话的持久记忆,支持语义检索 + 关系推理 + 反馈进化。

## 推荐组合
**首选**: [cognee](https://github.com/topoteretes/cognee) — 完整认知层 + 免费图谱
**替代**: [mem0](https://github.com/mem0ai/mem0) — Star 数更高但图谱功能锁付费
**框架一体**: [letta](https://github.com/letta-ai/letta) — 有状态 Agent 平台(含记忆)

## 实战代码片段
```bash
# 安装 cognee
uv pip install cognee

# 配置 LLM
export LLM_API_KEY=sk-...

# 5 分钟体验四行 API
python -c "
import cognee, asyncio
async def m():
    await cognee.remember('Cognee turns documents into AI memory.')
    print(await cognee.recall('What does Cognee do?'))
asyncio.run(m())
"
```

## "不要做的事"清单
- ❌ 不要把 cognee 当成纯向量数据库用(cognee 优势在图谱推理)
- ❌ 不要在需要严格合规的场景用 mem0 免费版(图谱功能被锁)
- ❌ 不要在没有 Docker 的环境跑 cognee MCP Server
- ❌ 不要忘记配 LLM_API_KEY(否则直接报错)
- ❌ 不要忽略 `improve` API(没反馈循环 = 静态记忆 = 用不出 cognee 优势)

## 关联项目
- [topoteretes-cognee](../projects/topoteretes-cognee.md) — 主推
- [mem0ai-mem0](../projects/mem0ai-mem0.md) — 竞品(Star 数更高)
- [letta-ai-letta](../projects/letta-ai-letta.md) — 框架一体方案
- [milvus-io-milvus](../projects/milvus-io-milvus.md) — 纯向量基础设施
