# AI ToolBox - 设计规范文档

> 基于 Claude Design System 构建，版本 0 | 更新日期：2026-07-25

---

## 1. 项目概览

| 属性 | 值 |
|------|-----|
| 项目名称 | AI ToolBox |
| 页面类型 | 工具集展示站 |
| 设计系统 | Claude (Built-in) |
| 设备适配 | 桌面优先，响应式 |
| 主题模式 | 深色 / 浅色双主题 |
| 页面文件 | `pages/index-ink-ripple.html` |

### 1.1 页面结构

页面由三大区域组成：

1. **顶部导航栏 (Sticky Nav)** — 固定吸顶，包含 Logo、分类筛选、搜索框、主题切换
2. **Hero 区域** — 标题 + 副标题 + 水墨涟漪 Canvas 动效
3. **工具卡片网格 (Tool Card Grid)** — 6 张产品卡片，支持分类筛选与搜索
4. **详情弹窗 (Detail Modal)** — 点击卡片"查看详情"触发的模态面板

---

## 2. 色彩系统

### 2.1 品牌色 (Brand)

| Token | 深色模式 | 浅色模式 | 用途 |
|-------|---------|---------|------|
| `--color-brand-500` | `#d97757` | `#d97757` (映射为 `--color-dark-primary: #b0683f`) | 主色调，按钮、选中态、强调 |
| `--color-brand-400` | `#b0683f` | — | 次级品牌色，实验性状态 |
| `--color-brand-300` | `#8a5740` | — | 墨韵粒子色 |
| `--color-brand-600` | `#e08d6f` | — | 按钮悬停态 |
| `--color-brand-700` | `#e8a98f` | — | 最亮品牌色 |

**品牌色语义映射：**

```
深色模式: --color-dark-primary: #d97757
浅色模式: --color-dark-primary: #b0683f
```

### 2.2 背景色 (Background)

| Token | 深色模式 | 浅色模式 | 用途 |
|-------|---------|---------|------|
| `--color-bg-50` | `#1b1b19` | `#faf9f5` | 页面主背景 |
| `--color-bg-100` | `#262624` | `#f1f1ef` | 渐变底色、Modal 背景 |
| `--color-bg-200` | `#2c2c2b` | `#e9e6dc` | 搜索框背景、图片占位 |
| `--color-bg-300` | `#30302e` | `#e0ddd3` | 悬停高亮 |
| `--color-bg-400` | `#3e3e38` | `#d0cdc3` | 技术标签背景、关闭按钮 |
| `--color-bg-500` | `#4a4a43` | `#b7b5a9` | 归档状态背景 |
| `--color-bg-700` | `#6e6d68` | `#908e84` | — |
| `--color-bg-800` | `#908e84` | `#6e6d68` | — |

### 2.3 文字色 (Text)

| Token | 深色模式 | 浅色模式 | 用途 |
|-------|---------|---------|------|
| `--color-text-900` | `#faf9f5` | `#1b1b19` | 主标题、卡片标题 |
| `--color-text-800` | `#f1f1ef` | `#2c2c2b` | — |
| `--color-text-700` | `#d8d6cd` | `#46443b` | 按钮悬停文字、Modal 正文 |
| `--color-text-600` | `#c3c0b6` | `#6e6d68` | 技术标签文字、特性列表 |
| `--color-text-500` | `#b7b5a9` | `#908e84` | 副标题、卡片描述 |
| `--color-text-400` | `#908e84` | `#b7b5a9` | 图标色、次要信息 |
| `--color-text-300` | `#6e6d68` | `#d0cdc3` | 创建时间 |
| `--color-text-200` | `#46443b` | `#e0ddd3` | — |
| `--color-text-100` | `#2c2c2b` | `#f1f1ef` | — |
| `--color-text-50` | `#1b1b19` | `#faf9f5` | — |

### 2.4 边框色 (Border)

