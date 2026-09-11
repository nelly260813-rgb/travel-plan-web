# 旅行计划网页

这是一个 Mobile First 的单页静态网页原型，依据：
- `travel-data.json`
- `旅行计划网页-信息架构设计.md`

## 已实现
- 首页：路线 Hero、下一程倒计时、交通横滑卡片、快捷入口
- 行程：Day 0–Day 8 日期条、Bottom Sheet 当日详情、时间轴、Google Maps 跳转、购票/预约提醒
- 自驾：取还车路线、检查清单、驾驶提醒、费用折叠
- 清单：增删勾选、localStorage 持久化，仅当前设备可见
- 账本：CNY/EUR/HUF、AA 平摊、汇率快照字段、实时汇率刷新与临时换算工具
- 页面分享安全：没有把护照号、租车 security code、PNR 等敏感凭证嵌入网页

## 重要说明
这是“前端可运行原型”，没有后端，因此账本目前也使用 localStorage。
要真正实现设计稿中 `shared=true` 的跨设备共享账本，需要接入数据库/后端（例如 Supabase/Firebase/自建 API），并把 expense CRUD 替换为远端存储。

## 运行
最简单：
1. 双击 `index.html`（部分浏览器的实时汇率请求可能因本地文件安全策略失败）
2. 推荐使用任意静态服务器，例如：
   `python3 -m http.server 8000`
   然后打开 `http://localhost:8000`

## 下一步
- 接入共享账本后端
- 加入真实目的地背景图
- 加入 PWA / 离线缓存
- 增加真正的分享链接与权限控制
