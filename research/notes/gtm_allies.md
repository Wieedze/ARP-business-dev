# ARP: who to lean on for first users (as of 2026-10-29)

Scope: grants, ERC-8004 people and channels, agent builder communities, events Nov 2026 to Jun 2027, and precedents. Every item carries a URL and a status. "Confirmed" means a primary or near-primary page states it; "unconfirmed" means only third-party listings or no date found.

## 0. Context numbers worth quoting in any pitch

1. ERC-8004 reputation is empty and spammed. arXiv 2606.26028 (submitted 2026-06-24, data to 2026-05-13): only 3% (Ethereum), 4% (BSC), 15% (Base) of registrations have a live endpoint; 73.5% / 59.2% / 90.6% of reviewers show coordinated Sybil behaviour; after removing Sybil feedback, 15.8% / 77.9% / 86.8% of rated agents have no valid feedback left. The authors say the Reputation Registry "cannot function as a trust signal". https://arxiv.org/abs/2606.26028
2. LLM4Agents audit (2026-08-17): 50,082 agents on Ethereum, 63,823 on Base; 3,215 feedback records on Ethereum covering about 3.3% of agents; zero validation requests on Ethereum. https://llm4agents.com/blog/erc-8004-registries-onchain-audit
3. Coinbase CDP Bazaar search already returns a `quality` field with 30-day call count, unique payers and last call time, and ranks on it. That is a ready-made usage signal ARP can read. https://docs.cdp.coinbase.com/x402/bazaar
4. HOL Registry Broker already exposes `availabilityStatus`, `availabilityScore`, latency and a `minTrust` filter, and indexes ERC-8004 (Ethereum, Base, Polygon, BSC, Monad), Virtuals ACP and x402 Bazaar. https://hol.org/docs/registry-broker/search/

Takeaway: ARP's "usage = reputation, stake-backed, no composite score" pitch lands best as the fix for the documented Sybil problem, not as yet another score. The reputation-scoring space is crowded (RNWY, 8k4, Verity, AgentStamp, Helixa, Assay, Agent Arena, QuickNode's composite score; see https://github.com/sudeepb02/awesome-erc8004).

## 1. Grants and funding

### Intuition ecosystem (best fit, highest odds)
1. Intuition Box grants. These are flexible grants, either KPI-based or one-time, with fast decisions. You apply by posting in the Atlas Discourse "Grant Applications" category. https://intuition.box/ and https://atlas.discourse.group/c/ecosystem-development/grant-applications/36
2. Cohort 1 was announced 2026-02-04: 100k USDT shared by 9 teams, including Sofia, AgentID and IntuitionMCP. The post says "more will follow". No cohort 2 date was found, so treat it as rolling or unconfirmed. https://intuition.box/blog/grant-recipients-cohort-1
3. The forum is active right now. Applications posted around 2026-10-29 include "AgentId: Decentralized Trust Registry for Autonomous Systems" and "AgentWitness Read-Only Trust Explorer" (posted 2026-10-06), both direct overlaps with ARP. https://atlas.discourse.group/c/ecosystem-development/31
4. Reference ask: the Tribe application (2025-12-05) requested $8k in three milestones and used a template of overview, build, team, milestones, ecosystem alignment and vision. https://atlas.discourse.group/t/tribe-grant-application/1190
5. Action: post an ARP application with KPI milestones (number of agents with hooks installed, `uses X` positions created, tools covered). Cross-reference Sofia's grant, which is already in the same category, to show delivery history. Watch out for overlap with AgentId and AgentWitness. It may be better to propose integrating with them than to compete.
6. Intuition bug bounty (Immunefi), which is not relevant for funding: https://immunefi.com/bug-bounty/intuition/