| Token | 深色模式 | 浅色模式 | 用途 |
|-------|---------|---------|------|
| `--color-border-200` | `#343430` | `#e0ddd3` | 导航栏底边框、Modal 分隔线 |
| `--color-border-300` | `#3e3e38` | `#3e3e38`(不变) | 卡片边框、分类 Pill 边框 |
| `--color-border-400` | `#4a4a43` | `#3e3e38` | — |
| `--color-border-500` | `#52514a` | `#4a4a43` | — |
| `--color-border-600` | `#6e6d68` | `#52514a` | — |
| `--color-border-700` | `#908e84` | `#6e6d68` | — |

### 2.5 状态色 (Status)

| Token | 深色模式 | 浅色模式 | 用途 |
|-------|---------|---------|------|
| `--color-success-500` | `#8ca06f` | — | "已上线"状态徽章 |
| `--color-success-700` | `#bccaa8` | — | — |
| `--color-error-500` | `#ef4444` | `#dc2626` | 错误/危险状态 |

### 2.6 语义色 (Semantic)

| Token | 深色模式 | 浅色模式 | 用途 |
|-------|---------|---------|------|
| `--color-dark-card` | `#2c2c2b` | `#ffffff` | 卡片背景 |
| `--color-dark-card-foreground` | `#faf9f5` | `#1b1b19` | 卡片前景文字 |
| `--color-dark-muted-foreground` | `#b7b5a9` | `#6e6d68` | 弱化文字 |
| `--color-dark-secondary` | `#e9e6dc` | `#46443b` | 次要文字 |
| `--color-dark-secondary-foreground` | `#30302e` | `#faf9f5` | 次要前景 |
| `--color-dark-accent` | `#1a1915` | `#e9e6dc` | 强调区域 |
| `--color-dark-primary-foreground` | `#141413` | `#faf9f5` | 主按钮文字色 |
| `--color-dark-destructive` | `#ef4444` | `#dc2626` | 破坏性操作 |

---

## 3. 字体系统

### 3.1 字体栈

| Token | 字体栈 | 用途 |
|-------|--------|------|
| `--font-display` | `Newsreader, Georgia, ui-serif, serif` | Hero 大标题 |
| `--font-sans` | `Poppins, ui-sans-serif, system-ui, sans-serif` | 正文、UI 元素、按钮、标签 |
| `--font-mono` | `Geist Mono, ui-monospace, monospace` | 代码块、Prompt 引用 |

### 3.2 字号规范

| 场景 | 字号 | 字重 | 行高 | 字体 |
|------|------|------|------|------|
| Hero 标题 (H1) | `clamp(36px, 5vw, 64px)` | 500 | 1.2 | Newsreader |
| 副标题 | `text-base` / `text-lg` (16/18px) | 400 | — | Poppins |
| 卡片标题 (H3) | 16px | 600 | — | Poppins |
| 卡片描述 | 13px | 400 | 1.5 | Poppins |
| Modal 标题 (H2) | `text-xl` / `text-2xl` (20/24px) | 700 | — | Poppins |
| Modal 段落标题 | 15px | 600 | — | Poppins |
| Modal 正文 | 14px | 400 | 1.6–1.8 | Poppins |
| 特性列表项 | 14px | 400 | 1.6 | Poppins |
| 搜索输入框 | 14px | 400 | — | Poppins |
| 分类 Pill | 13px | 400 | — | Poppins |
| 技术标签 | 12px | 400 | — | Poppins |
| 状态徽章 | 12px | 500 | — | Poppins |
| Prompt 标签 | 11px | 400 | — | Geist Mono |
| Prompt 代码 | 13px | 400 | 1.6 | Geist Mono |
| 覆盖层按钮 | 13px | 500 | — | Poppins |
| Logo 文字 | `text-base` / `text-lg` | 600 | — | Poppins |

### 3.3 文字处理规则

- Hero 标题: `text-wrap: balance; word-break: keep-all; overflow-wrap: break-word;`
- 卡片描述: `line-clamp-2` (最多两行截断)
- 卡片标题: `truncate` (单行截断)
- Modal 标题: `truncate` (单行截断)

