# INDEX — 曼昆微观经济学 Skill 总览与引用图

> 阶段 3 产出：Zettelkasten 链接

---

## Skill 总览

| # | Skill 名称 | slug | 核心功能 | 对应章节 |
|---|-----------|------|---------|---------|
| 1 | 经济学十大原理决策框架 | `econ-ten-principles` | 用 10 条原理快速搭建经济学思维脚手架 | Ch1 |
| 2 | 比较优势与贸易决策 | `comparative-advantage` | 通过机会成本比较确定最优分工与贸易 | Ch3 |
| 3 | 供需均衡分析框架 | `supply-demand-analysis` | 四步法分析市场冲击对价格和数量的影响 | Ch4-Ch6 |
| 4 | 福利经济学与成本收益分析 | `welfare-cost-benefit` | 用剩余分析评价政策/项目的效率与分配 | Ch7-Ch8 |
| 5 | 市场失灵诊断框架 | `market-failure-diagnosis` | 系统识别市场失灵类型并匹配政策工具 | Ch10-Ch11 |
| 6 | 市场结构分析框架 | `market-structure-analysis` | 从竞争到垄断的连续谱分析，预测企业行为 | Ch13-Ch17 |

---

## 引用关系图

```
econ-ten-principles (元框架 · 入口)
    │
    ├── 原理五 ──→ comparative-advantage (贸易获益原理的具体化)
    │
    ├── 原理六 ──→ supply-demand-analysis (市场优化原理的具体化)
    │                    │
    │                    └──→ welfare-cost-benefit (供需分析的效率评价延伸)
    │
    ├── 原理七 ──→ market-failure-diagnosis (政府改善市场的深化)
    │                    ↑
    │                    └── welfare-cost-benefit (衡量失灵的福利损失)
    │
    └── 原理六/七 ─→ market-structure-analysis (企业层面的市场与失灵)
                         ↑
                         └── supply-demand-analysis (供需分析的企业层面扩展)
```

### 核心引用链

1. **入门路径**：`econ-ten-principles` → `supply-demand-analysis` → `welfare-cost-benefit`
   - 从原理到工具，从定性到定量

2. **贸易路径**：`econ-ten-principles` → `comparative-advantage` → `welfare-cost-benefit`
   - 为什么贸易好 → 怎么贸易 → 贸易的福利分配

3. **失灵路径**：`supply-demand-analysis` → `market-failure-diagnosis` → `welfare-cost-benefit`
   - 理想市场 → 市场失灵 → 失灵的代价

4. **产业路径**：`supply-demand-analysis` → `market-structure-analysis` → `market-failure-diagnosis`
   - 竞争市场 → 不完全竞争 → 市场势力导致的失灵

---

## 决策树：该用哪个 Skill？

```
用户提出问题
    │
    ├─ 是经济学入门问题 / 需要快速诊断？
    │   → econ-ten-principles 【入口级】
    │
    ├─ 涉及分工/贸易/专业化决策？
    │   → comparative-advantage
    │
    ├─ 涉及市场价格/数量变化？
    │   ├─ 竞争市场 → supply-demand-analysis
    │   └─ 企业定价/行业竞争 → market-structure-analysis
    │
    ├─ 涉及政策效率评价/成本收益？
    │   → welfare-cost-benefit
    │
    ├─ 涉及市场为什么不好用/需要政府干预？
    │   ├─ 外部性/公共物品/公地悲剧 → market-failure-diagnosis
    │   └─ 垄断/寡头/市场势力 → market-structure-analysis
    │
    └─ 涉及企业行为/产业分析/竞争策略？
        → market-structure-analysis
```

---

## Skill 间的依赖关系

| Skill | 前置依赖 | 后续延伸 |
|-------|---------|---------|
| `econ-ten-principles` | 无（元框架） | 所有其他 skill |
| `comparative-advantage` | econ-ten-principles（原理五） | welfare-cost-benefit（贸易福利分配） |
| `supply-demand-analysis` | econ-ten-principles（原理六） | welfare-cost-benefit、market-structure-analysis、market-failure-diagnosis |
| `welfare-cost-benefit` | supply-demand-analysis | market-failure-diagnosis（衡量失灵损失） |
| `market-failure-diagnosis` | supply-demand-analysis、welfare-cost-benefit | （政策设计） |
| `market-structure-analysis` | supply-demand-analysis | market-failure-diagnosis（市场势力失灵） |

---

## 与书中章节的对应

| 书中篇章 | 对应 Skill | 备注 |
|---------|-----------|------|
| 第 1 篇 导言（Ch1-Ch3） | econ-ten-principles、comparative-advantage | 思维基础 |
| 第 2 篇 市场如何运行（Ch4-Ch6） | supply-demand-analysis | 核心工具 |
| 第 3 篇 市场和福利（Ch7-Ch9） | welfare-cost-benefit、comparative-advantage | 效率评价 |
| 第 4 篇 公共部门经济学（Ch10-Ch12） | market-failure-diagnosis、welfare-cost-benefit | 失灵与政策 |
| 第 5 篇 企业行为与产业组织（Ch13-Ch17） | market-structure-analysis | 供给曲线背后 |
| 第 6 篇 劳动市场经济学（Ch18-Ch20） | supply-demand-analysis（要素市场应用） | 供需工具的应用 |
| 第 7 篇 前沿（Ch21-Ch22） | 无对应独立 skill | 拓展内容，行为经济学等 |

---

## 概念层级结构

```
经济学思维
├── 决策层
│   ├── 权衡取舍
│   ├── 机会成本
│   ├── 边际分析
│   └── 激励反应
├── 交易层
│   ├── 比较优势
│   ├── 供需均衡
│   └── 市场效率
├── 市场结构层
│   ├── 完全竞争
│   ├── 垄断竞争
│   ├── 寡头（博弈论）
│   └── 垄断
├── 失灵层
│   ├── 外部性
│   ├── 公共物品
│   ├── 公共资源
│   └── 市场势力
└── 评价层
    ├── 效率（总剩余、DWL）
    └── 平等（分配）
```
