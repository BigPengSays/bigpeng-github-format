# README 版块目录

原则：**分层排版**；**Why 必选**；**有 README → 尽量沿用原文（含 H1）**；**无 README → 推断标题 + 生成经典全套**。

---

## 工作流：三步

```
第一步：分析仓库 + 规划版块
  → 仓库画像（repo-analysis.md）
  → 盘点 / 规划 ##
  → 映射标准槽（保留原有节）
  → 补 Why（必选）
  → 定稿 ## 顺序 + 导航草案表
  （不写 README）

第二步：实现初版版块
  → H1 + tagline + emoji + 全部 ## 正文
  → 无 Hero HTML（draft-implementation.md）

第三步：润色 + 真人化 + Hero
  → 连贯润色（content-polish.md）
  → 真人化（humanize-content.md）
  → 验证 href → 写 Hero HTML + 终版 README
```

---

## 一、必写版块

| 顺序 | 版块 | 规则 |
|------|------|------|
| 1 | 居中 **H1** | **有 README**：原 `#` 原样保留。**无 README**：见 [title-design.md](title-design.md) |
| 2 | **Tagline** | 原首段提炼，Hero 居中 |
| 3 | **徽章行** | 至少 License；升级 `for-the-badge` |
| 4 | **Hero 导航** | **第三步**验证通过后写入；**Why 必进导航** |
| 5 | **Why** | **必选**；原文无则从简介/首段拆出 |
| 6 | **Features** | 功能/公式/特性；可保留原节名 |
| 7 | **Usage** | 使用方法 / Usage |
| 8 | **Install** | 安装 / Install |
| 9 | **License** | 从 LICENSE 文件 |

强烈建议：**FAQ**（原「边界」「限制」等映射到此槽，**第三步改问答体**）。

---

## 二、标准槽 ↔ 原文映射

见 [nav-design.md](nav-design.md)。要点：

- **尽量沿用原有版块**；节名可规范化，**内容保留**  
- **Why 缺失必补**，不得只靠 Hero tagline 代替  
- **项目独有节保留**（如「爆款标题的 7 种公式」）  
- **FAQ**：边界 → 常见问题；bullet → 问答（第三步完成）  

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

**第一步**定 `##` + 导航草案 → **第二步**写初版正文 → **第三步**验证 href 后写 Hero。

每个导航锚点对应一个 `##`（外链文件除外）。详见 nav-design 核对表。

---

## 五、决策树

```
有 README（且含实质 ## 节）？
  → 是：第一步盘点全部 ##，尽量保留；缺的补（Why 必选）
  → 否：第一步规划经典全套（见 no-readme-scaffold.md）
         Why + Features + Usage + Install + FAQ + 仓库结构 + License

第一步：仓库分析 + 定 ## + 导航草案
第二步：初版 README（无 Hero）
第三步：润色 + 真人化 + Hero
```

---

## 六、与仓库类型的关系

第一步 [repo-analysis.md](repo-analysis.md) 的分析结果可能影响版块取舍（如纯文档仓、无 Install 步骤等），但 **Why 始终必选**。
