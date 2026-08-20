# Hymac自用HDT 2.1

适用于 Hearthstone 36.2.2 和酒馆战棋第 14 赛季。

![炉石传说酒馆战棋第 14 赛季](https://raw.githubusercontent.com/hymac731/Hymac-HDT/master/assets/battlegrounds-season-14.png)

## 更新内容

- 底层升级到 HSTracker 3.6.5，适配 Hearthstone 36.2.2，并同步最新卡牌数据。
- 新增 Eternal Knight 和 Ancestral Automaton 计数器，更新可令酒馆等级 7 出现的饰品列表。
- 合入上游战斗胜率、双人模式“最近对局”和 Sandy 崩溃修复，包括 Polarizing Beatboxer 附近的胜率计算修正。
- 保留 Hymac 2.0.1 已有的一键拔线、本机连接精确匹配、Clash 进程识别修复引导、阵容恢复、战绩面板调整和自定义外观。
- 新增 Hymac 版本提醒：每天最多检查一次 GitHub Release，发现新版时可下载、稍后提醒或忽略该版本，不会自动替换 App。
- 修复 Bob's Buddy 开发自测可能导致 2.1 启动时意外退出的问题。
- 补齐 Bob's Buddy 真实对局胜率计算所需的双架构运行组件，修复进入战斗后胜率框不显示的问题。
- 修复拔线重连后战棋类型丢失、胜率与战绩覆盖层无法恢复的问题。
- 修复重连恢复战绩面板时可能导致 hymac版HDT 意外退出的问题。
- 拔线设置标题新增构建编号；本次正式包为 `2.1（构建 148）`。

## 安装或升级

打开 DMG，把 `Hymac自用HDT.app` 拖进“应用程序”并选择替换，然后按照 DMG 内教程重新运行本地重签。

首次使用一键拔线前，请安装并保持 Clash Verge Rev 运行，设置为 TUN + 规则模式、游戏连接走 DIRECT。**不需要导入订阅。**

连接识别需要进入实际对局；如果进入对局后仍无法识别，请打开红色“拔线”旁边的齿轮，按照面板引导使用“修复进程识别”。

---

For Hearthstone 36.2.2 and Battlegrounds Season 14.

- Updates the HSTracker base to 3.6.5 with the latest card data.
- Adds Eternal Knight and Ancestral Automaton counters and updates the list of Trinkets that cause Tavern Tier 7 to appear.
- Includes upstream combat-odds, Duos Latest Games, and Sandy crash fixes, including corrected odds around Polarizing Beatboxer.
- Retains Hymac 2.0.1's reconnect helper, exact local connection matching, Clash repair guidance, opponent-board restoration, adjustable session panel, and Hymac appearance.
- Adds a daily Hymac GitHub Release reminder with Download, Remind Later, and Ignore options. It never replaces the app automatically.
- Fixes a development-only Bob's Buddy smoke test that could terminate version 2.1 during launch.
- Includes the dual-architecture runtime component required by live Bob's Buddy simulations, fixing a missing combat-odds panel during real matches.
- Restores the Battlegrounds game type after reconnecting so combat odds and session overlays can resume.
- Fixes a session-panel layout crash that could terminate Hymac HDT immediately after reconnecting.
- Adds the internal build number to the reconnect settings title; this release is `2.1 (build 148)`.

Open the DMG, drag `Hymac自用HDT.app` into Applications and choose Replace, then run the local re-sign command described in the DMG.

For the reconnect helper, install and keep Clash Verge Rev running in TUN + Rule mode with the game connection set to DIRECT. **No proxy subscription is required.** Process recognition becomes available only after entering an actual match; if it is still unavailable, open the gear panel and follow the Repair Process Recognition guidance.
