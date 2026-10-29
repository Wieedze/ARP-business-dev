# Non-crypto agent and tool discovery: MCP registries, skill registries, agent directories, and demand (as of 2026-10-29)

All "read" dates are 2026-10-29 (the date this research was done) unless stated. "Measured" means the figure comes from an independent count, crawl or probe with a stated method. "Self-reported" means the vendor's own figure, or a number shown on its site with no method given. Note: direct calls to registry.modelcontextprotocol.io from the research sandbox were blocked by the proxy, so this research did not do its own registry census. Every registry figure below comes from third-party censuses that state their method.

## Q1. Competitor table: what is shipped, usage, and pricing

### Takeaway
The market splits into three tiers. (a) Open MCP directories and crawlers (Glama, mcp.so, MCP Market, PulseMCP, Smithery, mcpservers.org) are free to browse and earn money, if at all, from hosting, gateways or sponsored placement. (b) Platform-owned app stores (OpenAI Apps, Claude connectors, Salesforce AgentExchange, GitHub MCP Registry, Docker) are curated, and their stores are not billed directly. (c) Hyperscaler enterprise registries (AWS Agent Registry, Google Agent Registry, Microsoft Agent 365) sell governance and inventory to enterprises. Only AWS publishes per-search-call pricing. None of these vendors reports registry revenue. The clearest consolidation event is Arcade buying Smithery (August 2026).

### Cited Findings

