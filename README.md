# 📊 可视化贷款计算器

[![在线试玩](https://img.shields.io/badge/在线试玩-点此访问-brightgreen?logo=googlechrome)](https://red-fire-99.github.io/loan-calculator/)
[![隐私](https://img.shields.io/badge/隐私-零数据上传-2563eb?icon=lock)](PRIVACY-AUDIT.md)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

一个**单文件、零依赖**的可视化贷款计算器。双击 `index.html` 即可在浏览器打开，无需安装、无需网络、无需构建。

## 功能

| 模块 | 说明 |
|---|---|
| 等额本息 / 等额本金 | 两种经典还款方式，对比计算 |
| 甜甜圈占比 | 本金 vs 利息占比一目了然 |
| 面积图 | 每期还款构成（本金↑ / 利息↓），支持悬浮查看第 N 期明细 |
| 提前还款模拟 | 一次性提前还款，支持「缩短期限 / 减少月供」两种处理方式 |
| 零息贷款节省 | 比较普通贷款与零息贷款的节省额 |
| 两种方式对比 | 等额本息 vs 等额本金同条件下对比 |
| 利率敏感性 | 当前利率 ±0.5% / ±1% 的总利息变化 |
| 50/30/20 法则 | 判断月供是否压得住月收入 |

## 快速开始

只需一个文件：

```bash
# 方式一：双击打开（推荐，无需任何服务）
open index.html

# 方式二：用本地服务器
python -m http.server 8080
# 访问 http://localhost:8080
```

## 在线试用

部署到 GitHub Pages 后（本仓库已配置）：

```
https://red-fire-99.github.io/loan-calculator/
```

## 隐私声明

✅ **完全本地计算，零数据上传**

- 所有计算在浏览器中完成，无后端服务器
- 无外部请求、无 CDN、无框架、无分析脚本
- 无 localStorage、无 cookies、无 fingerprinting
- 无网络请求，所有数据都停留在你的浏览器里

唯一的「数据」是：URL 哈希分享链接（如 `#principal=1000000&rate=4.2`），仅用于本地状态保存和分享，**不会发送到任何服务器**。

## 技术说明

- 单文件自包含：`index.html` 包含所有 CSS、HTML、JavaScript
- 零依赖：不引入任何 CDN、框架或库
- 图表：全部手写 SVG
- 计算：集中在 `buildSchedule(P, rate, years, method, prepay)` 中，改算法只需改这一处

## 项目文件结构

```
loan-calculator/
├── index.html      # 主文件（包含所有内容）
├── README.md       # 说明文档
├── LICENSE         # 开源许可证
├── .gitignore
└── .nojekyll       # GitHub Pages 忽略 Jekyll 处理
```

## 许可证

MIT License — 自由使用、修改、分发，保留版权声明即可。

---

*由 [red-fire-99](https://github.com/red-fire-99) 维护 · [隐私审计报告](PRIVACY-AUDIT.md)*
