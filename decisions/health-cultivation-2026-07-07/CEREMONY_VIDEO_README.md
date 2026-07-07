# 「道途」突破视频生成器 — 2026-07-07 v0.3.0

## 是什么
为"境界突破"瞬间自动生成 30 秒 1920x1080 竖屏可分享短视频。

## 5 个境界视频都齐了
- foundation_breakthrough.mp4 (筑基·一念清明)
- golden_core_breakthrough.mp4 (金丹·神识初成)
- nascent_soul_breakthrough.mp4 (元婴·阴神出窍)
- divine_spirit_breakthrough.mp4 (化神·通达神明)
- tribulation_breakthrough.mp4 (渡劫·九霄雷音)

每个 10.3 秒,3.3 MB。

## 怎么用
1. 浏览器打开 http://localhost:8765
2. 修为攒到境界阈值后,会弹"恭喜道友,XXX已突破"
3. 点 "🎬 分享突破时刻(30 秒视频)" 按钮
4. 30 秒后(轮询),视频下载链接出现
5. 下载即可发到 B 站/小红书/朋友圈

## 后台命令(直接重新生成)
```bash
cd /root/health-cultivation-simulator
python3 ceremony_video.py foundation  # 筑基
python3 ceremony_video.py golden_core # 金丹
python3 ceremony_video.py nascent_soul # 元婴
python3 ceremony_video.py divine_spirit # 化神
python3 ceremony_video.py tribulation # 渡劫
```

## 复用现有工具链
完全复用 **ai-video-pipeline/pipeline.py** 的 4 步函数:
- step1_generate_images: Pollinations 生图
- step2_generate_audio: edge-tts 配音(女声 zh-CN-XiaoyiNeural)
- step3_compose_clips: ffmpeg + zoompan + fade
- step4_merge_video: 拼接 + 字幕烧录

零成本,无需任何额外服务。
