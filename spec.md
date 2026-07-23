# AI ToolBox 设计规范文档

## 1. 项目概述

**项目名称**: AI ToolBox — AI 工具集展示网站
**页面语言**: 简体中文 (zh-CN)
**设计系统**: Claude Design Library (warm dark-tone palette)
**默认主题**: 深色模式 (Dark)
**技术栈**: HTML + Tailwind CSS (CDN) + Lucide Icons + Canvas 2D (ink ripple effect)
**设计约束**: 所有颜色通过 CSS 自定义属性管理，禁止硬编码色值（Canvas JS 除外）

---

## 2. 色彩系统

### 2.1 品牌色 (Brand)

| Token | 色值 | 用途 |
|-------|------|------|
| `--color-brand-300` | `#8a5740` | 品牌深色辅助、Canvas 墨雾色 |
| `--color-brand-400` | `#b0683f` | 品牌中深色（实验性状态标签背景）、Canvas 次墨色 |
| `--color-brand-500` | `#d97757` | **主品牌色 / 强调色**（按钮、激活态、CTA、Canvas 主墨色） |
| `--color-brand-600` | `#e08d6f` | 品牌浅色（按钮 hover 态） |
| `--color-brand-700` | `#e8a98f` | 品牌极浅色 |

### 2.2 背景色 (Background)

| Token (Dark) | Dark 色值 | Token (Light) | Light 色值 | 用途 |
|-------------|-----------|-------------|------------|------|
| `--color-bg-50` | `#1b1b19` | `#faf9f5` | **页面主背景** |
| `--color-bg-100` | `#262624` | `#f1f1ef` | 次级背景（渐变终点、模态面板） |
| `--color-bg-200` | `#2c2c2b` | `#e9e6dc` | 卡片背景、输入框内背景 |
| `--color-bg-300` | `#30302e` | `#e0ddd3` | 次级表面 |
| `--color-bg-400` | `#3e3e38` | `#d0cdc3` | 标签背景、关闭按钮背景 |
| `--color-bg-500` | `#4a4a43` | `#b7b5a9` | 归档状态背景 |
| `--color-bg-700` | `#6e6d68` | `#908e84` | 次级中性 |
| `--color-bg-800` | `#908e84` | `#6e6d68` | 次级中性（反转） |

### 2.3 文字色 (Text)

| Token (Dark) | Dark 色值 | Token (Light) | Light 色值 | 用途 |
|-------------|-----------|-------------|------------|------|
| `--color-text-900` | `#faf9f5` | `#1b1b19` | **正文标题 / 主文字** |
| `--color-text-800` | `#f1f1ef` | `#2c2c2b` | 次级标题 |
| `--color-text-700` | `#d8d6cd` | `#46443b` | 卡片描述、代码内容、关闭按钮图标 |
| `--color-text-600` | `#c3c0b6` | `#6e6d68` | 功能列表文字、问题描述、技术标签文字 |
| `--color-text-500` | `#b7b5a9` | `#908e84` | **副标题 / muted 文字**、卡片描述、分类标签默认色 |
| `--color-text-400` | `#908e84` | `#b7b5a9` | Placeholder、辅助说明、搜索图标色、主题切换图标色 |
| `--color-text-300` | `#6e6d68` | `#d0cdc3` | 辅助信息（创建时间等） |
| `--color-text-200` | `#46443b` | `#e0ddd3` | 次级辅助 |
| `--color-text-100` | `#2c2c2b` | `#f1f1ef` | 次级辅助（反转） |
| `--color-text-50` | `#1b1b19` | `#faf9f5` | 极次级（反转） |

### 2.4 边框色 (Border)

| Token | Dark 色值 | Light 色值 | 用途 |
|-------|-----------|------------|------|
| `--color-border-200` | `#343430` | `#e0ddd3` | 导航栏底线、模态分割线 |
| `--color-border-300` | `#3e3e38` | `#d0cdc3` | 卡片边框、输入框边框、Prompt 代码块边框 |
| `--color-border-400` | `#4a4a43` | `#3e3e38` | — |
| `--color-border-500` | `#52514a` | `#4a4a43` | — |
| `--color-border-600` | `#6e6d68` | `#52514a` | — |
| `--color-border-700` | `#908e84` | `#6e6d68` | — |

### 2.5 语义色 (Semantic)

| Token | 色值 | 用途 |
|-------|------|------|
| `--color-success-500` | `#8ca06f` | "已上线" 状态标签背景 |
| `--color-success-700` | `#bccaa8` | 浅色成功辅助 |
| `--color-error-500` | `#ef4444` | 错误/破坏性操作 |

### 2.6 复合语义色 (Composite Semantic)

| Token | 用途 |
|-------|------|
| `--color-dark-primary` | 品牌主色（同 brand-500），Dark/Light 通用 |
| `--color-dark-card` | 卡片背景（同 bg-200 Dark / 白色 Light） |
| `--color-dark-card-foreground` | 卡片前景色（同 text-900） |
| `--color-dark-muted-foreground` | 弱化文字色（同 text-500） |
| `--color-dark-secondary` | 次级色（Dark: `#e9e6dc`，Light: `#46443b`） |
| `--color-dark-secondary-foreground` | 次级前景色 |
| `--color-dark-accent` | 强调背景色 |
| `--color-dark-primary-foreground` | 品牌按钮文字色（Dark: `#141413`，Light: `#faf9f5`） |
| `--color-dark-destructive` | 破坏性色（Dark: `#ef4444`，Light: `#dc2626`） |

### 2.7 阴影系统 (Shadow)

