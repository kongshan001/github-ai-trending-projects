# AI 编程工作流框架 (ai-coding-workflow)

## 一句话定位
给现有 Coding Agent(Claude Code / Codex / Cursor 等)注入完整软件开发方法论(spec / TDD / Review / Whole-branch)的方法论 + orchestration 层。

## 推荐组合

### 首选: [obra/superpowers](https://github.com/obra/superpowers) ⭐ 248,390
- 完整 SDLC 方法论:Brainstorm → Plan → SDD → Review → Finish
- 9 种 harness 全支持:Claude Code / Codex / Cursor / Pi / Antigravity 等
- 最新 v6.1.1 (2026-07-02),v6.0.0 主升级带来 ~50% 加速 + ~50% token 节省
- MIT License

### 评估套件: [prime-radiant-inc/superpowers-evals](https://github.com/prime-radiant-inc/superpowers-evals)
- Quorum 系统,驱动 8 种 CLI 通过 Gauntlet QA agent

## 实战安装

```bash
# Claude Code 官方 marketplace
/plugin install superpowers@claude-plugins-official

# 或 Superpowers marketplace
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

## "不要做的事"清单(来自 v6 25 个实验)

- ❌ **不要给 Controller 加 thinking 预算** — 反而让 turns 从 92 涨到 138
- ❌ **不要砍 Plan 字数** — 测试信号 -62%
- ❌ **不要用 Sonnet 写 Plan** — 任务结构从平均 5.8 任务 → 3.6 任务
- ❌ **不要让 Reviewer 重定义 spec 为 global constraints** — 要给 task brief
- ❌ **不要 dispatch 不写 model** — 不写会继承 session 最贵模型
- ❌ **不要让 Reviewer 自己跑大量 git** — 要用脚本生成 review package

## 关联项目
- [obra-superpowers](../projects/obra-superpowers.md) — 主推
- [prime-radiant-inc-superpowers-evals](../projects/prime-radiant-inc-superpowers-evals.md) — 评估套件
