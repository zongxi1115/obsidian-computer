
**真正同时满足“评价数量较多、内容可靠、与 LLM 智能体直接相关”的首选，是《AI Engineering》。**
但它默认读者已经对大语言模型有基本认识。因此，更稳妥的组合是：

> **《Hands-On Large Language Models》打基础 → 《AI Engineering》建立智能体工程主线 → 《Artificial Intelligence: A Modern Approach》补搜索、规划和决策理论。**

截至 **2026 年 8 月 19 日**，专门以 “AI Agents” 为主题的图书大多才出版一两年，评价样本普遍只有个位数到几十条；相反，下面这些基础与工程书已经积累了数百到数千条评分。评分数字按 Goodreads 等页面当前显示取近似值，不同版本合并和新增评分会造成小幅变化。

商品卡主要用于辨认英文原版和正确版本，不代表必须在对应平台购买。

## 一、按“口碑成熟度 + 学习价值”排序

|推荐级别|书籍|当前读者评价信号|在智能体学习中的作用|
|--|--|--:|--|
|**核心主线**|**AI Engineering**|约 **4.36/5，1,300+ 条评分** ([好读书][1])|LLM 应用、RAG、工具、智能体、评测、监控和成本|
|**核心基础**|**Hands-On Large Language Models**|约 **4.31/5，294 条评分** ([好读书][2])|用可视化方式理解 token、embedding、Transformer、RAG、微调|
|**理论底座**|**Artificial Intelligence: A Modern Approach，4e**|约 **4.21/5，4,490 条评分** ([好读书][3])|智能体定义、搜索、规划、决策、多智能体、强化学习|
|**生产工程**|**Designing Machine Learning Systems**|约 **4.44/5，1,160+ 条评分** ([好读书][4])|部署、离线评测、监控、分布偏移、持续学习、MLOps|
|**模型原理**|**Build a Large Language Model (From Scratch)**|约 **4.58/5，370 条评分** ([好读书][5])|从代码层面理解 GPT、预训练、指令微调和 LoRA|
|**决策学习**|**Reinforcement Learning: An Introduction，2e**|约 **4.54/5，841 条评分** ([好读书][6])|MDP、价值函数、策略学习、试错决策|
|**可选补充**|**Natural Language Processing with Transformers**|约 **4.37/5，218 条评分** ([好读书][7])|Hugging Face、Transformer NLP 应用|

这里的推荐级别不是简单按照评分高低排列，而是按照**对系统学习智能体的实际贡献**排列。

---

# 二、逐本精确讲解

## 1. 《AI Engineering》：最推荐的智能体工程主线

**作者：Chip Huyen**

这是目前最符合你目标的一本书。它不把“智能体”孤立成一个框架教程，而是放在完整的基础模型应用系统中讲解。

官方目录涵盖：

- 基础模型与应用设计；
- AI 系统评测；
- Prompt Engineering；
- RAG；
- Agents；
- 微调；
- 数据集工程；
- 推理优化；
- 系统架构；
- Guardrails、路由、缓存、监控和用户反馈。

