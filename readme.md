# 咸鱼郑某 / ZhengHaoF

都是自己先用着、顺手开源出来的项目。

## 泛音 Overtone

<p align="center">
  <a href="https://github.com/ZhengHaoF/overtone">
    <img src="https://raw.githubusercontent.com/ZhengHaoF/overtone/main/docs/screenshots/windows-discover.webp" width="400" alt="泛音 桌面端发现页">
  </a>
  <a href="https://github.com/ZhengHaoF/overtone">
    <img src="https://raw.githubusercontent.com/ZhengHaoF/overtone/main/docs/screenshots/android-player.webp" width="200" alt="泛音 安卓播放页">
  </a>
</p>

多音源的第三方音乐客户端，酷狗概念版 / 网易云 / 哔哩哔哩，Flutter 写的。Android 和 Windows 有现成的安装包，Linux 能源码构建。

- 逐字歌词配译文音染、Windows 双进程悬浮窗、Android 悬浮窗、Linux X11 悬浮窗
- 评论能读能写，酷狗云盘能传能秒传，MV 带弹幕和小窗
- 皮肤折腾了默认、瑞士国际排版、EVA 红、EVA 蓝、MAGI 战术终端几套
- 翻车的地方也写在 README 里：Windows 半透明桌面歌词实测做不到，B 站的真实账号登录还没在真机上验收

[仓库](https://github.com/ZhengHaoF/overtone) · [Releases](https://github.com/ZhengHaoF/overtone/releases)

## Pi Agent Desktop

<p align="center">
  <a href="https://github.com/ZhengHaoF/pi-desktop">
    <img src="https://raw.githubusercontent.com/ZhengHaoF/pi-desktop/main/images/app-main.png" width="560" alt="Pi Agent Desktop 主工作区">
  </a>
</p>

把 Pi Coding Agent 塞进一个真能用的桌面工作台，Electron + React，跨平台。fork 自 [DLYZZT/pi-desktop](https://github.com/DLYZZT/pi-desktop)，我这边加的是：

- `web_search` / `web_fetch` 两个工具，连带一个设置页
- 上下文用量画成环，压缩之后的续读也接上了
- 桌面通知跟着界面语言走；模型选择器把 provider 的全量模型都列出来
- 新会话默认工具预设；About 里把 fork 作者标出来

[仓库](https://github.com/ZhengHaoF/pi-desktop) · [上游](https://github.com/DLYZZT/pi-desktop)

## Z Ai

AI 图像生成与编辑的 Web 应用。原本是 Flutter 客户端，被我整个重写成了 Web 版 —— 原因很朴素：长任务得在服务端跑，关掉页面还能继续出图。

- 服务端 Node 22 + Express + `node:sqlite`，任务有状态机，崩了能恢复，能取消
- 每个模型自带上游地址、协议和 Key，模型列表能从上游拉；多 Profile 隔离
- 单密码登录，日志用 WebSocket 实时推，图库能翻能下载
- 浏览器做不到的事就不做：系统托盘、前台保活、原生通知栏、写入相册

[仓库](https://github.com/ZhengHaoF/z_ai_img)

## YB Search

<p align="center">
  <a href="https://github.com/ZhengHaoF/yb-search">
    <img src="https://raw.githubusercontent.com/ZhengHaoF/yb-search/main/docs/screenshots/results-desktop.png" width="420" alt="YB Search 搜索结果页">
  </a>
</p>

私有的网页搜索站，底层是腾讯云元宝搜索 API。Vue 3 + Vite 前端，Fastify 在同一个仓库里代理，密钥只落在服务端。

- 查询和筛选全同步到 URL，刷新、收藏、前进后退都能还原
- 骨架屏、空结果、错误态都写了，错误里带 RequestId，可以直接复制去查
- `/` 聚焦搜索框、`Esc` 清空；移动端筛选收进底部抽屉
- 单口令登录，签名 HttpOnly Cookie，有效期 7 天
- 上游接口返回的版本一变，不支持的参数自动隐藏

[仓库](https://github.com/ZhengHaoF/yb-search)

## 烽火舆图 · Warlords 1931

全栈战争地图策略游戏，pnpm workspace 单仓多包：前端 Vue 3 + PixiJS 8，后端 NestJS + TypeORM + better-sqlite3，AI 对手走 DeepSeek 代理。

README 里专门留了条警告：Vite 实际跑在 5714，而后端 `CORS_ORIGIN` 默认还写着 5173，不改就是一堆 CORS 报错。

[仓库](https://github.com/ZhengHaoF/map-war)

## 人体检测 Demo

安卓摄像头实时人体检测，Kotlin + Compose + CameraX + MediaPipe，EfficientDet-Lite0 int8 纯端上推理，不联网。

帧进来先 `toBitmap()` 再手动转正 90°，检测框做 EMA 平滑，HUD 上写着当前人数、历史最大同屏人数和 FPS。

[仓库](https://github.com/ZhengHaoF/human-detect-demo)

## 零碎

- [NeriPlayer](https://github.com/ZhengHaoF/NeriPlayer)（fork）—— 给它加了酷狗音乐概念版的音源
- [cloudreve-v4-skill](https://github.com/ZhengHaoF/cloudreve-v4-skill) —— Cloudreve v4 上传用的 skill，零依赖 Node 上传器，兼容 S3 那种策略
- [clash-go](https://github.com/ZhengHaoF/clash-go) —— 机场的订阅走 Cloudflare 中转，直接把 IP 写回配置
- [Nice-Dns](https://github.com/ZhengHaoF/Nice-Dns) —— GitHub 抽风的时候救一下场

## 工具箱

- **前端**：Vue 3 / Vite / TypeScript 写得多，Pinia、Vue Router 熟；老项目里还有 Vue 2 后台和 uni-app
- **跨平台**：Flutter 的 Android 签名 APK、Windows 安装包、Linux 源码构建这条发布链自己维护；偶尔写 Kotlin + Compose 碰原生和端侧推理
- **服务端**：Node 22，Express / Fastify / NestJS 都用过；数据优先 `node:sqlite`、`better-sqlite3` 这种零运维方案，能单文件解决就不建库
- **部署**：一台腾讯云机器 + Cloudflare，能自托管的就自己托管
- **杂项**：Electron、PixiJS 小游戏、Python 脚本和数据抓取

## 联系

这个仓库没开 issue，有问题提到 [overtone 的 issue](https://github.com/ZhengHaoF/overtone/issues) 就能找到我
