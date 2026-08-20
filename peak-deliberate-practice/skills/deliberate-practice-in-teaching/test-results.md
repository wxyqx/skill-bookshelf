# 压力测试结果：deliberate-practice-in-teaching

- **测试日期**: 2026-08-20
- **测试方式**: 主流程自测（fallback）—— 当前环境无独立 sub-agent 盲测能力，结果可信度低于独立盲测。
- **测试用例数**: 9（4 should_trigger + 3 should_not_trigger + 2 edge_case）
- **通过数**: 9
- **失败数**: 0
- **通过率**: 100%

## 逐条判断

| ID | Type | Prompt | 预期 | 自测判断 | 理由 | 结果 |
|---|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 我设计的编程课学生能听懂语法，但不会写项目，课程结构该怎么改？ | 激活本 skill | 应触发 | 学生听懂但不会用，description 核心场景 | 通过 |
| should-trigger-02 | should_trigger | 如何把一门传统讲授式物理课改成刻意练习式教学？ | 激活本 skill | 应触发 | 改造讲授式课堂 | 通过 |
| should-trigger-03 | should_trigger | 我想设计一个训练营，让学生结课后能独立完成真实产品，该怎么做？ | 激活本 skill | 应触发 | 以可观察技能为终点的课程设计 | 通过 |
| should-trigger-04 | should_trigger | 翻转课堂上学生只讨论不思考，缺少有效反馈，怎么升级？ | 激活本 skill | 应触发 | 改进主动学习形式 | 通过 |
| should-not-trigger-01 | should_not_trigger | 请给我推荐几本适合初学者的Python书。 | 不触发 | 不触发 | 资源推荐 | 通过 |
| should-not-trigger-02 | should_not_trigger | 我们销售团队想提升客户演示能力，能在公司内部怎么训练？ | 不触发，应走 workplace-deliberate-practice | 不触发 | 工作场景员工训练，非课程设计 | 通过 |
| should-not-trigger-03 | should_not_trigger | 我想为自己制定一个三个月学摄影的计划。 | 不触发，应走 design-deliberate-practice-plan | 不触发 | 个人学习计划 | 通过 |
| edge-01 | edge_case | 我想做一门纯知识普及课，没有技能产出，需要刻意练习式设计吗？ | 不触发 | 不触发 | 纯知识普及，description 明确排除 | 通过 |
| edge-02 | edge_case | 一个200人的大班课，是否还能用这个项目式学习的方法？ | 触发但提示限制 | 应触发 | 仍属教学设计，但需说明反馈资源限制 | 通过 |

## 失败分析与修复建议

无失败。

## 备注

- 所有 should_not_trigger 均正确抑制，包括 2 条跨 skill 混淆（workplace-deliberate-practice / design-deliberate-practice-plan）。
- 建议在具备 sub-agent 能力后重新跑一轮独立盲测，以验证本结果的稳健性。
