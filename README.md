# MindShop AI — 静态演示站

给评委看的单页站 + 项目 deck。纯静态，无构建步骤、无外部依赖（不引入 CDN / webfont）。

## 文件

| 文件 | 说明 |
| --- | --- |
| `index.html` | 主页面（`#demo` 嵌视频，`#contact` 联系方式） |
| `deck.html` | 8 页项目 deck |
| `video_final-web.mp4` | 演示视频，4:54，英/俄字幕已烧进画面 |
| `poster.jpg` | 视频封面图 |
| `video_final.srt` | 字幕文本（备用，页面不引用） |
| `.nojekyll` | 关闭 GitHub Pages 的 Jekyll 处理，原样发布静态文件 |

## 语言切换（EN / RU）

两个页面右上角各有 `RU | EN` 切换控件（deck 上是固定悬浮，且在打印/导出 PDF 时自动隐藏）。

- **默认英语**：首次打开一律英语，不做浏览器语言识别。
- **`?lang=ru` / `?lang=en`**：URL 参数优先级最高。发给俄语评委就直接用
  `https://waterymonkey3.github.io/mindshop-ai/?lang=ru`。
- **记住选择**：手动切换后写入 `localStorage["mindshop-lang"]`，下次打开保持；
  页面之间会传递（index 的 deck 链接、deck 的 live demo 链接都会带上 `?lang=ru`）。
- **改文案**：在 HTML 里给元素加 `data-i18n="键名"`，再到该页 `<script>` 的 `RU` 字典里加同名键的俄语文本。
  英文原文不需单独维护：脚本首次加载时从 HTML 快照，所以切回英语与改动前逐字一致。
- 不翻译的内容：品牌 `MindShop AI`、`@WatertMonkey`、邮箱、URL、编号与时间戳、
  `index.html` 里的 `<code>` 配置引文，以及视频里已烧录的字幕。
- `deck.html` 第 03 张的聊天窗口保留英文原话，下方用细线隔开加一行灰字俄语译文。

## 本地预览

```powershell
python -m http.server 8000
# 打开 http://localhost:8000/
```

不要直接双击 `index.html` 打开：`file://` 下视频只能靠 Range 请求播，部分浏览器会无法拖动进度条。

## 线上地址

https://waterymonkey3.github.io/mindshop-ai/

## 发布 / 更新

推送到 `main` 分支即可，GitHub Pages 会自动重新发布（约 1 分钟）：

```powershell
git add -A
git commit -m "update site"
git push
```

## 注意

- 仓库必须保持 **Public**，免费账号不提供 Private 仓库的 Pages 服务。
- 所有资源引用都是相对路径，因此可以直接放在 `user.github.io/repo/` 子路径下。
- 视频 35 MiB，未超过单文件 100 MiB 上限；GitHub Pages 免费额度为 100 GB/月流量。
