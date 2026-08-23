# lollapalooza-effect — 测试结果

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
| should-trigger-01 | should_trigger | 为什么这家公司能突然爆发式增长？ | 应激活 lollapalooza-effect，引导用户识别多因素共振。 |
| should-trigger-02 | should_trigger | lollapalooza 效应是什么意思？ | 应激活 lollapalooza-effect，解释多因素非线性放大。 |
| should-trigger-03 | should_trigger | 这个产品成功是因为品牌好，还是因为渠道好？ | 应激活 lollapalooza-effect，指出可能是品牌+渠道+心理等多因素共振。 |
| should-not-trigger-01 | should_not_trigger | 帮我算一下这个投资组合的夏普比率。 | 不应激活本 skill，这是计算请求。 |
| should-not-trigger-02 | should_not_trigger | 我想用多个学科模型分析这个问题，应该看哪些模型？ | 不应激活 lollapalooza-effect，应激活 multi-disciplinary-thinking。 |
| edge-01 | edge_case | 这家公司最近增长很快，是因为 CEO 个人能力很强吗？ | 可以调用 lollapalooza-effect，但应先指出单一归因风险，再邀请用户补充其他因素。 |

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
