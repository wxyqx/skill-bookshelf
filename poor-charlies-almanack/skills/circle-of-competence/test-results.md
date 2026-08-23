# circle-of-competence — 测试结果

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
| should-trigger-01 | should_trigger | 我不懂这个领域，但机会好像很好，要不要冲？ | 应激活 circle-of-competence，帮助用户判断是否在能力圈内。 |
| should-trigger-02 | should_trigger | circle of competence 到底怎么判断？ | 应激活 circle-of-competence，解释能力圈定义和边界测试方法。 |
| should-trigger-03 | should_trigger | 大家都在买这个，我也想买，但我根本看不懂它的商业模式。 | 应激活 circle-of-competence，指出 FOMO 和能力圈外风险。 |
| should-not-trigger-01 | should_not_trigger | 给我介绍一下量子计算的基本原理。 | 不应激活本 skill，这是知识介绍请求。 |
| should-not-trigger-02 | should_not_trigger | 如果我看错了这个投资，最坏会怎样？ | 不应激活 circle-of-competence，应激活 margin-of-safety。 |
| edge-01 | edge_case | 我学过一些心理学，能不能算在能力圈内接咨询项目？ | 可以调用 circle-of-competence，但应引导用户用具体能力测试而非学历判断。 |

## 运行时测试说明

静态审查已确认 `test-prompts.json` 满足 cangjie-skill 质量红线：

1. 每个 skill 必须通过全部三重验证（在 `verified.md` 中完成）。
2. 每个 skill 必须有完整的 R / I / A1 / A2 / E / B 六段（在 `SKILL.md` 中完成）。
3. 原文引用 ≤150 字/段。
4. 每个 skill 必须有 `test-prompts.json`，且含诱饵测试（不应调用的场景），其中至少 1 条是同书兄弟 skill 的混淆场景。
5. `description` 字段已明确 trigger 条件。

运行时触发验证需要：

- 接入 darwin-skill 自动进化：`darwin evolve books/poor-charlies-almanack/`
- 或在真实对话中手动复现各 `prompt`，确认 agent 路由到正确的 skill。

## 改进记录

| 版本 | 改动 | 测试时间 |
|---|---|---|
| 0.1.0 | 初始版本，静态审查通过 | 2026-08-23 |
