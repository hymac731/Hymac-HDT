# Hymac自用HDT / Hymac HDT

> macOS 炉石传说酒馆战棋追踪器 + 一键重连工具。  
> A personal macOS Hearthstone Battlegrounds tracker with a one-click reconnect helper.

基于开源 [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker) 改造，参考 [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper) 的连接处理思路。  
Built on top of the open-source [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker), with the reconnect idea inspired by [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper).

![炉石传说酒馆战棋第 14 赛季](assets/battlegrounds-season-14.png)

- **当前版本 / Current version:** 自用正式版 2.0.1 / Personal Stable Release 2.0.1
- **适用赛季 / Battlegrounds season:** 酒馆战棋第 14 赛季 / Battlegrounds Season 14
- **游戏版本 / Hearthstone version:** Hearthstone 36.2
- **Release 附件 / Release asset:** `Hymac.HDT-2.0.1.dmg`

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
- 齿轮设置里会显示 Clash 状态、进程识别、拔线模式、目标连接和当前状态。
- 可导出 Clash 诊断报告，默认保存到桌面。
- 重连后尽量恢复已记录的对手阵容。
- 酒馆战棋战绩面板可以拖动、独立调整宽度、整体缩放并锁定位置。

### 2.0.1 更新内容

- 底层升级到 HSTracker 3.6.3，适配 Hearthstone 36.2 和酒馆战棋第 14 赛季，并更新卡牌数据。
- 合入上游 Hearthstone、Battlegrounds、Bob's Buddy、Duos 和覆盖层相关修复。
- 新增本机游戏连接精确匹配：自动对应 macOS 中的炉石连接与 Clash 连接，不再依赖固定的 `1119` 或 `3724` 端口。
- 未立即找到连接时会自动重新匹配约 3 秒，并在悬浮按钮和齿轮面板给出下一步提示。
- 酒馆战棋战绩面板新增拖动、独立宽度调整、整体缩放和锁定功能。
- 新增 Clash `find-process-mode` 检查。检测到 `strict` 时，齿轮面板会引导点击「修复进程识别」改为 `always`，并读取确认结果。
- 点击「拔线」时，若战棋已结束，或 Bob's Buddy 当前模拟同时为失败 100% 且致死 100%，则不执行拔线并短暂显示「没了 下一把吧」。
- 修复酒馆面板最近对局无法显示英雄、名次和 MMR 的问题，并补齐“可用随从 / 禁用随从”标题。
- 保留拔线按钮、状态看板、耗时显示、诊断导出、阵容/面板恢复、自定义图标和关闭自动更新。

### 下载

到 **[Releases](../../releases)** 下载：

```text
Hymac.HDT-2.0.1.dmg
```

### 首次安装

1. 打开 DMG。
2. 把 `Hymac自用HDT.app` 拖进「应用程序」。
3. 打开「终端」，运行：

```bash
bash "/Volumes/Hymac自用HDT 2.0.1/① 本地重签（先跑这个）.command"
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
bash "/Volumes/Hymac自用HDT 2.0.1/① 本地重签（先跑这个）.command"
```

5. 打开 app 测试。

如果更新后看不到阵容或覆盖层，重新检查「屏幕录制」和「辅助功能」权限，必要时取消勾选后重新勾选，并重启 app。

### Clash 设置

一键重连功能需要 Clash Verge Rev（mihomo 内核）。第一次使用请先完成以下设置：

