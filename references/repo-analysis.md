# 仓库分析

第一步的前置动作：**先搞清这个仓库是干什么的、给谁用**，再决定版块取舍。此步只产出「仓库画像」，不写 README。

与 [intake.md](intake.md) 配合：intake 负责字段采集，本文件负责**理解与归类**。

---

## 分析清单

按优先级读仓库，填以下字段（对话内确认即可）：

| 字段 | 说明 | 常见信息源 |
|------|------|------------|
| `REPO_TYPE` | 仓库类型（见下表） | 目录结构、入口文件 |
| `CORE_VALUE` | 核心能力 1–3 句 | SKILL.md、README 首段、package description |
| `AUDIENCE` | 目标读者 | 文档语气、依赖栈、使用场景 |
| `PRIMARY_ENTRY` | 主要入口文件 | `SKILL.md` / `src/` / `cli` / `docs/` |
| `HAS_INSTALL` | 是否有可写安装步骤 | package.json、Makefile、安装脚本 |
| `HAS_EXAMPLES` | 是否有示例外链 | `examples/`、`demo/` |
| `LANGUAGE` | README 主语言 | 原文或 SKILL 语言 |
| `UNIQUE_SECTIONS` | 项目独有节（非标准槽） | 原 README `##`、SKILL 特殊章节 |

---

## 仓库类型判断

| 类型 | 典型信号 | 版块侧重 |
|------|----------|----------|
| **Skill** | 根目录或 `.cursor/skills/` 下有 `SKILL.md` | Why、Usage（触发语）、Install（软链）、FAQ（硬规则） |
| **CLI 工具** | `bin/`、`cmd/`、可执行入口、`--help` | Install、Usage（命令示例）、Features（子命令） |
| **SDK / 库** | `package.json`、`pyproject.toml`、`src/` API | Install、Usage（代码示例）、Features（能力列表） |
| **文档 / 教程** | 以 `docs/` 为主，少可执行代码 | Why、Features（目录说明）、Examples 外链 |
| **示例集合** | 大量 `examples/`、README 短 | Features（示例索引）、Usage、Structure |
| **Monorepo** | 多 package、workspace | Structure 必选；Install/Usage 可能分模块 |
| **配置 / 模板** | 以模板文件为主 | Why、Usage（怎么用模板）、Install |

类型不确定时，在仓库画像里写「推断：…，依据：…」，不影响继续规划。

---

## 能力画像模板

第一步结束时，对话内输出：

```text
仓库画像
- 类型：（Skill / CLI / …）
- 核心能力：（1–3 句，用自己的话概括，不抄 description 整段）
- 目标读者：（如：Cursor 用户、Node 开发者）
- 主要入口：（SKILL.md / package.json / …）
- 推断依据：（读了哪些文件）
- 版块提示：（如：无 Install 步骤 → Install 节写「克隆即用」；有 examples/ → 导航加示例外链）
```

---

## 分析 → 版块映射

根据画像，在 [section-catalog.md](section-catalog.md) 标准槽上做取舍：

| 分析结论 | 版块决策 |
|----------|----------|
| 无安装步骤、clone 即用 | Install 节可简化为 clone + 路径说明 |
| 无 `examples/` | 导航不加「示例」外链 |
| SKILL 硬规则多 | FAQ 优先从硬规则拆问答 |
| 原 README 有独有公式/表格节 | **保留原名**，进导航则必须有对应 `##` |
| 纯文档仓、无代码 | Features 改为「内容目录」或「包含什么」 |
| Monorepo | Structure 必选，Usage 可按子包分块 |

**Why 始终必选**，与仓库类型无关。

---

## 有 README vs 无 README

| 模式 | 分析侧重 |
|------|----------|
| **有 README** | 原文 `##` 与画像是否一致；独有节是否反映核心能力 |
| **无 README** | 全靠仓库文件推断；分析结果直接驱动 [no-readme-scaffold.md](no-readme-scaffold.md) 各节内容来源 |

---

## 禁止

- 未读仓库就假定类型或功能  
- 把 GitHub About 一句话当完整能力描述  
- 分析阶段写 README 或 Hero HTML  

分析完成后进入版块规划：定 `##` 顺序 + 导航草案（见 [nav-design.md](nav-design.md)）。
