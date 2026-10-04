# seo proxies: how to pick and size residential IPs for city-level rank tracking without wasting budget

Most rank-tracking problems that look like a tooling bug are a network problem. You pull the same keyword set every morning, the numbers look plausible, and then a client in Dallas says the local pack shows something completely different from your report. Nothing is broken. Your requests are just leaving from one datacenter IP in Virginia, which is not what a searcher in Dallas looks like to Google.

That is the entire reason the phrase "seo proxies" gets searched. Not because anyone wants to buy proxies for fun, but because SERP collection breaks down in three predictable ways once you go past a few hundred keywords: rate limits and CAPTCHAs, wrong geography, and noisy data that swings for no reason because each run uses a different IP type.

## What an SEO proxy actually does, and what it can't fix

A proxy sits between your rank tracker (or your scraper) and the search engine, and it decides which IP the request appears to come from. For SEO work that buys you three things:

- **Requests that don't look like a bot sweep.** Search engines score IP reputation, ASN, and request patterns. Consumer ISP addresses from the market you're measuring start with a much cleaner slate.
- **Location-accurate results.** Google varies output by country, city, language, and device. If you need to know what someone in Toronto sees for "best insurance broker," you need an exit IP in Toronto.
- **Consistent, repeatable collection.** Tracking is only useful if today's run and next week's run are collected the same way.

What a proxy does not fix: missing or mismatched `gl`, `hl`, and `uule` parameters, a mobile user agent paired with a desktop viewport, blind retry loops, or a parser that quietly drops a page because the layout changed. Teams blame the proxy for problems the request template caused. Check those first before you buy capacity.

## The location math is the real cost driver

Here's the part that surprises people budgeting their first real rank-tracking setup: keyword count is the smallest number in the equation.

A weekly report on 500 keywords in one market is a light job. Now take those same 500 keywords across desktop and mobile, six metro areas, plus a competitor set, plus pagination depth to page three, plus a retry allowance. That's not 500 requests per run.

A workable planning sequence:

1. Count tracked keywords.
2. Multiply by markets and device variants.
3. Add retries and scheduled competitor checks.
4. Divide by the number of IPs or the bandwidth you plan to buy.
5. Leave headroom so a full run never depends on pushing every address to its limit.

There is no universal "one proxy per X keywords" ratio, and any sales page that gives you one is guessing. Search engines read timing, browser behaviour, and request shape, not just the raw count. A pilot on your own keyword set, in your own markets, tells you more than any published formula.

## Per-IP or per-GB: pick the billing model before the provider

This is where most SEO budgets get lost. Two people tracking the same 10,000 keywords can end up on completely different plans and neither is wrong.

**Per-GB** suits text-level SERP collection. A parsed Google results page is small. In a December 2025 case study published on Proxybros, the tester logged an average response payload of roughly 40–80 KB per request. At that size, 100,000 fetched SERPs lands somewhere in the 4–8 GB range. A modest bandwidth pack can cover months of daily rank tracking.

**Per-IP with unlimited bandwidth** suits anything that renders pages like a human: anti-detect browser profiles, screenshot-based SERP capture, full page loads with images and fonts, or long logged-in sessions where you don't want the session to rotate mid-flow. Those jobs blow through gigabyte budgets fast, which is exactly when unlimited-per-IP becomes the cheaper structure.

The mistake is choosing based on the headline price. The $0.018 per IP figure is meaningless if your workload is 200 MB of browser traffic a month, and the $3.00 per GB entry pack is a bad deal if you're running twelve always-on scraping jobs.

## Where 9Proxy fits into an SEO stack

9Proxy is a residential proxy provider with a pool the company puts at more than 20 million IPs across 90+ countries, with targeting down to country, state, city, ZIP code, and ISP level. For rank tracking, that targeting granularity is the relevant part of the marketing copy, not the pool size.

The platform sells residential access three ways: per-IP packages with unlimited bandwidth, per-GB packages with rotating or sticky sessions, and bundles that combine both. Protocol support covers HTTP/HTTPS and SOCKS5, and the network plugs into the places SEO teams actually work: rank trackers and crawl tools that accept a proxy field, custom Python scripts, and anti-detect browsers.

A few operational details that matter more than the feature list:

- **IP lifespan is natural, not permanent.** Per-IP addresses stay alive from a few hours up to around 24 hours. The auto-refresh feature swaps in a replacement when an IP drops, which cuts down on "connection refused" chains in the middle of a long run. A 60-second replacement window for dead IPs is described in third-party reviews.
- **Rotation is scheduled, not automatic, on the per-IP model.** You set rotation intervals on selected ports. The per-GB model rotates per request or per session, with sticky mode available.
- **The per-IP model requires the desktop app.** Long-lived IP sessions are managed through local port forwarding in the 9Proxy desktop client (Windows and macOS). The per-GB model works straight from the dashboard with username/password or IP whitelisting, which is simpler for headless servers.
- **Port-level targeting is the practical interface.** You bind ports to a country, city, ZIP, or ISP, then point different keyword groups at different ports. That maps cleanly onto markets.

