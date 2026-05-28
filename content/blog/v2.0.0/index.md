---
title: v2.0.0 Released!
summary: Hugo v2.0.0 released. Download now and follow the guide to get started in 5 minutes!
date: 2024-01-19
authors:
  - me
tags:
  - Hugo
  - Hugo Blox
  - Markdown
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com)'
---

Hugo v2.0.0 is now available! This release includes new experimental features to try out, improvements to accessibility, the ability for plugins to customize image optimization in Markdown, and many more improvements and bug fixes.
⚙️ 配置文件区域 (config/_default/)
这里是网站的大脑，所有控制网站行为和外观的全局设置都放在这里，修改这里的文件会影响整个网站。

文件	作用	如何修改
hugo.yaml	Hugo 引擎的核心配置。定义网站的基础信息，如网址 (baseURL)、网站标题 (title)、是否启用多语言等。	修改这个文件，可以更改网站的全局标题、语言设置、版权年份等。
params.yaml	HugoBlox 主题的外观与功能配置中心。包括网站身份（作者、简介）、主题颜色、字体、页眉/页脚布局、社交链接等。	这是修改网站视觉风格和功能的核心文件。想换主题色、改字体、显示/隐藏搜索框，都来这儿。
menus.yaml	网站导航菜单的结构。定义页眉主菜单和侧边栏菜单的链接项、文本、显示顺序等。	要增删菜单项（如"首页"、"博客"）或调整它们的顺序，就在这里操作。
languages.yaml	多语言网站的配置。如果你的网站需要支持中英文等多语言，需要在这里进行设置。	根据官方文档的指引来配置，对于个人博客来说，通常不需要动这个文件。
📝 内容中心 (content/)
这里是网站的血肉，你写的所有文章、博客、个人介绍等纯文本内容都放在这里。它们大多是 Markdown 格式（后缀 .md）的文件。

关键目录/文件	作用	如何修改
_index.md	网站的首页内容。它的 Front Matter（文件开头的 --- 部分）定义了首页由哪些“模块”（Blocks）组成。	想修改首页的布局、增减模块、修改欢迎语等，都在这个文件里。
authors/	作者信息目录。每个作者一个子文件夹，里面的 _index.md 文件存放该作者的详细信息。	修改网站的作者信息、头像、社交链接时，需要在这里操作。
blog/	博客文章目录。里面每一个 .md 文件就是一篇博客文章。	这就是你写博客的地方。创建、修改、删除文章，都在这里进行。
docs/	文档目录。用于存放文档站点的具体内容，通常按主题分子文件夹。	如果你想把网站做成产品文档或教程站，内容就放在这里。
showcase/ & community/	示例和社区页面。存放项目展示或社区页面的内容。	如果你想修改这些特定页面的内容，就编辑对应目录下的文件。
🎨 资源与静态文件 (assets/ & static/)
这里是网站的装饰和附件，存放图片、字体、CSS、JS 等资源文件。

目录	作用	如何修改
assets/	资源文件目录。存放需要 Hugo 处理（如压缩、合并）的资源，如图片、CSS、JS、SVG 图标等。	如果你想替换网站的Logo、添加自定义图标或样式表，可以放到 assets/media/icons/ 或 assets/css/ 等子目录下。
static/	静态文件目录。存放无需 Hugo 处理、直接提供给用户的文件，如 resume.pdf 供下载的文件。	如果你想在网站上提供文件下载（如简历、PDF文档），请将它们放入 static/uploads/ 目录。
🛠️ 构建工具 (.github/ & go.mod)
这里是网站的后勤保障，负责自动化构建和部署。

文件/目录	作用	如何修改
.github/workflows/	GitHub Actions 部署脚本。当你把代码推送到 GitHub 时，这个脚本会自动运行 hugo 命令，生成并发布你的网站。	这是一个自动化工具，除非你非常清楚自己在做什么，否则不建议修改。
go.mod	Go 模块文件。用于管理 Hugo 主题作为 Go 模块的依赖。	同上，这是技术管理文件，通常不需要个人博客作者修改。
🎨 网站风格与外观修改
这部分是快速“改头换面”的核心，主要通过修改 config/_default/params.yaml 来实现。

更换主题色 (theme 部分)：修改 pack: 后面的值，可以一键更换主题色系（如 default, minimal, coffee, dracula 等）。如果需要自定义颜色，可以在 colors: 下使用 Tailwind 颜色名或十六进制色值。

更换字体 (typography 部分)：修改 pack: 后面的值，可以切换字体组合，例如 modern (Inter + JetBrains Mono) 或 academic (Lora + Source Serif 4)。这个配置也在 params.yaml 中。

