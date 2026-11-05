# 吕昆泽 Kunze Lyu · 个人网站

纯静态网站，无需构建：`index.html` + `assets/`（4 张图表）。

## 本地预览
双击 `index.html`，或在本文件夹运行 `python3 -m http.server`，打开 http://localhost:8000

## 部署到 GitHub Pages（推荐，免费）
1. 在 GitHub 新建公开仓库，名字必须是 `xialuote77.github.io`
2. 上传 `index.html` 和 `assets/` 文件夹（保持目录结构）
3. 仓库 Settings → Pages → Source 选 `Deploy from a branch`，分支 `main`、目录 `/ (root)`
4. 1–2 分钟后访问 https://xialuote77.github.io

## 其他托管
Netlify / Vercel / Cloudflare Pages：把整个文件夹拖进去即可。

## 修改
- 中英文内容：每段文字都有 `<span lang="zh">` 和 `<span lang="en">` 两份
- 颜色和字体：`<style>` 顶部的 `:root` 变量，规则见 DESIGN.md
