---
name: bigpeng-github-format
description: >-
  将 GitHub 仓库 README 格式化为居中 Hero、徽章导航与分层文档结构。
  三步流程：分析仓库规划版块 → 实现初版 ## 节 → 润色连贯并真人化后写 Hero。
  保留原标题与正文，补必选 Why 节与 header emoji，Hero 导航锚点须可跳转。
  无 README 时生成全套经典版块（Why/Features/Usage/Install/FAQ 等）。
  用户提供仓库 URL、本地路径或 README.md，并要求格式化、美化时使用。
---

# BigPeng GitHub README 美化

把任意仓库 README 整理成分层文档首页：**居中 Hero、徽章带、可点击的锚点导航、分层结构**。

**核心原则：美化 ≠ 重写。** 有 README 时**尽量使用原文**（含 H1 与各版块）；无 README 时从上下文与仓库内容推断标题并生成经典全套。**Why 必选**；Hero 导航在正文 `##` 定稿且润色完成后生成，**每个锚点必须可跳转**。

完整决策流程见 [references/implementation-logic.md](references/implementation-logic.md)；标题规则见 [references/title-design.md](references/title-design.md)；**emoji 备选**见 [references/header-emoji.md](references/header-emoji.md)。

---

## 实现逻辑（摘要）

| 步骤 | 做什么 |
|------|--------|
| **0. 判断模式** | 有 README → 尽量用原文；无 README → 推断标题 + 生成经典版块 |
| **1. 第一步** | 分析仓库作用 + 规划版块 + Hero 导航草案（不写 README） |
| **2. 第二步** | 实现初版 `##` 节（H1 + tagline + 正文；**无 Hero**） |
| **3. 第三步** | 连贯润色 + 真人化 → 验证锚点 → 写 Hero + 终版 README |
| **4. 输出** | README.md + 对话「美化摘要」「待你补充」 |

---

## 必须执行的三步（不可跳过、不可颠倒）

### 第一步：分析仓库 + 规划版块

**目标**：搞清仓库是干什么的、给谁用，定稿正文有哪些 `##` 及 Hero 导航要链到哪些锚点。**此步不写 README 文件**。

1. **判断输入模式** — 见 [references/intake.md](references/intake.md)  
   - **有 README**：盘点 H1、全部 `##`、首段、安装、边界说明  
   - **无 README**：扫 SKILL / LICENSE / examples / 目录树；见 [references/no-readme-scaffold.md](references/no-readme-scaffold.md)

2. **仓库分析** — 见 [references/repo-analysis.md](references/repo-analysis.md)  
   - 类型（Skill / CLI / SDK / …）、核心能力、目标读者、主要入口  
   - 产出「仓库画像」与版块取舍提示  

3. **版块规划**（按输入模式分支） — 见 [references/section-catalog.md](references/section-catalog.md)、[references/preserve-content.md](references/preserve-content.md)  

   **有 README**  
   - **H1**：原文保留；无 leading emoji 时从 [header-emoji.md](references/header-emoji.md) 补 1 个  
   - **各 `##`**：尽量沿用原有版块；节名可规范化（Why / Usage / Install / FAQ）；项目独有节**保留原名**  
   - **必选**：Why（原文无从首段/简介拆出则规划为新建）  
   - **有内容则保留**：Usage、Install、FAQ  

   **无 README**  
   - **经典版块全部规划**：Why、Features、Usage、Install、FAQ、仓库结构、License（见 no-readme-scaffold）  
   - Hero 导航覆盖：为什么 · 功能 · 用法 · 安装 · FAQ（+ 结构 / 示例外链，有则加）  
   - 信息缺口记入 `GAPS[]`  

4. **Hero 导航草案**（只规划，不写 HTML） — 见 [references/nav-design.md](references/nav-design.md)  
   - 列出 `{导航标签 → 目标 ## 标题 → 预计 href}` 核对表  
   - 5–7 项为宜；License、Star History **不进**导航  

