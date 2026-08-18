# Hero 导航设计

导航属于**第一步（规划）**的产出、**第二步（验证）**的硬检查。**禁止**先写 Hero HTML 再凑正文 `##`。

## 两步中的位置

| 步骤 | 导航相关工作 |
|------|----------------|
| **第一步** | 定最终 `##` 列表；填导航**草案**（标签 → ## 标题 → 预计 href） |
| **第二步** | 按定稿 `##` **重算 href**；逐条验证可跳转；通过后写 Hero HTML |

## 失效原因（必避）

| 错误做法 | 后果 |
|----------|------|
| 导航指向 `<details>`，但没有对应 `##` 标题 | 点击无跳转（如「结构」→ 仅 details 包目录树） |
| href 凭猜测 slug，未对照最终 `##` 文案 | 中文/emoji 标题 slug 易错 |
| 导航项多于正文实际 `##` 节 | dead link |
| 把整节收进 details 且 summary 替代 `##` | summary 不产生 GitHub 锚点 |
| 第一步草案未更新，直接沿用预计 href | emoji/改节名后 slug 对不上 |

**铁律：Hero 每个 `#anchor` 必须对应文中一个真实的 `## 标题`；外链（`examples/foo.md`）除外。**

## 标准版块（Canonical Slots）

| 槽位 | 英文节名 | 中文节名 | 导航标签（中） | 导航标签（英） | 是否必选 |
|------|----------|----------|----------------|----------------|----------|
| **Why** | `Why` | `为什么` | 为什么 | Why | **必选** |
| Features | `Features` | `功能` / 保留原名 | 功能 / 短名 | Features | 有则进 |
| Usage | `Usage` | `使用方法` | 用法 | Usage | 强烈建议 |
| Install | `Install` | `安装` | 安装 | Install | 强烈建议 |
| FAQ | `FAQ` | `常见问题` | FAQ | FAQ | 有则进 |
| Examples | — | — | 示例 | Examples | 有 `examples/` 时可进（文件外链） |
| Structure | `Repository structure` | `仓库结构` | 结构 | Structure | 可选；**进导航则必须有 `##`** |

**Why 必选**：有 README 时原文无独立 Why 节则从首段拆出；**无 README 时与其他经典节一并新建**。Hero tagline 可保留精简版，Why 节展开（见 [content-polish.md](content-polish.md)）。

## 无 README：经典全套进导航

无 README 时，除 License 外，以下节**全部生成**且**默认进 Hero 导航**：

Why · Features/功能 · Usage/用法 · Install/安装 · FAQ · Structure/结构（有目录树时）

详见 [no-readme-scaffold.md](no-readme-scaffold.md)。

## 原文 → 标准槽映射（有 README）

**有 README 时尽量沿用原有版块**；节名可对齐通用槽，**正文保留**：

| 常见原文 `##` | 映射到 | 说明 |
|---------------|--------|------|
| 简介、About、背景 | **Why** | 内容迁入 Why，原节可删避免重复 |
| 功能、特性、公式、能产出什么 | **Features** | 项目特有标题可保留 |
| 使用方法、Getting Started、快速开始 | **Usage** | 跟 README 语言选「使用方法」或 Usage |
| 安装、Install | **Install** | 同上 |
| 边界、限制、Troubleshooting | **FAQ** | 节名改「常见问题」/ `FAQ`；**内容改问答体** |
| 仓库结构、Project structure | **Structure** | 见下方折叠规则 |
| License | License | 一般**不进** Hero 导航 |

**保留原文重要版块**：项目独有节**不强行改成 Features**，导航用短标签链到原 `##` 即可。

## 第一步：版块与导航规划流程

### 1. 列出原文 `##` 清单

### 2. 映射 + 补缺

- 对照上表映射到标准槽  
- **无 Why → 必须新建**  
- 缺 Usage / Install → 从原文其他位置合并或新建  
- 原文有的节**不删**（除非与 Why 完全重复且已迁入 Why）

### 3. 确定最终 `##` 标题列表（写入 README 的顺序）

示例（bigpeng-hot-gzh）：

```text
1. ## 🤔 为什么
2. ## 爆款标题的 7 种公式
3. ## 使用方法
4. ## 安装
5. ## 常见问题        ← 原「边界」，节名规范化
6. ## 仓库结构        ← 必须有 ##，树可放 details 内
7. ## License
```

### 4. 填导航草案（第一步产出）

```text
| 导航标签 | 对应 ## 标题 | 预计 href |
|----------|--------------|-----------|
| 为什么   | ## 🤔 为什么 | #-为什么 |
| 公式     | ## 爆款标题的 7 种公式 | #爆款标题的-7-种公式 |
| 用法     | ## 使用方法 | #使用方法 |
| 安装     | ## 安装 | #安装 |
| FAQ      | ## 常见问题 | #常见问题 |
| 示例     | examples/prompts.md | （文件外链） |
```

## 第二步：锚点验证 + 写 Hero

### 1. 重算 href（GitHub slug 近似规则）

- 去掉 emoji 后 slugify，或 emoji 变成 leading `-`  
- 空格 → `-`；中文通常保留  
- 示例：`## 🤔 为什么` → `#-为什么` 或 `#为什么`  
- **以定稿 `##` 文案为准**；改节名后必须重算  

### 2. 验证核对表

```text
| 导航标签 | href | 对应 ## 标题 | 存在？ |
|----------|------|--------------|--------|
| 为什么   | #-为什么 | ## 🤔 为什么 | ✓ |
| …        | …    | …            | ✓ / ✗ |
```

任一「存在？」为 ✗ → 删导航项或补 `##`，**不得发布失效链接**。

### 3. 组装 Hero 导航（5–7 项）

- 语言跟 README 主语言  
- 顺序跟正文阅读顺序  
- License、Star History **不进**导航  

```html
<p align="center">
  <a href="#-为什么">为什么</a> ·
  <a href="#爆款标题的-7-种公式">公式</a> ·
  <a href="#使用方法">用法</a> ·
  <a href="#安装">安装</a> ·
  <a href="#常见问题">FAQ</a> ·
  <a href="examples/prompts.md">示例</a>
</p>
```

「结构」若要进导航 → 正文必须有 `## 仓库结构`，不能把整节只放在 details 里。

## `<details>` 与导航的关系

```
✅ 正确：
## 仓库结构
<details><summary>目录树</summary>...</details>

❌ 错误（导航写了「结构」）：
<details><summary>📁 仓库结构</summary>...</details>
```

长表格、依赖列表：**进导航的节必须有 `##`**，details 只折叠节内子块。

## 语言：中文 README 用什么标签？

| 策略 | 适用 |
|------|------|
| 导航全中文 | 中文 README（推荐） |
| 导航全英文 | 英文 README |

**不要**中文正文配纯英文导航（Why · Features · Usage），除非用户明确要求双语 README。
