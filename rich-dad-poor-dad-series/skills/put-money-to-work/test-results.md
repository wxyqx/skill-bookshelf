# put-money-to-work — 测试结果

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
| should-trigger-01 | should_trigger | 我手里有30万闲钱，怎么让钱为我工作？ | 应激活 put-money-to-work，并引导用户盘点资金、定义工作岗位、筛选现金流资产。 |
| should-trigger-02 | should_trigger | 给你的钱找一份工作是什么意思？钱放在银行是不是在贬值？ | 应激活 put-money-to-work，解释概念并给出现金流资产示例。 |
| should-trigger-03 | should_trigger | How do I put my money to work instead... | 应激活 put-money-to-work，用英文给出资本配置思路。 |
| should-not-trigger-01 | should_not_trigger | 这个月工资怎么分配还花呗和生活费？ | 不应激活本 skill，因为用户需要月度预算与现金流管理，而非资本投资配置。 |
| should-not-trigger-02 | should_not_trigger | 买股票要看哪几个方面？怎么判断一只股票值不值得买？ | 不应激活本 skill，应激活 four-pillars-investing。 |
| edge-01 | edge_case | 把钱投入货币基金算让钱工作吗？ | 可以触发 put-money-to-work，但应说明货币基金收益通常跑不赢通胀，只能算临时停泊，而非真正的现金流资产；应引导用户投向更高现金流产出的资产。 |

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
