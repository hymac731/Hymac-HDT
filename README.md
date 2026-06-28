# Hymac自用HDT / Hymac HDT

> macOS 炉石传说酒馆战棋追踪器 + 一键重连工具。  
> A personal macOS Hearthstone Battlegrounds tracker with a one-click reconnect helper.

基于开源 [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker) 改造，参考 [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper) 的连接处理思路。  
Built on top of the open-source [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker), with the reconnect idea inspired by [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper).

**当前版本 / Current version:** 自用正式版 1.2 / Personal Stable Release 1.2  
**Release 附件 / Release asset:** `Hymac.HDT-1.2.dmg`

---

## 中文说明

### 这是什么

这是一个 macOS 上的自用版 HSTracker，主要给炉石酒馆战棋使用。它保留 HSTracker 的对手阵容、胜率模拟、流派参考等能力，并额外集成了一键重连/跳过战斗动画功能。

仅供个人自用和学习交流，不是暴雪、网易或 HearthSim 官方工具。

### 功能

- 对手阵容侦察、胜率模拟、流派参考。
- 一键重连/跳过战斗动画：默认快捷键 `⌥1`，也可以点红色悬浮按钮。
- 悬浮按钮可拖动，位置会记住。
- 快捷键可在齿轮设置里修改。
- 齿轮设置里会显示 Clash 状态、进程识别、拔线模式、目标连接和安全状态。
- 可导出 Clash 诊断报告，默认保存到桌面。
- 重连后尽量恢复已记录的对手阵容。
- 战棋面板可通过设置放到游戏右侧。

### 1.2 更新内容

- 修复启动时可能反复弹出「辅助功能访问」提示的问题：正常打开 App 时只做静默检查；只有重新录制快捷键时才会主动请求辅助功能权限。
- 更新安装/升级说明：推荐通过终端运行本地重签脚本，避免新版 macOS 拦截 `.command` 文件。
- 新增「拔线设置」看板：在红色拔线按钮旁边的齿轮里，可以直接看到 Clash 是否连接、进程识别是否可用、当前拔线模式、目标连接和安全状态。
- 新增「最近一次拔线耗时」：显示读取连接、匹配目标、删除连接和总耗时，方便判断慢是在 HDT 本地操作，还是炉石后续重连阶段。
- 新增「导出诊断」：一键生成诊断报告，默认保存到桌面，方便排查不同 Clash Verge 环境下的兼容问题。
- 优化兼容模式：当 Clash Verge 没有提供炉石进程路径时，使用更谨慎的 1119 端口纯 IP 连接规则，尽量只断炉石游戏服连接。
- 保留原有能力：对手阵容、胜率模拟、流派参考、右侧战棋面板、一键重连/跳过战斗动画。

### 下载

到 **[Releases](../../releases)** 下载：

```text
Hymac.HDT-1.2.dmg
```

### 首次安装

1. 打开 DMG。
2. 把 `Hymac自用HDT.app` 拖进「应用程序」。
3. 打开「终端」，运行：

```bash
bash "/Volumes/Hymac自用HDT 1.2/① 本地重签（先跑这个）.command"
```

4. 如果终端提示找不到文件，先运行 `ls /Volumes`，确认 DMG 挂载出来的名字，再替换上面命令里的卷名。
5. 系统设置 → 隐私与安全性：
   - 勾选「屏幕录制」里的 `Hymac自用HDT`
   - 勾选「辅助功能」里的 `Hymac自用HDT`
6. 完全退出并重新打开 `Hymac自用HDT`。
7. 进炉石，看到覆盖层/阵容信息即安装成功。

如果 macOS 提示无法验证 `.command` 是否包含恶意软件，不要点「移到废纸篓」，直接用上面的终端命令运行即可。

### 版本更新

不需要先删除旧版本：

1. 打开新版 DMG。
2. 把新的 `Hymac自用HDT.app` 拖进「应用程序」。
3. 系统提示已存在同名 app 时，选择「替换」。
4. 替换后再次打开「终端」，运行：

```bash
bash "/Volumes/Hymac自用HDT 1.2/① 本地重签（先跑这个）.command"
```

5. 打开 app 测试。

如果更新后看不到阵容或覆盖层，重新检查「屏幕录制」和「辅助功能」权限，必要时取消勾选后重新勾选，并重启 app。

### Clash 设置

一键重连功能需要 Clash Verge（mihomo 内核）：

1. 开启 TUN 模式。
2. 使用规则模式。
3. 确保游戏连接走 DIRECT。

Clash 在这里只是本地连接管理工具；追踪、胜率和阵容功能不依赖 Clash。

### 一键重连原理

自用版HDT 不会关闭 Wi-Fi，也不会让整台电脑断网。它会通过 Clash Verge 的本地连接接口读取当前网络连接，识别炉石的游戏服连接后，只删除这条连接。炉石客户端会进入短暂断线并自动重连，从而跳过一部分战斗动画。

正常情况下会优先使用 Clash 提供的 Hearthstone 进程路径来识别目标连接；如果个别电脑的 Clash Verge 不提供进程路径，1.2 会进入兼容模式，只匹配更谨慎的 1119 端口炉石纯 IP 连接。

点红色「拔线」按钮旁边的齿轮，可以查看当前 Clash 状态：

```text
Clash: 已连接
进程识别: 可用 / 不可用
拔线模式: 稳定模式 / 兼容模式 / 不可用
目标连接: 当前将断开的连接
安全状态: 可执行 / 不可执行
```