### Base / Coinbase
1. Base Batches 004 is CLOSED. Applications ran 2026-08-19 to 2026-09-10, the virtual program runs 2026-09-29 to 2026-11-15, and Demo Day is 2026-11-17 in New York. The offer is $100k from the Base Ecosystem Fund for pre-seed, Base-first teams, with "agents" as a focus area. The program runs twice a year, so batch 005 likely opens around Feb to Mar 2027 (unconfirmed). https://www.base.org/batches and https://www.base.org/blog/introducing-base-batches-004
2. Base Ecosystem Fund (with Coinbase Ventures): rolling pre-seed and seed applications. It needs a company. https://docs.base.org/get-started/get-funded
3. Base Builder Grants: 1 to 5 ETH, with no open application. The Base team finds grantees on X and Farcaster, and anyone can submit a nomination. The original post is undated. Shipping publicly on Base and tagging @buildonbase is the path. https://paragraph.xyz/@grants.base.eth/calling-based-builders
4. Caveat: ARP lives on Intuition's L3, which settles to Base. Base-first eligibility is arguable, so frame ARP as "reads Base ERC-8004 agents and Base x402 payments".
5. CDP Builder Grants: the last confirmed round was Summer 2025 (CDP Wallets, AgentKit, Onramp). No 2026 round was found, so this is unconfirmed. https://www.coinbase.com/developer-platform/discover/launches/summer-builder-grants
6. x402 Foundation: launched under the Linux Foundation (Decrypt, 2026-04-02), with members including Coinbase, Cloudflare, Google, Stripe, Visa and Mastercard. No grants program was found, so it is a standards and governance venue, not a funder. https://decrypt.co/363173/coinbase-linux-foundation-launch-x402-foundation and https://www.linuxfoundation.org/press/linux-foundation-is-launching-the-x402-foundation-and-welcoming-the-contribution-of-the-x402-protocol

### Ethereum Foundation
1. ESP now funds through a Wishlist and RFPs, plus Office Hours (blog 2025-11-03). The public applicants page showed no item tied to agents when checked. Office Hours are the realistic door: ask whether "Sybil-resistant ERC-8004 reputation signals" fits a wishlist item. https://esp.ethereum.foundation/applicants and https://blog.ethereum.org/2025/11/03/new-esp-grants
2. EF dAI team: Davide Crapis leads it. In the 2026 roadmap (reported 2025-11-11) he asked builders which directions to prioritise, and ERC-8004 and x402 are named focus areas. The site lists programs, open calls, grants and office hours, but their details were not readable. Check it directly. https://ai.ethereum.foundation/ and https://www.chaincatcher.com/en/article/2218942

### Optimism
1. Season 9 Grants Council (opened 2026-02-11, closed 2026-05-20) targeted DEX TVL and fees. That is not a fit, and it is closed. https://gov.optimism.io/t/season-9-grants-council-applications-now-open/10599
2. The dev tooling Retro Funding of Season 7 is over. No open 2026 dev tooling retro round was confirmed, so this is unconfirmed. https://gov.optimism.io/c/grants/retrofunding/46

### Gitcoin
1. GG24 ended in Nov 2025. Its domains included Dev Tooling ($600k), Interop Standards ($150k, on Celo) and Trust Graph. No GG25 was announced, and an Octant x Gitcoin GG25 matching proposal was withdrawn. The 2026 strategy post (2026-01-12) gives about $20M of runway, but no round dates were found. Unconfirmed. https://gitcoin.co/campaigns/gitcoin-grants-24-gg24 , https://gov.gitcoin.co/t/withdrawn-gitcoin-x-octant-yield-powered-matching-for-gg25/24977 and https://gov.gitcoin.co/t/gitcoin-2026-strategy-tl-dr/25049

### Other chains
1. Arbitrum Trailblazer 2.0: $1M total, up to $10k per submission for agent add-ons and capability integrations through VibeKit (posted 2025-06-04). Current status is unknown and it is probably stale. https://blog.arbitrum.foundation/trailblazer-2-0-1m-in-grants-to-power-agentic-defi-on-arbitrum/
2. Celo: ERC-8004 is live, with AltLayer, thirdweb and Olas as launch partners. Proof of Ship is the monthly rewards program (up to $15k a month in 2025) and runs through Karma GAP. No 2026 round dates were confirmed, but the program looked recurring. ARP would need a Celo deployment or read path. https://blog.celo.org/erc-8004-is-live-on-celo-accelerating-agentic-activity-with-real-world-utility-e30c2a176782 , https://docs.gap.karmahq.xyz/how-to-guides/integrations/celo-proof-of-ship and https://docs.celo.org/build-on-celo/build-with-ai/8004
3. MetaMask Grants DAO: launched in 2022 with $2.4M a year. No 2026 activity was found, so treat it as inactive or unconfirmed. https://metamaskgrants.notion.site/Mission-a1403580a5324f6b8ed07d83a2895ce9
4. Protocol Guild only funds Ethereum L1 core contributors, so it does not apply.

