# patience-and-action — 测试结果

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
| should-trigger-01 | should_trigger | 大家都开始投了，我还在观望，是不是太保守？ | 应激活 patience-and-action，帮助用户评估最佳击球区并克制行动偏好。 |
| should-trigger-02 | should_trigger | How do I know when to wait and when t... | 应激活 patience-and-action（description 含英文 trigger）。 |
| should-trigger-03 | should_trigger | 手上有现金，但找不到好机会，要不要随便买点什么？ | 应激活 patience-and-action，解释等待的机会成本与行动成本。 |
| should-not-trigger-01 | should_not_trigger | 帮我制定一个健身计划。 | 不应激活本 skill，这是执行计划请求。 |
| should-not-trigger-02 | should_not_trigger | 这两个投资机会哪个机会成本更低？ | 不应激活 patience-and-action，应激活 opportunity-cost。 |
| edge-01 | edge_case | 这个投资机会看起来还可以，但不算绝佳。 | 可以调用 patience-and-action，但应引导用户用机会成本和最佳击球区标准判断，不轻易建议等待或行动。 |

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
