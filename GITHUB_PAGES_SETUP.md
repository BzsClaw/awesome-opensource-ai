# GitHub Pages 部署指南

## ✅ 已完成的配置

已创建 GitHub Actions 工作流文件：`.github/workflows/deploy-pages.yml`

该工作流会在以下情况触发：
- 推送到 `main` 分支
- 手动触发（Actions 页面）

---

## 📋 需要在 GitHub 网页端完成的步骤

### 步骤 1：启用 GitHub Pages

1. 访问你的仓库页面：`https://github.com/<username>/<repo>`
2. 点击 **Settings**（设置）标签
3. 在左侧菜单找到并点击 **Pages**
4. 在 **Build and deployment** 部分：
   - **Source**: 选择 `GitHub Actions`
5. 点击 **Save**（如果需要）

### 步骤 2：验证部署

1. 点击 **Actions** 标签
2. 找到名为 **"Deploy to GitHub Pages"** 的工作流
3. 如果刚推送了代码，应该会自动运行
4. 如需手动触发：
   - 点击工作流名称
   - 点击 **Run workflow** 按钮
   - 选择 `main` 分支
   - 点击 **Run workflow**

### 步骤 3：访问你的站点

部署成功后，你会看到：
- Actions 中显示绿色 ✓
- Pages 设置页面显示已部署的 URL

访问地址格式：
```
https://<username>.github.io/<repo>/
```

---

## 🔍 故障排查

### 如果部署失败：

1. **检查权限**：确保仓库允许 GitHub Actions
   - Settings → Actions → General → Allow all actions

2. **检查分支名称**：确保默认分支是 `main`
   - 如果是 `master`，请修改工作流文件中的 `branches: - main` 为 `branches: - master`

3. **查看日志**：
   - 点击失败的 workflow run
   - 展开各个步骤查看详细错误信息

---

## 📝 注意事项

- 首次部署可能需要 1-2 分钟
- GitHub Pages 免费额度：每月 100GB 流量
- 静态内容会自动缓存，更新后可能需要几分钟生效
- README.md 会作为首页内容展示