---

## 4. 圆角系统

| Token | 值 | 用途 |
|-------|-----|------|
| `--radius-sm` | 8px | 覆盖层按钮、技术标签、状态徽章 |
| `--radius-md` | 12px | Prompt 代码块 |
| `--radius-lg` | 16px | 工具卡片 |
| `--radius-xl` | 20px | Modal 面板 |
| `--radius-2xl` | 24px | — |
| `--radius-full` | 9999px | 搜索框、分类 Pill、关闭按钮、特性列表圆点 |

---

## 5. 阴影系统

| Token | 深色模式 | 浅色模式 | 用途 |
|-------|---------|---------|------|
| `--shadow-sm` | `0 1px 3px 0 rgba(0,0,0,0.1), 0 1px 2px -1px rgba(0,0,0,0.1)` | `0 1px 3px 0 rgba(0,0,0,0.06), ...` | — |
| `--shadow-md` | 同上偏移 | 0.06 透明度 | — |
| `--shadow-lg` | 同上偏移 | 0.06 透明度 | 卡片悬停 |
| `--shadow-xl` | 同上偏移 | 0.06 透明度 | — |
| `--shadow-2xl` | `0 1px 3px 0 rgba(0,0,0,0.25)` | `0 1px 3px 0 rgba(0,0,0,0.12)` | Modal 面板 |

---

## 6. 间距系统

### 6.1 全局容器

| 属性 | 值 |
|------|-----|
| 最大内容宽度 | `max-w-7xl` (1280px) |
| 水平内边距 | `px-4 sm:px-6 lg:px-8` (16/24/32px) |
| 垂直内边距 (Hero) | `py-16 sm:py-20 lg:py-28` (64/80/112px) |
| 垂直内边距 (Grid) | `py-12 sm:py-16 lg:py-20` (48/64/80px) |

### 6.2 导航栏

| 属性 | 值 |
|------|-----|
| 高度 | `h-14 sm:h-16` (56/64px) |
| 元素间距 | `gap-3 sm:gap-4` (12/16px) |
| Logo 内部间距 | `gap-2` (8px) |
| 分类 Pill 内部间距 | `gap-2` (8px) |
| 右侧控件内部间距 | `gap-1 sm:gap-2` (4/8px) |

### 6.3 卡片

| 属性 | 值 |
|------|-----|
| 网格间距 | `gap: 24px` |
| 卡片内容区内边距 | `padding: 16px 18px 18px` |
| 标题与描述间距 | `margin-top: 6px` |
| 技术标签容器上间距 | `margin-top: 12px` |
| 技术标签间距 | `gap: 6px` (1.5 = 6px) |

### 6.4 Modal

| 属性 | 值 |
|------|-----|
| 面板内容区内边距 | `padding: 24px 28px 32px` (移动端: `20px 18px 28px`) |
| 区域间距 | `margin-top: 20px; padding-top: 20px` |
| 区域标题底部间距 | `margin-bottom: 10px` |
| Prompt 代码块内边距 | `padding: 14px 18px` |
| Prompt 标签底部间距 | `margin-bottom: 8px` |
| CTA 按钮上间距 | `margin-top: 24px` |
| 特性列表项间距 | `gap: 6px` |

---

## 7. 组件规范

### 7.1 导航栏 (Sticky Navigation)

**定位与布局：**
- `position: sticky; top: 0; z-index: 50`
- 背景色: `var(--color-bg-50)`（带毛玻璃效果）
- 底边框: `1px solid var(--color-border-200)`
- 内部 Flex 布局: `align-items: center; justify-content: start`（左对齐）
- 元素间距: `gap: 12px` (移动端) / `gap: 16px` (桌面端)
- 布局结构: Logo → 分类 Pill → 右侧控件，全部左对齐流动

**Logo 区域：**
- SVG 图标: 24x24px, `stroke: var(--color-brand-500)`, `stroke-width: 2`
- 文字: `font-sans`, `font-semibold`, `color: var(--color-text-900)`

