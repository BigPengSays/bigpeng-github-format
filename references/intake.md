# 信息采集

信息采集是**第一步**的前置动作。先判断**输入模式**，再采集。

## 输入模式判断

| 模式 | 条件 | 第一步策略 |
|------|------|------------|
| **有 README** | 文件存在且有实质 `##` 节或可用正文 | 以原文为权威，尽量沿用版块 |
| **无 README** | 文件不存在、几乎为空、或仅一行标题 | **生成经典全套**，见 [no-readme-scaffold.md](no-readme-scaffold.md) |

## 有 README：原文盘点

| 字段 | 说明 |
|------|------|
| `ORIGINAL_H1` | 原 `#` 完整文案 |
| `SECTIONS[]` | 全部 `##`，保持顺序 |
| `HAS_WHY` | 是否已有 Why/为什么/简介节 |
| `PRIMARY_LANGUAGE` | 中文 / English |
| `INTRO` | H1 下首段 → tagline + Why 素材 |
| `BOUNDARY` | 边界/限制 bullet → 日后改 FAQ 问答 |

## 无 README：仓库推断

| 字段 | 信息源 |
|------|--------|
| `ORIGINAL_H1` | **有 README**：原 `#` 原样保留。**无 README**：对话 → SKILL description → package → About → repo 名（见 title-design.md） |
| `TAGLINE` | SKILL.md description / package description |
| `CAPABILITIES` | SKILL.md 正文、scripts/、references/ |
| `USAGE_HINTS` | examples/prompts.md、SKILL 工作流 |
| `INSTALL_HINTS` | 依赖文件、clone 路径、skill 安装惯例 |
| `BOUNDARY_HINTS` | SKILL 硬规则、限制说明 |
| `TREE` | 实际目录结构 |
| `LICENSE` | LICENSE 文件 |
| `GAPS[]` | 无法推断、需用户补充的项 |

## 第一步产出

**有 README**：映射标准槽 → 定稿 `##` → 导航草案  

**无 README**：按 [no-readme-scaffold.md](no-readme-scaffold.md) 定经典全套 `##` → 导航草案 → 列出 `GAPS[]`

共用核对：[nav-design.md](nav-design.md)

1. Why **必选**（有 README 时缺则补；无 README 时新建）  
2. 填导航草案 `{标签, 对应 ##, 预计 href}`  

## 第二步产出

1. 按定稿 `##` **重算 href**，填验证核对表  
2. 逐节润色（[content-polish.md](content-polish.md)）  
3. 锚点全部通过后写 Hero HTML  

## 输入源

- **GitHub URL**：拉 README + remote 元数据；无 README 则扫仓库树  
- **本地仓库**：读 README.md、SKILL.md、LICENSE、examples/  
- **仅路径无 README**：走无 README 脚手架  

## 字段优先级

**有 README**：原 H1 原样保留  

**无 README**：用户对话 → SKILL.md description → package description → GitHub About → repo 名

## 冲突

- 安装命令不一致 → 以 SKILL.md / 官方脚本为准  
- 无 License 文件 → 待你补充说明，README 不写假许可证  
