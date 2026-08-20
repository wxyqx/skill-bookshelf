# Ready, Fire, Aim — 三重验证通过候选池

> 本文件由 cangjie-skill 流水线的 triple-verifier 生成。
> 录取标准：V1 跨域验证、V2 预测力测试、V3 独特性检验全部通过。
> 目标：为下游 skill-crafter 提供 10–15 个高价值、可迁移、具作者特色的单元。

---

- id: f01
  title: Ready-Fire-Aim 行动框架
  type: framework
  merged_from:
  - f01
  - p03
  - p04
  - p19
  - f29
  V1_cross_domain:
    passed: true
    evidence:
    - "第 1 章：企业成长的通用行动逻辑，反对'先完美计划再执行'的传统顺序"
    - 第 4 章：婴儿期销售至上的发布三步序列——ready enough → sell → improve if it sells
    - "第 11 章（Speed）：把'加速失败'作为学习机制，快速测试多数会被拒绝的想法"
    - 第 17 章：将该方法迁移到个人目标（电影、纪录片、房地产、音乐专辑）
  V2_predictive_power:
    passed: true
    novel_question: 一位软件工程师想转型独立咨询，但总觉得要先考证书、建网站、写完美提案，该如何启动？
    derived_answer: 她应在 48 小时内用一个简单报价向 5 位潜在用户发起对话，争取一份有偿试点；用试点反馈决定服务边界与定价，而不是用三个月准备。结论是：首笔收入和真实反馈会在数周内到来，产品形态将由市场而非想象塑造。
  V3_exclusivity:
    passed: true
    why_not_common: "不是泛泛的'行动力很重要'，而是把'准备—瞄准—开火'的古老顺序颠倒为'准备—开火—瞄准'，并给出'Ready enough'的启动阈值与'在反馈中修正'的闭环。普通聪明人会说'先干起来'，但不会把行动本身定义为最主要的学习机制。"
  source_quote: '"Get the product ready enough to sell it, but don''t worry about perfecting it. Sell it. Then, if it sells, make it better. That''s the smart way to launch a business."'
  tags:
  - 行动决策
  - 快速试错
  - 创业验证
  - 个人目标


- id: f02
  title: 四阶段企业成长诊断模型
  type: framework
  merged_from:
  - f02
  - p05
  - f23
  V1_cross_domain:
    passed: true
    evidence:
    - 第 1–2 章：模型总览，婴儿期（卖）、童年期（快）、青春期（结构）、成年期（财富）
    - 第 4 章：婴儿期与童年期的优先级排序为 Selling → Pushing → Improving → Organizing
    - 第 9 章：童年期通过快速产品创新突破单一产品综合症
    - 第 19–20 章：青春期必须从创业者转变为建立系统的企业领袖
    - 第 24–25 章：成年期创始人应转变为财富建造者，把企业当资产组合管理
  V2_predictive_power:
    passed: true
    novel_question: 一家年收入 200 万美元的营销代理公司增长停滞，创始人仍亲自审批每一份客户交付物，问题出在哪？
    derived_answer: "按四阶段模型，该企业已处于童年期向青春期过渡的节点。童年期的'快速销售与产品创新'策略正变成阻碍：创始人是最大瓶颈。结论是必须引入部门负责人、限制直接汇报人数、把创始人时间从质检转移到战略与教练，否则无法突破规模天花板。"
  V3_exclusivity:
    passed: true
    why_not_common: "大多数阶段模型按营收、员工数或行业惯例划分；该模型按'核心任务与创始人角色'划分，并强调上一阶段的成功策略会变成下一阶段的障碍，因此需要主动转型。"
  source_quote: '"Every entrepreneurial business has these four stages... Stage One: Infancy... Stage Two: Childhood... Stage Three: Adolescence... Stage Four: Adulthood. Each stage has its own unique characteristics in the form of problems, challenges, and opportunities."'
  tags:
  - 成长诊断
  - 阶段模型
  - 战略优先级
  - 创始人角色


