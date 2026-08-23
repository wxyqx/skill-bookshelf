# 流水线状态

> 本文件记录 cangjie-skill RIA-TV++ 各阶段完成情况，便于断点续跑。

---

## 内容元信息

- **书名**：《穷查理宝典：查理·芒格智慧箴言录（全新增订本）》
- **作者**：查理·芒格（Charles T. Munger）/ 编：彼得·考夫曼
- **出版年**：2021 年 7 月
- **内容来源**：EPUB
- **开始时间**：2026-08-23
- **完成时间**：2026-08-23

---

## 阶段完成状态

| 阶段 | 状态 | 产出文件 |
|---|---|---|
| 阶段 0 — 整书理解（Adler） | ✅ 完成 | `BOOK_OVERVIEW.md` |
| 阶段 1 — 并行提取 | ✅ 完成 | `candidates/frameworks.md`, `candidates/principles.md`, `candidates/cases.md`, `candidates/counter-examples.md`, `candidates/glossary.md` |
| 阶段 1.5 — 三重验证 | ✅ 完成 | `verified.md` |
| 阶段 2 — RIA++ 构造 skill | ✅ 完成 | 12 个 `<skill-slug>/SKILL.md` |
| 阶段 3 — Zettelkasten 链接 | ✅ 完成 | `INDEX.md`, `GLOSSARY.md` |
| 阶段 4 — 压力测试 | ✅ 静态审查完成 | 12 个 `test-prompts.json` 通过结构审查，JSON 有效、用例数量与跨 skill 混淆测试均达标；`test-results.md` 已生成 |
| 阶段 5 — 交付 | ✅ 完成 | `DIGEST.md`, `README.md`；已安装到 `e:\solo\.trae\skills\` |

---

## 最终入选 skills（12 个）

1. `multi-disciplinary-thinking` — 多元思维模型
2. `circle-of-competence` — 能力圈
3. `inversion-thinking` — 逆向思维
4. `checklist-method` — 检查清单法
5. `lollapalooza-effect` — Lollapalooza 效应
6. `two-track-analysis` — 双轨分析
7. `psychology-of-misjudgment` — 人类误判心理学
8. `patience-and-action` — 耐心与果断
9. `destroy-favorite-idea` — 破坏最爱的观念
10. `stop-doing-list` — Stop Doing List
11. `opportunity-cost` — 机会成本
12. `margin-of-safety` — 安全边际

---

## 备注

- 阶段 4 测试尚未实际运行，需接入 darwin-skill 或手动跑 `test-prompts.json` 后回填结果。
- 本目录为构建产物，skills 需复制到宿主 skills 目录方可被 agent 调用。
