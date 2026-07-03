# 🔒 AI 安全审计 / 合规 场景

> 目标：用 Agent 自动按安全框架自查代码 / 渗透测试规划 / 合规审计

## 唯一推荐（视频里就是这个）

**🎯 首选：[mukul975/Anthropic-Cybersecurity-Skills](../../projects/mukul975-Anthropic-Cybersecurity-Skills.md)**

- **覆盖**：817 个网络安全技能
- **对应框架**：
  - MITRE ATT&CK（全战术库）
  - NIST CSF 2.0
  - OWASP Top 10
  - ISO 27001
  - CIS Controls
  - PCI DSS
- **规模**：29 个安全领域 × 20+ 平台
- **Star**：2.4 万（月增 1.1 万，热度极高）

## 使用场景

### 🛡️ 场景 1：Agent 代码自查

```
开发者提交 PR
  ↓
Agent 加载 cybersecurity-skills
  ↓
按 OWASP Top 10 / CWE 标准逐项审查
  ↓
输出风险报告 + 修复建议
```

### 📋 场景 2：合规审计

```
目标系统
  ↓
Agent 按 NIST CSF 2.0 框架扫描
  ↓
自动生成合规报告
  ↓
标注缺口项 + 整改优先级
```

### ⚔️ 场景 3：红蓝对抗规划

```
蓝队 Agent
  ↓
按 MITRE ATT&CK 战术库生成攻击剧本
  ↓
红队 Agent 执行
  ↓
蓝队 Agent 复盘 + 防御加固
```

## 关联项目

- 🔗 [mukul975/Anthropic-Cybersecurity-Skills](../../projects/mukul975-Anthropic-Cybersecurity-Skills.md)

## 未来趋势

预计未来 3-6 个月会出现更多垂直安全 Skills：

- 🏥 医疗 HIPAA Skills
- ⚖️ 法律合规 Skills
- 💰 金融风控 Skills
- 🎓 教育数据保护 Skills