**搜索框 (`.search-input`)：**
- 宽度: 200px
- 高度: 36px
- 圆角: `var(--radius-full)` (胶囊形)
- 边框: `1px solid var(--color-border-300)`
- 背景: `var(--color-bg-100)`
- 左侧图标: Lucide `search`, 16x16px, `color: var(--color-text-400)`
- 图标定位: `absolute; left: 12px; top: 50%; transform: translateY(-50%)`
- 文字内边距: `0 12px 0 36px`
- Focus 态: 边框色 `var(--color-brand-500)`, 外发光 `0 0 0 2px rgba(217, 119, 87, 0.15)`
- 过渡: `transition: border-color 0.15s ease, box-shadow 0.15s ease`

**主题切换按钮 (`#theme-toggle`)：**
- 尺寸: `padding: 8px`, 圆角 `8px`
- 图标容器: 20x20px, `inline-flex` 居中
- Sun / Moon 图标: 20x20px, 绝对定位堆叠
- 过渡: `opacity 0.35s ease, transform 0.4s cubic-bezier(0.34, 1.56, 0.64, 1)`
- 深色模式: Moon 可见 (rotate 0, scale 1), Sun 隐藏 (rotate -90deg, scale 0)
- 浅色模式: Sun 可见 (rotate 90deg, scale 1), Moon 隐藏 (rotate -90deg, scale 0)
- 悬停态: 背景 `var(--color-bg-300)`, 文字 `var(--color-text-700)`
- 按压态: `scale(0.9)`
- 点击反馈: `scale(0.85)` → 150ms 后恢复

**分类筛选 Pill (`.category-pill`)：**
- 内边距: `6px 16px`
- 圆角: `var(--radius-full)` (胶囊形)
- 边框: `1px solid var(--color-border-200)`
- 背景: `transparent`
- 文字: `var(--color-text-500)`, 13px
- 悬停: 背景 `var(--color-bg-200)`, 文字 `var(--color-text-700)`
- 激活态: 背景 `var(--color-brand-500)`, 文字 `var(--color-dark-primary-foreground)`, 边框同色
- 过渡: `0.15s ease`

### 7.2 Hero 区域

**布局：**
- `position: relative; overflow: hidden`
- 背景: `linear-gradient(180deg, var(--color-bg-50) 0%, var(--color-bg-100) 100%)`
- 内容居中: `max-w-3xl mx-auto px-4 text-center`
- z-index: 2 (文字层在 Canvas 动效之上)

**装饰光晕：**
- 位置: 绝对定位，水平垂直居中
- 尺寸: 500x350px, `border-radius: 9999px`
- 颜色: `var(--color-brand-500)`
- 透明度: 0.05
- 模糊: `filter: blur(100px)`
- 交互: `pointer-events: none`

**标题 (H1)：**
- 字体: `var(--font-display)` (Newsreader)
- 字号: `clamp(36px, 5vw, 64px)` (响应式缩放)
- 字重: 500
- 行高: 1.2
- 颜色: `var(--color-text-900)`
- 文字处理: `text-wrap: balance; word-break: keep-all; overflow-wrap: break-word`

**副标题：**
- 字体: `var(--font-sans)` (Poppins)
- 字号: `text-base sm:text-lg` (16/18px)
- 颜色: `var(--color-text-500)`
- 最大宽度: 480px, 水平居中
- 上间距: `mt-4` (16px)

### 7.3 工具卡片 (`.tool-card`)

**卡片容器：**
- 圆角: `var(--radius-lg)` (16px)
- 边框: `1px solid var(--color-border-300)`
- 背景: `var(--color-dark-card)`
- 溢出: `overflow: hidden`
- 悬停效果: `box-shadow: var(--shadow-lg); transform: translateY(-2px)`
- 过渡: `box-shadow 0.2s ease, transform 0.2s ease`

