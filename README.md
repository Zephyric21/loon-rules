# Loon Rules

## 抖音 / UU 远程直连

在 Loon 的远程规则中添加以下地址，策略选择 `DIRECT`：

| App / 平台 | 规则地址 |
| --- | --- |
| 抖音（iPhone、Mac 共用） | `https://raw.githubusercontent.com/Zephyric21/loon-rules/main/douyin-direct.list` |
| UU 远程（iPhone） | `https://raw.githubusercontent.com/Zephyric21/loon-rules/main/uu-remote-direct.list` |
| UU 远程（Mac，含进程规则） | `https://raw.githubusercontent.com/Zephyric21/loon-rules/main/uu-remote-direct-mac.list` |

UU 的两个版本二选一。Mac 版包含同一份域名/IP 清单，并增加既有的四条 Mac 进程规则。

规则依据 App 隐私报告界面的 App 归属及 Loon 请求记录整理，只发布规则项。原始隐私报告、访问时间、传感器记录、个人配置、节点和证书不上传。UU 的 IP 采用当次观察到的公网地址 `/32`，不推导网段；内网、保留地址和 Loon Fake IP 不加入。IP 清单是当次快照，不能保证长期穷尽；共享 IP 的匹配也会作用于其他使用该地址的请求。抖音优先使用已有业务域名后缀，额外第三方域名仅加入观察到的完整主机名。

这三份是流量分流规则，不负责 DNS。经验证需要的单域名加密 DNS 例外应保留在各设备的 `[Host]`，不要因迁移规则订阅而删除。订阅中不包含 MITM 或证书设置。

## Talkatone

### Bottom Ad Block

```text
https://raw.githubusercontent.com/FuRina-AI/loon-rules/main/talkatone-bottom-ad.plugin
```

### Stable-IP Route for Registration

把 Talkatone / Google OAuth / hCaptcha 注册链路固定到同一个策略组，减少分流/换 IP/MITM 导致的风控失败。

导入前请把插件里的策略名 `TalkatoneProxy` 改成你 Loon 里实际的节点或策略组名；注册时不要对这些域名启用 MITM。

```text
https://raw.githubusercontent.com/FuRina-AI/loon-rules/main/talkatone-stable-ip.plugin
```

## NapCat / AstrBot


### NapCat QQ Login Rule URL

Loon「Rule」里添加 URL 用这个：

```text
https://raw.githubusercontent.com/FuRina-AI/loon-rules/main/napcat-qq-login.list
```

### AstrBot Video Parser Rule URL

Loon「Rule」里添加 URL 用这个：

```text
https://raw.githubusercontent.com/FuRina-AI/loon-rules/main/astrbot-video-parser.list
```


### NapCat QQ Login Domains

NapCat 登录 QQ、保活、头像/图片资源常用域名规则。

```text
https://raw.githubusercontent.com/FuRina-AI/loon-rules/main/napcat-qq-login.plugin
```

### AstrBot Video Parser Domains

AstrBot `astrbot_plugin_parser` 解析/下载视频与图集常用域名规则。

```text
https://raw.githubusercontent.com/FuRina-AI/loon-rules/main/astrbot-video-parser.plugin
```
