# 流水线状态

> 本文件记录 cangjie-skill RIA-TV++ 各阶段完成情况，便于断点续跑。

---

## 内容元信息

- **书名**：《富爸爸穷爸爸系列（共32册）》
- **作者**：罗伯特·T·清崎（Robert T. Kiyosaki）
- **出版年**：2021 年套装（系列出版时间跨度 1997–2020）
- **内容来源**：EPUB
- **开始时间**：2026-08-23
- **完成时间**：2026-08-24

---

## 阶段完成状态

| 阶段 | 状态 | 产出文件 |
|---|---|---|
| 阶段 0 — 整书理解（Adler） | ✅ 完成 | `BOOK_OVERVIEW.md` |
| 阶段 1 — 并行提取 | ✅ 完成 | `candidates/frameworks.md` (127 条原始候选), `candidates/principles.md` (29 条), `candidates/cases.md` (25 条), `candidates/counter-examples.md` (40 条), `candidates/glossary.md` (40 条) |
| 阶段 1.5 — 三重验证 | ✅ 完成 | `verified.md`（18 个入选）, `rejected.md` |
| 阶段 2 — RIA++ 构造 skill | ✅ 完成 | 18 个 `<skill-slug>/SKILL.md` + `test-prompts.json` |
| 阶段 3 — Zettelkasten 链接 | ✅ 完成 | `INDEX.md`, `GLOSSARY.md` 已生成；`related_skills` 已填充 |
| 阶段 4 — 压力测试 | ✅ 完成 | 18 个 `test-prompts.json` 静态审查完成；18 个 `test-results.md` 已生成 |
| 阶段 5 — 交付 | ✅ 完成 | `DIGEST.md`, `README.md` 已生成；18 个 skill 已安装到 `e:\solo\.trae\skills\` |

---

## 最终入选 skills（18 个）

1. `cashflow-quadrant` — 现金流象限（ESBI）
2. `asset-liability-filter` — 资产与负债区分法
3. `rat-race-detector` — 老鼠赛跑识别与跳出
4. `pay-yourself-first` — 先支付自己
5. `mind-your-own-business` — 关注自己的事业 / 资产项优先
6. `good-debt-bad-debt` — 良性债务 vs 不良债务
7. `five-financial-iqs` — 五种财商
8. `opm-opt-leverage` — OPM/OPT 杠杆模型
9. `bi-triangle` — B-I 三角形（企业八要素）
10. `put-money-to-work` — 给你的钱找一份工作
11. `four-pillars-investing` — 股票投资四柱法
12. `real-estate-cashflow` — 房地产投资现金流分析
13. `startup-ten-lessons` — 创业前的准备与目标设定
14. `sales-dogs` — 销售沟通与销售狗模型
15. `code-of-honor` — 荣誉守则 / 团队建设
16. `retirement-ark` — 退休方舟 / 财富大趋势
17. `second-chance` — 第二次致富机会 / 硬币另一面
18. `kids-financial-iq` — 儿童财商教育

---

## 备注

- 32 本书全部纳入分析，原始框架候选 127 条，去重后保留 18 个可独立成 skill 的框架。
- 阶段 4 运行时测试待接入 darwin-skill 后补跑。
