# DayPulse-Releases (WGT 分支)

> 本分支专用于托管与归档 **DayPulse (日脉) App 跨平台热更新差量资源包 (WGT)** 及相关发布规范。

---

## 一、分支职责与定位

- **产物形态**：uni-app 增量热更新资源包（扩展名 `.wgt`）；
- **应用场景**：日常功能迭代、UI 样式微调、Bug 修复等**不涉及原生底层 SDK / 插件新增或修改**的快速版本迭代；
- **核心优势**：体积小巧（通常 2MB ~ 5MB）、下载极速，用户端冷启动或后台静默更新，安装无需重新申请权限或重新安装覆盖。

---

## 二、热更新资源包命名规范与编号铁律

热更新包统一遵循以下命名格式：

```text
DayPulse_v{versionName}_{versionCode}.wgt
```

* **参数说明**：
  * `{versionName}`：面向用户的应用版本名称字符串（如 `0.05`、`1.0.3`），对应 `manifest.json` 的 `versionName`；
  * `{versionCode}`：供系统/服务端识别的纯数字递增版本代号（如 `5`、`103`），对应 `manifest.json` 的 `versionCode`。
* **命名示例**：
  * `DayPulse_v0.05_5.wgt`
  * `DayPulse_v0.06_6.wgt`
  * `DayPulse_v1.0.3_103.wgt`

### 避坑重点：
1. **严禁直接上传默认名**：HBuilderX 导出的 `__UNI__7CC4088.wgt` 必须在重命名后归档，避免历史版本相互覆盖。
2. **versionCode 必须递增**：客户端仅在检测到 `服务端 versionCode > 本地当前 versionCode` 时才会触发热更新，未递增编号将导致热更失效。

---

## 三、国内极速下载直链规范 (免翻墙高速直连)

配合开源 CDN 加速镜像生成直链，直接填入后台发布管理平台：

```text
https://ghfast.top/https://github.com/Xiosn/DayPulse-Releases/releases/download/{tag}/DayPulse_v{versionName}_{versionCode}.wgt
```

**直链示例**：
```text
https://ghfast.top/https://github.com/Xiosn/DayPulse-Releases/releases/download/v1.0.2/DayPulse_1.0.2.wgt
```

---

## 四、客户端安装与销毁生命周期

DayPulse 客户端已内置完整的热更新防护与垃圾回收机制：
1. **静默/弹窗检测**：在 `App.vue` 冷启动时请求服务端最新版本号；
2. **下载与校验**：比对当前 `versionCode`，若服务端版本更高则拉取 WGT 包；
3. **原生装载**：调用 `plus.runtime.install()` 完成资源替换；
4. **存储清理**：热更新完成后，由客户端内置的 `utils/cleaner.ts` 自动彻底清理释放临时 `.wgt` 缓存，杜绝手机存储膨胀。

---

## 五、已归档历史版本产物列表

| 版本名称 (`versionName`) | 内部版本号 (`versionCode`) | 文件名 | 文件大小 | SHA256 校验和 | 国内极速直链 |
|:---:|:---:|:---|:---:|:---|:---:|
| **v0.05.1** | **51** | `DayPulse_v0.05.1_51.wgt` | 16.36 MB | `baf03b96aa4567f4d9dbcfa5d3911d3cf029b4d61249b25ee81c05c7c490bc43` | [极速下载](https://ghfast.top/https://raw.githubusercontent.com/Xiosn/DayPulse-Releases/wgt/DayPulse_v0.05.1_51.wgt) |
| **v0.05** | **5** | `DayPulse_v0.05_5.wgt` | 16.36 MB | `3ccc4ba65053a67a366f45e404706affd84c8510e738b90a62bc8c403b1876a1` | [极速下载](https://ghfast.top/https://raw.githubusercontent.com/Xiosn/DayPulse-Releases/wgt/DayPulse_v0.05_5.wgt) |

---

## 六、关联与导航

- 📦 **全量安装包**：请切换至 [`apk`](https://github.com/Xiosn/DayPulse-Releases/tree/apk) 分支；
- 🏠 **发布仓库总览**：请切换至 [`main`](https://github.com/Xiosn/DayPulse-Releases/tree/main) 分支；
- 💻 **客户端主源码**：前往 [`DayPulse 主工程`](https://github.com/Xiosn/DayPulse.git)。
