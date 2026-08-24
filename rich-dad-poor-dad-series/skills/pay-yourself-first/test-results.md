# pay-yourself-first — 测试结果

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
| should-trigger-01 | should_trigger | 我每个月工资到账就花光，想开始先支付自己，该怎么操作？ | 应激活 pay-yourself-first，建议开设独立投资账户、设置自动转账、确定固定比例。 |
| should-trigger-02 | should_trigger | 工资发了，信用卡账单也来了，我应该先还卡还是先存一笔投资？ | 应激活 pay-yourself-first，解释“先支付自己”的反向预算逻辑，并协调与不良债务的关系。 |
| should-trigger-03 | should_trigger | 我想设置工资自动转账到投资账户，比例多少合适？需要单独开账户吗？ | 应激活 pay-yourself-first，给出自动化机制与账户隔离建议。 |
| should-not-trigger-01 | should_not_trigger | 我手上有10万，想买指数基金还是银行股？哪个现金流更好？ | 不应激活 pay-yourself-first，因为问题核心是具体投资标的选择，而非收入分配纪律。 |
| should-not-trigger-02 | should_not_trigger | 我感觉自己一直在老鼠赛跑里，工资涨了但存款没涨，该怎么跳出来？ | 不应激活 pay-yourself-first，应激活 rat-race-detector，因为问题核心是诊断无资产循环。 |
| edge-01 | edge_case | 我信用卡欠了3万，每月利息很高，但我也想开始投资。这时还要先支付自己吗？ | 应激活 pay-yourself-first，但需说明高息不良债务应先消灭或并行处理：先还最低额+小额投资储蓄，而不是盲目先投资让债务滚雪球。 |

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