| Token | 值 | 用途 |
|-------|----|------|
| `--shadow-sm` | `0 1px 3px 0 rgba(0,0,0,0.1), 0 1px 2px -1px rgba(0,0,0,0.1)` | 微妙浮起 |
| `--shadow-md` | `0 1px 3px 0 rgba(0,0,0,0.1), 0 2px 4px -1px rgba(0,0,0,0.1)` | 中等浮起 |
| `--shadow-lg` | `0 1px 3px 0 rgba(0,0,0,0.1), 0 4px 6px -1px rgba(0,0,0,0.1)` | 卡片 hover 阴影 |
| `--shadow-xl` | `0 1px 3px 0 rgba(0,0,0,0.1), 0 8px 10px -1px rgba(0,0,0,0.1)` | 大型浮起 |
| `--shadow-2xl` | `0 1px 3px 0 rgba(0,0,0,0.25)` | 模态面板 |

> Light 模式下所有阴影的 alpha 值降低为 `0.06` (sm-xl) 和 `0.12` (2xl)。

---

## 3. 字体系统

### 3.1 字体栈

| Token | 字体栈 | 用途 |
|-------|--------|------|
| `--font-display` | `Newsreader, Georgia, ui-serif, serif` | Hero 标题（展示字体） |
| `--font-sans` | `Poppins, ui-sans-serif, system-ui, sans-serif` | 正文、导航、按钮、标签 |
| `--font-mono` | `Geist Mono, ui-monospace, monospace` | 代码块、Prompt 展示、标签文字 |

### 3.2 字号规范

| 元素 | 字号 | 字重 | 字体 |
|------|------|------|------|
| Hero 标题 (H1) | `clamp(36px, 5vw, 64px)` | 500 | `font-display` |
| Hero 副标题 | `16px / 18px` (sm:lg) | 400 | `font-sans` |
| 模态标题 (H2) | `20px / 24px` (sm:) | 700 (bold) | `font-sans` |
| 模态区块标题 (H3) | 15px | 600 | `font-sans` |
| 功能列表项 | 14px | 400 | `font-sans` |
| 卡片标题 | 16px | 600 | `font-sans` |
| 卡片描述 | 13px | 400 | `font-sans` |
| 导航品牌名 | `16px / 18px` (sm:) | 600 (semibold) | `font-sans` |
| 搜索输入框 | 14px | 400 | `font-sans` |
| 分类标签 (pill) | 13px | 400 | `font-sans` |
| Overlay 按钮 | 13px | 500 | `font-sans` |
| 技术标签 | 12px | 400 | `font-sans` |
| 状态标签 | 12px | 500 | `font-sans` |
| Prompt 展示标签 | 11px | 400 | `font-mono` (uppercase) |
| Prompt 代码 | 13px | 400 | `font-mono` |
| 模态 CTA 按钮 | 14px | 500 | `font-sans` |
| 辅助信息 | 12px | 400 | `font-sans` |

### 3.3 行高

| 场景 | 行高 |
|------|------|
| Hero 标题 | 1.2 |
| 正文描述 | 1.5 ~ 1.6 |
| 功能列表 | 1.6 |
| 构建故事 | 1.8 |
| Prompt 代码 | 1.6 |
| 问题描述 | 1.7 |

### 3.4 字体渲染

```css
body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
```

---

## 4. 圆角系统

| Token | 值 | 用途 |
|-------|----|------|
| `--radius-sm` | 8px | 按钮、技术标签、状态标签 |
| `--radius-md` | 12px | Prompt 代码块 |
| `--radius-lg` | 16px | 卡片主体 |
| `--radius-xl` | 20px | 模态面板 |
| `--radius-2xl` | 24px | — |
| `--radius-full` | 9999px | 搜索输入框、分类标签、关闭按钮 |

---

## 5. 间距系统

基础单位: **4px**

### 5.1 页面级间距

| 场景 | 间距 |
|------|------|
| 导航栏高度 | 56px (sm: 64px) |
| Hero 区域垂直内边距 | 64px (mobile) / 80px (tablet) / 112px (desktop) |
| 卡片网格区域垂直内边距 | 48px (mobile) / 64px (tablet) / 80px (desktop) |
| 内容容器水平内边距 | 16px (mobile) / 24px (tablet) / 32px (desktop) |

### 5.2 组件级间距

| 场景 | 间距 |
|------|------|
| 卡片网格间距 | 24px |
| 卡片体内边距 | 16px 18px 18px (上 右 下) |
| 卡片标题与描述间距 | 6px (margin-top) |
| 卡片描述与技术标签间距 | 12px (margin-top via mt-3) |
| 卡片标签组间距 | 6px (gap) |
| Overlay 按钮间距 | 12px (gap) |
| 分类标签组间距 | 8px (gap) |
| 导航 Logo 与分类标签间距 | 24px (mx-6, desktop) |

### 5.3 模态间距

| 场景 | 间距 |
|------|------|
| 模态面板外边距 | `padding: 40px 16px` (desktop: `16px 40px`) |
| 模态面板体内边距 | 24px 28px 32px (mobile: 20px 18px 28px) |
| 模态区块间距 | 20px (margin-top + padding-top) |
| 模态标题行间距 | 12px (gap) |
| 模态描述行间距 | 8px (mb-2) |
| 模态时间行间距 | 4px (mb-1) |
| 模态技术标签行间距 | 24px (mb-6) |
| 模态区块标题下间距 | 10px (margin-bottom) |
| 功能列表项间距 | 6px (gap) |
| 功能列表项左侧缩进 | 18px (padding-left) |
| Prompt 标签下间距 | 8px (margin-bottom) |
| Prompt 代码块内边距 | 14px 18px |
| AI 工具/迭代行与 Prompt 间距 | 16px (mt-4) |
| AI 工具/迭代行与故事段落间距 | 16px (mb-4) |
| CTA 按钮上间距 | 24px (margin-top) |

### 5.4 尺寸规范

| 元素 | 尺寸 |
|------|------|
| 搜索输入框高度 | 36px |
| 搜索输入框宽度 | 200px (desktop) |
| 搜索输入框左侧 padding | 36px (给图标留位) |
| 搜索输入框右侧 padding | 12px |
| 分类标签高度 | 32px |
| 分类标签水平 padding | 0 14px |
| 技术标签高度 | 24px |
| 技术标签水平 padding | 0 10px |
| 状态标签高度 | 24px |
| 状态标签水平 padding | 0 10px |
| Overlay 按钮高度 | 36px |
| Overlay 按钮水平 padding | 0 16px |
| 模态 CTA 按钮高度 | 40px |
| 模态 CTA 按钮水平 padding | 0 24px |
| 关闭按钮尺寸 | 36×36px |
| Logo SVG 图标尺寸 | 24×24px |
| 功能列表圆点尺寸 | 6×6px |
| 卡片图片宽高比 | 16:9 |
| 模态图片宽高比 | 16:7 (mobile: 16:9) |

