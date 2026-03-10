# Mizuki 文档索引

欢迎查阅这个博客仓库的详细文档。

## 📚 文档列表

### 核心文档

- **[../README.md](../README.md)** - 仓库主说明
  - 本地开发
  - 常用命令
  - 目录结构
  - 部署方式

- **[BLOG_MAINTENANCE_GUIDE.md](./BLOG_MAINTENANCE_GUIDE.md)** - 博客维护指南
  - 哪些文件可以直接修改
  - 哪些地方需要谨慎修改
  - 主要功能模块
  - 推荐改造顺序

### 内容分离相关

- **[CONTENT_SEPARATION.md](./CONTENT_SEPARATION.md)** - 内容分离完整指南 ⭐
  - ENABLE_CONTENT_SYNC 控制开关
  - 环境变量配置详解
  - 私有仓库配置方法
  - 模式切换指南
  - 故障排查

- **[CONTENT_REPOSITORY.md](./CONTENT_REPOSITORY.md)** - 内容仓库结构指南
  - 推荐的目录结构
  - 文件组织方式
  - 内容编写规范
  - 图片管理建议

- **[MIGRATION_GUIDE.md](./MIGRATION_GUIDE.md)** - 内容迁移指南
  - 从单仓库迁移到分离模式
  - 详细迁移步骤
  - 测试验证方法

### 部署相关

- **[DEPLOYMENT.md](./DEPLOYMENT.md)** - 部署完整指南 ⭐
  - 各平台部署配置 (GitHub Pages / Vercel / Netlify / Cloudflare Pages)
  - 内容仓库更新自动触发构建
  - 私有仓库认证
  - 故障排查

- **[AUTO_BUILD_TRIGGER.md](./AUTO_BUILD_TRIGGER.md)** - 自动构建触发快速参考 🆕
  - 5 步快速配置，解决内容更新不触发部署的问题

## 🚀 快速查找

### 我是新手，想快速开始
→ 阅读 [主 README](../README.md)

### 我想部署博客
→ 阅读 [部署指南](./DEPLOYMENT.md)

### 我想使用内容分离功能
→ 阅读 [内容分离完整指南](./CONTENT_SEPARATION.md)

### 我想从单仓库迁移到分离模式
→ 阅读 [内容迁移指南](./MIGRATION_GUIDE.md)

### 我想配置私有内容仓库
→ 阅读 [内容分离指南 - 私有仓库配置](./CONTENT_SEPARATION.md#-私有仓库配置)

### 我的部署遇到问题
→ 阅读 [部署指南 - 故障排查](./DEPLOYMENT.md#-故障排查)

### 我遇到了内容同步错误
→ 阅读 [内容分离指南 - 故障排查](./CONTENT_SEPARATION.md#-故障排查)

### 内容仓库更新后站点没有自动重新部署 🆕
→ 阅读 [自动构建触发快速参考](./AUTO_BUILD_TRIGGER.md)

## 📖 文档架构

```
docs/
├── README.md                    # 本文档 - 索引导航
├── CONTENT_SEPARATION.md        # 内容分离核心指南
├── CONTENT_REPOSITORY.md        # 内容仓库结构
├── MIGRATION_GUIDE.md           # 迁移指南
├── DEPLOYMENT.md                # 部署完整指南
├── AUTO_BUILD_TRIGGER.md        # 自动构建触发快速参考
└── image/                       # 文档图片资源
```

## 🎯 文档使用建议

### 新用户推荐阅读顺序

1. [主 README](../README.md) - 了解项目基本情况
2. [博客维护指南](./BLOG_MAINTENANCE_GUIDE.md) - 了解可修改范围
3. [部署指南](./DEPLOYMENT.md) - 选择平台并部署
4. (可选) [内容分离指南](./CONTENT_SEPARATION.md) - 高级功能

### 高级用户推荐

- 直接查阅具体主题的文档
- 使用快速查找定位问题解决方案

## 🤝 需要帮助？

- 查看 [GitHub Issues](https://github.com/seniorous/blog/issues)
- 阅读相关文档的故障排查章节
- 运行 `pnpm check` 检查配置

祝你使用愉快！🎉
