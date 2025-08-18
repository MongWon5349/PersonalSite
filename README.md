# 个人网站 Vue 项目

这是一个使用 Vue 3 和 Vite 构建的现代化个人网站项目。

## 项目特性

- ✨ Vue 3 + Vite 快速开发
- 🎨 现代化的响应式设计
- 🚀 Vue Router 单页面应用
- 📱 移动端友好
- 🎯 简洁优雅的UI设计

## 项目结构

```
PersonalSite/
├── index.html          # 入口HTML文件
├── package.json        # 项目依赖配置
├── vite.config.js      # Vite配置文件
├── README.md          # 项目说明文档
└── src/
    ├── main.js        # 应用入口文件
    ├── App.vue        # 根组件
    └── components/
        ├── Home.vue   # 首页组件
        └── About.vue  # 关于页面组件
```

## 安装和运行

### 前提条件

确保你的系统已安装：
- Node.js (版本 16 或更高)
- npm 或 yarn

### 安装依赖

```bash
npm install
# 或
yarn install
```

### 开发模式运行

```bash
npm run dev
# 或
yarn dev
```

项目将在 `http://localhost:3000` 启动

### 构建生产版本

```bash
npm run build
# 或
yarn build
```

### 预览生产版本

```bash
npm run preview
# 或
yarn preview
```

## 页面说明

### 首页 (Home)
- 英雄区域展示
- 项目作品展示
- 现代化的卡片设计
- 平滑滚动效果

### 关于页面 (About)
- 个人简介
- 技能展示
- 联系方式
- 响应式布局

## 自定义配置

你可以根据需要修改以下内容：

1. **个人信息**: 编辑 `src/components/About.vue` 中的个人信息
2. **项目展示**: 修改 `src/components/Home.vue` 中的项目数据
3. **样式主题**: 调整各组件中的CSS变量和渐变色
4. **路由配置**: 在 `src/main.js` 中添加新的路由

## 技术栈

- **Vue 3**: 渐进式JavaScript框架
- **Vue Router**: 官方路由管理器
- **Vite**: 下一代前端构建工具
- **CSS3**: 现代CSS特性，包括Grid和Flexbox

## 浏览器支持

- Chrome >= 87
- Firefox >= 78
- Safari >= 14
- Edge >= 88

## 许可证

MIT License