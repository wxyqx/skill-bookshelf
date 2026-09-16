# 《权力的48条法则》 — AI Skill 蒸馏项目

> 使用 [cangjie-skill](https://github.com/alchaincyf/cangjie-skill) 的 RIA-TV++ 流水线，将罗伯特·格林的《权力的48条法则》蒸馏为一组可被 AI agent 调用的原子化 skill。

## 书籍信息

| 项目 | 内容 |
|---|---|
| 标题 | 《权力的48条法则》(The 48 Laws of Power) |
| 作者 | 罗伯特·格林 (Robert Greene) |
| 出版年份 | 1998 (中文译本 2007) |
| 内容类型 | 方法论 / 实操手册 |
| 源文件 | EPUB 中文译本 → `full-text.txt` |

## 一句话主旨

权力是一场文明化的战争——你必须学会用迂回、隐蔽、耐心的手段操控人心与局势，而非依赖暴力或直白的力量对抗。

## 流水线状态

| 阶段 | 名称 | 状态 | 产出文件 |
|---|---|---|---|
| 0 | 整书理解 (Adler) | ✅ 完成 | `BOOK_OVERVIEW.md` |
| 1 | 并行提取 | ✅ 完成 | `candidates/` (5 个文件, 151 个候选) |
| 1.5 | 三重验证 | ✅ 完成 | `verified.md` (15 个通过) + `rejected/REJECTED.md` |
| 2 | RIA++ 构造 skill | ✅ 完成 | 15 个 skill 目录 (各含 `SKILL.md` + `test-prompts.json`) |
| 3 | Zettelkasten 链接 | ✅ 完成 | `INDEX.md` + `GLOSSARY.md` |
| 4 | 压力测试 | ✅ 完成 | `test-results.md` (90/90 = 100% 通过) |
| 5 | 交付 | ✅ 完成 | `DIGEST.md` + 15 个 skill 已安装到 `.trae/skills/` |

## 目录结构

```
power-48-laws/
├── README.md                  ← 本文件
├── docs/
│   ├── BOOK_OVERVIEW.md        ← 阶段0: 整书结构/批判/应用潜力
│   ├── PIPELINE_STATE.md       ← 流水线状态追踪
│   ├── candidates/             ← 阶段1: 原始候选池
│   │   ├── frameworks.md       (25 个框架候选)
│   │   ├── principles.md       (63 条原则: 48条法则 + 15条子原则)
│   │   ├── cases.md            (30 个历史案例)
│   │   ├── counter-examples.md (15 个反例/失败模式)
│   │   └── glossary.md         (18 条关键术语)
│   ├── rejected/               ← 阶段1.5: 淘汰单元 + 原因
│   ├── verified.md             ← 阶段1.5: 15 个通过三重验证的候选
│   ├── INDEX.md                ← 阶段3: skill 总览 + 引用图
│   ├── GLOSSARY.md             ← 阶段3: 共享术语词典
│   ├── DIGEST.md               ← 阶段5: 面向读者的精华长文 (~8000字)
│   └── test-results.md         ← 阶段4: 压力测试结果 (100% 通过)
└── skills/                    ← 阶段2: 15 个独立 skill
    ├── indirect-approach/
    ├── emotion-mastery/
    ├── conceal-intent/
    ├── silence-power/
    ├── reputation-strategy/
    ├── enemy-to-ally/
    ├── manage-superior/
    ├── result-judgment/
    ├── patience-shield/
    ├── people-reading/
    ├── strategic-surrender/
    ├── detect-deception/
    ├── command-attention/
    ├── selective-honesty/
    └── cost-assessment/
        └── (各含 SKILL.md + test-prompts.json)
```

## 候选池概览

### 框架 (25 个)

从前言和法则中提取的可迁移思维模型，代表性候选：

- **f01 迂回前进艺术** — 权力获取的元方法论：间接路线 > 直接冲击
- **f02 双面守护神思维** — 同时保持两个矛盾面向的能力
- **f03 情绪控制框架** — 权力的基石是控制自己的愤怒、爱和恐惧

### 原则 (63 条)

- **p01-p48**: 全书48条法则本身（如"永远不要盖过上司的光芒"）
- **p49-p63**: 从"权力要点"部分提取的子原则

### 案例 (30 个)

跨越3000年历史权力案例，代表性：

- **c01 富凯的豪华宴会** — 1661年，盖过国王光芒的下场
- **c02 路易十四的凡尔赛宫** — 用对手的建筑师建造更华丽的宫殿

### 反例 (15 个)

失败模式和陷阱预警，代表性：

- **ce01 盖过上司光芒的灾难** — 炫耀才华如何引发上级不安全感
- **ce02 过度信任朋友的背叛** — 信任如何成为权力弱点

### 术语 (18 条)

核心概念及其与常识的差异，代表性：

- **g01 权力** — 泛指控制力和操纵力，不限于政治权谋
- **g02 迂回** — 间接手段达到目的，像台球回弹后击中目标

## 三重验证标准 (阶段 1.5)

每个候选必须通过三项检验才能进入 skill 构造：

| 验证 | 名称 | 标准 |
|---|---|---|
| V1 | 跨域验证 | 原文中至少有 2 处独立语境的佐证 |
| V2 | 预测力测试 | 能推导出原文未明说问题的答案 |
| V3 | 独特性检验 | 非常识性见解，不能是"大家都知道"的东西 |

历史通过率通常为 25-50%，本项目从 151 个候选中筛选出 15 个 skill（通过率 ~10%）。

## 已交付 skill 列表

通过三重验证的 15 个 skill，按分类组织：

### 自我管理
1. **emotion-mastery** — 控制愤怒和好感遮蔽理性 (法则 1, 38, 39)
2. **patience-shield** — 等待最佳时机的主动策略 (法则 29, 35)

### 信息策略
3. **conceal-intent** — 隐藏真实意图，用烟幕引导对手 (法则 3, 9)
4. **detect-deception** — 识别"天真伪装"和道德高地话术 (法则 2)
5. **people-reading** — 看透他人真实意图与弱点 (法则 33, 43, 44)
6. **result-judgment** — 以结果而非意图判断他人行动 (法则 13)

### 关系博弈
7. **enemy-to-ally** — 将对手转化为盟友的策略 (法则 2)
8. **manage-superior** — 向上管理，不盖过上司光芒 (法则 1)
9. **selective-honesty** — 用选择性诚实缴械对方 (法则 12)
10. **cost-assessment** — 以代价而非收益评估机会 (法则 16)

### 战略行动
11. **indirect-approach** — 迂回前进，不直接暴露目标 (法则 3, 8)
12. **strategic-surrender** — 示弱投降策略，麻痹对手 (法则 20, 40)

### 形象影响
13. **reputation-strategy** — 声誉的建立、防御与攻击 (法则 5)
14. **command-attention** — 引人注目而非被遗忘 (法则 16)
15. **silence-power** — 沉默威慑与信息控制 (法则 3, 4)

## 源文本说明

原始 EPUB 转换为文本时存在已知问题：

- 全文约 2380 万字符，但存在大量重复内容（EPUB 结构问题）
- 有效内容范围：前言 + 法则 1-6 的完整正文
- 法则 7-48 仅有标题和一句话摘要
- 候选提取基于可用文本完成，后续如获取完整文本可补充

## 如何使用

### 阅读精华

阅读 [`DIGEST.md`](./docs/DIGEST.md) — 一篇筛过水分的精华长文（约 8000 字），覆盖所有通过验证的核心方法论、陷阱和作者局限。

### 调用 skill

15 个 skill 已安装到 `.trae/skills/<skill-name>/`，可被 AI agent 在以下场景自动调用：

- 职场权力博弈决策
- 人际关系策略分析
- 谈判与沟通策略
- 个人情绪管理

### 查看技能地图

阅读 [`INDEX.md`](./docs/INDEX.md) 查看所有 skill 的总览、依赖关系和组合方式。

## 质量红线

本项目遵循 cangjie-skill 质量红线：

1. 每个 skill 必须通过全部三重验证 (V1/V2/V3)
2. 每个 skill 必须有完整的 R / I / A1 / A2 / E / B 六段
3. 原文引用 ≤150 字/段
4. 每个 skill 必须有 `test-prompts.json`，含诱饵测试和跨 skill 混淆测试
5. `description` 字段必须明确 trigger 条件

## 工具与方法

- **蒸馏工具**: [cangjie-skill](https://github.com/alchaincyf/cangjie-skill)
- **方法论**: RIA-TV++ (RIA 便签拆书法 + Triple Verification + 面向 agent 的扩展)
- **本地资源**: `e:\solo\cangjie-skill-main\` (方法论文档 + 提取器 prompt + 模板)
