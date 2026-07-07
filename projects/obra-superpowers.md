---
project: obra/superpowers
github: https://github.com/obra/superpowers
stars: 248390
license: MIT
language: Shell
created: 历史仓库(obra 个人项目)
category: ai-coding-workflow
tags: [agentic-skills, subagent-driven-development, sdlc, claude-code, codex, codex-cli, tdd, multi-agent-orchestration, code-review, spec-compliance]
analyzed: 2026-07-07
---

# obra/superpowers — Agentic Skills 框架 + 完整 SDLC 方法论

## 一句话定位
给现有 Coding Agent(Claude Code / Codex / Cursor / Pi / Antigravity 等)注入完整软件开发方法论 —— Brainstorm → Plan → TDD 实现 → 双面 Review → Whole-branch Review,完整 SDLC 纪律。

## 核心数据
- **Star**: 248,390 (GitHub Top 1%!)
- **Fork**: 22,031
- **License**: MIT
- **维护方**: Prime Radiant,创始人 Jesse Vincent
- **最新 release**: v6.1.1 (2026-07-02) — 紧跟 v6.0.0 (2026-06-16)
- **支持 harness**: Claude Code / Codex (App & CLI) / Cursor / Factory Droid / GitHub Copilot CLI / Kimi Code / OpenCode / Pi / Antigravity

## v6 三大核心改动

1. **Reviewer Handoff 改:脚本化确定性信息**
   - 旧的:Reviewer 自己跑大量 git 命令 → 占用 context
   - 新的:启动前脚本生成 review package(commit list + diff stat + 完整 diff)
   - 收益:~10% token & wall-clock 改善

2. **架构合并:两个 Reviewer → 一个 Task Reviewer**
   - 旧的:每个任务 2 个独立 reviewer(spec + quality)
   - 新的:单一 `task-reviewer-prompt.md`,一次 diff 同时返回两个 verdict
   - 收益:~15% token + 新增 "can-not-verify-from-diff" 状态防止 reviewer 偷偷补全局
   - release notes 同步删除 spec-reviewer-prompt.md 与 code-quality-reviewer-prompt.md

3. **强制每 dispatch 显式声明 model**
   - 否则继承 session 最贵模型,release notes 提到 "26 个 reviewer 全跑最高模型" 的惨案
   - 机械任务便宜模型、架构判断任务贵模型

## v6 实验证伪的"直觉"
- ❌ **Cap Controller thinking** → 反向爆炸,turns 92→138,输出翻倍
- ❌ **Plan Word Budget** → 测试信号 -62%
- ❌ **Sonnet 写 Plan** → 任务结构崩溃,Opus 平均 5.8 → Sonnet 3.6 任务数
- ✅ Narration Recipe = -54% reviewer 输出(每次省 $0.1-0.3,稳定小收益)
- ✅ Conditional Implementer Tiering = $0.5-1/run

## v6.1.x 增量亮点
- Visual Brainstorming Companion 加安全模型(per-session key,连接断开重启)
- 三个新 harness 支持(Kimi Code / Pi / Antigravity)
- worktrees 现在落地到项目里 `.worktrees/`,不再放 `~/.config/superpowers/worktrees/`

## 核心人物
- **Jesse Vincent (@obra)** — Berkeley, CA · Founder @ Prime Radiant · 个人 218 个公开仓库,obra/superpowers 475 个 commit
- **arittr** — 第二贡献者(79 commit)

## 评估套件
[prime-radiant-inc/superpowers-evals](https://github.com/prime-radiant-inc/superpowers-evals) ⭐ 69 — Quorum 系统,驱动 8 种 CLI 通过 Gauntlet QA agent 评测 workflow compliance。

## 适用场景
✅ 多文件功能开发 / 严格 TDD 要求的项目 / 团队一致性要求高
❌ 一次性小脚本 / 不需要 spec 设计的项目 / 对脑暴/计划流程没耐心的用户

## 5 分钟安装(Claude Code)
```bash
# 官方 marketplace
/plugin install superpowers@claude-plugins-official

# 或 Superpowers marketplace
/plugin marketplace add obra/superpowers-marketplace
/plugin install superpowers@superpowers-marketplace
```

## 视频定位
B站"为什么叫QQ"《Token 最高省 60% :Superpowers v6 真正优化了什么?》(BV1PAT16WEtv)— 从工程师视角深度拆解 v6 改动背后的工程逻辑,引用官方博客 + 25 个实验,适合作为 v6 设计哲学的入门视频。

## 注意事项
- ⚠️ v6 优化的"60% token / 50% wall-clock"是**作者 evals 范围**(Claude Code + Codex + 内部 benchmark),实际项目可能差异
- ⚠️ Plan 必须显著写清楚;如果你团队对脑暴没耐心,会被 Plan-driven 流程卡住
- ⚠️ Worktree 现在落地到项目里(`<project>/.worktrees/`),不是用户 home
- ⚠️ v6 删除了 spec-reviewer-prompt.md / code-quality-reviewer-prompt.md,老 dispatch 脚本需改成 task-reviewer-prompt.md
