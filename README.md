# 博客源码仓库

这是当前博客站点的源码仓库，技术栈为 `Astro + Svelte + Tailwind CSS`，用于管理文章内容、页面配置、静态资源和部署流程。

- 线上地址：<https://mizuki-sooty.vercel.app/>
- 部署平台：Vercel
- Node.js：`>= 20`
- 包管理器：`pnpm`

## 目录说明

```text
src/
  content/          文章和特殊页面
  data/             项目、技能、时间线、日记、设备等数据
  pages/            路由页面
  components/       组件和挂件
  layouts/          页面布局
  styles/           样式
  plugins/          Markdown 扩展
  utils/            工具函数
  config.ts         全站配置
  content.config.ts 文章 front matter 校验
public/
  assets/           banner、字体、音乐等静态资源
  images/           文章和专题页图片
docs/               项目文档
scripts/            构建和同步脚本
```

## 最常改的地方

- `src/config.ts`
- `src/content/posts/`
- `src/content/spec/about.md`
- `src/content/spec/friends.md`
- `src/data/`
- `public/images/`
- `public/assets/`

更详细的维护说明见：

- [docs/BLOG_MAINTENANCE_GUIDE.md](./docs/BLOG_MAINTENANCE_GUIDE.md)
- [docs/README.md](./docs/README.md)

## 本地开发

```bash
pnpm install
pnpm dev
```

默认本地地址：

```text
http://localhost:4321
```

## 常用命令

```bash
pnpm dev
pnpm build
pnpm preview
pnpm check
pnpm new-post my-post
```

## 发文方式

新文章放在 `src/content/posts/`，常用 front matter 结构如下：

```yaml
---
title: 文章标题
published: 2026-03-10
description: 文章摘要
image: /images/example/cover.jpg
tags: [标签1, 标签2]
category: 分类名
draft: false
pinned: false
comment: true
---
```

## 部署说明

- 当前仓库已绑定 Vercel 项目。
- 推送到远端后会触发部署。
- 手动部署可使用 `vercel deploy --prod`。
- 部署前确保 `src/config.ts` 中的 `siteURL` 与生产域名一致。

## 环境变量

可选环境变量示例见：

- [.env.example](./.env.example)

如果使用云平台部署，不要把 `.env` 提交到 Git，直接在平台配置环境变量即可。

## 当前站点包含的主要模块

- 文章系统
- 分类与标签
- 搜索
- RSS / Atom / Sitemap
- 归档页
- About / Friends
- Projects / Skills / Timeline / Diary / Anime / Albums / Devices
- 目录、分享、评论、音乐播放器、Pio、樱花效果等可选挂件
