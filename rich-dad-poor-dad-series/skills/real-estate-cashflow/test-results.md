# real-estate-cashflow — 测试结果

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
| 跨 skill 混淆测试 | 1 | ≥ 1 | ✅ 通过 |

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
| should-trigger-01 | should_trigger | 这套房买来出租，现金流怎么算？ | 应激活 real-estate-cashflow，并引导用户计算租金、空置、费用、月供、净现金流。 |
| should-trigger-02 | should_trigger | 房地产投资怎么判断正现金流？租售比多少才算合格？ | 应激活 real-estate-cashflow，解释正现金流标准、现金回报率与压力测试。 |
| should-trigger-03 | should_trigger | How do I analyze rental property cash... | 应激活 real-estate-cashflow，用英文说明现金流分析步骤。 |
| should-not-trigger-01 | should_not_trigger | 买自住房要不要提前还贷款？ | 不应激活本 skill，因为自住房不产生租金现金流，属于负债/资产配置问题。 |
| should-not-trigger-02 | should_not_trigger | 怎么用信用卡首付买房？ | 不应激活本 skill，应激活 opm-opt-leverage。 |
| edge-01 | edge_case | 公寓租金刚够还月供，算好的投资吗？ | 可以触发 real-estate-cashflow，但应指出“刚够还贷”未扣除空置、维修、物业、税费和机会成本，真实现金流可能为负；需要完整测算后再判断。 |

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
