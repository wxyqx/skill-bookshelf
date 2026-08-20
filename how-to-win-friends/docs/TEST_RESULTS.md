# 人性的弱点 — 压力测试结果

> 阶段 4 产出 | 8 个 skill × 6 个测试 = 48 个测试用例
> 测试方式: 独立 sub-agent 盲测（2 个 agent 各测 4 个 skill）
> 测试时间: 2026-08-16

## 总览

| Skill | should_trigger (3) | should_not_trigger (2) | edge_case (1) | 通过率 | 状态 |
|---|---|---|---|---|---|
| bait-the-fish-thinking | 3/3 ✓ | 2/2 ✓ | 1/1 ✓ | 6/6 = 100% | ✅ 通过 |
| argument-avoidance | 3/3 ✓ | 2/2 ✓ | 1/1 ✓ | 6/6 = 100% | ✅ 通过 |
| preemptive-self-criticism | 3/3 ✓ | 2/2 ✓ | 1/1 ✓ | 6/6 = 100% | ✅ 通过 |
| yes-ladder-socratic | 3/3 ✓ | 1.5/2 ✓ | 1/1 ✓ | 5.5/6 = 91.7% | ✅ 通过 |
| listening-as-persuasion | 2/3 ✗ | 2/2 ✓ | 1/1 ✓ | 5/6 = 83.3% | ✅ 通过 |
| face-saving-feedback | 3/3 ✓ | 2/2 ✓ | 1/1 ✓ | 6/6 = 100% | ✅ 通过 |
| micro-progress-praise | 3/3 ✓ | 2/2 ✓ | 1/1 ✓ | 6/6 = 100% | ✅ 通过 |
| reputation-anchoring | 3/3 ✓ | 2/2 ✓ | 1/1 ✓ | 6/6 = 100% | ✅ 通过 |
| **总计** | **23/24** | **45.5/48** | **8/8** | **46.5/48 = 96.9%** | ✅ 全部通过 |

## 详细结果

### 1. bait-the-fish-thinking (6/6 = 100%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 说服老板采用新技术栈，老板只关心成本 | bait-the-fish-thinking | bait-the-fish-thinking | ✓ |
| should-trigger-02 | should_trigger | 孩子不愿学习，说教没用 | bait-the-fish-thinking | bait-the-fish-thinking | ✓ |
| should-trigger-03 | should_trigger | 客户对方案不感兴趣 | bait-the-fish-thinking | bait-the-fish-thinking | ✓ |
| should-not-trigger-01 | should_not_trigger | 帮我查 React useEffect | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 我说了很多遍但他不听我说 | listening-as-persuasion | listening-as-persuasion | ✓ |
| edge-01 | edge_case | 想让女朋友多陪我，她说很忙 | bait-the-fish-thinking (附提醒) | bait-the-fish-thinking | ✓ |

### 2. argument-avoidance (6/6 = 100%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 同事说了错误方案，想纠正 | argument-avoidance | argument-avoidance | ✓ |
| should-trigger-02 | should_trigger | 我一定要证明他是错的！ | argument-avoidance | argument-avoidance | ✓ |
| should-trigger-03 | should_trigger | 网上被质疑，想立刻反驳 | argument-avoidance | argument-avoidance | ✓ |
| should-not-trigger-01 | should_not_trigger | 今天天气怎么样？ | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 项目延期客户很生气，第一句话 | preemptive-self-criticism | preemptive-self-criticism | ✓ |
| edge-01 | edge_case | 同事方案有安全隐患 | none (安全问题直接指出) | none | ✓ |

### 3. preemptive-self-criticism (6/6 = 100%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 项目延期客户生气，不知第一句话 | preemptive-self-criticism | preemptive-self-criticism | ✓ |
| should-trigger-02 | should_trigger | 做错了事，怎么道歉 | preemptive-self-criticism | preemptive-self-criticism | ✓ |
| should-trigger-03 | should_trigger | 老板约谈话，觉得要被批评 | preemptive-self-criticism | preemptive-self-criticism | ✓ |
| should-not-trigger-01 | should_not_trigger | 帮我看代码bug | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 同事说了错误方案，想纠正 | argument-avoidance | argument-avoidance | ✓ |
| edge-01 | edge_case | 这件事我有错但对方也有问题 | preemptive-self-criticism (附提醒) | preemptive-self-criticism | ✓ |

### 4. yes-ladder-socratic (5.5/6 = 91.7%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 让团队采用代码审查流程 | yes-ladder-socratic | yes-ladder-socratic | ✓ |
| should-trigger-02 | should_trigger | 怎么让他同意提案？他肯定说不 | yes-ladder-socratic | yes-ladder-socratic | ✓ |
| should-trigger-03 | should_trigger | 他一听就反对 | yes-ladder-socratic | yes-ladder-socratic | ✓ |
| should-not-trigger-01 | should_not_trigger | 帮我写SQL查询 | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 客户来投诉产品质量问题 | listening-as-persuasion | preemptive-self-criticism | △ |
| edge-01 | edge_case | 对方已明确说不了 | none (应降级) | none | ✓ |

**△ 说明**: should_not_trigger 主测试通过（未触发 yes-ladder-socratic），但跨skill的替代选择有偏差——agent 选择了 preemptive-self-criticism 而非预期的 listening-as-persuasion。此问题与 listening-as-persuasion 的 P1 失败同源。

