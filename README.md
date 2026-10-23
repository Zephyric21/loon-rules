# Loon Rules

## 不背单词

在 Loon「插件」中订阅：

```text
https://raw.githubusercontent.com/Zephyric21/loon-rules/main/bubei-cn.plugin
```

仅为实际观察到的 `api.beingfine.cn`、`static.beingfine.cn`、`audio.beingfine.cn`、`hwstatic.beingfine.cn` 设置 DIRECT 与阿里 DoH。依据为 iPhone Loon 请求与 DNS 记录，隐私报告列表未找到本 App，因此不声称来源为隐私报告。排除 Apple 及无关域名，不放行整个 CDN 后缀，不固定 IP，不修改默认 DNS、节点或证书。仅代表当次业务域名快照，不保证覆盖全部功能或修复所有卡顿。

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

## GSUIDCORE / 鸣潮 / ScoreEcho

Loon 插件订阅（DIRECT + 阿里加密 DNS，两台 Mac 可共用）：

```text
https://raw.githubusercontent.com/Zephyric21/loon-rules/main/gsuidcore-cn.plugin
```

仅分流时使用 `gsuidcore-direct.list`，远程规则策略选 DIRECT；DNS 合并片段为 `gsuidcore-host.txt`。完整插件和分流清单按用途选择，DNS 不能通过流量清单生效。

域名来自 2026-10-23 MacBook 运行容器的 XutheringWavesUID、RoverSign、ScoreEcho 源码、页面依赖及当前/既有日志。包括源码中的备用业务端点，不代表每个端点均在当日发出请求。仅匹配完整主机名，不扩大父域，不固定 CDN IP，不改变默认 DNS、系统 DNS、明文回落、节点、FINAL 或 MITM。

普通聊天中粘贴的网址、文档/仓库链接、IP 检测端点、模板占位符及本地监听地址不加入直连清单；GitHub 和海外公共 CDN 沿用既有策略。原始日志、URL 路径/参数、Cookie、用户信息和个人配置不发布。国内解析指这些业务域名统一使用阿里 DoH，不是把全网 DNS 改为国内。已有本地 Host/Rule 可能优先于插件，需要检查覆盖关系；不要开关 VPN 清缓存。

此次发现面板请求存在授权验证反复 TLS 超时、资源测速及排行失败。规则能修复已验证的域名解析/连接问题，不承诺解决插件的同步阻塞、失败重试或所有服务端故障。`ww1.loping151.top` 在指定解析 IP 的测试中仍发生超时，保留为代码中的资源候选，不宣称已恢复。

当前发布清单共 39 个精确域名，阿里 HTTPS DNS 查询均返回非空 A 答案。模板中的 `prod-all-ali-kuro-landing.kurogame.com` 当次返回 NXDOMAIN，未纳入生效规则。`api.ttocr.com` 在源码中是 HTTP 验证接口，HTTPS 根路径测试出现证书校验失败，未放宽校验或操作证书；规则不代表该可选服务可用。
