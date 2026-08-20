# Test Results — unique-selling-proposition

## 统计

- 总用例数: 7
- 通过: 7
- 部分通过: 0
- 失败: 0
- 通过率: 100.0% (按 通过=1, 部分通过=0.5, 失败=0 计算)

## 详细结果

| id | type | 预期 | 盲测结果 | 是否通过 | 备注 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 调用 unique-selling-proposition，做特性→利益→深层欲望翻译，选择并验证 USP 三要素（看起来独特、有用、一句话能说清），并延展为营... | yes | 通过 |  |
| should-trigger-02 | should_trigger | 调用 unique-selling-proposition，从客户利益出发找出看起来独特且有用的角度，生成候选 USP/slogan 并设计快速测试。 | yes | 通过 |  |
| should-trigger-03 | should_trigger | 调用 unique-selling-proposition，在红海中找到'看起来独特、对客户有用、一句话能说清'的认知位置，避免直接拼功能和价格。 | yes | 通过 |  |
| should-not-trigger-01 | should_not_trigger | 不应调用 unique-selling-proposition，应调用 marketing-four-legged-stool；用户问的是单一营销活动的四脚凳结... | no | 通过 |  |
| should-not-trigger-02 | should_not_trigger | 不应调用 unique-selling-proposition，应调用 incremental-degradation；用户描述的是产品差异化随时间渐进退化，需... | no | 通过 |  |
| should-not-trigger-03 | should_not_trigger | 不应调用 unique-selling-proposition，也不应调用本书任何 skill；这是语言翻译请求，与定位无关。 | no | 通过 |  |
| edge-01 | edge_case | 不应调用 unique-selling-proposition；产品完全是大宗商品且唯一竞争手段是最低价时，应使用成本领先或价格策略，而非 USP。 | edge | 通过 | 边界处理一致 |

## 失败分析

无失败用例。

## 结论

- 本 skill 通过压力测试，可进入阶段 5。
