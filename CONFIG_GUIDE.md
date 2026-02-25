# Gmeek 毛玻璃主题博客配置指南

本文档详细介绍如何配置和部署带有精美毛玻璃效果的博客。

---

## 一、快速开始

### 1. 部署到 GitHub Pages

1. **Fork 或上传项目**
   - 将整个项目上传到你的 GitHub 仓库
   - 仓库名建议格式：`用户名.github.io`

2. **启用 GitHub Pages**
   - 进入仓库 Settings → Pages
   - Source 选择 `Deploy from a branch`
   - Branch 选择 `main` 或 `master`，文件夹选择 `/ (root)`
   - 点击 Save

3. **访问博客**
   - 等待几分钟后，访问 `https://用户名.github.io` 即可看到你的博客

---

## 二、配置文件说明

### config.json 配置项

配置文件位于项目根目录的 `config.json`，以下是所有配置项说明：

```json
{
    "title": "椰青叶青",
    "subTitle": "椰青叶青个人博客",
    "avatarUrl": "https://avatars.githubusercontent.com/u/220160960?v=4&size=64",
    "GMEEK_VERSION": "last",
    "backgroundDesktop": "https://images.unsplash.com/photo-1519681393784-d120267933ba?w=1920",
    "backgroundMobile": "https://images.unsplash.com/photo-1557683316-973673baf926?w=800",
    "glassBlur": "20px",
    "glassOpacity": "0.85",
    "glassRadius": "20px",
    "glassBorder": "1px solid rgba(255, 255, 255, 0.3)",
    "glassShadow": "0 8px 32px rgba(0, 0, 0, 0.1)"
}
```

### 配置项详解

| 配置项 | 说明 | 默认值 | 示例 |
|--------|------|--------|------|
| `title` | 博客标题 | 必填 | "我的博客" |
| `subTitle` | 博客副标题 | 必填 | "记录生活点滴" |
| `avatarUrl` | 头像图片链接 | 必填 | 图片URL地址 |
| `GMEEK_VERSION` | Gmeek 版本 | "last" | 保持默认即可 |
| `backgroundDesktop` | 电脑端背景图片 | 推荐尺寸1920x1080 | 图片URL地址 |
| `backgroundMobile` | 手机端背景图片 | 推荐尺寸800x1200 | 图片URL地址 |
| `glassBlur` | 毛玻璃模糊程度 | "20px" | "10px" ~ "30px" |
| `glassOpacity` | 毛玻璃透明度 | "0.85" | "0.7" ~ "0.95" |
| `glassRadius` | 圆角大小 | "20px" | "10px" ~ "30px" |
| `glassBorder` | 边框样式 | "1px solid rgba(255, 255, 255, 0.3)" | CSS边框值 |
| `glassShadow` | 阴影效果 | "0 8px 32px rgba(0, 0, 0, 0.1)" | CSS阴影值 |

---

## 三、背景图片配置

### 推荐背景图片来源

1. **Unsplash** (免费高清图片)
   - 网址：https://unsplash.com
   - 使用方法：选择图片后，复制图片链接，添加 `?w=1920` 参数获取合适尺寸

2. **Pexels** (免费图片)
   - 网址：https://pexels.com

3. **自定义图片**
   - 可将图片上传到 GitHub 仓库，使用相对路径引用
   - 或使用图床服务获取链接

### 背景图片尺寸建议

- **电脑端背景**：宽度 1920px，高度 1080px 或更高
- **手机端背景**：宽度 800px，高度 1200px 或更高

### 示例配置

```json
{
    "backgroundDesktop": "https://images.unsplash.com/photo-1519681393784-d120267933ba?w=1920",
    "backgroundMobile": "https://images.unsplash.com/photo-1557683316-973673baf926?w=800"
}
```

---

## 四、毛玻璃效果参数调整

### 模糊程度 (glassBlur)

控制背景模糊的程度，值越大越模糊：

```json
{
    "glassBlur": "10px"  // 轻微模糊
    "glassBlur": "20px"  // 适中模糊（推荐）
    "glassBlur": "30px"  // 强烈模糊
}
```

### 透明度 (glassOpacity)

控制毛玻璃卡片的透明度：

```json
{
    "glassOpacity": "0.7"   // 较透明
    "glassOpacity": "0.85"  // 适中（推荐）
    "glassOpacity": "0.95"  // 几乎不透明
}
```

### 圆角大小 (glassRadius)

控制卡片的圆角程度：

```json
{
    "glassRadius": "10px"  // 小圆角
    "glassRadius": "20px"  // 中等圆角（推荐）
    "glassRadius": "30px"  // 大圆角
}
```

### 边框样式 (glassBorder)

控制卡片边框：

```json
{
    "glassBorder": "none"                                      // 无边框
    "glassBorder": "1px solid rgba(255, 255, 255, 0.3)"       // 白色半透明边框（推荐）
    "glassBorder": "2px solid rgba(100, 150, 255, 0.5)"       // 蓝色半透明边框
}
```

### 阴影效果 (glassShadow)

控制卡片阴影：

```json
{
    "glassShadow": "none"                                    // 无阴影
    "glassShadow": "0 8px 32px rgba(0, 0, 0, 0.1)"          // 柔和阴影（推荐）
    "glassShadow": "0 12px 48px rgba(0, 0, 0, 0.2)"         // 强烈阴影
}
```

---

## 五、发布新文章

### 通过 GitHub Issues 发布

1. 进入你的 GitHub 仓库
2. 点击 Issues → New Issue
3. 填写标题和内容（支持 Markdown 格式）
4. 添加标签（如 `documentation`）
5. 提交 Issue

### 文章自动生成

Gmeek 会自动将 Issues 转换为博客文章，生成的 HTML 文件位于 `docs/post/` 目录。

---

## 六、主题切换功能

博客内置了明暗主题切换功能：

- **Light 模式**：白色毛玻璃效果
- **Dark 模式**：深色毛玻璃效果
- **Auto 模式**：跟随系统设置

用户点击右上角的主题切换按钮即可切换。

---

## 七、自定义域名（可选）

### 绑定自定义域名

1. 在仓库根目录创建 `CNAME` 文件
2. 文件内容写入你的域名（如：`blog.example.com`）
3. 在域名服务商处添加 CNAME 记录指向 `用户名.github.io`

### HTTPS 配置

GitHub Pages 支持自动 HTTPS：
- 进入 Settings → Pages
- 勾选 Enforce HTTPS

---

## 八、常见问题

### Q: 背景图片不显示？

A: 检查图片链接是否有效，确保是 HTTPS 链接，且图片可公开访问。

### Q: 毛玻璃效果在手机上不显示？

A: 部分旧版浏览器可能不支持 `backdrop-filter`，建议使用现代浏览器。

### Q: 如何修改已发布的文章？

A: 在 GitHub Issues 中编辑对应的 Issue，保存后博客会自动更新。

### Q: 如何删除文章？

A: 关闭或删除对应的 Issue 即可。

---

## 九、效果预览

修改后的博客具有以下特点：

- ✨ 精美半透明毛玻璃卡片设计
- 🎨 圆角悬浮框效果
- 🌙 支持明暗主题切换
- 📱 响应式设计，手机端自动切换背景
- 🖼️ 可自定义电脑端和手机端背景图片
- 🚀 可直接部署到 GitHub Pages

---

## 十、技术支持

- Gmeek 官方文档：https://meekdai.com/Gmeek.html
- GitHub Pages 文档：https://docs.github.com/pages

---

**祝你使用愉快！** 🎉