1. 从 [Clash Verge Rev 官方 GitHub Releases](https://github.com/Clash-Verge-rev/clash-verge-rev/releases) 下载并安装 macOS 版本。
2. 打开 Clash Verge Rev，并在使用 hymac版HDT 时保持运行。**一键重连不需要导入订阅。**
3. 开启 TUN 模式。
4. 使用规则模式。
5. 确保游戏连接走 DIRECT。

Clash 在这里只是本地连接管理工具；追踪、胜率和阵容功能不依赖 Clash。

进程识别需要进入实际对局后才会出现；停留在游戏等待页面时显示未识别是正常现象。如果已经进入对局仍无法识别，请打开红色「拔线」按钮旁边的齿轮，按照面板提示点击「修复进程识别」，再点击「刷新状态」。

### 一键重连原理

自用版HDT 不会关闭 Wi-Fi，也不会让整台电脑断网。它会通过 Clash Verge 的本地连接接口读取当前网络连接，识别炉石的游戏服连接后，只删除这条连接。炉石客户端会进入短暂断线并自动重连，从而跳过一部分战斗动画。

2.0.1 会读取 macOS 本机已经建立的 Hearthstone TCP 连接，再与 Clash 中的纯 IP TCP + TUN 连接完整对应，因此不依赖固定游戏端口，也不会把带域名的战网连接当作拔线目标。进入实际对局后如果首次未匹配到，系统会在约 3 秒内自动重试，并提示下一步操作。

点红色「拔线」按钮旁边的齿轮，可以查看当前 Clash 状态：

```text
Clash: 已连接
Clash 进程识别: 不依赖
本机进程识别: 可用 / 未找到炉石连接
Clash 进程模式: always / strict
拔线模式: 本机精确匹配 / 需进入游戏对局 / 正在匹配连接
目标连接: 当前将断开的连接
当前状态: 可以拔线 / 暂不可拔线
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
- Clash status, process recognition, reconnect mode, target connection, and current status in the gear panel.
- Clash diagnostic export. The report is saved to the Desktop by default.
- Attempts to restore remembered opponent board states after reconnecting.
- Move, resize the width, uniformly scale, and lock the Battlegrounds session statistics panel.

### Version 2.0.1 Updates

- Updated the upstream base to HSTracker 3.6.3 for Hearthstone 36.2 and Battlegrounds Season 14, with updated card data.
- Included upstream Hearthstone, Battlegrounds, Bob's Buddy, Duos, and overlay fixes.
- Exactly matches the local macOS Hearthstone connection to its Clash TCP + TUN connection without relying on a fixed `1119` or `3724` port.
- Automatically retries for about three seconds and provides clear guidance when the connection is not immediately available.
- Adds moving, independent width adjustment, uniform scaling, and locking for the Battlegrounds session statistics panel.
- Added Clash `find-process-mode` detection. When it is `strict`, the gear panel guides the user to select `修复进程识别` / Repair Process Recognition and verifies the change to `always`.
- After Reconnect is clicked, the action is blocked if the Battlegrounds game has ended or the current Bob's Buddy simulation reports both 100% loss and 100% player lethal.
- Kept the reconnect button, status panel, timing display, diagnostic export, overlay restoration, custom icon, and disabled automatic updates.

### Download

Open **[Releases](../../releases)** and download:

```text
Hymac.HDT-2.0.1.dmg
```

### First-Time Installation

1. Open the DMG.
2. Drag `Hymac自用HDT.app` into `Applications`.
3. Open Terminal and run:

```bash
bash "/Volumes/Hymac自用HDT 2.0.1/① 本地重签（先跑这个）.command"
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
bash "/Volumes/Hymac自用HDT 2.0.1/① 本地重签（先跑这个）.command"
```

5. Open the app and test it.

If the overlay or opponent boards do not appear after updating, re-check Screen Recording and Accessibility permissions. Toggle them off and on again if needed, then restart the app.

### Clash Setup

The reconnect helper requires Clash Verge Rev with the mihomo core. For first-time setup:

1. Download and install the macOS build from the [official Clash Verge Rev GitHub Releases](https://github.com/Clash-Verge-rev/clash-verge-rev/releases).
2. Open Clash Verge Rev and keep it running while using Hymac HDT. **No proxy subscription is required for the reconnect helper.**
3. Enable TUN mode.
4. Use Rule mode.
5. Make sure the game connection stays DIRECT.

Clash is only used for local connection management. Tracking, win-rate simulation, and board information do not depend on Clash.

Process recognition becomes available only after entering an actual match. It is normal for the waiting screen to show no recognized Hearthstone connection. If recognition is still unavailable during a match, open the gear panel next to the red Reconnect button, follow the prompt to select `修复进程识别` / Repair Process Recognition, and then refresh the status.

### How the Reconnect Helper Works

Hymac HDT does not turn off Wi-Fi and does not disconnect the whole Mac. It reads the current connection list through Clash Verge's local connection API, identifies the Hearthstone game-server connection, and closes only that connection. Hearthstone then briefly disconnects and reconnects, which can skip part of the combat animation.

Version 2.0.1 reads the established local Hearthstone TCP connection and exactly matches it to the corresponding pure-IP TCP + TUN connection in Clash. It does not rely on a fixed game port and does not select Battle.net domain connections. If the first match is unavailable during an actual game, it retries automatically for about three seconds and shows the next step.

Click the gear button next to the red reconnect button to check Clash status:

```text
Clash: Connected
Clash process recognition: Not required
Local process recognition: Available / No Hearthstone connection
Clash process mode: always / strict
Reconnect mode: Exact local match / Enter an actual game / Matching connection
Target connection: The connection that will be closed
Current status: Ready / Not ready
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
