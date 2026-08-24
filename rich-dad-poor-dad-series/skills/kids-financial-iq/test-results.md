# kids-financial-iq — 测试结果

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
| should-trigger-01 | should_trigger | 孩子总是做家务要钱，我想用富爸爸的方法教他财商，该怎么做？ | 应激活 kids-financial-iq，引导家长转换金钱语言、设计存钱罐系统和真实场景练习。 |
| should-trigger-02 | should_trigger | 我想培养孩子的财富基因，从几岁开始、用什么工具比较好？ | 应激活 kids-financial-iq，给出分龄财商启蒙工具和现金流游戏建议。 |
| should-trigger-03 | should_trigger | kids financial IQ / 儿童财商教育，家长应该怎么在日常生... | 应激活 kids-financial-iq，识别英文 trigger 并给出家庭财商教育路径。 |
| should-not-trigger-01 | should_not_trigger | 我想学习如何区分资产和负债来做自己的购买决策。 | 不应激活 kids-financial-iq，应激活 asset-liability-filter。 |
| should-not-trigger-02 | should_not_trigger | 我想给自己做现金流象限定位，看看该往B/I迁移。 | 不应激活 kids-financial-iq，应激活 cashflow-quadrant。 |
| edge-01 | edge_case | 我 teenage 的孩子已经会炒股了，我还需要教他儿童财商吗？ | 可激活 kids-financial-iq，但需把内容升级为青少年版：侧重风险、杠杆、三种收入类型和创业思维，而非幼儿化工具。 |

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
