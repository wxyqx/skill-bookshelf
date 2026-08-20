# reputation-anchoring — 压力测试结果

> 测试时间: 2026-08-16 | 方式: 独立 sub-agent 盲测
> 详细结果见 [TEST_RESULTS.md](../../docs/TEST_RESULTS.md)

## 通过率: 6/6 = 100% ✅

| 测试 ID | 类型 | 预期 | sub-agent 判断 | 结果 |
|---|---|---|---|---|
| should-trigger-01 | should_trigger | reputation-anchoring | reputation-anchoring | ✅ |
| should-trigger-02 | should_trigger | reputation-anchoring | reputation-anchoring | ✅ |
| should-trigger-03 | should_trigger | reputation-anchoring | reputation-anchoring | ✅ |
| should-not-trigger-01 | should_not_trigger | none | none | ✅ |
| should-not-trigger-02 | should_not_trigger (跨skill) | face-saving-feedback | face-saving-feedback | ✅ |
| edge-01 | edge_case | none | none | ✅ |

## 关键区分

- **should-not-trigger-02**: "下属报告数据有错误需指出" → 正确识别为 face-saving-feedback（直接指出具体错误），而非声誉锚定（间接影响）。
- **edge-01**: "行为严重需直接纠正" → 正确识别为边界（声誉锚定太慢，严重行为需直接纠正）。
