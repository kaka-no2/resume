# 个人简历网站

## 部署方式

### 方式一：GitHub Pages（推荐，免费）

1. **创建GitHub仓库**
   - 登录GitHub，创建新仓库（例如：`resume`）
   - 设置为Public

2. **上传文件**
   ```bash
   cd 你的项目目录
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/你的用户名/resume.git
   git push -u origin main
   ```

3. **启用GitHub Pages**
   - 进入仓库Settings → Pages
   - Source选择：Deploy from a branch
   - Branch选择：main / (root)
   - 点击Save

4. **访问网站**
   - 网址：`https://你的用户名.github.io/resume/`
   - 通常5分钟内生效

### 方式二：Vercel（推荐，免费）

1. **访问** https://vercel.com
2. **导入项目**
   - 点击"New Project"
   - 导入GitHub仓库或直接拖拽文件夹
3. **部署**
   - 自动部署，获得网址如：`https://resume-xxx.vercel.app`
   - 支持自定义域名

### 方式三：Netlify（免费）

1. **访问** https://www.netlify.com
2. **拖拽部署**
   - 将整个项目文件夹拖到Netlify Drop区域
   - 自动部署，获得网址如：`https://xxx.netlify.app`

### 方式四：本地预览

```bash
cd 你的项目目录
python3 -m http.server 8000
```
访问：http://localhost:8000

## 文件结构

```
resume/
├── index.html          # 主页面
├── slides/             # 幻灯片图片
│   ├── titles.json     # 幻灯片标题配置（可修改）
│   └── slides.*.png    # 幻灯片图片
└── data/               # 原始数据（不需要部署）
```

## 修改幻灯片展示

编辑 `slides/titles.json` 文件，格式：
```json
{
  "4": "标题1",
  "5": "标题2",
  "7": "标题3",
  "8": "标题3"
}
```

- 键：幻灯片编号
- 值：显示的标题
- 相同标题的连续幻灯片会自动合并显示

修改后刷新页面即可看到更新。

## 注意事项

1. **部署时需要包含的文件**：
   - index.html
   - slides/ 文件夹（包含所有.png和titles.json）

2. **不需要部署的文件**：
   - data/ 文件夹（原始数据）
   - README.md（可选）

3. **自定义域名**：
   - GitHub Pages/Vercel/Netlify都支持绑定自定义域名
   - 需要在域名DNS设置中添加CNAME记录

## 技术栈

- 纯HTML/CSS/JavaScript
- 无需后端服务器
- 响应式设计，支持移动端
