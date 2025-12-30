# TechNova 购物网站

##  项目文件结构（简化版）

```
项目文件夹/
├── index-simple.html      # 首页
├── shop-simple.html       # 商城页面
├── cart-simple.html       # 购物车页面
├── login-simple.html      # 登录页面
├── about-simple.html      # 关于我们页面
├── product-simple.html    # 商品详情页面
├── css/
│   └── style.css          # 统一样式表（简化版）
├── photos/                # 商品图片文件夹
│   ├── 1.jpg ~ 6.jpg
└── videos/                # 商品视频文件夹
    └── 1.mp4 ~ 6.mp4
```

---

##  对应课本知识点

### 第1章：HTML5+CSS3初体验

| 知识点 | 代码位置 | 说明 |
|--------|----------|------|
| HTML5基本语法 | 所有HTML文件 | `<!DOCTYPE html>`, `<meta charset="UTF-8">` |
| 语义化标签 | 所有页面 | `<nav>`, `<header>`, `<footer>`, `<section>` |
| CSS引入方式 | HTML的`<head>` | `<link rel="stylesheet" href="css/style.css">` |
| 选择器 | style.css | 类选择器`.btn`、标签选择器`body`、后代选择器`.nav-menu a` |
| 盒子模型 | style.css | `padding`, `margin`, `border`, `box-sizing: border-box` |
| 圆角边框 | style.css | `border-radius: 8px` |
| 阴影 | style.css | `box-shadow: 0 2px 10px rgba(0,0,0,0.1)` |
| 线性渐变 | style.css | `background: linear-gradient(135deg, #ff4d4f, #ff7a45)` |

### 第2章：CSS3文本与图标

| 知识点 | 代码位置 | 说明 |
|--------|----------|------|
| 字体样式 | style.css | `font-family`, `font-size`, `font-weight` |
| 文本外观 | style.css | `text-align`, `color`, `line-height` |
| 链接属性 | style.css | `a:hover { color: #ff4d4f; }` |

### 第4章：HTML5表单

| 知识点 | 代码位置 | 说明 |
|--------|----------|------|
| form标签 | login-simple.html | `<form onsubmit="handleLogin(event)">` |
| input新特性 | login-simple.html | `type="email"`, `required`, `placeholder` |
| 表单验证 | login-simple.html | HTML5自动验证邮箱格式 |

### 第5章：JavaScript基础

| 知识点 | 代码位置 | 说明 |
|--------|----------|------|
| 变量 | 所有JS | `var cart = []` |
| 函数 | 所有JS | `function addToCart() { }` |
| 事件处理 | 所有JS | `onclick`, `onsubmit`, `window.onload` |
| DOM操作 | 所有JS | `document.getElementById()`, `innerHTML` |

### 第6章：HTML5音频和视频

| 知识点 | 代码位置 | 说明 |
|--------|----------|------|
| video标签 | shop-simple.html, product-simple.html | `<video controls poster="">` |
| source标签 | 同上 | `<source src="videos/1.mp4" type="video/mp4">` |
| controls属性 | 同上 | 显示视频控制条 |
| poster属性 | 同上 | 视频封面图 |

### 第7章：响应式Web设计

| 知识点 | 代码位置 | 说明 |
|--------|----------|------|
| viewport | HTML的`<head>` | `<meta name="viewport" content="width=device-width">` |
| 媒体查询 | style.css底部 | `@media (max-width: 768px) { }` |
| 弹性盒布局 | style.css | `display: flex`, `justify-content`, `align-items` |
| Grid布局 | style.css | `display: grid`, `grid-template-columns` |

---

##  主要功能说明

### 1. 首页 (index-simple.html)
- 顶部导航栏（粘性定位）
- 横幅区域（渐变背景）
- 特色服务展示（Flexbox布局）
- 商品展示（Grid布局）

### 2. 商城页面 (shop-simple.html)
- 视频展示区（HTML5 video）
- 商品搜索功能
- 商品列表展示
- 加入购物车功能

### 3. 购物车 (cart-simple.html)
- 显示已添加商品
- 修改商品数量
- 删除商品
- 计算总价
- 模拟结算

### 4. 登录页面 (login-simple.html)
- HTML5表单
- 邮箱验证
- 模拟登录

### 5. 关于我们 (about-simple.html)
- 公司介绍
- 数据统计展示
- 团队成员展示

### 6. 商品详情 (product-simple.html)
- 商品视频播放
- 商品信息展示
- 加入购物车

---

##  本地存储功能

使用 `localStorage` 保存购物车数据：

```javascript
// 保存数据
localStorage.setItem('cart', JSON.stringify(cart));

// 读取数据
var cart = JSON.parse(localStorage.getItem('cart')) || [];
```

---

##  CSS重点样式解释

### 1. Flexbox弹性盒布局
```css
.nav-content {
    display: flex;           /* 启用弹性盒 */
    justify-content: space-between;  /* 两端对齐 */
    align-items: center;     /* 垂直居中 */
}
```

### 2. Grid网格布局
```css
.product-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);  /* 4列等宽 */
    gap: 20px;               /* 间距 */
}
```

### 3. 渐变背景
```css
.hero {
    background: linear-gradient(135deg, #ff4d4f, #ff7a45);
}
```

### 4. 响应式媒体查询
```css
@media (max-width: 768px) {
    .product-grid {
        grid-template-columns: repeat(2, 1fr);  /* 手机端2列 */
    }
}
```

---

##  常见答辩问题

### Q1: 项目使用了哪些HTML5新特性？
**答**: 
- 语义化标签：`<nav>`, `<header>`, `<footer>`
- 表单新特性：`type="email"`, `required`, `placeholder`
- 视频标签：`<video>`, `<source>`
- 本地存储：`localStorage`

### Q2: 项目使用了哪些CSS3新特性？
**答**:
- 圆角边框：`border-radius`
- 阴影效果：`box-shadow`
- 渐变背景：`linear-gradient`
- 弹性盒布局：`display: flex`
- 网格布局：`display: grid`
- 媒体查询：`@media`

### Q3: 如何实现响应式设计？
**答**:
1. 使用 `viewport` 元标签
2. 使用 `@media` 媒体查询
3. 使用弹性盒和网格布局
4. 使用百分比和相对单位

### Q4: 购物车数据如何保存？
**答**: 使用 HTML5 的 `localStorage` 本地存储，将购物车数据转换为JSON字符串保存，页面刷新后数据不会丢失。

### Q5: 如何实现商品搜索？
**答**: 获取用户输入的关键词，遍历所有商品卡片，根据商品名称和分类判断是否匹配，匹配则显示，不匹配则隐藏。

---

##  如何运行项目

1. 确保 `photos` 文件夹中有 1.jpg ~ 6.jpg 图片
2. 确保 `videos` 文件夹中有 1.mp4 ~ 6.mp4 视频（可选）
3. 用浏览器打开 `index-simple.html` 即可

 
