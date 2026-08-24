# sales-dogs — 测试结果

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
| should-trigger-01 | should_trigger | 我害怕被拒绝，一直做不好销售，富爸爸销售狗模型里我属于哪种狗？ | 应激活 sales-dogs，帮助用户自评销售狗类型并制定短板训练计划。 |
| should-trigger-02 | should_trigger | 我组建了一个三人销售团队，但业绩很差，怎么用销售狗风格搭配人员？ | 应激活 sales-dogs，评估团队风格覆盖度并提出互补建议。 |
| should-trigger-03 | should_trigger | Sales dogs 说销售=收入，我应该怎么训练自己成为超级混种狗？ | 应激活 sales-dogs，识别英文 trigger 并给出综合风格训练路径。 |
| should-not-trigger-01 | should_not_trigger | 我公司产品定位不清晰，帮我用B-I三角形梳理一下产品、系统和现金流。 | 不应激活 sales-dogs，应激活 bi-triangle 进行企业八要素诊断。 |
| should-not-trigger-02 | should_not_trigger | 我想学习股票投资，怎么分析基本面和技术面？ | 不应激活 sales-dogs，应激活 four-pillars-investing。 |
| edge-01 | edge_case | 我在做线上客服，经常要回复客户投诉，这算销售狗模型吗？ | 不应优先激活 sales-dogs；应先确认是否存在销售/成交目标，若只是售后支持则不属于销售狗模型。 |

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
