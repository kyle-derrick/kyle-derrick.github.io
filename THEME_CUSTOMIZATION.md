# PaperMod 主题定制说明

## 概述

已从魔改版 PaperMod 切换到官方 PaperMod 主题，并基于官方版本重新实现了以下定制功能。

## 切换记录

### 移除的内容
- 移除了 `Kyle-Derrick/hugo-PaperMod` 子模块
- 清理了魔改版中的自定义样式

### 新增的内容
- 添加了官方 `adityatelange/hugo-PaperMod` 子模块
- 基于官方版本重新实现了所有定制功能

## 定制功能列表

### 1. 同级目录图片引入
- 支持在文章同级目录放置图片并通过相对路径引用
- 无需将图片放在 static 目录

### 2. 右侧目录固定 (toc.html)
- 大窗口 (>1280px) 时目录固定到右侧
- 小窗口时自动还原为官方默认样式（嵌入文章流中）
- 文件：`layouts/partials/toc.html`
- CSS：`assets/css/extended/custom-toc.css`

### 3. 目录滚动高亮
- 滚动时自动高亮当前浏览的章节
- JavaScript 实时检测滚动位置
- 已在 `toc.html` 中集成

### 4. 左侧文章树 (post-toc.html)
- 在文章和目录页面左侧显示完整文章列表
- 当前文章高亮显示
- 显示当前文章的子目录（标题）
- 小窗口 (<1280px) 时自动隐藏
- 文件：`layouts/partials/post-toc.html`
- CSS：`assets/css/extended/custom-post-toc.css`
- 已在 `layouts/single.html` 中引入

### 5. 面包屑当前页
- 顶部路径末尾添加当前页面标题
- 文件：`layouts/partials/breadcrumbs.html`
- CSS：`assets/css/extended/custom-breadcrumbs.css`

## 文件结构

```
layouts/
├── partials/
│   ├── toc.html           # 右侧目录（带高亮功能）
│   ├── post-toc.html      # 左侧文章树
│   └── breadcrumbs.html   # 面包屑（带当前页）
├── single.html            # 单页面模板（引入左侧文章树）

assets/css/extended/
├── custom-vars.css        # CSS变量扩展
├── custom-toc.css         # 右侧目录样式
├── custom-post-toc.css    # 左侧文章树样式
├── custom-breadcrumbs.css # 面包屑样式
├── custom-profile.css     # 个人主页样式
├── custom-post.css        # 文章样式
├── custom-entries.css     # 列表样式
├── custom-nav.css         # 导航样式
└── custom-global.css      # 全局样式
```

## 兼容性

- 与官方 PaperMod 主题完全兼容
- 支持官方深色/浅色模式切换
- 响应式设计，适配移动端

## 更新方法

如需更新官方 PaperMod 主题：

```bash
cd themes/PaperMod
git pull origin master
cd ../..
hugo --gc
```

定制功能位于项目根目录的 `layouts/` 和 `assets/css/extended/` 中，更新主题不会影响这些文件。
