# skill-bookshelf 📚

把书籍蒸馏成 **AI Skills** 的总目录导航。

> 每一本书通过 cangjie-skill（仓颉蒸馏流水线）的 RIA-TV++ 流程，
> 被蒸馏成一组**原子化、可被 AI Agent 在真实场景调用**的技能（skills）。
> 本仓库是所有已上传蒸馏书的统一入口——从这里可以找到每一本书的完整蒸馏仓库。

---

## 目录总览

**3 本书 · 27 个 skills**（最后更新：2026-08-18）

| 书名 | 作者 / 年份 | 主题 | Skills | 仓库 |
|---|---|---:|---|
| 《心流》*Flow* | 米哈里·契克森米哈赖 · 1990 | 心流 / 注意力 / 意义 | 8 | [flow-skills](https://github.com/wxyqx/flow-skills) |
| *Ready, Fire, Aim* | Michael Masterson · 2008 | 创业 / 销售 / 营销 | 11 | [ready-fire-aim-skills](https://github.com/wxyqx/ready-fire-aim-skills) |
| 《人性的弱点》 | 戴尔·卡耐基 · 1936 | 人际关系 / 说服 | 8 | [how-to-win-friends-skills](https://github.com/wxyqx/how-to-win-friends-skills) |

---

## 逐本详情

### 1. 《心流：最优体验心理学》 — *Flow: The Psychology of Optimal Experience*

- **作者**：米哈里·契克森米哈赖（Mihaly Csikszentmihalyi）· 1990
- **仓库**：[flow-skills](https://github.com/wxyqx/flow-skills) · 8 个 skills
- **一句话**：幸福不能直接追求——它是你全身心投入一件有挑战性的活动时，作为副产品自然涌现的最优体验。
- **Skills**：`flow-channel-trigger` · `pleasure-vs-enjoyment` · `flow-activity-designer` · `attention-audit` · `adversity-converter` · `life-theme-builder` · `meaning-spiral-assessor` · `action-reflection-balance`

### 2. *Ready, Fire, Aim*

- **作者**：Michael Masterson · 2008
- **仓库**：[ready-fire-aim-skills](https://github.com/wxyqx/ready-fire-aim-skills) · 11 个 skills
- **一句话**：创业先开枪再瞄准——用快速试错替代"准备完美再开始"的瘫痪，覆盖从获客、定价、销售到组织诊断的一整套增长方法。
- **Skills**：`ready-fire-aim` · `allowable-acquisition-cost` · `bottleneck-diagnosis` · `four-stages-of-growth` · `free-market-management` · `front-end-back-end-marketing` · `incremental-degradation` · `marketing-four-legged-stool` · `optimum-selling-strategy` · `tipping-point-innovation` · `unique-selling-proposition`

### 3. 《人性的弱点》 — *How to Win Friends and Influence People*

- **作者**：戴尔·卡耐基（Dale Carnegie）· 1936
- **仓库**：[how-to-win-friends-skills](https://github.com/wxyqx/how-to-win-friends-skills) · 8 个 skills
- **一句话**：人是被「重要感」驱动的生物——你能让别人感到自己重要，就能赢得合作；你打击别人的自尊，就永远树敌。
- **Skills**：`listening-as-persuasion` · `bait-the-fish-thinking` · `argument-avoidance` · `yes-ladder-socratic` · `preemptive-self-criticism` · `face-saving-feedback` · `micro-progress-praise` · `reputation-anchoring`

---

## 规划中

| 书名 | 作者 | 状态 |
|---|---|---|
| 《经济学原理（微观分册）》 | N. Gregory Mankiw | OCR 处理中，待蒸馏 |

---

## 如何添加一本新书

每蒸馏并上传一本新书，把它的入口登记到这个索引里，保持三步同步：

1. **上传蒸馏仓库**到 GitHub（命名约定：`<book-slug>-skills`，公开）；
2. 在「目录总览」表格里加一行，并把「N 本书 · M 个 skills」的计数加 1；
3. 在「逐本详情」里追加一个 `###` 小节，包含作者 / 仓库链接 / 一句话主旨 / Skills 列表。

字段从该书的 `README.md` 顶部「来源」表格和 `docs/INDEX.md` 里直接取，不必重新总结。
