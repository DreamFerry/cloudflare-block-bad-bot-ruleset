<p align="center">
<img src="https://cdn.jsdelivr.net/gh/XMD0718/dumeng-blog/wp-content/uploads/2021/03/5bd7b06b077df.png" width="200px">
</p>
<h1 align="center">Cloudflare Block Bad Bot Ruleset</h1>

> Block bad, possibly even malicious web crawlers (automated bots) using Cloudflare Firewall Rules<br>
> 使用 Cloudflare Firewall Rules 拦截恶意网络爬虫（自动机器人）和其它恶意流量

## Introduction 简介

`Cloudflare Block Bad Bot Ruleset` projects stop and block Bad Bot, Spam Referrer, Adware, Malware and any other kinds of bad internet traffic ever reaching your web sites. Inspired by [nginx-badbot-blocker](https://github.com/mariusv/nginx-badbot-blocker) & worked with Cloudflare Firewall Rules.

`Cloudflare Block Bad Bot Ruleset` 可以阻止恶意爬虫、垃圾引荐来源、广告、恶意软件以及任何其他类型的恶意互联网流量到达您的网站。灵感来自 [nginx-badbot-blocker](https://github.com/mariusv/nginx-badbot-blocker) 并与 Cloudflare Firewall Rules 搭配使用。

## Precautions 注意事项

`Cloudflare Block Bad Bot Ruleset` mainly based on User-Agent, which is known to all that could be changed easily. So the project can not replace the Web Application Firewall.

`Cloudflare Block Bad Bot Ruleset` 主要基于 User-Agent，但是众所周知 User-Agent 可以伪装，所以本项目并不能取代正规的 Web Application Firewall。

## Ruleset 规则

Rule Name                                           | Action               | What For
--------------------------------------------------- | -------------------- | ---------------------------------------------------
[Allow Legitimate Services](./expressions.md#part1) | Skip                 | Match known good bot.<br>匹配已知的正常爬虫
[Block Malicious Traffic](./expressions.md#part2)   | Block                | Block some known bad bot.<br>阻挡一些已知的恶意代理和漏洞探测
[Block Known Bad ASNs](./expressions.md#part3)      | Block                | Based on known bad ASN numbe.<br>匹配一些已知的恶意ASN号（AbuseIPDB）
[Strict Rule](./expressions.md#part4)               | Managed Challenge    | Strict rules, but there may be false positives.<br>严格的规则，但可能会有误报

## More Information 更多详情

- [Announcing Firewall Rules | Cloudflare Blog](https://blog.cloudflare.com/announcing-firewall-rules/)
- [Cloudflare Firewall Rules | Cloudflare Documentations](https://developers.cloudflare.com/waf/)
- [nginx-badbot-blocker | GitHub](https://github.com/mariusv/nginx-badbot-blocker)
- [nginx-ultimate-bad-bot-blocker | GitHub](https://github.com/mitchellkrogza/nginx-ultimate-bad-bot-blocker)
- [Cloudflare-WAF-Expressions | GitHub](https://github.com/sefinek/Cloudflare-WAF-Expressions)
- [cloudflare_waf_multi_zone_ci_exmaple | GitHub](https://github.com/homieyangg/cloudflare_waf_multi_zone_ci_exmaple)

## Maintainer 维护者

**Cloudflare Block Bad Bot Ruleset** Made By [Sukka](https://github.com/SukkaW) Modified By [Dumeng](https://github.com/XMD0718), Released under the [GPL](./LICENSE) License.
