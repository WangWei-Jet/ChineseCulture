# 中国文化研习录 · ChineseCulture

关于中国传统文化的学习笔记与通识讲义。所有内容以**单文件 HTML** 形式维护——
不依赖外部资源，可离线阅读，也可直接用浏览器打印成 PDF。

## 在线阅读

站点通过 GitHub Pages 自动发布：

> **https://wangwei-jet.github.io/ChineseCulture/**

## 目录结构

```
.
├── index.html                  # 站点首页（讲义索引）
├── tea/
│   └── index.html              # 茶 · 通识讲义（11 章 + 4 附录）
├── .github/workflows/
│   └── deploy.yml              # GitHub Pages 自动部署工作流
└── README.md
```

新增专题时，在仓库根目录建一个同名文件夹，放入 `index.html`，
然后在根 `index.html` 的卡片区加一张卡片即可。部署会自动完成。

## 现有讲义

| 专题 | 路径 | 内容 |
| --- | --- | --- |
| 茶 · 通识讲义 | [`tea/`](./tea/) | 11 章 + 4 附录：起源与字源、三千年茶史、六大茶类、制茶工艺、四大茶区、再加工茶与新式茶饮、成分科学、产业数据、选泡存实操、茶道茶俗、术语速查 |

### 茶讲义章节目录

1. **起源** —— 植物学来源、`荼`→`茶` 的字源演变、神农传说、从「吃茶」到「喝茶」
2. **三千年茶史** —— 先秦至今的时间线，含 2022 年列入人类非遗
3. **六大茶类** —— 发酵光谱、六个茶类详解、普洱茶归属争议
4. **制茶工艺词典** —— 萎凋 / 杀青 / 揉捻 / 做青 / 闷黄 / 渥堆 / 发酵
5. **中国四大茶区** —— 江南 / 江北 / 西南 / 华南
6. **再加工茶与现代茶饮** —— 茉莉花茶窨制八步、紧压茶、抹茶、新式茶饮
7. **茶杯里的科学** —— 三大成分、按需选茶、四个误区澄清
8. **茶产业全景** —— 2025 年产业数据、全球格局、品牌价值榜
9. **实用手册** —— 买、泡、存
10. **茶道与茶俗** —— 茶道精神、中国地方茶俗、世界茶俗对照
11. **附录** —— 术语速查、十大名茶、30 天入门路径、速查卡

## 本地预览

无需构建，直接打开 HTML 文件即可。或起一个本地静态服务器：

```bash
python3 -m http.server 8000
# 然后访问 http://localhost:8000
```

## 部署说明

站点由 GitHub Actions 自动部署，工作流定义在 `.github/workflows/deploy.yml`。

- **触发条件**：推送到 `main` 分支，或在 Actions 页面手动触发（`workflow_dispatch`）
- **构建过程**：把仓库内除 `.git` / `.github` / `_site` / `README.md` 之外的文件复制到 `_site/`，
  并写入 `.nojekyll`，然后作为 Pages 产物上传
- **权限**：使用 `GITHUB_TOKEN`，已声明 `pages: write` 与 `id-token: write`
- **Pages 启用**：`configure-pages` 已设置 `enablement: true`，首次部署会自动开启 Pages
  并把 Source 设为 GitHub Actions，**无需任何手动操作**

### 关于 Pages 设置

若日后部署报错 `Get Pages site failed` 或 `Not Found`，多半是 Pages 被关闭了。
可在 **Settings → Pages → Build and deployment → Source** 手动选一次 **GitHub Actions**，
再重跑工作流即可。日常维护不需要碰这个设置。

## 站点状态

| 页面 | 地址 | 状态 |
| --- | --- | --- |
| 首页 | https://wangwei-jet.github.io/ChineseCulture/ | 已上线 |
| 茶 · 通识讲义 | https://wangwei-jet.github.io/ChineseCulture/tea/ | 已上线 |

## 数据与内容说明

产业数据主要依据中国茶叶流通协会、《2025 年度中国茶叶产销形势分析报告》、
国际茶叶委员会《2025 年统计公报》、艾媒咨询新式茶饮行业报告等公开资料整理，
统计年度以 2025 年为主。价格与市场数据具时效性，实际应用请以最新发布为准。

涉及茶叶成分与健康的内容均为科普性质，**不构成医疗建议**。

## 许可

内容以公开资料整理，欢迎指正。