**Official MCP Registry (registry.modelcontextprotocol.io)**
- Shipped: preview opened 8 Sep 2025. It is still labeled "in preview", with "no uptime or data durability guarantees". It offers an unauthenticated read-only REST API (`GET /v0.1/servers`, cursor pagination, `updated_since`). It is designed for aggregators to scrape "once per hour" and store the data themselves, and for "subregistries" to re-serve it with custom `_meta` fields (ratings, download counts, security scans). Pricing: free. — [MCP docs: Registry Aggregators](https://modelcontextprotocol.io/registry/registry-aggregators) (read 2026-10-29)
- The registry repo had 7,391 GitHub stars and 1,032 forks (read 21 Oct 2026). Measured. — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- Server counts over time are covered in Q2.

**Glama (glama.ai)**
- 112,077 servers listed, "Updated 2026-10-29 07:30" (self-reported on the site). Cards show letter grades for license, quality and maintenance, but no security grade. The site offers a public "MCP Directory API" (`GET /v1/servers`). — [Glama servers page](https://glama.ai/mcp/servers) (read 2026-10-29)
- Pricing: Starter $9/month, Pro $26/month, Business $80/month. Each plan bundles the same amount in AI credits plus 3, 10 or 30 hosted servers. There is no permanent free plan. Pricing was verified in October 2026. — [Toolradar, citing glama.ai/pricing](https://toolradar.com/tools/glama/pricing)
- Funding and revenue: none found.

**Smithery (smithery.ai), now part of Arcade**
- The site shows "Browse 27,365+ MCPs" and per-listing usage figures, for example "22.49k uses" and "43.39k uses". The site does not define "uses". Self-reported. — [smithery.ai](https://smithery.ai/) (read 2026-10-29)
- Arcade acquired Smithery, announced 5 Aug 2026. Terms were not disclosed. Smithery's own usage metrics were not disclosed. Arcade raised a $60M Series A (led by SYN Ventures, with Morgan Stanley and Wipro) for $72M in total funding. Arcade says its own call volume grew 25x in six months (self-reported). — [Forbes, 10 Aug 2026](https://www.forbes.com/sites/janakirammsv/2026/08/10/arcade-acquires-smithery-to-own-the-agent-tool-supply-chain/)
- Pricing: freemium, with usage-based hosting. Sources conflict on creator monetization: some listings claim an 80% creator share, while an independent review says there is "no creator monetization". — [SEOSiri, 13 Sep 2026](https://www.seosiri.com/2026/09/mcp-monetization-gap-glama-smithery-developer-losses.html)
- Smithery offers a CLI and a registry API, so programmatic access exists. — [Innvesti, Jun 2026](https://www.innvesti.com/reports/best-mcp-server-directories-2026/)
- Smithery's pre-acquisition funding: no source could be retrieved (Tracxn blocked the fetch). Gap.

**mcp.so**
- The homepage shows no total. Third parties cite about 21,895 servers (2026, self-reported) and "20,000+" (Aug 2026). Free. Limited programmatic access. — [Innvesti, Jun 2026](https://www.innvesti.com/reports/best-mcp-server-directories-2026/); [Unyly, 3 Aug 2026](https://unyly.org/mcp-directories)
- Academic crawl, July–September 2025: 16,646 raw entries, of which only 7,223 were valid (43.4%). — [arXiv 2509.25292](https://arxiv.org/html/2509.25292v1)

**MCP Market (mcpmarket.com)**
- Homepage: "50,680 Servers", plus a skills section (self-reported, read 2026-10-29). — [mcpmarket.com](https://mcpmarket.com/)
- No public API. Free. — [Innvesti, Jun 2026](https://www.innvesti.com/reports/best-mcp-server-directories-2026/)
- Academic crawl, 2025: 14,280 raw entries, of which only 3,765 were valid (26.4%, the lowest validity of any market studied). — [arXiv 2509.25292](https://arxiv.org/html/2509.25292v1)

**PulseMCP**
- 21,710 servers listed on 14 Oct 2026. — [LocalCan, 15 Oct 2026](https://www.localcan.com/blog/state-of-mcp-server-development)
- Paused new submissions in mid-August 2026 for an ingestion rework. — [Innvesti, 24 Aug 2026](https://innvesti.com/reports/mcp-server-cards-roadmap-discovery-tools-2026/)
- Free, and not a hosting or billing platform. — [SEOSiri](https://www.seosiri.com/2026/09/mcp-monetization-gap-glama-smithery-developer-losses.html)

**mcpservers.org**
- About 9,800+ listings (3 Aug 2026). — [Unyly](https://unyly.org/mcp-directories)
- The homepage shows sponsor-labeled entries (Bright Data, Scout Monitoring, Alpha Vantage), which suggests paid placement. — [mcpservers.org](https://mcpservers.org/) (read 2026-10-29)

**Composio**
- Raised a $25M Series A led by Lightspeed, for $29M total (July 2025). Says it has "1500+ tools" and names customers Glean, Browser Use and Pelago Health. No usage metrics given. — [Composio blog](https://composio.dev/blog/series-a); [TheSaaSNews](https://www.thesaasnews.com/news/composio-raises-25m-series-a/)

**Zapier MCP**
- No separate fee: "Each successful tool call through your MCP server consumes two tasks" from the existing Zapier plan. Listing tools is not billed. — [Zapier docs](https://docs.zapier.com/mcp/usage.md) (read 2026-10-29)

**Cloudflare and Vercel hosting (as an indicator of where remote servers run)**
- Hostnames among official-registry remote URLs (14 Oct 2026): `workers.dev` 3,130, `vercel.app` 342, `railway.app` 247, `onrender.com` 244 (out of 28,332). The npm package `mcp-handler` (Vercel's adapter) had 5.40M downloads in 30 days, up 25.5x year over year. Measured. — [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development)

**Docker MCP Catalog**
- Beta launched 5 May 2025 (announced 22 Apr 2025). "300+ verified servers", with signed images and SBOMs. Bundled with Docker Desktop at $11–$24 per user per month. No pull counts reported. — [ChatForest](https://chatforest.com/reviews/docker-mcp-servers/)
- 1,177 active official-registry servers ship as OCI images (21 Oct 2026). — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)

**GitHub MCP Registry**
- Launched 16 Sep 2025 with "over 40" curated servers and one-click install into VS Code. No usage numbers. — [InfoQ, 13 Oct 2025](https://www.infoq.com/news/2025/10/github-mcp-registry/); [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- GitHub topic counts, 21 Oct 2026: 38,336 repos tagged `mcp-server` and 39,302 tagged `model-context-protocol`. — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)

**Anthropic: Claude connectors, plugins and skills**
- Claude marketplace connectors grew from 75+ (Dec 2025) to 995 (21 Oct 2026). Company-reported. — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- A third-party mirror, claudemarket.ai, lists "1,625 connectors". It is unofficial and was not reconciled with the 995 figure. — [claudemarket.ai](https://claudemarket.ai/connectors)
- Agent Skills (SKILL.md) launched in Claude Code in October 2025, and the open standard was published 18 Dec 2025. — [TerminalBlog, 24 Jul 2026](https://terminalblog.com/blog/agent-skills-670k-security-reckoning/)
- Official plugin marketplace size: no reliable count found. Gap.

**skills.sh (Vercel)**
- Launched 20 Jan 2026. It is free, with an MIT-licensed CLI. Skills are listed automatically from install telemetry, with no submission or review. Ranking is by install count. — [rywalker.com research](https://rywalker.com/research/skills-sh)
- June 2026: 669,670 skills and 43.6M total installs. The top skill, `find-skills`, had 2.0M installs. Secondary source. — [TerminalBlog](https://terminalblog.com/blog/agent-skills-670k-security-reckoning/); [rywalker](https://rywalker.com/research/skills-sh)
- Live leaderboard (read 2026-10-29): `find-skills` at 4.1M, `grill-me` (mattpocock) at 1.5M, `hyperframes-cli` at 1.3M. The "All Time (1,526,960)" label is smaller than the top skill's own count and is unexplained. — [skills.sh](https://skills.sh/)

**SkillsMP (skillsmp.com)**
- The page code sets `skills=17570`. Skills are scraped from public GitHub, and repos with fewer than 2 stars are dropped. No API mentioned. — [skillsmp.com](https://skillsmp.com/) (read 2026-10-29)
- Conflict: an academic crawl in January 2026 collected 73,193 skills from skillsmp.com, so the site's count method has changed or it has filtered heavily. — [arXiv 2602.06547](https://arxiv.org/html/2602.06547v1/)

**OpenAI ChatGPT Apps directory**
- The App Directory launched and third-party submissions opened 17 Dec 2025. The launch cited 800M+ ChatGPT users. "Monetization limits remain." — [Ground News](https://ground.news/article/openai-now-accepting-chatgpt-app-submissions-from-third-party-devs-launches-app-directory)
- A community list counted 1,624 apps and 14 connectors (2 Jul 2026), but its meta description says "330 verified", and the two figures are unreconciled. Unofficial. — [awesome-chatgpt-apps](https://github.com/rdmgator12/awesome-chatgpt-apps)

**Google: Gemini Enterprise Agent Platform, Agent Registry and A2A**
- Announced 22 Apr 2026 at Next '26, succeeding Vertex AI. Agent Registry is "a single source of truth" that indexes internal agents, tools and skills. Agent Identity gives each agent "a unique cryptographic ID". The announcement does not describe an A2A discovery mechanism. The only usage figure is 6T tokens per month through ADK. — [Google Cloud blog](https://cloud.google.com/blog/products/ai-machine-learning/introducing-gemini-enterprise-agent-platform)
- The registry supports automatic registration, and A2A agents can be registered in Gemini Enterprise. — [Agent Registry docs](https://docs.cloud.google.com/agent-registry/automatic-registration); [Register A2A agents](https://docs.cloud.google.com/gemini/enterprise/docs/register-and-manage-an-a2a-agent)
- No pricing or usage counts found for Google's registry. Gap.

**Microsoft: Agent 365, Entra Agent ID and the Agent Registry**
- Agent 365 became generally available 1 May 2026. It costs $15 per user per month standalone, or comes inside the M365 E7 bundle. The registry inventories agents that have an Entra Agent ID, agents in the Teams and Agent Store, and shadow agents found via Defender and Intune. No count of agents or customers given. — [holgerimbery.blog](https://holgerimbery.blog/agent-365-ga)

**AWS: Agent Registry (AgentCore)**
- Preview in April 2026; generally available 31 Aug 2026 in 5 regions. It indexes agents, tools, skills and MCP servers, and supports MCP and A2A natively. It offers hybrid keyword and semantic search, approval workflows, and access via an MCP server that "MCP-compatible clients such as Kiro and Claude Code can query". — [InfoQ, 17 Apr 2026](https://www.infoq.com/news/2026/04/aws-agent-registry-preview/); [AWS What's New](https://aws.amazon.com/about-aws/whats-new/2026/04/aws-agent-registry-in-agentcore-preview)
- Pricing at general availability: records cost $0.40 per 1K after the first 5K; Search API calls cost $0.02 per 1K after the first 1M; Get and List calls cost $0.004 per 1K after the first 2M. No usage figures published. — [Tech Insider AU](https://tech-insider.org/au/aws-agent-registry-general-availability-2026/)

**Salesforce AgentExchange**
- Launched 4 Mar 2025 with 200+ partners. It absorbed AppExchange and the Slack Marketplace in April 2026. The April 2026 relaunch cited 10,000+ apps, 2,600+ Slack apps and agents, 1,000+ Agentforce agents, tools and MCP servers, and 186,000 reviews. A $50M builders program accompanied it. The revenue share for agent components is undisclosed. Self-reported. — [PPC Land, 20 Oct 2026](https://ppc.land/agentexchange/)

**Hugging Face and LangChain Hub**
- Hugging Face runs a hosted MCP server (hf.co/mcp) and can expose Gradio Spaces as MCP servers. No count of MCP-enabled Spaces was found. — [HF docs](https://huggingface.co/docs/hub/en/spaces-mcp-servers)
- LangChain Hub now lives under `langchain-classic`, which suggests legacy status. No usage data found. — [LangChain reference](https://reference.langchain.com/python/langchain-classic/hub)

**MCP security and trust-scoring vendors**
- Snyk acquired Invariant Labs, the maker of mcp-scan, in June 2025. Its tool is now Snyk Agent Scan, which covers MCP servers and skills. — [BankInfoSecurity](https://www.bankinfosecurity.com/embargo-0624-9am-et-agentic-ai-security-gets-fuel-snyks-invariant-labs-buy-a-28789); [Snyk Labs](https://labs.snyk.io/resources/snyk-labs-invariant-labs/)
- Vendor landscape (October 2026, written by a vendor, Aembit): Aembit, Runlayer, Lasso, Snyk/Invariant, Pillar, Wiz, TrueFoundry, MintMCP and Cisco AI Defense. None advertises a public "trust score". — [Security Boulevard, 23 Oct 2026](https://securityboulevard.com/2026/10/top-9-mcp-security-platforms-and-gateways-in-2026)
- Runlayer raised an $11M seed (Khosla's Keith Rabois and Felicis, November 2025). A later $30M Series A is reported, date unverified. — [TechCrunch, 17 Nov 2025](https://techcrunch.com/2025/11/17/mcp-ai-agent-security-startup-runlayer-launches-with-8-unicorns-11m-from-khoslas-keith-rabois-and-felicis); [OffSeq](https://radar.offseq.com/threat/runlayer-raises-30-million-in-series-a-funding-bac6b452930c3234)
- Enkrypt AI offers an "MCP Scanner". — [Enkrypt AI](https://www.enkryptai.com/newsroom/ai-startups-received-2-9-billion-in-funding-last-quarter-these-3-u-s-companies-received-a-lot-of-it--and-youve-probably-never-heard-of-them)
- The mpak Trust Framework (NimbleBrain) is a scoring system, but no published scores were found. — [NimbleBrain, Mar 2026](https://nimblebrain.ai/blog/state-of-mcp-security-2026/)
- Golf and MCP-Shield: no reliable sources retrieved. Gap.

**Monetization layer (developer payouts)**
- Apify pays developers 80% and reportedly pays out $500K–$1.2M per month. MCP Marketplace takes a 15% fee and lists 5,800+ servers. MCPize pays 80–85%. x402 reportedly saw 3.3M transactions in 30 days averaging $0.46. Fewer than 5% of listed MCP servers are on a monetized path (ChatForest). These are all secondary and unverified. — [SEOSiri, 13 Sep 2026](https://www.seosiri.com/2026/09/mcp-monetization-gap-glama-smithery-developer-losses.html)

### Inferences
- No open directory (Glama, mcp.so, MCP Market, PulseMCP) discloses revenue or traffic. Their business models are hosting and gateway subscriptions (Glama, Smithery) or sponsorship (mcpservers.org). Consolidation into runtime and gateway companies (Arcade plus Smithery) suggests that discovery alone is hard to monetize.
- Hyperscalers price governance, not discovery. AWS's $0.02 per 1K searches is effectively free at any realistic volume, which leaves little room for a paid standalone discovery API.
- A trust and reputation layer is under-served. Directories show quality, license and maintenance grades (Glama) and "uses" counts (Smithery). Security vendors scan and gate. No one offers a portable, cross-registry reputation score that agents consume.

### Gaps
- Funding for Glama, PulseMCP, mcp.so, MCP Market and Smithery before the acquisition.
- Official counts for Anthropic plugins and the OpenAI app directory.
- Usage of any registry API (see Q4).

## Q2. Supply side: size, growth and quality

### Takeaway
The official registry grew from about 1,200 servers (end of 2025) to about 48,000 names (21 Oct 2026). Monthly additions roughly doubled every 2–3 months, and September 2026 alone added about 11,800. Quality is poor and concentrated. About 61% of servers were published once, and about 79% published nothing new in the prior 90 days. Of remote servers, only about 52% complete an unauthenticated handshake, and about 7% are dead. Only about 49% of random npm/stdio servers start at all. In the third-party directories, roughly half of crawled listings are invalid, and about 28–42% are duplicates or forks.

### Cited Findings: dated listing counts (official MCP Registry, unique server names)
- Nov 2025: "close to 2,000 entries" (MCP project). — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- Cumulative names first published by date (registry API, read 21 Oct 2026): 1,204 by 31 Dec 2025; 9,599 by 24 May 2026; 25,761 by 31 Aug 2026; 47,879 (47,267 active) on 21 Oct 2026. Measured. — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- 4 Mar 2026: 3,012 unique servers from 8,074 entries. Of these, 84.6% publish source, 10.6% are remote-only and 4.8% have no source. Measured. — [NimbleBrain](https://nimblebrain.ai/blog/state-of-mcp-security-2026/)
  - Caution: NimbleBrain's 3,012 on 4 Mar 2026 conflicts with later censuses, which imply more than 4,000 names first published by then. This is likely due to deletions or a different counting method.
- 25 Jul 2026: 18,387 distinct servers from 58,230 version records. Counting records instead of servers overstates the total by 3.2x. Measured. — [Circadian Agent](https://circadian-agent.com/research/mcp-registry)
- 22 Aug 2026: 24,135 unique servers. Measured. — [arXiv 2609.10962](https://arxiv.org/pdf/2609.10962)
- August 2026 harvest: 21,643 servers and 72,606 version records. Measured. — [arXiv 2609.14119](https://arxiv.org/pdf/2609.14119)
- 24 Sep 2026: 35,491 servers, 20,581 publishers and 114,876 versions. New publishers per month grew from 277 (September 2025) to 3,962 (August 2026). Measured. — [Oktopost](https://www.oktopost.com/blog/mcp-registry-legacy-servers/)
- 14 Oct 2026: 43,012 active servers from 43,538 names and 150,595 versions. Of these, 64% have a remote URL. 27 bulk namespaces (each with more than 50 servers) hold 9,094 servers. Measured. — [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development)
- New servers per month (LocalCan, by first publish date): Sep 2025 454; Dec 2025 274; Jan 2026 386; Feb 1,071; Mar 1,894; Apr 2,526; May 2,993; Jun 3,806; Jul 5,025; Aug 6,464; Sep 11,809; 1–14 Oct 5,846. Remote share of new servers rose from 35% to 77% (excluding bulk publishers). — [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development)
- The Circadian (July) and LocalCan (October) monthly series differ slightly (for example, July 4,523 versus 5,025) because names were published retroactively and counted later.

### Cited Findings: dated directory counts (self-reported, and not comparable with each other)
- Glama: about 31,644 servers (4 Jun 2026) [Innvesti](https://www.innvesti.com/reports/best-mcp-server-directories-2026/); 67,600+ (3 Aug 2026) [Unyly](https://unyly.org/mcp-directories); 77,220 (24 Aug 2026) [Innvesti](https://innvesti.com/reports/mcp-server-cards-roadmap-discovery-tools-2026/); 97,619 (14 Oct 2026) [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development); 112,077 (29 Oct 2026) [Glama](https://glama.ai/mcp/servers).
- Smithery: 6,751 raw (2025 crawl) [arXiv 2509.25292](https://arxiv.org/html/2509.25292v1); 7,000+ (June and August 2026, possibly stale); 17,021+ (August 2026) [Innvesti](https://innvesti.com/reports/mcp-server-cards-roadmap-discovery-tools-2026/); 26,700+ (14 Oct 2026) [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development); 27,365+ (29 Oct 2026) [smithery.ai](https://smithery.ai/).
- PulseMCP: 6,013 raw (2025) [arXiv 2509.25292](https://arxiv.org/html/2509.25292v1); 16,820+ (June 2026) [Innvesti](https://www.innvesti.com/reports/best-mcp-server-directories-2026/); 11,800+ (August 2026, per Unyly, conflicting) [Unyly](https://unyly.org/mcp-directories); 21,710 (14 Oct 2026) [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development).
- MCP Market: 14,280 raw (2025) [arXiv 2509.25292](https://arxiv.org/html/2509.25292v1); 10,000+ (2026) [Innvesti](https://www.innvesti.com/reports/best-mcp-server-directories-2026/); 50,680 (29 Oct 2026) [mcpmarket.com](https://mcpmarket.com/).
- mcp.so: 16,646 raw (2025); about 21,895 (2026); 20,000+ (August 2026). The arXiv authors note that mcp.so "has largely plateaued". — [arXiv 2509.25292](https://arxiv.org/html/2509.25292v1)
- Anthropic: "more than 10,000 active public MCP servers" (9 Dec 2025, company-reported). — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- Arcade's ToolBench indexes 43,400+ MCP servers and 219,069 tools (August 2026). — [Forbes](https://www.forbes.com/sites/janakirammsv/2026/08/10/arcade-acquires-smithery-to-own-the-agent-tool-supply-chain/)
- Skills: skills.sh had 669,670 skills (June 2026). SkillsMP had 73,193 (January 2026, crawled) and 17,570 (October 2026, on site). skills.rest had 25,187 (January 2026). — [TerminalBlog](https://terminalblog.com/blog/agent-skills-670k-security-reckoning/); [arXiv 2602.06547](https://arxiv.org/html/2602.06547v1/); [skillsmp.com](https://skillsmp.com/)

### Cited Findings: reachability and functionality (measured)
- **Remote handshake probe (LocalCan, 14 Oct 2026):** random sample of 500 from 16,718 active Streamable HTTP remotes (margin of error about ±4.4 points). Results: 51.8% completed `initialize` without credentials; 33.0% returned 401 with OAuth `resource_metadata`; 5.6% returned other 401s; about 7% were dead (3.4% no answer, 2.6% returned 404 or 405, 1.0% returned 5xx); 0.4% returned 402. Of the parseable handshakes, 23.0% used a protocol revision older than 2025-11-25. Method: one unauthenticated request, 10 s timeout, no redirects. This measures handshakes, not working tool calls, so it is an upper bound. — [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development)
- **Local npm/stdio probe (Afsar, August 2026):** random sample of 400 from 7,258 npm stdio servers (registry snapshot of 24,135, 22 Aug 2026). Results: 48.8% functional (handshake completed); 37.5% did not start; 13.3% required credentials; 0.5% had an unavailable package. A curated comparison set was 66.7% functional. 58.8% of tools carry no safety annotations. Exact duplicate tools among real servers: 0.4%. — [arXiv 2609.10962](https://arxiv.org/pdf/2609.10962)
- **MCPZoo (Fudan, arXiv 2607.11086, 13 Jul 2026):** 156,842 raw entries from 10 sources (MCP Store, MCP World, MCP Market, the MCP Servers repository, AIBase, PulseMCP, mcp.so, Smithery, npm, PyPI). Of these, 113,927 were valid and 64,611 unique after URL dedup. 28.3% of unique servers are forks, copies or mirrors (46,327 entities after code grouping). Only 57.7% could be deployed for dynamic analysis. 78.6% have no Dockerfile. Only 19.6% of projects with a Dockerfile, README and config run without modification. 63.6% of failures came from external dependencies such as credentials. — [arXiv 2607.11086](https://arxiv.org/html/2607.11086)
- **arXiv 2509.25292 (crawl window reported as Jul 26–Sep 12, 2025):** across 6 markets, 16,950 raw servers yielded 8,060 valid (47.5%). Validity by market: MCP Market 26.4%, mcp.so 43.4%, Smithery 38.3%. 32.3% of projects appear in more than one market; the introduction says 41.9%, which is internally inconsistent. On maintenance: 40.9% were updated within 90 days and 21.9% were inactive for more than a year. — [arXiv 2509.25292](https://arxiv.org/html/2509.25292v1)

### Cited Findings: maintenance and abandonment in the official registry (measured)
- 25 Jul 2026: 60.7% of servers were published exactly once (median of 1 version); 36.2% were updated in the last 30 days; 72.3% are under `io.github.*`. — [Circadian Agent](https://circadian-agent.com/research/mcp-registry)
- 24 Sep 2026: of servers listed for at least 90 days, 54.5% have only one version, and 78.7% published nothing in the prior 90 days. Verified-domain publishers were no better (82.5%; the difference is not significant). 81.2% of servers listed before the 28 Jul 2026 spec revision have not published since. — [Oktopost](https://www.oktopost.com/blog/mcp-registry-legacy-servers/)
- Silent drift (August 2026): 51.09% of servers with multiple versions changed an advertised field. 40.58% made a "silent semantic" change, keeping the same identifier but changing meaning or destination. 4.16% moved their remote endpoint to a different host under the same identity. The registry "does not version tool definitions at all." — [arXiv 2609.14119](https://arxiv.org/pdf/2609.14119)

### Cited Findings: vulnerability and security (measured)
- In the official registry (14,353 servers scanned, August 2026), 15.21% had at least one finding and 11.14% at least one high-severity finding. Corrected for scanner precision, high-severity prevalence is about 7.6%. The top issue was unauthenticated network exposure (9.57% observed, 6.83% corrected). No tool poisoning was found. — [arXiv 2609.14119](https://arxiv.org/pdf/2609.14119)
- Scanner reliability (MCPZoo, 37,288 servers): 96.89% were flagged by at least one of 8 scanners, but no server was flagged by all 8. Mean manual precision was 45.53% (range 10.4%–96.9%). Recall on 10 known CVEs was 24.17%, and three scanners caught none. Mean pairwise agreement (Jaccard) was 15.66%. MCPScan had 45.53% precision and 74.29% recall. — [arXiv 2607.11086](https://arxiv.org/html/2607.11086)
- MCP-related CVEs in the NVD: 58 in 2025 and 324 in 2026 to 21 Oct, for 382 total (79 Critical, 161 High). — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- Astrix (2025, cited by NimbleBrain): 88% of servers require credentials, 53% use long-lived static secrets, and 8.5% use OAuth. — [NimbleBrain](https://nimblebrain.ai/blog/state-of-mcp-security-2026/)
- Skills, academic study: 98,380 skills (skills.rest plus skillsmp, January 2026). 4.4% were flagged by static analysis, and 157 (0.16%) were confirmed malicious after sandboxing and dual manual review (κ = 0.89). — [arXiv 2602.06547](https://arxiv.org/html/2602.06547v1/)
- Skills, Snyk ToxicSkills (February 2026): of 3,984 skills from ClawHub and skills.sh, 13.4% had critical issues, 36.8% had any flaw, and 76 were confirmed malicious. — [TerminalBlog](https://terminalblog.com/blog/agent-skills-670k-security-reckoning/)
- ClawHavoc campaign (January 2026): 1,184 malicious skills across 12 accounts. Five of the top seven most-downloaded ClawHub skills were malware at peak. — [TerminalBlog](https://terminalblog.com/blog/agent-skills-670k-security-reckoning/)
- skills.sh: Trail of Bits bypassed Vercel's malicious-skill detector. — [rywalker](https://rywalker.com/research/skills-sh)

### Cited Findings: duplication and install-count reliability
- 28.3% of unique MCP servers are code-level forks or copies (MCPZoo). Cross-market duplication is 32.3% (or 41.9%) (arXiv 2509.25292). Counting registry version records instead of servers overstates the total by 3.2x, and 134 packages are claimed by multiple registry entries (Circadian). — sources above.
- skills.sh install counts come from CLI telemetry with no review. A review says they "can be gamed" and do not correlate with quality. The site's own "All Time" total (1,526,960) is smaller than its top skill's 4.1M count. — [rywalker](https://rywalker.com/research/skills-sh); [skills.sh](https://skills.sh/)
- The Circadian author withdrew all npm download figures from an earlier version of the post, an example of how fragile install counts are. — [Circadian Agent](https://circadian-agent.com/research/mcp-registry)

### Inferences
- Growth: the official registry roughly doubled every 6–7 weeks from May to October 2026 (9.6K on 24 May to 25.8K on 31 Aug to 47.9K on 21 Oct). Glama grew about 3.5x from June to October 2026 (31.6K to 112K), likely by crawling GitHub broadly.
- Of about 48K registry names, a rough effective-supply estimate is: at most half reachable without credentials, about one fifth actively maintained in any 90-day window, and about 7–11% carrying a high-severity static finding. This combines figures from different studies, so treat it as directional only.
- Directory totals mostly measure crawl breadth, not usable supply. Because scanners disagree (15.66% overlap), a single "security score" is unreliable unless it combines several signals.

### Gaps
- Directory traffic (visits, MAU) for any MCP directory was not found.
- No longitudinal reachability series exists. Only single snapshots (October 2026 remote, August 2026 stdio) are available.

## Q3. Demand: developers browsing versus agents querying programmatically

### Takeaway
There is strong evidence of developer and builder demand (SDK downloads, surveys). Runtime agent discovery is built (AWS's MCP endpoint, Glama's API, Smithery's CLI and API, the MCPfinder meta-server, the official registry API), but **no registry publishes call volumes, and no measured evidence was found of production agents querying registries at runtime**. The official registry is explicitly designed for aggregators that scrape hourly, not for clients. The .well-known Server Cards discovery path is still only a roadmap item.

### Cited Findings
- Official registry intent: aggregators should "scrape data on a regular but infrequent basis (e.g., once per hour)". Subregistries then serve MCP host applications. — [MCP docs](https://modelcontextprotocol.io/registry/registry-aggregators)
- Server Cards (.well-known) were named a priority in the 22 Aug 2026 roadmap, but no schema or ship date has been published. MCPfinder, an MCP server agents can call mid-task to search and install servers, aggregates the official registry, Glama and Smithery, with about 27K+ servers. — [Innvesti, 24 Aug 2026](https://innvesti.com/reports/mcp-server-cards-roadmap-discovery-tools-2026/)
- AWS Agent Registry is reachable through an MCP server by clients such as Kiro and Claude Code, and its search API is priced per call. But InfoQ frames it as discovery by developers and tools, and no runtime lookup volumes are published. — [InfoQ](https://www.infoq.com/news/2026/04/aws-agent-registry-preview/); [Tech Insider](https://tech-insider.org/au/aws-agent-registry-general-availability-2026/)
- Glama exposes `GET /v1/servers` (the MCP Directory API). PulseMCP and mcp.so have only partial or community programmatic access, and MCP Market has no API. — [Glama](https://glama.ai/mcp/servers); [Innvesti](https://www.innvesti.com/reports/best-mcp-server-directories-2026/)
- skills.sh's top skill is `find-skills` (4.1M installs), a skill that lets an agent search for and install other skills. This is indirect evidence of agent-mediated discovery, but the count is CLI telemetry, not query volume. — [skills.sh](https://skills.sh/)
- Smithery shows per-server "uses" and "calls", but does not define them or give totals. — [smithery.ai](https://smithery.ai/)
- SDK downloads, 30 days to 12–13 Oct 2026 (measured; includes CI): `@modelcontextprotocol/sdk` 273.3M (8.7x year over year); TS v2 server 37.3M and client 27.5M; `mcp-remote` 3.82M; Inspector 1.64M; PyPI `mcp` 235.2M; `fastmcp` 53.7M. — [LocalCan](https://www.localcan.com/blog/state-of-mcp-server-development)
- TS SDK npm downloads per month: 102,851 (Dec 2024), 38.5M (Dec 2025), 231.9M (Sep 2026). — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- Enterprise survey (Stacklok, January 2026, fielded December 2025, 300 leaders, run by a vendor): 41% run MCP in production (12% broadly); among large software companies, 45%. 64% cite security as the top obstacle, and 69% are building an in-house MCP platform. — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- Ecosystem: the Agentic AI Foundation grew from 49 members (9 Dec 2025) to 286 (21 Oct 2026). — [Digital Applied](https://www.digitalapplied.com/blog/mcp-adoption-statistics-2026-model-context-protocol)
- Enterprise registry demand comes from governance against "agent sprawl". A Southwest Airlines quote: teams want to "find and reuse existing agents rather than rebuild". — [InfoQ](https://www.infoq.com/news/2026/04/aws-agent-registry-preview/)
- Market sizing (analyst projections, low reliability): MCP market of $1.28B (2025), projected to $28.46B by 2035 (DataM). — [SEOSiri](https://www.seosiri.com/2026/09/mcp-monetization-gap-glama-smithery-developer-losses.html)

### Inferences
- Demand today looks like developers and admins choosing tools at install time: IDE one-click install, connector stores, and enterprise approval workflows. Registries act as supply-chain catalogs rather than runtime routing layers.
- Most directories run on a supply-side growth model. Publishers list to gain distribution, and bulk publishers inflate counts. Paid demand is concentrated in hosting, gateways and enterprise governance.
- For a reputation product, the stronger near-term buyers are enterprise governance owners (AWS, Google and Microsoft registries already ask for approval workflows), and the weaker buyers are autonomous agents.

### Gaps
- **No public figures were found for registry API calls, MAU, or agent-originated queries, for any registry (official, Glama, Smithery, AWS, Google, Microsoft).** Programmatic agent querying is technically possible, but its scale is undocumented.
- No Google Trends or search-volume data for "MCP server" was retrieved.
- No independent developer survey (for example, Stack Overflow or JetBrains 2026) with MCP-discovery questions was retrieved.
- Registry revenue is undisclosed everywhere. The only payout figures (Apify, MCP Marketplace, x402) are secondary and unverified.
