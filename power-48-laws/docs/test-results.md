# 《权力的48条法则》— 压力测试结果

> 测试时间: 2026-09-16
> 测试方式: 独立 sub-agent 盲测 (3 个 agent 各负责 5 个 skill)
> 总用例数: 90 (15 skill × 6 用例)
> 总通过率: **100%**

---

## 测试方法

每个 sub-agent 获得全部 15 个 skill 的 name + description 列表, 面对 30 条用户 prompt, 做"该激活哪一个 skill"的选择题。agent 不知道每条 prompt 的 type、expected_behavior 或 notes。

### 评判标准

- `should_trigger`: agent 应明确激活目标 skill
- `should_not_trigger` (诱饵): agent 不应激活被测 skill (容错为 0)
  - 诱饵分为两类: (1) 完全无关场景 → none; (2) 应触发同书其他 skill → 激活兄弟 skill
- `edge_case`: agent 的判断应合理(可触发可不触发, 但理由要清晰)

---

## 逐 skill 结果

### 1. indirect-approach (迂回前进艺术)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 1 | should_trigger | 提案被老板否了,让他接受同样想法 | indirect-approach | indirect-approach | ✅ |
| 2 | should_trigger | 想接近行业大佬但直连会被拒 | indirect-approach | indirect-approach | ✅ |
| 3 | should_trigger | 谈判中让对方自己得出有利结论 | indirect-approach | indirect-approach | ✅ |
| 4 | should_not_trigger | 想学沟通技巧提高表达能力 | none | none | ✅ |
| 5 | should_not_trigger | 怎么隐藏真实立场(跨skill) | conceal-intent | conceal-intent | ✅ |
| 6 | edge | 紧急情况老板让直接表态,迂回还是直接 | 边界合理 | none | ✅ |

通过率: 6/6 = 100%

---

### 2. emotion-mastery (情绪控制框架)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 7 | should_trigger | 同事会上公开指责,气得想反击 | emotion-mastery | emotion-mastery | ✅ |
| 8 | should_trigger | 知道有风险但因好感忽视 | emotion-mastery | emotion-mastery | ✅ |
| 9 | should_trigger | 关键时刻冷静不下来 | emotion-mastery | emotion-mastery | ✅ |
| 10 | should_not_trigger | 想提高情商改善人际关系 | none | none | ✅ |
| 11 | should_not_trigger | 开会时我该说多少(跨skill) | silence-power | silence-power | ✅ |
| 12 | edge | 家人做了让我愤怒的事,该用情绪控制吗 | 边界合理 | none(亲密关系排除) | ✅ |

通过率: 6/6 = 100%

---

### 3. conceal-intent (隐藏意图与烟幕策略)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 13 | should_trigger | 想跳槽但不想让同事和老板察觉 | conceal-intent | conceal-intent | ✅ |
| 14 | should_trigger | 谈判中怎么隐藏我的底线 | conceal-intent | conceal-intent | ✅ |
| 15 | should_trigger | 怎么让对手以为做A实际做B | conceal-intent | conceal-intent | ✅ |
| 16 | should_not_trigger | 想提高演讲说服力 | none | none | ✅ |
| 17 | should_not_trigger | 提案被否让他接受同样想法(跨skill) | indirect-approach | indirect-approach | ✅ |
| 18 | edge | 在亲密关系中可以隐藏意图吗 | 边界合理 | none(亲密关系排除) | ✅ |

通过率: 6/6 = 100%

---

### 4. silence-power (沉默威慑法)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 19 | should_trigger | 新团队leader怎么建立权威 | silence-power | silence-power | ✅ |
| 20 | should_trigger | 开会忍不住说太多怎么管住嘴 | silence-power | silence-power | ✅ |
| 21 | should_trigger | 谈判中怎么让对方先亮底牌 | silence-power | silence-power | ✅ |
| 22 | should_not_trigger | 想提高公开演讲能力 | none | none | ✅ |
| 23 | should_not_trigger | 同事会上指责我气得想反击(跨skill) | emotion-mastery | emotion-mastery | ✅ |
| 24 | edge | 老板问我直接问题,我该沉默吗 | 边界合理 | none(需明确表态) | ✅ |

通过率: 6/6 = 100%

---

### 5. reputation-strategy (声誉攻防法)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 25 | should_trigger | 刚加入新公司前90天怎么建立口碑 | reputation-strategy | reputation-strategy | ✅ |
| 26 | should_trigger | 有人在背后抹黑我怎么应对 | reputation-strategy | reputation-strategy | ✅ |
| 27 | should_trigger | 对手声望很高怎么削弱他 | reputation-strategy | reputation-strategy | ✅ |
| 28 | should_not_trigger | 想做个人品牌运营 | none | none | ✅ |
| 29 | should_not_trigger | 开会没人注意我(跨skill) | command-attention | command-attention | ✅ |
| 30 | edge | 产品有质量问题该用声誉策略掩盖吗 | 边界合理 | none(不可掩盖质量) | ✅ |

