# code-of-honor — 测试结果

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
| should-trigger-01 | should_trigger | 我和朋友准备合伙创业，想先定一份荣誉守则，应该怎么写？ | 应激活 code-of-honor，引导用户识别高压场景并制定可问责的团队守则。 |
| should-trigger-02 | should_trigger | 团队扩大到10人后开始出现甩锅和信息不透明，能不能用富爸爸的荣誉守则模型？ | 应激活 code-of-honor，帮助用户复盘团队冲突并制定/升级守则。 |
| should-trigger-03 | should_trigger | Code of honor 在团队中具体怎么用？我们想建立可问责的团队文化。 | 应激活 code-of-honor，识别英文 trigger 并给出团队契约制定步骤。 |
| should-not-trigger-01 | should_not_trigger | 我一个人做自由职业，想提升销售技巧，该学什么？ | 不应激活 code-of-honor，应激活 sales-dogs。 |
| should-not-trigger-02 | should_not_trigger | 公司已经成立，我想诊断产品、法律、现金流等八个要素是否齐全。 | 不应激活 code-of-honor，应激活 bi-triangle。 |
| edge-01 | edge_case | 家庭成员一起投资房产，经常为花钱和决策吵架，能用荣誉守则吗？ | 可以激活 code-of-honor，但需把团队守则转化为家庭投资公约，并强调情感关系与法律协议的平衡。 |

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