**图片区域 (`.card-image-wrapper`)：**
- 宽高比: `aspect-ratio: 16 / 9`
- 溢出: `overflow: hidden`
- 背景: `var(--color-bg-200)` (图片加载占位)
- 图片: `object-fit: cover; width: 100%; height: 100%`
- 图片悬停: `transform: scale(1.03)` (0.3s ease)

**悬停覆盖层 (`.card-overlay`)：**
- 定位: `absolute; inset: 0`
- 布局: `flex; align-items: center; justify-content: center; gap: 12px`
- 背景: `rgba(0, 0, 0, 0.55)`
- 模糊: `backdrop-filter: blur(4px)`
- 默认: `opacity: 0`
- 悬停: `opacity: 1`
- 过渡: `opacity 0.2s ease`

**覆盖层主按钮 (`.overlay-btn`)：**
- 高度: 36px
- 内边距: `0 16px`
- 圆角: `var(--radius-sm)` (8px)
- 背景: `var(--color-brand-500)`
- 文字: `var(--color-dark-primary-foreground)`
- 字号: 13px, 字重: 500
- 悬停: `var(--color-brand-600)`

**覆盖层次要按钮 (`.overlay-btn-secondary`)：**
- 背景: `rgba(255, 255, 255, 0.15)`
- 文字: `rgba(255, 255, 255, 0.9)`
- 边框: `1px solid rgba(255, 255, 255, 0.25)`
- 悬停: `rgba(255, 255, 255, 0.25)`

**浅色图片适配 (`.overlay-btn-secondary.img-light`)：**
- 文字: `rgba(27, 27, 25, 0.9)`
- 背景: `rgba(27, 27, 25, 0.12)`
- 边框: `rgba(27, 27, 25, 0.22)`
- 悬停: `rgba(27, 27, 25, 0.2)`
- 亮度检测阈值: > 0.55 时触发 `img-light` 类

**卡片内容区 (`.card-body`)：**
- 内边距: `16px 18px 18px`
- 标题行: Flex 布局, `justify-content: space-between; gap: 8px`

**卡片标题 (`.card-title`)：**
- 字号: 16px, 字重: 600
- 颜色: `var(--color-text-900)`
- 截断: `truncate` (单行)

**卡片描述 (`.card-desc`)：**
- 字号: 13px
- 颜色: `var(--color-text-500)`
- 行高: 1.5
- 上间距: 6px
- 截断: `line-clamp-2`

### 7.4 技术标签 (`.tech-tag`)

- 高度: 24px
- 内边距: `0 10px`
- 圆角: `var(--radius-sm)` (8px)
- 背景: `var(--color-bg-400)`
- 文字: `var(--color-text-600)`, 12px
- 空白: `nowrap`

### 7.5 状态徽章 (`.status-badge`)

- 高度: 24px
- 内边距: `0 10px`
- 圆角: `var(--radius-sm)` (8px)
- 字号: 12px, 字重: 500

| 状态 | 类名 | 背景 | 文字 |
|------|------|------|------|
| 已上线 | `.status-live` | `var(--color-success-500)` | `var(--color-dark-primary-foreground)` |
| 开发中 | `.status-dev` | `var(--color-brand-500)` | `var(--color-dark-primary-foreground)` |
| 实验性 | `.status-exp` | `var(--color-brand-400)` | `var(--color-text-900)` |
| 归档 | `.status-arch` | `var(--color-bg-500)` | `var(--color-text-400)` |

### 7.6 详情弹窗 (Modal)

**遮罩层 (`.modal-overlay`)：**
- 定位: `fixed; inset: 0; z-index: 100`
- 布局: `flex; align-items: flex-start; justify-content: center`
- 内边距: `40px 16px`
- 溢出: `overflow-y: auto`

**背景蒙版 (`.modal-backdrop`)：**
- `fixed; inset: 0`
- 背景: `rgba(0, 0, 0, 0.6)`
- 模糊: `backdrop-filter: blur(6px)`

