# 《穷查理宝典》Skills — 测试报告

> 阶段 4 压力测试静态审查报告。运行时触发验证待接入 darwin-skill 后补充。
> 
> 审查时间：2026-08-23

---

## 审查范围

- 12 个 skill 的 `test-prompts.json`
- 12 个 skill 的 `test-results.md`
- cangjie-skill 质量红线符合性

---

## 审查结果

| Skill | should_trigger | should_not_trigger | edge_case | 跨 skill 混淆 | JSON 有效 | 状态 |
|---|---|---|---|---|---|---|
| checklist-method | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| circle-of-competence | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| destroy-favorite-idea | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| inversion-thinking | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| lollapalooza-effect | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| margin-of-safety | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| multi-disciplinary-thinking | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| opportunity-cost | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| patience-and-action | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| psychology-of-misjudgment | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| stop-doing-list | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |
| two-track-analysis | 3 | 2 | 1 | 1 | 是 | ✅ 通过 |

**全部 12 个 skill 通过静态审查。**

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

## 修复记录

- `stop-doing-list/test-prompts.json` 第 46 行原先含未转义的中文双引号，导致 JSON 解析失败。已替换为书名号 `「完全停止」「减少频率」`，JSON 恢复有效。

---

## 待完成项

- [ ] 接入 darwin-skill 运行真实对话触发测试
- [ ] 手动复现关键边界用例，验证 agent 路由准确性
- [ ] 根据运行时结果迭代 `test-prompts.json` 与 `SKILL.md` 的 trigger 描述

---

*详细结果见各 skill 目录下的 `test-results.md`。*
