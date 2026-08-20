# 压力测试结果：self-practice-3f-method

- **测试日期**: 2026-08-20
- **测试方式**: 主流程自测（fallback）—— 当前环境无独立 sub-agent 盲测能力，结果可信度低于独立盲测。
- **测试用例数**: 9（4 should_trigger + 3 should_not_trigger + 2 edge_case）
- **通过数**: 9
- **失败数**: 0
- **通过率**: 100%

## 逐条判断

| ID | Type | Prompt | 预期 | 自测判断 | 理由 | 结果 |
|---|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 没有老师教，我想自学插画，但不知道画完怎么判断好坏，该怎么练？ | 激活本 skill | 应触发 | 无导师+自学+需要自我反馈，符合 3F 场景 | 通过 |
| should-trigger-02 | should_trigger | 看编程视频很爽，一写就废，有没有办法自己获得反馈？ | 激活本 skill | 应触发 | 典型“一看就会一做就废”，需要 focus-feedback-fix | 通过 |
| should-trigger-03 | should_trigger | 我想自学日语口语，找不到语伴和导师，怎么自己练发音？ | 激活本 skill | 应触发 | 无导师且寻求自我训练方法 | 通过 |
| should-trigger-04 | should_trigger | 富兰克林那种自学写作的方法具体怎么做？ | 激活本 skill | 应触发 | 直接询问无导师自学方法 | 通过 |
| should-not-trigger-01 | should_not_trigger | 你能帮我查一下这个 API 的参数吗？ | 不触发 | 不触发 | 纯信息查询 | 通过 |
| should-not-trigger-02 | should_not_trigger | 我已经报了一个有真人教练每天批改的写作营，下一步该怎么练？ | 不触发 | 不触发 | 已有即时反馈导师，description 明确排除 | 通过 |
| should-not-trigger-03 | should_not_trigger | 我想系统提升公开演讲，该制定一个怎样的长期训练计划？ | 不触发，应走 design-deliberate-practice-plan | 不触发 | 用户要的是长期蓝图，不是单次执行循环 | 通过 |
| edge-01 | edge_case | 我找不到导师，但学的领域似乎也没有公认的高手样板，还能用3F法吗？ | 不触发或提示边界 | 不触发 | 没有可观察质量标准，3F 反馈环节失效 | 通过 |
| edge-02 | edge_case | 我想自学一个全新的小众 AI 工具，网上教程很少，也没有参考答案 | 触发但先设计反馈源 | 应触发 | 仍属无导师自学，但需要先补 feedback 源设计 | 通过 |

## 失败分析与修复建议

无失败。

## 备注

- 所有 should_not_trigger 均正确抑制，包括 1 条跨 skill 混淆（design-deliberate-practice-plan）。
- 建议在具备 sub-agent 能力后重新跑一轮独立盲测，以验证本结果的稳健性。
