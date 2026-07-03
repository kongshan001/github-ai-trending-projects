# 🎬 短视频自动化生产 场景

> 目标：从选题到成片全自动，支持 YouTube Shorts / TikTok / B 站 / 视频号

## 推荐组合（按规模选）

### 🟢 轻量级：单人自媒体

**🎯 首选：[harry0703/MoneyPrinterTurbo](../../projects/harry0703-MoneyPrinterTurbo.md)**

- 9.5 万 star，一条命令从选题到成片
- 支持国产模型（DeepSeek / 通义千问）
- 兼容 edge-tts 免费配音

**流程**：

```
选题 → MoneyPrinterTurbo → 自动文案 → 配图 → edge-tts 配音 → 字幕 → MP4
```

### 🟡 中量级：内容工作室

**🎯 升级方案：[calesthio/OpenMontage](../../projects/calesthio-OpenMontage.md)**

- 3.1 万 star，12 条流水线 + 52 个工具 + 500 个 Agent Skills
- AI Agents 自主决策剪辑方案
- 对标 Moovly / Descript 等付费 SaaS（免费）

### 🔵 高量级：MCN / 企业宣传

- MoneyPrinterTurbo 做单条（快）
- OpenMontage 做专辑/系列（精）
- 自建人工审核环节

## 工具组合建议

| 环节 | 推荐工具 |
|------|----------|
| 文案 | LLM (DeepSeek / GPT) |
| 配音 | edge-tts (免费 14 种中文) |
| 配图 | Pollinations / MoneyPrinterTurbo 内置 |
| 数字人 | MoneyPrinterTurbo 内置批量 |
| 字幕 | ffmpeg 烧录 / Whisper 反向生成 |
| 剪辑 | MoneyPrinterTurbo / OpenMontage |

## 国内场景注意点

- 避免海外模型 API（不稳定），用国产替代
- edge-tts 微软服务，国内访问偶发超时，建议加 retry
- 4K 输出对算力要求高，建议 1080p 起步

## 关联项目

- 🔗 [harry0703/MoneyPrinterTurbo](../../projects/harry0703-MoneyPrinterTurbo.md)
- 🔗 [calesthio/OpenMontage](../../projects/calesthio-OpenMontage.md)