# 无 README 时的经典版块脚手架

用户**未提供 README**（空文件、只有标题、或只给仓库路径）时，第一步不是「保留原有版块」，而是**生成全套经典版块**。

## 两种输入模式

| 模式 | 第一步策略 |
|------|------------|
| **有 README** | 尽量沿用原有 `##`；节名可规范化；缺的才补 |
| **无 README** | **经典版块全部生成**；从仓库文件推断内容 |

判断「无 README」：文件不存在、几乎为空、或只有 `# 项目名` 一行且无实质 `##` 节。

---

## 无 README 时必须生成的经典版块

按正文顺序，**以下 `##` 节全部要有**（License 不进 Hero 导航）：

| 顺序 | 槽位 | 中文节名 | 英文节名 | 进 Hero 导航 |
|------|------|----------|----------|--------------|
| 1 | Why | `## 🤔 为什么` | `## 🤔 Why` | ✓ 必选 |
| 2 | Features | `## 功能` | `## Features` | ✓ |
| 3 | Usage | `## 使用方法` | `## Usage` | ✓ |
| 4 | Install | `## 安装` | `## Install` | ✓ |
| 5 | FAQ | `## 常见问题` | `## FAQ` | ✓ |
| 6 | Structure | `## 仓库结构` | `## Repository structure` | 可选（有树则建议进） |
| 7 | License | `## License` | `## License` | ✗ |

**Examples**：若存在 `examples/`、`examples/prompts.md` 等，Hero 导航加「示例 / Examples」外链，Usage 节内提一句即可。

**Star History、Banner**：默认不生成；缺口写进「待你补充」。

---

## 内容从哪来（禁止编造）

按优先级读仓库，能写多少写多少；**写不出的留 honest 占位或挪到「待你补充」**，不虚构 Star 数、性能数据、赞助商。

| 版块 | 信息源（按优先级） |
|------|-------------------|
| **H1** | `SKILL.md` description 提炼 / 用户对话 / `package.json` description / repo 名（最后）；见 [title-design.md](title-design.md) |
| **Tagline** | `SKILL.md` description 首句 / package description / repo About |
| **Why** | `SKILL.md` 首段、description、解决的问题；补痛点与「不做什么」 |
| **Features** | `SKILL.md` 能力列表、scripts/、references/、核心 API |
| **Usage** | `examples/prompts.md`、`SKILL.md` 工作流、可执行命令 |
| **Install** | 现有安装方式（npm/pip/skill 软链）、clone 命令、依赖文件 |
| **FAQ** | `SKILL.md` 硬规则/边界、常见限制；至少 3 条问答体 |
| **Structure** | 实际目录树（`SKILL.md`、`references/`、`examples/` 等） |
| **License** | `LICENSE` 文件；无文件则在「待你补充」说明，README 不写假许可证 |

### 无 README 时的 FAQ 最低要求

即使仓库无边界说明，也要生成 FAQ 节，至少覆盖：

1. **这个项目/ skill 是做什么的？**（一句话 + 链接 SKILL.md）
2. **不能做什么 / 常见误用？**（从 SKILL 硬规则推断，推断不出则写「见 SKILL.md」）
3. **怎么开始用？**（指向 Usage / Install）

---

## 无 README 时的 Hero 导航（中文示例）

定稿 `##` 后，导航草案通常类似：

```text
| 标签 | 对应 ## | 预计 href |
|------|---------|-----------|
| 为什么 | ## 🤔 为什么 | #-为什么 |
| 功能 | ## 功能 | #功能 |
| 用法 | ## 使用方法 | #使用方法 |
| 安装 | ## 安装 | #安装 |
| FAQ | ## 常见问题 | #常见问题 |
| 结构 | ## 仓库结构 | #仓库结构 |
| 示例 | examples/prompts.md | （文件外链，有则加） |
```

英文 README 用 Why · Features · Usage · Install · FAQ · Structure · Examples。

---

## 无 README 时的第一步产出模板

```text
输入模式：无 README → 生成经典全套

最终 ## 顺序：
1. ## 🤔 为什么
2. ## 功能
3. ## 使用方法
4. ## 安装
5. ## 常见问题
6. ## 仓库结构
7. ## License

导航草案：（见上表）

信息缺口：（列出无法从仓库推断、需用户补充的项）
```

---

## 第二步注意

- 新生成各节仍须**通顺连贯**（见 [content-polish.md](content-polish.md)），不是 bullet 堆砌  
- FAQ 一律**问答体**  
- 锚点验证规则与「有 README」相同  
- 无法在仓库中找到的信息 → README 用「见 SKILL.md / 待补充」类 honest 表述，详细清单进对话「待你补充」