- id: f03
  title: 最优销售策略（OSS）
  type: framework
  merged_from:
  - f03
  - p07
  - p08
  - p09
  - p12
  V1_cross_domain:
    passed: true
    evidence:
    - 第 5 章：OSS 定义为媒体、产品、定价、文案主张的可重复组合
    - 第 8 章：Scott Moore 花近三年不断测试不同营销想法，最终找到 OSS
    - 第 9 章：出版公司与香水业务通过快速测试多个 OSS 变量实现高速增长
    - 第 13 章：好想法未实现常因完美主义与琐事，强调快速测试
  V2_predictive_power:
    passed: true
    novel_question: 一家本地面包店想开拓线上销售，但不知道从何入手，如何设计测试？
    derived_answer: 同时测试四个变量：获客渠道（Instagram vs 农贸市场）、首款产品（酸种面包套装 vs 曲奇礼盒）、价格（25 美元 vs 45 美元）、核心信息（手工工艺 vs 便利省心）。结论：不要孤立优化某一个变量，而要找到让单位经济模型为正的可重复组合，然后把 80% 资源投入该组合。
  V3_exclusivity:
    passed: true
    why_not_common: "普通营销建议会讲'找到你的目标客户'或'写个好文案'，但该框架把销售从艺术重构为四个可验证变量的系统，并指出四个答案必须同时成立，缺一即销售锁无法打开。"
  source_quote: '"To determine the optimum selling strategy for your business, you need to answer four questions... 1. Where are you going to find your customers? 2. What product will you sell them first? 3. How much will you charge for it? 4. How will you convince them to buy it?"'
  tags:
  - 获客策略
  - 销售测试
  - 商业验证
  - 四变量系统


- id: f04
  title: 可承受获客成本（AAC）计算框架
  type: framework
  merged_from:
  - f04
  - p11
  - f06
  V1_cross_domain:
    passed: true
    evidence:
    - 第 5 章：给出 AAC 公式——终身毛利减去成本、 overhead 与期望利润
    - 第 7 章：通过降低前端价格与 ROI 目标，快速获取 10,000 名合格客户
    - 第 9 章：前端亏损获客、后端盈利的组合策略反复出现
  V2_predictive_power:
    passed: true
    novel_question: 一款订阅健身应用知道用户平均留存 18 个月、月费 20 美元、毛利率 60%，应花多少钱获客？
    derived_answer: "客户终身毛利 = 18 × 20 × 60% = 216 美元。扣除分摊 overhead 与期望利润后，若 AAC 定为 80 美元，则应用可以在免费试用漏斗中最高花费 80 美元获取一位用户，即使首月免费或首单亏损。结论：把获客从'成本'重新定义为'可承受的投资'，改变定价与营销预算决策。"
  V3_exclusivity:
    passed: true
    why_not_common: "常识认为'亏损获客危险'或'首次销售必须盈利'；该框架反直觉地允许首次亏损，但要求用客户终身毛利倒推严格上限，并与合格客户临界规模（CMQC）联动。"
  source_quote: '"Figure out how much a customer will spend with you, on average, over a lifetime. Deduct the cost of goods from that. Then deduct a percentage of your overhead. And then figure out and deduct how much you want to profit from that customer. The final number is your allowable acquisition cost."'
  tags:
  - 定价策略
  - 客户终身价值
  - 财务决策
  - 合格客户临界规模


