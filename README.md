<h1 align="center"> GitHub README 格式化 Skill</h1>

<p align="center">
  <strong>把 GitHub 仓库 README 整理成 book-to-skill 式首页——居中 Hero、可点击导航、分层结构。</strong>
</p>

<p align="center">
  <a href="./SKILL.md"><img src="https://img.shields.io/badge/skill-bigpeng--github--format-E23D2D?style=for-the-badge" alt="skill"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="MIT"></a>
  <a href="https://github.com/virgiliojr94/book-to-skill"><img src="https://img.shields.io/badge/style-book--to--skill-blueviolet?style=for-the-badge" alt="book-to-skill"></a>
</p>

<p align="center">
  <a href="#-为什么">为什么</a> ·
  <a href="#功能">功能</a> ·
  <a href="#使用方法">用法</a> ·
  <a href="#安装">安装</a> ·
  <a href="#常见问题">FAQ</a> ·
  <a href="#仓库结构">结构</a> ·
  <a href="./SKILL.md">Skill</a>
</p>

---

## 🤔 为什么

GitHub 首页是仓库的「门面」，但不少 README 信息齐全、排版却难扫：标题不居中、导航点不动、长表格堆在首屏、该折叠的内容没有折叠。

本 skill 把任意仓库 README 整理成 [book-to-skill](https://github.com/virgiliojr94/book-to-skill) 式结构：**美化 ≠ 重写**——保留原标题、表格和命令，只补缺失结构、统一版块命名、让 Hero 导航每个链接都能跳转。有 README 时尽量沿用原有版块；没有 README 时，从 `SKILL.md`、目录树等推断并生成经典全套。

---

## 功能

核心工作流分**两步**，不可跳过、不可颠倒：

| 步骤 | 做什么 |
|------|--------|
| **第一步** | 规划版块 + Hero 超链接草案：定稿正文有哪些 `##`，列出导航核对表 |
| **第二步** | 验证锚点 + 润色各节：每个 `#anchor` 可跳转；迁移后的内容通顺连贯 |

**有 README 时**

- 尽量沿用原有 `##`；节名可规范化（边界→常见问题、Getting Started→使用方法）
- **Why 必选**；Usage / Install / FAQ 有内容则保留
- 项目独有节（如公式表）保留原名

**无 README 时**

- 生成经典全套：Why、功能、使用方法、安装、常见问题、仓库结构、License
- 内容从仓库文件推断，**禁止编造**；缺口写进「待你补充」

规则与参考文档见 [SKILL.md](./SKILL.md) 及 `references/` 目录。

---

## 使用方法

对 Agent 说「用 bigpeng-github-format」，并提供仓库 URL、本地路径或 README 内容。

**美化远程仓库**

```text
用 bigpeng-github-format 美化 https://github.com/foo/bar
```

**美化本地 README（保留原标题和章节）**

```text
美化 README，保留原标题和章节，补 Why，导航要能跳转，各节内容要通顺
```

Agent 会按 [SKILL.md](./SKILL.md) 执行两步流程，并在对话末尾输出「美化摘要」与「待你补充」。完整规则、导航设计与内容润色指南在 `references/`。

---

## 安装

### Cursor

```bash
git clone https://github.com/BigPengSays/bigpeng-github-format.git
cd bigpeng-github-format
ln -sfn "$(pwd)" "${HOME}/.cursor/skills/bigpeng-github-format"
```

### Claude Code / Codex 等

把本目录放到对应产品的 skills 路径，能读到 `SKILL.md` 即可。入口是 [SKILL.md](./SKILL.md)。

---

## 常见问题

**会重写我的 README 吗？**  
不会。核心原则是**美化 ≠ 重写**：H1 用原标题，表格、代码块、链接路径尽量保留；只改排版、补缺失节、收折叠。禁止用 repo 名替换产品名。

**为什么必须有 Why 节？**  
Why 是 book-to-skill 式首页的叙事起点，Hero 导航也**必须含「为什么 / Why」**。原文没有时，从首段或简介拆出新建。

**Hero 导航点不动怎么办？**  
每个 `#anchor` 必须对应文中一个真实的 `##` 标题；不能只有 `<details>` 而没有 `##`。skill 要求先定稿正文 `##`，验证锚点后再写 Hero HTML。

**会自动加 Star History 吗？**  
默认**不加**。需要时在对话「待你补充」里会给可粘贴片段；只有用户明确要求才写入 README。

**没有 README 也能用吗？**  
可以。会从 `SKILL.md`、`LICENSE`、`examples/`、`package.json` 等推断内容，生成 Why / 功能 / 用法 / 安装 / FAQ / 仓库结构等经典版块；写不出的信息不编造，列进「待你补充」。

---

## 仓库结构

<details>
<summary>目录树</summary>

```text
bigpeng-github-format/
├── SKILL.md                 # skill 入口与工作流
├── README.md
├── LICENSE
└── references/
    ├── nav-design.md        # Hero 导航设计
    ├── content-polish.md    # 各节润色要点
    ├── preserve-content.md  # 保留原文规则
    ├── no-readme-scaffold.md
    ├── section-catalog.md
    ├── readme-template.md
    ├── intake.md
    ├── qa-checklist.md
    └── followup-template.md
```

</details>

---

## License

[MIT](./LICENSE) · 作者 [BigPeng](https://github.com/BigPengSays)
