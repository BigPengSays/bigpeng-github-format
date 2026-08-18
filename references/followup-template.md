# 对话固定输出：待你补充

每次美化完成后，**必须**在对话末尾输出「美化摘要」+「待你补充」（不写入 README.md）。

## 模板

```markdown
## 美化摘要
- 输入模式：（有 README / 无 README）
- 输入来源：（URL / 路径 / 粘贴）
- 第一步 — 保留的原有章节：（有 README 时列出；无 README 写「经典全套新建」）
- 第一步 — 规范化节名：（如 边界→常见问题）
- 第一步 — 新增章节：（仅 beautify 新补的节，无则写「无」）
- 第二步 — emoji 选用：（列出 H1 与各 ## 所选 emoji 及槽位）
- 导航语言：（中文 / English / …）
- 导航项：（列出 Hero 锚点/外链）
- 锚点验证：（全部通过 / 修正项说明）
- 写入路径：（若已写入文件）

## 待你补充

以下可选优化未写入 README，按需处理：

- [ ] **Banner 图**：建议路径 `docs/assets/banner.webp`，补好后可在 Hero 顶栏加入：
  ```html
  <p align="center">
    <img src="docs/assets/banner.webp" alt="（项目名）" width="100%">
  </p>
  ```

- [ ] **Star History**（默认未加）：若需要增长曲线，可在 License 节后插入：
  ```markdown
  ## Star History

  <a href="https://www.star-history.com/?repos={{OWNER}}%2F{{REPO}}&type=date&legend=top-left">
   <picture>
     <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos={{OWNER}}/{{REPO}}&type=date&theme=dark&legend=top-left" />
     <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos={{OWNER}}/{{REPO}}&type=date&legend=top-left" />
     <img alt="Star History Chart" src="https://api.star-history.com/chart?repos={{OWNER}}/{{REPO}}&type=date&legend=top-left" />
   </picture>
  </a>
  ```
  预览页：https://star-history.com/#{{OWNER}}/{{REPO}}

- [ ] **Release 徽章**：仓库已有 release 时可加 shields 版本徽章

- [ ] **多语言 README**：若有 `README.zh-CN.md` 等，可在 Hero 加语言切换行

- [ ] **（其他）**：根据本次美化发现的缺口自定义一行
```

## 填写规则

- `{{OWNER}}/{{REPO}}`：从 git remote 或用户 URL 解析；解析不出则写「请替换为 owner/repo」。
- Star History：**只出现在「待你补充」**，除非用户当场要求。
- Banner：无图时**必提**；已有则删除该项。
- 「第二步 — 润色说明」：至少列出 Why / FAQ 是否润色；无改动写「各节原文已通顺，未大改」。
