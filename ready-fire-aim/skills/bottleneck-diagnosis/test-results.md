# Test Results — bottleneck-diagnosis

## 统计

- 总用例数: 7
- 通过: 7
- 部分通过: 0
- 失败: 0
- 通过率: 100.0% (按 通过=1, 部分通过=0.5, 失败=0 计算)

## 详细结果

| id | type | 预期 | 盲测结果 | 是否通过 | 备注 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 调用 bottleneck-diagnosis，执行一周时间审计并分类质控类工作，召开核心团队访谈收集'可停止/可授权'清单，制定授权标准与 30 天试行计划。 | yes | 通过 |  |
| should-trigger-02 | should_trigger | 调用 bottleneck-diagnosis，通过时间审计与团队访谈两条线交叉验证创始人是否为瓶颈，并给出具体授权路径。 | yes | 通过 |  |
| should-trigger-03 | should_trigger | 调用 bottleneck-diagnosis，帮助创始人识别可授权事项，区分'可完全授权''可授权但有复核点''不可授权'三类，并制定 30 天试行计划。 | yes | 通过 |  |
| should-not-trigger-01 | should_not_trigger | 不应调用 bottleneck-diagnosis，应调用 free-market-management；根因是部门政治与激励扭曲，不是创始人亲力亲为造成的速度... | no | 通过 |  |
| should-not-trigger-02 | should_not_trigger | 不应调用 bottleneck-diagnosis，应调用 four-stages-of-growth；用户需要先判断企业阶段，确认 Stage Three 后... | no | 通过 |  |
| should-not-trigger-03 | should_not_trigger | 不应调用 bottleneck-diagnosis；问题本质是下属执行力或能力问题，应先用招聘/培训/淘汰解决人问题，再谈授权。 | no | 通过 |  |
| edge-01 | edge_case | 不应调用 bottleneck-diagnosis；企业仍在婴儿期，创始人是唯一能做销售和产品的人，此时亲力亲为是必要的，不是瓶颈。 | edge | 通过 | 边界处理一致 |

## 失败分析

无失败用例。

## 结论

- 本 skill 通过压力测试，可进入阶段 5。
