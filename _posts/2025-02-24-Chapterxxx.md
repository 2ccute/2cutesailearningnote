---
title: Chapterxxx
date: 2025-02-24
categories: [技术, 教程]
tags: [jekyll, github, 博客]
---

## 什么是 Jekyll？

Jekyll 是一个基于 Ruby 的静态网站生成器，它可以将 Markdown、HTML 和 Liquid 模板转换为静态网站。Jekyll 是 GitHub Pages 的默认生成器，非常适合用来搭建个人博客或文档网站。

## 安装 Jekyll

在开始之前，你需要确保已经安装了 Ruby 和 Bundler。然后运行以下命令安装 Jekyll：
```bash
gem install jekyll bundler
```

## 创建一个新的 Jekyll 项目

使用以下命令创建一个新的 Jekyll 项目：

```bash
jekyll new my-blog
cd my-blog
```

## 项目结构

一个典型的 Jekyll 项目结构如下：

```
.
├── _config.yml       # 配置文件
├── _posts/           # 博客文章目录
├── _layouts/         # 布局模板
├── _includes/        # 可重用的组件
├── _data/            # 数据文件
├── assets/           # 静态资源（CSS, JS, 图片等）
├── _site/            # 生成的静态文件（自动生成）
└── index.md          # 首页
```

## 写第一篇文章

在 `_posts` 目录下创建一个新的 Markdown 文件，文件名格式为 `YYYY-MM-DD-标题.md`，例如：

```
_posts/2023-10-01-my-first-post.md
```

文件内容如下：

```markdown
---
title: 我的第一篇文章
date: 2023-10-01
categories: [技术, 教程]
tags: [jekyll, github]
---

这是我的第一篇文章，欢迎阅读！
```

## 本地测试

在项目根目录下运行以下命令启动本地服务器：

```bash
bundle exec jekyll serve
```

访问 `http://localhost:4000` 查看你的博客。

## 部署到 GitHub Pages

1. 将项目推送到 GitHub 仓库。
2. 在仓库的 `Settings -> Pages` 中启用 GitHub Pages。
3. 访问 `https://yourusername.github.io` 查看你的博客。

## 自定义主题

Jekyll 支持主题，你可以在 `_config.yml` 中指定主题：

```yaml
theme: minima
```

也可以自定义主题，修改 `_layouts` 和 `_includes` 中的文件。

## 总结

通过本教程，你已经学会了如何安装 Jekyll、创建项目、写文章以及部署到 GitHub Pages。接下来，你可以探索更多 Jekyll 的功能，例如插件、数据文件和 SEO 优化。

Happy blogging!
```

### 说明：
1. 这篇文章介绍了 Jekyll 的基本用法，适合初学者。
2. 你可以根据自己的需求修改内容或添加更多细节。
3. 保存文件后，推送到 GitHub 仓库即可在博客中看到这篇文章。

希望这篇文章对你有帮助！如果有其他问题，随时告诉我！
