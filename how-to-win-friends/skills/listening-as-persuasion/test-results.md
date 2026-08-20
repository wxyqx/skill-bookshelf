# listening-as-persuasion — 压力测试结果

> 测试时间: 2026-08-16 | 方式: 独立 sub-agent 盲测
> 详细结果见 [TEST_RESULTS.md](../../docs/TEST_RESULTS.md)

## 通过率: 5/6 = 83.3% ✅

| 测试 ID | 类型 | 预期 | sub-agent 判断 | 结果 |
|---|---|---|---|---|
| should-trigger-01 | should_trigger | listening-as-persuasion | preemptive-self-criticism | ✗ |
| should-trigger-02 | should_trigger | listening-as-persuasion | listening-as-persuasion | ✅ |
| should-trigger-03 | should_trigger | listening-as-persuasion | listening-as-persuasion | ✅ |
| should-not-trigger-01 | should_not_trigger | none | none | ✅ |
| should-not-trigger-02 | should_not_trigger (跨skill) | yes-ladder-socratic | yes-ladder-socratic | ✅ |
| edge-01 | edge_case | none | none | ✅ |

## 关键区分

- **should-trigger-01 (✗)**: "客户来投诉产品质量问题，怎么处理？" 应触发 listening-as-persuasion（先倾听客户不满），但被误判为 preemptive-self-criticism（先认错）。原因：本 skill 的 description 集中在"说太多/他不听"等 trigger 词，未覆盖"投诉处理"场景，而 preemptive-self-criticism 的"对方生气了"更直接匹配。
- **修复建议**: 在 description 中增加"投诉处理 / complaint handling"作为 trigger 场景，留待 darwin-skill 自动进化阶段处理。