**面板 (`.modal-panel`)：**
- 最大宽度: 800px
- 圆角: `var(--radius-xl)` (20px)
- 背景: `var(--color-bg-100)`
- 阴影: `var(--shadow-2xl)`
- z-index: 1

**关闭按钮 (`.modal-close-btn`)：**
- 定位: `absolute; top: 12px; right: 12px; z-index: 10`
- 尺寸: 36x36px
- 圆角: `var(--radius-full)`
- 背景: `var(--color-bg-400)`
- 图标: Lucide `x`, 20x20px
- 悬停: `var(--color-bg-500)`

**图片区域 (`.modal-image-section`)：**
- 宽高比: `16 / 7` (移动端: `16 / 9`)
- 背景: `var(--color-bg-200)`
- 图片: `object-fit: cover`

**内容区域 (`.modal-content-body`)：**
- 内边距: `24px 28px 32px`

**区域分隔 (`.modal-section`)：**
- 上间距: 20px, 上内边距: 20px
- 顶边框: `1px solid var(--color-border-200)`

**区域标题 (`.modal-section-heading`)：**
- 字号: 15px, 字重: 600
- 颜色: `var(--color-text-900)`
- 底部间距: 10px

**Prompt 代码块 (`.prompt-block`)：**
- 内边距: `14px 18px`
- 圆角: `var(--radius-md)` (12px)
- 背景: `var(--color-bg-50)`
- 边框: `1px solid var(--color-border-300)`
- 标签: 11px, `var(--font-mono)`, `text-transform: uppercase`, `letter-spacing: 0.05em`
- 代码: 13px, `var(--font-mono)`, 行高 1.6

**特性列表 (`.feature-list`)：**
- 列表样式: `none`
- 布局: Flex 纵向, `gap: 6px`
- 列表项: 左内边距 18px, 相对定位
- 圆点: 6x6px, `border-radius: full`, `var(--color-brand-500)`, 绝对定位 `left: 0; top: 9px`

**CTA 按钮 (`.modal-cta-btn`)：**
- 高度: 40px
- 内边距: `0 24px`
- 圆角: `var(--radius-sm)` (8px)
- 背景: `var(--color-brand-500)`
- 文字: `var(--color-dark-primary-foreground)`
- 字号: 14px, 字重: 500
- 上间距: 24px
- 悬停: `var(--color-brand-600)`

**移动端适配 (max-width: 639px)：**
- 遮罩: `padding: 16px 0; align-items: flex-end`
- 面板: `max-width: 100%; border-radius: 20px 20px 0 0; max-height: 90vh; overflow-y: auto`
- 内容区内边距: `20px 18px 28px`
- 图片宽高比: `16 / 9`

---

## 8. 交互与动效

### 8.1 主题切换

- 持久化: `localStorage` key `toolbox-theme`
- 默认主题: 深色
- 切换方式: `<html>` 元素 `class` 在 `dark` / `light` 间切换
- CSS 变量通过 `html.light` 选择器覆盖

### 8.2 分类筛选

- 筛选逻辑: 卡片 `data-category` 属性与当前选中分类匹配
- "全部" 显示所有卡片
- 不匹配的卡片添加 `.card-hidden` → `display: none`
- 桌面端 Pill 与移动端 Pill 状态同步

### 8.3 搜索

- 搜索范围: 卡片 `data-name` 和 `data-desc` 属性
- 大小写不敏感
- 实时过滤 (input 事件)
- 桌面搜索框与移动端搜索框值同步
- 分类与搜索联合过滤 (AND 逻辑)

### 8.4 卡片悬停

- 卡片上移: `translateY(-2px)`, 0.2s ease
- 阴影增强: `var(--shadow-lg)`
- 图片微放大: `scale(1.03)`, 0.3s ease
- 覆盖层淡入: `opacity: 0 → 1`, 0.2s ease

### 8.5 图片亮度自适应

