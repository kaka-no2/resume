# 简历网站部署指南

## 密码保护功能说明

✅ 已添加密码保护功能
- **默认密码：** *******
- 访问网站时需要输入密码
- 密码使用SHA-256加密存储
- 验证状态保存在sessionStorage（关闭浏览器后需重新输入）

### 修改密码方法

如需修改密码，请按以下步骤操作：

1. 生成新密码的SHA-256哈希值：
   ```bash
   echo -n "你的新密码" | shasum -a 256
   ```

2. 打开 `index.html`，找到这一行：
   ```javascript
   const PASSWORD_HASH = '*************';
   ```

3. 将哈希值替换为新生成的值

## GitHub Pages 部署步骤

### 第一步：创建GitHub仓库

1. 登录 https://github.com
2. 点击右上角 "+" → "New repository"
3. 填写信息：
   - Repository name: `resume`（或其他名称）
   - Description: `个人简历网站`
   - 选择 **Public**（必须是Public才能使用免费的GitHub Pages）
4. 点击 "Create repository"

### 第二步：上传代码

**方式A：使用命令行（推荐）**

```bash
# 1. 进入项目目录
cd 你的项目目录

# 2. 初始化Git仓库
git init

# 3. 添加所有文件
git add .

# 4. 创建第一次提交
git commit -m "Initial commit: 添加个人简历网站"

# 5. 设置主分支名称
git branch -M main

# 6. 关联远程仓库（替换为你的用户名）
git remote add origin https://github.com/你的用户名/resume.git

# 7. 推送到GitHub
git push -u origin main
```

**方式B：使用GitHub网页上传**

1. 进入刚创建的仓库页面
2. 点击 "uploading an existing file"
3. 拖拽以下文件到页面：
   - `index.html`
   - `slides/` 文件夹（包含所有PNG和titles.json）
4. 点击 "Commit changes"

### 第三步：启用GitHub Pages

1. 进入仓库页面
2. 点击 "Settings"（设置）
3. 左侧菜单找到 "Pages"
4. 在 "Source" 下：
   - Branch: 选择 `main`
   - Folder: 选择 `/ (root)`
5. 点击 "Save"
6. 等待1-5分钟，页面会显示网址

### 第四步：访问网站

网址格式：`https://你的用户名.github.io/resume/`

## 分享简历

### 分享方式

1. **直接分享链接**
   ```
   https://你的用户名.github.io/resume/
   密码：resume2026
   ```

2. **生成短链接**（可选）
   - 使用 bit.ly 或 tinyurl.com 生成短链接
   - 更专业美观

### 注意事项

⚠️ **重要提醒：**
1. 密码保护是前端验证，不是绝对安全
2. 适合分享给HR、面试官等普通用户
3. 技术人员仍可能通过技术手段查看
4. 不要在简历中放置高度敏感信息

✅ **安全措施：**
- 密码使用SHA-256加密存储
- 禁用右键菜单
- 禁用F12开发者工具快捷键
- 验证状态仅保存在session中

## 更新简历

修改简历后重新部署：

```bash
cd 你的项目目录
git add .
git commit -m "更新简历内容"
git push
```

等待1-2分钟，网站自动更新。
