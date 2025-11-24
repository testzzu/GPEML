# GPEML Conference Website

This is a conference website built with [Hugo](https://gohugo.io/) static site generator, styled after academic conference websites like PRICAI 2025.

## 快速开始

### 安装 Hugo

如果你还没有安装 Hugo，请访问 [Hugo 官网](https://gohugo.io/installation/) 查看安装说明。

### 本地开发

1. 启动开发服务器：
```bash
hugo server
```

2. 在浏览器中访问：http://localhost:1313

### Create New Content

```bash
# Create a new page
hugo new content page-name.md

# Create a new post
hugo new content posts/post-name.md
```

### 构建静态网站

```bash
hugo
```

构建后的文件将输出到 `public/` 目录。

## Site Structure

The website follows the structure of academic conference websites:

- **Home** - Welcome message and important dates
- **Organization** - Organizing committee and contact information
- **Calls** - Call for papers, workshops, sponsorship, and student scholarships
- **Submission** - Paper submission guidelines and system
- **Attending** - Venue, accommodation, visa, and travel information
- **Registration** - Registration fees and process
- **Program** - Conference schedule, keynotes, workshops, and tutorials
- **Proceedings** - Conference proceedings information

## Project Structure

```
GPEML/
├── archetypes/           # Content templates
├── assets/               # Asset files
├── content/              # Website content
│   ├── _index.md         # Homepage
│   ├── organization.md   # Organization page
│   ├── calls/            # Calls section
│   │   ├── call-for-papers.md
│   │   ├── call-for-workshops.md
│   │   ├── call-for-sponsorship.md
│   │   └── call-for-student-scholarship.md
│   ├── submission.md     # Submission page
│   ├── attending.md      # Attending page
│   ├── registration.md   # Registration page
│   ├── program.md        # Program page
│   └── proceedings.md    # Proceedings page
├── data/                 # Data files
├── hugo.toml             # Configuration file
├── i18n/                 # Internationalization
├── layouts/              # Custom layouts
├── static/               # Static files (images, CSS, JS)
└── themes/               # Themes directory
    └── PaperMod/         # PaperMod theme
```

## Theme

This project uses the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, which provides a clean and professional look suitable for academic conferences.

## Configuration

The main configuration file is `hugo.toml`, where you can modify:

- Site title and description
- Theme settings
- Menu configuration
- Other Hugo parameters

The site is configured with English as the primary language and includes a navigation menu matching typical conference website structures.

## 部署

### GitHub Pages

1. 构建网站：`hugo`
2. 将 `public/` 目录的内容推送到 GitHub Pages 仓库

### Netlify

1. 连接你的 Git 仓库到 Netlify
2. 构建命令：`hugo`
3. 发布目录：`public`

### Vercel

1. 连接你的 Git 仓库到 Vercel
2. 构建命令：`hugo`
3. 输出目录：`public`

## 更多资源

- [Hugo 文档](https://gohugo.io/documentation/)
- [PaperMod 主题文档](https://github.com/adityatelange/hugo-PaperMod/wiki)
- [Hugo 主题库](https://themes.gohugo.io/)

## 许可证

MIT License

