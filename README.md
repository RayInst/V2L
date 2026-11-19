# V2L — Video to Laser

**[中文](#中文说明) | [English](#english)**

---

## 中文说明

**V2L（Video to Laser）** 是一款面向演艺现场的 **视频转激光 + 大屏同步工作站**（Windows 64 位）。它把视频 / NDI / 测试源实时提取为矢量激光图形，经多 ZONE 拼接与振镜优化后，直接推送给 **Pangolin BEYOND**，同时输出大屏窗口与 NDI，并支持毫秒级延时对位与时间码联动。

### 核心特性

| 模块 | 说明 |
| --- | --- |
| **多轨时间线** | 视频 / 音频 / 测试源 / NDI / `.v2lcache` 多轨编辑；缩放、裁剪入出点、切分、复制、拖动重排；`←/→` 逐帧微调；`I/O` 设置 A-B 循环区间 |
| **双模式视觉提取** | 近似多边形跟踪（轮廓、镂空、嵌套）与图块 Blob 圆形跟踪；近线合并、单线化、自动屏蔽视频外边框 |
| **多 ZONE 拼接** | 规则网格（如 1×3、2×2）、重叠比例、硬裁剪 / 中心归属、镜像、偏移与缩放、映射到 BEYOND Zone 1~20 |
| **毫秒级延时同步** | 视频 / NDI、激光全局基准、**每个 ZONE 独立附加延时**，滚轮 1 ms 微调；内置「旋转长条」测试素材便于对位 |
| **离线烘焙（授权版）** | 生成 `.v2lcache` 与按 ZONE 切分的标准 ILDA（`.ild`），时间线按帧号锁帧回放 |
| **时间码联动** | Art-Net UDP / LTC 音频从机同步，亦可作为 Art-Net 时间码主机广播 |
| **输出** | 独立大屏窗口（可全屏）、NDI 输入 / 输出、本地音频同步播放 |
| **双语界面** | 首次启动自动跟随系统语言；顶部可随时切换 中 / EN；`F1` 打开内置完整参数手册 |

### 下载与运行

1. 在 [Releases](https://github.com/RayInst/V2L/releases) 页面下载最新的 `V2L_Win64.zip` 并解压到任意目录（路径尽量避免特殊字符）。
2. 如需激光硬件输出，先启动 **Pangolin BEYOND**，再运行 `V2L.exe`。
3. 首次启动内置测试动画，无需外部素材即可调试；关闭软件时自动保存工程与时间线。

压缩包已内置 `BEYONDIO.dll`、NDI 运行库、便携 FFmpeg 与 MSVC 运行库，免安装、零配置。

### 授权与试用

- 未激活：单次运行提供 **30 分钟实时模式试用**，期间激光输出每隔 10 秒叠加 2 秒 `DEMO` 字样；试用版不包含离线同步、离线烘焙、ILDA 导出与 `.v2lcache` 导入。
- 激活：点击顶部「载入」后的授权按钮，粘贴 `V2L-` 激活码联网激活，或导入离线 `license.dat`；授权绑定本机硬件特征码，可联网解绑换机。
- 购买授权请访问 **[www.r1gy.com](https://www.r1gy.com)**。

### 版本更新

软件启动时会匿名检查本仓库 Releases 页面是否有新版本，发现新版本时顶部会出现更新提示；也可点击顶部 `V2L v版本号` 徽章手动检查。

### 系统要求

- Windows 10 / 11 64 位
- 激光输出需安装 Pangolin BEYOND
- 独立显卡与现代 GPU 驱动（界面基于 wgpu / glow 渲染）

---

## English

**V2L (Video to Laser)** is a live-show **video-to-laser and LED-wall sync workstation** for Windows x64. It extracts vector laser graphics from video, NDI streams or test patterns in real time, tiles them across multiple zones, optimizes the galvo point stream, and sends it straight to **Pangolin BEYOND** — while also driving a screen output window and NDI, with millisecond-level delay alignment and timecode sync.

### Key Features

| Module | Description |
| --- | --- |
| **Multi-track timeline** | Video / audio / test pattern / NDI / `.v2lcache` tracks; zoom, trim In/Out, split, duplicate, drag-reorder; `←/→` frame nudging; `I/O` to set an A-B loop region |
| **Dual vision modes** | Approx-polygon tracking (contours, holes, nesting) and Blob-circle tracking; line merging, single-line collapse, automatic video-border masking |
| **Multi-zone tiling** | Regular grids (e.g. 1×3, 2×2), overlap ratio, hard clip / centroid assign, flip, offset & scale, map to BEYOND Zones 1–20 |
| **Millisecond delay sync** | Video/NDI delay, global laser delay and **per-zone extra delay**, 1 ms mouse-wheel steps; built-in "Spinning Bar" test pattern for calibration |
| **Offline baking (licensed)** | Generate `.v2lcache` and per-zone standard ILDA (`.ild`); frame-locked playback on the timeline |
| **Timecode** | Art-Net UDP / LTC audio slave sync, or broadcast as an Art-Net timecode master |
| **Outputs** | Standalone screen window (fullscreen capable), NDI in/out, synchronized local audio |
| **Bilingual UI** | Follows the OS language on first launch; switch ZH / EN anytime; press `F1` for the built-in full parameter manual |

### Download & Run

1. Download the latest `V2L_Win64.zip` from the [Releases](https://github.com/RayInst/V2L/releases) page and extract it anywhere.
2. For laser output, start **Pangolin BEYOND** first, then run `V2L.exe`.
3. A built-in test animation lets you tune everything without external media; project and timeline are auto-saved on exit.

The package already bundles `BEYONDIO.dll`, the NDI runtime, portable FFmpeg and MSVC runtimes — no installation or configuration required.

### Licensing & Trial

- Unlicensed: each launch offers a **30-minute Realtime trial**, with a 2-second `DEMO` laser watermark every 10 seconds. The trial excludes Offline Sync, offline baking, ILDA export and `.v2lcache` import.
- Activation: click the license button after "Load", paste a `V2L-` code to activate online, or import an offline `license.dat`. Licenses are bound to your hardware ID and can be released online to move machines.
- Purchase licenses at **[www.r1gy.com](https://www.r1gy.com)**.

### Updates

On startup V2L anonymously checks this repository's Releases page for a newer version and shows an update badge in the top bar. You can also click the `V2L v<version>` badge to check manually.

### System Requirements

- Windows 10 / 11 x64
- Pangolin BEYOND installed for laser output
- A modern GPU driver (UI renders via wgpu / glow)
