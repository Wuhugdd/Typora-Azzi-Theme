# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is the Typora themes directory (`%APPDATA%\Typora\themes`). It contains CSS themes for the Typora Markdown editor. Themes are pure CSS files that style the editor's preview and source modes using Typora's CSS class structure (`#write`, `.md-heading`, `.md-fences`, etc.).

## Architecture

**Theme structure pattern:**
- Each theme has a main `.css` file at the root (e.g., `claude.css`) and an optional subfolder for fonts/assets (e.g., `claude-fonts/`)
- Themes use `@import` for modular CSS (e.g., `happysimple.css` imports `happysimple/source/happysimple-set.css`)
- Fonts are declared via `@font-face` pointing to local files in the theme's subfolder
- CSS variables in `:root` blocks control colors, fonts, spacing — these are the primary customization points

**Key Typora CSS selectors:**
- `#write` — main content area
- `h1`–`h6` / `.md-heading` — headings
- `.md-fences` / `.code-block` — code blocks
- `#typora-source` — source code mode
- `#sidebar` — file tree sidebar

**Theme categories in this directory:**
- Custom: `azzi.css` (Azzi), `claude.css`, `claude-dark.css`, `azzi-dark.css`
- Community: `happysimple.css`
- Resource folders: `azzi/` (Azzi 源文件), `claude-fonts/`, `happysimple/`, `github/`

## Development

**Applying a theme:** In Typora, go to Preferences → Appearance → Open Theme Folder, then place the `.css` file here. Select it from Preferences → Appearance.

**Testing changes:** Edit the `.css` file and save — Typora hot-reloads themes on save.

**Font management:** Declare `@font-face` in the theme CSS, reference via CSS variable or `font-family`. Use `font-display: swap` to avoid layout shifts.

**Common variables to customize (in `:root`):**
- `--bg-color`, `--side-bar-bg-color` — background colors
- `--text-color`, `--control-text-color` — text colors
- `--heading-color` — heading text
- Code block fonts and colors via `.code-block` or `.md-fences`

## Claude theme specifics

`claude.css` (light) and `claude-dark.css` use fonts from `claude-fonts/`:
- Anthropic Serif Web Text (headings)
- Anthropic Sans Web Text (body)
- Anthropic Mono Variable (code)
- Noto Serif SC (CJK)
- Noto Sans (CJK)
- UnifrakturMaguntia (decorative)

The two files share identical font declarations; differences are in color variables and the `html`/`body` blocks.

## Azzi theme specifics

`azzi.css` 以紫色为主色调，采用 Claude 的设计理念：

**文件结构（仿 Happysimple 模块化）：**
```
azzi.css                      ← 入口：@import + 变量覆盖（~40行）
azzi/source/
├── azzi-set.css               ← 主样式（~2100行，全CSS规则）
├── azzi-fonts.css             ← Anthropic 字体声明
├── (复用) happysimple/source/font/fonts.css   ← 中文字体
└── (复用) happysimple/source/icon/iconfont.css ← 图标字体
```

**自定义方式：** 只需编辑 `azzi.css` 中的 `:root` 变量即可改配色/字体，无需动 `azzi-set.css`。

**配色方案：**
- 背景 `#f8f6ff`（浅紫调白）、强调色 `#7C5CFC`（紫色）
- 文件夹图标从深到浅：`#7C5CFC` → `#9B7DFF` → `#b8a5e8` → `#c8bbee`
- 所有交互色（选中、高亮、光标、链接悬停）统一为紫色

**来自 Claude 的设计理念：**
- 浮动侧边栏（15px 圆角 + 紫调阴影 + 毛玻璃）
- 胶囊式顶栏切换器（带滑动高光动画）
- 药丸形浮动底栏（66px 圆角）
- 右键菜单毛玻璃入场动画（`azzi-in`）
- 文件树展开滑入动画（`treeItemIn`，10 项递进延迟）
- 大纲树状连线（紫色 L 型 + I 型连线）
- 设置界面完整样式（pane-group、nav-group-item、export-detail）
- YAML 前置块纸张纹理（紫色调）

**标题层级设计：**
- H1：1.5rem，左边 3px 紫色竖线（非图标）
- H2：1.25rem，底部 2px 半透明紫色下划线
- H3：1.1rem，紫色文字色
- H4-H6：渐小字号，保持 Claude 简洁风格