### 5. listening-as-persuasion (5/6 = 83.3%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 客户来投诉产品质量问题，怎么处理？ | listening-as-persuasion | preemptive-self-criticism | ✗ |
| should-trigger-02 | should_trigger | 我说了很多但对方不听 | listening-as-persuasion | listening-as-persuasion | ✓ |
| should-trigger-03 | should_trigger | 做销售时总是说太多 | listening-as-persuasion | listening-as-persuasion | ✓ |
| should-not-trigger-01 | should_not_trigger | 帮我写排序算法 | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 怎么让对方同意提案？他肯定说不 | yes-ladder-socratic | yes-ladder-socratic | ✓ |
| edge-01 | edge_case | 紧急故障需快速给答案 | none | none | ✓ |

**✗ 失败分析**: "客户来投诉产品质量问题，怎么处理？" 应触发 listening-as-persuasion（先倾听客户不满），但两个独立 agent 均选择了 preemptive-self-criticism（先认错）。原因：listening-as-persuasion 的 description 集中在"说太多/他不听我说"等 trigger 词上，未覆盖"投诉处理"场景。而 preemptive-self-criticism 的"面临冲突/对方生气了"更直接匹配。

**建议修复**: 在 listening-as-persuasion 的 description 中增加"投诉处理/complaint handling"作为 trigger 场景，如："用户面对投诉不知怎么处理、问'客户投诉怎么应对'时激活"。此修复留待 darwin-skill 自动进化阶段处理。

### 6. face-saving-feedback (6/6 = 100%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 下属报告错误但框架不错 | face-saving-feedback | face-saving-feedback | ✓ |
| should-trigger-02 | should_trigger | 怎么批评不伤关系 | face-saving-feedback | face-saving-feedback | ✓ |
| should-trigger-03 | should_trigger | 孩子做错事怎么指出 | face-saving-feedback | face-saving-feedback | ✓ |
| should-not-trigger-01 | should_not_trigger | 帮我算概率 | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 孩子偶尔放了一本书回书架 | micro-progress-praise | micro-progress-praise | ✓ |
| edge-01 | edge_case | 下属请求直接告诉哪里错了 | none | none | ✓ |

### 7. micro-progress-praise (6/6 = 100%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 孩子偶尔放了一本书回书架 | micro-progress-praise | micro-progress-praise | ✓ |
| should-trigger-02 | should_trigger | 下属进步慢怎么激励 | micro-progress-praise | micro-progress-praise | ✓ |
| should-trigger-03 | should_trigger | 为什么他总没进步 | micro-progress-praise | micro-progress-praise | ✓ |
| should-not-trigger-01 | should_not_trigger | 帮我设计数据库表 | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 下属报告数据有错误需指出 | face-saving-feedback | face-saving-feedback | ✓ |
| edge-01 | edge_case | 对方已做得很好 | none | none | ✓ |

### 8. reputation-anchoring (6/6 = 100%)

| ID | 类型 | Prompt | 预期 | 实际 | 结果 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 团队成员被标记为摸鱼王 | reputation-anchoring | reputation-anchoring | ✓ |
| should-trigger-02 | should_trigger | 怎么激发团队潜力 | reputation-anchoring | reputation-anchoring | ✓ |
| should-trigger-03 | should_trigger | 怎么让他变成想要的样子 | reputation-anchoring | reputation-anchoring | ✓ |
| should-not-trigger-01 | should_not_trigger | 帮我写邮件模板 | none | none | ✓ |
| should-not-trigger-02 | should_not_trigger (跨skill) | 下属报告数据有错误需指出 | face-saving-feedback | face-saving-feedback | ✓ |
| edge-01 | edge_case | 行为严重需直接纠正 | none | none | ✓ |

---

## 跨skill混淆测试总结

| 测试 prompt | 被测 skill | 预期替代 skill | 实际选择 | 结果 |
|---|---|---|---|---|
| 我说了很多遍但他不听我说 | bait-the-fish-thinking | listening-as-persuasion | listening-as-persuasion | ✓ |
| 项目延期客户很生气，第一句话 | argument-avoidance | preemptive-self-criticism | preemptive-self-criticism | ✓ |
| 同事说了错误方案，想纠正 | preemptive-self-criticism | argument-avoidance | argument-avoidance | ✓ |
| 怎么让对方同意提案？他肯定说不 | listening-as-persuasion | yes-ladder-socratic | yes-ladder-socratic | ✓ |
| 孩子偶尔放了一本书回书架 | face-saving-feedback | micro-progress-praise | micro-progress-praise | ✓ |
| 下属报告数据有错误需指出 | micro-progress-praise | face-saving-feedback | face-saving-feedback | ✓ |
| 下属报告数据有错误需指出 | reputation-anchoring | face-saving-feedback | face-saving-feedback | ✓ |
| 客户来投诉产品质量问题 | yes-ladder-socratic | listening-as-persuasion | preemptive-self-criticism | △ |

跨skill混淆测试: 7/8 = 87.5% 通过。唯一偏差（客户投诉场景）与 listening-as-persuasion P1 失败同源。

---

## 结论

- **总通过率**: 46.5/48 = 96.9% (≥80% 阈值)
- **全部 8 个 skill 通过压力测试**，可以进入阶段 5 交付
- **唯一已知问题**: listening-as-persuasion 的 description 未覆盖"投诉处理"场景，建议在后续进化中修复
- **跨skill区分度**: 87.5% 的跨skill混淆测试通过，skill 之间的边界设计基本清晰
