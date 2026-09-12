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
