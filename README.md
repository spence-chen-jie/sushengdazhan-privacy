# 宿命大战 · 隐私政策（GitHub Pages 站点）

《宿命大战》游戏隐私政策静态站点，供 TapTap 上架时填写「隐私政策链接」使用。

- 游戏：《宿命大战》
- 运营者：听风止汐的工作室
- 更新时间：2026年11月2日

## 页面

| 路径 | 说明 |
|---|---|
| `/` | 隐私政策首页（响应式，带侧边目录） |
| `/privacy-policy.pdf` | PDF 版（10 页） |
| `/sushengdazhan-privacy-policy.docx` | Word 版 |
| `/privacy-policy.html` | 与首页内容相同（兼容旧链接） |

纯静态文件，无构建步骤、无后端、无外部依赖：所有资源内联（CSS/JS/图标），仅正文中的 TapTap 官方文档为外链。

## 本地预览

```bash
python -m http.server 8123
# 打开 http://127.0.0.1:8123/
```

## 更新内容

1. 修改 `index.html` 与 `privacy-policy.html`（两者内容需一致）
2. 替换 `privacy-policy.pdf`、`sushengdazhan-privacy-policy.docx`
3. 提交推送：

```bash
git add -A
git commit -m "docs: 更新隐私政策"
git push
```

GitHub Actions 无构建过程，推送后 1 分钟左右自动生效。

## 许可

内容为运营者自有法律文本，仅用于本游戏。