### 5.5 最大宽度

| 元素 | 最大宽度 |
|------|---------|
| 内容容器 | `1280px` (max-w-7xl) |
| Hero 文字容器 | `768px` (max-w-3xl) |
| Hero 副标题最大宽度 | `480px` |
| 模态面板 | `800px` |
| 模态面板最大高度 (mobile) | `90vh` |
| 卡片网格列最小宽度 | `320px` |

---

## 6. 页面结构

### 6.1 整体布局

```
<body>
  <nav> — 粘性顶部导航 (sticky, z-50)
  <main>
    <section#hero-section> — Hero 区域 (含 Canvas 水墨动效)
    <section> — 卡片网格区域
  </main>
  <div#detail-modal> — 详情模态浮层 (fixed, z-100)
</body>
```

### 6.2 导航栏 (Sticky Navigation)

- **定位**: `sticky top-0 z-50`
- **背景**: `var(--color-bg-50)`
- **底线**: `1px solid var(--color-border-200)`
- **高度**: 56px (mobile) / 64px (tablet+)
- **内部布局**: Flex, `justify-between`, 左 logo / 中分类标签 / 右搜索+切换
- **响应式**:
  - Desktop (>=768px): 分类标签水平排列，搜索框展开
  - Mobile (<768px): 搜索框收起为图标，分类标签收入汉堡下拉菜单

**Logo**:
- 内联 SVG 图标 (三层堆叠方块)，24x24px，`stroke-width: 2`
- 颜色: `var(--color-brand-500)`
- 文字: "AI ToolBox"，`font-sans`，16/18px，semibold
- `shrink-0` 禁止压缩

**分类标签 (Category Pills)**:
- 样式类: `.category-pill`
- 激活态 (`.active`): `background-color: var(--color-brand-500)`, `color: var(--color-dark-primary-foreground)`, `border-color: var(--color-brand-500)`
- 默认态: 透明背景，`border: 1px solid transparent`, `color: var(--color-text-500)`
- Hover: `background-color: var(--color-bg-200)`, `color: var(--color-text-700)`
- 过渡: `background-color 0.15s ease, color 0.15s ease, border-color 0.15s ease`
- 分类项: 全部 / Web应用 / 小工具 / Chrome插件 / 自动化脚本 / 实验性项目
- Desktop: 水平排列，`overflow-x: auto`，`scrollbar-width: none`
- Mobile: 收入 `#mobile-menu` 下拉面板，同样水平排列可滚动

**搜索输入框**:
- 样式类: `.search-input`
- 宽度: 200px (desktop)，full (mobile 下拉)
- 高度: 36px
- 圆角: `var(--radius-full)`
- 边框: `1px solid var(--color-border-300)`
- 背景: `var(--color-bg-100)`
- Focus 态: `border-color: var(--color-brand-500)`, `box-shadow: 0 0 0 2px rgba(217,119,87,0.15)`
- Focus ring 颜色: `rgba(217,119,87,0.15)` (品牌色 15% 透明度)
- 左侧 Lucide `search` 图标，14x14px，`color: var(--color-text-400)`，绝对定位 `left: 12px, top: 50%, translateY(-50%)`
- Placeholder: `color: var(--color-text-400)`

**主题切换按钮**:
- Dark 模式显示 `sun` 图标，Light 模式显示 `moon` 图标
- 图标尺寸: 20x20px (w-5 h-5)
- 颜色: `var(--color-text-400)`
- 偏好存储: `localStorage('toolbox-theme')`
- 切换时通过 `style.display` 控制图标显隐

**汉堡菜单按钮** (Mobile only):
- 显示条件: `<768px` (md:hidden)
- Lucide `menu` 图标，20x20px
- 颜色: `var(--color-text-400)`
- 点击行为: toggle `#mobile-menu` 和 `#mobile-search-bar` 的 `hidden` 类

**Mobile 搜索按钮** (Mobile only):
- 显示条件: `<640px` (sm:hidden)
- Lucide `search` 图标，20x20px
- 点击行为: toggle `#mobile-search-bar` 的 `hidden` 类

---

### 6.3 Hero 区域

- **ID**: `#hero-section`
- **背景**: 渐变 `linear-gradient(180deg, var(--color-bg-50) 0%, var(--color-bg-100) 100%)`
- **装饰光晕**: 绝对定位圆形，500x350px，居中偏移 (`top: 50%, left: 50%, translate(-50%, -50%)`)，`background: var(--color-brand-500)`, `opacity: 0.05`, `filter: blur(100px)`, `pointer-events: none`
- **垂直内边距**: `py-16 sm:py-20 lg:py-28` (64px / 80px / 112px)
- **overflow**: `hidden`（裁剪 Canvas 超出部分）
- **水墨 Canvas**: 见 6.6 节
- **文字层**: `relative z-index: 2`，居中对齐 (`text-center, max-w-3xl, mx-auto, px-4`)

**H1 标题**:
- "用自然语言写出来的产品"
- `font-family: var(--font-display)`
- `font-size: clamp(36px, 5vw, 64px)`
- `font-weight: 500`
- `line-height: 1.2`
- `color: var(--color-text-900)`
- `text-wrap: balance`（自动平衡换行）
- `word-break: keep-all`（中文词语不拆分）
- `overflow-wrap: break-word`（超长时允许拆分）

**副标题**:
- "每一个工具都始于一句 Prompt，终于一次点击"
- `font-family: var(--font-sans)`
- `font-size: 16px` (mobile) / `18px` (sm+)
- `color: var(--color-text-500)`
- `margin-top: 16px` (mt-4)
- `max-width: 480px`, `margin-left: auto; margin-right: auto`

