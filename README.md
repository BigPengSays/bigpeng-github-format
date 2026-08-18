<h1 align="center">📝 GitHub README 排版 Skill</h1>

<p align="center">
  <strong>一键生成和排版 Github README——基于专业的 ReadMe 模板制作的 Skill</strong>
</p>

<p align="center">
  <a href="./SKILL.md"><img src="https://img.shields.io/badge/skill-bigpeng--github--format-E23D2D?style=for-the-badge" alt="skill"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="MIT"></a>
  <img src="https://img.shields.io/badge/for-GitHub%20README-24292f?style=for-the-badge" alt="GitHub README">
</p>

<p align="center">
  <a href="#-为什么">为什么</a> ·
  <a href="#-功能">功能</a> ·
  <a href="#-使用方法">用法</a> ·
  <a href="#-安装">安装</a> ·
  <a href="#-常见问题">FAQ</a> ·
  <a href="#-仓库结构">结构</a> ·
  <a href="./SKILL.md">Skill</a>
</p>

---

## 💡 为什么

仓库 README 往往信息齐全，却不好扫：标题贴边、导航点不动、长表格占满首屏、该折叠的没折叠。

本 skill 专做 GitHub 首页排版：**美化 ≠ 重写**。提供了原始 README，就尽量保留你的标题和各版块正文，只补 Why、规范节名、收进折叠；没有 README，就从对话和仓库内容总结合适标题，并生成经典全套版块。

---

## ⚡ 功能

排版产出：**居中 Hero**（标题 + 一句话 + 徽章 + 锚点导航）+ **分层正文**（Why / 功能 / 用法 / 安装 / FAQ 等）。H1 与各节标题会加贴切 emoji，每槽位从备选池轮换，避免千篇一律。

| 阶段 | 做什么 |
|------|--------|
| **判断模式** | 有 README → 尽量用原文；无 README → 推断标题 + 生成经典版块 |
| **第一步** | 规划版块 + Hero 导航草案；为 H1 / 各 `##` 选 emoji |
| **第二步** | 验证每个链接可跳转；润色各节；通过后写 Hero HTML |
| **输出** | `README.md` + 对话「美化摘要」「待你补充」 |

**有 README**：H1 文案保留（无 emoji 则补）；原有 `##` 尽量沿用；Why 必选。

**无 README**：生成经典全套；从 SKILL / LICENSE / examples / 目录树推断，**禁止编造**。

详细规则见 [SKILL.md](./SKILL.md)、[references/implementation-logic.md](references/implementation-logic.md)、[references/title-design.md](references/title-design.md)、[references/header-emoji.md](references/header-emoji.md)。

---

## 📖 使用方法

对 Agent 说「用 bigpeng-github-format」，并提供仓库 URL、本地路径或 README 内容。

**远程仓库**

```text
用 bigpeng-github-format 美化 https://github.com/foo/bar
```

**本地 README（保留原标题和章节）**

```text
美化 README，保留原标题和章节，补 Why，导航要能跳转，各节内容要通顺
```

Agent 按两步流程执行，对话末尾输出「美化摘要」与「待你补充」。

---

## 🧲 安装

### Cursor

```bash
git clone https://github.com/BigPengSays/bigpeng-github-format.git
cd bigpeng-github-format
ln -sfn "$(pwd)" "${HOME}/.cursor/skills/bigpeng-github-format"
```

### Claude Code / Codex 等

把本目录放到对应产品的 skills 路径，能读到 `SKILL.md` 即可。

---

## ❓ 常见问题

**会重写我的 README 吗？**  
不会。有原始 README 时，H1 和各版块正文尽量原样保留；只改排版、补缺失节、收折叠。


---

## 🗂️ 仓库结构

<details>
<summary>目录树</summary>

```text
bigpeng-github-format/
├── SKILL.md
├── README.md
├── LICENSE
└── references/
    ├── implementation-logic.md
    ├── title-design.md
    ├── header-emoji.md        # 各节 emoji 备选池
    ├── nav-design.md
    ├── content-polish.md
    ├── preserve-content.md
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
