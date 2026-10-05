# MST crush workspace

> 我的个人暗恋对象分析仓库。  
> 用来把聊天记录、相处细节和主观观察整理成可维护的 **persona / memory / analysis** 档案，而不是一个泛化演示项目。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://python.org)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)

---

## 这是什么

这个仓库现在的定位很明确：

- **它首先是我的个人资料库**，不是面向所有人的通用样板
- 用来沉淀某个对象的 **说话方式、关系记忆、互动风格、分析依据**
- 既能作为 **Claude Code Skill** 使用，也能作为我自己的长期记录仓库继续维护

当前已经整理的对象在：

- `crushes/vicky/persona.md`
- `crushes/vicky/memory.md`
- `crushes/vicky/analysis_references.md`

其中：

- `persona.md`：她怎么说话、怎么表达关心、边界感和关系模式
- `memory.md`：你们之间已经发生过的关键经历和上下文
- `analysis_references.md`：给聊天分析提供学术参考，说明分析维度来自哪类文献

---

## 仓库目标

这个仓库不是为了“凭空模拟一个人”，而是为了做三件事：

1. **把零散聊天记录结构化**  
   让“她到底平时怎么说话、会怎么接话、什么话题会展开”变成可维护文档。

2. **把关系判断和证据拆开**  
   主观感觉归主观感觉，聊天信号、行为特征、学术参考各自独立保存。

3. **把后续更新变简单**  
   后面有新聊天、新语音、新照片、新判断时，可以直接继续补档，不用每次重来。

---

## 当前结构

```text
.
├── SKILL.md                      # 主 Skill 定义
├── README.md                     # 当前中文说明（个人版）
├── README_EN.md                  # 英文版说明
├── requirements.txt              # 解析脚本依赖
├── prompts/                      # 生成、修正、合并、分析用提示词
│   ├── intake.md
│   ├── memory_analyzer.md
│   ├── memory_builder.md
│   ├── persona_analyzer.md
│   ├── persona_builder.md
│   ├── merger.md
│   ├── correction_handler.md
│   ├── confession_simulator.md
│   ├── date_simulator.md
│   ├── progression_tracker.md
│   └── crush_analyzer.md
├── tools/                        # 聊天记录 / 照片 / 社交内容解析工具
│   ├── wechat_parser.py
│   ├── qq_parser.py
│   ├── social_parser.py
│   ├── photo_analyzer.py
│   ├── version_manager.py
│   └── skill_writer.py
└── crushes/
    └── vicky/
        ├── persona.md
        ├── memory.md
        └── analysis_references.md
```

---

## 我的使用方式

我现在把这个仓库当成一套持续更新的工作流来用：

### 1. 收集原始材料

- 微信 / QQ 聊天记录
- 语音转文字后的片段
- 截图、照片、朋友圈或别的社交内容
- 我对某次互动的主观补充说明

### 2. 更新人物档案

- 新的说话习惯、口头禅、表达方式 → 更新 `persona.md`
- 新的共同经历、重要节点、关系变化 → 更新 `memory.md`
- 如果某次分析需要“为什么这么判断”的依据 → 补进 `analysis_references.md`

### 3. 用 Skill 做回放或模拟

- `/create-crush`
- `/update-crush {slug}`
- `/{slug}`
- `/{slug}-persona`
- `/{slug}-memory`

这样做的重点不是“沉迷模拟”，而是方便我：

- 回看关系是怎么一步步变化的
- 检查某些判断是不是过度解读
- 让 persona 的一致性更高

---

## 安装成 Skill

如果我要把这个仓库直接接到 Claude Code 里，可以这样装：

```bash
# 在 git 仓库根目录执行
mkdir -p .claude/skills
git clone https://github.com/Zh4iYuJia/MSTcrush-skills .claude/skills/create-crush
```

或者全局安装：

```bash
git clone https://github.com/Zh4iYuJia/MSTcrush-skills ~/.claude/skills/create-crush
```

可选依赖：

```bash
pip install -r requirements.txt
```

---

## 我关心的不是“泛用功能”，而是这些点

- **人物一致性**：她说话像不像她
- **关系上下文**：回应里有没有真正带上共同经历
- **更新成本**：后续加材料是不是方便
- **分析边界**：能不能区分“有文献支持的推断”与“纯主观脑补”

这也是为什么仓库里除了 Skill 本体，还保留：

- prompts：方便持续生成/修正
- tools：方便导入原始材料
- analysis references：避免把情绪判断硬说成结论

---

## 隐私与边界

这个仓库只应该用于：

- 个人整理
- 对话回顾
- 关系分析
- Skill 调试

不应该用于：

- 骚扰真人
- 冒充真人
- 替代真实沟通
- 绕过对方边界去制造“虚拟关系”

我保留这些资料，是为了更清楚地理解一段关系，不是为了把现实中的人变成可操控对象。

---

## 现阶段备注

现在这个仓库已经不是一个空壳项目了，而是**明确绑定我自己的使用场景**：

- 已经有具体对象档案：`vicky`
- 已经有持续补充的人设数据
- 已经有分析参考文献列表
- 后续 README 也会继续按“我实际怎么用”去更新，而不是再写回通用宣传文案

如果以后扩展更多对象，就继续按 `crushes/{slug}/` 往下维护。