通过率: 6/6 = 100%

---

### 6. enemy-to-ally (化敌为友策略)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 31 | should_trigger | 跨部门stakeholder阻挠我怎么争取 | enemy-to-ally | enemy-to-ally | ✅ |
| 32 | should_trigger | 竞争对手考虑合作怎么开始 | enemy-to-ally | enemy-to-ally | ✅ |
| 33 | should_trigger | 发现朋友在背后搞我该重新评估吗 | enemy-to-ally | enemy-to-ally | ✅ |
| 34 | should_not_trigger | 想学人际交往技巧交更多朋友 | none | none | ✅ |
| 35 | should_not_trigger | 怎么看出新同事真实意图(跨skill) | people-reading | people-reading | ✅ |
| 36 | edge | 对方伤害过我但现在有诚意合作 | 边界合理 | enemy-to-ally(合理判断) | ✅ |

通过率: 6/6 = 100%

---

### 7. manage-superior (不盖过上司光芒)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 37 | should_trigger | 大项目全员称赞但上司态度微妙 | manage-superior | manage-superior | ✅ |
| 38 | should_trigger | 比上司能力强学历高怎么相处 | manage-superior | manage-superior | ✅ |
| 39 | should_trigger | 新老板好像不太喜欢我 | manage-superior | manage-superior | ✅ |
| 40 | should_not_trigger | 想学向上管理改善和老板关系 | none | none | ✅ |
| 41 | should_not_trigger | 开会说太多暴露信息(跨skill) | silence-power | silence-power | ✅ |
| 42 | edge | 上司明显在犯错我该盖过来纠正吗 | 边界合理 | none(非关系管理) | ✅ |

通过率: 6/6 = 100%

---

### 8. result-judgment (结果导向判断)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 43 | should_trigger | 同事好心帮但搞砸了该追究吗 | result-judgment | result-judgment | ✅ |
| 44 | should_trigger | 对手说他是善意的能信吗 | result-judgment | result-judgment | ✅ |
| 45 | should_trigger | 复盘失败合作纠结对方是不是故意 | result-judgment | result-judgment | ✅ |
| 46 | should_not_trigger | 想学批判性思维提高判断力 | none | none | ✅ |
| 47 | should_not_trigger | 合作代价太大该不该做(跨skill) | cost-assessment | cost-assessment | ✅ |
| 48 | edge | 家人出于好意但造成实际伤害 | 边界合理 | none(亲密关系排除) | ✅ |

通过率: 6/6 = 100%

---

### 9. patience-shield (耐心盾牌)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 49 | should_trigger | 被跳过两次晋升该跳槽还是再等 | patience-shield | patience-shield | ✅ |
| 50 | should_trigger | 等审批等得焦躁该催还是等 | patience-shield | patience-shield | ✅ |
| 51 | should_trigger | 计划没做好但忍不住想提前行动 | patience-shield | patience-shield | ✅ |
| 52 | should_not_trigger | 想学时间管理提高效率 | none | none | ✅ |
| 53 | should_not_trigger | 谈判处于弱势该示弱吗(跨skill) | strategic-surrender | strategic-surrender | ✅ |
| 54 | edge | 等待成本越来越高耐心还有意义吗 | 边界合理 | none(等待代价超标) | ✅ |

通过率: 6/6 = 100%

---

### 10. people-reading (研究他人与弱点识别)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 55 | should_trigger | 怎么看出新同事真实意图和弱点 | people-reading | people-reading | ✅ |
| 56 | should_trigger | 即将进入新团队如何了解权力格局 | people-reading | people-reading | ✅ |
| 57 | should_trigger | 我总看错人怎么提高识人能力 | people-reading | people-reading | ✅ |
| 58 | should_not_trigger | 想学心理学基础了解人性 | none | none | ✅ |
| 59 | should_not_trigger | 阻挠我的对手该怎么争取(跨skill) | enemy-to-ally | enemy-to-ally | ✅ |
| 60 | edge | 面对真诚待我的人还要研究吗 | 边界合理 | none(对方真诚) | ✅ |

通过率: 6/6 = 100%

---