**第一步产出（对话内确认，不写文件）**：

```text
仓库画像: 类型 / 能力 / 读者 / 推断依据
最终 ## 顺序:
1. ## 🤔 为什么
2. ## …
…

导航草案:
| 标签 | 对应 ## | 预计 href |
|------|---------|-----------|
| 为什么 | ## 🤔 为什么 | #-为什么 |
| … | … | … |

GAPS[]: （无 README 或信息不足时）
```

---

### 第二步：实现初版版块

**目标**：按第一步定稿结构，写出初版 README 正文；结构到位、信息完整，**不要求此时通顺或去 AI 腔**。

详见 [references/draft-implementation.md](references/draft-implementation.md)。

1. **写 H1 + tagline + badges（可选）**  
   - 有 README：H1 原样保留；tagline 从首段提炼  
   - 无 README：推断 H1 + tagline（[title-design.md](references/title-design.md)）  

2. **写全部 `##` 正文**  
   - 有 README：迁移/合并原文到规划槽位（[preserve-content.md](references/preserve-content.md)）  
   - 无 README：从仓库推断生成各节（[no-readme-scaffold.md](references/no-readme-scaffold.md)）  
   - 为 H1 与各 `##` 分配 emoji（[header-emoji.md](references/header-emoji.md)）  
   - FAQ 可先保留 bullet，第三步改问答  

3. **禁止写 Hero HTML** — 留第三步；可在顶加注释 `<!-- Hero 导航：第三步写入 -->`  

**第二步产出**：`README.md` 初稿 = H1 + tagline + badges + 全部 `##`；**无 Hero 导航块**。

---

### 第三步：润色 + 真人化 + Hero 定稿

**目标**：逐节通顺、去 AI 腔；锚点验证通过后写 Hero，输出终版。

1. **连贯润色** — 见 [references/content-polish.md](references/content-polish.md)  
   - 迁移/合并后的节要通顺；Why 独立可读；节间衔接  
   - tagline 与 Why 去重复  

2. **真人化** — 见 [references/humanize-content.md](references/humanize-content.md)  
   - 删套话；短句优先；FAQ 改读者口吻问答  
   - **禁止**编造事实、改 H1、覆盖表格/命令  

3. **锚点验证** — 见 [references/nav-design.md](references/nav-design.md)  
   - 按**定稿后的 `##` 标题**重算 href  
   - **每个** `#anchor` 必须有对应 `##`；失效项删或补 `##`  

4. **生成 Hero + 完整 README** — 见 [references/readme-template.md](references/readme-template.md)  

5. **自检** — [references/qa-checklist.md](references/qa-checklist.md) + [references/followup-template.md](references/followup-template.md)

---

## 硬规则

1. **保留 H1 与正文**：有 README 时 H1 与正文**尽量用原文**；禁止用 repo 名替换产品名。见 [references/preserve-content.md](references/preserve-content.md)、[references/title-design.md](references/title-design.md)。
2. **Why 必选**；Hero 导航**必须含 Why/为什么**。
3. **先规划 → 再写初版 ## → 再润色验证锚点写 Hero**——禁止跳步或颠倒。
4. **第二步禁止写 Hero HTML**；第三步必须润色且 FAQ 改问答——不允许把边界 bullet 无修改地留在终版。
5. **Star History 默认不加**；片段放「待你补充」。
6. **固定输出**：「美化摘要」+「待你补充」。
7. **生成内容禁止出现 `book-to-skill`**（含链接、徽章、正文描述）；用「分层首页」「Hero + 导航 + 分层结构」等表述替代。
8. **标题 emoji**：H1 与各 `##` 须带 1 个贴切 emoji；每槽位从 [header-emoji.md](references/header-emoji.md) 备选池选取，**轮换避免千篇一律**；License 不加。

## 示例触发

```text
用 bigpeng-github-format 美化 https://github.com/foo/bar
```

```text
美化 README，保留原标题和章节，补 Why，导航要能跳转，各节内容要通顺
```
