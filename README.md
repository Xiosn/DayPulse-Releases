# DayPulse-Releases (日脉官方发行归档)

> 本仓库专用于统一托管与归档 **DayPulse (日脉)** 的全量安装包 (APK) 与差量热更新资源包 (WGT)。

---

## 一、版本号管理铁律（全局单一递增主线）

为彻底避免 APK 底座与 WGT 热更新版本倒挂，本项目严格遵循以下规范：

1. **`versionCode`（纯数字代号）全局唯一且严格单调递增**：
   - 无论是发布全量 APK 还是增量 WGT，`versionCode` **必须严格按顺序 +1 递增**；
   - 客户端版本检测逻辑：`只要 服务端 versionCode > 本地当前 versionCode`，即触发更新。
2. **`versionName`（版本名称字符串）语义化规范**：
   - **大版本 / 次版本（X.Y）**：对应 **全量安装包 APK**（当涉及原生插件、底层 SDK、权限变更、无法通过 WGT 解决的改动时，升级 X 或 Y，例如 `0.06.0`、`0.07.0`）；
   - **补丁修订号（Z）**：对应 **热更新包 WGT**（纯前端 JS/Vue/CSS 修复与优化，例如 `0.06.1`、`0.06.2`、`0.06.3`）。

---

## 二、仓库目录结构

整个发行仓库统一汇聚于 `main` 主分支，按产物类型分目录清晰归档：

```text
DayPulse-Releases/
├── apk/                  # Android 全量安装包 (.apk)
│   ├── DayPulse_v0.06.3_63.apk
│   └── DayPulse_v0.07.0_70.apk
├── wgt/                  # 跨平台增量热更新包 (.wgt)
│   ├── DayPulse_v0.06.2_62.wgt
│   ├── DayPulse_v0.06.3_63.wgt
│   ├── DayPulse_v0.06.4_64.wgt
│   └── DayPulse_v0.07.2_72.wgt
└── README.md
```

---

## 三、国内极速免翻墙下载直链规范

所有产物均支持通过开源 CDN 镜像直连高速下载：

### 1. 全量安装包 (APK) 直链模板
```text
https://gh-proxy.com/https://raw.githubusercontent.com/Xiosn/DayPulse-Releases/main/apk/DayPulse_v{versionName}_{versionCode}.apk
```

**最新 APK 示例：**
- [DayPulse_v0.07.0_70.apk](https://gh-proxy.com/https://raw.githubusercontent.com/Xiosn/DayPulse-Releases/main/apk/DayPulse_v0.07.0_70.apk)

### 2. 增量热更新 (WGT) 直链模板
```text
https://ghproxy.net/https://raw.githubusercontent.com/Xiosn/DayPulse-Releases/main/wgt/DayPulse_v{versionName}_{versionCode}.wgt
```

**最新 WGT 示例：**
- [DayPulse_v0.07.2_72.wgt](https://ghproxy.net/https://raw.githubusercontent.com/Xiosn/DayPulse-Releases/main/wgt/DayPulse_v0.07.2_72.wgt)

---

## 四、安全校验与签名
- **证书别名**：`daypulse`
- **签名算法**：SHA256withRSA
- **证书路径**：`DayPulse/打包资料/daypulse.keystore`
