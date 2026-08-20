# 压力测试结果：workplace-deliberate-practice

- **测试日期**: 2026-08-20
- **测试方式**: 主流程自测（fallback）—— 当前环境无独立 sub-agent 盲测能力，结果可信度低于独立盲测。
- **测试用例数**: 9（4 should_trigger + 3 should_not_trigger + 2 edge_case）
- **通过数**: 9
- **失败数**: 0
- **通过率**: 100%

## 逐条判断

| ID | Type | Prompt | 预期 | 自测判断 | 理由 | 结果 |
|---|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 我们销售团队在客户会议上总是犯同样的错，有没有办法在内部先演练？ | 激活本 skill | 应触发 | 工作场景+团队技能+仿真演练需求 | 通过 |
| should-trigger-02 | should_trigger | 医生能不能通过仿真训练提高手术技能？ | 激活本 skill | 应触发 | 高风险职业仿真训练 | 通过 |
| should-trigger-03 | should_trigger | 我想把每周的复盘会从信息传递改成真正的技能演练，该怎么做？ | 激活本 skill | 应触发 | 把工作例会改造成练习—反馈循环 | 通过 |
| should-trigger-04 | should_trigger | 我们公司想建一个客服投诉处理案例库给员工练习。 | 激活本 skill | 应触发 | 组织内案例库+练习 | 通过 |
| should-not-trigger-01 | should_not_trigger | 我想自学吉他，每天下班后怎么安排练习？ | 不触发，应走 design-deliberate-practice-plan / self-practice-3f-method | 不触发 | 个人兴趣爱好，非工作场景 | 通过 |
| should-not-trigger-02 | should_not_trigger | 如何设计一门让学生结课后能独立完成项目的物理课？ | 不触发，应走 deliberate-practice-in-teaching | 不触发 | 课程/教学设计对象是学生 | 通过 |
| should-not-trigger-03 | should_not_trigger | 请帮我查一下销售行业的最新趋势报告。 | 不触发 | 不触发 | 行业信息查询 | 通过 |
| edge-01 | edge_case | 我是自由职业者，没有同事和团队，工作中还能做王牌训练吗？ | 不触发 | 不触发 | 缺少组织内反馈来源，应 redirect 到 3F 法 | 通过 |
| edge-02 | edge_case | 我们部门例会只有15分钟，根本不够做一次角色扮演，还能怎么练？ | 触发但微缩 | 应触发 | 仍属工作场景，但需压缩为微仿真 | 通过 |

## 失败分析与修复建议

无失败。

## 备注

- 所有 should_not_trigger 均正确抑制，包括 2 条跨 skill 混淆（self-practice-3f-method / deliberate-practice-in-teaching）。
- 建议在具备 sub-agent 能力后重新跑一轮独立盲测，以验证本结果的稳健性。
