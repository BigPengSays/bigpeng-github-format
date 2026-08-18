# README 版块目录

原则：**分层排版**；**Why 必选**；**有 README → 尽量沿用原文（含 H1）**；**无 README → 推断标题 + 生成经典全套**。

---

## 工作流：两步

```
第一步：规划版块 + 导航草案
  → 盘点原文 ##
  → 映射标准槽（保留原有节）
  → 补 Why（必选）
  → 定稿 ## 顺序 + 导航草案表

第二步：验证锚点 + 润色内容
  → 重算 href，验证每个锚点
  → 逐节润色（content-polish.md）
  → 写 Hero HTML + 完整 README
```

---

## 一、必写版块

| 顺序 | 版块 | 规则 |
|------|------|------|
| 1 | 居中 **H1** | **有 README**：原 `#` 原样保留。**无 README**：见 [title-design.md](title-design.md) |
| 2 | **Tagline** | 原首段提炼，Hero 居中 |
| 3 | **徽章行** | 至少 License；升级 `for-the-badge` |
| 4 | **Hero 导航** | 第二步验证通过后写入；**Why 必进导航** |
| 5 | **Why** | **必选**；原文无则从简介/首段拆出 |
| 6 | **Features** | 功能/公式/特性；可保留原节名 |
| 7 | **Usage** | 使用方法 / Usage |
| 8 | **Install** | 安装 / Install |
| 9 | **License** | 从 LICENSE 文件 |

强烈建议：**FAQ**（原「边界」「限制」等映射到此槽，**改问答体**）。

---

## 二、标准槽 ↔ 原文映射

见 [nav-design.md](nav-design.md)。要点：

- **尽量沿用原有版块**；节名可规范化，**内容保留**  
- **Why 缺失必补**，不得只靠 Hero tagline 代替  
- **项目独有节保留**（如「爆款标题的 7 种公式」）  
- **FAQ**：边界 → 常见问题；bullet → 问答  

---

## 三、可选版块

| 版块 | 何时加 |
|------|--------|
| Banner | 有素材 |
| Examples | 有 `examples/`；导航链文件外链 |
| 仓库结构 | 原文有；**进导航则必须 `## 仓库结构`** |
| Star History | 仅用户明确要求 |
| `<details>` | 折叠**节内**长内容，不替代 `##` |

---

## 四、Hero 导航与正文一致性

**第一步**定 `##` + 导航草案 → **第二步**验证 href → **最后**写 Hero。

每个导航锚点对应一个 `##`（外链文件除外）。详见 nav-design 核对表。

---

## 五、决策树

```
有 README（且含实质 ## 节）？
  → 是：盘点全部 ##，尽量保留；缺的补（Why 必选）
  → 否：生成经典全套（见 no-readme-scaffold.md）
         Why + Features + Usage + Install + FAQ + 仓库结构 + License

定稿 ## 列表 + 填导航草案（第一步产出）

重算 href，验证锚点（第二步）
  → 逐节润色 content-polish
  → 写 Hero + README
```

## 六、无 README 经典全套（速查）

| ## 节 | 必生成 |
|-------|--------|
| 🤔 为什么 | ✓ |
| 功能 / Features | ✓ |
| 使用方法 / Usage | ✓ |
| 安装 / Install | ✓ |
| 常见问题 / FAQ | ✓（至少 3 条问答） |
| 仓库结构 | ✓ |
| License | ✓ |
| Examples 导航外链 | 有 `examples/` 时加 |

详见 [no-readme-scaffold.md](no-readme-scaffold.md)。
