# 压力测试结果：identify-true-experts

- **测试日期**: 2026-08-20
- **测试方式**: 主流程自测（fallback）—— 当前环境无独立 sub-agent 盲测能力，结果可信度低于独立盲测。
- **测试用例数**: 9（4 should_trigger + 3 should_not_trigger + 2 edge_case）
- **通过数**: 9
- **失败数**: 0
- **通过率**: 100%

## 逐条判断

| ID | Type | Prompt | 预期 | 自测判断 | 理由 | 结果 |
|---|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 我要招一个资深数据科学家，怎么判断他真厉害还是只会写简历？ | 激活本 skill | 应触发 | 招聘中判断简历 vs 实力 | 通过 |
| should-trigger-02 | should_trigger | 这两位外科医生资历差不多，哪位手术水平更高？ | 激活本 skill | 应触发 | 求医时比较专家客观水平 | 通过 |
| should-trigger-03 | should_trigger | 怎么判断一个行业大V是不是真专家，而不是包装出来的？ | 激活本 skill | 应触发 | 识别自我宣传者 | 通过 |
| should-trigger-04 | should_trigger | 我想给孩子选一位钢琴老师，怎么验证老师的真实水平？ | 激活本 skill | 应触发 | 选导师/教练 | 通过 |
| should-not-trigger-01 | should_not_trigger | 请介绍一下某知名投资人的公开成就。 | 不触发 | 不触发 | 名人公开信息查询 | 通过 |
| should-not-trigger-02 | should_not_trigger | 我喜欢印象派画风，帮我推荐几位画家。 | 不触发 | 不触发 | 主观审美偏好 | 通过 |
| should-not-trigger-03 | should_not_trigger | 我想在公司内部培养销售高手，该设计什么样的仿真训练？ | 不触发，应走 workplace-deliberate-practice | 不触发 | 培养人而非判断/选择专家 | 通过 |
| edge-01 | edge_case | 我想选一位吉他老师，但这个领域没有统一考级，怎么判断？ | 触发但用近似方法 | 应触发 | 仍属专家选择，只是缺少统一指标 | 通过 |
| edge-02 | edge_case | 这位医生很有名，患者口碑也很好，是不是就可以直接认为他是专家？ | 触发并提醒验证 | 应触发 | 声望/口碑不能替代客观绩效，需要验证 | 通过 |

## 失败分析与修复建议

无失败。

## 备注

- 所有 should_not_trigger 均正确抑制，包括 1 条跨 skill 混淆（workplace-deliberate-practice）。
- 建议在具备 sub-agent 能力后重新跑一轮独立盲测，以验证本结果的稳健性。
