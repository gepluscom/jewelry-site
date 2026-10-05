# 玥光珠宝品牌展示站

纯静态网站（单 `index.html` + `assets/` 图片），零依赖、零构建，
按「AI 生成代码 → GitHub 托管 → Cloudflare Pages 免费部署」三步上线。

## 本地预览

```bash
cd ~/workspace/jewelry-site
python3 -m http.server 8080
# 浏览器打开 http://localhost:8080
```

## 第 2 步：推送到 GitHub

```bash
cd ~/workspace/jewelry-site
git init -b main
git add .
git commit -m "品牌展示站第一版"

# 方式 A：用 GitHub CLI（一行搞定，需先 gh auth login）
gh repo create jewelry-site --public --source=. --push

# 方式 B：网页建空仓库后
git remote add origin https://github.com/你的用户名/jewelry-site.git
git push -u origin main
```

## 第 3 步：Cloudflare Pages 免费部署

1. 登录 [dash.cloudflare.com](https://dash.cloudflare.com) → 左侧 **Workers & Pages**
2. **Create** → **Pages** → **Connect to Git** → 授权并选中 `jewelry-site` 仓库
3. 构建设置：Framework preset 选 **None**，
   Build command 留空，Build output directory 填 `/`
4. **Save and Deploy**，约 1 分钟后得到 `https://jewelry-site.pages.dev`
5. （可选）在 Pages → Custom domains 绑定自己的域名，免费自动配 HTTPS

## 改内容

| 想改 | 位置 |
|---|---|
| 品牌名 | `index.html` 搜索 `YUEGUANG` / `玥光` 全文替换 |
| 邮箱 | 搜索 `hello@example.com` 替换 |
| 价格/文案 | 搜索 `¥` / 对应中文文案 |
| 产品图 | 替换 `assets/` 下同名 `.webp` 文件即可 |

Cloudflare Pages 免费额度：每月 500 次构建、无限带宽（合理使用），个人展示站完全够用。
