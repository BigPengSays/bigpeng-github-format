---
name: bigpeng-github-format
description: >-
  将 GitHub 仓库 README 格式化为居中 Hero、徽章导航与分层文档结构。
  保留原标题与正文，补必选 Why 节，Hero 导航锚点须可跳转，迁移版块需润色通顺。
  无 README 时生成全套经典版块（Why/Features/Usage/Install/FAQ 等）。
  用户提供仓库 URL、本地路径或 README.md，并要求格式化、美化时使用。
---

# BigPeng GitHub README 美化

把任意仓库 README 整理成分层文档首页：**居中 Hero、徽章带、可点击的锚点导航、分层结构**。

**核心原则：美化 ≠ 重写。** 有 README 时**尽量使用原文**（含 H1 与各版块）；无 README 时从上下文与仓库内容推断标题并生成经典全套。**Why 必选**；Hero 导航在正文 `##` 定稿后生成，**每个锚点必须可跳转**。

完整决策流程见 [references/implementation-logic.md](references/implementation-logic.md)；标题规则见 [references/title-design.md](references/title-design.md)。

---

## 实现逻辑（摘要）

| 步骤 | 做什么 |
|------|--------|
| **0. 判断模式** | 有 README → 尽量用原文；无 README → 推断标题 + 生成经典版块 |
| **1. 信息采集** | 有 README：盘点 H1、`##`、正文；无 README：扫 SKILL / LICENSE / examples / 目录树 |
| **2. 定 H1** | 有 README：**原标题原样保留**；无 README：对话 → SKILL → package → About → repo 名 |
| **3. 第一步** | 规划版块 + Hero 导航草案 |
| **4. 第二步** | 验证锚点 + 润色各节 → 写 Hero + README |
| **5. 输出** | README.md + 对话「美化摘要」「待你补充」 |

---

## 必须执行的两步（不可跳过、不可颠倒）

### 第一步：规划版块 + Hero 超链接草案

**目标**：定稿正文有哪些 `##`，以及 Hero 导航要链到哪些锚点。

1. **信息采集** — 先判断输入模式  
   - **有 README**：**尽量使用原文**（H1、各 `##`、段落、表格、命令、链接）；盘点全部 `##`、首段、安装、边界说明  
   - **无 README**：读仓库文件 + 用户对话上下文，**推断合适 H1** 并生成经典版块；见 [references/no-readme-scaffold.md](references/no-readme-scaffold.md)、[references/title-design.md](references/title-design.md)  
   - 共用：[references/preserve-content.md](references/preserve-content.md)、[references/intake.md](references/intake.md)、[references/implementation-logic.md](references/implementation-logic.md)

2. **版块规划**（按输入模式分支）  

   **有 README**  
   - **H1 原样保留**（仅改居中）；**尽量沿用原有版块与正文**  
   - 节名尽量规范化：对齐 Why / Usage / Install / FAQ / Examples；项目独有节**保留原名**  
   - **必选**：Why（原文无从首段/简介拆出则新建）  
   - **有内容则保留**：Usage、Install、FAQ  

   **无 README**  
   - **经典版块全部生成**：Why、Features、Usage、Install、FAQ、仓库结构、License（见 no-readme-scaffold）  
   - Hero 导航覆盖：为什么 · 功能 · 用法 · 安装 · FAQ（+ 结构 / 示例外链，有则加）  
   - 内容从仓库推断；**禁止编造**；缺口写 honest 占位，详细清单进「待你补充」  

   映射表：[references/nav-design.md](references/nav-design.md)、[references/section-catalog.md](references/section-catalog.md)

3. **Hero 导航草案**（此步只规划，不写最终 HTML）  
   - 列出 `{导航标签 → 目标 ## 标题 → 预计 href}` 核对表  
   - 5–7 项为宜；语言跟 README 主语言  
   - `examples/*.md` 等外链可用「示例 / Examples」标签  
   - License、Star History **不进**导航  

**第一步产出（写入 README 前先在脑中或对话里确认）**：

```text
最终 ## 顺序：
1. ## 🤔 为什么
2. ## …
…

导航草案：
| 标签 | 对应 ## | 预计 href |
|------|---------|-----------|
| 为什么 | ## 🤔 为什么 | #-为什么 |
| … | … | … |
```

### 第二步：验证锚点 + 润色各节内容

**目标**：Hero 每个链接可点击；每个版块读起来通顺连贯。

1. **锚点验证**（见 [references/nav-design.md](references/nav-design.md)）  
   - 按**定稿后的 `##` 标题**重算 href，填入核对表  
   - **每个** `#anchor` 必须有对应 `##`；外链文件除外  
   - **禁止**导航指向仅有 `<details>`、无 `##` 的块  
   - 核对表任一项「存在？」为否 → 删导航项或补 `##`，**不得**带失效链接发布  

2. **内容润色**（见 [references/content-polish.md](references/content-polish.md)）  
   - 逐节检查：迁移、合并、拆段后的上下文是否连贯  
   - Why：独立可读，有痛点与能力边界，不与 tagline 整段重复  
   - FAQ：边界类 bullet 改为**问答体**，不要原样粘贴  
   - Usage / Install：补引导句，与前后节衔接  
   - **保留**表格、代码、命令、路径、事实数据；只修过渡与重复  

3. **生成 Hero + 完整 README**  
   - 锚点验证通过后再写 Hero 导航 HTML  
   - 骨架：[references/readme-template.md](references/readme-template.md)  

4. **自检**：[references/qa-checklist.md](references/qa-checklist.md) + 输出 [references/followup-template.md](references/followup-template.md)

---

## 硬规则

1. **保留 H1 与正文**：有 README 时 H1 与正文**尽量用原文**；禁止用 repo 名替换产品名。见 [references/preserve-content.md](references/preserve-content.md)、[references/title-design.md](references/title-design.md)。
2. **Why 必选**；Hero 导航**必须含 Why/为什么**。
3. **先规划版块，再验证锚点，最后写 Hero**——禁止先写导航再凑正文。
4. **迁移版块必须润色**——不允许把边界 bullet 或首段原句无修改地塞进新节名。
5. **Star History 默认不加**；片段放「待你补充」。
6. **固定输出**：「美化摘要」+「待你补充」。
7. **生成内容禁止出现 `book-to-skill`**（含链接、徽章、正文描述）；用「分层首页」「Hero + 导航 + 分层结构」等表述替代。

## 示例触发

```text
用 bigpeng-github-format 美化 https://github.com/foo/bar
```

```text
美化 README，保留原标题和章节，补 Why，导航要能跳转，各节内容要通顺
```
