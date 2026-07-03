# 👔 HR 招聘 / 简历评估 场景

> 目标：自动化简历初筛 + JD 智能匹配 + 候选人评估报告

## 推荐方案

### 🏆 唯一推荐

**🎯 [InterviewStreet/hiring-agent](../../projects/InterviewStreet-hiring-agent.md)**

- **Star**：4.4k（周增 2,266，**热度极高**）
- **核心能力**：
  - 自动解析 PDF/Word 简历
  - 抽取技能、工作经历、项目亮点
  - 按 JD 智能匹配度评分
  - 输出结构化候选人报告（含优缺点分析）

## 使用场景

### 📋 场景 1：HR 简历初筛

```
HR 收到 500 份简历
  ↓
hiring-agent 自动解析每份简历
  ↓
提取关键技能: [Python, K8s, 5年经验, AWS认证, ...]
  ↓
对比 JD 要求: [Python, K8s, 3年+, GCP 优先]
  ↓
输出: 候选人 #127 匹配度 92% ✅ / #89 匹配度 31% ❌
  ↓
HR 只需看 top 50
```

### 🎯 场景 2：技术评估

```
候选人简历
  ↓
Agent 评估项目经验含金量:
  - 是否独立负责?
  - 技术栈深度?
  - 业务影响?
  ↓
输出: "候选人 A 有 2 个独立负责的 K8s 项目, 含金量高"
```

### 📊 场景 3：批量招聘决策

```
100 份简历 → hiring-agent
  ↓
50 份通过初筛
  ↓
10 份推荐面试 (高匹配度)
  ↓
3 份 offer (含优缺点分析)
  ↓
招聘周期从 4 周 → 1 周
```

## 实战代码

```bash
# 部署 hiring-agent
git clone https://github.com/InterviewStreet/hiring-agent
cd hiring-agent
pip install -r requirements.txt
python -m hiring_agent --resume resume.pdf --jd job_description.txt
```

输出示例：
```json
{
  "candidate": "张三",
  "match_score": 87,
  "skills_extracted": ["Python", "Kubernetes", "AWS", "PostgreSQL"],
  "strengths": [
    "5年 K8s 经验，独立负责过百万 QPS 系统",
    "AWS 认证 (Solutions Architect)",
    "开源贡献者 (CNCF 项目 200+ star)"
  ],
  "weaknesses": [
    "无 GCP 经验（JD 提到 GCP 优先）",
    "前端技能缺失（岗位需要全栈）"
  ],
  "recommendation": "推荐技术二面"
}
```

## 关联项目

- 🔗 [InterviewStreet/hiring-agent](../../projects/InterviewStreet-hiring-agent.md)

## 不要做的事

- ❌ 完全替代人工评估（AI 评估有偏差，关键岗位仍需人工）
- ❌ 用 AI 决策录用（AI 只是辅助，最终 HR 决策）
- ❌ 忽略偏见问题（历史数据偏差会被 AI 放大）

## 合规性

招聘场景涉及大量个人敏感信息，使用前注意：

- 📜 简历数据使用前需获得候选人授权
- 🔒 存储/传输加密（GDPR / 个保法）
- 🤖 评估算法需可解释（避免"算法歧视"质疑）