# 一键交互指令手册（GitHub Pages 部署包）

本仓库用于托管 **Neurosurgicalrc** 的交互式指令手册（v2.2）。部署目标：`https://Neurosurgicalrc.github.io`。

> 本站为纯静态前端（单页 HTML），数据仅在浏览器本地处理。

## 快速部署（两种方式）

### 方式 A：网页上传（最简单）
1. 打开仓库：<https://github.com/Neurosurgicalrc/Neurosurgicalrc.github.io>
2. 点击 **Add file → Upload files**，将此压缩包解压后的全部文件（`index.html`、`404.html`、`.nojekyll`、`favicon.svg` 等）拖拽上传到仓库根目录（`main` 分支）。
3. 上传完成后，约 10–60 秒内即可通过 `https://Neurosurgicalrc.github.io` 访问。

### 方式 B：命令行（Git）
```bash
git clone https://github.com/Neurosurgicalrc/Neurosurgicalrc.github.io.git
cd Neurosurgicalrc.github.io
# 将本包内文件解压覆盖到仓库根目录
git add -A
git commit -m "deploy: interactive template handbook v2.2"
git push origin main
```
用户页（User/Organization Pages）使用 `main` 分支根目录作为发布源，无需额外设置或 Actions。

## 可选配置：云盘文件选择器（Google Drive / OneDrive）

**Google Drive Picker**
- 创建/选择 GCP 项目，启用 **Google Picker API** 与 **Google Drive API**。
- 创建 **OAuth 2.0 客户端（类型：Web 应用）** 与 **API Key**。
- **授权 JavaScript 来源**与**重定向 URI**请添加：
  - `https://Neurosurgicalrc.github.io`
- 建议将 **API Key** 限制为 *HTTP 引荐来源（网站）*：`neurosurgicalrc.github.io/*`
- 在 `index.html` 中搜索 `GOOGLE_PICKER_CLIENT_ID` 与 `GOOGLE_API_KEY` 占位符（若存在），替换为你自己的 **Client ID** 和 **API Key**。如无占位符，请在页面顶部的配置块 `window.PICKER_CONFIG` 内填写。

**OneDrive / Microsoft 365 Picker**
- 在 Azure 门户 **App registrations** 新建应用，获取 **应用（客户端）ID**（即 `clientId`）。
- *Redirect URI（Web）* 添加：`https://Neurosurgicalrc.github.io`
- 在 `index.html` 中搜索 `ONEDRIVE_CLIENT_ID`（或 `oneDriveClientId`）并替换为你的应用 ID，或在 `window.PICKER_CONFIG` 中填写。

> 前端集成的 Picker 所需的 **Client ID / API Key** 在浏览器端可见，属正常设计。请通过**域名限制**、**OAuth 同意屏幕**等方式约束使用范围。

## 书签「一键粘贴 & 开启新对话」
- 页面右上角提供书签按钮（或“安装说明”链接）。若浏览器不显示拖拽面板，可在页面“帮助”中复制书签 JavaScript 手动创建。
- 机制：先调用 Clipboard API 复制提示词，再 `window.open()` 打开新的 ChatGPT 对话页。若浏览器阻止弹窗，请在地址栏允许弹窗。

## 本地开发
直接双击 `index.html` 或用任意静态服务器打开即可。所有功能在浏览器本地运行。

---
最后更新：2025-08-24 08:26 UTC
