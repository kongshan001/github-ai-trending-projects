---
project: prime-radiant-inc/superpowers-evals
github: https://github.com/prime-radiant-inc/superpowers-evals
stars: 69
license: None (但 Subpath 引用 obra/superpowers 是 MIT)
category: eval-lab
tags: [eval, behavioral-testing, claude-code, codex, multi-agent, workflow-compliance]
analyzed: 2026-07-07
---

# prime-radiant-inc/superpowers-evals — Quorum 行为评估实验室

## 一句话定位
驱动 8 种 Coding Agent(Claude/Codex/Antigravity/Gemini/Kimi/OpenCode/Pi/Copilot)通过 Gauntlet QA agent,评测 SDLC workflow compliance。

## 核心数据
- **Star**: 69
- **License**: None(组件级见 obra/superpowers MIT)
- **角色**: 行为评估实验室,非通用 benchmark
- **核心 CLI**: `quorum`(小写,代码/CLI/路径都用小写;`Quorum` 仅用于标题和演员表)

## 评估维度
- skill triggering(被触发的 skills)
- worktree 行为
- subagent 协调
- 验证反射
- review 质量
- 成本控制模式(cost-shaping patterns)

## 关键安全设计
- **每种 Agent 的 HOME 临时改到一次性 `$QUORUM_HOME_ENV`**,host 的 `~/.claude` 等不被污染
- 静态检查(biome/tsc/bun test)安全可跑公开 CI
- Live eval(trusted-maintainer only): 使用 `--dangerously-skip-permissions` 类危险开关

## 支持的 Coding Agent CLI
- Claude (`--dangerously-skip-permissions`)
- Codex (`--dangerously-bypass-approvals-and-sandbox`)
- Antigravity (`--dangerously-skip-permissions`)
- Gemini (`--skip-trust --approval-mode=yolo`)
- Kimi (`--yolo`)
- OpenCode (`--dangerously-skip-permissions`)
- Pi (工具白名单 + API-key 认证)
- Copilot (`--allow-all`)

## 用途
不是给最终用户用的,而是给 Superpowers 维护者量化"每一次改动对各 harness 的影响"。

## 关联
- [obra-superpowers](../projects/obra-superpowers.md) — 主项目
- [Superpowers v6 博客](https://primeradiant.com/blog/2026/superpowers-6.html) — 25 个实验记录见 docs/experiments/2026-06-11-build-loop-autoresearch.md
