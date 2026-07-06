# iflytek/skillhub（科大讯飞 Skill 仓库平台）

> **仓库**：`iflytek/skillhub`
> **Star**：3,774
> **梯队**：T2 垂直领域明星
> **来源**：[20260706 期报告](../reports/20260706_analysis.md) · UP 主：GitHub星探

## 🏷️ 标签

- `Skill 仓库`
- `团队协作`
- `自托管`
- `Apache 2.0`
- `科大讯飞`

## 💎 核心价值

Self-hosted, open-source agent skill registry for enterprises — **视频 stage3.html 明确推荐的 Skill 仓库开源平台**。

## 📋 业务场景

- 团队 Skill 仓库私有化部署（防火墙后 / 内网）
- Skill 发布 + 语义化版本（beta/stable/latest 标签）
- 团队命名空间（Owner/Admin/Member 角色）
- Skill 审核与治理（命名空间审核 + 全局推广 + 审计日志）

## 🎯 最佳实践

- **技术栈**：Java 21 + Spring Boot + React 19 + PostgreSQL，Docker Compose / K8s 一键部署
- **CLI 优先**：兼容 ClawHub 协议，一条命令装到 `~/.claude/skills`
- **安全扫描器**：vetter 规则审核 Skill 安全性
- **Apache 2.0**：科大讯飞出品，放心商用

## 一键安装

```bash
# 兼容 ClawHub 协议，一条命令装到 ~/.claude/skills
clawhub install iflytek/skillhub
```

## 🔗 关联项目

- 🔗 [obra/superpowers](obra-superpowers.md) — 全球最大 Skills 框架（247k ⭐）
- 🔗 [anthropics/skills](../projects/anthropics-skills.md) — 官方协议
- 🔗 [Fission-AI/OpenSpec](Fission-AI-OpenSpec.md) — 与 Skill 编排的 SDD 工具

---

## 元数据

```yaml
repo: iflytek/skillhub
star_count: 3774
star_raw: "3,774"
growth: ""
first_seen: 20260706
source_video: BV1mGT96JERY
tags: ['skill-仓库', '团队协作', '自托管', 'apache-2.0', '科大讯飞']
```
