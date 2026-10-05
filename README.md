# create-crush

> 基于 LLM 的聊天记录分析、人物画像构建与关系信号整理工具。  
> 目标是利用当前大语言模型的文本理解、风格归纳和关系分析能力，帮助缺乏恋爱经验、表达能力较弱的理工科用户，更系统地理解互动对象并优化追求与沟通策略。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Python 3.9+](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://python.org)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blueviolet)](https://claude.ai/code)

---

## 项目简介

`create-crush` 是一个围绕“聊天记录整理 + Persona 建模 + 关系分析”构建的 Skill 工程。

它的核心用途不是简单生成“像某个人的聊天机器人”，而是把零散的聊天、语音转写、社交内容和主观观察整理为一套可维护的结构化资料，帮助用户：

- 提取对象稳定的说话风格与表达习惯
- 识别互动中的兴趣信号、舒适度、边界感和关系阶段
- 复盘聊天内容，减少过度脑补或错误解读
- 为后续沟通、邀约和推进节奏提供更清晰的依据

---

## 适用场景

本项目适合以下场景：

- 有较完整的聊天记录，希望分析对方风格与互动模式
- 不擅长恋爱沟通，希望通过结构化分析降低误判
- 想长期维护某个对象的画像、记忆和关系进展
- 想把聊天分析、Persona 和模拟回复能力接入 Claude Code

---

## 核心思路

项目围绕三类信息构建：

### 1. Persona（人物画像）

提取对象稳定的行为与表达特征，例如：

- 常用口头禅
- 语气、断句、标点习惯
- 关心人的方式
- 回消息节奏
- 对暧昧、边界、压力和冲突的典型反应

### 2. Memory（关系记忆）

沉淀与对象之间已经发生过的关键事实和上下文，例如：

- 认识路径
- 共同经历
- 长期话题
- 重要节点
- inside jokes
- 对方反复提到的烦恼、偏好与禁区

### 3. Analysis（关系分析）

利用 LLM 的文本分析能力，对聊天进行更细致的结构化判断，例如：

- 自我披露强度
- 双向回应性
- 互动黏性
- 关系不确定性
- 可能的升温信号与风险点

---

## 项目目标

项目目标可以概括为三点：

1. **把聊天资料变成可维护数据**  
   将零散截图、聊天记录和主观印象整理为清晰文档，而不是停留在模糊感觉层面。

2. **把关系判断从“直觉”升级为“可解释分析”**  
   尽量用可复核的聊天证据和稳定维度去支撑判断，而不是只靠情绪化猜测。

3. **为真实沟通提供辅助，而不是替代真实沟通**  
   项目最终服务的是现实中的聊天、邀约和推进，而不是构建封闭的虚拟依恋。

---

## 当前目录结构

```text
.
├── SKILL.md
├── README.md
├── README_EN.md
├── requirements.txt
├── prompts/
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
├── tools/
│   ├── wechat_parser.py
│   ├── qq_parser.py
│   ├── social_parser.py
│   ├── photo_analyzer.py
│   ├── version_manager.py
│   └── skill_writer.py
└── crushes/
    └── {slug}/
        ├── persona.md
        ├── memory.md
        └── analysis_references.md
```

---

## 主要能力

### 聊天记录与材料导入

支持将不同来源的资料整理为统一输入，包括：

- 微信聊天记录
- QQ 聊天记录
- 社交媒体截图
- 照片与时间线材料
- 用户手动补充的回忆和观察

### Persona 构建

根据原始材料总结对象的：

- 语言风格
- 情绪表达模式
- 熟络方式
- 回避模式
- 边界与底线

### 关系复盘与信号判断

结合 Memory 与 Persona，对聊天进行辅助分析，例如：

- 这是礼貌性聊天还是明显高于普通同学/朋友的互动
- 对方是在单纯倾诉，还是已经把用户当作稳定的情绪承接对象
- 互动是在升温、停滞，还是已经出现消耗与失衡

### 持续更新

支持基于新聊天、新截图和纠正意见继续迭代，而不是一次性生成后就失效。

---

## 典型工作流

### Step 1：录入基础信息

输入对象代号、关系背景和初始印象。

### Step 2：导入材料

导入聊天记录、照片、截图或手动回忆。

### Step 3：生成结构化档案

生成并维护以下核心文件：

- `persona.md`
- `memory.md`
- `analysis_references.md`

### Step 4：做关系分析或对话模拟

基于上述资料进行：

- 聊天风格模拟
- 关系阶段复盘
- 升温风险判断
- 沟通与推进建议

---

## 安装

### Claude Code

```bash
mkdir -p .claude/skills
git clone https://github.com/Zh4iYuJia/MSTcrush-skills .claude/skills/create-crush
```

或全局安装：

```bash
git clone https://github.com/Zh4iYuJia/MSTcrush-skills ~/.claude/skills/create-crush
```

### 依赖

```bash
pip install -r requirements.txt
```

---

## 使用方式

在 Claude Code 中可通过以下方式触发：

- `/create-crush`
- `/update-crush {slug}`
- `/{slug}`
- `/{slug}-persona`
- `/{slug}-memory`

常见用法包括：

- 创建一个新的对象画像
- 追加聊天记录并更新档案
- 修正“这个人不会这样说话”的偏差
- 基于现有档案分析一段新聊天

---

## 这个项目解决什么问题

很多缺乏恋爱经验的用户，在面对喜欢的人时常见问题不是“没有感觉”，而是：

- 看不懂聊天信号
- 不知道什么话该接、什么节奏该放慢
- 容易把礼貌误判成好感，或者把好感误判成普通朋友
- 情绪上投入很多，但缺少结构化复盘能力

`create-crush` 试图解决的不是“替用户谈恋爱”，而是：

- 帮用户更准确地读懂文本互动
- 帮用户减少误判和过度投射
- 帮用户在追求过程中更有分寸感和策略感

---

## 边界与原则

本项目用于：

- 个人关系复盘
- 聊天分析
- Persona 维护
- 沟通辅助

本项目不应用于：

- 骚扰、跟踪或侵犯隐私
- 冒充真人进行外部交流
- 替代现实中的真诚表达与真实沟通
- 在对方明确拒绝后继续借助工具强化执念

---

## 说明

本工程的价值不在于“完美模拟某个人”，而在于把 LLM 的文本分析能力真正落到关系理解和现实沟通上。

如果使用得当，它更像一个：

- 恋爱沟通分析器
- 聊天复盘工具
- Persona 资料管理器
- 关系推进辅助系统

而不是一个单纯的角色扮演玩具。

