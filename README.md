# AI 视频提示词工坊 — PWA 部署指南

## 文件清单

```
pwa/
├── index.html      ← 主程序
├── manifest.json   ← PWA 配置
├── sw.js           ← Service Worker（离线支持）
├── icon-192.png    ← 应用图标 192x192
├── icon-512.png    ← 应用图标 512x512
└── README.md       ← 本文件
```

## 部署到 GitHub Pages（推荐，完全免费）

### 步骤 1：创建 GitHub 仓库
1. 登录 GitHub，点击右上角 "+" → "New repository"
2. 仓库名填写 `prompt-builder`（或你喜欢的名字）
3. 选择 Public，点 Create

### 步骤 2：上传文件
1. 在仓库页面点 "Add file" → "Upload files"
2. 把 pwa 文件夹里的所有文件（不含文件夹本身）拖入上传
3. 点 "Commit changes"

### 步骤 3：开启 GitHub Pages
1. 进入仓库 → Settings → Pages
2. Source 选择 "Deploy from a branch"
3. Branch 选 "main"，目录选 "/ (root)"
4. 点 Save
5. 等 1-2 分钟，页面会显示你的网址，类似：
   `https://你的用户名.github.io/prompt-builder/`

### 步骤 4：安装为桌面应用
1. 用 Chrome 或 Edge 打开上述网址
2. 地址栏右侧会出现安装图标（或点击菜单 → "安装应用"）
3. 点击安装，桌面就会出现应用图标
4. 之后从桌面图标打开，跟原生应用一样

## 部署到 Vercel（备选方案）

1. 访问 https://vercel.com，用 GitHub 账号登录
2. 点 "New Project" → "Import Git Repository"
3. 选择你的仓库
4. Framework Preset 选 "Other"
5. 点 Deploy
6. 部署完成后会给你一个 .vercel.app 域名

## 部署到 Netlify（备选方案）

1. 访问 https://app.netlify.com
2. 直接把 pwa 文件夹拖到页面上
3. 自动部署，几秒后给你一个网址

## 导出 / 导入配置

- 点击右上角 ☰ 菜单 → "导出配置"，会下载一个 JSON 文件
- 换设备后，同样点 ☰ → "导入配置"，选择之前的 JSON 文件即可恢复
- 建议定期导出备份

## 更新应用

修改文件后重新上传到 GitHub（或 push），GitHub Pages 会自动更新。
用户下次打开应用时，Service Worker 会自动获取新版本。

## 注意事项

- 首次加载需要联网（下载 React、字体等 CDN 资源）
- 安装后离线也能正常使用
- 数据保存在浏览器 localStorage 中，清除浏览器数据会丢失
- 建议定期使用"导出配置"功能备份数据