- id: f05
  title: 前端/后端营销组合框架
  type: framework
  merged_from:
  - f05
  - p10
  V1_cross_domain:
    passed: true
    evidence:
    - 第 5 章：理想定价组合是前端大幅折扣引流、后端强调品质盈利
    - 第 9 章：出版业务通过前端通讯获客、后端高价产品实现利润，约一半增长来自后端
    - 第 16 章：购买狂热与重复购买机制支撑后端利润
  V2_predictive_power:
    passed: true
    novel_question: 一位职业规划师希望降低获客压力，应如何设计产品组合？
    derived_answer: "设计 19 美元的简历诊断（前端）作为获客品，即使保本或微亏；用 2000 美元的一对一转型教练（后端）获取利润。结论：前端产品的成功与否不应以自身利润衡量，而应以'是否带来愿意购买后端的合格客户'衡量；这改变了产品组合设计逻辑。"
  V3_exclusivity:
    passed: true
    why_not_common: "普通理解把产品线按价格或品类划分；该框架按'客户是否已购买过'划分，并赋予前端'获客'、后端'盈利'两种战略使命，允许前端亏损。"
  source_quote: '"The purpose of the front-end sale is to acquire a new customer. The purpose of the back-end sale is to produce a profit... To bring in as many qualified customers as possible, you must be willing to just break even on your front-end marketing, or even take a loss."'
  tags:
  - 营销系统
  - 客户终身价值
  - 产品组合
  - 前端后端


- id: f07
  title: 独特销售主张（USP）定位框架
  type: framework
  merged_from:
  - f07
  - p14
  - p12
  V1_cross_domain:
    passed: true
    evidence:
    - "第 6 章：USP 三特征——外表独特、有用、概念简单；Schlitz 啤酒案例说明'率先说出行业共有事实'也可成为 USP"
    - 第 14 章：通过持续小改进维护 USP，避免产品沦为平庸
    - 第 15 章：Big Idea 源自 USP，是营销四脚凳的基础
  V2_predictive_power:
    passed: true
    novel_question: 一款新的记账软件进入已被巨头占据的市场，如何切割出可防守的位置？
    derived_answer: "不必声称'最好的记账软件'，而是找到一个对买家有用、但未被竞争对手率先占位的 truth：例如'自动按 CPA 要求的科目分类费用'。结论：USP 可以是行业中人人皆知但消费者第一次听说的真相，关键在于'对买家有益且一句话能说清'。"
  V3_exclusivity:
    passed: true
    why_not_common: "常识要求 USP 必须真实、客观上独一无二；作者降低门槛到'外表独特'，并指出率先说出行业共有事实也可成立，这是一种反直觉的定位操作。"
  source_quote: '"Every successful unique selling proposition should have three characteristics: 1. The appearance of uniqueness. 2. Usefulness. 3. Conceptual simplicity... If it doesn''t sell, it doesn''t do you any good."'
  tags:
  - 定位
  - 差异化
  - 营销传播
  - 独特卖点


- id: f08
  title: 营销四脚凳
  type: framework
  merged_from:
  - f08
  - p15
  - p22
  - f10
  V1_cross_domain:
    passed: true
    evidence:
    - 第 6 章：有效销售努力的四个组成部分——Big Idea、Big Promise、Specific claims、Proof
    - 第 15 章：伟大营销活动有四元素——Big Idea、Big Benefit、Big Promise、Proof
    - 第 16 章：购买狂热 campaign 的设计同样依赖这四个支柱
  V2_predictive_power:
    passed: true
    novel_question: 一个床垫众筹页面转化率低迷，如何用四脚凳诊断？
    derived_answer: "Big Idea='装在盒子里的床垫'；Big Benefit='不用去展厅也能睡好'；Big Promise='100 晚无忧试睡'；Proof='10,000 条好评 + 脊椎医生背书'。结论：若缺少任何一脚——例如有 Idea 无 Proof，或有 Benefit 无 Promise——转化率就会崩塌；可作为发布前的硬性检查表。"
  V3_exclusivity:
    passed: true
    why_not_common: "虽然'信息—利益—证据'结构在营销中不罕见，但作者把四个元素命名为'四脚凳'并强调缺一即 campaign 倒塌，提供了一种可快速自检的负载结构。"
  source_quote: '"Every great marketing campaign has four elements... The first element is the Big Idea... The second element is the Big Benefit... The third element is the Big Promise... The fourth element is the Proof."'
  tags:
  - 广告创意
  - 营销检验
  - 传播结构
  - 检查表