其中第 6 章直接讨论 RAG 与 Agents，包括工具、规划、记忆、智能体失败模式及其评测；第 10 章继续讨论上下文、Guardrails、路由、缓存、编排、可观测性与用户反馈。这种安排很重要，因为一个能调用工具的程序不等于一个可靠的智能体系统。([O'Reilly 机构][8])

### 它能精确解决什么

读完后，你应该能够回答：

- 什么任务适合普通工作流，什么任务才值得使用智能体；
- 如何选择模型，而不是默认使用最昂贵的模型；
- 如何设计 RAG 与工具调用；
- 如何评测 Agent 的任务完成率和调用轨迹；
- 如何控制延迟、成本和上下文长度；
- 如何加入 Guardrails、监控、反馈和故障处理；
- 为什么 Agent 在演示中有效，上线后却可能不稳定。

### 它不能替代什么

它不是：

- Transformer 数学推导教材；
- 从零编写大模型的代码教材；
- 传统搜索、MDP、博弈论教材；
- 某个智能体框架的逐行 API 教程。

因此它特别适合做**主线教材**，但基础薄弱时最好先读下一本。

### 推荐阅读顺序

不要严格从第一页读到最后一页，可以按照：

> 第 1 章 → 第 3、4 章 → 第 5、6 章 → 第 10 章 → 第 7—9 章按需求补充

其中：

- 第 3、4 章解决“怎样评测”；
- 第 5 章解决“怎样与模型交互”；
- 第 6 章进入 RAG 和智能体；
- 第 10 章解决生产系统问题。

### 购买结论

**已经会 Python、调用过 LLM API、知道基本 RAG 概念时，只买一本就选它。**

它已有官方中文版《AI工程：大模型应用开发实战》，人民邮电出版社，2026 年出版，ISBN 为 9787115686398。([慕课网][9])

---

## 2. 《Hands-On Large Language Models》：最适合补齐 LLM 直觉

这本书的价值不是“手把手搭一个复杂 Agent”，而是帮助你真正理解 Agent 背后的模型为什么会这样工作。

官方目录覆盖：

- tokenization；
- embeddings；
- Transformer 内部结构；
-文本分类和聚类；
- Prompt Engineering；
-文本生成；
-语义搜索；
- RAG；
-多模态模型；
- embedding 模型训练；
-微调。

它采用大量图示和代码解释，从模型表示逐步进入检索与生成应用，适合对 Transformer、embedding 和 RAG 只有模糊认识的读者。([O'Reilly 机构][10])

### 它能精确解决什么

读完后，你应该能够解释：

- 文本为什么需要变成 token；
- embedding 为什么能用于语义检索；
- Transformer 如何利用上下文；
-生成模型和 embedding 模型有什么区别；
-语义搜索、向量检索和 RAG 分别是什么；
- Prompt、RAG 与微调各自适合解决什么问题；
-为什么检索到了正确文档，模型仍然可能答错。

### 它没有系统讲什么

它不会完整覆盖：

- Agent Loop；
-工具选择与参数校验；
-长期记忆；
-规划与反思；
-多智能体协调；
-智能体轨迹评测；
-权限与安全设计。

所以它是**进入智能体之前最好的 LLM 基础书之一**，但不能作为唯一的智能体教材。

### 推荐阅读顺序

第一轮重点读：

> 第 1—3 章 → 第 6—8 章

先掌握模型、token、embedding、Prompt、生成和语义搜索。

第二轮再读：

> 第 10—12 章

补多模态、embedding 训练和微调。

### 购买结论

**对 LLM 原理不熟时，把它放在《AI Engineering》前面。**

---

## 3. 《Artificial Intelligence: A Modern Approach》：最严谨的智能体理论底座

通常简称 **AIMA**。

它的优势在于：不会把智能体简单定义成“能调用工具的大语言模型”，而是从智能体与环境的关系开始建立完整理论。

第四版官方目录涵盖智能体、搜索、约束满足、规划、不确定性、决策、多智能体、强化学习、自然语言处理、机器人和 AI 安全等内容。该教材被全球大量高校课程采用。([伯克利人工智能研究所][11])

### 对 LLM 智能体最相关的章节

|章节|对智能体学习的意义|
|--|--|
|第 2 章 Intelligent Agents|智能体、环境、观察、动作、理性、效用的严格定义|
|第 3—4 章 Search|BFS、A*、启发式搜索，以及复杂搜索环境|
|第 11 章 Automated Planning|状态、动作、前置条件、结果和规划|
|第 16—17 章 Decision Making|不确定环境中的效用与序列决策|
|第 18 章 Multiagent Decision Making|多智能体合作、竞争和决策|
|第 22 章 Reinforcement Learning|通过环境反馈学习策略|

### 它能纠正哪些常见误解

读完相关章节后，你会明白：

- “会生成计划”不等于真正完成了规划；
- Prompt 里的任务清单不等于可执行状态空间；
-多智能体角色扮演不等于多智能体决策系统；
-记住聊天内容不等于拥有完备状态；
-模型输出的置信语气不代表决策具有高效用；
-反复调用模型不等于搜索算法。

### 它的不足

- 篇幅很大；
- 数学和符号较多；
- 不直接讨论现代 LLM 工具调用框架；
- 不适合当作第一本编程实践书。

因此不建议从头到尾通读，而应把它当作**理论教材和长期参考书**。

### 购买结论

**认真研究规划、长期决策、多智能体或具身智能时必备；只做简单 API 应用时可以选择性阅读。**

已有官方中文第四版《人工智能：现代方法（第4版）（上下册）》。([PT Press][12])

---

## 4. 《Designing Machine Learning Systems》：把实验性 Agent 变成生产系统

这本书不是专门讲智能体，但对于真正部署 Agent 非常重要。

它讨论：

- 数据工程；
-模型开发和离线评测；
-模型部署与在线预测；
-数据分布偏移；
-线上监控；
-持续学习；
-生产环境测试；
- MLOps 基础设施。

尤其值得读的是第 6—10 章，它们覆盖离线评价、部署、监控、分布变化、生产测试和基础设施。([O'Reilly 机构][13])

### 为什么智能体学习需要它

普通模型通常是：

```text
输入 → 模型 → 输出
```

智能体则可能是：

```text
输入
→ 模型判断
→ 调用检索
→ 调用数据库
→ 修改状态
→ 再次推理
→ 调用外部系统
→ 最终回答
```

这意味着它的失败不仅是“回答不好”，还可能包括：

- 工具参数错误；
- 无限循环；
- 数据写入错误；
-权限越界；
-外部服务超时；
-状态不同步；
-延迟或费用失控；
-环境变化后性能下降。

这本书能够帮你建立**部署、监控、数据与反馈闭环的工程意识**。

### 它没有讲什么

它不会详细教：

- ReAct；
- Agent memory；
-工具调用协议；
- Tree of Thoughts；
- MCP；
-多智能体对话框架。

### 购买结论

**准备把智能体用于真实业务时优先购买；只处于入门和实验阶段时可以稍后读。**

中文版为《机器学习系统设计》，2024 年出版。([图书馆在线][14])

---

## 5. 《Build a Large Language Model (From Scratch)》：理解智能体“大脑”的内部结构

这本书使用 PyTorch 从头构建一个 GPT 风格语言模型，内容包括：

- 文本处理；
-注意力机制；
- Transformer；
- GPT 模型实现；
-预训练；
-分类微调；
-指令微调；
- LoRA。

官方介绍和目录明确以“从零构建大语言模型”为核心。([Manning Publications][15])

### 它能精确解决什么

读完后，你会更清楚：

- token 是怎样进入模型的；
-注意力具体在计算什么；
-上下文窗口为什么有限；
-模型如何预测下一个 token；
-预训练和指令微调有什么区别；
- LoRA 为什么能降低微调成本；
-模型为什么可能生成流畅但错误的内容。

### 它和智能体的关系

Agent 使用 LLM 作为决策组件。理解模型内部机制，有助于判断：

- 哪些问题可以依靠 Prompt；
- 哪些问题需要外部检索；
- 哪些问题需要工具验证；
- 为什么模型不适合保存精确状态；
- 为什么不能把模型输出直接当成可信动作。

但它基本不教：

-工具系统；

- Agent Loop；
-规划；
-记忆；
-多智能体；
-生产评测。

### 购买结论

**准备做模型研究、微调或深入理解 Transformer 时很值得；只想快速开发智能体应用时不是前三本。**

---

## 6. 《Reinforcement Learning: An Introduction》：适合研究“会学习的智能体”

Sutton 和 Barto 的这本书是强化学习领域的经典教材，主要研究智能体如何通过与环境交互和获得奖励来学习行为策略。

第二版涵盖多臂老虎机、MDP、动态规划、Monte Carlo、时序差分学习、Sarsa、Q-learning、策略梯度等核心内容。([MIT Press][16])

### 它与当前 LLM Agent 的区别

很多 LLM Agent 实际上只是：

- 使用预训练模型；
-根据 Prompt 选择工具；
-读取工具结果；
-继续生成下一步。

它们通常并没有真正根据奖励更新策略。

强化学习研究的则是：

- 状态；
-动作；
-转移；
-奖励；
-策略；
-长期回报；
-探索与利用；
-基于经验更新行为。

### 哪些方向需要它

比较重要的方向包括：

-机器人与具身智能；
-游戏智能体；
-自动驾驶决策；
-长期任务规划；
-基于环境奖励训练 Agent；
-自我改进；

- verifier 和 outcome reward；
-多智能体强化学习。

### 哪些方向暂时不需要

只做以下项目时，可以后置：

-文档问答；
-企业知识库；
-邮件助手；
-简单数据分析助手；
-固定业务流程工具调用。

### 购买结论

**应用型 LLM Agent 入门不是必读；研究型、具身型和训练型智能体是重要教材。**

已有官方中文第二版《强化学习（第2版）》。([广视网站][17])

---

# 三、专门讲 AI Agent 的新书怎么样

## 《AI Agents in Action》

第一版直接覆盖：

- Agent profile 与行为；
-工具；
-记忆；
-规划；
-反馈循环；
-多智能体；
-语音和视觉；
- LangChain、AutoGen、CrewAI 等框架。

Manning 列出的第二版进一步加入 MCP、ReAct、Reflexion、Tree of Thoughts 和 Sequential Thinking 等内容，主题与当前 Agent 开发非常直接。([Manning Publications][18])

问题在于，第一版目前只有约 **66—80 条评分，均分约 3.95**，不同版本页面的聚合数字略有差异；第二版的成熟评价样本还更少。([好读书][19])

**判断：适合作为第二阶段代码参考，不适合作为唯一理论教材。**

框架类内容还存在天然问题：API、框架名称和推荐写法更新很快，而评测、状态、搜索、规划和安全等原理更加稳定。

---

## 《Agentic Design Patterns》

这本书由 Springer 出版，按照设计模式组织章节。每种模式通常包括：

-概念概览；
-适用场景；
-代码；
-实践注意事项；
-关键结论。

它适合在已经理解 Agent Loop、工具和评测后，用来建立“路由、反思、规划、协作”等模式库。([Springer][20])

**判断：很适合作为模式手册，但出版时间较新，尚不符合“评价量很多”的条件。**

---

## 《An Illustrated Guide to AI Agents》

官方目录非常贴合系统学习需求，包括：

- LLM 基础；
-推理；
-记忆；
-工具与 MCP；
-规划与反思；
-智能体评测；
-多智能体；
-多模态和编程 Agent。

但截至 **2026 年 8 月 19 日**，它仍处于 Early Release 状态，官方标注正式出版时间为 **2026 年 9 月**，读者评分只有约 5 条。([O'Reilly 机构][21])

**判断：目录值得关注，但目前不能依据读者口碑判断质量，不建议把它列为第一批核心教材。**

---

# 四、按知识主题精确对应到书

|要学习的主题|最合适的书|重点章节或内容|
|--|--|--|
|LLM、token、embedding、Transformer|Hands-On LLM|第 1—3 章|
|Prompt 与生成控制|Hands-On LLM、AI Engineering|Hands-On 第 6—7 章；AI Engineering 第 5 章|
|RAG 与语义检索|Hands-On LLM、AI Engineering|Hands-On 第 8 章；AI Engineering 第 6 章|
|工具调用和 Agent 架构|AI Engineering|第 6 章|
|评测体系|AI Engineering|第 3—4 章|
|Guardrails、路由、监控|AI Engineering|第 10 章|
|智能体严格定义|AIMA|第 2 章|
|搜索与规划|AIMA|第 3—4、11 章|
|长期决策和不确定性|AIMA|第 16—17 章|
|多智能体理论|AIMA|第 18 章|
|模型内部实现|Build a Large Language Model|注意力、GPT、预训练、指令微调章节|
|强化学习 Agent|Reinforcement Learning|第 1—6 章起步|
|部署、监控和线上反馈|Designing ML Systems|第 6—10 章|
|常见 Agent 设计模式|Agentic Design Patterns|按实际项目查阅|

---

# 五、最合理的购买方案

## 只买一本

### 已经了解 LLM、Prompt 和 RAG

买：

> **《AI Engineering》**

它与现代 LLM Agent 的应用设计最接近。

### 对 LLM 原理仍然比较模糊

买：

> **《Hands-On Large Language Models》**

先建立模型、embedding、检索和生成直觉。

---

## 买两本：应用型学习最优组合

> **《Hands-On Large Language Models》
＋《AI Engineering》**

第一本回答“模型和 RAG 为什么这样工作”，第二本回答“怎样设计、评测和部署一个可靠系统”。

这两本的重叠不算严重：

- Hands-On LLM 更偏模型理解和具体技术；
- AI Engineering 更偏系统决策、评测与架构。

---

## 买三本：最完整的通用组合

> **《Hands-On Large Language Models》
＋《AI Engineering》
＋《Artificial Intelligence: A Modern Approach》**

第三本不用通读，只读智能体、搜索、规划、决策、多智能体和强化学习相关章节。

这个组合分别覆盖：

```text
模型基础
    ↓
LLM 应用与 Agent 工程
    ↓
搜索、规划、决策理论
```

---

## 准备做生产项目

在上述组合上增加：

> **《Designing Machine Learning Systems》**

用于补部署、监控、分布变化、反馈和可靠性。

---

## 准备做模型或科研方向

增加：

> **《Build a Large Language Model (From Scratch)》**

进一步研究学习型、具身型或长期决策 Agent 时，再增加：

> **《Reinforcement Learning: An Introduction》**

---

# 六、8 周按书学习路线

## 第 1—2 周：建立 LLM 基础

阅读《Hands-On Large Language Models》：

- 第 1—3 章；
- 第 6—8 章。

实践：

- 调用一个 LLM；
-计算文本 embedding；
-实现语义搜索；
-实现一个最小 RAG；
-比较“不检索”和“检索后回答”。

目标：能够解释 token、embedding、上下文、生成和 RAG。

---

## 第 3—5 周：建立智能体工程主线

阅读《AI Engineering》：

- 第 1 章；
- 第 3—6 章；
- 第 10 章。

实践：

- 给模型定义三个工具；
-实现结构化工具参数；
-加入最大步数、超时和费用预算；
-建立 30 个测试任务；
-记录工具调用轨迹；
-统计成功率、调用次数和延迟。

目标：不是只做出一个 Agent Demo，而是开始建立评测体系。

---

## 第 6 周：补搜索与规划

阅读 AIMA：

- 第 2 章；
- 第 3—4 章；
- 第 11 章。

实践：

-实现 BFS 或 A*；
-把一个复杂任务表示为状态、动作、前置条件和目标；
-比较模型自由生成计划与形式化搜索的差异。

目标：能够区分“生成一段计划文字”和“在状态空间中规划”。

---

## 第 7 周：补决策与多智能体

阅读 AIMA：

- 第 16—18 章；
- 第 22 章选读。

实践：

-建立一个有随机失败概率的工具环境；
-为动作设置成本与收益；
-比较单 Agent、Supervisor-Worker 和独立验证器三种架构。

目标：理解多智能体不是简单增加角色数量。

---

## 第 8 周：根据方向分流

### 应用和生产方向

阅读《Designing Machine Learning Systems》第 6—10 章，给项目增加：

-监控；
-错误分类；
-数据版本；
-回归测试；
-人工审批；
-回滚机制。

### 模型研究方向

阅读《Build a Large Language Model》第 2—7 章，理解：

-注意力；

- GPT；
-预训练；
-指令微调。

### 具身、游戏或训练型 Agent

开始《Reinforcement Learning》第 1—6 章，并实现：

-多臂老虎机；

- GridWorld；
- value iteration；
- Q-learning。

---

# 最终推荐

按照你现在“系统学习智能体，并且希望材料可靠、评价量足够”的目标，最稳妥的顺序是：

1. **《Hands-On Large Language Models》**：建立 LLM、embedding、RAG 的精确理解；
2. **《AI Engineering》**：作为智能体应用、评测和系统设计的核心教材；
3. **AIMA 第四版**：选择性学习搜索、规划、决策和多智能体；
4. **《Designing Machine Learning Systems》**：准备部署真实系统时加入；
5. **《Build a Large Language Model》或《Reinforcement Learning》**：根据模型研究或具身智能方向分流。

**《AI Agents in Action》和《Agentic Design Patterns》适合作为代码与模式补充，但现阶段不应替代前三本，也不建议作为唯一的知识来源。**

[1]: https://www.goodreads.com/en/book/show/216848047-ai-engineering "https://www.goodreads.com/en/book/show/216848047-ai-engineering"

[2]: https://www.goodreads.com/en/book/show/210408850-hands-on-large-language-models "https://www.goodreads.com/en/book/show/210408850-hands-on-large-language-models"

[3]: https://www.goodreads.com/book/show/27543.Artificial_Intelligence "https://www.goodreads.com/book/show/27543.Artificial_Intelligence"

[4]: https://www.goodreads.com/author/show/22327517.Chip_Huyen "https://www.goodreads.com/author/show/22327517.Chip_Huyen"

[5]: https://www.goodreads.com/author/show/7167707.Sebastian_Raschka "https://www.goodreads.com/author/show/7167707.Sebastian_Raschka"

[6]: https://www.goodreads.com/book/show/739791.Reinforcement_Learning "https://www.goodreads.com/book/show/739791.Reinforcement_Learning"

[7]: https://www.goodreads.com/author/list/21943785.Lewis_Tunstall "https://www.goodreads.com/author/list/21943785.Lewis_Tunstall"

[8]: https://www.oreilly.com/library/view/ai-engineering/9781098166298/ "https://www.oreilly.com/library/view/ai-engineering/9781098166298/"

[9]: https://www.ituring.com.cn/book/3404 "https://www.ituring.com.cn/book/3404"

[10]: https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/ "https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/"

[11]: https://aima.cs.berkeley.edu/contents.html "https://aima.cs.berkeley.edu/contents.html"

[12]: https://www.ptpress.com.cn/shopping/buy?bookId=055c496a-7db2-4be0-910c-c93d0fdda173 "https://www.ptpress.com.cn/shopping/buy?bookId=055c496a-7db2-4be0-910c-c93d0fdda173"

[13]: https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/ "https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/"

[14]: https://libopac.cjlu.edu.cn/mspace/searchDetailLocal/mdf473a269b9cdd4f9092ab28ff11079f "https://libopac.cjlu.edu.cn/mspace/searchDetailLocal/mdf473a269b9cdd4f9092ab28ff11079f"

[15]: https://www.manning.com/books/build-a-large-language-model-from-scratch "https://www.manning.com/books/build-a-large-language-model-from-scratch"

[16]: https://mitpress.mit.edu/9780262039246/reinforcement-learning/ "https://mitpress.mit.edu/9780262039246/reinforcement-learning/"

[17]: https://www.broadview.com.cn/book/6080 "https://www.broadview.com.cn/book/6080"

[18]: https://www.manning.com/books/ai-agents-in-action "https://www.manning.com/books/ai-agents-in-action"

[19]: https://www.goodreads.com/author/list/333630.Christopher_Kendrick "https://www.goodreads.com/author/list/333630.Christopher_Kendrick"

[20]: https://link.springer.com/book/10.1007/978-3-032-01402-3 "https://link.springer.com/book/10.1007/978-3-032-01402-3"

[21]: https://www.oreilly.com/library/view/an-illustrated-guide/9798341662681/ "https://www.oreilly.com/library/view/an-illustrated-guide/9798341662681/"
