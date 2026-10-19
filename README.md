# 地点撒点地图 · PWA 文件包

## 文件
- `index.html` 应用本体（单文件，已内置 d3 / topojson / 地图数据，约 1.7 MB）
- `manifest.webmanifest` 应用清单（名称、图标、独立窗口模式）
- `sw.js` Service Worker，首次打开后离线可用
- `icons/` 192、512、maskable 512、苹果触摸图标

## 部署（任选其一，必须是 HTTPS 或 localhost）
1. **静态托管**：把整个文件夹上传到 GitHub Pages / Cloudflare Pages / Netlify / Vercel / 自己的 Nginx，用 HTTPS 地址打开。
2. **本机测试**：在本文件夹运行 `python3 -m http.server 8080`，浏览器打开 http://localhost:8080 。
   直接双击 `index.html`（file://）仍能用，但不会注册离线缓存，也不能安装。

## 安装
- 电脑 Chrome / Edge：地址栏右侧「安装」图标。
- Android Chrome：菜单 → 安装应用 / 添加到主屏幕。
- iPhone Safari：分享 → 添加到主屏幕。

## 更新
修改 `index.html` 后，把 `sw.js` 里的 `VERSION` 改成新值（如 `v16-1`）再部署，用户下次联网打开即自动更新。

## 说明
- 应用逻辑全部在本地运行，地点坐标识别用内置数据，不上传任何内容。
- 唯一的外部请求是 Google 字体（IBM Plex）；离线或加载失败时自动回退系统字体，不影响使用。
- 导出的 GIF / MP4 在 PWA 窗口中同样通过浏览器下载保存；iOS 上请长按预览保存。
