# GPEML 网站使用指南

## 如何通过 Hugo 新增页面

本网站使用 [Hugo](https://gohugo.io/) 静态网站生成器构建，使用 PaperMod 主题。以下是新增页面的几种方式：

### 方式一：在 content 目录下直接创建 Markdown 文件

这是最简单的方式，适用于创建独立页面。

1. **创建 Markdown 文件**

   在 `content/` 目录下创建新的 `.md` 文件，例如 `content/my-page.md`

2. **添加 Front Matter**

   在文件开头添加 YAML front matter（用 `+++` 包围）：

   ```markdown
   +++
   date = '2025-01-01T00:00:00+08:00'
   draft = false
   title = '我的页面标题'
   ShowToc = true
   +++
   
   ## 页面内容
   
   这里是页面的正文内容，支持 Markdown 语法。
   ```

3. **Front Matter 常用参数说明**

   - `date`: 页面日期（ISO 8601 格式）
   - `draft`: 是否为草稿（`false` 表示发布，`true` 表示不发布）
   - `title`: 页面标题
   - `ShowToc`: 是否显示目录（`true`/`false`）
   - `hiddenInHomeList`: 是否在首页列表中隐藏（`true`/`false`）

4. **访问页面**

   文件 `content/my-page.md` 会自动生成 URL：`/my-page/`

### 方式二：创建子目录（带 _index.md）

适用于创建有多个子页面的章节。

1. **创建目录和索引文件**

   例如创建 `content/my-section/` 目录，并在其中创建 `_index.md`：

   ```markdown
   +++
   title = '我的章节'
   +++
   
   这是章节的概述页面。
   ```

2. **添加子页面**

   在 `content/my-section/` 目录下创建其他 `.md` 文件作为子页面：

   - `content/my-section/page1.md` → URL: `/my-section/page1/`
   - `content/my-section/page2.md` → URL: `/my-section/page2/`

### 方式三：添加到导航菜单

如果希望新页面出现在网站导航栏中，需要编辑 `hugo.toml` 文件：

```toml
[[menu.main]]
  identifier = 'my-page'
  name = '我的页面'
  url = '/my-page/'
  weight = 80
```

参数说明：
- `identifier`: 菜单项的唯一标识符
- `name`: 在导航栏中显示的名称
- `url`: 页面的 URL 路径
- `weight`: 菜单项的排序权重（数字越小越靠前）

### 示例：参考现有页面

可以参考以下现有页面了解不同场景：

- **简单页面**: `content/organization.md`
- **带子页面的章节**: `content/attending/` 目录
- **首页**: `content/_index.md`

### 本地预览

1. **启动开发服务器**

   ```bash
   hugo server
   ```

2. **访问网站**

   打开浏览器访问 `http://localhost:1313/`

3. **查看更改**

   修改内容文件后，Hugo 会自动重新生成页面（热重载）

### 构建静态网站

生成最终网站文件：

```bash
hugo
```

生成的文件会输出到 `public/` 目录。

### 注意事项

1. **文件命名**: 使用小写字母和连字符，避免空格和特殊字符
2. **Front Matter**: 必须使用 `+++` 包围 YAML front matter
3. **图片路径**: 图片放在 `static/images/` 目录，引用时使用 `/images/文件名`
4. **草稿模式**: 设置 `draft = true` 的页面不会在构建时发布

### 更多资源

- [Hugo 官方文档](https://gohugo.io/documentation/)
- [PaperMod 主题文档](https://github.com/adityatelange/hugo-PaperMod)
- [Markdown 语法指南](https://www.markdownguide.org/)

