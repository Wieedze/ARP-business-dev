# Adjacent markets that clear money for trust, discovery or verification of software components

All URLs read on 2026-10-29 unless otherwise stated. "Reported" means a company filing, press release or official page. "Estimate" means a third party estimate (Sacra, GetLatka, etc.) and is flagged as such.

## 1. Package registries: who pays, and for what?

### Takeaway
Public discovery and publishing on registries is free everywhere. Money comes from enterprises paying for private hosting, proxying/caching, access control and compliance (JFrog is a $532M/yr public business). Public registries themselves are cost centres that are only now trying to charge their heaviest corporate consumers or corporate organisations.

### Cited Findings
- npm: Free ($0) for public package authors with unlimited public packages; Pro $7/month and Teams $7/user/month, both adding unlimited private packages and permissions. No paid tier is about public discovery. [npm pricing](https://npmjs.com/pricing)
- GitHub: Free plan includes 500 MB Packages storage; Team $4/user/month (first 12 months) with 2 GB; Enterprise from $21/user/month with 50 GB, SAML SSO, audit log API, SOC reports, FedRAMP. Paid value is governance/compliance, not trust signals. [GitHub pricing](https://github.com/pricing)
- PyPI Organizations announced 2023-04-23; free for community projects, "a small fee" for corporate projects. [PyPI blog](https://blog.pypi.org/posts/2023-04-23-introducing-pypi-organizations/)
- PyPI corporate organizations priced at $5 per member user per month; community organizations free; an org without a paid seat is deactivated. [PyPI docs](https://docs.pypi.org/organization-accounts/pricing-and-payments/)
- As of March 2025, PyPI paid Organizations were still in closed beta; the goal of paid features is to make PyPI "a staffed platform that can respond to support requests"; PyPI has over 600,000 projects and served 235.7B downloads two years earlier. [DevClass, 2025-03-10](https://devclass.com/2025/03/10/pypi-repository-takes-steps-towards-paid-services-as-volunteers-struggle-to-meet-demand/)
- JFrog (reported, FY2025 ended 2025-12-31, released 2026-02-12): revenue $531.8M (+24% YoY); cloud revenue $243.3M (+45%); 1,168 customers above $100K ARR; 74 above $1M ARR; net dollar retention 119%; FY2026 guidance $623M to $628M. [JFrog press release](https://jfrog.com/press-room/jfrog-announces-fourth-quarter-and-fiscal-2025-results/)
- JFrog "Security Core" (curation, advanced security) was 7% of FY2025 revenue, 10% of ARR and 16% of RPO, i.e. the security/trust add-on is a growing but minority share of a business driven by artifact management. [JFrog press release](https://jfrog.com/press-room/jfrog-announces-fourth-quarter-and-fiscal-2025-results/)
- Cloudsmith raised a $23M Series B (2025-03-03, led by TCV); earlier $26M Series A; about 100 employees; ~three quarters of revenue from US customers; the product is a private registry that mirrors PyPI, Docker Hub, Maven Central, npm and scans/blocks risky artifacts. No revenue disclosed. [TechCrunch](https://techcrunch.com/2025/03/03/cloudsmith-raises-23m-to-solve-software-supply-chain-security/)
- Cloudsmith 2025: total package delivery +352% YoY, headcount +92%; no customer count or ARR disclosed. [Cloudsmith blog](https://cloudsmith.com/blog/cloudsmith-2025-by-the-numbers)
- Maven Central (run by Sonatype): "83% of the total bandwidth of Maven Central is being consumed by just 1% of the IP addresses"; roughly three quarters of traffic from hyperscale cloud customers; Sonatype response is throttling (HTTP 429) and pushing caching proxies such as Nexus Repository. [Sonatype blog, 2024-06-26](https://www.sonatype.com/blog/maven-central-and-the-tragedy-of-the-commons?hs_amp=true)
- Secondary report: ~9.8T to 10T open source downloads per year; "82% of Maven Central consumption coming from less than 1% of IPs"; registries are discussing tiered/volume pricing for heavy users, not charging yet. [Startup Fortune, 2026-05-06](https://startupfortune.com/open-source-downloads-have-hit-10-trillion-and-the-hidden-commons-is-starting-to-bill-its-biggest-users/)
- Anaconda: March 2024 terms require government and non-profit entities with over 200 employees or contractors to buy Business/Enterprise licences; legal notices threatened back bills; Mass General Brigham had to buy licences and pulled Anaconda from its HPC repositories; researchers "scrambling". CEO said revenue from academia/non-profits was not higher than a year or two earlier. Anaconda sued Intel over expired licence use. [The Register, 2024-08-08](https://www.theregister.com/2024/08/08/anaconda_puts_the_squeeze_on/)
- Sonatype has been majority owned by Vista Equity Partners since 2019. [Sonatype blog](https://www.sonatype.com/blog/vista-acquires-a-majority-interest-in-sonatype)

### Inferences
- The paying party is the enterprise consumer's platform/security team, buying private hosting, a caching proxy (to stop hitting public registries) and policy gates. The publisher of public packages never pays, and nobody pays for public discovery or ranking.
- Monetisation of the commons happens by gating at a threshold (Anaconda: org size; PyPI: corporate orgs; Maven Central: heavy-IP throttling), and these moves cause backlash and migration rather than large revenue.
- For agent/tool reputation: the analogue that pays is "a private, curated proxy of approved agents/tools inside the enterprise" (JFrog Curation, Cloudsmith), not a public score.

### Gaps
- Sonatype revenue is not public; I found no reliable recent figure.
- Anaconda revenue/ARR: only Sacra pages surfaced (not fetched); treat any number as an estimate.
- npm Enterprise pricing not listed on npm's pricing page.
- Whether PyPI corporate billing has gone live by Oct 2026 was not confirmed.

## 2. Software supply chain trust: what sells, and what happened to free trust scores?

### Takeaway
Buyers pay substantial sums for supply chain security when it is a blocking control (firewall, hardened images, SCA in CI) bought by enterprises, with valuations in the billions. Standalone public "trust score" products have been free, been renamed/pivoted (Stacklok Trusty became Stacklok Insight, while Stacklok's focus moved to an MCP platform) or been sold off as assets (Phylum to Veracode). Regulatory pull in the US softened in 2026; the EU CRA becomes the main mandate.

### Cited Findings
- Snyk (estimate, Sacra, 2026-03-08): $326M ARR in Feb 2026, +7% YoY, down from 27% growth the year before; ~$300M ARR in 2024 and $250M at end of 2023 per earlier Sacra coverage; valuation marked to ~$3.7B by BlackRock vs $7.4B peak. All Sacra estimates, not company-reported. [Sacra](https://sacra.com/research/snyk-at-326m-arr-growing-7-yoy/)
- Snyk pricing: Free $0 (Open Source 200 tests, Code 100, IaC 300, Container 100; 5 projects); Team from $25/month (100 projects); Enterprise is credit-based ("1 credit = $1"), contact sales. [Snyk plans](https://snyk.io/plans/)
- Chainguard (reported to Fortune, 2025-04-23): $356M Series D at $3.5B valuation (up from $1.12B the previous summer); $40M ARR at end of fiscal 2025 after 7x growth; targeting $100M ARR by end of fiscal 2026; 150+ customers incl. Canva, HPE, GitLab; buyers are engineering teams paying for a "trusted source" of open source (hardened images/packages). [Fortune](https://fortune.com/2025/04/23/exclusive-chainguard-secures-356-million-series-d-as-valuation-soars-to-3-5-billion)
- Socket: $60M Series C at $1B valuation, $125M total raised, led by Thrive Capital with a16z, ~100 employees; products include Socket Firewall (blocks malicious packages in dev/CI), certified patches, and protection for browser extensions, editor extensions, AI tools and MCP servers. No revenue disclosed. [SecurityWeek](https://www.securityweek.com/socket-raises-60-million-at-1-billion-valuation/); round dated May 2026 per [Cooley, 2026-05-20](https://www.cooley.com/news/coverage/2026/2026-05-20-socket-raises-$60-million-series-c-at-$1-billion-valuation)
- Endor Labs raised a $93M Series B (April 2025). [Latham & Watkins](https://www.lw.com/en/news/2025/04/latham-watkins-advises-on-endor-labs-us93-million-series-b-financing-round); ARR not found.
- Phylum: Veracode acquired "certain assets of Phylum, Inc., including its malicious package analysis, detection, and mitigation technology" (2025-01-07); price undisclosed; folded into Veracode SCA. An asset sale, not a company acquisition. [Veracode release via SecurityInfoWatch](https://www.securityinfowatch.com/cybersecurity/press-release/55253331/veracode-veracode-acquires-phylum-inc-technology-to-transform-software-supply-chain-security)
- Stacklok Trusty: "Trusty is now known as Stacklok Insight!" (2024-12-05); domain moved to insight.stacklok.com; v1 API deprecated (2024-11-11) with no removal date. [Stacklok changelog](https://docs.stacklok.com/insight/about/changelog). Trusty VS Code extension was "temporarily" removed. [Trusty FAQ](https://docs.stacklok.com/trusty/about/faq)
- Stacklok's current homepage promotes ToolHive (an open source MCP platform) and an agent harness, with no mention of Trusty/Insight. [Stacklok](https://stacklok.com/trusty)
- US mandate weakening: OMB M-26-05 rescinded M-22-18 and M-23-16 (mandatory secure software attestations); agencies may still request attestations and SBOMs but are not required to; CISA SBOM templates still draft. [Davis Wright Tremaine, 2026-02-10](https://www.dwt.com/blogs/privacy--security-law-blog/2026/02/omb-changes-course-on-software-security)
- EU Cyber Resilience Act (Regulation (EU) 2024/2847): vulnerability/incident reporting obligations from 2026-09-11 (24h early warning, 72h notification); full essential requirements including SBOM from 2027-12-11; fines up to €15M or 2.5% of global turnover. Source is a vendor marketing page. [HeroDevs](https://www.herodevs.com/eu-cyber-resilience-acts)

### Inferences
- What sells: controls that sit in the path (block/allow at install time, hardened artifacts with SLAs) and compliance evidence, bought top-down by enterprises. Chainguard and Socket valuations imply investors believe "trusted source plus enforcement" is a large market.
- What does not sell on its own: an advisory public trust score. Trusty was free, rebranded, and its parent's attention shifted to MCP tooling; Phylum's scoring tech ended as assets inside a larger SCA vendor; OpenSSF Scorecard, Sigstore, SLSA and deps.dev are free public goods that set the price of a generic score at zero.
- Snyk's growth deceleration (estimate) suggests even a category leader with a freemium developer funnel hits a ceiling; free tiers drive adoption, enterprise contracts drive revenue.
- Notably, Socket already markets protection for MCP servers and AI tools, and Stacklok pivoted to MCP: the incumbents in software supply chain trust are moving directly into agent/tool trust.

### Gaps
- Socket, Endor Labs, Chainguard 2026 ARR: not found in reported sources.
- Chainguard published price points not found.
- deps.dev, Libraries.io and npms.io status/decline: fetches failed or returned no content; no reliable source found on npms.io being unmaintained or on Libraries.io traffic. Report-writer should not claim decline without a source.
- OpenSSF Scorecard and Sigstore adoption numbers not gathered.

## 3. Uptime and status monitoring: own endpoints vs third party monitoring

### Takeaway
People pay modest SaaS fees ($12 to ~$1,500/month) to monitor and communicate about their own endpoints, with huge free tiers. Third party monitoring of others' services exists as a niche (StatusGator, IsDown at $22 to $300/month aggregating vendor status pages), and at scale only as an advertising/data business (Downdetector inside Ookla, ~$231M revenue division sold for $1.2B), where the consumer is free and telecoms/enterprises/advertisers pay.

### Cited Findings
- UptimeRobot: 2,306,643 community members and 7,999,157 monitors at end of 2023 (6.39M HTTP/S); site claims "3.4M+" users; no paying customer or revenue figures. [UptimeRobot blog](https://uptimerobot.com/blog/2023-wrapped/)
- UptimeRobot pricing: Free 50 monitors; Solo $12/month annual; Team $39/month (100 monitors); Scale $79/month (200 monitors); Enterprise custom. [UptimeRobot pricing](https://uptimerobot.com/pricing/)
- Better Stack: 4,000+ customers, 200,000+ developers; "unintentionally" profitable; $10M round (Jan 2024) after $18.6M Series A (2022); no revenue disclosed. [Tech.eu, 2024-01-22](https://tech.eu/2024/01/22/better-stack-unintentionally-reaches-profitability-adds-10m-to-continue-growth/)
- Atlassian Statuspage: public pages Free, $29, $99, $399, $1,499/month; private pages $79 to $1,499/month; audience-specific from $300/month. The status page owner pays to publish its own status. [Atlassian](https://www.atlassian.com/software/statuspage/pricing)
- StatusGator (third party vendor status aggregation): Free 3 monitors; Starter $72/month annual (25); Team $137/month (75); Corporate $274/month (150); Enterprise custom; tracks "more than 12,110 services"; positioned for IT teams to "reduce tickets". [StatusGator plans](https://statusgator.com/plans)
- IsDown: Starter $22/month annual (15 monitors) up to Business $150/month (150), MSP $200; Outage Data API unpriced (call). [IsDown pricing](https://isdown.app/pricing)
- Ziff Davis is selling its Connectivity division (Ookla: Speedtest, Downdetector, Ekahau, RootMetrics) to Accenture for $1.2B cash; division revenue $231M in 2025 (~16% of Ziff Davis revenue). [Benton Institute, 2026-03-03](https://www.benton.org/headlines/ziff-davis-sell-connectivity-division-accenture-12-billion)
- Datadog Synthetics bills per 10K API test runs and per 1K browser tests; exact prices not retrieved. [Datadog pricing](https://www.datadoghq.com/pricing/?product=synthetic-testing-monitoring)

### Inferences
- The payer for monitoring is almost always the operator of the endpoint (self-interest, SLA), not the consumer. Third party monitoring (StatusGator, IsDown) sells to consumers of SaaS vendors, but at small-business price points; it is a niche, not a big market.
- The one large "third party reputation of others' services" business (Downdetector/Speedtest) monetises aggregate data and ads sold to network operators and enterprises, with the public view free. This is the closest structural analogue to a public agent uptime/reputation board: free for readers, monetised via data licensing to the measured parties and their competitors.

### Gaps
- UptimeRobot revenue and ownership not confirmed (search did not surface a reliable source).
- Pingdom and Checkly pricing/scale not gathered.
- Ookla revenue split (enterprise data vs advertising) not found.
- StatusGator/IsDown revenue: none found (StarterStory exists but not fetched; would be self-reported).

## 4. API directories and marketplaces: what failed and why

### Takeaway
Public API discovery has repeatedly failed to become a standalone business. RapidAPI, once valued at $1B with ~4M users, sold to Nokia in Nov 2024 for an undisclosed sum (speculated ~$100M) after 82% headcount cuts; ProgrammableWeb was shut by Salesforce in 2022 after 17 years. Discovery survives as a free feature of a tool people pay for (Postman).

### Cited Findings
- Rapid (RapidAPI): Nokia acquired it 2024-11-13; terms undisclosed, with Light Reading speculation "as little as $100 million"; previously valued at $1B (2022); raised nearly $273M (a16z, Microsoft, SoftBank); peak up to 4M users and ~40,000 APIs; active users now "in the thousands"; at least two layoff rounds cut headcount by 82%; unclear whether ever profitable. [TechCrunch](https://techcrunch.com/2024/11/13/nokia-acquires-rapid-the-api-company-once-valued-at-1b/)
- Dealroom headline cites "$150M assets" for the Nokia deal; conflicts with the ~$100M speculation and is unverified. [Dealroom](https://app.dealroom.co/news/feed/nokia-acquires-rapidapi-for-150m-assets)
- ProgrammableWeb shut down in October 2022 (often cited as 2023) after 17 years, under Salesforce (via MuleSoft); described as "a static API directory and a pay for play blog" with SEO-driven, transactional content. [API Evangelist, 2022-10-15](https://apievangelist.com/2022/10/15/programmableweb-is-shutting-down/)
- Postman Public API Network served 17M users and 500k organisations in 2021, framed as the largest public API hub; free discovery inside a paid collaboration tool. [Help Net Security, 2021-08-10](https://www.helpnetsecurity.com/2021/08/10/postman-public-api-network/)

### Inferences
- Marketplaces that tried to take a cut of API transactions (RapidAPI) or sell placement (ProgrammableWeb) lost to direct relationships: once a developer finds an API they integrate directly, so the intermediary loses the transaction.
- Discovery is valued only when bundled into a workflow the buyer already pays for. This is directly relevant to agent/MCP registries: a public directory alone is unlikely to monetise.

### Gaps
- RapidAPI revenue never disclosed; exact Nokia price not confirmed.
- APIs.guru: no business model data gathered (it is a free open source directory).
- ProgrammableWeb traffic/revenue at shutdown not found.

## 5. App stores and review platforms: who pays for reviews and ranking?

### Takeaway
In platform stores, review and curation are funded by transaction take rates (15 to 30%) or small anti-spam fees, never by readers. In B2B review sites, vendors pay (PPC, profiles, intent data) while readers are free. Trustpilot is a $261M revenue business paid by reviewed businesses.

### Cited Findings
- Apple: US App Store facilitated $406B in developer billings and sales in 2024; over 90% involved no Apple commission; Apple rejected 1.9M app submissions in 2024; prevented over $9B in fraud over five years. [Apple Newsroom, 2025-05-29](https://www.apple.com/newsroom/2025/05/app-store-in-the-us-facilitated-406-billion-usd-in-developer-billings-and-sales-in-2024)
- Google Play: 15% on the first $1M of annual revenue, 30% above; 15% on auto-renewing subscriptions; in AU/EEA/JP/UK/US a 10% service fee plus 5% billing fee structure. [Google Play Console Help](https://support.google.com/googleplay/android-developer/answer/112622)
- Chrome Web Store: one-time $5 developer registration fee, required upfront since 2020-03-12; framed as curbing spam/abusive extensions. [9to5Google](https://9to5google.com/2020/03/12/chrome-web-store-fee/)
- Trustpilot (reported trading update, 2026-01-13): FY2025 revenue $261M (+24%), bookings $291M (+22%); 1.3M businesses use Trustpilot; 361M+ reviews. Revenue is from business subscriptions. [Stockopedia RNS](https://www.stockopedia.com/share-prices/trustpilot-LON:TRST/news/strong-fy-25-performance-18-cc-bookings-growth-019e6a03-b708-7596-8255-460b493fe3ed/)
- G2: private, never published audited revenue. GetLatka estimates $112.9M (2023) and $162.9M (2024) revenue (estimates). CEO stated a $100M ARR target for end of 2022. ~3,000 paying vendors as of March 2022 on freemium (free listing, paid marketing tools); also data licensing (ServiceNow taxonomy, ~50 investors). [GetLatka](https://getlatka.com/blog/g2-revenue)
- Capterra: buyers free, vendors list free and pay per click for sponsored positions and for leads; acquired by Gartner September 2015 for $206.2M; 2M verified reviews by Jan 2023. [Wikipedia](https://en.wikipedia.org/wiki/Capterra)

### Inferences
- Readers never pay for ratings in any of these markets. Either the platform funds review from a transaction take (app stores) or the rated party pays for visibility/badges/leads (Trustpilot, G2, Capterra).
- Review as a gatekeeping cost (Apple's 1.9M rejections) is only sustainable because the platform controls distribution and payments.
- A $5 publisher fee is used as an anti-Sybil device rather than a revenue line, which is relevant to agent registries facing spam.

### Gaps
- VS Code Marketplace and WordPress plugin directory: no fees found/verified (both believed free to publish; not sourced, so do not assert).
- Chrome Web Store take rate (payments were deprecated) not sourced.
- Gartner Digital Markets segment revenue not gathered.

## 6. Credit and business reputation analogues

### Takeaway
Paid third party reputation at scale exists where the score gates a financial decision: Dun & Bradstreet earns $2.38B/yr (58% from Finance & Risk) and was taken private for $7.7B. Where the verification became automatable and was offered free (Let's Encrypt DV certs, now 762M websites), the paid market for that tier collapsed and incumbents moved up to higher assurance. BBB shows the conflict of interest when the rated party pays.

### Cited Findings
- Dun & Bradstreet FY2024 (reported, 2025-02-20): revenue $2,381.7M (+2.9%); Finance & Risk $1,375.5M; Sales & Marketing $1,006.2M (segment totals summed from regional figures). [D&B release via Silicon UK](https://www.silicon.co.uk/press-release/dun-bradstreet-reports-fourth-quarter-and-full-year-2024-financial-results)
- Clearlake took D&B private for ~$7.7B ($9.15/share), announced 2025-03-24, approved by shareholders 2025-06-12. [Jacksonville Daily Record, 2025-06-19](https://www.jaxdailyrecord.com/news/2025/jun/19/dun-bradstreet-shareholders-overwhelmingly-ok-77b-buyout)
- Let's Encrypt went from serving 492M to 762M websites over 2025; issues up to 10M certificates on some days; ISRG is a 501(c)(3) "100% supported by donations"; turned off OCSP in August 2025. [Let's Encrypt EOY letter, 2025-12-29](https://letsencrypt.org/2025/12/29/eoy-letter-2025)
- Early impact (2016): Let's Encrypt had ~13.1% SSL share within 10 months of public beta; at that time it slowed rather than hurt other CAs; issued DV only (no EV), 90 day certs. [W3Techs, 2016-09-26](https://w3techs.com/blog/entry/the_impact_of_lets_encrypt_on_the_ssl_certificate_market)
- BBB: nearly $200M revenue in 2013, mostly from businesses it oversees; accreditation fees from several hundred to over $10,000/yr; critics call business funding a "serious conflict of interest"; CNNMoney found 100+ companies facing government action with A ratings. [CNNMoney, 2015](https://money.cnn.com/2015/09/30/news/better-business-bureau-millions/)

### Inferences
- The buyer of credit-style reputation is the counterparty taking financial risk (lenders, suppliers, procurement), paying because the score changes a money decision and is backed by proprietary data (DUNS) and liability. That is the strongest precedent for paid agent reputation, but it requires a counterparty with money at risk per decision.
- Let's Encrypt is the cautionary tale: once a verification is automatable and a credible non-profit offers it free with industry sponsors, its price goes to zero. Generic agent identity/liveness verification is likely to follow that path; paid value sits in higher-assurance, liability-backed or decision-gating signals.
- BBB-style "rated party pays" models invite credibility attacks.

### Gaps
- Current Let's Encrypt market share and DV certificate price history (e.g., pre/post 2015 prices) not sourced; avoid stating specific price collapse figures.
- Credit bureau (Experian/Equifax/TransUnion) revenue not gathered.
- BBB current revenue/accredited business counts not gathered (2013 data only).
