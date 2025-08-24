# 华西神外 · 梁锐超课题组 — 一键交互指令手册 v2.2（移动端适配）

- 本包基于您提供的 v2.2 `index.html`，仅增加**移动端抽屉侧栏、栅格自适配、iOS/Android 安全区**以及 **PWA(离线/添加到主屏幕)** 支持。
- 不改动原有字段/卡片/逻辑；在桌面版外观保持一致。

## 部署（GitHub Pages 根仓库）
1. 将本压缩包**全部文件**解压到仓库根目录（如 `Neurosurgicalrc.github.io/`），覆盖旧版本。
2. `git add . && git commit -m "deploy v2.2 mobile" && git push`。
3. 打开 `https://Neurosurgicalrc.github.io/`；若显示旧界面，硬刷新（Win: Ctrl+F5 / macOS: ⌘⇧R），或清除浏览器缓存、等待 CDN 生效。

## 移动端使用
- 顶部右侧新增「菜单」按钮，小屏幕点击后左侧栏以抽屉方式展开；点击遮罩或 `Esc` 关闭。
- 小屏幕下表单区与网格自动单列排布，触控目标≥44px。
- 已注册 `service worker` 与 `manifest`，可「添加到主屏幕」并离线访问（静态资源层面）。

> 如需变更主题色或图标，请替换 `/assets` 下 PNG；如需关闭 PWA，可删除 `manifest.webmanifest` 与 `sw.js`。