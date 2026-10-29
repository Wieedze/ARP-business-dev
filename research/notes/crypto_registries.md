# Crypto-native agent reputation, registries and discovery: shipped vs announced (as of 2026-10-29)

All URLs were read on 2026-10-29. "SR" means self-reported by the project or a party paid by it. "M" means measured by a third party (on-chain explorer, independent researcher, analytics firm). "M?" means a third-party aggregator whose method is not public.

## 1. ERC-8004 (Trustless Agents): what is running, how much is used, how much is reachable

### Takeaway
ERC-8004 is the only standard here with large, verifiable on-chain registration counts: about 1.57M identities across 29 networks per 8004scan. Every independent liveness study finds that most registrations are not callable agents. Estimates of working endpoints range from about 2% to 15% of identities. The Validation Registry is effectively unused, and the Reputation Registry is dominated by Sybil feedback. The registry is real, but "registered agent" is not a meaningful usage unit.

### Cited Findings
**Deployment (shipped)**
- Mainnet went live on Ethereum on 2026-01-29 and on Base on 2026-02-03. The Identity, Reputation and Validation proxies sit at the same addresses on 25 mainnets (M; the author read contract storage directly) — [LLM4Agents audit, 2026-08-17](https://llm4agents.com/blog/erc-8004-registries-onchain-audit)
- The spec is [EIP-8004](https://eips.ethereum.org/EIPS/eip-8004). Contracts are in [erc-8004/erc-8004-contracts](https://github.com/erc-8004/erc-8004-contracts).
- Explorers: [8004scan](https://www.8004scan.io/) and the [Quicknode ERC-8004 Explorer](https://erc-8004.quicknode.com/), which covers 15 chains. Allium indexes ERC-8004 events ([docs](https://docs.allium.so/historical-data/supported-blockchains/evm/x_layer/agents/erc8004-events)).
- A Solana ERC-8004 implementation (Quantu AI) was announced 2026-03-03 — [MEXC/PANews](https://www.mexc.com/news/840442)

**Registration counts (M, on-chain)**
- 8004scan homepage, read 2026-10-29: 1,569,786 registered agents (+4,309 in 24h), 813,789 feedback submissions, 2,415,043 unique wallets, 29 networks — [8004scan](https://www.8004scan.io/)
- 8004scan figures for 2026-09-18 (quoted secondhand): 519,333 agents and 589,322 feedback across 30 networks. BNB Chain held 62.1% of agents but only 2.0% of feedback. Base held 13.1% of agents and 79.1% of feedback — [Datawallet](https://www.datawallet.com/crypto/erc-8004-explained)
- Note that this is roughly a 3x jump between 2026-09-18 and 2026-10-29. I found no explanation, and batch minting is a likely driver (inference; see the batch data below).
- Direct storage read on 2026-08-17: Ethereum `_lastId` was 50,082 and Base was 63,823 — [LLM4Agents](https://llm4agents.com/blog/erc-8004-registries-onchain-audit)
- Quicknode reported about 39,000 registrations and more than 73,000 feedback events in the first 90 days (SR by an infrastructure vendor, 2026-05-18) — [Quicknode blog](https://www.quicknode.com/ko/blog/the-quicknode-erc-8004-stack-a-public-window-into-onchain-agents)
- On Ethereum, 48.3% of agents were created by batch transactions. Only 629 agents (0.4%) are registered on two or more mainnets (Imperial study, quoted) — [Datawallet](https://www.datawallet.com/crypto/erc-8004-explained)

**Reputation Registry usage (M)**
- Ethereum through block 25,773,811: 3,215 NewFeedback events, 37 responses and 0 revocations. Only 1,668 distinct agents received feedback (about 3.3% of registered agents), from 653 distinct clients — [LLM4Agents](https://llm4agents.com/blog/erc-8004-registries-onchain-audit)
- Among reviewers, 73.5% (Ethereum), 59.2% (BSC) and 90.6% (Base) show coordinated Sybil behavior. After removing Sybil feedback, 15.8% (Ethereum), 77.9% (BSC) and 86.8% (Base) of rated agents have no valid feedback. The authors conclude that the Reputation Registry "cannot currently serve as a trust signal" — [Xiong et al., arXiv 2606.26028, data to 2026-05-13](https://arxiv.org/abs/2606.26028)
- The median cost to fabricate a rating is about $0.055 on Ethereum, $0.0042 on BSC and $0.0027 on Base (Imperial study, quoted) — [Datawallet](https://www.datawallet.com/crypto/erc-8004-explained)
- A case study of the first 10 Base agents counted 245 feedback entries from 29 clients. One client filed 32% of agent #0's entries, and the naive average overstates trust compared with witness-capped scoring. One prominent agent's endpoint had been dead for weeks while its registration file still marked it active — [dev.to, 2026-07-13](https://dev.to/hanjoon_choe_bdd8d1f719c1/we-measured-trust-on-erc-8004-and-the-naive-average-crowns-the-wrong-agent-18gb)

**Validation Registry usage (M)**
- Ethereum: 0 ValidationRequest and 0 ValidationResponse events. Base: 13 requests and 8 responses since 2026-02-03 (as of 2026-08-17) — [LLM4Agents, "ERC-8004's third registry is live and empty"](https://llm4agents.com/blog/erc-8004-registries-onchain-audit)

**Reachability / liveness studies (M, independent)**
- Imperial College-led study: only 3% (Ethereum), 4% (BSC) and 15% (Base) of registrations have a valid registration file with at least one live service endpoint. Data runs to 2026-05-13 — [arXiv 2606.26028](https://arxiv.org/abs/2606.26028). **This is the "~15%" figure the user remembered. It applies to Base only, and the other chains are far lower.**
- Base funnel study (n=1,204 sampled from 63,832 registrations, data to 2026-08-16): 63.1% have a URI, 53.7% resolve, 28.3% match the schema, 17.9% declare services, and **6.8% have an endpoint that responds** (95% CI 5.5–8.4%). It also found **122 of 371 declared services working (32.9%)**, and only 10.2% of owners have at least one working agent. The author calls these figures an upper bound — [maxguryanov/agent-registry-research](https://github.com/maxguryanov/agent-registry-research)
- 12-chain study (392,258 identities, snapshot 2026-08-10): 21.3% declare a routable endpoint. Of the probed endpoints, 47.6% passed an A2A card or MCP initialize/tools/list handshake in two rounds 48h apart. The host-reweighted estimate is 38.6% of endpoint-declaring identities, which implies roughly 8% of all identities (my calculation: 21.3% × 38.6%). A re-run is planned for 2026-11-10 — [yaojin0609/erc-8004-liveness](https://github.com/yaojin0609/erc-8004-liveness)
- 8004scan's July ecosystem report: about 2.24% of agents passed A2A/MCP health checks, and 89.2% declared neither protocol (quoted secondhand) — [Datawallet](https://www.datawallet.com/crypto/erc-8004-explained)
- Mafrur & Khusumanegara describe Ethereum ERC-8004 adoption as "registration-heavy but operationally shallow," with ownership and feedback concentrated in a few wallets — [arXiv 2606.12128](https://arxiv.org/abs/2606.12128)

**Revenue / pricing**
- The ERC-8004 registries charge no protocol fee; registration costs only gas (inferred from the spec and contracts). I found no revenue evidence for the standard itself. 8004scan's business model is unknown.

### Inferences
- If roughly 2–8% of 1.57M identities are callable, about 30k–125k ERC-8004 agents respond, and far fewer do anything useful. Base is the healthiest chain. BNB Chain's volume looks like mass minting: 62% of agents with 2% of feedback.
- The user's "3 of 122" claim was not found as stated. The closest matches are the 3% Ethereum figure in Xiong et al. and "122 of 371 services working" in the maxguryanov study. The user may be combining two sources, so this needs confirmation before citing.
- A gap exists for a measured, Sybil-resistant reputation signal tied to verifiable interactions. Every study found the on-chain Reputation Registry fails at this.

### Gaps
- I could not find a 8004scan methodology page that explains how "registered agents" are counted (deduplicated or not) or what explains the jump from 2026-09 to 2026-10.
- The full PDF numbers in arXiv 2606.12128 were not extracted.
- thespawn.io/analytics failed to load.

## 2. Intuition (knowledge graph, TRUST token)

### Takeaway
Intuition's mainnet (its own L3) and the TRUST token have been live since 2025-10-29. The site self-reports about 20.2M transactions and about 496k accounts. The token is down about 92% from its all-time high. I found no shipped agent-reputation app on Intuition with usage. Agent-registry projects there are still grant proposals.

### Cited Findings
- Mainnet and TRUST launched 2025-10-29. Total raised is $8.5M, including CoinList and Legion community sales. Backers include Superscrypt, Shima, F-Prime (Fidelity), ConsenSys, Polygon, and angels Joseph Lubin and Jonathan Christodoro (SR, press release) — [Chainwire](https://chainwire.org/2025/10/29/intuition-launches-mainnet-with-8-5m-to-build-the-trust-layer-for-ai-and-the-internet/)
- Testnet: 17.5M transactions from more than 900k accounts over about 8 weeks (SR; testnets are typically airdrop-farmed) — [Chainwire](https://chainwire.org/2025/10/29/intuition-launches-mainnet-with-8-5m-to-build-the-trust-layer-for-ai-and-the-internet/)
- Homepage counters read 2026-10-29: 20,231,538+ transactions and 496,237+ accounts. The consumer app is still an "invite-only beta" (SR) — [intuition.systems](https://www.intuition.systems/)
- TRUST trades at $0.05176 with a $9.29M market cap. The ATH was $0.6283 on 2025-11-05, so the token is down about 92% (M, CMC) — [CoinMarketCap](https://coinmarketcap.com/currencies/intuition/)
- "AgentID," a decentralized agent registry and reputation layer on Intuition (agents as Atoms, capabilities as Triples, TRUST-bonded identity, MCP trust-score server), is a grant application from 2025-12-05. It is self-described as "Idea / Prototype," requests $28k, and has no usage — [Atlas forum](https://atlas.discourse.group/t/grant-application-agentid-the-decentralized-trust-registry-for-autonomous-systems/1195)
- "Inturank" is also at the grant-application stage — [Atlas forum](https://atlas.discourse.group/t/inturank-ieii-grant-application/1167)
- The Tiger Research report on Intuition was partly funded by Intuition — [Tiger Research](https://reports.tiger-research.com/p/intuition-eng)

### Inferences
- Intuition's agent-reputation niche is open: there is infrastructure but no product with usage. Sofia, which the user co-founded, would sit here (context, not a finding).
- Transaction and account counts are SR and likely include points and airdrop farming. I found no Dune or DefiLlama usage breakdown.

### Gaps
- No atom or triple counts, TVL or staked figures, or protocol fee revenue were found from any third party. The DefiLlama chain page failed to load.

## 3. Olas / Autonolas

### Takeaway
Olas is shipped and running. It is one of the few projects with a live on-chain dashboard showing modest real activity: 454 daily active agents (7-day average) and 21M lifetime transactions, both self-reported on-chain counters. Measured protocol revenue is tiny.

### Cited Findings
- Homepage, 2026-10-29 14:00 UTC: 3,783 "agents deployed" (defined as unique operators), 21,023,254 lifetime transactions, 14,897,539 of them agent-to-agent, and **454 daily active agents** (unique multisigs, 7-day average). The Mech Marketplace protocol fee went live on 2026-06-15 (SR, on-chain derived) — [olas.network](https://olas.network/)
- Raised $13.8M led by 1kx on 2025-02-04 to launch the Pearl agent app store. At the time it claimed more than 3.5M transactions across 9 chains (SR) — [The Block](https://www.theblock.co/post/338713/olas-raises-13-8-million-to-launch-pearl-an-app-store-for-autonomous-ai-agents-in-crypto)
- DefiLlama, Pearl V1: TVL $103.5k. Fees were $12.38 over 30 days and $78.6k cumulative. Revenue is $58.2k cumulative, and annualized revenue is about $45.9k (M) — [DefiLlama](https://defillama.com/protocol/pearl-v1)

### Inferences
- Olas has the most honest "active agent" metric found: 454 per day, versus 1.57M "registered" on ERC-8004. That gap shows the scale of real versus registered agents.
- Usage is largely OLAS-staking-incentive driven. Revenue in the tens of thousands of dollars per year means it is token-subsidised.

### Gaps
- Registry component and service counts on registry.olas.network were not retrieved.

## 4. Virtuals Protocol (ACP, agent registry)

### Takeaway
Virtuals ACP is shipped on Base and other chains with real fee flows. Most revenue comes from token-launch trading, not agent commerce. ACP revenue is small (about $452k cumulative) and the job metrics are self-reported. Independent writers question them.

### Cited Findings
- Fundstrat Q2 update (2026-06-24): ACP peaked at about 414k jobs in January and about 1,321 daily users in March (ATH). More than 2,000 agents were onboarded after ACP v2.0 (April 2026). Cumulative gross ACP fees are about $4.5M and ACP protocol revenue about $452k. The launchpad 1% trading fee is the largest revenue segment. No data provider is named, so treat these as SR — [Fundstrat PDF](https://fundstrat.com/wp-content/uploads/2026/06/20260624-Digital-Asset-Strategy-Virtuals-Protocol-–-Growing-Agentic-GDP-Q2-Update.pdf)
- Virtuals reported $470M aGDP and 1.77M completed jobs in February 2026 (SR). Forkast calls aGDP a "black box" needing independent verification and notes that a $1M/month reward program can make simulated commerce more profitable than real commerce. Trailing-12-month revenue is about $59M (unsourced) — [Forkast, 2026-07-22](https://forkast.news/the-machine-as-buyer-virtuals-acp-and-the-evaluator-problem/)
- An analysis from 2026-08-17, citing Virtuals' Dune dashboard, DefiLlama and CoinMetrics: about 2.5M completed ACP jobs, about $4.5M in agent earnings (under $2 per job), more than 45k agent launches, and $15.24B cumulative agent-token trading volume, which is more than $3,300 of token turnover per $1 of service revenue. Weekly fees fell from $918,889 in mid-July to $74,652 on 2026-08-10 (mixed M/SR) — [analysis mirror](https://san-1510.aid.brainsum.com/news/analysis/virtuals-got-robinhoods-traffic-and-kept-almost-none-it). **Caveat: the URL is a mirror domain, and I could not confirm the original publisher.**
- The HOL Registry Broker counted 6,983 Virtuals agents in March 2026 (M?) — [HOL State of AI Agents, March 2026](https://hol.org/blog/state-of-ai-agents-march-2026)

### Inferences
- ACP's evaluator role is a reputation mechanism with no published independent measurement of evaluator honesty.

### Gaps
- I did not retrieve the Blockworks or Token Terminal income statement (the redirect required login).

## 5. Fetch.ai Agentverse / Almanac

### Takeaway
Agentverse and the Almanac contract are shipped and are the largest single registry by count in one aggregator (36k agents in March 2026). There is no independent liveness measurement and no headline usage numbers.

### Cited Findings
- 36,338 AgentVerse agents, 34.8% of 104k agents aggregated across 15 registries (M?, HOL Registry Broker, published 2026-03-04) — [HOL](https://hol.org/blog/state-of-ai-agents-march-2026)
- The Almanac is an on-chain contract for agent registration and discovery — [Fetch.ai docs](https://fetch.ai/docs/concepts/fetch-network/almanac)
- The Agentverse homepage shows "Exchanged messages" and "Hrs of compute time" labels, but no values rendered. It claims use by Bosch and T-Systems without figures (SR) — [agentverse.ai](https://agentverse.ai/)

### Gaps
- No usage evidence found for Agentverse beyond registration counts. No revenue data.

## 6. Coinbase x402 and the x402 Bazaar

### Takeaway
x402 is shipped and has real but small adjusted volume. Visa and Artemis put it at about $19M across about 134M transactions, with roughly 4k wallets making 90% of spending. A large share of raw activity was found to be gamed. The Bazaar is a live public discovery API with a usage-based quality ranking (call volume, unique payers), which is the most production-grade "reputation-like" signal found. It is not a trust score.

### Cited Findings
- Visa and Artemis adjusted figures: about $19M volume and about 134M transactions. About 4,000 wallets account for about 90% of adjusted spend, mostly on Base (M, method not public; 2026-07-16) — [The Defiant](https://thedefiant.io/news/infrastructure/visa-s-sheffield-pegs-adjusted-x402-volume-at-19m)
- Artemis classified an average of 63.94% of x402 transactions as "gamed" between 2025-11-09 and 2026-02-07 (peak 90.21%). On Polygon, 30 new wallets generated 91.8% of 2.1M transactions, 99.99% of them sending 0.01 USDC to one address (M; Artemis heuristics not public) — [Four Pillars](https://research.4pillars.io/en/research/x402-on-polygon-real-or-gamed)
- More than 95% of x402 activity was "protocol signaling rather than buyer-seller exchange" (unsourced claim) — [Forkast](https://forkast.news/the-machine-as-buyer-virtuals-acp-and-the-evaluator-problem/)
- The Bazaar is "a catalog of payment-gated services discovered by the CDP Facilitator," with public discovery, no API key, SDK, REST and MCP access, and up to 20 results per search. Ranking blends relevance and quality, where quality is 30-day call count, unique payers, last-called time and metadata completeness. There is no separate trust score and no published total count — [CDP docs](https://docs.cdp.coinbase.com/x402/bazaar)
- 7,606 x402 Bazaar entries in March 2026 (M?) — [HOL](https://hol.org/blog/state-of-ai-agents-march-2026)
- A probe of the agentic.market directory (not the Bazaar) covered 20,338 endpoints from 516 services. 87.3% returned HTTP 402, one provider accounted for 52% of endpoints, and 161 endpoints were priced at $1,000 USDC or more per call ("honeypots") (M, independent, April 2026) — [dev.to](https://dev.to/afx/we-probed-20338-x402-endpoints-161-are-agent-honeypots-4c3n)
- Binance runs a parallel "B402 Bazaar" — [Binance docs](https://developers.binance.com/en/docs/products/onchainpay-x402/b402-bazaar)

### Inferences
- Bazaar's quality field (paid calls, unique payers) is the closest thing to a reputation signal based on real usage. It is still gameable by self-paying wallets, as the Polygon data shows. A measured reputation layer could complement it.

### Gaps
- No Coinbase-published facilitator revenue. Coinbase's facilitator fee model and current pricing were not confirmed. x402scan did not render.

## 7. Recall Network

### Takeaway
Recall's competitions and Skill Markets are shipped with the RECALL token. Usage figures are mostly self-reported or VC-reported, and funding figures were not confirmed from a primary source.

### Cited Findings
- USV, an investor (2025-10-15): in the first week of the DeFi arena, more than 100 agents made more than 100k trades worth about $1.2M in volume. "Thousands of agents" have participated overall (SR by investor) — [USV](https://www.usv.com/writing/recall-skill-markets-for-ai)
- Four Pillars (2025-10-30): more than 10 Skill Markets, more than 1.4M users and more than 10M curation signals. No revenue figures; fees are described only qualitatively (SR-derived) — [Four Pillars](https://research.4pillars.io/en/research/the-market-decides-which-ai-wins-in-the-recall-skill-market)

### Gaps
- Funding total not verified (coinlaunch pages failed). No independent usage or revenue data.

## 8. Kite AI (Agent Passport)

### Takeaway
Kite's mainnet went live on 2026-04-28 (an Avalanche L1) with Agent Passport. Its usage numbers are testnet-era and self-reported. I found no mainnet usage evidence or passport counts.

### Cited Findings
- $18M Series A led by PayPal Ventures and General Catalyst (2025-09-02), for $33M total — [PayPal newsroom](https://newsroom.paypal-corp.com/2025-09-02-Kite-Raises-18M-in-Series-A-Funding-To-Enforce-Trust-in-the-Agentic-Web)
- Mainnet date 2026-04-28. Testnet saw more than 1.9B "agent interactions," a 30M daily call peak, more than 300M transactions and more than 51M addresses (SR by the Avalanche Foundation) — [Avalanche blog](https://www.avalanche.com/about/blog/1-9-billion-interactions-later-it-goes-live)
- Kite Chain and Agent Passport launch press release (2026-04-30) — [The Block PR](https://www.theblock.co/press-releases/399534/kite-launches-kite-chain-and-kite-agent-passport-enabling-autonomous-ai-agent-payments)
- AP2 Community Partner since 2026-02-25. No passport counts — [BlockEden](https://blockeden.xyz/blog/2026/04/22/kite-ai-l1-google-agent-payments-protocol-crypto-big-tech/)

### Gaps
- No mainnet usage evidence found.

## 9. Skyfire, Nevermined (agent payments with identity)

### Cited Findings
- Skyfire raised $8.5M seed (2024-08-21) plus Coinbase Ventures and a16z CSX, for $9.5M total (2024-10-24). The article gives no usage metrics — [The Block](https://www.theblock.co/post/322742/coinbase-ventures-and-a16zs-csx-bring-skyfires-total-funding-raised-to-9-5-million)
- Nevermined raised more than $4M led by Generative Ventures (2025-01-22), with Olas/Valory founders as angels. No usage figures — [Pulse 2.0](https://pulse2.com/nevermined-ai-payment-infrastructure-company-raises-over-4-million)

### Gaps
- No usage evidence found for either (KYAPay volumes, Nevermined payment volume).

## 10. Warden, Theoriq, Giza, Talus, Sentient, Masa, Story

### Cited Findings
- **Warden**: $4M strategic round at a $200M valuation (2026-01-22). Claims about 20M users, 250k DAU, more than 60M agentic tasks and about $2.5M annualized revenue. These are entirely SR in a sponsored Chainwire release — [Decrypt/Chainwire](https://decrypt.co/355413/warden-announces-4-million-strategic-funding-round-led-by-builders-and-infrastructure-partners)
- **Theoriq**: AlphaSwarm and AlphaVaults on Base, a THQ token (TGE around December 2025), and a Kaito launchpad sale at about $75M valuation. No TVL or usage figures found — [OneKey blog](https://onekey.so/blog/ecosystem/thq-deep-dive-report-token-future-and-price-outlook)
- **Giza (ARMA)**: TVL $31.54M (Base $18.16M, Arbitrum $11.49M). Fees and revenue were $2,552 over 30 days and $90,867 cumulative (M) — [DefiLlama](https://preview.dl.llama.fi/protocol/giza)
- **Talus**: Protocol v1.0 went to Sui mainnet on 2026-04-15 as a "closed mainnet phase" with permissioned access and no usage numbers — [Talus blog](https://blog.talus.network/talus-protocol-v1-0-release-verifiable-ai-agents-live-on-sui-mainnet/). It raised $6M strategic led by Polychain at a $150M valuation, for $9M total (2024-11-26) — [The Block](https://www.theblock.co/post/328313/talus-network-polychain-funding-round-150-million-usd-valuation-tiktok-ai-dating). A further investment of about $10M from Sui and Walrus followed (2025-09-29) — [Decrypt](https://decrypt.co/341976/talus-network-receives-investment-from-sui-and-walrus-to-accelerate-prediction-ai)
- **Sentient**: $85M seed led by Founders Fund, Pantera and Framework (2024-07) — [The Defiant](https://thedefiant.io/news/defi/sentient-labs-raises-85-million-seed-funding-led-founders-fund-pantera-capital). Not an agent-reputation product. No registry usage evidence found.
- **Masa**: AI Agent Arena on Bittensor with Yuma — [The Defiant](https://thedefiant.io/masa-launches-ai-agent-arena-on-bittensor). No current usage evidence found.
- **Story**: "Agent TCP/IP" announced 2024-12-19 — [Decrypt](https://decrypt.co/297903/story-launches-agent-tcp-ip-the-foundational-layer-for-the-ai-agent-economy). No agent-registry usage evidence found.

### Inferences
- Warden's numbers are the largest claimed and the least verified. They should not be compared with on-chain-measured figures.

### Gaps
- Theoriq and Warden have no DefiLlama data retrieved. Masa and Story have no 2026 agent-usage data.

## 11. NANDA (MIT), cheqd, Human Passport, EigenLayer, aggregators

### Cited Findings
- **NANDA Index**: hosted at 15 universities and partners, with AgentFacts (signed JSON-LD). The Join39 directory lists more than 1,000 agents. The "Registry Quilt" federation is still a design concept (2025-10-24) — [The New Stack](https://thenewstack.io/how-mits-project-nanda-aims-to-decentralize-ai-agents/). HOL counted 2,702 NANDA agents in March 2026 (M?) — [HOL](https://hol.org/blog/state-of-ai-agents-march-2026). It is academic, with no revenue.
- **cheqd**: ships an MCP server (`/who_is`), trust registries via cheqd Studio and SDKs, and hosted TRAIN accreditation APIs. It claims "deployed at scale" with no figures and no pricing on that page — [cheqd docs](https://docs.cheqd.io/product/ai-agents). No usage evidence found.
- **Human Passport (formerly Gitcoin Passport), as an analogue**: more than 2M accounts, more than 43M credentials, about 436k on-chain passports, and more than $500M "protected from Sybils." Company-wide revenue was about 1.3M (unit unclear), with no Passport-specific revenue (SR, 2026-01-22) — [human.tech](https://human.tech/blog/holonym-foundation-2025-wrapped). Holonym acquired it in 2025 — [Cointelegraph](https://cointelegraph.com/news/zk-identity-holonym-acquire-gitcoin-passport-10-million)
- **EigenLayer "Verifiable Agents"**: the 2025-02-04 post covers open-sourced zkTLS (Opacity) and EigenDA proofs in elizaOS. It is mostly a roadmap, with no usage numbers for verifiable agents — [Eigen Labs blog](https://www.eigenlabs.org/blog/introducing-verifiable-agents-on-eigenlayer/)
- **HOL Registry Broker (Hashgraph Online)**: aggregated about 104.5k agents across 15 registries (AgentVerse 36,338; ERC-8004 Ethereum 18,344; PulseMCP 16,510; Moltbook 14,436; x402 Bazaar 7,606; Virtuals 6,983; NANDA 2,702; OpenRouter 535; and others). It computes trust scores that include "availability," but publishes no reachability rate. The per-registry figures sum to 104,351 against a 104,504 headline (2026-03-04) — [HOL](https://hol.org/blog/state-of-ai-agents-march-2026). It is a cross-registry aggregator and reputation scorer, and arguably the closest direct competitor among new entrants (inference).
- **Third-party liveness tooling**: an "erc8004-agent-liveness" MCP server returns verdicts such as REGISTERED_UNREACHABLE and REGISTRATION_FETCH_FAILED. It is a tool, not a study — [Glama](https://glama.ai/mcp/servers/nexus-mcp-infra/erc8004-agent-liveness)

### Inferences
- Several actors (HOL, 8004scan, agentutility, liveness MCPs) have started measuring liveness and availability, so "reachability-aware reputation" is becoming crowded at the tooling level. No one has shown paying customers.

### Gaps
- No revenue evidence found for any registry, aggregator or reputation layer. Wherever monetisation exists, it sits in payments (x402 fees, Virtuals trading fees) or token incentives, not in reputation queries.
