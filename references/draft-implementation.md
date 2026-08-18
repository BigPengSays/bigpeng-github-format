# 初版版块实现

第二步：**按第一步定稿的 `##` 顺序，写出初版 README 正文**。结构到位、信息完整即可；通顺与真人化留给第三步。

---

## 第二步目标

| 要做 | 不做 |
|------|------|
| H1 + tagline + badges（可选）+ 全部 `##` 正文 | Hero 导航 HTML |
| 分配 H1 / 各 `##` emoji | 逐节深度润色 |
| 迁移或生成各节内容 | FAQ 必须已是完美问答（可先 bullet） |
| 补 Why（必选） | 锚点最终验证（第三步做） |

---

## 初稿结构

```text
# {emoji} H1（居中 HTML，第二步可先写 markdown H1）

<p align="center"><strong>Tagline 一句</strong></p>

（可选）徽章行

---

## {emoji} 为什么
…

## {emoji} …
…

## License
…
```

**禁止**在此步插入 Hero 导航 `<p align="center">` 锚点链接块。可在文件顶加 HTML 注释：`<!-- Hero 导航：第三步写入 -->`。

---

## 模式 A：有 README

规则详见 [preserve-content.md](preserve-content.md)。

1. **H1**：原 `#` 文案保留，仅改居中；无 leading emoji 则从 [header-emoji.md](header-emoji.md) 补 1 个  
2. **Tagline**：原首段提炼一句（可粗糙，第三步 refine）  
3. **各 `##`**：按第一步映射，把原文段落/表格/代码迁入对应槽位  
4. **Why**：原文无从首段/简介拆出则新建（可先写要点 bullet）  
5. **FAQ**：边界 bullet 可先原样迁入或保留列表，**第三步**改问答体  
6. **项目独有节**：保留内容与标题，只规范化 emoji  

### 允许（初版）

- 过渡句生硬、节首无引导  
- tagline 与 Why 有部分重复  
- FAQ 仍是 bullet 列表  

### 禁止

- 改 H1 产品名、删表格/命令/链接  
- 编造功能或数据  
- 写 Hero HTML  

---

## 模式 B：无 README

规则详见 [no-readme-scaffold.md](no-readme-scaffold.md)。

1. **H1**：推断自然语言标题 + emoji（[title-design.md](title-design.md)）  
2. **Tagline**：从 SKILL description / package description 提炼  
3. **经典全套 `##`**：Why、Features、Usage、Install、FAQ、Structure（有树则写）、License  
4. **内容来源**：仅仓库文件 + 第一步仓库画像；缺口用 honest 占位（「见 SKILL.md」「待补充」）  
5. **FAQ**：至少 3 条；可先写粗问答，第三步真人化  

---

## 共用规则

| 项 | 规则 |
|----|------|
| emoji | H1 + 各 `##` 各 1 个；从 [header-emoji.md](header-emoji.md) 槽位池选；同 README 不重复 |
| License | 从 LICENSE 文件；无文件则节内写「待补充」，详情进对话 GAPS |
| Badges | 可选；至少 License badge |
| Structure | 长目录树收进 `<details>`，但节标题必须是 `## 仓库结构` |
| Examples | 有 `examples/` 时在 Usage 提一句；导航外链第三步定 |

---

## 第二步产出

写入 `README.md`（或对话中展示全文），并自检：

- [ ] 第一步规划的每个 `##` 都已存在  
- [ ] Why 节有实质内容（非空壳）  
- [ ] H1 / 各 `##` 已有 emoji  
- [ ] **无** Hero 导航 HTML 块  
- [ ] 表格、代码块、链接未丢  

完成后进入第三步：[content-polish.md](content-polish.md) + [humanize-content.md](humanize-content.md) + 锚点验证 + Hero。