---

### 6.4 卡片网格

**容器**:
- 垂直内边距: `py-12 sm:py-16 lg:py-20`
- 水平内边距: `px-4 sm:px-6 lg:px-8`
- 背景: `var(--color-bg-50)`

**网格布局**:
```css
.tool-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 24px;
}
```

| 断点 | 列数 |
|------|------|
| >=1024px | 3~4 列 (auto-fill, min 320px) |
| 768px ~ 1023px | 2 列 |
| <768px | 1 列 (媒体查询强制覆盖) |

**单张卡片结构**:
```html
<article class="tool-card" data-category="..." data-name="..." data-desc="...">
  <div class="card-image-wrapper">        <!-- 16:9 预览图区 -->
    <img class="card-preview-img" src="..." alt="..." loading="eager|lazy">
    <div class="card-overlay">            <!-- hover 浮出层 -->
      <button data-dom-id="detail-N" class="overlay-btn">查看详情</button>
      <a href="#" target="_blank" rel="noopener noreferrer"
         class="overlay-btn overlay-btn-secondary">在线体验</a>
    </div>
  </div>
  <div class="card-body">                 <!-- 卡片信息区 -->
    <div class="flex items-center justify-between gap-2">
      <h3 class="card-title truncate">...</h3>
      <span class="status-badge status-{live|dev|exp|arch} shrink-0">...</span>
    </div>
    <p class="card-desc line-clamp-2">...</p>
    <div class="flex flex-wrap gap-1.5 mt-3">
      <span class="tech-tag">...</span>
    </div>
  </div>
</article>
```

**卡片样式**:
- 圆角: `var(--radius-lg)` (16px)
- 边框: `1px solid var(--color-border-300)`
- 背景: `var(--color-dark-card)`
- `overflow: hidden`
- Hover: `box-shadow: var(--shadow-lg)`, `transform: translateY(-2px)`, 过渡 `0.2s ease`
- 隐藏态: `.card-hidden` → `display: none`

**预览图**:
- 样式类: `.card-preview-img`
- `width: 100%, height: 100%, object-fit: cover, display: block`
- 第一张卡片 `loading="eager"`，其余 `loading="lazy"`
- Hover: `transform: scale(1.03)`，过渡 `0.3s ease`

**图片背景色** (`.card-image-wrapper`):
- `background-color: var(--color-bg-200)` — 图片加载前的兜底背景

**Hover Overlay** (`.card-overlay`):
- 绝对定位覆盖图片区域 (`inset: 0`)
- Flex 居中 (`display: flex, align-items: center, justify-content: center`)
- 间距: `gap: 12px`
- 背景: `rgba(0, 0, 0, 0.55)`
- 模糊: `backdrop-filter: blur(4px)`, `-webkit-backdrop-filter: blur(4px)`
- 默认 `opacity: 0`，hover 时 `opacity: 1`
- 过渡: `opacity 0.2s ease`

**"查看详情" 按钮** (`.overlay-btn`):
- `display: inline-flex, align-items: center, justify-content: center`
- 高度: 36px，padding: `0 16px`
- 圆角: `var(--radius-sm)` (8px)
- `border: none`
- 字号: 13px，字重: 500
- 背景: `var(--color-brand-500)`
- 文字色: `var(--color-dark-primary-foreground)`
- Hover: `background-color: var(--color-brand-600)`
- 过渡: `background-color 0.15s ease`

**"在线体验" 按钮** (`.overlay-btn-secondary`):
- 继承 `.overlay-btn` 基础样式
- 背景: `rgba(255, 255, 255, 0.15)`
- 文字色: `var(--color-text-900)`
- 边框: `1px solid rgba(255, 255, 255, 0.25)`
- Hover: `background-color: rgba(255, 255, 255, 0.25)`

**状态标签** (`.status-badge`):

| 状态 | 修饰类 | 背景色 | 文字色 |
|------|--------|--------|--------|
| 已上线 | `.status-live` | `var(--color-success-500)` | `var(--color-dark-primary-foreground)` |
| 开发中 | `.status-dev` | `var(--color-brand-500)` | `var(--color-dark-primary-foreground)` |
| 实验性 | `.status-exp` | `var(--color-brand-400)` | `var(--color-text-900)` |
| Archive | `.status-arch` | `var(--color-bg-500)` | `var(--color-text-400)` |

**技术标签** (`.tech-tag`):
- `display: inline-flex, align-items: center`
- 高度: 24px，padding: `0 10px`
- 圆角: `var(--radius-sm)` (8px)
- 背景: `var(--color-bg-400)`
- 文字: `var(--color-text-600)`
- 字号: 12px

---

### 6.5 详情模态浮层 (Detail Modal)

**容器 ID**: `#detail-modal`
**触发**: 点击卡片的"查看详情"按钮 (`data-dom-id="detail-N"`, N = 1~6)

**结构**:
```html
<div id="detail-modal" class="modal-overlay hidden">
  <div class="modal-backdrop"></div>
  <div class="modal-panel">
    <button id="modal-close" class="modal-close-btn" aria-label="关闭">
      <i data-lucide="x" class="w-5 h-5"></i>
    </button>
    <div class="modal-image-section">
      <img id="modal-image" src="" alt="" class="modal-image">
    </div>
    <div class="modal-content-body">
      <!-- 标题行: H2 + 状态标签 -->
      <!-- 描述 -->
      <!-- 创建时间 -->
      <!-- 技术标签组 -->
      <!-- 区块: 这个工具解决什么问题 -->
      <!-- 区块: 核心功能 (功能列表) -->
      <!-- 区块: 构建故事 (Prompt 代码块 + AI 工具 + 迭代 + 故事) -->
      <!-- CTA 按钮 -->
    </div>
  </div>
</div>
```

