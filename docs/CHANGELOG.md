# 开发日志 (CHANGELOG)

本文件记录 bilibili-trending-projects 仓库的演进。

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