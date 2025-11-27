# 情侣纪念网站项目概述

## 项目简介
这是一个专为情侣设计的纪念网站，具有浪漫的设计风格和丰富的交互功能。网站采用液态玻璃效果和Q弹动效，营造温馨甜蜜的氛围。

## 技术架构

### 前端技术栈
- **HTML5**: 语义化结构和现代Web标准
- **CSS3**: 液态玻璃效果、动画和响应式设计
- **JavaScript ES6+**: 交互逻辑和动态效果
- **动画库**: 
  - Anime.js: 页面切换和元素动画
  - Matter.js: 物理引擎驱动的照片爱心效果
  - Pixi.js: 背景特效和光影效果

### 数据存储
- **LocalStorage**: 用户数据、博客内容、照片和任务状态
- **JSON格式**: 结构化数据存储和读取

## 页面结构

### 1. 登录页面 (index.html)
**功能特性**:
- 背景虚化效果
- 用户身份验证
- 色调切换功能（5种配色方案）
- "我要申请"邮件功能
- 更新日志展示

**视觉设计**:
- 液态玻璃登录表单
- 浪漫的背景图像
- Q弹的按钮动效
- 柔和的过渡动画

### 2. 主页面 (main.html)
**功能特性**:
- 日常列表展示
- 照片墙功能
- 导航菜单
- 用户信息显示

**视觉设计**:
- 卡片式布局
- 爱心形状的照片汇聚
- 悬停交互效果
- 响应式网格

### 3. 写日常页面 (write.html)
**功能特性**:
- 身份验证和权限控制
- 富文本编辑器
- 实时预览
- 发布动效

**视觉设计**:
- 简洁的编辑器界面
- 优雅的表单样式
- 渐变按钮效果
- 成功发布动画

### 4. 我们一起做页面 (together.html)
**功能特性**:
- 200个情侣任务清单
- 双方完成状态追踪
- 进度统计
- 庆祝动效

**视觉设计**:
- 网格布局的任务卡片
- 颜色渐变表示完成状态
- 粒子庆祝效果
- 进度可视化

### 5. 一键报备页面 (report.html)
**功能特性**:
- 地理位置获取
- 自动日常生成
- 位置信息格式化
- 权限处理

**视觉设计**:
- 圆形报备按钮
- 位置信息展示
- 加载状态指示
- 友好的错误提示

## 核心功能模块

### 用户认证系统
```javascript
// 用户数据结构
const users = {
    '林粤冬': {
        password: '2006111620250601',
        identity: '狮王',
        avatar: 'lion-icon'
    },
    '蒲振宇': {
        password: '2008062220250601',
        identity: '小鱼',
        avatar: 'fish-icon'
    }
};
```

### 日常管理系统
```javascript
// 日常数据结构
const dailyPosts = [
    {
        id: timestamp,
        sender: '狮王',
        author: '林粤冬',
        title: '主题内容',
        content: '正文内容',
        date: '发布时间',
        type: 'normal' // 或 'report'
    }
];
```

### 照片墙系统
```javascript
// 照片数据结构
const photos = [
    {
        id: 'unique-id',
        url: 'base64-image-data',
        uploadDate: 'timestamp',
        uploader: 'username'
    }
];
```

### 任务追踪系统
```javascript
// 任务数据结构
const coupleTasks = [
    {
        id: 1,
        task: '一起做早餐',
        completedBy: ['林粤冬', '蒲振宇'], // 完成用户列表
        isFullyCompleted: true
    }
];
```

## 视觉效果实现

### 液态玻璃效果
```css
.glass-effect {
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.18);
    border-radius: 20px;
    box-shadow: 0 0 20px rgba(255, 255, 255, 0.1);
}
```

### Q弹动效
```javascript
anime({
    targets: '.element',
    scale: [1, 1.05, 1],
    duration: 300,
    easing: 'easeOutElastic(1, .8)'
});
```

### 色调切换系统
```javascript
const colorSchemes = {
    romantic: {
        primary: '#FFB6C1',
        secondary: '#FFD700',
        background: '#FFF0F5',
        text: '#8B4513'
    }
    // ... 其他配色方案
};
```

## 响应式设计

### 断点设置
- 移动端: 320px - 768px
- 平板端: 768px - 1024px
- 桌面端: 1024px+

### 适配策略
- 移动优先设计
- 渐进增强功能
- 触摸友好交互
- 性能优化考虑

## 数据持久化

### 本地存储结构
```javascript
// 用户设置
localStorage.setItem('userSettings', JSON.stringify({
    colorScheme: 'romantic',
    currentUser: '林粤冬',
    lastVisit: timestamp
}));

// 网站数据
localStorage.setItem('coupleWebsiteData', JSON.stringify({
    dailyPosts: [],
    photos: [],
    coupleTasks: [],
    userProgress: {}
}));
```

## 性能优化

### 图片处理
- Base64编码存储
- 压缩优化
- 懒加载实现
- 缓存策略

### 动画优化
- GPU加速
- 节流防抖
- 动画队列
- 内存管理

## 用户体验

### 交互反馈
- 即时视觉反馈
- 状态指示器
- 友好错误提示
- 成功庆祝动效

### 情感化设计
- 温馨色彩搭配
- 浪漫动效设计
- 个性化定制
- 纪念意义体现

## 部署和维护

### 静态网站部署
- 单页面应用
- 资源优化
- CDN加速
- HTTPS安全

### 数据备份
- 本地存储备份
- 导出功能
- 数据恢复
- 版本兼容