# 巴山 e 悦行 - 巴中旅游微信小程序

🏔️ 一款专为巴中旅游打造的微信小程序，提供景点推荐、美食探索、路线规划等一站式旅游服务。

![微信小程序](https://img.shields.io/badge/平台 - 微信小程序-green)
![License](https://img.shields.io/badge/license-MIT-blue)

## ✨ 功能特性

### 🏠 首页
- 精美轮播图展示热门景点
- 快捷入口：景点、美食、出行、露营
- 热门景点横向滚动推荐
- 特色美食横向滚动推荐

### 🤖 AI 智能助手
- 对话式交互界面
- 智能生成定制游玩路线
- 快速提问模板
- 根据用户需求推荐景点、美食、路线

### 🏞️ 景点推荐
- 8 个热门景点展示（光雾山、诺水河、恩阳古镇等）
- 景点详情页面
- 搜索功能
- 分类筛选（自然景观、历史文化、地质奇观）

### 🍜 美食推荐
- 10 种巴中特色美食（巴中凉面、南江黄羊、恩阳麻饼等）
- 正餐/小吃分类浏览
- 美食详情页面
- 推荐指数展示

### ⛺ 露营推荐
- 4 个露营基地推荐
- 露营地详细信息
- 价格、位置、特色展示
- 露营小贴士

### 👤 个人中心
- 用户登录/注册
- 我的收藏
- 我的行程
- 偏好设置
- 设置功能

## 🛠️ 技术栈

- **开发框架**: 微信小程序原生开发
- **页面结构**: WXML
- **样式**: WXSS
- **逻辑**: JavaScript
- **数据请求**: 封装的 request 工具类
- **UI 风格**: 绿色清新主题

## 📁 项目结构

```
wenlv/
├── api/                    # 接口封装
│   ├── ai.js              # AI 对话接口
│   ├── attraction.js      # 景点接口
│   ├── camping.js         # 露营接口
│   ├── favorite.js        # 收藏接口
│   ├── food.js            # 美食接口
│   ├── index.js           # 统一导出
│   ├── tag.js             # 标签接口
│   ├── travel.js          # 出行接口
│   └── user.js            # 用户接口
├── config/                 # 配置文件
│   └── index.js           # 全局配置
├── custom-tab-bar/         # 自定义底部导航
│   ├── index.js
│   ├── index.wxml
│   ├── index.wxss
│   └── index.json
├── images/                 # 图片资源
├── pages/                  # 页面
│   ├── ai/                # AI 对话页
│   ├── attractions/       # 景点列表页
│   ├── camping/           # 露营页
│   ├── food/              # 美食页
│   ├── index/             # 首页
│   ├── login/             # 登录页
│   ├── profile/           # 个人中心
│   ├── tags/              # 标签选择页
│   └── travel/            # 出行指南页
├── utils/                  # 工具类
│   └── request.js         # 网络请求封装
├── app.js                  # 小程序入口
├── app.json                # 全局配置
├── app.wxss                # 全局样式
└── README.md               # 项目说明
```

## 🚀 快速开始

### 环境准备
1. 下载并安装 [微信开发者工具](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html)
2. 注册微信小程序账号

### 运行项目
1. 克隆项目到本地
```bash
git clone https://github.com/linsy0830/wenlv.git
cd wenlv
```

2. 打开微信开发者工具
3. 选择"导入项目"
4. 选择项目目录 `d:\bazhong\qianduan`
5. 填写 AppID（测试账号可选）
6. 点击"导入"

### 配置后端接口
修改 `config/index.js` 中的 `baseUrl`：
```javascript
const config = {
  baseUrl: 'https://your-api-domain.com',  // 修改为你的后端地址
  timeout: 15000,
  tokenKey: 'token'
}
```

## 📱 页面截图

> 待添加实际运行截图

## 🎨 设计特色

- **主题色**: 绿色 (#2E7D32) - 象征自然生态
- **UI 风格**: 清新自然、简洁明快
- **交互体验**: 流畅的页面切换、友好的用户提示
- **响应式布局**: 适配不同尺寸屏幕

## 📝 主要功能说明

### AI 对话
- 基于关键词匹配生成路线推荐
- 支持快速提问（必去景点、亲子游、美食、周末游）
- 智能识别用户意图（天数、偏好、人群）

### 景点/美食
- 本地数据展示，无需后端即可运行
- 支持搜索和筛选
- 详情页展示完整信息

### 用户系统
- 支持手机号密码登录
- 本地存储用户信息
- 标签偏好设置

## 🔧 开发说明

### 添加新景点
编辑 `pages/attractions/attractions.js`，在 `attractions` 数组中添加：
```javascript
{
  id: 9,
  name: '景点名称',
  description: '景点描述',
  tags: ['标签 1', '标签 2'],
  rating: 4.5,
  price: '门票价格',
  emoji: '🏔️',
  color: 'linear-gradient(...)'
}
```

### 添加新美食
编辑 `pages/food/food.js`，在 `foods` 数组中添加：
```javascript
{
  id: 11,
  name: '美食名称',
  description: '美食描述',
  tags: ['标签 1', '标签 2'],
  price: 50,
  sales: '1000+',
  rating: 4.8,
  type: 'dinner',  // dinner 或 snack
  emoji: '🍜',
  color: 'linear-gradient(...)'
}
```

### 自定义 API 接口
在 `api/` 目录下创建新的接口文件，参考现有接口格式：
```javascript
const request = require('../utils/request.js')

function getData(params) {
  return request.get('/api/your-endpoint', params)
}

module.exports = {
  getData
}
```

## 📄 接口文档

项目已封装完整的 API 接口层，位于 `api/` 目录：

- **用户接口**: 登录、注册、获取用户信息
- **景点接口**: 列表、详情、搜索、筛选
- **美食接口**: 列表、详情、分类
- **AI 接口**: 智能对话、路线生成
- **收藏接口**: 添加/取消收藏
- **标签接口**: 获取标签、保存偏好

详细接口定义请查看各文件注释。

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

## 📧 联系方式

- 项目地址：https://github.com/linsy0830/wenlv
- 问题反馈：请提 Issue

## 📜 开源协议

MIT License

---

**巴山 e 悦行** - 您的巴中旅游智能助手 🏞️
