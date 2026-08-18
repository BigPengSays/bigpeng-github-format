# 保留原 README 内容

美化是**换排版、补结构**，不是**重写文案、换 H1**。节名可对齐标准槽（Why / Usage / Install / FAQ），**正文与表格必须保留**。

- **第二步**：按本文件迁移原文，写出初版各节（见 [draft-implementation.md](draft-implementation.md)）  
- **第三步**：仅润色通顺与真人化，不覆盖事实（见 [content-polish.md](content-polish.md)、[humanize-content.md](humanize-content.md)）

**无 README** 时不适用「保留原文」，改走 [no-readme-scaffold.md](no-readme-scaffold.md) 生成经典全套。

## 必须保留

| 元素 | 规则 |
|------|------|
| **H1** | 原 `#` 文案，仅改居中；禁止换 repo 名 |
| **原有版块** | 原文有的 `##` 尽量保留；不删公式表、边界、安装等实质内容 |
| **正文** | 原段落、表格、代码块、列表尽量原句迁入 |
| **链接路径** | `references/`、`examples/` 等不改 |
| **项目独有节** | 如「爆款标题的 7 种公式」保留内容与标题 |

## 允许调整（为导航与结构）

| 元素 | 允许 |
|------|------|
| **`##` 节名** | 对齐标准槽；**从 header-emoji 池为每节选 1 个 emoji**（已有则保留） |
| **首段** | Hero tagline + 拆入 **Why** 节（Why 必选） |
| **FAQ 体例** | 边界 bullet → **第三步**改问答体（内容意思保留） |
| **折叠** | 长表/目录树收进 `##` 节内的 `<details>` |
| **节序** | Why 通常放 Hero 后第一节 |
| **过渡句** | **第三步**迁移、合并后为通顺可改引导语 |

## 禁止

- 用 repo 名替换 H1 产品名  
- 删除原文表格、边界说明、安装命令  
- 为凑模板写生硬英文套话  
- 仅 `<details>` 代替应有 `##` 且该节进 Hero 导航  
- 终版 FAQ 仍保留边界 bullet 而不改问答体  

## 处理流程（对应三步）

**第一步**（规划，不写 README）

1. 盘点原文全部 `##`  
2. 映射标准槽（见 [nav-design.md](nav-design.md)）  
3. **补 Why**（无则规划新建）  
4. 保留 / 规范化节名，定稿 `##` 顺序  
5. 填导航草案  

**第二步**（初版）

6. 迁移原文到规划槽位，写 H1 + tagline + 各 `##`  
7. **不写 Hero HTML**  

**第三步**（终版）

8. 逐节连贯润色 + 真人化  
9. 按定稿 `##` 验证锚点  
10. 写 Hero 导航 HTML  

## 标题（H1）

| 模式 | 规则 |
|------|------|
| **有 README** | 原 `#` / `<h1>` **原样保留**，仅改居中；详见 [title-design.md](title-design.md) |
| **无 README** | 从对话 + 仓库内容推断自然语言标题；**禁止**裸 repo slug |

## 标题优先级（无 README）

用户对话 → SKILL.md description → package description → GitHub About → repo 名（最后）

## 自检

读者应能认出同一份 README；Why 节存在且通顺；FAQ 是问答不是边界列表；Hero 每个锚点可跳转。
