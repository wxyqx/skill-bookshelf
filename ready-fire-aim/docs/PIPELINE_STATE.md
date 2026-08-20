# Pipeline State — Ready, Fire, Aim

## 当前阶段
阶段 5 — 交付：已完成。

## 已完成
- [x] EPUB 文本提取并切分为 chunk_000.txt ~ chunk_012.txt
- [x] 生成 BOOK_OVERVIEW.md 并经用户确认
- [x] 阶段 1：5 个提取器并行抽取候选方法论
  - frameworks.md: 29 条
  - principles.md: 35 条
  - cases.md: 28 条
  - counter-examples.md: 19 条
  - glossary.md: 12 条
- [x] 阶段 1.5：三重验证筛选
  - verified.md: 14 条（11 框架 + 3 反例）
  - rejected/: 78 条
  - shared_terms: 12 条
- [x] 阶段 2：为 11 个框架构造 SKILL.md（R/I/A1/A2/E/B 六段完整）
- [x] 阶段 3：建立 skill 间链接关系，生成 INDEX.md 与 GLOSSARY.md
- [x] 阶段 4：压力测试
  - 11 个 skill 均通过，通过率 100%（7/7）
  - 每个 skill 均有 test-prompts.json 与 test-results.md
- [x] 阶段 5：交付
  - 生成 DIGEST.md（约 5600 中文字）
  - 安装 11 个 skill 到 `e:\solo\.trae\skills\`

## 产出清单

| 产出 | 路径 |
|---|---|
| 整书理解 | `e:\solo\books\ready-fire-aim\BOOK_OVERVIEW.md` |
| 候选池 | `e:\solo\books\ready-fire-aim\candidates\` |
| 验证池 | `e:\solo\books\ready-fire-aim\verified.md` |
| 淘汰池 | `e:\solo\books\ready-fire-aim\rejected\` |
| Skill 总览 | `e:\solo\books\ready-fire-aim\INDEX.md` |
| 术语词典 | `e:\solo\books\ready-fire-aim\GLOSSARY.md` |
| 精华长文 | `e:\solo\books\ready-fire-aim\DIGEST.md` |
| 已安装 skills | `e:\solo\.trae\skills\<skill-slug>\` |

## 可用命令

持续进化：`darwin evolve books/ready-fire-aim/`
