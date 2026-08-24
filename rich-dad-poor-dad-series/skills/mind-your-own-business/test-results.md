# mind-your-own-business — 测试结果

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
| should-trigger-01 | should_trigger | 我在公司干了十年，除了工资啥也没留下。关注自己的事业到底是什么意思？ | 应激活 mind-your-own-business，解释职业≠事业，引导用户盘点资产项并制定资产优先行动。 |
| should-trigger-02 | should_trigger | 我该把精力花在升职加薪上，还是花在买房、投资这些资产项上？ | 应激活 mind-your-own-business，比较收入项与资产项的长期效果，建议资产项优先。 |
| should-trigger-03 | should_trigger | 我不想一辈子为别人打工，除了辞职创业，还能怎么建立自己的资产？ | 应激活 mind-your-own-business，说明不一定要辞职，可在职买入资产，逐步构建自己的事业。 |
| should-not-trigger-01 | should_not_trigger | 我买的这套房子每个月还要还贷款，它是资产还是负债？ | 不应激活 mind-your-own-business，应激活 asset-liability-filter，因为问题核心是单笔资产/负债判断。 |
| should-not-trigger-02 | should_not_trigger | 我年薪50万，但税和开销也越来越高，感觉永远在老鼠赛跑。现金流象限里我到底... | 不应激活 mind-your-own-business，应激活 cashflow-quadrant，因为问题核心是判断象限位置和迁移路径。 |
| edge-01 | edge_case | 我现在工资不高，但想关注自己的事业。是不是应该先辞职创业？ | 应激活 mind-your-own-business，但需强调不一定辞职；建议低收入者先保住现金流，用副业/小额投资逐步建资产，而非孤注一掷创业。 |

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
