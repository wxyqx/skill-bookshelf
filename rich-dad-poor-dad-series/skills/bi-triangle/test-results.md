# bi-triangle — 测试结果

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
| should-trigger-01 | should_trigger | 我要创业，需要准备哪些关键要素？ | 应激活 bi-triangle，并介绍使命、团队、领导力、产品、法律、系统、沟通、现金流八要素。 |
| should-trigger-02 | should_trigger | B-I 三角形八个要素分别是什么？为什么我的公司离不开我？ | 应激活 bi-triangle，解释八要素并指出系统/团队缺失导致企业停留在 S 型。 |
| should-trigger-03 | should_trigger | Why do most startups fail according t... | 应激活 bi-triangle，用英文解释八要素缺失如何导致失败。 |
| should-not-trigger-01 | should_not_trigger | 我该选哪个行业打工，才能更快升职加薪？ | 不应激活本 skill，因为用户问题是职业选择而非创业企业结构。 |
| should-not-trigger-02 | should_not_trigger | 我想用别人的钱扩大生意，应该怎么设计融资结构？ | 不应激活本 skill，应激活 opm-opt-leverage。 |
| edge-01 | edge_case | 我有一个很好的产品创意，可以创业了吗？ | 可以触发 bi-triangle，但应指出仅有产品远远不够，还需要验证使命、团队、法律、系统、现金流等其他七项。 |

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