- id: f11
  title: 临界点创新预判法
  type: framework
  merged_from:
  - f11
  - g09
  V1_cross_domain:
    passed: true
    evidence:
    - 第 10 章：消费者寻找的是熟悉产品的巧妙改编，而非全新产品；80% 旧 + 20% 新是合理比例
    - 第 9 章：出版与香水业务通过在已有趋势上快速推出变体实现 Stage Two 增长
    - 第 14 章：对畅销产品做持续小改进，维持 USP
  V2_predictive_power:
    passed: true
    novel_question: 电动自行车开始被通勤者接受但仍未主流化，此时进场该押注什么创新？
    derived_answer: "不要重新发明交通工具，而是在'熟悉的电动自行车'上加一个被用户强烈需要的小改动——例如集成防盗 GPS。结论：成功来自在趋势即将溢出的时刻，对成熟品类做关键微创新，而非创造全新品类。"
  V3_exclusivity:
    passed: true
    why_not_common: "商业媒体崇尚'颠覆式创新'；作者提出反直觉的 80/20 改编比例，并把创新比作'满杯水上的最后一滴水'，是一种基于趋势临界点而非技术突破的创新观。"
  source_quote: '"Consumers aren''t looking for brand-new products. They are looking for clever new adaptations of products they already know and love... Eighty percent of the old and 20 percent of the new is a good ratio."'
  tags:
  - 创新策略
  - 趋势判断
  - 产品时机
  - 临界点


- id: f20
  title: 自由市场反政治管理法
  type: framework
  merged_from:
  - f20
  - p33
  V1_cross_domain:
    passed: true
    evidence:
    - "第 22 章：'The ultimate solution to politics is freedom'，用自由市场管理取代办公室政治"
    - 第 20 章：从创业者转变为企业领袖，强调利润中心与授权
    - 第 25 章：成年期将企业拆分为独立核算利润中心，创始人退居顾问/投资人
  V2_predictive_power:
    passed: true
    novel_question: 一家 150 人的软件公司部门间互相抢资源、会议充满政治博弈，如何治理？
    derived_answer: "为每条产品线建立内部 P&L，让团队在一定范围内自主选择供应商、定价和优先级；公开各产品线的客户获取成本、留存率与利润；让'为客户提供更好产品'成为唯一晋升标准。结论：政治会自然减少，因为成功不再取决于讨好老板，而取决于市场结果。"
  V3_exclusivity:
    passed: true
    why_not_common: 多数反政治建议依赖文化宣导、价值观培训或更严格的层级控制；作者提出用市场机制和自由度作为解药，把政治问题重新框定为激励设计问题。
  source_quote: '"The ultimate solution to politics is freedom. The more freedom you establish in your business, the more difficult it will be for politics to thrive and spread... take a laissez-faire attitude toward product development and marketing. Some business gurus call this free-market management."'
  tags:
  - 组织治理
  - 反政治
  - 自由市场管理
  - 利润中心


- id: f21
  title: 瓶颈自我诊断法
  type: framework
  merged_from:
  - f21
  - p32
  V1_cross_domain:
    passed: true
    evidence:
    - "第 22 章：两种诊断方法——检查自己是否还在做质控类工作；问核心团队'我可以停止或授权什么'"
    - 第 19 章：CEO 直接下属不超过六到七人，超过则管理失控
    - 第 20 章：作者客户的 retreat 上，两位企业家被指出亲自把控广告与质量，成为自身企业的瓶颈
  V2_predictive_power:
    passed: true
    novel_question: 一位 50 人电商品牌创始人仍亲自审批每一张广告素材，增长放缓，怎么办？
    derived_answer: "执行两个诊断：记录一周时间，看多少小时花在质控类任务；召集营销负责人问'如果我停止审批广告，你们能多快测试新素材？'。结论：若审批是瓶颈，应制定清晰的素材标准并授权给营销总监，创始人只参与标准制定与月度复盘，否则企业规模被其个人处理能力锁死。"
  V3_exclusivity:
    passed: true
    why_not_common: "'创始人瓶颈'是管理常识，但作者把它转化为两个具体可执行的问题，并给出'每天做质控类工作不应超过一小时'的量化标准，使其从抱怨变成诊断工具。"
  source_quote: '"There are two simple ways to do that. The first way is to take a look at how you spend your time and see if you are doing any quality-control sort of activities... The other way... Call a meeting of your top people... ask them: ''What can I delegate or stop doing entirely that would make your lives easier or our business run faster?''"'
  tags:
  - 瓶颈分析
  - 授权
  - 创始人角色
  - Stage Three


