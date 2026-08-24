# rat-race-detector — 测试结果

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
| should-trigger-01 | should_trigger | 我感觉自己一直在老鼠赛跑里，工资涨了但存款没涨，越忙越焦虑。怎么跳出来？ | 应激活 rat-race-detector，诊断恐惧-贪婪循环，盘点资产项，给出被动收入覆盖支出的跳出条件。 |
| should-trigger-02 | should_trigger | 每次加薪我就换更好的车和房，结果压力更大了。这是不是恐惧和贪婪在控制我？ | 应激活 rat-race-detector，指出加薪-增支循环，帮助用户识别老鼠赛跑机制。 |
| should-trigger-03 | should_trigger | 我每个月都是起床、上班、还花呗、再起床、再上班。没有被动收入，一停下来就慌。 | 应激活 rat-race-detector，使用书中原文循环描述，确认无资产现金流的状态。 |
| should-not-trigger-01 | should_not_trigger | 公司给了我两个offer，一个稳定但钱少，一个高薪但有裁员风险，我该怎么选？ | 不应激活 rat-race-detector，因为问题核心是单次职业选择/风险评估，而非结构性老鼠赛跑循环。 |
| should-not-trigger-02 | should_not_trigger | 我每月工资到账，应该先还信用卡还是先存一笔做投资？ | 不应激活 rat-race-detector，应激活 pay-yourself-first，因为问题核心是现金流分配顺序。 |
| edge-01 | edge_case | 我工资全部用来还房贷和养娃，没有存款，但房本上有我的名字，这算老鼠赛跑吗？ | 应激活 rat-race-detector，但需说明自住房即使署名也不产生现金流，用户仍处于无资产现金流的老鼠赛跑状态；同时可联动 asset-liability-filter 进一步判断房产性质。 |

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
