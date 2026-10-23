# GSUIDCORE 域名清单

采集日期：2026-10-23。只保留主机名，不发布请求路径、参数或用户内容。

## 直连与阿里 DoH（39 个）

来源为当前安装的三个插件、它们的页面依赖、当前及既有服务日志。包含源码备用项，不能视作逐项实际请求抓包。

- `api.kurobbs.com`
- `api.ttocr.com`
- `api.xiaoheihe.cn`
- `api3.sanyueqi.cn`
- `cdn.staticfile.org`
- `cnb.cool`
- `event.kurobbs.com`
- `fonts.loli.net`
- `ga.loping151.site`
- `gchat.qpic.cn`
- `gmserver-api.aki-game2.com`
- `gmserver-api.aki-game2.net`
- `gxh.vip.qq.com`
- `hf-mirror.com`
- `hkc-download.ftn.qq.com`
- `lib.baomitu.com`
- `lulush.microgg.cn`
- `multimedia.nt.qq.com.cn`
- `newsimg.5054399.com`
- `njc-download.ftn.qq.com`
- `pc-launcher-sdk-api.kurogame.net`
- `prod-alicdn-community.kurobbs.com`
- `q.qlogo.cn`
- `q1.qlogo.cn`
- `scoreecho.loping151.site`
- `sdkapi.kurogame-service.com`
- `silverwing.elysia.beauty`
- `static.geetest.com`
- `static.geevisit.com`
- `tjc-download.ftn.qq.com`
- `web-static.kurobbs.com`
- `wh.loping151.site`
- `ww1.loping151.top`
- `ww2.loping151.top`
- `ww3.loping151.cn`
- `www.4399.com`
- `www.kurobbs.com`
- `www.loping151.site`
- `xwservice.loping151.site`

## 其余源码 URL 主机名（不新增策略）

包括核心可选游戏 API、海外服务、代码托管、帮助文档、IP 检测和备用下载线路；出现于代码不代表当前三个插件实际调用。沿用既有策略，避免仅因引用文本就强制直连。

- `act-nap-api.mihoyo.com`
- `akashadata.feixiaoqiu.com`
- `api-account-sg.hoyoverse.com`
- `api-os-takumi.mihoyo.com`
- `api-takumi-record.mihoyo.com`
- `api-takumi.mihoyo.com`
- `api.enka.network`
- `api.geetest.com`
- `api.hakush.in`
- `api.ipify.org`
- `apiv6.geetest.com`
- `app.mihoyo.com`
- `bbs-api-os.hoyolab.com`
- `bbs-api.mihoyo.com`
- `bbs-api.miyoushe.com`
- `blog.minigg.cn`
- `cn-js-nj-1.lcf.icu`
- `docs.qq.com`
- `docs.sayu-bot.com`
- `enka.network`
- `file.minigg.cn`
- `genshin.honeyhunterworld.com`
- `genshin.minigg.cn`
- `ghproxy.mihomo.me`
- `gi.yatta.moe`
- `gitcode.com`
- `github.com`
- `gscore.focalors.com`
- `hk4e-api-os.hoyoverse.com`
- `hk4e-api.mihoyo.com`
- `hk4e-sdk.mihoyo.com`
- `httpbin.org`
- `info.minigg.cn`
- `jp.qxqx.cf`
- `kr.qxqx.cf`
- `map.minigg.cn`
- `passport-api-sg.hoyoverse.com`
- `passport-api.mihoyo.com`
- `peps.python.org`
- `profile.microgg.cn`
- `public-data-api.mihoyo.com`
- `public-operation-hk4e-sg.hoyoverse.com`
- `public-operation-hk4e.mihoyo.com`
- `servicewechat.com`
- `sg-1.lcf.icu`
- `sg-2.qxqx.cf`
- `sg-hk4e-api.hoyolab.com`
- `sg-hk4e-api.hoyoverse.com`
- `sg-public-api.hoyolab.com`
- `sg-public-api.hoyoverse.com`
- `sm.ms`
- `tw-taipei-1.lcf.icu`
- `us-lax-2.lcf.icu`
- `webstatic.mihoyo.com`
- `www.kancloud.cn`

## 已失效模板项

- `prod-all-ali-kuro-landing.kurogame.com`：当次 AliDNS 返回 NXDOMAIN，未纳入生效规则。
