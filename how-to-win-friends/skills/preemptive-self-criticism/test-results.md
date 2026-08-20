# preemptive-self-criticism — 压力测试结果

> 测试时间: 2026-08-16 | 方式: 独立 sub-agent 盲测
> 详细结果见 [TEST_RESULTS.md](../../docs/TEST_RESULTS.md)

## 通过率: 6/6 = 100% ✅

| 测试 ID | 类型 | 预期 | sub-agent 判断 | 结果 |
|---|---|---|---|---|
| should-trigger-01 | should_trigger | preemptive-self-criticism | preemptive-self-criticism | ✅ |
| should-trigger-02 | should_trigger | preemptive-self-criticism | preemptive-self-criticism | ✅ |
| should-trigger-03 | should_trigger | preemptive-self-criticism | preemptive-self-criticism | ✅ |
| should-not-trigger-01 | should_not_trigger | none | none | ✅ |
| should-not-trigger-02 | should_not_trigger (跨skill) | argument-avoidance | argument-avoidance | ✅ |
| edge-01 | edge_case | preemptive-self-criticism (附提醒) | preemptive-self-criticism | ✅ |

## 关键区分

- **should-not-trigger-02**: "同事说了错误方案，想纠正" → 正确识别为 argument-avoidance（预防性避免争辩，而非认错）。
- **edge-01**: "这件事我有错但对方也有问题" 仍触发，但需附提醒——认的错必须是真实的，且需评估对方是否会拿认错当攻击把柄。
