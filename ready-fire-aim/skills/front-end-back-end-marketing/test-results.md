# Test Results — front-end-back-end-marketing

## 统计

- 总用例数: 7
- 通过: 7
- 部分通过: 0
- 失败: 0
- 通过率: 100.0% (按 通过=1, 部分通过=0.5, 失败=0 计算)

## 详细结果

| id | type | 预期 | 盲测结果 | 是否通过 | 备注 |
|---|---|---|---|---|---|
| should-trigger-01 | should_trigger | 调用 front-end-back-end-marketing，盘点现有产品并划分前后端角色，设计前端获客品与后端盈利路径，并用 AAC 设定经济模型与测试漏斗... | yes | 通过 |  |
| should-trigger-02 | should_trigger | 调用 front-end-back-end-marketing，重新划分各产品在'获客'与'盈利'中的战略角色，设计整体 LTV 路径并调整考核方式。 | yes | 通过 |  |
| should-trigger-03 | should_trigger | 调用 front-end-back-end-marketing，设计前端获客品、后端利润品、upsell 触发点与最短转化路径，并测试整体 LTV:CAC。 | yes | 通过 |  |
| should-not-trigger-01 | should_not_trigger | 不应调用 front-end-back-end-marketing，应调用 marketing-four-legged-stool；用户问的是单一营销素材的创意... | no | 通过 |  |
| should-not-trigger-02 | should_not_trigger | 不应调用 front-end-back-end-marketing，应调用 allowable-acquisition-cost；用户问的是'可承受获客成本'的... | no | 通过 |  |
| should-not-trigger-03 | should_not_trigger | 不应调用 front-end-back-end-marketing，也不应调用本书任何 skill；这是工具推荐请求，与前后端营销框架无关。 | no | 通过 |  |
| edge-01 | edge_case | 不应调用 front-end-back-end-marketing；只有单一产品且没有第二款产品计划时，应先使用 OSS 或 AAC 优化首次销售，等产品矩阵形... | edge | 通过 | 边界处理一致 |

## 失败分析

无失败用例。

## 结论

- 本 skill 通过压力测试，可进入阶段 5。
