# 压力测试结果：build-mental-representation

- **测试日期**: 2026-08-20
- **测试方式**: 主流程自测（fallback）—— 当前环境无独立 sub-agent 盲测能力，结果可信度低于独立盲测。
- **测试用例数**: 9（4 should_trigger + 3 should_not_trigger + 2 edge_case）
- **通过数**: 9
- **失败数**: 0
- **通过率**: 100%

## 逐条判断

| ID | Type | Prompt | 预期 | 自测判断 | 理由 | 结果 |
|---|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 我背了很多英语单词，但阅读时还是看不懂长句，感觉只能死记硬背，怎么建立心理表征？ | 激活本 skill | 应触发 | 死记硬背+建立心理表征，直接命中 description | 通过 |
| should-trigger-02 | should_trigger | 围棋高手是怎么一眼看出棋局大势的？我也想学会这种判断。 | 激活本 skill | 应触发 | 想理解高手快速判断与预测 | 通过 |
| should-trigger-03 | should_trigger | 学了那么多设计原则，一到做项目就懵，好像不会用。 | 激活本 skill | 应触发 | 知识多但不会迁移，需要构建模式 | 通过 |
| should-trigger-04 | should_trigger | 我想训练团队的新人，让他们像资深工程师一样快速定位 bug，该怎么设计？ | 激活本 skill | 应触发 | 把零散经验转化为可调用的专家模式 | 通过 |
| should-not-trigger-01 | should_not_trigger | 请解释一下什么是刻意练习。 | 不触发 | 不触发 | 纯概念查询 | 通过 |
| should-not-trigger-02 | should_not_trigger | 我想在三个月内学会弹吉他，该怎么安排练习时间？ | 不触发，应走 design-deliberate-practice-plan | 不触发 | 要计划/时间表，不是表征构建 | 通过 |
| should-not-trigger-03 | should_not_trigger | 我每天都在背50个单词，是不是练习量还不够？ | 不触发 | 不触发 | 只关注练习量，description 排除单纯增量 | 通过 |
| edge-01 | edge_case | 高手说的'语感'是不是就是心理表征？ | 触发但不止于定义 | 应触发 | 包含关键触发词“心理表征”，可借机引导构建 | 通过 |
| edge-02 | edge_case | 我已经能稳定完成中级编程题，但想提速，是不是该继续大量刷题？ | 不触发 | 不触发 | 已稳定正确，只是增量/提速，非表征构建 | 通过 |

## 失败分析与修复建议

无失败。

## 备注

- 所有 should_not_trigger 均正确抑制，包括 1 条跨 skill 混淆（design-deliberate-practice-plan）。
- 建议在具备 sub-agent 能力后重新跑一轮独立盲测，以验证本结果的稳健性。
