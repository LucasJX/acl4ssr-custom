# ACL4SSR OpenClash 自用模板

基于 [ACL4SSR Online Full](https://github.com/ACL4SSR/ACL4SSR/blob/master/Clash/config/ACL4SSR_Online_Full.ini) 的自定义 subconverter 模板，融合 [Aethersailor](https://github.com/heunghingwan/Aethersailor-Custom_OpenClash_Rules) 规则，用于 OpenClash 订阅转换。

## 相比原版 ACL4SSR Online Full 的改动

| 改动 | 原版 | 自用版 |
|------|------|--------|
| `ChinaIp.list` | ❌ 注释掉 | ✅ 取消注释，增强中国IP段匹配 |
| `GEOIP,LAN` | ❌ 注释掉 | ✅ 取消注释，局域网流量直连 |
| Steam 平台 | 合并在游戏平台 | ✅ 独立代理组，可单独控制 |
| Steam 下载 CDN | 无 | ✅ 直连（Aethersailor 规则） |
| 游戏下载 CDN | 无 | ✅ 直连（Aethersailor 规则） |
| 非标直连规则 | 无 | ✅ 629 条自定义直连域名 |
| 非标代理规则 | 无 | ✅ 16 条自定义代理域名 |
| 非标端口规则 | 无 | ✅ 80/443 之外端口直连 |

## 代理组

| 代理组 | 类型 | 说明 |
|--------|------|------|
| 🚀 节点选择 | select | 主代理组，手动选择 |
| 🚀 手动切换 | select | 显示所有节点，手动切换 |
| ♻️ 自动选择 | url-test | 自动测速选最快节点 |
| 🎮 Steam平台 | select | Steam 商店/社区/好友代理 |
| 📲 电报消息 | select | Telegram 专用 |
| 💬 Ai平台 | select | AI 平台专用 |
| 📹 油管视频 | select | YouTube 专用 |
| 🎥 奈飞视频 | select | Netflix 专用 |
| 📺 巴哈姆特 | select | 巴哈姆特专用 |
| 📺 哔哩哔哩 | select | Bilibili 专用 |
| 🌍 国外媒体 | select | 国外媒体专用 |
| 🌏 国内媒体 | select | 国内媒体专用 |
| 📢 谷歌FCM | select | Google FCM 专用 |
| Ⓜ️ 微软Bing | select | 微软 Bing 专用 |
| Ⓜ️ 微软云盘 | select | OneDrive 专用 |
| Ⓜ️ 微软服务 | select | 微软服务专用 |
| 🍎 苹果服务 | select | Apple 专用 |
| 🎮 游戏平台 | select | Epic/Origin/Sony/Nintendo |
| 🎶 网易音乐 | select | 网易云音乐专用 |
| 🎯 全球直连 | select | 直连组 |
| 🛑 广告拦截 | select | REJECT 拦截 |
| 🍃 应用净化 | select | REJECT 净化 |
| 🐟 漏网之鱼 | select | 兜底代理组 |

## 使用方法

在 OpenClash **配置文件订阅 → 编辑订阅** 中：

1. **自定义模板链接** 填入：
```
https://raw.githubusercontent.com/LucasJX/acl4ssr-custom/main/ACL4SSR_Online_Full_Custom.ini
```
2. **subconverter 后端地址** 填你自己的（如 `http://192.168.100.100:25500/sub`）
3. **规则集订阅** 关闭（不勾选）
4. 更新订阅

## 仓库结构

```
├── ACL4SSR_Online_Full_Custom.ini   ← subconverter 模板
├── README.md
├── rule/
│   ├── Steam_CDN_Classical.yaml     ← Steam CDN 域名（直连）
│   ├── Steam_CDN_Classical_IP.yaml  ← Steam CDN IP（直连）
│   ├── Game_Download_CDN.list       ← 游戏下载 CDN（直连）
│   ├── Custom_Direct_Classical.yaml ← 非标直连规则（629条）
│   ├── Custom_Proxy_Classical.yaml  ← 非标代理规则（16条）
│   └── Custom_Port_Direct.yaml      ← 非标端口（80/443之外直连）
```

## 规则来源

- [ACL4SSR](https://github.com/ACL4SSR/ACL4SSR) — 基础规则模板
- [Aethersailor](https://github.com/heunghingwan/Aethersailor-Custom_OpenClash_Rules) — Steam CDN、游戏下载、非标规则
