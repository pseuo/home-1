# LinkNest 链巢

一个轻量、响应式、易部署的个人引导页 / 链接聚合页开源项目。

LinkNest 适合用于搭建个人主页、站点导航页、项目入口页或个人服务聚合页。

项目基于原生 HTML、CSS 和少量 JavaScript 构建，无需复杂依赖，下载后即可修改和部署。

## 目录

- `index.html`：首页 / 个人引导页
- `latest.html`：最新动态页
- `about.html`：关于页面
- `data/latest.json`：最新动态数据源
- `css/style.css`：全站样式
- `image/icon.png`：站点图标
- `image/github.png`：GitHub 卡片图标

## 特性

- 轻量简洁：仅使用 HTML、CSS 和少量原生 JavaScript
- 响应式布局：适配桌面端、平板和移动端访问
- 链接聚合：集中展示个人站点、导航、图床、GitHub 等入口
- 动态区域：支持展示最新动态、关于页面或其他内容入口
- 动态数据：支持通过 JSON 文件配置最新动态内容
- SEO 友好：内置基础 `title`、`description`、Open Graph 和 Twitter Card 信息
- 易于部署：可部署到 GitHub Pages、Cloudflare Pages、Vercel、Netlify 或任意静态网站服务


## 项目结构

```text
linknest/
├── index.html        # 首页 / 个人引导页
├── latest.html       # 最新动态页面
├── about.html        # 关于页面
├── data/
│   └── latest.json   # 最新动态数据源
├── image/
│   └── icon.png      # 本地图标
├── css/
│   └── style.css     # 页面样式
└── README.md         # 项目说明
```

### 修改内容

主要修改 `index.html` 中的以下内容：

- 网站标题和 SEO 信息
- 头像、站点图标和封面图片
- 个人简介文案
- 链接卡片名称、描述和 URL
- 最新动态页、关于页面入口


如果你想更新动态内容，只需要修改：

```text
data/latest.json
```

其中 `posts` 数组里的每一项代表一条动态，支持以下字段：

- `tag`：分类标签
- `category`：内容分类
- `author`：作者名称
- `date`：日期或状态文本
- `title`：标题
- `summary`：正文摘要
- `image`：可选，封面图片地址
- `pinned`：可选，是否置顶
- `link`：可选，详情链接
- `external`：可选，是否外链打开

建议保留 `date` 的统一格式，便于后续按时间维护与排序。

如需调整视觉样式，可以修改：

```text
css/style.css
```


## 自定义建议

- 将页面中的 `LinkNest`、头像、描述替换为你的个人信息
- 将链接卡片替换为你的博客、导航站、项目页、社交主页等
- 修改 `theme-color`、背景色和卡片样式，让页面更符合个人风格
- 部署前检查 `canonical`、`og:url`、图片地址等 SEO 信息是否为你的真实地址

## 常见问题

### 为什么最新动态页显示“加载失败”？

通常是因为没有通过静态服务器打开，或者 `data/latest.json` 路径不正确。请优先使用本地静态服务器预览。
PS：如果你直接双击打开 HTML 文件，部分浏览器可能会限制 `fetch` 读取本地 JSON，导致最新动态无法加载。

### 怎么新增一条动态？

直接在 `data/latest.json` 的 `posts` 数组里追加一项即可。页面会自动渲染，`pinned: true` 的内容会排在前面。

### 怎么替换成自己的站点？

把首页文案、卡片链接、头像图标和关于页联系方式替换成你的信息即可。


## 维护说明

- 页面内容偏静态，适合个人主页和轻量导航页场景
- `latest.html` 适合后续接入 RSS、接口数据或 CMS 输出
- 当前示例内容中的域名和联系方式需要按你的实际站点替换
