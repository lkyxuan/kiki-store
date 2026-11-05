# Kiki 宝库

[Kiki](https://github.com/lkyxuan/kiki) 的宝库：**https://lkyxuan.github.io/kiki-store/**

网站就是这个仓库里的 `index.html`，读 `store.json` 列出每样东西。点「在 Kiki 里打开」会拉起 Kiki（`kiki://install?...`），在 Kiki 里看一眼再装上。

现在能上架两类：

| 类型 | 是什么 | 装到哪 |
|---|---|---|
| `theme` 外观 / 装饰 | 主题包：`theme.json` + `theme.css` + 图片、字体。装饰（如 AI 娘立绘）叠在任何外观上，条目里加 `"kind": "decor"`，theme.json 里也写 `"kind": "decor"` | `~/kiki-data/themes/<id>/` |
| `bao` 宝 | 一个宝：`AGENTS.md`（或 `.bao` 文件）+ `skills/` | 先显示它会做什么，确认后装成新宝 |

技能、插件带代码，以后再开放。

## 上架

1. 把你的外观或宝放在一个**公开**的 GitHub 仓库（可以是仓库里的一个文件夹）。
2. Fork 这个仓库，在 `store.json` 的 `items` 里加一条，提 PR。
3. 审核通过合并后，所有 Kiki 刷新宝库就能看到。

```json
{
  "id": "sao",
  "type": "theme",
  "name": "SAO",
  "author": "你的名字",
  "description": "一句话介绍（160 字以内）",
  "repo": "你的账号/你的仓库",
  "path": "仓库里的子文件夹，放在根目录就不写",
  "ref": "40 位 commit SHA",
  "preview": "preview.png"
}
```

- `id`：外观的 `id` 就是装好后的文件夹名，只能用小写字母、数字、连字符，不能叫 `system` / `light` / `dark`。
- `ref`：必须是**完整的 commit SHA**，不能写分支名。Kiki 装的永远是审核过的这一版，作者之后改仓库不会悄悄影响别人。要发新版，提 PR 改 `ref`，装过的人会看到「更新」。
- `preview`：外观的缩略图，约 192×124，路径相对 `path`。

### 外观包的要求

- 只会装文件夹顶层的 `theme.json`、`.css`、`.png`、`.jpg`、`.svg`、`.webp`、`.woff2`，其他文件（脚本、README、子文件夹）一律不装。
- 单个文件不超过 2MB，全部不超过 6MB，最多 40 个文件。
- 写法见 Kiki 文档 `docs/themes.md`。

### 审核看什么

- 外观：不带别人作品的 logo、角色图、原版字体等素材；只借鉴风格。
- 宝：说明里写清楚它负责什么、会联系哪些网站；没有可疑的命令或要密钥的地方。

## 讨论

想法、求助、晒作品，去 [Discussions](../../discussions)。
