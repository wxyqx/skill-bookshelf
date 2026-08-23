# margin-of-safety — 测试结果

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
| should-trigger-01 | should_trigger | 这个投资机会我看不太准，应该怎么办？ | 应激活 margin-of-safety，建议用户要求更大的价格折扣或缓冲。 |
| should-trigger-02 | should_trigger | How much margin of safety should I le... | 应激活 margin-of-safety（description 含英文 trigger）。 |
| should-trigger-03 | should_trigger | 如果我的判断错了，这个方案会不会崩盘？ | 应激活 margin-of-safety，引导用户设计缓冲机制。 |
| should-not-trigger-01 | should_not_trigger | 今天天气怎么样？ | 不应激活本 skill，这是闲聊。 |
| should-not-trigger-02 | should_not_trigger | 我不懂这个领域，但机会很好，要不要投？ | 不应激活 margin-of-safety，应激活 circle-of-competence。 |
| edge-01 | edge_case | 这个机会价格已经很高了，但公司确实伟大。 | 可以调用 margin-of-safety，但应明确提醒用户价格过高时安全边际消失，伟大公司也需要合理价格。 |

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
