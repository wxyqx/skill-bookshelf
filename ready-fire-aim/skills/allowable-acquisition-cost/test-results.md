# Test Results — allowable-acquisition-cost

## 统计

- 总用例数: 7
- 通过: 7
- 部分通过: 0
- 失败: 0
- 通过率: 100.0% (按 通过=1, 部分通过=0.5, 失败=0 计算)

## 详细结果

| id | type | 预期 | 盲测结果 | 是否通过 | 备注 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 调用 allowable-acquisition-cost，计算客户终身毛利，扣除 overhead 分摊和期望利润后得到 AAC，再用 AAC 评估各渠道预算... | yes | 通过 |  |
| should-trigger-02 | should_trigger | 调用 allowable-acquisition-cost，基于订阅周期、留存率、毛利率计算 Lifetime Gross Profit，推导 AAC，并明确首... | yes | 通过 |  |
| should-trigger-03 | should_trigger | 调用 allowable-acquisition-cost，用客户终身毛利倒推 AAC，明确 CAC ≤ AAC 的放量条件，以及 AAC ≤ 0 时的判停条件... | yes | 通过 |  |
| should-not-trigger-01 | should_not_trigger | 不应调用 allowable-acquisition-cost，应调用 front-end-back-end-marketing；用户问的是产品组合与客户终身价... | no | 通过 |  |
| should-not-trigger-02 | should_not_trigger | 不应调用 allowable-acquisition-cost，应调用 optimum-selling-strategy；用户需要先找到有效获客组合，再用 AA... | no | 通过 |  |
| should-not-trigger-03 | should_not_trigger | 不应调用 allowable-acquisition-cost，也不应调用本书任何 skill；这是个人税务计算，与获客成本无关。 | no | 通过 |  |
| edge-01 | edge_case | 不应鼓励用 AAC 做首次亏损获客；应说明没有复购/后端利润的一次性生意 AAC 基本为零或极低，首次销售必须盈利。 | no | 通过 | 预期不触发/边界停止 |

## 失败分析

无失败用例。

## 结论

- 本 skill 通过压力测试，可进入阶段 5。
