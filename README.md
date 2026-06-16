# ACL4SSR OpenClash 自用模板

基于 [ACL4SSR Online Full](https://github.com/ACL4SSR/ACL4SSR/blob/master/Clash/config/ACL4SSR_Online_Full.ini) 的自定义 subconverter 模板，用于 OpenClash 订阅转换。

## 相比原版的改动

1. **取消注释 `ChinaIp.list`** — 原版注释掉了中国IP段规则，导致部分国内IP无法匹配直连规则
2. **移除 `GEOIP,LAN` 注释** — 确保局域网流量正确直连

## 使用方法

在 OpenClash 的 **配置文件订阅 → 编辑订阅** 中：

- **自定义模板链接** 填入：
  ```
  https://raw.githubusercontent.com/LucasJX/acl4ssr-custom/main/ACL4SSR_Online_Full_Custom.ini
  ```
- **subconverter 后端地址** 保持你自己的（如 `http://192.168.100.100:25500/sub`）

## 为什么需要这个模板

原版 ACL4SSR Online Full 有两个问题：
1. `ChinaIp.list` 被注释掉，导致中国IP段匹配不完整
2. subconverter 生成的 rule-provider URL 默认指向 `127.0.0.1:25500`，如果 subconverter 不在本机运行，规则文件全部无法下载
