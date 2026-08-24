# 《富爸爸穷爸爸系列》Skills — 测试报告

> 阶段 4 压力测试静态审查报告。运行时触发验证待接入 darwin-skill 后补充。
>
> 审查时间：2026-08-23

---

## 审查范围

- 18 个 skill 的 `test-prompts.json`
- 18 个 skill 的 `test-results.md`
- cangjie-skill 质量红线符合性

---

## 审查结果

| Skill | should_trigger | should_not_trigger | edge_case | 跨 skill 混淆 | JSON 有效 | 状态 |
|---|---|---|---|---|---|---|
| asset-liability-filter | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| bi-triangle | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| cashflow-quadrant | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| code-of-honor | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| five-financial-iqs | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| four-pillars-investing | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| good-debt-bad-debt | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| kids-financial-iq | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| mind-your-own-business | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| opm-opt-leverage | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| pay-yourself-first | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| put-money-to-work | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| rat-race-detector | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| real-estate-cashflow | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| retirement-ark | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| sales-dogs | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| second-chance | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |
| startup-ten-lessons | 3 | 2 | 1 | 2 | 是 | ✅ 通过 |

---

## 审查标准

1. ✅ 每个 skill 已通过三重验证（见 `verified.md`）。
2. ✅ 每个 skill `SKILL.md` 包含完整 R / I / A1 / A2 / E / B 六段。
3. ✅ 原文引用 ≤150 字/段。
4. ✅ 每个 skill 有 `test-prompts.json`：
   - ≥ 3 条 `should_trigger`
   - ≥ 2 条 `should_not_trigger`（其中 ≥ 1 条为同书兄弟 skill 混淆场景）
   - ≥ 1 条 `edge_case`
5. ✅ `description` 字段明确 trigger 条件。
6. ✅ `test-prompts.json` 为有效 JSON 且 `darwin_compatible: true`。

---

## 待完成项

- [ ] 接入 darwin-skill 运行真实对话触发测试
- [ ] 手动复现关键边界用例，验证 agent 路由准确性
- [ ] 根据运行时结果迭代 `test-prompts.json` 与 `SKILL.md` 的 trigger 描述

---

*详细结果见各 skill 目录下的 `test-results.md`。*
