# 人性的弱点 — 流水线状态

> 蒸馏对象: 《人性的弱点》 戴尔·卡耐基 (1936)
> 蒸馏工具: cangjie-skill RIA-TV++
> 开始时间: 2026-08-16
> 完成时间: 2026-08-16

## 流水线状态

| 阶段 | 状态 | 产出文件 |
|---|---|---|
| 0 — 整书理解 (Adler) | ✅ 完成 | BOOK_OVERVIEW.md |
| 1 — 并行提取 | ✅ 完成 | candidates/ (5个文件, 64个候选) |
| 1.5 — 三重验证 | ✅ 完成 | verified.md (64→8) |
| 2 — RIA++ 构造 skill | ✅ 完成 | 8 个 `<skill-slug>/SKILL.md` |
| 3 — Zettelkasten 链接 | ✅ 完成 | INDEX.md, GLOSSARY.md |
| 4 — 压力测试 | ✅ 完成 | 8×test-prompts.json, test-results.md |
| 5 — 交付 | ✅ 完成 | DIGEST.md + .trae/skills/ + README.md |

## 交付清单

- ✅ 8 个 skill 已安装到 `.trae/skills/`
- ✅ DIGEST.md 精华长文 (~6500字)
- ✅ README.md 项目说明
- ✅ INDEX.md skill 总览 + 引用图
- ✅ GLOSSARY.md 共享术语词典
- ✅ test-results.md 压力测试报告 (96.9% 通过率)

## 8 个 Skills

1. `bait-the-fish-thinking` — 钓鱼思维 (100% 通过)
2. `argument-avoidance` — 争辩避免术 (100% 通过)
3. `preemptive-self-criticism` — 认错先行术 (100% 通过)
4. `yes-ladder-socratic` — Yes-Ladder 苏格拉底法 (91.7% 通过)
5. `listening-as-persuasion` — 倾听引导法 (83.3% 通过)
6. `face-saving-feedback` — 面子保全批评法 (100% 通过)
7. `micro-progress-praise` — 赞美微进步 (100% 通过)
8. `reputation-anchoring` — 声誉锚定 (100% 通过)

## 已知问题

- `listening-as-persuasion` 的 description 未覆盖"投诉处理"场景，导致 "客户来投诉" prompt 误触发 preemptive-self-criticism。建议在 darwin-skill 自动进化阶段修复。
