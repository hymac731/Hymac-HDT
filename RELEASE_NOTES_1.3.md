# Hymac自用HDT 1.3

基于 HSTracker 3.6.2，适配 Hearthstone 36.0.3。

- 合入上游 Battlegrounds、Bob's Buddy、Duos 和重连识别修复。
- 保留 Hymac 一键拔线、Clash Verge 状态看板、诊断导出和重连后阵容/面板恢复。
- 稳定模式只识别 Hearthstone 纯 IP `3724` 游戏连接；兼容模式仅匹配纯 IP `1119`。
- 「没了 下一把吧」只按官方游戏结束状态判断，不使用胜率预测拦截。

升级时直接把新版 App 拖进「应用程序」并选择替换，然后按 DMG 内教程重新运行本地重签脚本。

---

Based on HSTracker 3.6.2 and updated for Hearthstone 36.0.3.

- Includes upstream Battlegrounds, Bob's Buddy, Duos, and reconnect-detection fixes.
- Keeps the Hymac reconnect helper, Clash Verge status panel, diagnostic export, and overlay restoration.
- Stable mode targets only the Hearthstone pure-IP port `3724` game connection; compatibility mode is limited to pure-IP port `1119`.
- The ended-game block uses only the official game state, never win-rate predictions.

To upgrade, replace the existing App in Applications and run the local re-sign script included in the DMG.