**Overlay 容器** (`.modal-overlay`):
- `position: fixed, inset: 0, z-index: 100`
- `display: flex, align-items: flex-start, justify-content: center`
- `padding: 40px 16px`
- `overflow-y: auto`
- 隐藏态: `.hidden` → `display: none`

**遮罩层** (`.modal-backdrop`):
- `position: fixed, inset: 0`
- `background-color: rgba(0, 0, 0, 0.6)`
- `backdrop-filter: blur(6px)`, `-webkit-backdrop-filter: blur(6px)`

**面板** (`.modal-panel`):
- `position: relative, width: 100%, max-width: 800px`
- 圆角: `var(--radius-xl)` (20px)
- 背景: `var(--color-bg-100)`
- 阴影: `var(--shadow-2xl)`
- `overflow: hidden, z-index: 1`

**关闭按钮** (`.modal-close-btn`):
- `position: absolute, top: 12px, right: 12px, z-index: 10`
- `display: flex, align-items: center, justify-content: center`
- 尺寸: 36x36px
- 圆角: `var(--radius-full)` (9999px)
- `border: none`
- 背景: `var(--color-bg-400)`
- 文字/图标色: `var(--color-text-700)`
- Hover: `background-color: var(--color-bg-500)`
- 过渡: `background-color 0.15s ease`

**大图区域** (`.modal-image-section`):
- `width: 100%, aspect-ratio: 16/7` (mobile: 16/9)
- `overflow: hidden`
- 背景: `var(--color-bg-200)`

**信息区** (`.modal-content-body`):
- 内边距: `24px 28px 32px` (mobile: `20px 18px 28px`)

**标题行**:
- Flex 布局, `align-items: center, gap: 12px, flex-wrap`
- H2: `font-size: 20px sm:24px, font-weight: 700, color: var(--color-text-900), truncate, min-width: 0`
- 状态标签: `shrink-0`

**描述**:
- 字号: 14px, `color: var(--color-text-500)`, `line-height: 1.6`, `margin-bottom: 8px`

**创建时间**:
- Flex 布局, `align-items: center, gap: 8px`
- 字号: 12px, `color: var(--color-text-300)`

**技术标签组**:
- Flex 布局, `flex-wrap, gap: 6px`, `margin-bottom: 24px`
- 预留 3 个 `.tech-tag` 元素（隐藏超出项）

**区块** (`.modal-section`):
- `margin-top: 20px, padding-top: 20px`
- `border-top: 1px solid var(--color-border-200)`

**区块标题** (`.modal-section-heading`):
- 字号: 15px, `font-weight: 600`, `color: var(--color-text-900)`
- `margin-bottom: 10px`

**Prompt 代码块** (`.prompt-block`):
- 内边距: `14px 18px`
- 圆角: `var(--radius-md)` (12px)
- 背景: `var(--color-bg-50)`
- 边框: `1px solid var(--color-border-300)`

**Prompt 标签** (`.prompt-label`):
- `display: block`
- 字号: 11px, `font-family: var(--font-mono)`, `color: var(--color-text-400)`
- `text-transform: uppercase`, `letter-spacing: 0.05em`
- `margin-bottom: 8px`

**Prompt 代码**:
- `font-family: var(--font-mono)`, `font-size: 13px`
- `color: var(--color-text-700)`, `line-height: 1.6`, `word-break: break-word`

**功能列表** (`.feature-list`):
- `list-style: none, padding: 0, margin: 0`
- Flex 纵向布局, `flex-direction: column, gap: 6px`
- 每项 (li):
  - 字号: 14px, `color: var(--color-text-600)`, `line-height: 1.6`
  - `padding-left: 18px, position: relative`
  - 左侧 6px 品牌色圆点 (`::before` 伪元素)
    - `content: ''`, 绝对定位 `left: 0, top: 9px`
    - `width: 6px, height: 6px`
    - `border-radius: var(--radius-full)`
    - `background-color: var(--color-brand-500)`
- 预留 4 个 `<li>` 元素（隐藏超出项）

**AI 工具 + 迭代行**:
- Flex 布局, `align-items: center, gap: 12px, flex-wrap`
- 标签文字: 字号: 12px, `color: var(--color-text-400)`
- 值: `.tech-tag` 样式

**构建故事段落**:
- `color: var(--color-text-600)`, `line-height: 1.8`

**CTA 按钮** (`.modal-cta-btn`):
- `display: inline-flex, align-items: center, justify-content: center`
- 高度: 40px, padding: `0 24px`, `margin-top: 24px`
- 圆角: `var(--radius-sm)` (8px)
- 背景: `var(--color-brand-500)`
- 文字色: `var(--color-dark-primary-foreground)`
- 字号: 14px, 字重: 500
- `text-decoration: none, white-space: nowrap`
- Hover: `background-color: var(--color-brand-600)`
- 过渡: `background-color 0.15s ease`
- `target="_blank", rel="noopener noreferrer"`

**交互行为**:
- 点击背景 (`.modal-backdrop`) 或关闭按钮关闭
- ESC 键关闭
- 打开时 `document.body.style.overflow = 'hidden'`
- 关闭时恢复 `document.body.style.overflow = ''`

**Mobile 适配** (<640px):
```css
.modal-overlay {
  padding: 16px 0;
  align-items: flex-end;
}
.modal-panel {
  max-width: 100%;
  border-radius: var(--radius-xl) var(--radius-xl) 0 0;
  max-height: 90vh;
  overflow-y: auto;
}
.modal-content-body {
  padding: 20px 18px 28px;
}
.modal-image-section {
  aspect-ratio: 16 / 9;
}
```

---

### 6.6 水墨涟漪动效 (Ink Ripple Canvas)

**容器**: `<canvas id="ink-canvas">`，位于 `#hero-section` 内
- 绝对定位覆盖整个 Hero section: `position: absolute, top: 0, left: 0, width: 100%, height: 100%`
- z-index: 1, `pointer-events: none` (不拦截鼠标事件)
- CSS 尺寸 100%x100%，Canvas 像素分辨率按 `devicePixelRatio` 缩放（上限 2x）

