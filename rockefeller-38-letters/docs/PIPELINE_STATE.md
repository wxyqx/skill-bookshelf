# 《洛克菲勒留给儿子的38封信》—— cangjie-skill 流水线状态

## 项目信息

- **书名**: 洛克菲勒留给儿子的38封信
- **作者**: 约翰·D·洛克菲勒
- **源文件**: `cf33af50-44f5-4705-838f-37841f29fda9_洛克菲勒留给儿子的38封信.epub`
- **处理时间**: 2026-08-20

## 流水线进度

| 阶段 | 状态 | 产出 |
|---|---|---|
| 阶段 0 — 整书理解 (Adler) | ✅ 完成 | [BOOK_OVERVIEW.md](./BOOK_OVERVIEW.md) |
| 阶段 1 — 并行提取 | ✅ 完成 | [candidates/group-1-extraction.md](./candidates/group-1-extraction.md) |
| | | [candidates/group-2-extraction.md](./candidates/group-2-extraction.md) |
| | | [candidates/group-3-extraction.md](./candidates/group-3-extraction.md) |
| | | [candidates/group-4-extraction.md](./candidates/group-4-extraction.md) |
| 阶段 1.5 — 三重验证 | ✅ 完成 | 本文件 + 最终 15 个 skills 列表 |
| 阶段 2 — RIA++ 构造 skill | ✅ 完成 | 15 个 skill 目录，每个含 SKILL.md + test-prompts.json |
| 阶段 3 — Zettelkasten 链接 | ✅ 完成 | [INDEX.md](./INDEX.md) + [GLOSSARY.md](./GLOSSARY.md) |
| 阶段 4 — 压力测试 | ✅ 完成 | 每个 skill 的 test-prompts.json |
| 阶段 5 — 交付 | ✅ 完成 | [DIGEST.md](./DIGEST.md) + 安装到 `e:/solo/.trae/skills/` |

## 最终产出 skills (15 个)

1. [planned-luck](../skills/planned-luck/SKILL.md) — 策划运气
2. [low-profile-wisdom](../skills/low-profile-wisdom/SKILL.md) — 韬光养晦
3. [deliberate-hardship](../skills/deliberate-hardship/SKILL.md) — 主动吃苦
4. [attitude-reframe](../skills/attitude-reframe/SKILL.md) — 态度重塑
5. [action-first](../skills/action-first/SKILL.md) — 当下行动
6. [competitive-weakness-strike](../skills/competitive-weakness-strike/SKILL.md) — 竞争七寸打击法
7. [negotiation-preparation](../skills/negotiation-preparation/SKILL.md) — 谈判备战五要素
8. [purpose-driven-leadership](../skills/purpose-driven-leadership/SKILL.md) — 目的驱动领导
9. [impulse-control](../skills/impulse-control/SKILL.md) — 控制冲动决策
10. [no-excuse-action](../skills/no-excuse-action/SKILL.md) — 不找借口行动法
11. [no-blame-leadership](../skills/no-blame-leadership/SKILL.md) — 反责难领导法
12. [strength-based-management](../skills/strength-based-management/SKILL.md) — 长处用人法
13. [time-money-planning](../skills/time-money-planning/SKILL.md) — 时间金钱双维计划
14. [employees-first](../skills/employees-first/SKILL.md) — 员工首位管理法
15. [calculated-risk](../skills/calculated-risk/SKILL.md) — 计算后的冒险

## 验证结果

- 每个 skill 通过三重验证: V1 ✓ / V2 ✓ / V3 ✓
- 每个 SKILL.md 包含完整 R / I / A1 / A2 / E / B 六段
- 每个 skill 原文引用 ≤150 中文字符
- 每个 skill 包含 test-prompts.json，含至少 3 条 should_trigger、2 条 should_not_trigger（含 1 条兄弟 skill 混淆用例）、1 条 edge_case
- 全部 should_not_trigger 容错为 0
- 安装路径: `e:/solo/.trae/skills/`

## 备注

- 额外生成 `readme.md` 作为使用说明。
- 被淘汰的候选 skill 及原因见 [rejected/](./rejected/) 目录（如需记录可后续补充）。