### 11. strategic-surrender (示弱投降策略)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 61 | should_trigger | 谈判中对方明显强势怎么获得有利条件 | strategic-surrender | strategic-surrender | ✅ |
| 62 | should_trigger | 对手太强直接对抗会输怎么办 | strategic-surrender | strategic-surrender | ✅ |
| 63 | should_trigger | 怎么让对手低估我 | strategic-surrender | strategic-surrender | ✅ |
| 64 | should_not_trigger | 想学谦卑改善人际关系 | none | none | ✅ |
| 65 | should_not_trigger | 被跳过晋升该跳槽还是再等(跨skill) | patience-shield | patience-shield | ✅ |
| 66 | edge | 对方也在示弱我们都在演吗 | 边界合理 | detect-deception(合理判断) | ✅ |

通过率: 6/6 = 100%

---

### 12. detect-deception (天真伪装识别法)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 67 | should_trigger | 新同事总说自己不懂政治能信吗 | detect-deception | detect-deception | ✅ |
| 68 | should_trigger | 有人总站在道德高地发言是伪装吗 | detect-deception | detect-deception | ✅ |
| 69 | should_trigger | 这人看起来很天真总觉得哪里不对 | detect-deception | detect-deception | ✅ |
| 70 | should_not_trigger | 想学反诈骗技巧保护自己 | none | none | ✅ |
| 71 | should_not_trigger | 怎么看出新同事真实意图(跨skill) | people-reading | people-reading | ✅ |
| 72 | edge | 一个人确实谦虚但也获益了是伪装吗 | 边界合理 | detect-deception(合理判断) | ✅ |

通过率: 6/6 = 100%

---

### 13. command-attention (引人注目策略)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 73 | should_trigger | 部门最资历浅开会总被忽视 | command-attention | command-attention | ✅ |
| 74 | should_trigger | 产品上线了但没人关注 | command-attention | command-attention | ✅ |
| 75 | should_trigger | 害怕争议低调但发现正在被遗忘 | command-attention | command-attention | ✅ |
| 76 | should_not_trigger | 想学个人品牌营销推广产品 | none | none | ✅ |
| 77 | should_not_trigger | 前90天怎么建立口碑(跨skill) | reputation-strategy | reputation-strategy | ✅ |
| 78 | edge | 争议会损害专业形象该冒险吗 | 边界合理 | none(负面关注损害) | ✅ |

通过率: 6/6 = 100%

---

### 14. selective-honesty (选择性诚实缴械)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 79 | should_trigger | 需向客户承认产品缺陷怎么利用劣势 | selective-honesty | selective-honesty | ✅ |
| 80 | should_trigger | 谈判中怎么建立信任窗口 | selective-honesty | selective-honesty | ✅ |
| 81 | should_trigger | 怎么让人对我敞开心扉 | selective-honesty | selective-honesty | ✅ |
| 82 | should_not_trigger | 想学真诚沟通改善关系 | none | none | ✅ |
| 83 | should_not_trigger | 想跳槽但不让人知道真实意图(跨skill) | conceal-intent | conceal-intent | ✅ |
| 84 | edge | 承认缺陷后对方反而不信任了哪里出错 | 边界合理 | selective-honesty(合理判断) | ✅ |

通过率: 6/6 = 100%

---

### 15. cost-assessment (代价评估法)

| # | 类型 | prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| 85 | should_trigger | 有人邀我合伙创业零投资只需时间 | cost-assessment | cost-assessment | ✅ |
| 86 | should_trigger | 纠结该不该接受合作邀请 | cost-assessment | cost-assessment | ✅ |
| 87 | should_trigger | 做决策总看收益不看代价怎么改 | cost-assessment | cost-assessment | ✅ |
| 88 | should_not_trigger | 想学投资理财评估项目回报 | none | none | ✅ |
| 89 | should_not_trigger | 同事好心帮但搞砸了(跨skill) | result-judgment | result-judgment | ✅ |
| 90 | edge | 代价很高但收益也很高该做吗 | 边界合理 | cost-assessment(合理判断) | ✅ |

通过率: 6/6 = 100%

---

## 汇总

| Skill | should_trigger | should_not_trigger | edge_case | 总通过率 |
|---|---|---|---|---|
| indirect-approach | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| emotion-mastery | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| conceal-intent | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| silence-power | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| reputation-strategy | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| enemy-to-ally | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| manage-superior | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| result-judgment | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| patience-shield | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| people-reading | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| strategic-surrender | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| detect-deception | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| command-attention | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| selective-honesty | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| cost-assessment | 3/3 ✅ | 2/2 ✅ | 1/1 ✅ | 100% |
| **总计** | **45/45** | **30/30** | **15/15** | **100%** |

## 结论

全部 15 个 skill 通过压力测试, 通过率 100%, 无需回炉重做。跨 skill 混淆诱饵全部正确分流, 说明 description 字段的 trigger 条件设计精准, 兄弟 skill 之间区分度清晰。

**进入阶段 5 — 交付。**
