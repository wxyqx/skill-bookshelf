# five-financial-iqs — 测试结果

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
| should-trigger-01 | should_trigger | 我想系统提升自己的财商，应该从哪开始？ | 应激活 five-financial-iqs，并引导用户自评五维财商、找出短板。 |
| should-trigger-02 | should_trigger | 我的五种财商里，哪一项最弱？赚更多的钱、守住钱、预算、杠杆、信息怎么平衡？ | 应激活 five-financial-iqs，逐项解释并帮助用户诊断。 |
| should-trigger-03 | should_trigger | How can I improve my five financial I... | 应激活 five-financial-iqs，用英文或中英双语给出五维框架。 |
| should-not-trigger-01 | should_not_trigger | 推荐一只好股票，我想短线赚一波。 | 不应激活本 skill，因为用户已锁定具体股票并要求荐股，不属于财商能力诊断。 |
| should-not-trigger-02 | should_not_trigger | OPM 和 OPT 杠杆怎么用才能快速放大收益？ | 不应激活本 skill，应激活 opm-opt-leverage。 |
| edge-01 | edge_case | 我收入很高但存不下钱，这是财商问题吗？ | 可以触发 five-financial-iqs，但应指出问题可能落在‘守住你的钱’和‘预算你的钱’两个维度，而非单纯收入不足。 |

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
