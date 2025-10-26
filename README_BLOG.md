# 众妙之门 - 博客系统使用说明

## 📁 目录结构

```
/
├── index.html              # 主站（宇宙本体哲学论）
├── blog.html              # 博客首页（文章列表）
├── blog/                  # 博客目录
│   ├── posts/            # 文章存放目录
│   │   ├── template.html # 文章模板
│   │   └── example.html  # 示例文章
├── assets/               # 资源目录（可选）
│   └── css/             # 样式文件
├── CNAME                 # 自定义域名配置
└── README_BLOG.md        # 本说明文档
```

## 🎨 功能特性

### 1. 统一的设计风格
- 深色/浅色主题切换
- 响应式设计，支持手机和桌面
- 优雅的排版，适合长文阅读
- 自动生成文章目录（TOC）

### 2. 博客首页 (blog.html)
- 文章卡片列表展示
- 显示发布日期、分类、摘要
- 悬停动画效果
- 返回顶部按钮

### 3. 文章页面
- 自动生成侧边栏目录
- 平滑滚动导航
- 上一篇/下一篇导航
- 社交媒体分享元数据（Open Graph）

## ✍️ 如何添加新文章

### 方法一：复制模板（推荐）

1. **复制模板文件**
   ```bash
   cp blog/posts/template.html blog/posts/你的文章名.html
   ```

2. **编辑文章内容**
   - 修改 `<title>` 标签
   - 修改 SEO meta 标签（description, keywords）
   - 修改文章头部信息（标题、日期、分类）
   - 在 `<article class="article-content">` 中写入正文

3. **更新博客首页**
   在 `blog.html` 中添加文章卡片：
   ```html
   <article class="article-card" onclick="location.href='blog/posts/你的文章名.html'">
       <div class="article-meta">
           <span class="article-date">📅 2025-01-20</span>
           <span class="article-category">🏷️ 分类名称</span>
       </div>
       <h2 class="article-title">文章标题</h2>
       <p class="article-excerpt">
           文章摘要，建议100-200字...
       </p>
       <a href="blog/posts/你的文章名.html" class="read-more">阅读全文</a>
   </article>
   ```

### 方法二：参考示例文章

查看 `blog/posts/example.html` 了解完整的文章结构。

## 📝 文章编写规范

### 标题层级
```html
<h1>  <!-- 仅用于文章标题 -->
<h2 id="section1">第一节标题</h2>  <!-- 主要章节 -->
<h3 id="subsection">小节标题</h3>   <!-- 子章节 -->
```

**重要**：为 h2 和 h3 添加 `id` 属性，用于目录导航。

### 段落和缩进
```html
<p>正文段落会自动首行缩进2个字符...</p>
```

### 引用
```html
<blockquote>
    <p>这是引用内容，会显示特殊样式</p>
</blockquote>
```

### 列表
```html
<ul>
    <li>无序列表项</li>
</ul>

<ol>
    <li>有序列表项</li>
</ol>
```

### 强调文本
```html
<strong>重要内容</strong>  <!-- 显示为金色 -->
```

### 分割线
```html
<hr>  <!-- 会显示装饰性分隔符 ✦ -->
```

### 代码
```html
<code>行内代码</code>

<pre><code>
代码块
多行代码
</code></pre>
```

## 🎯 SEO 优化建议

### 1. 页面元数据
每篇文章都应包含完整的 meta 标签：

```html
<title>文章标题 - 众妙之门</title>
<meta name="description" content="文章描述，建议150-160字">
<meta name="keywords" content="关键词1,关键词2,关键词3">
<meta name="author" content="卿艺">
```

### 2. Open Graph（社交分享）
```html
<meta property="og:type" content="article">
<meta property="og:title" content="文章标题">
<meta property="og:description" content="文章描述">
<meta property="og:url" content="https://qingyi.chat/blog/posts/文章名.html">
```

### 3. 文章结构
- 使用清晰的标题层级（H1 > H2 > H3）
- 每个章节有唯一的 ID
- 合理使用语义化 HTML 标签

## 🌐 网站访问地址

- **主站**: https://qingyi.chat 或 https://qingyi.chat/index.html
- **博客**: https://qingyi.chat/blog.html
- **文章**: https://qingyi.chat/blog/posts/文章名.html

## 🚀 部署到 GitHub Pages

1. **提交更改**
   ```bash
   git add .
   git commit -m "添加新文章：文章标题"
   git push
   ```

2. **等待部署**
   GitHub Pages 会自动部署，通常需要1-2分钟

3. **访问验证**
   在浏览器中打开对应链接验证

## 🎨 主题定制

如果需要修改颜色主题，编辑 CSS 变量：

```css
:root {
    --bg-color: #0f0f0f;        /* 背景色 */
    --text-color: #e8e6e3;      /* 文字颜色 */
    --heading-color: #f5f5dc;   /* 标题颜色 */
    --accent-color: #d4af37;    /* 强调色（金色） */
    --secondary-bg: #1a1a1a;    /* 次要背景 */
    --border-color: #333;       /* 边框颜色 */
    --link-color: #87ceeb;      /* 链接颜色 */
}
```

## 📱 响应式设计

博客系统已针对不同设备优化：
- **桌面端**: 最佳阅读体验，侧边栏目录
- **平板**: 自适应布局
- **手机**: 简化导航，触摸优化

## 💡 使用技巧

### 1. 文章目录自动生成
只要为 h2 和 h3 标签添加 id 属性，JavaScript 会自动生成侧边栏目录，支持平滑滚动导航。

### 2. 主题偏好记忆
用户切换主题后，选择会保存在浏览器 localStorage 中，下次访问自动应用。

### 3. 文章卡片点击
博客首页的文章卡片整个区域都可点击，提升用户体验。

### 4. 移动端优化
在移动设备上，点击目录项后会自动关闭侧边栏，避免遮挡内容。

## 📋 待办事项（可选扩展）

- [ ] 添加文章标签系统
- [ ] 实现按分类筛选
- [ ] 添加搜索功能
- [ ] RSS 订阅支持
- [ ] 评论系统集成（如 Giscus）
- [ ] 阅读时长估算
- [ ] 文章浏览量统计

## 🤝 维护建议

1. **定期备份**: 定期备份整个仓库
2. **文章编号**: 建议文章文件名使用日期前缀，如 `2025-01-15-article-title.html`
3. **图片管理**: 如需添加图片，建议创建 `assets/images/` 目录
4. **版本控制**: 每次添加/修改文章都应提交到 Git

## 📞 问题反馈

如有问题或建议，可以：
- 在 GitHub 仓库提 Issue
- 联系作者：卿艺

---

✨ 祝写作愉快！
