# Hymac自用HDT 2.0

适用于 Hearthstone 36.2 和酒馆战棋第 14 赛季。

![炉石传说酒馆战棋第 14 赛季](https://raw.githubusercontent.com/hymac731/Hymac-HDT/master/assets/battlegrounds-season-14.png)

## 更新内容

- 底层更新到 HSTracker 3.6.3，加入第 14 赛季卡牌数据及 Battlegrounds、Bob's Buddy、Duos 和覆盖层修复。
- 保留 Hymac 一键重连、状态面板、诊断导出、淘汰提示和重连后阵容恢复。
- 稳定模式支持动态游戏端口；新增 Clash 进程模式检查及「修复进程识别」引导。
- 进程识别需要进入实际对局；等待页面未识别属于正常现象。进入对局仍未识别时，请在齿轮面板点击「修复进程识别」。
- 修复酒馆面板最近对局无法显示英雄、名次和 MMR 的问题，并补齐“可用随从 / 禁用随从”标题。

## 安装或升级

打开 DMG，把 `Hymac自用HDT.app` 拖进「应用程序」并选择替换，然后按照 DMG 内教程重新运行本地重签。

---

For Hearthstone 36.2 and Battlegrounds Season 14.

- Updated to HSTracker 3.6.3 with Season 14 card data and upstream Battlegrounds, Bob's Buddy, Duos, and overlay fixes.
- Keeps the Hymac reconnect helper, status panel, diagnostics, elimination message, and post-reconnect overlay restoration.
- Supports dynamic game ports and adds Clash process-mode detection with guided process-recognition repair.
- Process recognition is expected only during an actual match. If it remains unavailable in a match, use Repair Process Recognition in the gear panel.
- Fixes missing hero, placement, and MMR details in the recent Battlegrounds games panel, and restores the minion header labels.
