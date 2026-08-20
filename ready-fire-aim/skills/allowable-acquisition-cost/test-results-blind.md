# Blind Test Results — allowable-acquisition-cost

| id | would_trigger | reason | if_triggered_action | best_alternative_skill |
|---|---|---|---|---|
| should-trigger-01 | yes | 用户准备投放信息流广告，但老板询问预算上限，且团队对“越多越好”与“首单必须盈利”存在分歧，需要一个理性的获客成本计算框架。 | 1. 计算客户终身毛利（Lifetime Gross Profit）；2. 扣除 overhead 分摊和期望利润，得到可承受获客成本 AAC；3. 用 AAC 评估各渠道预算上限并设定止损点。 | none |
| should-trigger-02 | yes | 用户设计订阅制会员产品，想用低价甚至免费试用获客，投资人质疑是否烧钱，需要把获客成本摊到客户生命周期中评估。 | 1. 基于订阅周期、留存率、毛利率计算 Lifetime Gross Profit；2. 推导 AAC 并明确首次亏损边界；3. 设定 CAC ≤ AAC 的放量条件与止损点。 | none |
| should-trigger-03 | yes | 团队内部争论是否“烧钱获客”，销售与财务对首单是否必须盈利有分歧，需要用数字讲清楚可承受的获客边界。 | 1. 用客户终身毛利倒推 AAC；2. 明确 CAC ≤ AAC 的放量条件，以及 AAC ≤ 0 时的判停条件；3. 帮助团队用统一数字框架达成共识。 | none |
| should-not-trigger-01 | no | 用户问的是复购率低、该设计什么后端产品让客户继续消费，核心是前后端产品组合与客户终身价值路径设计，不是计算获客成本上限。 | N/A | front-end-back-end-marketing |
| should-not-trigger-02 | no | 团队同时尝试多个渠道但不知道哪个值得加大投入，核心是先找到有效的获客组合，再给组合定财务边界。 | N/A | optimum-selling-strategy |
| should-not-trigger-03 | no | 这是个人税务计算请求，与获客成本、客户终身价值完全无关。 | N/A | none |
| edge-01 | no | 客户生命周期仅一周、基本只购买一次且无后端产品，属于 AAC 明确不适用的一次性生意场景，首次销售必须盈利。 | N/A | none |
