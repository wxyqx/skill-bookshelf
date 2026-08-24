# startup-ten-lessons — 测试结果

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
| should-trigger-01 | should_trigger | 我想辞职创业，但不知道创业前该做哪些准备，你能按富爸爸的10堂必修课帮我梳理吗？ | 应激活 startup-ten-lessons，引导用户完成使命、代价、B-I三角形自检、大目标与里程碑等步骤。 |
| should-trigger-02 | should_trigger | 我副业做了一年，发现只靠自己忙不过来，是不是该用B-I三角形先检查一下再决... | 应激活 startup-ten-lessons，强调创立前自检与从S向B迁移的思维转换。 |
| should-trigger-03 | should_trigger | Before you quit your job, what should... | 应激活 startup-ten-lessons，用中英混合触发词也能识别。 |
| should-not-trigger-01 | should_not_trigger | 我公司已经运转三年了，最近现金流总是断，帮我诊断一下哪里出了问题。 | 不应激活 startup-ten-lessons，应激活 bi-triangle 或 cashflow-quadrant 进行企业诊断。 |
| should-not-trigger-02 | should_not_trigger | 我想学习个人理财，提高自己的财商五力，应该怎么开始？ | 不应激活 startup-ten-lessons，应激活 five-financial-iqs。 |
| edge-01 | edge_case | 我打算下周辞职开咖啡馆，已经租好店面了，现在想请你帮我做创业前准备。 | 可激活 startup-ten-lessons，但需提醒用户店面已租、部分决策已不可逆，重点转为剩余风险控制和B-I三角形补缺。 |

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
