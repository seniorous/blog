# 博客维护指南

## 概览

这个仓库是一个基于 Astro 的静态博客，整体可以分成三层：

1. 内容层：文章、特殊页面和结构化数据。
2. 站点配置层：站点信息、导航、挂件、功能开关和主题行为。
3. 框架实现层：路由、布局、组件、样式、Markdown 插件、构建脚本和部署配置。

如果你的目标是把它改成自己的博客，建议先改内容层和配置层，大多数情况下不需要一开始就动框架层。

## 顶层结构

```text
src/
  content/          Markdown 文章和特殊页面
  data/             项目、时间线、技能、日记、设备等结构化数据
  pages/            路由页面
  components/       公共组件和挂件
  layouts/          页面布局
  styles/           全局和模块样式
  plugins/          Markdown 的 remark/rehype 扩展
  utils/            内容、路由、日期和 UI 工具
  config.ts         主站点配置
  content.config.ts 内容集合 schema
public/
  assets/           字体、banner、音乐资源、图标等静态资源
  images/           文章配图、相册图、设备图、日记图
  js/               前端辅助脚本
  pio/              Live2D 资源
scripts/            构建和内容同步脚本
docs/               项目文档
dist/               构建产物
```

## 哪些地方可以放心改

下面这些目录和文件，属于博客日常维护的主要区域，可以直接改：

- `src/config.ts`
- `src/content/posts/`
- `src/content/spec/`
- `src/data/`
- `public/images/`
- `public/assets/`

### 各区域通常负责什么

- `src/config.ts`：站点标题、副标题、域名、语言、功能开关、导航、个人资料卡、挂件、评论、分享、音乐播放器、壁纸、侧边栏布局、樱花效果、Pio、permalink 等。
- `src/content/posts/`：博客文章 Markdown 文件。
- `src/content/spec/about.md`：关于页正文。
- `src/content/spec/friends.md`：友链页正文。
- `src/data/`：项目、时间线、技能、日记、番剧、设备等数据页面。
- `public/images/`：文章图片和相册资源。
- `public/assets/`：logo、banner、字体、音乐相关资源等。

## 哪些地方可以改，但要谨慎

这几类文件一旦改动，会影响全站行为，属于主题和框架层定制：

- `src/pages/`
- `src/components/`
- `src/layouts/`
- `src/styles/`
- `src/plugins/`
- `src/utils/`
- `src/content.config.ts`
- `astro.config.mjs`

典型场景：

- 改页面结构或新增路由：`src/pages/`
- 替换或重做挂件：`src/components/`
- 改全站布局逻辑：`src/layouts/`
- 改视觉系统或排版：`src/styles/`
- 扩展 Markdown 能力：`src/plugins/`
- 改 front matter 校验规则：`src/content.config.ts`
- 改 Astro 集成、Markdown 管线或构建行为：`astro.config.mjs`

## 哪些地方通常不要动

除非你明确知道自己在做什么，否则不要把这些文件纳入日常维护：

- `dist/`
- `node_modules/`
- `.astro/`
- `.git/`
- `.vercel/project.json`
- `pnpm-lock.yaml`

这些要么是构建产物，要么是依赖元数据，要么是部署绑定信息。

## 主要功能模块

### 内容与发布

- Markdown 文章系统，支持分类、标签、草稿、置顶、评论、别名和自定义 permalink。
- About / Friends 页面由 Markdown 驱动。
- RSS、Atom、sitemap、robots 自动生成。

### 阅读与发现

- 首页分页和归档页。
- 基于 Pagefind 的全文搜索。
- 文章目录。
- 阅读时间和文章元信息展示。

### Markdown 增强

- Expressive Code 代码块渲染。
- KaTeX 数学公式。
- Mermaid 图表。
- Admonition 和自定义 markdown 指令。
- 图片增强和画廊行为。

### 站点视觉与交互

- 明暗主题切换。
- Banner 壁纸和全屏壁纸模式。
- 侧边栏挂件。
- 公告卡片。
- 分享海报。
- 可选评论系统。
- 音乐播放器。
- Pio Live2D 看板娘。
- 樱花特效。

### 专题页面

- Anime
- Diary
- Friends
- Projects
- Skills
- Timeline
- Albums
- Devices

这些专题页都可以在 `src/config.ts` 里开关。

## 文章 Front Matter

文章由 `src/content.config.ts` 校验，常用 front matter 字段如下：

```yaml
---
title: 文章标题
published: 2026-03-10
description: 简短摘要
image: /images/example/cover.jpg
tags: [标签1, 标签2]
category: 分类名
draft: false
pinned: false
comment: true
lang: zh_CN
alias: custom-slug
permalink: custom-path
encrypted: false
password:
---
```

## 推荐改造顺序

如果你想把这个博客真正改成自己的，建议按下面顺序做：

1. 先改 `src/config.ts`，把站点标题、副标题、域名、语言、导航、个人信息和功能开关换成自己的。
2. 再替换 `public/assets/` 和 `public/images/` 里的 banner、logo、头像和图片资源。
3. 清掉示例文章，在 `src/content/posts/` 里写自己的文章。
4. 重写 `src/content/spec/about.md` 和 `src/content/spec/friends.md`。
5. 把 `src/data/` 中的项目、时间线、技能、日记、设备等换成自己的数据。
6. 把用不到的专题页在 `src/config.ts` 里关掉。
7. 最后再决定要不要做主题级修改，比如改组件、布局、样式或路由。

## 常用命令

```bash
pnpm dev
pnpm build
pnpm preview
pnpm check
pnpm new-post my-post
```

### 含义

- `pnpm dev`：本地开发服务器
- `pnpm build`：生产构建
- `pnpm preview`：预览构建结果
- `pnpm check`：Astro 诊断和类型检查
- `pnpm new-post <name>`：创建一篇新文章

## 部署说明

- 当前部署方式是 Vercel，配置在 `vercel.json`。
- 本地 Vercel 项目绑定在 `.vercel/project.json`。
- `src/config.ts` 中的 `siteURL` 应该和生产域名一致。
- 如果你使用环境变量，先参考 `.env.example`，再在托管平台上配置同名变量。

## 实用判断规则

如果一项修改涉及站点身份、内容、图片、导航，或者只是启用和关闭某个模块，通常都比较安全。

如果一项修改涉及渲染逻辑、路由生成、Markdown 解析或构建行为，就把它当成框架层改动，谨慎处理。
