# 📚 团队 Skill 仓库 / 能力沉淀场景

> 目标：把团队重复工作流沉淀成可复用 Skill，让"调走员工的 AI 经验"留在团队
> **来源**：BV1mGT96JERRY（E05 基础设施四件套 · stage3.html 重点）

## 核心理念

**留不住能力**——某个开发者很会用 AI，调走后经验跟着走。**Skill 仓库** = 把高频能力沉淀成团队资产。

## 两层架构 + RAG 联动（降 Token 关键）

| 层级 | 放什么 | 谁维护 |
|---|---|---|
| **公共 Skill** | 公司级通用能力：代码生成、自检查、测试用例生成、代码提交部署 | 架构组统一维护 |
| **项目级 Skill** | **只含 RAG 调用逻辑 + 项目专属规则**（编码规范、接口风格） | 项目负责人维护 |

**🔑 降 Token 关键**：业务数据**不塞进 Skill**，而是入 RAG 向量库按需检索。项目级 Skill 保持极轻（只有规则 + 检索逻辑）。

> "不必每次把整个项目知识塞进上下文——与代码图谱省 token、CLI 优于 MCP 省 token 是同一思路：**能检索/查证的就不盲读**"

## Skill 生命周期

```
AI 生成初始 → 人工审核（符合规范）→ 试点验证 → 持续优化 → 复用推广
                                       ↓
                                  与 RAG 数据更新保持同步
```

## 推荐组合

### 🏆 自托管平台首选

**🎯 [iflytek/skillhub](../../projects/iflytek-skillhub.md)**（⭐3,774，Apache 2.0）

- **定位**：自托管的私有智能体技能注册中心，专为内网/防火墙后部署设计
- **核心能力**：
  - 发布 + 语义化版本（beta/stable/latest 标签）
  - 团队命名空间（Owner/Admin/Member 角色 + 发布策略）
  - 审核与治理（命名空间审核 + 全局推广 + 审计日志）
  - 全文搜索 + 收藏/评分/下载量
  - CLI 优先（兼容 ClawHub 协议，一条命令装到 `~/.claude/skills`）
  - 安全扫描器（vetter 规则审核 Skill 安全性）
- **技术栈**：Java 21 + Spring Boot + React 19 + PostgreSQL，Docker Compose / K8s 一键部署

### 全球最大 Skills 框架

**🎯 [obra/superpowers](../../projects/obra-superpowers.md)**（⭐247,558）

- Agentic skills framework & software development methodology that works
- 行业事实标准
- 配套 stage3 Stage 路由表：
  | 阶段 | 调用技能 | 代码图谱工具 |
  |---|---|---|
  | Stage 1 需求探索 | superpowers:brainstorming | — |
  | Stage 3 计划拆分 | superpowers:writing-plans | impact, locate |
  | Stage 5 验证 | verification-before-completion | detect_changes |

### SDD 配套（E06 预告）

**🎯 [Fission-AI/OpenSpec](../../projects/Fission-AI-OpenSpec.md)**（⭐58,965）

- Spec-driven development (SDD) for AI coding assistants
- OpenSpec（规范）+ Superpowers（执行）= 阶段4 闭环

## 何时用

- ✅ 团队超过 10 人，需要能力沉淀
- ✅ 关键员工调走风险高（核心能力在 1-2 人手里）
- ✅ 多个项目需要复用相同流程（代码生成、部署、审查）
- ❌ 个人开发者（用 [anthropics/skills](../../projects/anthropics-skills.md) 官方 Skills 就够）
- ❌ 单一项目（项目级 Skill 即可，无需公共层）

## 一键安装示例

```bash
# iflytek/skillhub（兼容 ClawHub 协议）
clawhub install iflytek/skillhub

# obra/superpowers
git clone https://github.com/obra/superpowers ~/.claude/skills/superpowers

# Fission-AI/OpenSpec
npm install -g @fission-ai/openspec
```

## 设计原则

### ✅ DO

- **业务数据入 RAG**：项目结构、代码注释、功能描述 → RAG
- **Skill 保持极轻**：只有规则 + 检索逻辑
- **按阶段拆分**：每个阶段独立 .md，渐进式披露（每次只读当前阶段）
- **Hook 强制激活**：避免漏跑关键 Skill
- **定期审计**：整理废弃 Skill，避免上下文污染

### ❌ DON'T

- ❌ 把所有业务数据塞进 Skill（上下文爆炸）
- ❌ 全装 1800+ Skills（上下文污染）
- ❌ Skill 之间职责重叠（导致 AI 选错）
- ❌ 不写测试用例 Skill（质量参差）

## 推广路径

1. **试点**：1-2 个高频任务（如"代码审查"），看效果
2. **标准化**：统一 Skill 格式 + 命名规范
3. **治理**：架构组维护公共 Skill，项目负责人维护项目级 Skill
4. **度量**：使用率、成功率、调走员工的关键 Skill 迁移率

## 关联项目

- 🔗 [iflytek/skillhub](../../projects/iflytek-skillhub.md) — **视频 stage3 主推**
- 🔗 [obra/superpowers](../../projects/obra-superpowers.md) — 全球最大框架
- 🔗 [Fission-AI/OpenSpec](../../projects/Fission-AI-OpenSpec.md) — SDD 配套
- 🔗 [anthropics/skills](../../projects/anthropics-skills.md) — 官方协议
- 🔗 [mattpocock/skills](../../projects/mattpocock-skills.md) — TypeScript 工程师派
- 🔗 [Johnson-Jia/ai-landing-tutorial](../../projects/Johnson-Jia-ai-landing-tutorial.md) — stage3.html 教程
