# 开发日志 (CHANGELOG)

本文件记录 bilibili-trending-projects 仓库的演进。

---

## 2026-07-03 · v0.2.1 · 补全 3 个 Hub Skill 项目

**动机**：v0.2.0 重构时，原 v0.1.0 报告里有 10 个 Hub Skill 类项目被归类为"生态综述"未精确识别。本版本通过 GitHub API 精确搜索，把其中 **3 个项目** 补全出来。

### 🎯 补全项目

| 转写片段 | 真实仓库 | Star | 校验时间 |
|----------|----------|------|----------|
| `Adios Mani Agents skills 6.1 萬` | `addyosmani/agent-skills` | 6.86 万 | 2026-07-03 |
| `Leonxung Staste Steal 5.3 萬` | `Leonxlnx/taste-skill` | 5.5 万 | 2026-07-03 |
| `Interview Street Hiring Agents 4.020` | `InterviewStreet/hiring-agent` | 4,410 | 2026-07-03 |

### 📦 数据规模变化

- 项目卡片：14 → **17** 张
- 业务场景索引：9 → **11** 个（新增前端设计 + HR 招聘）
- T1 项目数：5 → **7** 个（addyosmani、Leonxlnx 都是千星月增过万）
- T2 项目数：6 → **7** 个（InterviewStreet 加入）

### 🪛 已踩的坑

| 现象 | 根因 | 解决方案 |
|------|------|----------|
| `stats/20260701_stars.json` 写入后 ID 冲突 | 重复 push 同一项目时 ID 未去重 | 写 stats 时按 `repo` 字段去重 |
| `patch` 工具误删"场景"行 | old_string 漏了一行 | 先 read_file 完整内容再 patch |

### 🔜 剩余未识别

仍有 7 个 Hub Skills 项目未识别（详见 `reports/20260701_analysis.md` 末尾 v0.2.1 章节），归类为生态综述：
- Whackley (NL→Shell)
- Bud Rover (代码库理解)
- self-improving agent (Prompt 工程)
- ATXP (Task tracker)
- Google Workspace 技能
- Agent Browser (浏览器 MCP)
- Samarice Summarize
- Gig Hub (GitHub MCP)
- Tallly Web Search

---

## 2026-07-03 · v0.2.0 · 重构：按业务场景检索

**动机**：原仓库是"一期一份分析报告"的扁平结构，无法快速回答"我想做 XX 业务场景，有哪些开源项目可用？"。本次重构新增三轨索引。

### 🎯 决策

1. **新增 `topics/` 业务场景索引目录**
   - 按"用户想做 XX → 哪些项目可用"的视角组织
   - 替代"按项目分类看场景"的旧逻辑
   - 9 个核心场景覆盖大部分 AI Agent 需求

2. **新增 `projects/` 项目卡片目录**
   - 每项目一张 Markdown 卡片，含标签/价值/场景/最佳实践/元数据
   - 未来跨期合并去重（比如 `anthropics/skills` 出现多期）
   - 文件名用 `owner-repo.md` 格式

3. **新增 `stats/` Star 数快照目录**
   - 每期 JSON 快照，未来对比热度趋势
   - 包含仓库地址、star 数值、增长、标签、梯队

4. **报告移到 `reports/` 子目录**
   - 原始分析报告（含 UP 主原话引用、趋势提炼）作为深度调研入口

### 📁 新结构

```
README.md                        ← 场景检索入口
topics/                          ★ 9 个业务场景索引
projects/                        ★ 14 个项目卡片
reports/                         ← 原始视频分析
transcripts/                     ← 视频转写原文
stats/                           ★ Star 数快照
```

### 🪛 已踩的坑

| 现象 | 根因 | 解决方案 |
|------|------|----------|
| `growth` 字段只截到 "3" | 正则 `[\d,]+` 不含 `.` | 改用 `[\d.]+` |
| 转写报告里 14 个项目有 1 个未识别（第 17-25 Hub Skills 表格形式） | 用了 `####` 而非 `####` 章节标题 | 表格形式保留原报告，本目录只覆盖 `####` 项目块 |

### 📦 数据规模

- 项目卡片：14 张（覆盖第 1-3 梯队）
- 场景索引：9 个（RAG/短视频/Agent Coding/安全/跨平台/记忆/成本/代码搜索/GCP）
- Star 快照：1 份（20260701）

### 🔜 下一步

- [ ] 多期合并时的项目去重逻辑
- [ ] 自动更新 Star 数（GitHub API 定时任务）
- [ ] 跨期趋势图（matplotlib → SVG 输出）
- [ ] 补全第 17-25 项 Hub Skills（去 GitHub 验证）
- [ ] `projects/` 卡片支持 `latest_star_count` 字段自动更新

---

## 2026-07-02 · v0.1.0 · 仓库创建 + 首期解析

**仓库**：https://github.com/kongshan001/bilibili-trending-projects

### 内容

- 解析 B 站 [BV1puTi6tEoE](https://www.bilibili.com/video/BV1puTi6tEoE)（UP：前端布洛芬，7m36s）
- 识别 15 个核心开源项目（14 个高置信 + 1 个生态综述）
- 输出 `20260701_analysis.md`（16KB 详细报告）
- 沉淀 skill：`devops/bilibili-video-to-projects`（7 步流程 + 10 个坑）

### 三大趋势提炼

1. **Agent Skills 标准化爆发**：`anthropics/skills` 15.7 万 star 是协议标志
2. **从通用到垂直 Skills**：cybersecurity-skills 817 个 skill 覆盖 6 大安全框架
3. **多平台生态扩张**：Agent-Reach + MCP 协议成为 USB-C 式标准