修改 Logo 与网站标题：网站的标题在 params.yaml 的 identity: -> name: 字段中修改。更换 Logo 则需要将图片放入 assets/media/icons/ 目录，并在 params.yaml 的对应位置进行配置。

修改网站顶部菜单：导航栏中的菜单项在 config/_default/menus.yaml 文件中配置。你可以修改 name: (显示文字) 和 url: (链接地址) 来定制菜单。

✏️ 页面结构与内容
你现在可能主要关心两个页面：首页和博客文章。

首页 (content/_index.md)：这个文件的 Front Matter 定义了首页的“模块”构成。每个模块负责一个区块（如 Hero 横幅、Features 特性列表）。要修改首页内容，通常需要理解这些模块的用法。你可以在 HugoBlox 的官方文档中搜索 “Page Builder” 或 “Blocks” 来获得更详细的指引。

作者页面 (content/authors/me/_index.md)：这个文件专门用于配置网站作者的个人信息，比如姓名、职称、个人简介和社交链接等。

博客文章 (content/blog/xxx.md)：这就是你存放博客文章的地方。建议为每篇文章的 Front Matter 添加 categories (分类) 和 tags (标签) 字段，方便日后归档和检索。图片等资源建议放在文章同级的 index_files/ 文件夹中。

🧩 深入：当基础修改不够时
如果通过 YAML 文件已经无法满足你的定制需求，就需要修改更底层的模板了。

Hugo 模板的结构：主题的文件（在 themes/hugo-theme-documentation/ 中）是只读的，正确的修改方式是在项目根目录下创建同名的文件和文件夹来“覆盖”它们。

如何覆盖：比如要修改页脚，先找出主题中 themes/hugo-theme-documentation/layouts/partials/footer.html 文件，然后在你的项目根目录下创建 layouts/partials/footer.html，复制内容进去修改即可。你还可以通过覆盖 /assets/css/ 或 /assets/js/ 下的 custom.css 和 custom.js 文件来添加全局样式或脚本。

💎 总结与建议
现在，你已经对这个网站的“工具箱”有了一个整体的了解。

对于刚开始的你，不建议一上来就大改特改。我建议你按这个顺序来“改造”你的网站：

从修改外观开始：调整 params.yaml 中的网站名称、主题色和字体，立刻就能看到效果。

定制菜单和信息：修改 menus.yaml 来调整导航菜单，并更新 content/authors/me/_index.md 中的个人介绍。

创建你的第一篇博客：在 content/blog/ 目录下创建一个新的 .md 文件，开始你的写作。

处理首页内容：等你对博客流程熟悉后，再根据需求去研究和修改 content/_index.md 中的各个模块。

通过分步实践，你会对网站的结构和运作方式产生越来越深的理解。

如果在实践过程中，对某个具体文件或某个修改步骤有疑问，欢迎随时带着具体的问题来问我，我会为你提供更详细的说明。
Highlights include:

- New config options
- Improved accessibility
- Customizable image optimization in Markdown

Thank you to everyone who contributed to this release!

## New Features

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean vitae fringilla sem. Integer mattis dictum augue non auctor. Proin quis porttitor enim. Praesent vulputate arcu egestas scelerisque condimentum. Vivamus elit risus, suscipit et enim et, viverra molestie elit. Nulla ullamcorper nisl vel nisi pellentesque, id feugiat risus interdum. Duis consequat ipsum elit. Aenean hendrerit diam ipsum, a convallis magna congue et. Sed ex erat, pretium et ante id, malesuada luctus nibh. Nunc nec consectetur elit.

## Bug Fixes

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean vitae fringilla sem. Integer mattis dictum augue non auctor. Proin quis porttitor enim. Praesent vulputate arcu egestas scelerisque condimentum. Vivamus elit risus, suscipit et enim et, viverra molestie elit. Nulla ullamcorper nisl vel nisi pellentesque, id feugiat risus interdum. Duis consequat ipsum elit. Aenean hendrerit diam ipsum, a convallis magna congue et. Sed ex erat, pretium et ante id, malesuada luctus nibh. Nunc nec consectetur elit.

## How to Upgrade

Simply run the following command in your terminal:

```bash
hugo mod get -u github.com/HugoBlox/kit/modules/blox@main
```

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean vitae fringilla sem. Integer mattis dictum augue non auctor. Proin quis porttitor enim. Praesent vulputate arcu egestas scelerisque condimentum. Vivamus elit risus, suscipit et enim et, viverra molestie elit. Nulla ullamcorper nisl vel nisi pellentesque, id feugiat risus interdum. Duis consequat ipsum elit. Aenean hendrerit diam ipsum, a convallis magna congue et. Sed ex erat, pretium et ante id, malesuada luctus nibh. Nunc nec consectetur elit.
