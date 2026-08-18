# README 输出模板

**顺序**：第一步定全部 `##` + 导航草案 → 第二步验证锚点并润色各节 → 最后写 Hero 导航。

**H1**：有 README 用原文（无 emoji 则补）；无 README 推断文案 + emoji。各 `##` 从 [header-emoji.md](header-emoji.md) 选 emoji。

```markdown
<h1 align="center">{{H1_EMOJI}} {{H1_TEXT}}</h1>

<p align="center">
  <strong>{{TAGLINE}}</strong>
</p>

<p align="center">{{BADGE_ROW}}</p>

<!-- 第二步验证通过后写入；Why 必选 -->
<p align="center">
  <a href="#{{ANCHOR_WHY}}">{{NAV_WHY}}</a> ·
  <a href="#{{ANCHOR_FEATURES}}">{{NAV_FEATURES}}</a> ·
  <a href="#{{ANCHOR_USAGE}}">{{NAV_USAGE}}</a> ·
  <a href="#{{ANCHOR_INSTALL}}">{{NAV_INSTALL}}</a> ·
  <a href="#{{ANCHOR_FAQ}}">{{NAV_FAQ}}</a>
  <!-- 无对应 ## 的项不要写；examples/ 外链 optional -->
</p>

---

## {{WHY_EMOJI}} {{WHY_TITLE}}

{{WHY_BODY_POLISHED}}

---

## {{FEATURES_EMOJI}} {{FEATURES_TITLE_OR_ORIGINAL}}

{{FEATURES_BODY}}

---

## {{USAGE_EMOJI}} {{USAGE_TITLE}}

{{USAGE_BODY_POLISHED}}

---

## {{INSTALL_EMOJI}} {{INSTALL_TITLE}}

{{INSTALL_BODY}}

---

## {{FAQ_EMOJI}} {{FAQ_TITLE}}

{{FAQ_BODY_AS_QA}}

---

## {{STRUCTURE_EMOJI}} {{STRUCTURE_TITLE}}

<!-- 进导航时必须有本 ##；树可折叠在 details 内 -->
<details>
<summary>目录树</summary>

{{REPO_TREE}}

</details>

---

## License

{{LICENSE}}
```

## 中文 README 示例（bigpeng-hot-gzh）

### 第一步产出

**最终 `##` 顺序**：

```text
## 🤔 为什么
## 爆款标题的 7 种公式
## 使用方法
## 安装
## 常见问题
## 仓库结构
## License
```

**导航草案**：

| 标签 | 对应 ## | 预计 href |
|------|---------|-----------|
| 为什么 | ## 🤔 为什么 | #-为什么 |
| 公式 | ## 爆款标题的 7 种公式 | #爆款标题的-7-种公式 |
| 用法 | ## 使用方法 | #使用方法 |
| 安装 | ## 安装 | #安装 |
| FAQ | ## 常见问题 | #常见问题 |
| 示例 | examples/prompts.md | （文件外链） |

### 第二步

- 验证上表 href 与定稿 `##` 一致  
- 润色 Why / FAQ（边界 → 问答）  
- 通过后写入 Hero HTML  

## 无 README 时的 `##` 顺序（中文）

```text
## 🤔 为什么
## 功能
## 使用方法
## 安装
## 常见问题
## 仓库结构
## License
```

导航：为什么 · 功能 · 用法 · 安装 · FAQ · 结构（+ 示例外链）

详见 [no-readme-scaffold.md](no-readme-scaffold.md)。

## 排版约定

- Hero 居中 HTML；导航语言 = README 主语言。  
- **Star History 默认不输出**。  
- details 不得替代需要进导航的 `##`。
