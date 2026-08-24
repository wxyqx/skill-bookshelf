# retirement-ark — 测试结果

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
| should-trigger-01 | should_trigger | 我现在只靠公司交的社保和401k，担心退休后不够，怎么打造退休方舟？ | 应激活 retirement-ark，引导用户盘点退休依赖、识别风险并设计三类资产方舟。 |
| should-trigger-02 | should_trigger | 通胀这么厉害，我想按富爸爸的财富大趋势重新配置退休资产，该怎么做？ | 应激活 retirement-ark，从宏观趋势角度给出资产结构建议。 |
| should-trigger-03 | should_trigger | retirement ark 是什么意思？我该怎么为养老建立多元现金流？ | 应激活 retirement-ark，识别英文 trigger 并解释退休方舟框架。 |
| should-not-trigger-01 | should_not_trigger | 我有一笔钱，想给每笔钱找一份能产生现金流的工作，怎么分配？ | 不应激活 retirement-ark，应激活 put-money-to-work。 |
| should-not-trigger-02 | should_not_trigger | 我想学习房地产投资现金流分析，该看什么指标？ | 不应激活 retirement-ark，应激活 real-estate-cashflow。 |
| edge-01 | edge_case | 我刚毕业，收入只够覆盖生活支出，现在谈退休方舟是不是太早？ | 可激活 retirement-ark，但需调整为“起步版”：先建立现金流象限意识和小额资产积累，而非直接配置多元资产。 |

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
