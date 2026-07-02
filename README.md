# B 站热门开源项目视频解析笔记

> 从 B 站热门 GitHub 项目速览视频中提取项目价值与最佳实践，构建可复用的开源项目情报库。

## 系列说明

本仓库收录对 B 站「每日 GitHub AI / Agent / Skills 热门项目速览」系列视频的深度解析。每个视频对应一个分析报告。

## 已收录视频

| 期数 | 日期 | 标题 | 报告 |
|------|------|------|------|
| 28 | 2026-07-01 | 每日 github AI / Agent / Skills 热门项目速览 | [20260701_analysis.md](./20260701_analysis.md) |

## 视频源

- UP 主：[前端布洛芬](https://space.bilibili.com/79332967)（mid=79332967）
- 合集：[每日AI/Skills热门项目速览](https://www.bilibili.com/video/BV1puTi6tEoE)
- 视频源文件：本仓库 `transcripts/` 下

## 解析流程（可复用）

详见每个分析报告的"解析流程"章节。核心步骤：
1. b23.tv 短链 → 302 跳转拿 BV 号
2. WBI 签名调用 B 站 API
3. 下载音频流 → MP3
4. Whisper 转写 → 文本
5. 同音字纠错 + GitHub API 验证
6. 出报告

## 仓库结构

```
.
├── README.md                           # 本文件
├── 20260701_analysis.md                # 20260701 期解析报告
├── transcripts/
│   └── 20260701.txt                    # 视频原始转写文本
│   └── 20260701.srt                    # SRT 字幕
└── data/
    └── (分析用原始数据)
```

## 后续计划

- [ ] 把整套解析流程封装为 Hermes skill
- [ ] 持续追踪系列视频，构建项目热度趋势数据集
- [ ] 自动追踪 star 数变化，每周更新一次
