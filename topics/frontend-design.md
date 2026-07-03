# 🎨 前端设计 / Vibe Coding 场景

> 目标：用 AI 生成高质量、有"设计品味"的 UI，而不是千篇一律的渐变色 + 圆角通用模板

## 推荐方案

### 🏆 唯一推荐

**🎯 [Leonxlnx/taste-skill](../../projects/Leonxlnx-taste-skill.md)**

- **Star**：5.5 万（月增 2.7 万，**增长爆发**）
- **核心价值**：赋予 AI Agent 前端设计品味，对抗 AI Slop
- **多平台兼容**：Claude Code / Cursor / Codex / Lovable / Bolt

## 使用场景

### 🎯 场景 1：vibe coding 加持

```
你在 Lovable / Bolt 里 vibe coding
  ↓
加载 taste-skill
  ↓
AI 输出不再"渐变 + 圆角 + emoji" 通用模板
  ↓
按成熟设计 token 生成有质感的 UI
```

### 🎯 场景 2：Claude Code 前端开发

```bash
# 安装
npx taste-skill

# Claude Code 自动加载
# 用户: "帮我做一个落地页"
# AI: 遵循 taste-skill 的设计 token, 输出有品味的页面
```

### 🎯 场景 3：Codex / Cursor

- Cursor：在 Settings → Features → Skills 安装
- Codex：在 `.codex/skills/` 目录加载

## 设计系统约束原理

```
通用 AI 输出（无 taste-skill）
  ↓
[蓝色渐变背景] [白色卡片] [圆角 16px] [通用 emoji]
  ↓
一眼 AI 生成的垃圾 (slop)

加载 taste-skill 后
  ↓
[遵循成熟设计 token] [合理间距] [有质感的排版]
  ↓
看起来像有经验的工程师设计的
```

## 关联项目

- 🔗 [Leonxlnx/taste-skill](../../projects/Leonxlnx-taste-skill.md)

## 与设计类 Skills 对比

| 项目 | 定位 | 适用 |
|------|------|------|
| **Leonxlnx/taste-skill** ⭐ | 通用设计品味 | 所有前端项目 |
| Owl-Listener/designer-skills | 设计资源集合 | 设计资产管理 |
| carmahhawwari/ui-design-brain | UI 组件知识 | Cursor 专属 |

## ⚠️ 注意

taste-skill 是**约束 AI 输出的风格指南**，不是 UI 组件库。安装后 AI 会按其设计哲学输出，但具体组件实现仍需前端框架（React/Vue）+ 组件库（shadcn/Material UI）支撑。