- 检测时机: 图片加载完成后 或 已缓存图片立即检测
- 检测方法: Canvas 采样 (20x20 缩略图), ITU-R BT.601 亮度公式
- 阈值: `luminance > 0.55` 时为浅色图片
- 效果: "在线体验"按钮添加 `.img-light` 类，文字变深色

### 8.6 Modal

- 打开: 移除 `.hidden`, 锁定 body 滚动
- 关闭方式: 点击关闭按钮 / 点击蒙版 / 按 Escape 键
- 数据源: JS 内置 `toolData` 数组 (6 个工具对象)

### 8.7 水墨涟漪动效 (Ink Ripple)

**技术实现：** Canvas 2D API, `requestAnimationFrame` 动画循环

**触发条件：**
- 鼠标进入 Hero 区域时触发欢迎涟漪 (`mouseenter`)
- 鼠标移动时根据速度生成拖尾粒子和涟漪 (`mousemove`)
- 尊重 `prefers-reduced-motion` 设置 (禁用时隐藏 Canvas)

**粒子类型：**

| 类型 | 视觉效果 | 生命周期 | 生成频率 |
|------|---------|---------|---------|
| Trail (拖尾) | 不规则墨点，8 段多边形 | 2000–4000ms | 速度 x 0.15 (最多 6 个/帧) |
| Ripple (涟漪) | 扩展圆环，线宽递减 | 1500–2500ms | 鼠标移动 80–120px 距离触发 |
| Mist (墨雾) | 径向渐变柔光团 | 3000–5000ms | 3% 概率/帧 |

**墨色配色：**

| 名称 | RGB | 使用概率 |
|------|-----|---------|
| Primary | `(217, 119, 87)` | 60% |
| Secondary | `(176, 104, 63)` | 25% |
| Mist | `(142, 87, 64)` | 15% |

**性能参数：**
- Canvas DPR: `min(devicePixelRatio, 2)` (限制最大 2 倍)
- 最大粒子数: 300
- 帧间隔上限: 50ms (防止大跳帧)
- 无粒子时停止动画循环 (释放资源)
- 欢迎涟漪: 鼠标进入时延迟 120ms 连续生成 4 个

**拖尾粒子参数：**
- 基础半径: 2–5px
- 最大半径: 基础半径 + 8–18px
- 初始透明度: 0.3–0.7
- 扩展速度: 4–10px/生命周期百分比
- 形状抖动: 0.7–1.3 (多边形顶点半径系数)

**涟漪参数：**
- 初始半径: 2px
- 最大半径: 80–150px
- 初始透明度: 0.5
- 扩展速度: 60–120px/生命周期百分比
- 初始线宽: 2px (递减至 0.5px)

**墨雾参数：**
- 半径: 200–400px
- 透明度: 0.03–0.08
- 偏移: 随机 -60 到 60px
- 渐变: 中心 0.6 → 边缘 0 透明度

---

## 9. 网格系统

### 9.1 工具卡片网格

```css
.tool-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 24px;
}
```

- 桌面端: 自动填充，每列最小 320px
- 移动端 (<768px): 单列 `grid-template-columns: 1fr`

### 9.2 响应式断点

| 断点 | 宽度范围 | 关键变化 |
|------|---------|---------|
| sm | >= 640px | 搜索框显示，Hero 间距增大 |
| md | >= 768px | 桌端分类 Pill 显示，移动菜单隐藏，网格多列 |
| lg | >= 1024px | 间距进一步增大 |

---

## 10. 图标系统

- 图标库: Lucide Icons v1.7.0
- 加载方式: `lucide.createIcons()` (声明式渲染)
- 使用方式: `<i data-lucide="icon-name" class="w-N h-N"></i>`

| 图标 | 尺寸 | 位置 | 颜色 |
|------|------|------|------|
| `layers` (三层堆叠) | 24x24 | Logo | `var(--color-brand-500)` |
| `search` | 16x16 | 搜索框内 | `var(--color-text-400)` |
| `search` | 20x20 | 移动端搜索按钮 | `var(--color-text-400)` |
| `sun` | 20x20 | 主题切换 | 同主题按钮 |
| `moon` | 20x20 | 主题切换 | 同主题按钮 |
| `menu` | 20x20 | 汉堡菜单 | `var(--color-text-400)` |
| `x` | 20x20 | Modal 关闭 | `var(--color-text-700)` |

