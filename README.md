# Hymac自用HDT / Hymac HDT

> macOS 炉石传说酒馆战棋追踪器 + 一键重连工具。  
> A personal macOS Hearthstone Battlegrounds tracker with a one-click reconnect helper.

基于开源 [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker) 改造，参考 [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper) 的连接处理思路。  
Built on top of the open-source [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker), with the reconnect idea inspired by [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper).

**当前版本 / Current version:** 自用正式版 1.0 / Personal Stable Release 1.0  
**Release 附件 / Release asset:** `Hymac.HDT-1.0.dmg`

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
- 重连后尽量恢复已记录的对手阵容。
- 战棋面板可通过设置放到游戏右侧。

### 下载

到 **[Releases](../../releases)** 下载：

```text
Hymac.HDT-1.0.dmg
```

### 首次安装

1. 打开 DMG。
2. 把 `Hymac自用HDT.app` 拖进「应用程序」。
3. 运行 `① 本地重签（先跑这个）.command`。
4. 系统设置 → 隐私与安全性：
   - 勾选「屏幕录制」里的 `Hymac自用HDT`
   - 勾选「辅助功能」里的 `Hymac自用HDT`
5. 完全退出并重新打开 `Hymac自用HDT`。
6. 进炉石，看到覆盖层/阵容信息即安装成功。

### 版本更新

不需要先删除旧版本：

1. 打开新版 DMG。
2. 把新的 `Hymac自用HDT.app` 拖进「应用程序」。
3. 系统提示已存在同名 app 时，选择「替换」。
4. 替换后再次运行 `① 本地重签（先跑这个）.command`。
5. 打开 app 测试。

如果更新后看不到阵容或覆盖层，重新检查「屏幕录制」和「辅助功能」权限，必要时取消勾选后重新勾选，并重启 app。

### Clash 设置

一键重连功能需要 Clash Verge（mihomo 内核）：

1. 开启 TUN 模式。
2. 使用规则模式。
3. 确保游戏连接走 DIRECT。

Clash 在这里只是本地连接管理工具；追踪、胜率和阵容功能不依赖 Clash。

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
- Attempts to restore remembered opponent board states after reconnecting.
- Optional setting to place the Battlegrounds session panel on the right side.

### Download

Open **[Releases](../../releases)** and download:

```text
Hymac.HDT-1.0.dmg
```

### First-Time Installation

1. Open the DMG.
2. Drag `Hymac自用HDT.app` into `Applications`.
3. Run `① 本地重签（先跑这个）.command`.
4. In macOS System Settings → Privacy & Security, allow `Hymac自用HDT` under:
   - Screen Recording
   - Accessibility
5. Quit and reopen `Hymac自用HDT`.
6. Launch Hearthstone. If the overlay and board information appear, installation is complete.

### Updating From an Older Version

You do not need to manually delete the old app:

1. Open the new DMG.
2. Drag the new `Hymac自用HDT.app` into `Applications`.
3. Choose `Replace` when macOS asks.
4. Run `① 本地重签（先跑这个）.command` again.
5. Open the app and test it.

If the overlay or opponent boards do not appear after updating, re-check Screen Recording and Accessibility permissions. Toggle them off and on again if needed, then restart the app.

### Clash Setup

The reconnect helper requires Clash Verge with the mihomo core:

1. Enable TUN mode.
2. Use Rule mode.
3. Make sure the game connection stays DIRECT.

Clash is only used for local connection management. Tracking, win-rate simulation, and board information do not depend on Clash.

### Notes

- Personal-use, free, and for learning purposes.
- Use the reconnect helper responsibly.
- macOS only.
- MIT License, with original HSTracker copyright retained.
- Not affiliated with Blizzard, NetEase, HearthSim, or the official HSTracker project.
