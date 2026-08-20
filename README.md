# Logist Homepage

Logist 的个人主页，包含首页（项目展示）与关于页（个人介绍、联系方式）。

## 技术栈

- [Vue 3](https://vuejs.org/) + `<script setup>`
- [Vite](https://vitejs.dev/) 构建
- [Vue Router](https://router.vuejs.org/)（Hash 模式，便于静态部署）

## 快速开始

```bash
npm install        # 安装依赖
npm run dev        # 开发服务器（默认 http://localhost:5173）
npm run build      # 构建到 dist/
npm run preview    # 预览构建产物
```

## 项目结构

```
├── index.html              # HTML 入口
├── vite.config.js          # Vite 配置（base: './'，可部署到任意子路径）
├── src/
│   ├── main.js             # 应用入口
│   ├── App.vue             # 根组件（路由出口 + 页脚）
│   ├── assets/main.css     # 全局样式（设计变量 + 组件样式）
│   ├── components/         # 公共组件
│   │   └── GitHubIcon.vue  # GitHub 图标
│   ├── router/index.js     # 路由配置（含 404 兜底）
│   └── views/              # 页面
│       ├── Home.vue        # 首页：个人简介 + 项目展示（数据在组件内维护）
│       └── About.vue       # 关于页：技术栈 / 学习计划 / 联系方式
```

## 说明

- 页脚的「广告位招租」横幅为刻意保留的元素，如需移除请编辑 `src/App.vue`。
- 项目数据维护在 `src/views/Home.vue` 的 `projects` 数组中，首页「项目」统计数字会自动跟随该数组长度变化。
- 路由采用 Hash 模式（`#/`），配合 `base: './'` 可部署到 GitHub Pages 等任意静态托管。