# Hymac自用HDT / Hymac HDT

> macOS 炉石传说酒馆战棋追踪器 + 一键重连工具。  
> A personal macOS Hearthstone Battlegrounds tracker with a one-click reconnect helper.

基于开源 [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker) 改造，参考 [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper) 的连接处理思路。  
Built on top of the open-source [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker), with the reconnect idea inspired by [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper).

![炉石传说酒馆战棋第 14 赛季](assets/battlegrounds-season-14.png)

- **当前版本 / Current version:** 自用正式版 2.5 / Personal Stable Release 2.5
- **正式构建 / Release build:** 2503
- **适用赛季 / Battlegrounds season:** 酒馆战棋第 14 赛季 / Battlegrounds Season 14
- **游戏版本 / Hearthstone version:** Hearthstone 36.4.2
- **Release 附件 / Release asset:** `Hymac.HDT-2.5.dmg`

> [!CAUTION]
> **🔴 安装或升级后必须检查覆盖层权限**
>
> `① 本地重签（安装后跑一次）.command` **不能自动打开 macOS 隐私权限**。替换新版并完成本地重签后，请进入“系统设置 → 隐私与安全性 → 屏幕与系统音频录制”，确认 `Hymac自用HDT` 已开启，然后完全退出并重新打开 App。否则可能只看到红色“拔线”按钮，看不到阵容、胜率和战绩覆盖层。

> [!IMPORTANT]
> **🔴 悬浮组件可以移动和调整**
>
> - 红色“拔线”按钮：直接拖动到想要的位置，App 会记住位置。
> - 酒馆战棋战绩面板：点击面板上方的锁解锁，拖动六点区域移动；可调整“宽度”和“缩放”，完成后再次锁定。

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

### 2.5 更新内容

- Meta/阵容指南支持左侧解锁、拖动、锁定和复位，记住位置；向上移动已实战确认可用。
- 修复冰箱（寒冰屏障）保护下的出局误判，调整拔线资格判断；**待实战验证**。
- 覆盖层默认在炉石切到后台时隐藏。
- 保留 2.4 的连接识别、拔线重试、阵容恢复与战绩看板。

### 2.4 更新内容

- 底座更新至 HSTracker 3.6.9。
- 新增本机对局记录保存：已识别记录默认仅保存在本机，不上传、不共享。
- 阵容指南可按本局已识别的可用种族筛选，并支持滚动浏览；赛前或种族池尚未识别时会显示全量内容。
- 修复“随从与流派指南”攻略详情显示：固定在标准面板宽度内，中文文本自动换行、卡图完整排列，内容仅在面板内纵向滚动。
- 保留一键重连、对手阵容、胜率模拟与可调整的战绩面板。

### 2.3 更新内容

- 底座更新至上游 HSTracker 3.6.8，适配炉石传说 36.4.2（酒馆战棋）。
- 同步 macOS 稳定性、覆盖层与日志读取相关修复：覆盖层 / 卡图改为线程安全构建，修复 macOS 26 上覆盖层与卡牌 HUD 等后台线程崩溃，并修复重复启动日志读取器的问题。
- 同步酒馆战棋与 Bob's Buddy 相关修复（Tavern Pinning 残留、Tier7 预加载、composition 指南加载、session MMR 格式化，以及 Bob's Buddy 一批计算与显示修复）。
- 新增：战绩面板“最近对局”显示数量可在 **5 场 / 8 场 / 10 场** 之间选择，默认 8 场。
- 保留一键拔线、本机连接精确匹配、Clash 进程识别修复引导、阵容恢复、版本提醒、战绩面板调整和自定义外观。

### 下载

到 **[Releases](../../releases)** 下载：

```text
Hymac.HDT-2.5.dmg
```

### 首次安装

1. 打开 DMG。
2. 把 `Hymac自用HDT.app` 拖进「应用程序」。
3. **默认方式（推荐）：在 DMG 中右键 `① 本地重签（安装后跑一次）.command`，选择「打开」，等待终端显示“完成”。** 日常安装只用这一步即可完成重签，无需输入任何终端命令。
4. 只有当 macOS 拦截右键打开、无法打开这个 `.command` 文件、或运行后没有显示“完成”时，才把下面的终端命令作为**排障备用**（不要每次安装都手动输入）：

```bash
bash "/Volumes/Hymac自用HDT 2.5/① 本地重签（安装后跑一次）.command"
```

5. 如果终端提示找不到文件，先运行 `ls /Volumes`，确认 DMG 挂载出来的名字，再替换上面命令里的卷名。
6. 系统设置 → 隐私与安全性：
   - 勾选「屏幕录制」里的 `Hymac自用HDT`
   - 勾选「辅助功能」里的 `Hymac自用HDT`
   - 本地重签不能自动勾选这些权限，必须由用户手动确认
7. 完全退出并重新打开 `Hymac自用HDT`。
8. 进炉石，看到覆盖层/阵容信息即安装成功。

同一个版本日常打开不需要重复重签，也不需要重复输入终端命令。

### 版本更新

不需要先删除旧版本：

1. 打开新版 DMG。
2. 把新的 `Hymac自用HDT.app` 拖进「应用程序」。
3. 系统提示已存在同名 app 时，选择「替换」。
4. 替换完成后，**默认方式（推荐）：在 DMG 中右键 `① 本地重签（安装后跑一次）.command`，选择「打开」，重签一次。**
5. 只有当 macOS 拦截右键打开、无法打开这个 `.command` 文件、或运行后没有显示“完成”时，才把下面的终端命令作为**排障备用**：

