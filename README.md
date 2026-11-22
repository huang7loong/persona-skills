# Persona Skills（人物思想推演库）

一个用于**个人深度思考、决策推演与观点压力测试**的 Skill 仓库。

与追求“语气像不像”的娱乐角色扮演 Prompt 不同，本仓库把每一位思想者、创始人或历史人物的**底层公理、价值排序、推理算法与认知盲区**结构化为可执行的 Antigravity Skill（同时兼容标准 Plugin 规范），让 AI 成为帮你照见盲区、检验逻辑的“可运行思维操作系统”。

---

## 目录结构

```text
persona-skills/
├── plugin.json                         # Antigravity Plugin 清单
├── README.md                           # 仓库说明与人物索引
├── .agents/
│   └── skills.json                     # 在本仓库目录内自动发现 skills/
├── rules/
│   └── AGENTS.md                       # 推演纪律（史实与外推分离、禁止谄媚、必附盲区）
├── templates/
│   └── persona-skill-template.md       # 新增人物 Skill 的标准模板
└── skills/
    ├── persona-distiller/              # 【元技能】从一手语料提炼新的人物 Skill
    │   └── SKILL.md
    ├── persona-council/                # 【元技能】调度多视角独立推演与圆桌交锋
    │   └── SKILL.md
    ├── elon-musk/                      # 【人物技能】埃隆·马斯克思想推演系统
    │   ├── SKILL.md
    │   ├── references/
    │   │   ├── mental-models.md        # 演进阶段、10 个核心思维模型与盲区剖析
    │   │   ├── quotes.md               # 带出处的已核实一手原话库
    │   │   └── cases.md                # 5 个真实决策、修正与跨界边界案例
    │   └── examples/
    │       └── calibration-qa.md       # 标定问答（用于校验推演是否跑偏）
    ├── jensen-huang/                   # 【人物技能】黄仁勋思想推演系统
    │   ├── SKILL.md
    │   ├── references/
    │   │   ├── mental-models.md        # 演进阶段、10 个核心思维模型与盲区剖析
    │   │   ├── quotes.md               # 带出处的已核实一手原话库
    │   │   └── cases.md                # 5 个真实决策、撤退与败局案例
    │   └── examples/
    │       └── calibration-qa.md       # 标定问答（用于校验推演是否跑偏）
    └── zhang-yiming/                   # 【人物技能】张一鸣思想推演系统
        ├── SKILL.md
        ├── references/
        │   ├── mental-models.md        # 演进阶段、10 个核心思维模型与盲区剖析
        │   ├── quotes.md               # 带出处的已核实一手原话库
        │   └── cases.md                # 5 个关键真实决策与反思案例
        └── examples/
            └── calibration-qa.md       # 标定问答（用于校验推演是否跑偏）
```

---

## 已收录人物索引

| Skill ID | 人物 | 核心思想范式 | 最适合推演的问题类型 | 入口 |
| :--- | :--- | :--- | :--- | :--- |
| `zhang-yiming` | 张一鸣 | 工程师底色的务实浪漫、系统优化、延迟满足、Context not Control、平常心 | 个人长期职业/成长决策、项目/想法压力测试、组织机制与信息流设计、去抽象纠偏 | [SKILL.md](./skills/zhang-yiming/SKILL.md) |
| `jensen-huang` | 黄仁勋 | 物理第一性原理（光速基准）、零亿美元市场、战略撤退、低预期强韧性、全栈协同与任务即老板 | 技术/职业长周期押注、沉没成本战略撤退、红海路线纠偏、抗压韧性测试与一线卡点排查 | [SKILL.md](./skills/jensen-huang/SKILL.md) |
| `elon-musk` | 埃隆·马斯克 | 物理学第一性原理、白痴指数、五步工程算法（删减先于优化、自动化最后）、制造机器的机器 | 个人工作流与方案暴力精简、拆解高摩擦成本、工程从原型到量产闭环诊断、挑战行业隐含前提 | [SKILL.md](./skills/elon-musk/SKILL.md) |

### 元技能（Meta-Skills）

- `persona-distiller`：从人物的一手演讲、书信、原著与完整访谈中提炼底层公理与推理算法，生成新的人物 Skill 或校准已有 Skill。入口：[SKILL.md](./skills/persona-distiller/SKILL.md)
- `persona-council`：针对复杂抉择组织多视角独立辩论（支持多位收录人物直接交锋，或单人物自动配对对立镜像视角以暴露盲区）。入口：[SKILL.md](./skills/persona-council/SKILL.md)

---

## 日常使用方法

在本仓库内（或全局挂载后在任意工作区）直接向 Agent 提问即可：

1. **个人决策与工作流重构（单人物推演）**
   > “激活 `elon-musk` skill，用五步算法和白痴指数帮我重构当前这套过于复杂的个人工作流。”
   > “激活 `zhang-yiming` 或 `jensen-huang` skill，推演我当前手头 A 与 B 两个职业选择的长期复利和取舍。”
2. **想法压力测试（挑刺纠偏）**
   > “用黄仁勋的战略撤退视角，或用马斯克的‘删除先于优化’视角，对我的这个方案做一次压力测试。”
3. **三巨头圆桌交锋（张一鸣 vs 黄仁勋 vs 马斯克）**
   > “调用 `persona-council`，让 `zhang-yiming`、`jensen-huang` 和 `elon-musk` 各自独立评估我的这个新方向，拆解他们底层公理、风险偏好与方法论的根本分歧。”
4. **扩充新人物**
   > “使用 `persona-distiller` 帮我提炼【芒格 / 王阳明 / 纳瓦尔 / 某位你关注的人】的思想逻辑，补充到这个仓库里。”

---

## 如何挂载到 Antigravity 全局生效

只在当前仓库打开时，`.agents/skills.json` 会自动加载 `skills/` 下的全部技能。如果你想在**任意项目或对话**里随时调用它们，可以任选下面一种方式注册到 `~/.gemini/config/`：

### 方式 A：作为 Skills 注册（轻量，推荐优先使用）

编辑 `~/.gemini/config/skills.json`（若不存在则新建），将本仓库的 `skills` 目录加入 `entries`：

```json
{
  "entries": [
    {
      "path": "~/Projects/persona-skills/skills"
    }
  ]
}
```

### 方式 B：作为完整 Plugin 挂载（同时启用 `rules/AGENTS.md` 推演纪律与卡片快捷入口）

二选一即可：

1. **软链接到插件目录**：
   ```bash
   ln -s ~/Projects/persona-skills ~/.gemini/config/plugins/persona-skills
   ```
2. **或通过 `~/.gemini/config/plugins.json` 显式引入**：
   ```json
   {
     "entries": [
       {
         "path": "~/Projects",
         "include_only": ["persona-skills"]
       }
     ]
   }
   ```

> **提示**：`rules/AGENTS.md` 已显式限定“仅在激活人物 Skill 或明确要求人物推演时生效”，挂载为全局 Plugin 也不会干扰日常写代码或普通问答。

---

## 仓库维护原则

- **绝不编造语录**：所有原话必须附可追溯的年份、场合与出处，存疑语录不入库。
- **保持 `SKILL.md` 精炼**：只放公理、推理算法和纪律；大段案例与语录放进 `references/` 按需读取。
- **每次新增或修改后必跑标定**：用 `examples/calibration-qa.md` 测试，确认模型是在“用其逻辑推理”，而不是在“背诵其口号”。