- id: f22
  title: 渐进退化 vs 渐进改进循环
  type: framework
  merged_from:
  - f22
  - g11
  V1_cross_domain:
    passed: true
    evidence:
    - 第 14 章：提出 Incremental Degradation 理论——任何产品质量若不被维护会随时间退化
    - 第 10 章：Stage Two 的高速创新要求持续小改进
    - "第 22 章：官僚主义'存在本身脱离核心目的'，与渐进退化共享'缓慢侵蚀'机制"
  V2_predictive_power:
    passed: true
    novel_question: 一款 SaaS 产品在 18 个月内逐步减少客户成功支持、改为全自助，每次改动都通过了 A/B 测试，为什么留存率反而大幅下降？
    derived_answer: "每次单独改动对用户体验影响微小，但累积起来侵蚀了客户信任和感知价值。结论：必须建立一个'参考版本'的客户旅程，并定期将当前版本与参考版本做整体对照，而不是只对比上一个改动。"
  V3_exclusivity:
    passed: true
    why_not_common: "质量控制通常只检查单次变更是否达标；作者指出'单独不可察觉的小降级会累积成致命损失'，并要求对照原始版本而非上一个版本，这是一种反直觉的系统性质量观。"
  source_quote: '"Incremental degradation... If left alone, the quality of any product will degrade over time. The remedy is to consistently make improvements, innovations that allow the product to maintain its USP and avoid becoming ordinary and unremarkable."'
  tags:
  - 产品迭代
  - 持续改进
  - 竞争防御
  - 质量基准


- id: ce01
  title: 把琐事放在销售之前
  type: counter-example
  V1_cross_domain:
    passed: true
    evidence:
    - "第 4 章：'我见过更多企业因销售不足而倒闭，而不是因缺少电脑'，强调销售优先于设备与物料"
    - "第 8 章：'不要把时间浪费在企业营销上'，不要先做精美宣传册、网站、名片"
    - 第 7 章：创业伊始的无知导致随机决策，现金会在准备阶段耗尽
  V2_predictive_power:
    passed: true
    novel_question: 一位自由顾问创业第一个月只做了 logo、名片和网站，没有主动联系客户，结果会如何？
    derived_answer: 现金流在获得第一笔收入前就会枯竭。正确顺序应改为：先通过电话/社交平台获得 3–5 次付费对话，验证有人愿意付钱，再按需建设品牌物料。
  V3_exclusivity:
    passed: true
    why_not_common: "虽然'要重视销售'是常识，但作者反复指出一种具体幻觉：把'准备'误认为'进展'。这个失败模式在创始人中极为常见，却少被如此尖锐地命名。"
  source_quote: '"I''ve seen a lot more businesses go broke because they didn''t have enough sales than I''ve seen go under from lack of computers. Why don''t you work on first things first?"'
  tags:
  - stage-one
  - sales-first
  - cash-flow
  - 反例


