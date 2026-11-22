---
name: persona-distiller
description: >-
  Use this skill when the user wants to distill a thinker, founder, historical figure,
  or character from primary sources (speeches, books, interviews, letters) into a new
  persona skill in persona-skills, or audit and refine an existing persona skill.
---

# Persona Distiller（人物思想提炼器）

将人物零散的言论、著作与经历，提炼为**可执行的思维操作系统**（而非语录汇编或表面风格模仿）。

## 何时使用

- 用户要求新增一位人物到 `skills/<name>/`。
- 用户提供了某位人物的演讲稿、访谈、书信或书摘，希望总结其哲学逻辑并沉淀为 Skill。
- 用户觉得现有人物 Skill 在模拟时流于口号、缺失后期反思或容易偏离逻辑，需要审计修正。

## 六步提炼工作流

### 第 1 步：界定思想阶段与收集一手语料
1. 划定人物主要的**认知演化阶段**（至少区分早期成型期与成熟/反思期，避免把某一时期的观点当成静态教条）。
2. 优先检索和采信**一手原典**：本人公开演讲实录、亲笔信件、著作原文、完整深度访谈。
3. **严格清洗二手语料**：剔除无出处的鸡汤金句、被自媒体改写过度的段子；若必须引用待核实材料，显式标明存疑或直接弃用。

### 第 2 步：提炼核心公理与价值排序
从一手语料中反推出 5–7 条底层的**不可再约假设（Core Axioms）**：
- 问自己：TA 如何看待人性、事实与信息、时间复利、系统与个人、风险与不确定性？
- 明确写出**价值冲突时的取舍排序**（例如：长期复利 vs 短期名声、一手事实 vs 体面抽象叙事、系统能力 vs 单次英雄主义）。

### 第 3 步：将静态观点形式化为推理算法
这是区分“语录机”与“可推演 Skill”的关键步骤：
- 不要只列出“第一性原理”“延迟满足”等名词；
- 必须写成**面对一个全新、未知问题时的 4–6 步操作指令**：输入怎么拆解、先检验哪条假设、如何找关键变量、如何构造最小验证动作、最后如何自查盲区。

### 第 4 步：梳理真实决策案例与认知边界
1. 选取 3–5 个关键历史决策（必须包含至少 1 个失误、危机或重大认知修正案例）。
2. 每个案例统一拆解为：**背景约束 → 当时常规做法 → 本人的底层逻辑与选择 → 结果及暴露出的思想盲区**。
3. 单独总结该人物体系的**系统性盲区（Epistemic Boundaries）**（例如工具理性对情感与意义维度的忽视、特定时代与行业路径的局限）。

### 第 5 步：按标准模板落盘并更新索引
严格参照 [persona-skill-template.md](./resources/persona-skill-template.md) 创建以下目录结构：
- `skills/<kebab-case-name>/SKILL.md`：保持精炼（建议 120–180 行），只放核心坐标、公理、推理算法、交互模式、反模式与索引链接。
- `skills/<kebab-case-name>/references/mental-models.md`：思想阶段、核心模型深析（含常见误解辨析）与盲区剖析。
- `skills/<kebab-case-name>/references/quotes.md`：按主题归类的一手原话，每条必须标注时间与出处。
- `skills/<kebab-case-name>/references/cases.md`：真实决策与反思案例。
- `skills/<kebab-case-name>/examples/calibration-qa.md`：至少 3 组标定示范（个人决策、想法压力测试、跨时代新议题外推）。

若在完整 `persona-skills` 仓库内执行，同步更新仓库根目录的 `README.md` 中的“已收录人物索引”表格。

### 第 6 步：标定自检（Calibration Audit）
用 `calibration-qa.md` 的 3 类测试题做一次试跑，逐项核对：
- **反 Cosplay 检查**：去掉人物名字和标志性词汇后，推理链条本身是否依然严谨、可验证？
- **反谄媚检查**：面对明显有逻辑漏洞的用户提问时，是否敢于直接指正？
- **防编造检查**：是否所有原话引用均可追溯到 `references/quotes.md`？外推结论是否清晰标注为“逻辑推演”？
- **盲区检查**：是否在推演结尾指出了该视角在本题上的固有局限？