如果一键重连异常，点「导出诊断」。报告会保存到桌面，文件名类似：

```text
hymac-hdt-clash-diagnostic-20260626-1905.txt
```

把这个 txt 发给维护者即可排查。

### 说明

- 个人自用、免费、学习交流。
- 一键重连功能请理性使用。
- 仅支持 macOS。
- 遵循 MIT License，保留原 HSTracker 版权声明。
- 与 Blizzard、网易、HearthSim 官方无关。

---

## English

### What This Is

Hymac HDT is a personal macOS build of HSTracker for Hearthstone Battlegrounds. It keeps HSTracker's opponent board tracking, win-rate simulation, and Battlegrounds helper panels, and adds a one-click reconnect helper for skipping combat animations.

This is a personal-use tool for learning and convenience. It is not an official Blizzard, NetEase, HearthSim, or HSTracker release.

### Features

- Opponent board tracking, win-rate simulation, and Battlegrounds helper panels.
- One-click reconnect / combat animation skip.
- Default hotkey: `Option + 1`.
- Floating reconnect button with remembered position.
- Customizable hotkey through the gear button.
- Clash status, process recognition, reconnect mode, target connection, and safety status in the gear panel.
- Clash diagnostic export. The report is saved to the Desktop by default.
- Attempts to restore remembered opponent board states after reconnecting.
- Optional setting to place the Battlegrounds session panel on the right side.

### Version 1.2 Updates

- Fixed repeated macOS Accessibility permission prompts on normal app launch. The app now checks permission silently at startup and only prompts when recording a new hotkey.
- Updated install/update instructions. Running the local re-sign script through Terminal is recommended to avoid `.command` blocking on newer macOS versions.
- Added a reconnect settings panel next to the red reconnect button. It shows Clash connection status, process recognition, reconnect mode, target connection, and safety status.
- Added last reconnect timing. It shows connection read time, target matching time, delete time, and total local HDT time. This helps separate local HDT work from the later Hearthstone reconnect phase.
- Added diagnostic export. The report is saved to the Desktop and helps troubleshoot different Clash Verge setups.
- Improved compatibility mode. If Clash Verge does not provide the Hearthstone process path, 1.2 uses a stricter 1119-port pure-IP fallback to avoid disconnecting unrelated traffic.
- Existing tracker features remain: opponent boards, win-rate simulation, Battlegrounds helper panels, right-side panel option, and one-click reconnect / combat animation skip.

### Download

Open **[Releases](../../releases)** and download:

```text
Hymac.HDT-1.2.dmg
```

### First-Time Installation

1. Open the DMG.
2. Drag `Hymac自用HDT.app` into `Applications`.
3. Open Terminal and run:

```bash
bash "/Volumes/Hymac自用HDT 1.2/① 本地重签（先跑这个）.command"
```

4. If Terminal says the file cannot be found, run `ls /Volumes`, check the mounted DMG name, and replace the volume name in the command above.
5. In macOS System Settings → Privacy & Security, allow `Hymac自用HDT` under:
   - Screen Recording
   - Accessibility
6. Quit and reopen `Hymac自用HDT`.
7. Launch Hearthstone. If the overlay and board information appear, installation is complete.

If macOS says it cannot verify whether the `.command` file contains malware, do not move it to Trash. Use the Terminal command above instead.

### Updating From an Older Version

You do not need to manually delete the old app:

1. Open the new DMG.
2. Drag the new `Hymac自用HDT.app` into `Applications`.
3. Choose `Replace` when macOS asks.
4. Open Terminal and run:

```bash
bash "/Volumes/Hymac自用HDT 1.2/① 本地重签（先跑这个）.command"
```

5. Open the app and test it.

If the overlay or opponent boards do not appear after updating, re-check Screen Recording and Accessibility permissions. Toggle them off and on again if needed, then restart the app.

### Clash Setup

The reconnect helper requires Clash Verge with the mihomo core:

1. Enable TUN mode.
2. Use Rule mode.
3. Make sure the game connection stays DIRECT.

Clash is only used for local connection management. Tracking, win-rate simulation, and board information do not depend on Clash.

### How the Reconnect Helper Works

Hymac HDT does not turn off Wi-Fi and does not disconnect the whole Mac. It reads the current connection list through Clash Verge's local connection API, identifies the Hearthstone game-server connection, and closes only that connection. Hearthstone then briefly disconnects and reconnects, which can skip part of the combat animation.

When available, the tool uses Clash's Hearthstone process path to identify the target connection. On machines where Clash Verge does not provide the process path, version 1.2 uses a stricter compatibility rule for the 1119-port pure-IP Hearthstone connection.

Click the gear button next to the red reconnect button to check Clash status:

```text
Clash: Connected
Process recognition: Available / Unavailable
Reconnect mode: Stable / Compatibility / Unavailable
Target connection: The connection that will be closed
Safety status: Executable / Not executable
```

If reconnect does not work correctly, click `导出诊断` / `Export Diagnostic`.
The report is saved to the Desktop with a name like:

```text
hymac-hdt-clash-diagnostic-20260626-1905.txt
```

### Notes

- Personal-use, free, and for learning purposes.
- Use the reconnect helper responsibly.
- macOS only.
- MIT License, with original HSTracker copyright retained.
- Not affiliated with Blizzard, NetEase, HearthSim, or the official HSTracker project.