**三层视觉效果**:

| 层 | 类型 | 视觉描述 | 初始尺寸 | 最大尺寸 | 生命周期 | 颜色概率分布 |
|----|------|---------|---------|---------|---------|-------------|
| 墨迹粒子 | `trail` | 不规则半透明墨点 (8 段多边形) | 2~5px | +8~18px (扩散) | 2000~4000ms | 60% 主墨色, 25% 次墨色, 15% 雾色 |
| 涟漪环 | `ripple` | 同心圆环向外扩散 | 2px | 80~150px | 1500~2500ms | 100% 主墨色 |
| 墨雾 | `mist` | 大面积径向渐变云雾 | 200~400px | 不变 | 3000~5000ms | 100% 雾色 |

**颜色 RGB 分量** (Canvas JS 常量):
- 主墨色 `INK_PRIMARY`: `[217, 119, 87]` — 对应 `#d97757` (brand-500)
- 次墨色 `INK_SECONDARY`: `[176, 104, 63]` — 对应 `#b0683f` (brand-400)
- 辅助雾色 `INK_MIST`: `[142, 87, 64]` — 对应 `#8a5740` (brand-300)

**粒子生成参数**:

墨迹粒子 (`createTrailParticle`):
- 扩散角度: 随机 0~2PI
- 扩散距离: `Math.random() * Math.min(speed * 0.4, 30)`
- 初始半径: `rand(2, 5)`
- 最大半径: `baseR + rand(8, 18)`
- 初始透明度: `rand(0.3, 0.7)`
- 形状: 8 段多边形，奇偶段交替 jitter (0.7~1.3 倍半径)
- 扩散缓动: `1 - (1 - progress)^3` (ease-out cubic)

涟漪环 (`createRipple`):
- 初始半径: 2px
- 最大半径: `rand(80, 150)`
- 初始透明度: 0.5
- 扩展速度: `rand(60, 120)` px/s
- 线宽: `max(0.5, 2 - 1.5 * progress)` (从 2px 线性减至 0.5px)

墨雾 (`createMist`):
- 偏移: `x/y + rand(-60, 60)`
- 初始透明度: `rand(0.03, 0.08)`
- 渐变: 中心 0.6 透明度 → 边缘 0 透明度
- 淡入: 前 20% 生命周期线性淡入
- 淡出: 后 80% 生命周期线性淡出

**鼠标交互参数**:
- 追踪范围: 仅 `#hero-section` 内 (`getBoundingClientRect()` 计算)
- `mousemove`:
  - 速度计算: `sqrt(dx^2 + dy^2)`
  - 速度阈值: >1px 才触发
  - 粒子数量: `floor(max(1, speed * 0.15))`，上限 6
  - 涟漪间距: 每 80~120px 累积路径长度触发一次
  - 墨雾概率: 每帧 3%
- `mouseenter`:
  - 触发 4 个欢迎涟漪，间隔 120ms
  - 涟漪偏移: `x/y + rand(-40, 40) / rand(-30, 30)`
  - 涟漪透明度: 0.35 (比常规低)
  - 最大半径: `rand(60, 120)` (比常规小)
- `mouseleave`: 剩余粒子自然消散完毕

**动画循环**:
- 使用 `requestAnimationFrame`
- delta-time 模式: `dt = min(timestamp - lastTime, 50)` (上限 50ms 防跳帧)
- 每帧清空整个 Canvas
- 绘制后剔除生命周期结束的粒子 (`alpha < 0.005` 或 `progress >= 1`)
- 无活跃粒子时停止循环 (`animId = null`)
- `mousemove` / `mouseenter` 事件重新启动循环

**性能约束**:
- 最大活跃粒子数: 300 (`MAX_PARTICLES`)
- 超限时 `shift()` 移除最老的粒子
- `devicePixelRatio` 上限 2（避免超高 DPI 设备性能问题）
- `prefers-reduced-motion`: Canvas 直接 `display: none`，完全跳过初始化

---

## 7. 交互规范

### 7.1 分类筛选
- 点击分类标签 → 当前标签添加 `.active` 类 → 卡片按 `data-category` 属性筛选
- 不匹配的卡片添加 `.card-hidden` 类 → `display: none`
- 搜索与分类同时生效（取交集）
- Desktop 和 Mobile 分类标签状态同步（遍历所有 `.category-pill` 元素）
- Mobile: 选择分类后自动关闭菜单

### 7.2 搜索
- 实时输入匹配（`input` 事件）
- 匹配范围: `data-name` 和 `data-desc` 属性（大小写不敏感）
- Desktop 和 Mobile 搜索框值同步
- 与分类筛选叠加使用

### 7.3 深浅主题切换
- 点击切换按钮 → `<html>` class 在 `dark` / `light` 间切换
- 自动存储偏好到 `localStorage('toolbox-theme')`
- 页面加载时读取存储值，无存储则默认 `dark`
- Light 模式下: 背景色与文字色互反转，阴影 alpha 降低

### 7.4 模态浮层
- 打开: 点击 `data-dom-id="detail-N"` → 从 `toolData[N-1]` 填充数据 → 移除 `.hidden` → 锁定 body 滚动
- 关闭: 点击 X 按钮 / 点击 backdrop / 按 ESC
- 数据填充方式: 直接 `textContent` / `src` / `className` 赋值（非 innerHTML）

### 7.5 卡片 Hover
- 卡片整体: `translateY(-2px)` + `box-shadow: var(--shadow-lg)`，过渡 `0.2s ease`
- 预览图: `transform: scale(1.03)`，过渡 `0.3s ease`
- Overlay: `opacity: 0 → 1`，过渡 `0.2s ease`

---

## 8. 动画与过渡规范

### 8.1 CSS 过渡时长

