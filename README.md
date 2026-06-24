# Hymac自用HDT

> macOS 上的炉石传说**酒馆战棋**追踪器 + **一键拔线**。
> 基于开源 [HearthSim/HSTracker](https://github.com/HearthSim/HSTracker) 改造，整合了 [z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper) 的拔线思路。
> **个人自用 / 学习交流**。仅 macOS。

**当前版本：自用正式版 1.0**  
Release 附件：`Hymac.HDT-1.0.dmg`

<!-- 截图位：把游戏内截图传到仓库后，改成 ![预览](screenshot.png) -->

---

## 这是什么

Windows 上有「团子版 HDT」，能侦察对手阵容、模拟胜率、还能一键拔线跳过战斗动画。但 **Mac 上一直没有好用的**。

这个就是给 Mac 玩家的：在成熟的开源 **HSTracker**(对手阵容/胜率覆盖层)基础上，**集成了一键拔线**，凑齐了 Mac 上「侦察 + 拔线」一条龙。本质是**把两个现成的开源方案融合 + 打包，方便 Mac 玩家直接用**。

## 功能

- 🔍 **对手阵容侦察 / 胜率模拟 / 流派指南**：游戏内覆盖层（来自 HSTracker）。
- ⚡ **一键拔线**：战斗开始时按 `⌥1` 或点悬浮「拔线」按钮 → 游戏秒回、跳过战斗动画。
  - 悬浮按钮可拖动、记忆位置；旁边 ⚙ 齿轮可**自定义快捷键**。
  - **干净重连、不掉登录**，且重连后**对手阵容自动恢复**（修了原版拔线后阵容丢失的问题）。
- 战棋面板可一键放到游戏右边，避免挡住选手列表。

---

## 原理思路（它是怎么工作的）

**① 侦察 / 胜率**：HSTracker 读取炉石进程内存，还原八家英雄、几本、血量、名次、对手棋盘随从，再用内置的 BobsBuddy 模拟器算胜率。所以需要「屏幕录制 + 辅助功能 + 读内存」权限——和官方 HSTracker 完全一样。

**② 一键拔线（参考 hearthstone_skipper）**：
- 战棋的战斗结果在**战斗一开始就由服务器算定**了，动画只是播放。所以**在战斗开始那一下短暂断开客户端 → 重连 → 动画就被跳过**，直接进下一阶段（多出操作时间）。
- 关键是**怎么"干净地"断**：让游戏流量经过本地的 **Clash**，再用 Clash 的接口**主动关闭**那条游戏服连接 → 游戏瞬间察觉、干净重连、**不掉登录**。（比拔网线/防火墙丢包都干净。）
- 本工具自动识别炉石那条「纯 IP 直连的游戏服连接」并掐掉，掐完游戏自己重连，覆盖层这边还会把对手阵容补回来。

---

## Clash 怎么设置（拔线必读）

⚠️ **不需要买任何 VPN / 梯子！** 游戏流量是**直连(DIRECT)**的、不经过任何代理节点；Clash 在这里只是"连接的看门人"，好让它的接口能掐掉连接。

1. 装 **[Clash Verge](https://github.com/clash-verge-rev/clash-verge-rev)**(mihomo 内核)。
2. 开 **TUN 模式**(让游戏裸 TCP 流量也走 Clash)。
3. 用 **规则(Rule) 模式**，配置里要有让国服 IP 直连的规则，例如：
   ```yaml
   rules:
     - GEOIP,CN,DIRECT
     - MATCH,DIRECT
   ```
   （只要保证国服游戏服走 DIRECT 就行，否则游戏延迟会爆。）
4. 如果你手上一份配置都没有，可以用一份**只有 TUN + 全直连、没有任何节点**的极简配置——纯本地、不花钱。

> 没装 Clash 或没开 TUN：拔线点了没反应（会提示找不到连接），但**追踪/胜率照常能用**。

---

## 安装

到 **[Releases](../../releases)** 下载 `Hymac.HDT-1.0.dmg`，打开后照里面的 `安装教程.txt` 做：

1. `Hymac自用HDT.app` 拖进「应用程序」。
2. 右键 `① 本地重签（先跑这个）.command` →「打开」（去隔离 + 用你机器身份重签，让读内存权限生效）。
3. 系统设置 → 隐私与安全性 → 给它勾上 **屏幕录制** + **辅助功能**，然后退出重开 app。
4. 进炉石，看到覆盖层 = 成功。拔线再按上面配好 Clash。

## 使用

| 操作 | 方法 |
|---|---|
| 拔线 | 战斗开始时按 `⌥1`，或点红色「拔线」悬浮按钮 |
| 改快捷键 | 点「拔线」旁的 ⚙ 齿轮 → 按下新组合键（需含 ⌘/⌥/⌃/⇧） |
| 挪按钮 | 拖按钮空白处（记忆位置） |
| 面板放右边 | 终端 `defaults write net.hearthsim.hstracker.selfbuild bgSessionOnRight -bool YES` 后重启 app |

> 看到「正在重新连接」别点"退出游戏"，等它自己回来。

---

## 🙏 致谢

本项目站在巨人的肩膀上，只是做了整合：

- **[HearthSim/HSTracker](https://github.com/HearthSim/HSTracker)** —— Mac 炉石追踪器底座（MIT 协议），侦察/胜率/覆盖层全靠它。
- **[z2z63/hearthstone_skipper](https://github.com/z2z63/hearthstone_skipper)** —— 用 Clash 核心实现 macOS 一键拔线的思路，本项目的拔线方案参考自它。

感谢以上原作者的开源工作。

## 说明

- 个人自用、免费、学习交流。**拔线为娱乐功能，请理性使用。**
- 仅 macOS；Windows 请用 HsMod / 团子版 HDT。
- 遵循 **MIT License**（保留 HSTracker 原版版权声明）。
- 与暴雪娱乐(Blizzard)、网易无关。Hearthstone © Blizzard Entertainment。