- id: ce13
  title: 过早从阶段一跨入阶段二
  type: counter-example
  V1_cross_domain:
    passed: true
    evidence:
    - "第 18 章：'不要在你准备好之前进入阶段二'，阶段一应尽可能激进地销售单一产品"
    - 第 9 章：当企业准备好改变时必须改变，但固执守旧会不可逆地损害业务
    - 第 5 章：找到 OSS 之前不应分散资源
  V2_predictive_power:
    passed: true
    novel_question: 一款食品卡车第一款产品尚未盈利，创始人就开设三家分店并推出酱料产品，最可能的结果是什么？
    derived_answer: 在没有可重复 OSS 和稳定现金流的情况下扩张，会把原本可能盈利的单点亏损放大到多个产品线与地点。结论：必须等到单一产品在被选市场中的销售已经激进且单位经济为正，再进入阶段二。
  V3_exclusivity:
    passed: true
    why_not_common: "创业圈常鼓励'快速规模化'和'多元化'；作者把'何时扩张'与'阶段一是否完成'绑定，并强调过早扩张是阶段二的头号陷阱，这与主流增长叙事相反。"
  source_quote: '"Don''t make the mistake of shifting into Stage Two until you are ready for it. Stage One is about selling a single product as aggressively as possible in the market that is available to you."'
  tags:
  - stage-one
  - stage-two
  - focus
  - premature-expansion
  - 反例


- id: ce14
  title: 创新时跨越两步以上
  type: counter-example
  V1_cross_domain:
    passed: true
    evidence:
    - 第 10 章：开发新产品时，不要投资与已知能力相差两步以上的事物，成功率随步数几何下降
    - 第 14 章：产品改进应维护 USP，避免沦为平庸
    - 第 9 章：突破单一产品综合症需要创新，但创新应基于已有客户与能力
  V2_predictive_power:
    passed: true
    novel_question: 一家成功的桌游出版商决定进入流媒体视频制作，应如何评估风险？
    derived_answer: 桌游到流媒体同时改变客户群、渠道、内容生产能力和变现模式，属于多步远离核心业务。结论：失败概率几何级上升；更稳妥的扩张是一步之遥——如桌游配件、联名周边或授权游戏。
  V3_exclusivity:
    passed: true
    why_not_common: "'做你懂的事'是常识，但作者用'每一步远离核心能力，成功率几何下降'给出精确的风险量化表述，并与 tipping-point 的 80/20 改编原则形成对偶。"
  source_quote: '"When developing new products, you don''t want to make the mistake of investing in something that is two or more steps away from what you know how to do. That''s because your chances of success decrease geometrically with each step."'
  tags:
  - innovation
  - one-step-removed
  - core-competence
  - risk
  - 反例


---

# shared_terms

> 术语不独立成 skill，但作为共享概念保留，供下游 GLOSSARY.md 与 skill 引用。

- id: g01
  term: Ready, Fire, Aim（先行动，再瞄准）
  type: term
  notes: 核心方法论，已并入 f01
- id: g02
  term: Optimum Selling Strategy（OSS，最优销售策略）
  type: term
  notes: 已并入 f03
- id: g03
  term: Allowable Acquisition Cost（AAC，可承受获客成本）
  type: term
  notes: 已并入 f04
- id: g04
  term: Lifetime Gross Profit（客户终身毛利）
  type: term
  notes: 计算 AAC 的起点，已作为 f04 的组成概念
- id: g05
  term: Front-end / Back-end（前端产品 / 后端产品）
  type: term
  notes: 已并入 f05
- id: g06
  term: Four Stages of Business Growth（企业成长四阶段）
  type: term
  notes: 已并入 f02
- id: g07
  term: Unique Selling Proposition（USP，独特销售主张）
  type: term
  notes: 已并入 f07
- id: g08
  term: Critical Mass of Qualified Customers（CMQC，合格客户临界量）
  type: term
  notes: 已并入 f04 作为目标设定维度
- id: g09
  term: Tipping-point Product（临界点产品 / 爆款产品）
  type: term
  notes: 已并入 f11
- id: g10
  term: Accelerated Failure（加速失败）
  type: term
  notes: 与 f01 Ready-Fire-Aim 配套使用的文化概念
- id: g11
  term: Incremental Degradation（渐进式降级）
  type: term
  notes: 已并入 f22
- id: g12
  term: Goodwill（客户 goodwill / 信任余额）
  type: term
  notes: 支撑后端利润的信任余额，与 f05、f11 相关
