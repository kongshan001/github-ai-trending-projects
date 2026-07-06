# 🧠 代码知识图谱 / 代码理解场景

> 目标：用知识图谱替代纯字符串检索，让 AI 改代码前看到爆炸半径
> **来源**：BV1mGT96JERRY（E05 基础设施四件套 · stage3.html 主推）

## 核心理念

**为什么用图谱不用 RAG？**

| 维度 | 传统 RAG（多轮查询） | 代码知识图谱 |
|---|---|---|
| 上下文完整性 | LLM 发 4+ 次查询拼凑 | 索引期算好关系，一次调用拿全 |
| 可靠性 | LLM 漏掉上下文 | 工具响应塞满，不漏 |
| Token 消耗 | 高（~412k tokens / 5次查询） | 低（~3.4k tokens / 5次结构查询，**120x 节省**） |
| 模型依赖 | 强依赖顶级模型 | 解放小模型 |

**6 阶段索引管线**：扫描建索引 → Tree-sitter 解析符号 → 跨文件类型传播 → 社区发现画功能域 → 执行流追踪 → 提取业务概念

## 14 个 MCP 工具（三大类）

- **理解类**：`context`（看符号 360 度视图）
- **变更类**：`impact`（算爆炸半径）、`detect_changes`（把 diff 映射到受影响符号）
- **查询类**：自由筛选图谱查询，补足谱的盲区

## 🚨 两条铁律（必须写进 AI 指令）

- **铁律 1**：改任何符号前**必跑影响分析**（`impact`）
- **铁律 2**：提交前**必跑变更检查**（`detect_changes`）

> "这两条是基础设施能不能落地的命门"
>
> 实测：某团队累计排查 144 个生产 bug，覆盖率 80.4%

## 推荐组合

### 🏆 生产首选

**🎯 [DeusData/codebase-memory-mcp](../../projects/DeusData-codebase-memory-mcp.md)**

- **Star**：27,197（视频 stage3 主推）
- **支持语言**：158 种
- **核心能力**：
  - 极致索引速度：Linux 内核（28M LOC、75K 文件）**3 分钟**索引完
  - 14 个 MCP 工具（与视频描述完全吻合）
  - Hybrid LSP 语义类型解析（Python/TS/JS/PHP/C#/Go/C/C++/Java/Kotlin/Rust）
  - 单文件静态二进制 + 零依赖
  - 跨 11 个 Coding Agent 一键安装
  - arXiv 论文 2603.27277（83% 答案质量、10x 节省 token）

### 快速上手

**🎯 [abhigyanpatwari/GitNexus](../../projects/abhigyanpatwari-GitNexus.md)**（⭐43,682）

- **零服务器本地运行**
- 一键配置：
  ```bash
  npx gitnexus setup
  ```
- 适合不愿搭后端的快速试用

### 替代方案

| 项目 | Star | 定位 | 适合 |
|---|---|---|---|
| [AsyncFuncAI/deepwiki-open](../../projects/AsyncFuncAI-deepwiki-open.md) | 17,179 | 仓库→可交互 wiki + RAG | 文档自动化 |
| [sourcebot-dev/sourcebot](../../projects/sourcebot-dev-sourcebot.md) | 3,564 | 自托管代码搜索 + MCP | Sourcegraph 替代 |

## 何时用

- ✅ 大型代码仓库（百万行级）
- ✅ 跨仓库微服务
- ✅ AI Agent 需要跨项目理解代码
- ✅ 新人快速上手项目
- ❌ 单仓库几万行内（直接 grep 更快）
- ❌ 业务知识不算复杂（小团队跳过这套基础设施）

## 实战示例

```
开发者: "改一下 user_auth.verify() 的返回类型"
  → 旧：grep "user_auth"  →  找到 30 个调用点，全字符串匹配
       （不知道哪些是真调用，哪些只是注释/字符串）

  → 用 codebase-memory-mcp：
       Step 1: 跑 impact user_auth.verify → 列出 17 个真实调用点 + 调用方
       Step 2: 检测每个调用点的字段使用 → 6 个调用点用了 result.legacy_field
       Step 3: 跑 detect_changes → 把 diff 映射到 17 个调用点
       Step 4: 提交前再跑一遍 → 0 个遗漏
```

## 与传统工具对比

| 工具 | 检索方式 | 适合 |
|---|---|---|
| **codebase-memory-mcp** | 语义+图谱 | 大仓，跨项目 |
| **GitNexus** | 零服务器图谱 | 快速试用 |
| **deepwiki-open** | wiki + RAG | 文档自动化 |
| **sourcebot** | 自托管搜索 | Sourcegraph 替代 |
| Sourcegraph | 语义 | 企业级 |
| ripgrep | 字符串 | 简单查找 |

## 两条铁律的实现（必须写进 AI 指令）

```markdown
# CLAUDE.md / AGENTS.md 必备

## 代码变更规则（基础设施铁律）

### 改任何符号前必跑影响分析
\`\`\`
1. 明确要改的函数/类/接口
2. 跑 mcp__codebase-memory__impact --target=<symbol>
3. 查看返回的爆炸半径（受影响符号清单）
4. 在 PR 描述中记录影响范围
\`\`\`

### 提交前必跑变更检查
\`\`\`
1. 跑 mcp__codebase-memory__detect_changes --diff=<git_diff>
2. 确认所有受影响的符号都已处理
3. CI 阶段加 detect_changes 门槛（不通过则 merge 失败）
\`\`\`
```

## 推广路径

1. **试点**（3-5 个高频改动核心服务，量化"漏改率下降"）
2. **标准化**（AGENTS.md 模板 + CI 强制 detect_changes 门槛 + GUARDRAILS 失败模式沉淀）
3. **全员**（中心 MCP 网关 + SSO + 项目级权限）

## 常见坑

1. **过度工程**——小代码库也建全套基础设施（CLAUDE.md + grep 就够）
2. **全量重建而非增量**——上百项目扛不住 commit 级全量重建（必须文件级增量 + CI/夜间双轨刷新）
3. **N+1 跨库查询**——不做 sidecar 预聚合，高频查询每次开数百连接
4. **有图谱却跳过 impact 盲改**——等于白建，铁律是改前必跑影响分析
5. **什么都塞 MCP**——能用 CLI 的别用 MCP，工具定义常驻烧 token

## 关联项目

- 🔗 [DeusData/codebase-memory-mcp](../../projects/DeusData-codebase-memory-mcp.md) — **视频 stage3 主推**
- 🔗 [abhigyanpatwari/GitNexus](../../projects/abhigyanpatwari-GitNexus.md) — 零服务器快速上手
- 🔗 [AsyncFuncAI/deepwiki-open](../../projects/AsyncFuncAI-deepwiki-open.md) — wiki + RAG
- 🔗 [sourcebot-dev/sourcebot](../../projects/sourcebot-dev-sourcebot.md) — 自托管代码搜索
- 🔗 [Johnson-Jia/ai-landing-tutorial](../../projects/Johnson-Jia-ai-landing-tutorial.md) — stage3.html 教程
