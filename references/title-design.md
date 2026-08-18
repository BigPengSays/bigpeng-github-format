# 标题（H1）设计

Hero 的 `<h1>` 是读者第一眼看到的产品名。**写人话、写能力**，不要堆 repo slug、作者名、英文术语。美化后须带 **1 个 leading emoji**（见 [header-emoji.md](header-emoji.md)）。

## 两种模式

| 模式 | H1 规则 |
|------|---------|
| **有 README** | **尽量用原标题**；原文无 emoji 则从领域池补 1 个 |
| **无 README** | 从**对话 + 仓库**总结标题，并从领域池加 emoji |

有 README 时，**禁止**把「微信公众号爆款AI选题Skill」改成 `bigpeng-hot-gzh`，也禁止把能力型标题改成 repo/作者堆砌名。

---

## 有 README：尽量使用原文

1. 读取原 README 第一个 `# …` 或 `<h1>…</h1>`，记为 `ORIGINAL_H1`
2. 美化后 Hero `<h1 align="center">` **文案与 `ORIGINAL_H1` 一致**（仅排版变化）
3. **`ORIGINAL_H1` 无 leading emoji** → 按项目领域从 [header-emoji.md](header-emoji.md) H1 池选 1 个， prepend 到标题前
4. **已有 emoji** → 保留，不替换
5. 原文各 `##`、段落、表格、代码**尽量原样迁入**；补 Why、改节名、收折叠、润色过渡
6. 各 `##` 无 emoji 时，从槽位备选池各选 1 个（同 README 不重复）

**允许**：居中、徽章、导航、节名规范化、补 emoji  
**禁止**：换 H1 文案、删实质内容、用 repo 名覆盖产品名

---

## 无 README：从上下文与仓库总结标题

按优先级推断 H1 文案，**前一项够用就不往后取**：

| 优先级 | 来源 | 用法 |
|--------|------|------|
| 1 | **用户对话** | 用户说的产品名、一句话定位 |
| 2 | **SKILL.md** | `description` 提炼能力 |
| 3 | **package.json / pyproject.toml** | `description` 或 `name` 改写成展示名 |
| 4 | **仓库 About** | 远程元数据 |
| 5 | **repo 名** | **最后兜底** |

推断文案后，从 [header-emoji.md](header-emoji.md) **H1 领域池**选 1 个 emoji 写在最前。

| 反例（生硬） | 正例（自然） |
|--------------|--------------|
| `bigpeng-hot-gzh` | 📱 微信公众号爆款 AI 选题 Skill |
| `BigPeng GitHub README 格式化 Skill` | 📝 GitHub README 排版 Skill |

「美化摘要」注明 **H1 来源**与所选 emoji。

---

## Tagline（Hero 第二行）

- 有 README：从原首段提炼**一句**，≤ 80 字  
- 无 README：从 SKILL description / 仓库定位总结一句  
- **不加 emoji**（emoji 只在 H1 / `##` 标题）  
- 不与 H1 重复  

---

## 自检

- [ ] 有 README 时 H1 文案与原文一致（emoji 可补）  
- [ ] 无 README 时 H1 不是裸 repo 名  
- [ ] H1 有 1 个 leading emoji  
- [ ] 各 `##` 有 emoji 且不重复（License 除外）  
- [ ] Tagline 补充 H1，不重复 H1  
