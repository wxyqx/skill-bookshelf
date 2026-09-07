# PIPELINE_STATE — 《思考，快与慢（第二版）》

- **书**: 思考，快与慢（第二版） — [美] 丹尼尔·卡尼曼；赵佳颖 审校
- **版本来源**: E:\download\思考，快与慢（第二版）.epub（中信出版社，2025）
- **产出目录**: E:\download\books\thinking-fast-and-slow\
- **安装决策**: 用户选择**不安装**，仓库形式交付
- **开始时间**: 2026-09-04

## 阶段状态

| 阶段 | 状态 | 产出 |
|---|---|---|
| 0 文本抽取 | ✅ 完成 2026-09-04 | source/ 42 个章节 txt，373,575 字，UTF-8 验证通过 |
| 1 整书理解 (Adler) | ✅ 完成 2026-09-04 | stage0/report-A~F.md + BOOK_OVERVIEW.md（骨架已获用户确认） |
| 2 并行提取 (5 extractor) | ✅ 完成 2026-09-04（降级串行） | candidates/：框架57 原则98 反例70 案例72 术语45 |
| 3 三重验证 | ✅ 完成 2026-09-04 | verified.md（28 单元全过）+ rejected/_index.md（127 条去向） |
| 4 RIA++ 构造 | ✅ 完成 2026-09-05 | **28 个** <skill-slug>/SKILL.md（六段齐全，related_skills 已回填；首批 15 + 补齐 13） |
| 5 Zettelkasten 链接 | ✅ 完成 2026-09-05 | INDEX.md（28 skill 全览 + mermaid 引用图 38 条关系 + 学习顺序）+ GLOSSARY.md（45 术语） |
| 6 压力测试 | ✅ 完成 2026-09-05 | 两批 197 条盲测（6 个干净 agent，隐藏预期）；首轮 95%，2 处兄弟 skill 触发歧义修复并独立重测、1 条漏判诱饵补测 → **197/197**；诱饵容错 0；test-results.md |
| 7 交付 | ✅ 完成 2026-09-05 | DIGEST.md（约 6.5k 字）+ README.md（用户额外要求，已更新至 28 skill）；按用户决策**不安装**，仓库形式交付 |

## 文本分块（供 extractor 使用，含 BOOK_OVERVIEW 锚点）

| 块 | 文件 | 字数 |
|---|---|---|
| A 序言+第一部分 | 00-序言 ~ 09-第9章 | ~91k |
| B 第二部分 启发式与偏差 | 10-第10章 ~ 18-第18章 | ~66k |
| C 第三部分 过度自信 | 19-第19章 ~ 24-第24章 | ~58k |
| D 第四部分 选择 | 25-第25章 ~ 34-第34章 | ~90k |
| E 第五部分+结论 | 35-第35章 ~ 39-结论 | ~38k |
| F 附录A+B | 40-附录A, 41-附录B | ~35k |

## 断点记录

- 2026-09-04: 计划批准；epub 抽取成功（extract_epub.py 可重跑）。
- 2026-09-04: 阶段 1（整书理解）完成——6 个分块精读 agent（块A~F）产出 stage0/report-A~F.md（含 109 条方法论候选、200+ 案例、137 反例、200+ 术语，均带逐字引用与章节号）；BOOK_OVERVIEW.md 已合成并通过用户骨架确认。
- **降级决策（阶段 2 提取）**: 环境实测并发上限 ≈2 个 agent（user concurrency limit exceeded），且单 agent 全书扫描耗时 >10 分钟。按 SKILL.md"并行降级"条款：5 个 extractor 两两串行，各自以"干净视角"基于 6 份精读报告独立提取 + 对引用做原文抽查核验（共核验 97 处），产出格式不变。
- 2026-09-04: 阶段 1.5 完成——155 条候选合并去重后 28 个单元全部通过 V1/V2/V3（verified.md + rejected/_index.md）；确认点用户未答复，按推荐方案构建核心 15 个（其余 13 个记入 INDEX"已验证待建"）。
- 2026-09-04: 阶段 2-3 完成——15 个 SKILL.md（R/I/A1/A2/E/B 六段+frontmatter trigger 描述+related_skills）、INDEX.md、GLOSSARY.md、test-prompts.json ×15（每套含 ≥1 条兄弟 skill 混淆诱饵）。
- 2026-09-04: 阶段 4 盲测——3 组后台 agent 分担 15 个 skill（隐藏 expected/notes，仅给 SKILL.md+兄弟清单+prompt）；组1 首跑因 user concurrency limit exceeded 失败后重试成功。首轮 101/105，1 条真失败（wide-frame↔fourfold 触发歧义）按方法论修 skill 后单案重测通过；2 条灰色 edge 与 1 条判卷脚本关键词漏配均已人工复核记录。第一批最终 105/105。
- 2026-09-05: **用户指示"全部补齐"**——13 个已验证单元全部建成（SKILL.md 六段+frontmatter+related_skills，测试用例 92 条），INDEX/README/test-results 同步更新至 28 skill。第二批盲测 3 组 agent（兄弟清单扩至 28；组5 首跑因 model concurrency limit exceeded 失败后重试成功）：首轮严格判卷 87/92，1 条真失败（small-sample↔precheck 歧义，修 description 认领"就试一次但感觉特别准"信号并写明与 precheck 的链式分工）后单案重测通过；另 1 条漏判诱饵（wysiati"今天好累啊"）由独立 agent 补测回填；灰色 edge 均已人工复核记录。**全部 28 skill 通过：197/197，诱饵容错 0。流水线整体完成。**
