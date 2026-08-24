# good-debt-bad-debt — 测试结果

> 本文件记录 `test-prompts.json` 的审查与测试结果。

## 测试状态

- [x] 静态审查：JSON 格式有效，结构符合 cangjie-skill 模板
- [ ] 运行时测试：待接入 darwin-skill / 真实对话触发验证

## 测试用例统计

| 类型 | 数量 | 最低要求 | 状态 |
|---|---|---|---|
| should_trigger | 3 | ≥ 3 | ✅ 通过 |
| should_not_trigger | 2 | ≥ 2 | ✅ 通过 |
| edge_case | 1 | ≥ 1 | ✅ 通过 |
| 跨 skill 混淆测试 | 2 | ≥ 1 | ✅ 通过 |

## 结果汇总

| 指标 | 数值 |
|---|---|
| JSON 有效性 | 有效 |
| 模板要求 | 满足 |
| 最低通过率 | 0.8 |
| 总用例数 | 6 |

## 用例明细

| ID | 类型 | Prompt 摘要 | 期望行为 |
|---|---|---|---|
| should-trigger-01 | should_trigger | 我有一套出租房在还贷款，每月租金覆盖月供后还有结余。这是良性债务吗？ | 应激活 good-debt-bad-debt，判定为正现金流覆盖本息的出租房贷款属于良性债务，并提示利率上升、空置等风险。 |
| should-trigger-02 | should_trigger | 我信用卡欠了5万，每月只还最低额，还借了消费贷去旅游。这些是不良债务吗？ | 应激活 good-debt-bad-debt，判定信用卡债和消费贷为不良债务，建议优先还清并改变消费行为。 |
| should-trigger-03 | should_trigger | 富爸爸说良性债务和不良债务怎么区分？我想借钱投资股票，算良性吗？ | 应激活 good-debt-bad-debt，解释区分标准，并评估股票融资的风险与现金流特征。 |
| should-not-trigger-01 | should_not_trigger | 我月薪两万，公司给了我两个offer，一个稳定但税高，一个创业合伙人但无底... | 不应激活 good-debt-bad-debt，因为问题核心是职业/象限选择，不是债务性质判断。 |
| should-not-trigger-02 | should_not_trigger | 我刚买了一套自住房，每月还房贷1万，这房子到底是资产还是负债？ | 不应激活 good-debt-bad-debt，应激活 asset-liability-filter，因为问题核心是房产的现金流方向定性。 |
| edge-01 | edge_case | 我生意需要贷款扩张，但现在市场环境不好，订单不稳定。这时候借钱是良性还是不良？ | 应激活 good-debt-bad-debt，但需说明债务性质取决于未来现金流的可预测性；在市场不确定时应保守，先稳住现金流再谈杠杆。 |

## 运行时测试说明

静态审查已确认 `test-prompts.json` 满足 cangjie-skill 质量红线：

1. 每个 skill 必须通过全部三重验证（在 `verified.md` 中完成）。
2. 每个 skill 必须有完整的 R / I / A1 / A2 / E / B 六段（在 `SKILL.md` 中完成）。
3. 原文引用 ≤150 字/段。
4. 每个 skill 必须有 `test-prompts.json`，且含诱饵测试（不应调用的场景），其中至少 1 条是同书兄弟 skill 的混淆场景。
5. `description` 字段已明确 trigger 条件。

运行时触发验证需要：

- 接入 darwin-skill 自动进化：`darwin evolve books/rich-dad-poor-dad-series/`
- 或在真实对话中手动复现各 `prompt`，确认 agent 路由到正确的 skill。

## 改进记录

| 版本 | 改动 | 测试时间 |
|---|---|---|
| 0.1.0 | 初始版本，静态审查通过 | 2026-08-23 |