| 组件 | 属性 | 时长 | 缓动函数 |
|------|------|------|---------|
| 分类标签 | background-color, color, border-color | 0.15s | ease |
| 搜索输入框 | border-color, box-shadow | 0.15s | ease |
| 卡片整体 | box-shadow, transform | 0.2s | ease |
| 卡片预览图 | transform | 0.3s | ease |
| Overlay | opacity | 0.2s | ease |
| Overlay 按钮 | background-color | 0.15s | ease |
| 关闭按钮 | background-color | 0.15s | ease |
| CTA 按钮 | background-color | 0.15s | ease |

### 8.2 Canvas 动画缓动

| 效果 | 缓动函数 | 说明 |
|------|---------|------|
| 粒子扩散 | `1 - (1 - progress)^3` | ease-out cubic |
| 粒子透明度衰减 | `opacity * (1 - progress)` | 线性衰减 |
| 涟漪环扩散 | 同粒子 | ease-out cubic |
| 涟漪线宽衰减 | `max(0.5, 2 - 1.5 * progress)` | 线性衰减 |
| 墨雾淡入 | `progress / 0.2` (前 20%) | 线性 |
| 墨雾淡出 | `1 - ((progress - 0.2) / 0.8)` (后 80%) | 线性 |

### 8.3 减弱动效

- Canvas: `prefers-reduced-motion: reduce` → Canvas `display: none`，完全禁用
- CSS: 所有交互过渡使用 CSS `transition` 属性，浏览器可统一降级

---

## 9. 响应式断点

| 断点 | Tailwind 前缀 | 范围 | 导航 | 卡片网格 | 模态 |
|------|--------------|------|------|---------|------|
| Mobile S | 默认 | < 640px | 汉堡菜单, 搜索图标 | 1 列 | 底部抽屉 |
| Mobile L | `sm:` | 640px ~ 767px | 同 Mobile S | 2 列 | 居中面板 |
| Desktop | `md:` | >= 768px | 标签展开, 搜索框展开 | 3~4 列 (auto-fill) | 居中面板 |
| Wide | `lg:` | >= 1024px | 同 Desktop | 同 Desktop | 同 Desktop |

### Mobile 特殊处理
- 导航高度: 56px (默认) → 64px (sm+)
- Hero 内边距: `py-16` → `py-20 sm` → `py-28 lg`
- 搜索框: 收起为图标 (sm:hidden)，点击展开下拉搜索栏 (`#mobile-search-bar`)
- 分类标签: 收入汉堡下拉菜单 (`#mobile-menu`)，同样水平排列可滚动
- 模态面板: 从底部滑入 (`align-items: flex-end`)，上方圆角下方直角，最大高度 90vh

---

## 10. CSS 类名索引

| 类名 | 类型 | 用途 |
|------|------|------|
| `.search-input` | 元素 | 搜索输入框 |
| `.category-pill` | 元素 | 分类标签 |
| `.category-pill.active` | 状态 | 当前激活分类 |
| `.tool-grid` | 布局 | 卡片网格容器 |
| `.tool-card` | 元素 | 工具卡片 |
| `.tool-card.card-hidden` | 状态 | 筛选隐藏的卡片 |
| `.card-image-wrapper` | 布局 | 卡片图片容器 |
| `.card-preview-img` | 元素 | 卡片预览图 |
| `.card-overlay` | 覆盖层 | 卡片 hover 浮出层 |
| `.overlay-btn` | 元素 | Overlay 主按钮 |
| `.overlay-btn-secondary` | 修饰 | Overlay 次按钮 |
| `.card-body` | 布局 | 卡片信息区 |
| `.card-title` | 排版 | 卡片标题 |
| `.card-desc` | 排版 | 卡片描述 |
| `.tech-tag` | 元素 | 技术标签 |
| `.status-badge` | 元素 | 状态标签基础 |
| `.status-live` | 修饰 | "已上线" 状态 |
| `.status-dev` | 修饰 | "开发中" 状态 |
| `.status-exp` | 修饰 | "实验性" 状态 |
| `.status-arch` | 修饰 | "Archive" 状态 |
| `.modal-overlay` | 容器 | 模态全屏覆盖 |
| `.modal-overlay.hidden` | 状态 | 模态隐藏 |
| `.modal-backdrop` | 覆盖层 | 模态遮罩 |
| `.modal-panel` | 元素 | 模态内容面板 |
| `.modal-close-btn` | 元素 | 模态关闭按钮 |
| `.modal-image-section` | 布局 | 模态大图区 |
| `.modal-image` | 元素 | 模态大图 |
| `.modal-content-body` | 布局 | 模态信息区 |
| `.modal-section` | 布局 | 模态内容区块 |
| `.modal-section-heading` | 排版 | 模态区块标题 |
| `.prompt-block` | 元素 | Prompt 代码块 |
| `.prompt-label` | 排版 | Prompt 标签 |
| `.feature-list` | 布局 | 功能列表 |
| `.modal-cta-btn` | 元素 | 模态 CTA 按钮 |

---

## 11. 数据结构 (工具卡片)

每张工具卡片包含以下字段:

```
{
  name:       string   // 项目名称
  desc:       string   // 一句话简介
  category:   string   // 分类: Web应用 | 小工具 | Chrome插件 | 自动化脚本 | 实验性项目
  status:     string   // 状态: 已上线 | 开发中 | 实验性 | Archive
  image:      string   // 预览图路径 (../assets/xxx.jpg)
  tech:       string[] // 技术标签数组 (最多 3 项)
  prompt:     string   // 原始 Prompt
  aiTool:     string   // 使用的 AI 工具 (如 "Cursor + Claude")
  iterations: string   // 迭代轮数 (如 "12 轮")
  problem:    string   // 解决什么问题
  features:   string[] // 核心功能列表 (最多 4 项)
  story:      string   // 构建故事
}
```

### 状态→CSS 类映射

| 状态值 | CSS 类 |
|--------|--------|
| 已上线 | `status-live` |
| 开发中 | `status-dev` |
| 实验性 | `status-exp` |
| (其他/默认) | `status-arch` |

### 现有工具数据