---

## 11. 无障碍

- 图标按钮均设置 `aria-label`
- Modal 可通过 Escape 键关闭
- 移动端菜单和搜索栏可通过 `hidden` 类控制显示
- `prefers-reduced-motion` 时禁用 Canvas 动效
- 链接设置 `rel="noopener noreferrer"` 和 `target="_blank"`

---

## 12. 数据结构

### 12.1 工具数据 (toolData)

每个工具对象包含以下字段：

```javascript
{
  name: string,        // 工具名称
  desc: string,        // 简短描述
  category: string,    // 分类标签
  status: string,      // 状态: "已上线" | "开发中" | "实验性"
  image: string,       // 截图路径
  tech: string[],      // 技术栈 (最多 3 项)
  prompt: string,      // 构建 Prompt
  aiTool: string,      // 使用的 AI 工具
  iterations: string,  // 迭代轮数
  problem: string,     // 解决的问题
  features: string[],  // 核心功能 (最多 4 项)
  story: string        // 构建故事
}
```

### 12.2 卡片数据属性

| 属性 | 用途 |
|------|------|
| `data-category` | 分类筛选 |
| `data-name` | 搜索匹配 (工具名) |
| `data-desc` | 搜索匹配 (描述) |
| `data-dom-id` | Modal 数据绑定 (格式: `detail-N`) |

---

## 13. 文件结构

```
ai-toolbox-showcase/
├── ai-toolbox-showcase.design    # Canvas 项目元数据
├── design-spec.md                # 本设计规范文档
├── pages/
│   ├── index.html                # 原始页面
│   └── index-ink-ripple.html     # 当前活跃页面 (含水墨动效)
└── assets/
    ├── tool-web-app-screenshot.jpg         # 深色截图 (6张)
    ├── tool-chrome-extension-screenshot.jpg
    ├── tool-automation-script-screenshot.jpg
    ├── tool-ai-writer-screenshot.jpg
    ├── tool-data-viz-screenshot.jpg
    ├── tool-experimental-screenshot.jpg
    ├── tool-web-app-screenshot-light.jpg    # 浅色截图 (6张)
    ├── tool-chrome-extension-screenshot-light.jpg
    ├── tool-automation-script-screenshot-light.jpg
    ├── tool-ai-writer-screenshot-light.jpg
    ├── tool-data-viz-screenshot-light.jpg
    └── tool-experimental-screenshot-light.jpg
```

---

## 14. 外部依赖

| 依赖 | 版本 | 用途 | 加载方式 |
|------|------|------|---------|
| Tailwind CSS (Browser) | v4 | 原子化 CSS 工具类 | CDN `<script>` |
| Lucide Icons | v1.7.0 | 线性图标库 | CDN `<script>` |
| Google Fonts | — | Newsreader + Poppins 字体 | `<link>` preconnect |

---

## 15. 关键设计决策

1. **双主题架构**: 通过 CSS 自定义属性 + `html.light` 选择器实现，所有颜色均通过变量控制，无硬编码色值

2. **自适应按钮文字**: "在线体验"按钮通过 Canvas 采样检测图片亮度，自动在深色/浅色文字间切换，保证在深色和浅色截图上均有良好可读性

3. **水墨动效性能**: 使用粒子池上限 (300) + 无粒子时暂停循环 + DPR 限制 (max 2) 确保流畅运行

4. **卡片覆盖层设计**: 使用半透明黑色蒙版 + `backdrop-filter: blur(4px)` 确保按钮在任何图片色调下都清晰可读

5. **左对齐导航布局**: Logo、分类筛选、右侧控件统一左对齐，使用 `gap` 控制间距，适应不同内容宽度下的自然流动
