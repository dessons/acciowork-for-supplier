# 🚀 GitHub Pages 部署指南

## 自动部署（推荐）

本项目已配置 GitHub Actions 自动部署，每次推送代码时会自动构建并发布到 GitHub Pages。

### 首次配置步骤

1. **推送代码到 GitHub**
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

2. **启用 GitHub Pages**
   - 访问：https://github.com/dessons/acciowork-for-supplier/settings/pages
   - **Source** 选择：`GitHub Actions`
   - 保存设置

3. **等待自动部署**
   - 推送代码后，GitHub Actions 会自动运行
   - 查看部署进度：https://github.com/dessons/acciowork-for-supplier/actions
   - 等待 2-3 分钟完成部署

4. **访问网站**
   - 网站地址：https://dessons.github.io/acciowork-for-supplier

### 后续更新

每次修改代码后，只需：

```bash
git add .
git commit -m "更新描述"
git push
```

GitHub Actions 会自动构建并部署最新版本！

## 手动部署步骤

如果自动脚本遇到问题，可以手动执行：

```bash
# 1. 初始化仓库
git init
git add .
git commit -m "Initial commit: Accio Work landing page"

# 2. 关联远程仓库（使用 token）
git remote add origin https://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@github.com/dessons/acciowork-for-supplier.git

# 3. 推送代码
git branch -M main
git push -u origin main

# 4. 部署到 GitHub Pages
npm run deploy
```

## 常见问题

### Q: 网站显示 404
A: 检查 GitHub Pages 设置是否选择了 `gh-pages` 分支

### Q: 部署后看不到更新
A: GitHub Pages 可能需要几分钟才能更新，清除浏览器缓存后重试

### Q: Token 过期了怎么办
A: 
1. 访问 https://github.com/settings/tokens
2. 生成新的 token
3. 更新 `deploy.sh` 中的 TOKEN 变量

## 项目信息

- **仓库地址**: https://github.com/dessons/acciowork-for-supplier
- **网站地址**: https://dessons.github.io/acciowork-for-supplier
- **构建工具**: Webpack 5
- **部署工具**: gh-pages

## 安全提示

⚠️ **重要**: `deploy.sh` 文件包含您的 GitHub Token，请不要将其提交到公开仓库！

Token 已添加到 `.gitignore`，但请确保：
- 不要分享 `deploy.sh` 文件
- 定期更换 Token
- Token 过期后及时更新

