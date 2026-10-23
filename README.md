# Loon Rules

## 不背单词

在 Loon「插件」中订阅：

```text
https://raw.githubusercontent.com/Zephyric21/loon-rules/main/bubei-cn.plugin
```

仅为实际观察到的 `api.beingfine.cn`、`static.beingfine.cn`、`audio.beingfine.cn` 设置 DIRECT 与阿里 DoH。依据为 iPhone Loon 请求与 DNS 记录，隐私报告列表未找到本 App，因此不声称来源为隐私报告。排除 Apple 及无关域名，不放行整个 CDN 后缀，不固定 IP，不修改默认 DNS、节点或证书。仅代表当次业务域名快照，不保证覆盖全部功能或修复所有卡顿。

只需分流时使用 `bubei-direct.list`，在远程规则中选择 DIRECT；它不包含 DNS 设置。原始 URL、请求时间、次数、用户数据和个人配置不上传。

## 微信 / QQ 国内直连与加密 DNS

推荐在 Loon「插件」中订阅这一份，并放在现有拦截插件之前：

```text
https://raw.githubusercontent.com/Zephyric21/loon-rules/main/wechat-qq-cn.plugin
```

它同时包含 `DIRECT` 流量规则与阿里加密 DNS 的 `[Host]` 例外，只匹配 59 个实际观察到的完整主机名。微信隐私界面 23 个、QQ 隐私界面 34 个非 Apple 域名，加上本次微信请求日志中两个业务主机。`amp-api-edge.apps.apple.com` 被排除，现有 Apple 策略不作更改。包含这两个 App 实际联系过的第三方域名，但不将它们全部认定为腾讯所有。

已有订阅中出现的拦截规则，可能与此次明确要求的直连策略冲突；将此插件放在其他插件之前，并检查本地规则是否仍有覆盖。仅导入规则清单不会改变 DNS，也不保证覆盖优先级更高的插件拦截。

只需要流量规则时，用下列地址添加到「远程规则」，策略设为 `DIRECT`；它和上面的完整插件二选一：

```text
https://raw.githubusercontent.com/Zephyric21/loon-rules/main/wechat-qq-direct.list
```

不发布原始隐私报告、访问时间、次数、聊天内容或个人配置。不将「未命名域」中的 IP 当成域名，不加入 Fake IP 或私网地址，不固定 CDN IP，不添加全局国内 DNS 分流，不改系统 DNS/明文回落、默认 DNS、节点、证书或 MITM。现有 HTTPDNS 防泄露拦截不在本清单中放行。

此清单是当次观察快照，不保证穷尽今后新增的业务域名，也不承诺仅靠这些规则解决所有连接问题。Loon 的 DNS 缓存和既有连接可能仍保留旧结果，不应通过关闭/开启 VPN 来刷新。该插件不包含 MITM 段。

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
