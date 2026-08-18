# 标题（H1）设计

Hero 的 `<h1>` 是读者第一眼看到的产品名。**写人话、写能力**，不要堆 repo slug、作者名、英文术语。

## 两种模式

| 模式 | H1 规则 |
|------|---------|
| **有 README** | **尽量用原标题**：原 `#` 或 `<h1>` 文案原样保留，仅改为居中 HTML |
| **无 README** | 从**对话上下文 + 仓库内容**总结一个合适的 GitHub 标题 |

有 README 时，**禁止**把「微信公众号爆款AI选题Skill」改成 `bigpeng-hot-gzh`，也禁止把能力型标题改成 `BigPeng GitHub README 格式化 Skill` 这类 repo/作者堆砌名。

---

## 有 README：尽量使用原文

1. 读取原 README 第一个 `# …` 或 `<h1>…</h1>`，记为 `ORIGINAL_H1`
2. 美化后 Hero 的 `<h1 align="center">` **必须与 `ORIGINAL_H1` 一致**（仅排版变化）
3. 原文各 `##`、段落、表格、代码、链接**尽量原样迁入**；只补 Why、改节名、收折叠、润色过渡
4. Tagline 从原首段**提炼一句**，不要替代 H1；Why 节展开，不与 tagline 整段重复

**允许**：居中、徽章、导航、节名规范化（边界→常见问题）  
**禁止**：换 H1、删实质内容、用 repo 名覆盖产品名

---

## 无 README：从上下文与仓库总结标题

按优先级推断 H1，**前一项够用就不往后取**：

| 优先级 | 来源 | 用法 |
|--------|------|------|
| 1 | **用户对话** | 用户说的产品名、一句话定位 |
| 2 | **SKILL.md** | `description` 提炼能力；frontmatter `name` 仅作参考，通常需改写成自然语言 |
| 3 | **package.json / pyproject.toml** | `description` 或 `name` 改写成展示名 |
| 4 | **仓库 About / GitHub description** | 远程元数据 |
| 5 | **repo 名** | **最后兜底**；kebab-case 需改写成可读中文/英文产品名 |

### 无 README 标题怎么写

- **说清做什么**，不贴作者名、不贴 repo slug  
- 中文 skill 常见格式：`{场景}{能力} Skill` 或 `{动词}{对象}`  
- 英文：`{Product} — {one-line capability}` 或 `{Verb} {Object} Skill`

| 反例（生硬） | 正例（自然） |
|--------------|--------------|
| `bigpeng-hot-gzh` | 微信公众号爆款 AI 选题 Skill |
| `BigPeng GitHub README 格式化 Skill` | GitHub README 排版 Skill |
| `roper-gen-image` | AI 图片生成脚本 |

推断后写入 Hero `<h1>`，并在「美化摘要」注明：**H1 来源**（推断依据）。

---

## Tagline（Hero 第二行）

- 有 README：从原首段提炼**一句**，≤ 80 字  
- 无 README：从 SKILL description / 仓库定位总结一句  
- 不与 H1 重复；不写成长段落  

---

## 自检

- [ ] 有 README 时 H1 与原文一致  
- [ ] 无 README 时 H1 不是裸 repo 名  
- [ ] H1 读出来像产品名，不像仓库路径  
- [ ] Tagline 补充 H1，不重复 H1  
