# DayPulse-Releases (官方发布与产物分发中心)

> **感受时间的温度，记录当下的坚持。**  
> 本仓库为 **DayPulse (日脉)** 官方各端编译产物分发中心与版本发布资产托管仓库。

---

## 📌 发布分支导航矩阵

为解决不同产物混杂、发布混乱的问题，本仓库采用**严格分支隔离策略**，将全量安装包与增量热更新资源包独立管理：

| 分支名称 | 托管产物形态 | 应用场景 | 产物规范与示例 | 分支直达链接 |
|:---|:---|:---|:---|:---:|
| **`apk`** | Android 原生全量安装包 | 新安装、大版本重构、底层原生 SDK/插件变动 | `DayPulse_v{versionName}_{versionCode}.apk`<br>例：`DayPulse_v1.0.3_103.apk` | [👉 进入 `apk` 分支](https://github.com/Xiosn/DayPulse-Releases/tree/apk) |
| **`wgt`** | uni-app 热更新差量资源包 | 日常功能微调、Bug 修复、UI 优化、秒级静默更新 | `DayPulse_v{versionName}_{versionCode}.wgt`<br>例：`DayPulse_v1.0.3_103.wgt` | [👉 进入 `wgt` 分支](https://github.com/Xiosn/DayPulse-Releases/tree/wgt) |

---

## ⚡ 国内免翻墙极速下载 CDN 规则

所有发布在 GitHub Releases 的安装包或更新资源，均自动配合开源 CDN 加速镜像生成国内高速直连链接：

```text
https://ghfast.top/https://github.com/Xiosn/DayPulse-Releases/releases/download/{tag}/{filename}
```

- **全量 APK 直链示例**：  
  `https://ghfast.top/https://github.com/Xiosn/DayPulse-Releases/releases/download/v1.0.3/DayPulse_v1.0.3_103.apk`
- **差量 WGT 直链示例**：  
  `https://ghfast.top/https://github.com/Xiosn/DayPulse-Releases/releases/download/v1.0.2/DayPulse_1.0.2.wgt`

---

## 🔗 项目关联仓库导航

1. 📱 **[DayPulse 主客户端工程](https://github.com/Xiosn/DayPulse.git)**：基于 uni-app + Vue 3 的多端核心源码；
2. 🌐 **[DayPulse_H5 网页端](https://github.com/Xiosn/DayPulse_H5.git)**：独立 Web 站点源码；
3. 🚀 **[DayPulse_Server 服务端](https://github.com/Xiosn/DayPulse_Server.git)**：FastAPI 异步高性能后端与管理后台接口服务；
4. 📦 **[DayPulse-Releases 发布仓库](https://github.com/Xiosn/DayPulse-Releases.git)**（当前仓库）。
