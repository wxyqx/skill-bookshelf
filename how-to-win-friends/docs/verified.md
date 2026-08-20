# 人性的弱点 — 三重验证结果

> 阶段 1.5 产出 | 64 个候选 → 8 个通过 → 进入阶段 2

## 通过的候选 (8 个 → 将做成 skill)

```yaml
- id: s01
  title: 钓鱼思维 (Bait-the-Fish Thinking)
  merged_from: [f01, p03, g02]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第一篇·第三章: 钓鱼比喻——用虫不用奶油
      - 第一篇·第三章: 教育孩子——吸烟→不能参加棒球队
      - 第二篇·第五章: 罗斯福见客前准备对方感兴趣的话题
      - 第三篇·第十章: 诉诸高尚动机——给人好听的的理由
  V2_predictive_power:
    passed: true
    novel_question: "一位程序员想说服老板采用新技术栈，但老板只关心成本。怎么说服？"
    derived_answer: "不说'我想用这个技术'，而说'这个技术能把服务器成本降30%'——从老板最关心的成本角度出发设计'饵'。如果老板关心的是稳定性而非成本，则换成'这个技术能把故障率降低50%'。"
  V3_exclusivity:
    passed: true
    why_not_common: "大多数人的说服本能是'我要什么'，而非'对方要什么'。这个视角转换是反直觉的——即使是聪明人也会在争论中只谈自己的理由。"

- id: s02
  title: 争辩避免术 (Argument Avoidance)
  merged_from: [p09, ce02, ce03, p10]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第三篇·第一章: 史密斯爵士宴会争辩——赢了逻辑输了关系
      - 第三篇·第二章: 林肯不寄出的愤怒信件
      - 第三篇·第四章: 洛克菲勒面对罢工不用威胁
      - 第六篇·第三章: 狄斯瑞利不批评妻子
  V2_predictive_power:
    passed: true
    novel_question: "同事在会议上说了一个明显错误的方案，你觉得必须纠正。怎么办？"
    derived_answer: "不说'你这个方案有问题'。先说'这个思路有创意'（友好开场），再问'如果我们遇到X情况，这个方案会怎么处理？'（让对方自己发现漏洞）。如果对方坚持，放弃争辩——因为争辩只会让对方更坚定。"
  V3_exclusivity:
    passed: true
    why_not_common: "常识说'有理就要争'，卡耐基说'有理更不要争'。其独特之处在于：不是回避问题，而是用非对抗方式达成同样目的。心理学依据（说'不'触发人格防御）是他的独特贡献。"

- id: s03
  title: 认错先行术 (Preemptive Self-Criticism)
  merged_from: [f09, p11]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第三篇·第三章: 卡耐基在公园被警察抓到不戴狗笼——先认错
      - 第四篇·第三章: 卡耐基对侄女约瑟芬——先说自己的错误
      - 第三篇·第八章: 同理心公式的入口——先承认自己也可能如此
  V2_predictive_power:
    passed: true
    novel_question: "项目延期了，客户很生气。你的第一句话应该说什么？"
    derived_answer: "'这件事是我的责任，我在进度管理上做得不够好。'在客户指责你之前先认错，客户的攻击能量无处释放，反而开始说'其实也不全怪你'。认错 = 解除对方武装。"
  V3_exclusivity:
    passed: true
    why_not_common: "大多数人的本能是先为自己辩护。'在对方指责你之前先认错'是反直觉的——但它把'被动道歉'变成'主动掌控'。"

- id: s04
  title: Yes-Ladder 苏格拉底法
  merged_from: [f02, g04]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第三篇·第五章: 奥弗斯德教授的'不'字障碍理论
      - 第三篇·第四章: 洛克菲勒对罢工工人——先说共同点
      - 第三篇·第七章: 赛尔滋让推销员自己说需求
  V2_predictive_power:
    passed: true
    novel_question: "你想让团队采用新的代码审查流程，大家觉得太麻烦。怎么开场？"
    derived_answer: "不说'我们需要新的代码审查流程'。先问'大家都希望减少线上bug吧？'(是)→'如果能在提交前发现问题更好吧？'(是)→'有一种方法可以在提交阶段就发现大部分问题…'(是)。三个'是'之后，阻力已经大大降低。"
  V3_exclusivity:
    passed: true
    why_not_common: "大多数人遇到分歧时直接亮出分歧点。先找共同点、积累'是'的惯性再引入分歧，这是卡耐基从销售话术中提炼的独特对话节奏控制法。"

- id: s05
  title: 倾听引导法 (Listening as Persuasion)
  merged_from: [f10, p13]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第二篇·第四章: 桥牌聚会上听小姐谈非洲
      - 第三篇·第六章: 汽车公司采购——让对方说完
      - 第三篇·第七章: 赛尔滋让推销员自己说需求
  V2_predictive_power:
    passed: true
    novel_question: "一位客户来投诉产品质量问题，你如何处理？"
    derived_answer: "不解释、不辩护。问'您能详细说说遇到了什么问题吗？'然后安静听15分钟。客户说完所有不满后，怒气已经释放大半，此时他开始问'那你们怎么解决？'——他从投诉者变成了寻求解决方案的合作者。"
  V3_exclusivity:
    passed: true
    why_not_common: "常识认为说服=说更多。卡耐基的洞察是：说服=让对方说更多。沉默本身就是说服工具——这反直觉。"

- id: s06
  title: 面子保全批评法 (Face-Saving Feedback)
  merged_from: [f06, p15, ce10, p17, ce08, p18]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第四篇·第一章: 柯立芝赞美女秘书再提改进
      - 第四篇·第二章: 司华伯给工人雪茄而非责骂
      - 第四篇·第三章: 卡耐基对侄女先说自己错误
      - 第四篇·第四章: 杨欧文用建议代替命令
      - 第四篇·第五章: 奇异电气公司给斯坦米滋新头衔
  V2_predictive_power:
    passed: true
    novel_question: "你的下属交了一份报告，数据有几处错误，但整体框架不错。怎么反馈？"
    derived_answer: "(1)先真诚赞美：'框架思路很清晰，特别是市场分析那部分'。(2)间接指出问题：'有几个数据点需要更新——我之前也犯过类似的引用错误'。(3)用提问代替命令：'你觉得如果我们重新核对一下这三处数据会怎样？'(4)保全面子：私下沟通，不当众指出。"
  V3_exclusivity:
    passed: true
    why_not_common: "常识的批评是'指出问题'。卡耐基的批评法包含5个组件（赞美铺垫+间接指出+先说自己错+提问代替命令+保全面子），构成一套完整的'不伤害自尊的行为改造术'——这不是常识能自然产出的。"

- id: s07
  title: 赞美微进步 (Micro-Progress Praise)
  merged_from: [p16, c10]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第四篇·第六章: 巴洛训练狗——稍有进步就奖励
      - 第四篇·第六章: 洛斯狱长赞美犯人微小进步
      - 第四篇·第八章: 第二个舞蹈老师——赞美好的一面
  V2_predictive_power:
    passed: true
    novel_question: "你的孩子从来不愿收拾房间，偶尔放了一本书回书架。怎么做？"
    derived_answer: "不等他收拾完整个房间才表扬。说'我注意到你把数学书放回书架了——这个开始很好！'赞美微小进步会强化进步方向，让他下次想做得更多。如果等完美才表扬，他永远得不到正反馈。"
  V3_exclusivity:
    passed: true
    why_not_common: "大多数人只在显著成就时才赞美。卡耐基借用动物训练原理——赞美最小进步——并将其应用于人类，这在1936年是开创性的洞察。"

- id: s08
  title: 声誉锚定 (Reputation Anchoring)
  merged_from: [f05, g09]
  type: framework
  V1_cross_domain:
    passed: true
    evidence:
      - 第四篇·第七章: 琴德太太给女佣好声誉
      - 第四篇·第九章: 霍斯上校让勃雷恩觉得决定有道理
      - 第三篇·第十章: 诉诸高尚动机——给人好听的的理由
  V2_predictive_power:
    passed: true
    novel_question: "你接手了一个团队，其中一个成员被标记为'摸鱼王'。怎么改变他？"
    derived_answer: "不说'你的表现很差需要改进'。说'我听说你是团队里最有创造力的人——我正需要一个能跳出框架思考的人来负责这个新项目'。给他一个'有创造力'的声誉，他会为了维护这个身份而主动展现创造力。"
  V3_exclusivity:
    passed: true
    why_not_common: "常识认为改变行为=指出问题。卡耐基的方法是反过来的：不指出问题，而是赋予一个正面身份，让人自觉向该身份靠拢。这是间接影响的最高形式。"
```

## 淘汰的候选 (部分列出)

| 候选 | 不通过 | 原因 |
|---|---|---|
| 记住名字 (p05) | V3 | 虽然有效但是常识——"记住别人名字"不需要skill承载 |
| 微笑 (第二篇Ch2) | V3 | 常识——微笑让人喜欢是所有人都知道的 |
| 真诚关心他人 (p04) | V3 | 虽然是核心原则但太常识，已融入钓鱼思维skill |
| 戏剧化呈现法 (f08) | V1 | 全书仅一个主要案例（费城晚报），跨域佐证不足 |
| 不唠叨 (p19) | V3 | 太具体且常识，已融入面子保全批评法 |
| 挑战激励法 (f07) | V1 | 仅一个主要案例（司华伯写6），跨域佐证不足 |
| 意见所有权转移 (f04) | V3边界 | 与倾听引导法高度重叠，合并为后者的组件 |
| 同理心转换公式 (f03) | V3边界 | 同理心在现代已是常识，但作为钓鱼思维的子组件保留 |