```bash
bash "/Volumes/Hymac自用HDT 2.5/① 本地重签（安装后跑一次）.command"
```

6. 进入“系统设置 → 隐私与安全性 → 屏幕与系统音频录制”，重新确认 `Hymac自用HDT` 的开关已经打开。
7. 完全退出并重新打开 App 后使用。

如果更新后看不到阵容或覆盖层，重新检查「屏幕录制」和「辅助功能」权限，必要时取消勾选后重新勾选，并重启 app。

同一个版本日常打开不需要再次重签；只有首次安装或用新版 app 覆盖旧版后才需要运行一次。

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

2.3 继续读取 macOS 本机已经建立的 Hearthstone TCP 连接，再与 Clash 中的纯 IP TCP + TUN 连接完整对应，因此不依赖固定游戏端口，也不会把带域名的战网连接当作拔线目标。进入实际对局后如果首次未匹配到，系统会在约 3 秒内自动重试，并提示下一步操作。

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

> [!CAUTION]
> **After every install or upgrade, verify overlay permission.** The local re-sign command cannot enable macOS privacy permissions automatically. After replacing and re-signing the app, open System Settings → Privacy & Security → Screen & System Audio Recording, make sure `Hymac自用HDT` is enabled, then fully quit and reopen the app. Otherwise, the red Reconnect button may appear while board, combat-odds, and session overlays remain hidden.

> [!IMPORTANT]
> **Floating components are adjustable.** Drag the red Reconnect button to move it. For the Battlegrounds session panel, click the lock to unlock it, drag the six-dot handle, adjust Width or Scale, and lock it again when finished.

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

### Version 2.4 Updates

- Updates the base to HSTracker 3.6.9.
- Saves recognized match records locally by default; records are not uploaded or shared.
- Comp guides can filter to the races recognized in the current lobby and can be scrolled. The full list is shown before lobby races are known.
- Fixes Comp Guide detail layout: the detail remains within the standard panel width, text wraps, card art is fully arranged, and content scrolls only inside the panel.
- Retains the reconnect helper, opponent tracking, combat odds, and the adjustable session panel.

### Version 2.3 Updates

- Updates the base to upstream HSTracker 3.6.8, targeting Hearthstone 36.4.2 (Battlegrounds).
- Synchronizes macOS stability, overlay, and log-reading fixes: overlay / card artwork is now built in a thread-safe way, fixing macOS 26 overlay and card HUD background-thread crashes, and fixing a duplicate-log-reader issue.
- Synchronizes Battlegrounds and Bob's Buddy fixes (Tavern Pinning persistence, Tier7 pre-lobby, composition guide loading, session MMR formatting, plus a batch of Bob's Buddy simulation and display fixes).
- New: the Battlegrounds session panel's "Recent games" count is selectable between **5 / 8 / 10**, defaulting to 8.
- Other stability and interface polish.
- Retains the reconnect helper, exact local connection matching, Clash repair guidance, opponent-board restoration, update reminders, adjustable session panel, and Hymac appearance.

### Download

Open **[Releases](../../releases)** and download:

```text
Hymac.HDT-2.5.dmg
```

### First-Time Installation

1. Open the DMG.
2. Drag `Hymac自用HDT.app` into `Applications`.
3. **Default (recommended): right-click `① 本地重签（安装后跑一次）.command` in the DMG, choose `Open`, and wait for Terminal to report completion.** This is all you need to re-sign on a normal install; no Terminal command is required.
4. Only if macOS blocks right-click-open, the `.command` file cannot be opened, or it does not report completion, use this Terminal command as a **fallback / troubleshooting step** (do not type it manually on every install):

```bash
bash "/Volumes/Hymac自用HDT 2.5/① 本地重签（安装后跑一次）.command"
```

5. If Terminal says the file cannot be found, run `ls /Volumes`, check the mounted DMG name, and replace the volume name in the command above.
6. In macOS System Settings → Privacy & Security, allow `Hymac自用HDT` under:
   - Screen Recording
   - Accessibility
   - The local re-sign command cannot enable these permissions for you; they require manual confirmation.
7. Quit and reopen `Hymac自用HDT`.
8. Launch Hearthstone. If the overlay and board information appear, installation is complete.

Daily launches of the same installed version do not require re-signing or re-entering the Terminal command.

### Updating From an Older Version

You do not need to manually delete the old app:

1. Open the new DMG.
2. Drag the new `Hymac自用HDT.app` into `Applications`.
3. Choose `Replace` when macOS asks.
4. After replacing the app, **right-click `① 本地重签（安装后跑一次）.command` in the DMG, choose `Open`, and re-sign once.**
5. Only if macOS blocks right-click-open, cannot open the `.command` file, or it does not report completion, use this Terminal fallback:

```bash
bash "/Volumes/Hymac自用HDT 2.5/① 本地重签（安装后跑一次）.command"
```

6. Open System Settings → Privacy & Security → Screen & System Audio Recording and verify that `Hymac自用HDT` is enabled.
7. Fully quit and reopen the app before use.

If the overlay or opponent boards do not appear after updating, re-check Screen Recording and Accessibility permissions. Toggle them off and on again if needed, then restart the app.

Daily launches of the same version do not require another re-sign. Run it once only after the first installation or after replacing the app with a newer build.

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

Version 2.3 continues to read the established local Hearthstone TCP connection and exactly matches it to the corresponding pure-IP TCP + TUN connection in Clash. It does not rely on a fixed game port and does not select Battle.net domain connections. If the first match is unavailable during an actual game, it retries automatically for about three seconds and shows the next step.

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
