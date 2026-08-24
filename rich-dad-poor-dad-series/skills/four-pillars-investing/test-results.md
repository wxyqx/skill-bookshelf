# four-pillars-investing — 测试结果

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
| should-trigger-01 | should_trigger | 怎么用四柱法分析一只股票？ | 应激活 four-pillars-investing，并展开基本面、技术面、现金流策略、风险管理四个维度。 |
| should-trigger-02 | should_trigger | 基本面、技术面、现金流策略、风险管理分别是什么？我想通过股票产生现金流。 | 应激活 four-pillars-investing，解释四柱并给出股票现金流策略示例。 |
| should-trigger-03 | should_trigger | Can you use the four pillars to evalu... | 应激活 four-pillars-investing，用英文说明四柱法及用户需提供的信息。 |
| should-not-trigger-01 | should_not_trigger | 这套房子租金能覆盖月供吗？值不值得买？ | 不应激活本 skill，因为用户询问的是房地产投资现金流，而非股票四柱法。 |
| should-not-trigger-02 | should_not_trigger | 我有一笔资金想投资，选股票还是房产更好？ | 不应激活本 skill，应激活 put-money-to-work（或资产配置相关 skill）。 |
| edge-01 | edge_case | 只看基本面长期持有可以吗？巴菲特不也这样？ | 可以触发 four-pillars-investing，但应指出四柱法强调四维度结合；仅看基本面会忽略技术面时机、现金流策略和风险管理，巴菲特也有严格安全边际与仓位纪律。 |

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
