# Hymac自用HDT 2.0.1

适用于 Hearthstone 36.2 和酒馆战棋第 14 赛季。

![炉石传说酒馆战棋第 14 赛季](https://raw.githubusercontent.com/hymac731/Hymac-HDT/master/assets/battlegrounds-season-14.png)

## 更新内容

- 新增本机游戏连接精确匹配，自动对应 macOS 中的炉石连接与 Clash 连接，不再依赖固定端口。
- 未立即找到连接时会自动重新匹配约 3 秒，并给出清楚的下一步提示。
- 酒馆战棋战绩面板新增拖动、独立宽度调整、整体缩放和锁定功能。
- 保留历史战绩悬停查看最终阵容；面板锁定后不会阻挡炉石界面点击。
- 优化齿轮面板状态文案，并保留 HSTracker 3.6.3、Hearthstone 36.2、第 14 赛季数据及 Hymac 2.0 的全部功能。

## 安装或升级

打开 DMG，把 `Hymac自用HDT.app` 拖进“应用程序”并选择替换，然后按照 DMG 内教程重新运行本地重签。

首次使用一键重连前，请安装并保持 Clash Verge Rev 运行，设置为 TUN + 规则模式、游戏连接走 DIRECT。**不需要导入订阅。**连接识别需要进入实际对局；首次未匹配到时，等待自动匹配提示即可。

---

For Hearthstone 36.2 and Battlegrounds Season 14.

- Exactly matches the local macOS Hearthstone connection to its Clash connection without relying on a fixed game port.
- Automatically retries for about three seconds and provides clear guidance when a connection is not immediately available.
- Adds moving, independent width adjustment, uniform scaling, and locking for the Battlegrounds session statistics panel.
- Keeps final-board previews on history hover without blocking Hearthstone clicks while locked.
- Improves reconnect status wording while retaining HSTracker 3.6.3 and all Hymac 2.0 features.
