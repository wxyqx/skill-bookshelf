# Blind Test Results — incremental-degradation

| id | would_trigger | reason | if_triggered_action | best_alternative_skill |
|---|---|---|---|---|
| should-trigger-01 | yes | 用户描述了多次小改动（减少客户成功支持、 onboarding 改全自助）单次均通过 A/B 测试，但 18 个月后整体留存率大幅下降，这是“单次无害、累积有害”的渐进退化典型机制。 | 1. 选定一个能代表 USP 的历史版本作为“原始基准”，定义 3–5 个核心指标（响应速度、人工支持比例、核心功能完成率、NPS、复购率等）；2. 列出从基准到现在的主要改动，评估单独影响与累积影响，识别退化源；3. 制定 3 项以内的小改进计划，并设立每季度对照原始基准的复盘机制。 | none |
| should-trigger-02 | yes | 用户描述 USP 变得普通、和竞品越来越像，且因降本增效的小改动累积导致产品“变了味”，符合 USP 随时间弱化的渐进退化场景。 | 1. 建立原始基准版本并定义 USP 关键指标；2. 将当前版本与基准做整体对照，检查 USP 关键指标是否退化；3. 制定让产品保持独特卖点的小改进计划并设立季度复盘机制。 | none |
| should-trigger-03 | yes | 用户指出团队把“维持现状”当目标、KPI 只关注不出现故障、畅销产品长期未主动改进而竞品在进步，这正是“不改进=退化”的核心洞察场景。 | 1. 为畅销产品建立原始基准版本与 USP 关键指标；2. 将当前版本与基准对照，识别相对市场退化点；3. 重新定义“维护”为持续小改进，制定 3 项以内改进动作并设立季度复盘。 | none |
| should-not-trigger-01 | no | 用户说的是现有产品增长放缓、需要找到下一款接力的增长品、想在已有趋势上做微创新，这是推出新产品的 tipping-point-innovation 场景，而非维护现有产品不退化。 | N/A | tipping-point-innovation |
| should-not-trigger-02 | no | 用户的核心需求是找到差异化定位、回答“我们和 XX 有什么区别”，属于 USP 定位/重建问题，尚未到防止已有 USP 退化的阶段。 | N/A | unique-selling-proposition |
| should-not-trigger-03 | no | 用户描述的是系统昨晚崩溃的重大事故，需要紧急排查修复，属于危机处理，不是多次小改动累积造成的渐进退化。 | N/A | none |
| edge-01 | edge | 产品尚未上市，只有原型和早期测试数据，尚未验证市场，此时不存在“退化”问题；但用户主动希望提前建立基准对照机制，意图与本 skill 相关，故判为边界。 | N/A | ready-fire-aim |
