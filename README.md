# Azzi Theme for Typora 🎀

> 为虚拟主播 **阿梓从小就很可爱** 而生的 Typora 主题

基于 [Typora-theme-jiaran](https://github.com/q19980722/Typora-theme-jiaran) 的架构设计，融合 Claude 界面的优雅交互与棉花糖配色灵感，打造的一款紫色系 Markdown 写作主题。

## ✨ 特性

- **棉花糖配色** — 灵感来源于全城系列棉花糖配色球鞋，紫 → 蓝 → 灰柔和渐变
- **Happysimple 多彩内容** — 标题多色层级、彩色引用块（info/warn/danger/success）、文字特效
- **Claude 优雅界面** — 浮动侧边栏、胶囊顶栏切换器、药丸底栏、毛玻璃右键菜单、文件树展开动画
- **macOS 风格代码块** — 三圆点顶栏 + VS Code Dark+ 语法高亮 + 右上角语言标签
- **科研排版** — 三线表、加大加粗标题层级、楷体引用、宋体正文、1.8 倍行高
- **右下角阿梓** — 编辑区右下角常驻阿梓小人插图

## 📁 文件结构

```
azzi.css                    ← 入口文件（变量覆盖）
azzi/
└── source/
    ├── azzi-set.css         ← 主样式（2180 行）
    ├── azzi-fonts.css       ← Anthropic 字体声明
    └── image/
        └── img-1.png        ← 阿梓小人
```

## 🚀 安装

1. 打开 Typora → 偏好设置 → 外观 → 打开主题文件夹
2. 将 `azzi.css` 和 `azzi/` 文件夹复制到主题文件夹
3. 重启 Typora，在主题菜单中选择 **Azzi**

## 🎨 自定义

编辑 `azzi.css` 中的 `:root` 变量即可修改配色：

```css
:root {
    --bg-color: #f3f0f9;       /* 界面底色 */
    --LOGO-color: #7c6ddb;     /* 主强调色 */
    --font-serif: ...;          /* 衬线字体 */
    --font-sans: ...;           /* 无衬线字体 */
}
```

## 📷 截图

![azzi](https://gitee.com/wuhu_gdd/typora-image-bed/raw/master/img/azzi.png)

## 🙏 致谢

- [Typora-theme-jiaran](https://github.com/q19980722/Typora-theme-jiaran) — 主题架构参考
- Claude Desktop 设计团队 — 界面交互灵感
- **阿梓从小就很可爱** — 配色的灵魂 ❤️

## 📄 License

MIT