| # | 名称 | 分类 | 状态 | 技术栈 | AI 工具 | 迭代 |
|---|------|------|------|--------|---------|------|
| 1 | AI Assistant Pro | Web应用 | 已上线 | React, TypeScript, Node.js | Cursor + Claude | 12 轮 |
| 2 | SmartSummarize | Chrome插件 | 已上线 | Chrome API, Vue 3, Tailwind | Cursor + GPT-4 | 8 轮 |
| 3 | AutoFlow Script | 自动化脚本 | 开发中 | Python, LangChain, FastAPI | TRAE + Copilot | 6 轮 |
| 4 | WriteFlow | Web应用 | 已上线 | Next.js, OpenAI API, PostgreSQL | ChatGPT + Cursor | 15 轮 |
| 5 | DataLens | 小工具 | 已上线 | Python, Plotly, Streamlit | TRAE | 5 轮 |
| 6 | NeuroCanvas | 实验性项目 | 实验性 | Python, PyTorch, Stable Diffusion | ChatGPT + Claude | 20 轮 |

---

## 12. 资源清单

| 资源 | 类型 | 来源 | 版本/说明 |
|------|------|------|----------|
| Tailwind CSS | CDN | `cdn.jsdelivr.net/npm/@tailwindcss/browser@4` | v4 (browser build) |
| Lucide Icons | CDN | `unpkg.com/lucide@1.7.0` | v1.7.0 |
| Newsreader | Google Fonts | serif 展示字体 | opsz 6..72, wght 200..800 |
| Poppins | Google Fonts | sans 正文字体 | wght 300,400,500,600,700 |
| Geist Mono | 系统回退 | monospace 代码字体 | 无 CDN 引入，依赖系统 |
| 6 张工具预览图 | 本地 assets | AI 生成产品截图 | .jpg 格式 |

### 使用的 Lucide 图标

| 图标名 | 用途 | 尺寸 |
|--------|------|------|
| `search` | 搜索框图标、移动搜索按钮 | 16x16 / 20x20 |
| `sun` | 主题切换 (Dark 模式下显示) | 20x20 |
| `moon` | 主题切换 (Light 模式下显示) | 20x20 |
| `menu` | 汉堡菜单按钮 (Mobile) | 20x20 |
| `x` | 模态关闭按钮 | 20x20 |

### Logo SVG

内联三层堆叠方块图标:
- 尺寸: 24x24px, viewBox `0 0 24 24`
- `fill="none"`, `stroke="currentColor"`, `stroke-width="2"`, `stroke-linecap="round"`, `stroke-linejoin="round"`
- 三条路径: 上层菱形 (`M12 2L2 7l10 5 10-5-10-5z`) + 中层 (`M2 17l10 5 10-5`) + 下层 (`M2 12l10 5 10-5`)

---

## 13. 无障碍要求

| 规则 | 实现 |
|------|------|
| `prefers-reduced-motion` | Canvas 动画完全禁用 (`display: none`) |
| 图片 alt 属性 | 每张 `<img>` 均有描述性 alt 文本 (如 "AI Assistant Pro 界面截图") |
| 按钮 aria-label | 搜索、主题切换、汉堡菜单、关闭模态均有 `aria-label` |
| 键盘导航 | ESC 关闭模态 |
| 语义化标签 | `<nav>`, `<main>`, `<section>`, `<article>`, `<h1>`~`<h3>` |
| Focus 态 | 搜索输入框有可见 focus ring (`box-shadow: 0 0 0 2px rgba(217,119,87,0.15)`) |
| 外部链接安全 | 所有 `target="_blank"` 链接均带 `rel="noopener noreferrer"` |
| 文字截断 | 长标题使用 `truncate` class，描述使用 `line-clamp-2` |

---

## 14. 设计约束与编码规范

### 颜色约束
- HTML/CSS 中必须使用 CSS 自定义属性 (如 `var(--color-brand-500)`)，禁止硬编码色值
- Canvas JavaScript 中允许使用原始色值 RGB 分量 (如 `[217, 119, 87]`)，因为 Canvas API 不支持 CSS 变量
- Overlay 按钮中的 `rgba(255,255,255,...)` 值除外 (半透明白色无对应 token)

### 全局样式
- `box-sizing: border-box` 应用于所有元素
- body 背景: `var(--color-bg-50)`, 文字: `var(--color-text-900)`, 字体: `var(--font-sans)`
- 字体平滑: `-webkit-font-smoothing: antialiased; -moz-osx-font-smoothing: grayscale`
- `margin: 0` on body

### JavaScript 规范
- 所有逻辑包裹在 IIFE 中 `(function() { ... })()`，避免全局污染
- 使用 `var` 声明变量 (非 let/const)
- DOM 查询优先使用 `getElementById`，批量操作使用 `querySelectorAll`
- 事件监听使用匿名函数，不具名绑定
- localStorage 操作包裹在 try-catch 中 (兼容隐私模式)
- Lucide 图标通过 `lucide.createIcons()` 统一初始化

### HTML 属性规范
- 卡片 `data-category`, `data-name`, `data-desc` 用于筛选和搜索
- 模态按钮 `data-dom-id="detail-N"` 用于关联工具数据索引
- 第一张卡片图片 `loading="eager"`，其余 `loading="lazy"`

---

## 15. 文件结构

```
ai-toolbox-showcase/
  ai-toolbox-showcase.design    — Canvas 项目元数据
  ai-toolbox-design-spec.md     — 本设计规范文档
  orchestration-summary.json    — 构建摘要
  validation-report.json         — 验证报告
  pages/
    index.html                  — 基础页面 (含终端动画)
    index-ink-ripple.html       — 当前主页面 (水墨涟漪动效, 无终端)
  assets/
    tool-web-app-screenshot.jpg          — AI Assistant Pro 截图
    tool-chrome-extension-screenshot.jpg — SmartSummarize 截图
    tool-automation-script-screenshot.jpg — AutoFlow Script 截图
    tool-ai-writer-screenshot.jpg       — WriteFlow 截图
    tool-data-viz-screenshot.jpg       — DataLens 截图
    tool-experimental-screenshot.jpg    — NeuroCanvas 截图
```
