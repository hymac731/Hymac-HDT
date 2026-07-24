# Hymac自用HDT 1.3

基于 HSTracker 3.6.2，适配 Hearthstone 36.0.3。

- 合入上游 Battlegrounds、Bob's Buddy、Duos 和重连识别修复。
- 保留 Hymac 一键拔线、Clash Verge 状态看板、诊断导出和重连后阵容/面板恢复。
- 稳定模式只识别 Hearthstone 纯 IP `3724` 游戏连接；兼容模式仅匹配纯 IP `1119`。
- 点击「拔线」时，若战棋已结束，或 Bob's Buddy 当前模拟同时为失败 100% 且致死 100%，则不执行拔线并短暂显示「没了 下一把吧」。
- 拔线设置显示版本 1.3；悬浮按钮已加宽，提示文字可完整显示。退出炉石后会自动隐藏拔线按钮和游戏覆盖层。

升级时直接把新版 App 拖进「应用程序」并选择替换，然后按 DMG 内教程重新运行本地重签脚本。

---

Based on HSTracker 3.6.2 and updated for Hearthstone 36.0.3.

- Includes upstream Battlegrounds, Bob's Buddy, Duos, and reconnect-detection fixes.
- Keeps the Hymac reconnect helper, Clash Verge status panel, diagnostic export, and overlay restoration.
- Stable mode targets only the Hearthstone pure-IP port `3724` game connection; compatibility mode is limited to pure-IP port `1119`.
- After Reconnect is clicked, the action is blocked if the game has ended or the current Bob's Buddy simulation reports both 100% loss and 100% player lethal.
- Reconnect settings show version 1.3, the wider button displays the full message, and reconnect/game overlays hide automatically after Hearthstone quits.

To upgrade, replace the existing App in Applications and run the local re-sign script included in the DMG.
