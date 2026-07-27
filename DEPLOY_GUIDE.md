# 🌐 部署指南：让外部用户也能访问文档

## 📋 当前状态

✅ **已完成**:
- 文档已转换为精美 HTML 网页
- 内网用户可通过 https://qq-personalization-guide.pages.woa.com 访问

❌ **限制**: OA Pages 是内网平台，**司外用户无法访问**

---

## 🚀 方案选择（推荐程度排序）

### ⭐ 方案一：Netlify Drop（最简单，30秒）

**适合人群**: 不想折腾技术细节的用户

**步骤**:
1. 打开浏览器访问: https://app.netlify.com/drop
2. 将文件夹 `/Users/boying/WorkBuddy/2026-07-27-18-59-52` 直接拖入浏览器窗口
3. 等待部署完成（约30秒）
4. 获得公开链接，格式如: `https://random-name-12345.netlify.app`

**优点**:
- ✅ 零配置，拖拽即用
- ✅ 自动 HTTPS
- ✅ 全球 CDN 分发
- ✅ 完全免费
- ✅ 无需注册也可快速预览（但建议注册以保留链接）

---

### ⭐⭐ 方案二：GitHub Pages（推荐，永久稳定）

**适合人群**: 有 GitHub 账号或愿意注册的用户

#### 方法 A：使用脚本自动部署（推荐）

```bash
# 1. 安装 GitHub CLI (如果未安装)
brew install gh

# 2. 登录 GitHub
gh auth login

# 3. 运行一键部署脚本
bash /Users/boying/WorkBuddy/2026-07-27-18-59-52/deploy-to-github.sh
```

#### 方法 B：手动部署（5分钟）

**步骤**:

1. **创建 GitHub 仓库**
   - 访问 https://github.com/new
   - Repository name: `qq-personalization-guide`
   - 选择 **Public**
   - 勾选 "Add a README file"
   - 点击 "Create repository"

2. **上传文件**
   ```bash
   cd /Users/boying/WorkBuddy/2026-07-27-18-59-52
   git init
   git add index.html images/
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<你的GitHub用户名>/qq-personalization-guide.git
   git push -u origin main
   ```

3. **启用 GitHub Pages**
   - 进入仓库 Settings -> Pages
   - Source 选择 "Deploy from a branch"
   - Branch 选择 `main`，目录选择 `/ (root)`
   - 点击 Save

4. **访问网站**
   - 等待1-2分钟
   - 访问: `https://<你的GitHub用户名>.github.io/qq-personalization-guide/`

**优点**:
- ✅ 永久免费托管
- ✅ 高可靠性（GitHub 基础设施）
- ✅ 支持自定义域名
- ✅ 版本控制（可追溯修改历史）
- ✅ 全球 CDN 加速

---

### ⭐⭐⭐ 方案三：Vercel（速度最快）

**步骤**:
1. 访问 https://vercel.com/import
2. 选择 "Import Git Repository" 或直接拖拽文件夹
3. 配置:
   - Framework Preset: Other
   - Build Command: 留空
   - Output Directory: `.`
4. 点击 Deploy

**优点**:
- ✅ 部署速度极快（全球边缘节点）
- ✅ 自动 HTTPS
- ✅ 实时预览每次更改
- ✅ 免费套餐足够个人使用

---

## 🔍 对比总结

| 特性 | Netlify Drop | GitHub Pages | Vercel |
|------|-------------|--------------|--------|
| **难度** | ⭐ 极简 | ⭐⭐ 简单 | ⭐⭐ 简单 |
| **时间** | 30秒 | 5分钟 | 2分钟 |
| **持久性** | 需注册账号 | 永久 | 永久 |
| **自定义域名** | 支持 | 支持 | 支持 |
| **版本控制** | ❌ | ✅ | ✅ |
| **速度** | 快 | 较快 | 最快 |

---

## 💡 推荐决策

- **只想快速分享给几个人看** → 用 **Netlify Drop**（30秒搞定）
- **需要长期稳定公开访问** → 用 **GitHub Pages**（推荐）
- **追求极致访问速度** → 用 **Vercel**

---

## 📞 需要帮助？

如果遇到问题，可以：
1. 查看各平台官方文档
2. 在终端运行脚本查看详细日志
3. 联系我获取进一步协助

---

**最后更新**: 2026-07-27
