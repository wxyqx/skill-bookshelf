# argument-avoidance — 压力测试结果

> 测试时间: 2026-08-16 | 方式: 独立 sub-agent 盲测
> 详细结果见 [TEST_RESULTS.md](../../docs/TEST_RESULTS.md)

## 通过率: 6/6 = 100% ✅

| 测试 ID | 类型 | 预期 | sub-agent 判断 | 结果 |
|---|---|---|---|---|
| should-trigger-01 | should_trigger | argument-avoidance | argument-avoidance | ✅ |
| should-trigger-02 | should_trigger | argument-avoidance | argument-avoidance | ✅ |
| should-trigger-03 | should_trigger | argument-avoidance | argument-avoidance | ✅ |
| should-not-trigger-01 | should_not_trigger | none | none | ✅ |
| should-not-trigger-02 | should_not_trigger (跨skill) | preemptive-self-criticism | preemptive-self-criticism | ✅ |
| edge-01 | edge_case | none (安全问题直接指出) | none | ✅ |

## 关键区分

- **should-not-trigger-02**: "项目延期客户很生气，第一句话" → 正确识别为 preemptive-self-criticism（冲突已发生需化解，而非预防性避免争辩）。
- **edge-01**: "同事方案有安全隐患" → 正确识别为安全边界，避免争辩不适用，应直接明确指出。
