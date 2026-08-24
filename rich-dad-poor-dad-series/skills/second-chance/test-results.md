# second-chance — 测试结果

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
| should-trigger-01 | should_trigger | 我创业失败欠了债，感觉没希望了，富爸爸说的第二次致富机会怎么开始？ | 应激活 second-chance，引导用户清点现实、转换提问、寻找导师并小步验证现金流。 |
| should-trigger-02 | should_trigger | 被裁员后行业也不景气，我想把这次危机当作重新开始的机会，有什么框架？ | 应激活 second-chance，帮助用户从危机中看到硬币另一面并制定重启计划。 |
| should-trigger-03 | should_trigger | second chance / 东山再起，失败后的心态和行动步骤是什么？ | 应激活 second-chance，识别英文 trigger 并给出翻盘行动框架。 |
| should-not-trigger-01 | should_not_trigger | 我工作稳定，想提前规划退休资产，该怎么做？ | 不应激活 second-chance，应激活 retirement-ark。 |
| should-not-trigger-02 | should_not_trigger | 我刚毕业，想第一次创业，需要做哪些准备？ | 不应激活 second-chance，应激活 startup-ten-lessons。 |
| edge-01 | edge_case | 我投资亏损了30%，但本职工作还在，这算需要第二次致富机会吗？ | 可激活 second-chance，但侧重轻微危机的心态复盘与资产再平衡，而非破产级别的重启。 |

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
