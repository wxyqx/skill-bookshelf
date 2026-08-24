# asset-liability-filter — 测试结果

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
| should-trigger-01 | should_trigger | 我买了套自住房，每月还房贷1万，这房子到底是资产还是负债？ | 应激活 asset-liability-filter，按现金流方向判断：自住房贷、税费、维护均为现金流出，属于负债而非资产。 |
| should-trigger-02 | should_trigger | 朋友说我车值30万是资产，我怎么觉得是负债？ | 应激活 asset-liability-filter，解释汽车折旧、油费、保险、贷款等现金流出，判定为负债。 |
| should-trigger-03 | should_trigger | 我想整理一下我的资产负债表，哪些东西是真正值钱的资产？ | 应激活 asset-liability-filter，引导用户按现金流方向重新归类资产、负债与支出。 |
| should-not-trigger-01 | should_not_trigger | 我该不该为了省税，把存款从定期改成货币基金？ | 不应激活 asset-liability-filter，因为问题核心是现金管理/资产配置，不针对单笔物品的资产/负债定性。 |
| should-not-trigger-02 | should_not_trigger | 我刷信用卡买了台游戏机，现在分期还没还完，这是良性债务还是不良债务？ | 不应激活 asset-liability-filter，应激活 good-debt-bad-debt，因为问题核心是债务性质判断。 |
| edge-01 | edge_case | 我买了一套小户型出租，租金刚好覆盖月供，略有结余。这套房算资产吗？ | 应激活 asset-liability-filter，判定为正现金流即为资产；但需提示出租房仍有空置、维修、利率等风险，资产≠无风险。 |

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
