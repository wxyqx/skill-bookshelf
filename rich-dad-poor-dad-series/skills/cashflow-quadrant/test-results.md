# cashflow-quadrant — 测试结果

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
| should-trigger-01 | should_trigger | 我年薪50万，但税和开销也越来越高，感觉永远在老鼠赛跑。现金流象限里我到底... | 应激活 cashflow-quadrant，先定位用户在E/S象限，再解释高收入为何仍在左侧，并给出迁往B/I的路径建议。 |
| should-trigger-02 | should_trigger | 我在考虑辞职做自由职业者，还是直接创业。富爸爸说的S型和B型企业有什么区别？ | 应激活 cashflow-quadrant，用ESBI区分S与B，指出是否拥有可复制系统。 |
| should-trigger-03 | should_trigger | 我不想一辈子为钱工作，应该成为雇员、投资者还是企业家？哪个象限适合我？ | 应激活 cashflow-quadrant，引导用户从收入来源和思维模式判断E/S/B/I位置。 |
| should-not-trigger-01 | should_not_trigger | 我刚买了一套自住房，月供8000，这房子到底是资产还是负债？ | 不应激活 cashflow-quadrant，应激活 asset-liability-filter，因为问题核心是单笔资产的现金流方向判断。 |
| should-not-trigger-02 | should_not_trigger | 我每月工资到账就还信用卡和花呗，根本存不下钱，该怎么先支付自己？ | 不应激活 cashflow-quadrant，应激活 pay-yourself-first，因为问题核心是现金流分配顺序与预算纪律。 |
| edge-01 | edge_case | 我白天是雇员，晚上有出租房在收租，周末还经营一个小工作室。我属于哪个象限？ | 应激活 cashflow-quadrant，但需说明用户同时跨E/I/S多个象限，按主要收入占比和未来迁移目标分别定位，而非简单归到单一象限。 |

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
