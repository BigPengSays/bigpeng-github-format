# 实现逻辑

本 skill 的完整决策流程。Agent 按序执行，不可跳步。

---

## 0. 判断输入模式

```
用户提供 README？
├── 有实质内容（## 节、段落、表格、安装命令等）
│   └── 模式 A：有 README → 尽量使用原文
└── 无 / 空 / 仅一行标题
    └── 模式 B：无 README → 生成经典全套 + 推断标题
```

---

## 1. 信息采集

| 模式 | 采集什么 |
|------|----------|
| **A 有 README** | 原 H1、全部 `##`、首段、安装、边界/FAQ 素材、链接路径 |
| **B 无 README** | 扫仓库：`SKILL.md`、`LICENSE`、`examples/`、`package.json`、目录树；读用户对话上下文 |

详见 [intake.md](intake.md)。

---

## 2. 确定 H1、emoji 与 Tagline

| 模式 | H1 | emoji | Tagline |
|------|-----|-------|---------|
| **A 有 README** | 原 `#` / `<h1>` 文案保留 | 无 leading emoji 则从 [header-emoji.md](header-emoji.md) 领域池补 | 原首段提炼一句 |
| **B 无 README** | 对话 → SKILL → package → About → repo 名 | 领域池选 1 个 | 从 description 总结一句 |

各 `##` 从槽位备选池各选 1 个 emoji（已有则保留；同 README 不重复）。见 [title-design.md](title-design.md)。

**铁律**：有 README 时不换标题；无 README 时不使用裸 repo slug 当 H1。

---

## 3. 第一步：规划版块 + Hero 导航草案

| 模式 | 版块策略 |
|------|----------|
| **A 有 README** | 尽量沿用原有 `##`；节名可规范化（Why / Usage / Install / FAQ）；**Why 必选**（缺则从首段拆） |
| **B 无 README** | 经典全套：Why、功能、使用方法、安装、常见问题、仓库结构、License |

产出：

1. 定稿 `##` 顺序  
2. 导航草案表 `{标签 → ## 标题 → 预计 href}`  

详见 [nav-design.md](nav-design.md)、[section-catalog.md](section-catalog.md)、[no-readme-scaffold.md](no-readme-scaffold.md)。

---

## 4. 第二步：验证锚点 + 润色内容

1. **锚点**：按定稿 `##` 重算 href；每个导航项必须有对应 `##`（外链除外）  
2. **润色**：迁移/合并后的节要通顺；FAQ 改问答；Why 独立可读  
3. **写 Hero**：验证通过后再输出 HTML 导航  

详见 [content-polish.md](content-polish.md)。

---

## 5. 输出 README + 对话摘要

1. 完整 `README.md`（居中 Hero + 正文 `##`）
2. 对话末尾固定输出「美化摘要」+「待你补充」（[followup-template.md](followup-template.md)）  
3. Star History **默认不加**

---

## 决策总览

```text
输入
  → 有 README？
       是 → H1/正文尽量用原文 → 映射版块 → 补 Why
       否 → 推断 H1 → 生成经典全套
  → 第一步：定 ## + 导航草案
  → 第二步：验证锚点 + 润色
  → 写 Hero + README
  → 美化摘要 + 待你补充
```