There are honest limits. 9Proxy is not a managed SERP API — it won't return parsed JSON with featured snippets and AI Overviews extracted. You bring your own scraper and parser. Independent comparisons also disagree with the vendor's own targeting claims: a September 2026 comparison on Traffic Creator rated 9Proxy's city-level targeting as "limited," and put its success rate at 95%+ on unprotected Tier 1 targets but 85–92% on moderately protected ones, below mid-market providers that claim 96–99%. If your targets are heavily defended e-commerce sites or you need verified traffic generation, that's a real gap worth knowing before you commit. For plain Google SERP pulls from a text-level script, the picture is different, and third-party commentary has placed 9Proxy among the more aggressive pricing options in the residential market.

The referral structure is also unusual: sign-ups run through an invite code, and 9Proxy's own affiliate documentation has described a 5% discount for users who arrive through a referral, alongside 5% bonuses or discounts on selected payment methods. Payment options include cards, crypto (USDT, BTC, ETH, LTC, DOGE and others), Alipay, Apple Pay, and Google Pay.

👉 [Start a 9Proxy account with the invite code applied](https://bit.ly/9-Proxy)

## 9Proxy plans, in full

Prices below reflect the adjustment 9Proxy announced on May 18, 2026, which took effect June 1 and raised IP-based and bundle pricing. Per-GB pricing was explicitly left unchanged. There's no monthly subscription — you buy balance, and balance is consumed as you use it.

### IP-based residential packages (unlimited bandwidth per IP)

| Package | What you get | Rate per IP | Total price | Notes | Purchase |
| --- | --- | --- | --- | --- | --- |
| 100 IPs | 100 residential IPs, unlimited bandwidth | $0.24 | $24 | Entry tier; enough for a single-market pilot | [Get the 100-IP package](https://bit.ly/9-Proxy) |
| 500 IPs | 500 residential IPs, unlimited bandwidth | $0.144 | $72 | Solo operators running a few markets | [Get the 500-IP package](https://bit.ly/9-Proxy) |
| 1,000 + 500 bonus | 1,500 residential IPs total | $0.084 | $126 | Includes 500 bonus IPs | [Get the 1,000+500 IP package](https://bit.ly/9-Proxy) |
| 2,500 IPs | 2,500 residential IPs | $0.084 | $210 | Multi-vertical setups | [Get the 2,500-IP package](https://bit.ly/9-Proxy) |
| 5,000 IPs | 5,000 residential IPs | $0.072 | $360 | Typical agency SEO stack | [Get the 5,000-IP package](https://bit.ly/9-Proxy) |
| 15,000 IPs | 15,000 residential IPs | $0.048 | $720 | Regional teams | [Get the 15,000-IP package](https://bit.ly/9-Proxy) |
| 25,000 IPs | 25,000 residential IPs | $0.035 | $863 | Reseller and heavy automation inventory | [Get the 25,000-IP package](https://bit.ly/9-Proxy) |
| 50,000 IPs | 50,000 residential IPs | $0.029 | $1,438 | High-volume reseller tier | [Get the 50,000-IP package](https://bit.ly/9-Proxy) |
| 100,000 IPs (Business) | 100,000 residential IPs | $0.023 | $2,300 | High-volume business tier | [Get the 100,000-IP business package](https://bit.ly/9-Proxy) |
| 200,000 IPs (Business) | 200,000 residential IPs | $0.021 | $4,140 | High-volume business tier | [Get the 200,000-IP business package](https://bit.ly/9-Proxy) |
| 500,000 IPs (Business) | 500,000 residential IPs | $0.018 | $8,625 | Lowest advertised per-IP rate | [Get the 500,000-IP business package](https://bit.ly/9-Proxy) |

Unused IPs on this model never expire, so a package bought for a seasonal campaign doesn't evaporate at month end.

👉 [Compare every IP-based tier on the 9Proxy pricing page](https://bit.ly/9-Proxy)

### GB-based residential packages (pay per traffic)

| Package | Rate per GB | Total price | Validity | Purchase |
| --- | --- | --- | --- | --- |
| 5 GB | $3.00 | $15 | 180 days | [Get the 5 GB pack](https://bit.ly/9-Proxy) |
| 50 + 5 GB bonus | $2.10 | $105 | 180 days | [Get the 50+5 GB pack](https://bit.ly/9-Proxy) |
| 100 GB | $1.50 | $150 | 180 days | [Get the 100 GB pack](https://bit.ly/9-Proxy) |
| 200 GB | $1.00 | $200 | 180 days | [Get the 200 GB pack](https://bit.ly/9-Proxy) |
| 1,000 GB | $0.80 | $800 | 180 days | [Get the 1,000 GB pack](https://bit.ly/9-Proxy) |
| 2,000 GB | $0.75 | $1,500 | 180 days | [Get the 2,000 GB pack](https://bit.ly/9-Proxy) |
| Enterprise 3,000–10,000 GB | $0.72 down to $0.68 | Quoted by tier | Unlimited | [Ask about enterprise GB volume](https://bit.ly/9-Proxy) |

The 180-day validity is the detail agencies should weigh. If your reporting cadence is project-based, unused bandwidth survives the gap between engagements instead of expiring in 30 days.

### Bundle packages (IPs plus traffic)

| Bundle | Package contents | Price | Purchase |
| --- | --- | --- | --- |
| Starter Bundle | 100 IPs + 5 GB | $30 | [Get the Starter bundle](https://bit.ly/9-Proxy) |
| Growth Bundle | 1,500 IPs + 50 GB | $180 | [Get the Growth bundle](https://bit.ly/9-Proxy) |
| Pro Bundle | 5,000 IPs + 500 GB | $720 | [Get the Pro bundle](https://bit.ly/9-Proxy) |

Bundled traffic runs on the same 180-day validity window.

## Which plan for which SEO job

**Solo consultant, 300 keywords, one country, text-level SERPs.** The 5 GB pack or the 50+5 GB pack. At 40–80 KB per response, you have room for months of daily pulls. Buying IPs here would be paying for unlimited bandwidth you'll never touch.

**Small agency, 2,000 keywords across four cities and two devices.** The 50+5 GB pack is still the starting point, but watch consumption after the first month before scaling. If you start rendering pages with screenshots for client decks, bandwidth climbs into gigabyte-per-run territory and your model choice flips.

**E-commerce or international group with anti-detect browser workflows.** The IP-based packages, because sessions need to stay alive and bandwidth needs to stop mattering. 500 IPs at $72 is a reasonable entry point; the 5,000-IP tier is the standard agency footprint.

**Teams that genuinely need both.** The bundles exist for this, and buying a bundle is cheaper than buying the two components separately.

## Setting it up for rank tracking

1. **Create the account through the invite link** so the referral discount attaches to your signup.
2. **Choose the billing model** based on whether you're fetching text or rendering pages.
3. **Open the desktop app (per-IP) or the dashboard (per-GB).** The per-IP route means configuring port numbers; the per-GB route means generating endpoint credentials.
4. **Bind ports or endpoints to your markets.** One port group per city is the tidiest mapping, and it makes bad regions obvious in your logs.
5. **Turn on auto-refresh** for anything long-running, and set rotation intervals deliberately. Rotating on every request looks noisier than rotating per batch.
6. **Match your parameters.** `gl`, `hl`, and `uule` need to agree with the exit location, and device user agents need matching viewports. A Toronto IP with a US geo parameter gives you a wrong answer with confidence.
7. **Validate the geography before you trust the report.** Check the exit IP with a lookup tool and compare the SERP layout against a manual check in the target city.
8. **Track your own failure rates.** Block rate, CAPTCHA rate per 1,000 requests, geo mismatch percentage, and cost per successful request tell you when to escalate from cheap capacity to residential.

## Cost control that doesn't wreck accuracy

- Default to the cheapest option that clears your block thresholds, and measure before you upgrade tiers.
- Schedule runs off-peak in each market where your reporting window allows it.
- Cache and dedupe. If nothing changed, you don't need to re-fetch.
- Separate critical keywords from long-tail experiments, and give them different settings.
- Back off after a hard block instead of retrying on the same address. Retry storms train the anti-bot model against your IPs.

## FAQ

**Do these still work for Google?** Yes, at the text-collection layer, when you pair residential IPs with sensible request pacing and correct geo parameters. Residential addresses carry the trust that datacenter ranges lost years ago. None of that compensates for machine-speed bursts with no session logic.

**How many IPs do I need?** Nobody can answer that from a keyword count alone. Run a pilot week, measure success rate per region, and size from there.

**Rotating or sticky sessions?** Rotate per batch for broad keyword collection. Hold sticky sessions for paginated runs where page flow matters. Holding a session too long accumulates request history that can trip defenses.

**Is there a free trial?** 9Proxy describes trials for new users as limited and availability-dependent rather than as a standing free tier on the pricing page, and reviews note that trial access often has to be requested. A $15 starter pack is usually the more reliable way to test.

**Can I share access with my team?** Yes, via the code-sharing and sub-account features in the dashboard.

**What about refunds on dead IPs?** Third-party reviews describe a short replacement window for IPs that never connect. Confirm the current policy in the dashboard before you build a workflow around it.

## The short version

If your rank tracking fails in the field, fix the request template before you shop for proxies. Once that's clean, decide whether your workload is text or rendering, and let that decide whether you pay per gigabyte or per IP. For most SEO teams pulling SERPs at scale, a bandwidth pack covers the job for a fraction of what an IP package costs. The IP packages earn their place when sessions must survive and bandwidth must stop being a line item — which, in practice, is when you graduate into browser-based verification work.

👉 [Open a 9Proxy account and pick the plan that matches your workload](https://bit.ly/9-Proxy)
