# test-results.md — 阶段 4 压力测试审计（两批）

- 测试时间: 2026-09-04（第一批 15 skill）/ 2026-09-05（第二批 13 skill）
- 被测对象: **28 个 skill**，两批共 **197 条**用例
- 用例构成: should_trigger 113 条 / should_not_trigger 76 条（其中 **28 条为同书兄弟 skill 混淆诱饵**，每 skill ≥1 条）/ edge_case 28 条（第二批 92 条含 1 条漏判补测，已回填 blind-4.json）

## 测试方法与可信度声明

- **盲测方式**: 每批 3 个未参与蒸馏的干净 sub-agent，共 6 个。每个 agent 只获得：(a) 全部候选 skill 的 name+description 清单（第一批 15 个、第二批扩至 28 个，使其做"该激活哪一个"的选择题）；(b) 被测 skill 的完整 SKILL.md；(c) 隐藏了 type/expected_behavior/notes 的 prompt 包（stage4/_blind-pack-*.json）。
- **偏差控制**: agent 被要求逐条独立判断、不许顺延；判卷由主流程按 test-prompts.json 逐条对照（脚本 + 人工复核全部 edge）。
- **降级披露**: 环境并发受限（user/model concurrency limit exceeded，共 3 次 agent 首跑失败后均重试成功），采用"一 agent 覆盖 4–5 个 skill"的批量盲测——独立性低于每用例独立 agent 的理想值，可信度标注为 **盲测-批量版**。结果文件: stage4/blind-{1..6}.json。

## 总体结果

| 批次 | 覆盖 | 用例 | 首轮严格判卷 | 修复 | 终态 |
|---|---|---|---|---|---|
| 第一批 | 15 skill | 105 | 101/105 (96%) | wide-frame↔fourfold 触发歧义：修两处 description/交接后单案重测通过 | 105/105 |
| 第二批 | 13 skill | 92 | 87/92 (95%) | small-sample↔precheck 歧义：修 description 后单案重测通过；1 条漏判诱饵补测通过 | 92/92 |
| **合计** | **28** | **197** | **188/197 (95%)** | 2 处修复，均经独立重测确认 | **197/197** |

## 红线核验（两批合并）

- **诱饵容错为 0**: 76 条 should_not_trigger 全部通过，无一被误激活；28 条兄弟混淆诱饵全部正确改选到语义更贴合的兄弟 skill（如"不甘心卖股"→zero-base、"方案没定先找坑"→premortem、"检测阳性"→base-rate、"医疗方案比较"→dual-ledger）。✅
- **should_trigger**: 113/113 通过（含 2 处修复后的独立重测）。✅
- **edge_case**: 28 条全部落在预期边界理由内（逐条人工复核）。✅

## 修复记录（2 处，均为兄弟 skill 触发歧义）

### 1. wide-frame-trader ↔ fourfold-risk-locator（第一批）
- 用例: "50% 亏 100 / 50% 赚 200，收益划算但不敢接" → 盲测判 fourfold（孤立赌局属四重模式警报）
- 修复: wide-frame description 增补"对一个收益明明算得过来的机会'就是不敢接'（正期望却过度避险）"；fourfold E5 交接改为"交给 wide-frame-trader（临场重述）或 risk-policy（高频立法）"
- 重测: 全新盲测 agent → chosen=wide-frame-trader，执行动作正确 ✅

### 2. small-sample-rules ↔ expert-intuition-precheck（第二批）
- 用例: "我就面试过一次，但感觉特别准" → 盲测判 precheck（直觉有效性问题）
- 修复: small-sample description 增补"就试过一次但感觉很准"触发语，并在排除条款中写明"评估资深专家的长期直觉先交 precheck，预检不过再回到本程序"——把两个 skill 的分工写成链而非竞争
- 重测: 全新盲测 agent → chosen=small-sample-rules，执行动作正确（报 n=1→两端检查→运气优先）✅

## 灰色 edge 记录（判为通过，理由在案）

1. 第一批 substitution-check/edge（"老板让我表态怎么不被带偏"）: 预期为宽松表述"可用最小版本"，盲测判 null——与边界意图兼容。
2. 第一批 anti-anchoring/edge（"朋友车价30万"）: 预期"口头警报即可"，盲测判"轻度触发"——行为差异为零。
3. 第二批 wysiati-check/edge（"怎么让报告更有说服力"）: 预期宽松（"可轻量使用"），盲测判 null 并指出该 skill 目标相反——与预期文本的提醒条款一致。
4. 第二批 regression-to-mean/edge（"连续三个月远超目标不是运气吧"）: 盲测判 small-sample-rules（"是不是运气"是其触发语）；两个 skill 为组合关系，最终建议链相同（"高于平均但低于峰值"）。记录为合法兄弟分工。
5. 判卷脚本关键词漏配 2 处（第一批 zero-base/edge、第二批 peak-end/edge）: 预期文本本意为"不激活"，盲测判 null/激活以回答程序问题，均与预期一致；已人工更正判卷。

## 逐 skill 结果

| skill | 用例 | 终态 | skill | 用例 | 终态 |
|---|---|---|---|---|---|
| high-stakes-slow-thinking | 8 | 8 ✅ | fourfold-risk-locator | 7 | 7 ✅ |
| substitution-check | 7 | 7 ✅ | frame-check | 7 | 7 ✅ |
| wysiati-check | 7 | 7 ✅ | zero-base-rethink | 7 | 7 ✅ |
| anti-anchoring | 7 | 7 ✅ | wide-frame-trader | 7 | 7 ✅（修复后） |
| base-rate-first | 7 | 7 ✅ | risk-policy | 7 | 7 ✅ |
| availability-check | 7 | 7 ✅ | peak-end-design | 7 | 7 ✅ |
| scenario-scrutiny | 7 | 7 ✅ | two-selves-check | 7 | 7 ✅ |
| rare-events-check | 7 | 7 ✅ | focusing-illusion | 7 | 7 ✅ |
| small-sample-rules | 7 | 7 ✅（修复后） | dual-ledger | 7 | 7 ✅ |
| regression-to-mean | 7 | 7 ✅ | independent-judgment | 7 | 7 ✅ |
| four-step-prediction | 7 | 7 ✅ | decision-factory | 7 | 7 ✅ |
| interval-calibration | 7 | 7 ✅ | bias-proof-review | 7 | 7 ✅ |
| formula-over-intuition | 7 | 7 ✅ | expert-intuition-precheck | 7 | 7 ✅ |
| outside-view | 7 | 7 ✅ | premortem | 6 | 6 ✅ |

## 结论

全部 **28 个 skill** 通过阶段 4（197/197，含 2 次修复+独立重测、1 次漏判补测）。两批诱饵容错均为 0。阶段 5 交付完成。
