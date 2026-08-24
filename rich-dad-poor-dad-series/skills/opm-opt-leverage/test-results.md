# opm-opt-leverage — 测试结果

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
| should-trigger-01 | should_trigger | 怎么用别人的钱（OPM）投资房地产？ | 应激活 opm-opt-leverage，并解释 OPM 概念、给出融资结构思路。 |
| should-trigger-02 | should_trigger | OPT 是什么意思，怎么让别人的时间为我工作？ | 应激活 opm-opt-leverage，区分 OPM 与 OPT 并给出案例。 |
| should-trigger-03 | should_trigger | Can you explain OPM and OPT leverage ... | 应激活 opm-opt-leverage，用英文解释 OPM/OPT 及使用前提。 |
| should-not-trigger-01 | should_not_trigger | 我信用卡欠了很多，怎么尽快还清？ | 不应激活本 skill，因为用户需要债务清偿与现金流管理，而非加杠杆。 |
| should-not-trigger-02 | should_not_trigger | 房地产企业现金流怎么算？租金能不能覆盖月供？ | 不应激活本 skill，应激活 real-estate-cashflow。 |
| edge-01 | edge_case | 借钱买自住房算 OPM 吗？ | 可以调用 opm-opt-leverage，但应明确说明自住房若无正现金流属于不良债务/负债，不是 OPM 投资意义上的杠杆。 |

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
