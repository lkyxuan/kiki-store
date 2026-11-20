# 主题包：指挥塔、眼睛、贴纸

这三套原来是 Kiki 内置的外观，11/20 搬出主仓库（主仓库只留角色版 / 素版的浅色、深色），放在这里当人才库的主题包。

- 每个文件夹：`theme.json`（名字、基于浅色还是深色）、`theme.css`（样式，全挂在 `:root[data-theme="<id>"]` 下）、`preview.png`（设置里的缩略图）。
- 只能放样式和图片。原来靠 App 代码做的几件事不跟过来：Dock 图标换 logo 和灯、贴纸外观里每位成员是一样实物的头像。
- 贴纸带的 `sora-latin.woff2` 是 Sora 字体（SIL Open Font License 1.1），只截了拉丁字符。
- 改完提交后，把 `store.json` 里对应条目的 `ref` 换成新的提交号，装了的 Kiki 会自动换新版。