### France (micro-entreprise)
1. Bourse French Tech (Bpifrance): up to €30k, or €45k for strong-tech projects, covering 70% of expenses. The company must be under 1 year old or in creation, and you must self-fund at least 30%. Sources mention entreprises individuelles and natural persons supported by an incubator with a selection committee. Micro-entreprise eligibility is not explicit, so confirm with the Bpifrance Marseille regional office. https://www.legalstart.fr/fiches-pratiques/aides-creation-entreprise/bourse-french-tech/ and https://hayot-expertise.fr/blog/bourse-french-tech-bpifrance-conditions
2. Practical route: join a Marseille incubator or network with a selection committee (for example the French Tech Aix-Marseille network or Réseau Entreprendre), which makes the BFT accessible. Consider whether a micro-entreprise older than 1 year disqualifies you. A new SAS for ARP might be cleaner.
3. i-Nov: projects of €1M to €5M with a 12 to 36 month duration. Not a fit for a solo founder. No 2026 wave date was found. https://www.finalli.com/blog/concours-innovation-i-nov/

## 2. ERC-8004 people, channels, and how to get listed

1. Spec authors: Marco De Rossi (MetaMask, @MarcoMetaMask), Davide Crapis (EF, davide@ethereum.org), Jordan Ellis (Google), Erik Reppel (Coinbase). Created 2025-08-13, status Draft. https://eips.ethereum.org/EIPS/eip-8004
2. Core team (contracts repo): Leonard Tan (MetaMask), Vitto Rivabella (EF), Isha Sangani (EF). Contact team@8004.org. Registries are deployed on 25 mainnets, including Base and Ethereum, and a Validation Registry revision is planned. https://github.com/erc-8004/erc-8004-contracts
3. Community: the Telegram group t.me/ERC8004 is listed as the official builder group. The Ethereum Magicians thread is at https://ethereum-magicians.org/t/erc-8004-trustless-agents/25098 . Community call recordings are at https://www.youtube.com/playlist?list=PLJqWcTqh_zKFWAMzJaPE4L2B3FXwheK9H . 8004.org has a "build" area with community chat, ecosystem project submission, events and grants, but the details render client-side and could not be read. Open https://www.8004.org/ in a browser.
4. Past events: Trustless Agents Day at Devconnect (2025-11-21), 8004 Launch Day (2026-03-17, online, run by the EF dAI team, https://luma.com/658en7zs ).
5. ethresear.ch already discusses whether ERC-8004 forms a trust network, which makes it a good venue for an ARP write-up: https://ethresear.ch/t/does-erc-8004-form-an-agent-to-agent-trust-network/25322
6. 8004scan is run by AltLayer (docs at https://docs.altlayer.io/8004-scan/overview/ , site https://8004scan.io/ , X @8004_scan). An AltLayer team member who posts as YQ tags Crapis, De Rossi and others. Best Practices (Feedback Data Profile v2.0, 2026-01-20, community and non-normative) supports custom `tag1` metric types, so you could propose a `tool-usage` or `uses` profile through the issue tracker. https://best-practices.8004scan.io/docs/02-feedback-standard.html and https://github.com/alt-research/8004scan-issue-tracker
7. QuickNode ERC-8004 Explorer and API (2026-05-18): 15 chains, a published composite score formula, and a REST API paid per request over x402. It could be a data source or a mirror for ARP. https://www.quicknode.com/blog/the-quicknode-erc-8004-stack-a-public-window-into-onchain-agents
8. The Graph Agent0 subgraphs cover ERC-8004 on 5 chains, so ARP can read identity from there instead of indexing it. https://thegraph.com/blog/agent0-subgraphs-live-erc-8004-agent-economy/
9. Awesome lists (PR to get listed): https://github.com/sudeepb02/awesome-erc8004 (there are forks too).
10. Virtuals ACP: all graduated agents are auto-registered on ERC-8004, and reviews are pushed to the Reputation Registry. It is a large source of agents ARP can read. https://x.com/virtuals_io/status/2020095058989793411

## 3. Agent builder communities and data partners

1. Official MCP Registry: an open, unauthenticated read API, designed for aggregators. A subregistry can inject custom `_meta` (for example `"org.arp/usage"`) with ratings and download counts. This is the cleanest legitimate path: become an MCP subregistry that serves registry data enriched with ARP usage signals. https://modelcontextprotocol.io/registry/registry-aggregators and the Registry WG charter at https://modelcontextprotocol.io/community/working-groups/registry
2. HOL Registry Broker: indexes ERC-8004, Virtuals and x402, and exposes availability and trust. There is no documented adapter or partner process. A third party offered a source adapter in issue #20 (2026-10-18), which is unanswered. Offer an "ARP usage signal" adapter the same way, and ask how trust is computed. https://github.com/hashgraph-online/registry-broker-skills/issues/20 , API at https://hol.org/registry/docs , "Feature your agent" at https://hol.org/registry/feature-your-agent
3. x402 Bazaar: the CDP Bazaar exposes call counts and unique payers through REST, the SDK and MCP. https://docs.cdp.coinbase.com/x402/bazaar . The protocol-level spec (no usage fields) is at https://docs.x402.org/extensions/bazaar . The ecosystem page has no stated listing process: https://www.x402.org/ecosystem
4. skills.sh (Vercel): ranks skills by anonymous CLI install counts. Its API returns `installs`, but auth is Vercel OIDC, so it only works from a Vercel-deployed app (600 requests a minute). Partnership goes through the contact page. https://skills.sh/about and https://skills.sh/docs/api
5. Glama: the directory API requires a key, the data is licensed, and attribution plus links back to Glama are required. Its telemetry endpoint takes anonymous tool-usage reports, which is conceptually close to ARP's hooks, so Glama is either a partner or a competitor. https://images.glama.ai/mcp/reference
6. Smithery, PulseMCP and mcp.so: submission-based directories. List the ARP MCP server or skill there for distribution. https://geekflare.com/guides/mcp-server-directories/
7. ElizaOS: plugin registry with a documented publish flow. Ship `@elizaos/plugin-arp` with the discovery and call hooks. https://docs.elizaos.ai/guides/publish-a-plugin
8. Daydreams: the Lucid Agents SDK combines x402 and ERC-8004, so an ARP hook integration there is natural. https://smithery.ai/skills/daydreamsai/lucid-agents-sdk
9. Olas: an ERC-8004 launch partner on Celo. No 2026 builder grant was confirmed.
10. Intuition Discord: weekly community calls, including a Semantic Engineering call on the Intuition Box page. https://intuition.box/

## 4. Events (Nov 2026 to Jun 2027)

1. Devcon 8, Mumbai, 2026-11-03 to 06 (confirmed). https://blog.ethereum.org/2025/12/23/devcon-mumbai . An Agents Hub community hub was proposed (2026-08-25) covering ERC-8004, x402 and agent security, but it is unconfirmed. https://forum.devcon.org/t/devcon-8-india-agentic-hub/8949
2. ETHGlobal Mumbai, 2026-11-05 to 07 (confirmed on https://ethglobal.com/events ). It is a week away, too soon unless you travel.
3. MCP Dev Summit Nairobi, 2026-11-19 to 20 (AAIF). No AAIF events were listed for Dec 2026 to Mar 2027. https://www.linuxfoundation.org/press/agentic-ai-foundation-announces-global-2026-events-program-anchored-by-agntcon-mcpcon-north-america-and-europe
4. Base Batches 004 Demo Day, New York, 2026-11-17 (useful for watching, not entering).
5. ETHDenver 2027: the 10th edition is "still happening". Third-party sites list 2027-02-17 to 21, but ETHDenver had not confirmed dates as of 2026-09-30 and warned about fake tickets. Unconfirmed. https://cryptoevents.substack.com/p/ethdenver-says-2027-is-still-happening
6. EthCC[10], Cannes, 2027-04-12 to 15 (confirmed by the Palais des Festivals; EthCC is in Cannes until 2028). It is about 2h from Marseille and the best ROI. ETHGlobal Cannes 2026 ran just after EthCC 2026 (Apr 3 to 5), so an ETHGlobal Cannes 2027 around Apr 2027 is likely but unconfirmed. https://en.palaisdesfestivals.com/offers/ethereum-community-conference-cannes-en-5198662/
7. ETHPrague 2027, 2027-05-28 to 30, with a hackathon themed on Ethereum and AI, including agents (confirmed on the site). https://ethprague.com/
8. ETHConf 2027 (ETHGlobal), New York, 2027-06-14 to 16. https://ethglobal.com/events
9. VivaTech 2027, Paris, 2027-06-16 to 19. https://dealroom.co/events/vivatech-2027/
10. Signal Week (formerly Paris Blockchain Week), Paris, 2027-07-06 to 07. It is institutional and C-suite heavy, so it is low priority for first users. https://tradefest.io/es/event/signal-week-formerly-paris-blockchain-week
11. ETHDam 2027: no dates found. Unconfirmed. https://ethdam.substack.com/
12. Intuition hackathons: none found for this window. Ask in Discord.
13. Async option: ETHGlobal ran "Open Agents" async (2026-04-24 to 05-06). Its ETHOnline 2026 prizes included Hedera ("extra points for ERC-8004"), The Graph (Agent0 subgraphs, x402) and ENS (agent registry ENSIPs). Expect similar tracks at the next ETHGlobal events. https://ethglobal.com/events/openagents and https://ethglobal.com/events/ethonline2026/prizes

## 5. Precedents and lessons

1. DefiLlama (2020, 0xngmi and co-founders): open-source adapters where protocols list themselves by PR (36k+ commits, 41 open PRs at check time). Methodology is public and reproducible, and the project held a neutral "present the data" stance until fake numbers forced curation. Lesson: let tool and agent builders submit their own adapters or hooks, and publish the method. https://github.com/DefiLlama/DefiLlama-Adapters , https://iq.wiki/wiki/defillama , https://www.dlnews.com/articles/defi/an-interview-with-0xngmi-on-new-defillama-pro-dashboard/
2. shields.io: a badge in every README, now 1.6B+ images a month. Contributors add service integrations through PRs. Lesson: ship an "ARP: used by N agents / live" badge for MCP servers and skills. Each README becomes distribution. https://cdn.jsdelivr.net/gh/badges/shields@master/README.md (skills.sh copied this with install badges: https://skills.sh/docs )
3. Socket.dev (about 2022): a free GitHub app with one-click install and no config, design partners (Brave, Expo), and free public package pages anyone can browse. Lesson: free public pages per tool and agent, plus a near-zero-config hook install. https://changelog.com/podcast/482
4. mcp.so: launched 2024-12-03, eight days after MCP (2024-11-25), and reached 50k+ monthly visits within about 3 months. Lesson: be the first neutral index the moment a standard launches. For ERC-8004 that window has passed for explorers, but not for usage-backed reputation. https://nichesitegrowth.beehiiv.com/p/directories-directories-directories
5. Glama: its founder also maintains the dominant awesome-mcp-servers list, so the list fed the directory. Lesson: own or co-maintain the awesome list. https://images.glama.ai/mcp/reference
6. 8004scan (AltLayer): launched alongside the standard, tagged the spec authors, shipped mobile apps, and wrote the community Best Practices profiles. That made it the de facto convention setter. Lesson: publish a "tool-usage feedback profile" spec and get it into the 8004scan best practices. https://best-practices.8004scan.io/docs/02-feedback-standard.html

## Recommended order (first 90 days)
1. Post the Intuition Box grant application now, with KPI milestones. It is the highest-probability funding.
2. Propose a `uses`/tool-usage feedback data profile on the 8004scan issue tracker and in t.me/ERC8004, citing the arXiv Sybil findings.
3. Ship an MCP subregistry with `_meta` usage signals, plus a README badge.
4. Open an issue on the HOL registry-broker repo offering an ARP signal adapter, modelled on issue #20.
5. Book EF ESP Office Hours and check the dAI team's open calls.
6. Target EthCC[10] Cannes (Apr 2027) and a likely ETHGlobal Cannes 2027 as the demo moment. Consider Base Batches 005 (likely early 2027) if ARP becomes a company.
7. In parallel, ask Bpifrance Marseille whether the micro-entreprise qualifies for the Bourse French Tech, and whether an incubator route works.
