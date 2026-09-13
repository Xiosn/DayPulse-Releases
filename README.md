# DayPulse-Releases (APK 分支)

> 本分支专用于托管与归档 **DayPulse (日脉) Android 全量安装包 (APK / AAB)** 及相关发布规范。

---

## 一、分支职责与定位

- **目标平台**：Android 7.0 (API Level 24) 及以上；
- **产物形态**：Android 全量安装包（扩展名 `.apk`）；
- **应用场景**：全新安装、跨大版本重构升级、涉及原生 SDK / 插件变更时的整包升级。

---

## 二、安装包命名规范

为确保版本回溯清晰与自动化脚本正常识别，全量安装包统一遵循以下命名格式：

```text
DayPulse_v{versionName}_{versionCode}.apk
```

**示例**：
- `DayPulse_v1.0.3_103.apk` (正式公测版)
- `DayPulse_v1.1.0_110.apk` (重大功能迭代版)

---

## 三、国内极速下载直链规范 (免翻墙高速直连)

在 GitHub Releases 发布后，统一配合开源 CDN 加速镜像生成直链：

```text
https://ghfast.top/https://github.com/Xiosn/DayPulse-Releases/releases/download/{tag}/DayPulse_v{versionName}_{versionCode}.apk
```

**直链示例**：
```text
https://ghfast.top/https://github.com/Xiosn/DayPulse-Releases/releases/download/v1.0.3/DayPulse_v1.0.3_103.apk
```

---

## 四、签名证书与安全校验

所有正规发布的 APK 均由专属私钥签名保护：
- **证书别名 (Alias)**：`daypulse`
- **签名算法**：SHA256withRSA
- **证书文件存放**：主工程 `DayPulse/打包资料/daypulse.keystore`
- **安全提示**：请勿安装或分发未经上述签名签署的未知来源 APK 安装包。

---

## 五、关联与导航

- 🔄 **热更新增量包**：请切换至 [`wgt`](https://github.com/Xiosn/DayPulse-Releases/tree/wgt) 分支；
- 🏠 **发布仓库总览**：请切换至 [`main`](https://github.com/Xiosn/DayPulse-Releases/tree/main) 分支；
- 💻 **客户端主源码**：前往 [`DayPulse 主工程`](https://github.com/Xiosn/DayPulse.git)。
