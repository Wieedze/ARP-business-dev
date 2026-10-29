# Reputation systems: what was tried, what failed, decayed or got gamed (lessons for a staked, permissionless reputation layer for AI agents and tools)

All sources were read on 2026-10-29. Each finding is tagged [INCIDENT/DATA] for a documented event or measured data, or [COMMENTARY] for analysis or opinion. Coverage is uneven: some items in the brief had no reliable sources. Those are listed under Gaps rather than filled in.

## Q1. Token-curated registries: did any sustain? Testing "TCRs have been tried repeatedly since 2017 and none sustained"

### Takeaway
The belief is mostly true for **general-purpose, subjective, token-launched TCRs** (adChain, Civil, Messari's planned registry, FOAM's map registry, TCRParty, Everest). It is **false as stated**. Kleros Curate / Scout has run continuously since about 2019 and reports 600k+ tagged addresses, 16k+ submissions and 508 court disputes. Proof of Humanity reached about 17k registrants. Both survived by narrowing to objective, cheaply verifiable predicates, delegating disputes to a separate court, and paying ongoing incentives (about 366k PNK a month in 2026). That last point leaves open whether the activity is organic. A fair rewrite is: "Standalone TCRs with their own token and subjective listing criteria have not sustained. The one survivor uses objective criteria, an external court and continuous subsidy."

### Cited Findings
**Theory and critiques**
- [COMMENTARY] Tabarrok (Nov 2, 2018): "TCRs are likely to work when high quality information is available at low cost." When the truth is costly to find, the mechanism becomes open to bias, manipulation and collusion, and "if good, cheap information exists, many designs should work... If it doesn't, perhaps none will." — [Marginal Revolution, Tabarrok 2018](https://marginalrevolution.com/marginalrevolution/2018/11/can-token-curated-registries-actually-work.html)
- [COMMENTARY] FlatOutCrypto (HackerNoon, Feb 2019) lists the failure modes. Voters are paid for matching the majority rather than for being right. Turnout is low, so small groups swing outcomes. Concentrated initial token holdings create plutocracy: about 40% of adToken was reserved for MetaX/ConsenSys. Listing applicants have more motive to game the list than neutral voters have to curate it. — [HackerNoon](https://medium.com/hackernoon/token-curated-registries-probably-arent-going-to-change-the-world-b97feb34e99)
- [COMMENTARY] Entriken (Jun 9, 2018) describes theoretical attacks: a 51% attack; a "34% attack", in which a third of the vote plus herd-following voters steers the result; a "one-vote attack", in which costly research plus a liquid vote market collapses decisions onto one published vote; and a "Borg attack" (vote pooling). These are hypothetical, with no documented incidents. — [blog.phor.net](https://blog.phor.net/token-curated-registries-uses-exploits)

**Dead or failed TCRs**
- [INCIDENT/DATA] Civil, a journalism TCR: the token sale aimed for $8M and raised about $1.4M (about 18%), and about three quarters of that came from ConsenSys, its own seed investor. All roughly 3,000 buyers were refunded (Oct 16, 2018). ConsenSys then committed $3.5M to buy CVL and promised not to vote those tokens, which concedes the concentration problem. — [Nieman Lab, Oct 16 2018](https://www.niemanlab.org/2018/10/civils-token-sale-has-failed-now-what-refunds-for-one-thing/)
- [INCIDENT/DATA] Civil employees reported unpaid wages (Nov 2018). — [CoinDesk](https://coindesk.com/markets/2018/11/26/employees-say-startup-civil-hyped-crypto-returns-but-failed-to-pay/)
- [INCIDENT/DATA] Messari (2018) planned a TCR "whitelist" of compliant crypto projects, with token-holding hedge funds, exchanges and advisers as voters. — [CoinDesk 2018](https://www.coindesk.com/token-regulate-tokens-messari-raise-ico-2018/). I found no source documenting that it launched. Messari became a centralized data company (see Gaps).
- [INCIDENT/DATA] adChain: early votes challenged Facebook and the New York Times, and the NYT challenge failed. A 2019 reader comment called voting "a waste of time and tokens." That is anecdotal. — [HackerNoon](https://medium.com/hackernoon/token-curated-registries-probably-arent-going-to-change-the-world-b97feb34e99)
- [INCIDENT/DATA] FOAM's FOA token was delisted from Bitfinex with trading ending 23 Nov 2020 (no reason given). — [Bitfinex support](https://support.bitfinex.com/hc/en-us/articles/360023962013-FOAM-Token-FOA-Delisted)
- [INCIDENT/DATA] TCRParty (ConsenSys Alpine, Feb 2019, testnet) curated 99 Crypto Twitter accounts and had about 400 regular users in its first month. "A user who exploited the token faucet gained outsized influence over rankings." The economic assumptions were never tested because the tokens had no value. — [Breaker, Mar 15 2019](https://breakermag.com/tcrparty-wants-to-pay-you-for-finding-the-smartest-people-on-twitter/)
- [INCIDENT/DATA] Everest (MetaCartel → The Graph): a project registry launched about May 2020. It asked for a $6,000 grant and was explicitly run "without a token incentive." I found no later status, and it appears dormant. — [The Graph blog, May 14 2020](https://thegraph.com/blog/everest-inception-of-project-identities/); [MetaCartel forum](https://forum.metacartel.org/t/everest-tcr-proposal-for-funding/232)

**Survivors and partial survivors**
- [INCIDENT/DATA] Kleros Scout / Curate, as of January 2026: 600,000+ tagged addresses, 16,000+ individual submissions (peaks of 300+ a week), 508 Curation Court disputes in total (235 in 2025), and 34% of PNK staked on Gnosis locked in the Curation Court. Kleros calls the incentives "an investment to grow the registries fast enough," with 100,000 PNK reward pools per registry. — [Kleros blog, Jan 2026](https://blog.kleros.io/january-2026-scout-incentives-update-and-2025-highlights/)
- [INCIDENT/DATA] Kleros, August 2026: monthly reward pools of 100k PNK each for the Address Tag, Token and Contract Domain Name registries, plus 66.5k for Address Tag Queries (about 366.5k PNK a month in total). Each reward is capped at 500 PNK. Kleros now ships "agent-ready submissions", i.e. AI-agent skills at skills.kleros.io that find, verify and submit entries. Explorer references are Blockscout and Etherscan family. — [Kleros blog, Aug 2026](https://blog.kleros.io/august-2026-scout-incentives-new-chain-coverage-and-agent-ready-submissions/)
- [INCIDENT/DATA] Kleros Scout is distributed as a MetaMask Snap that shows Curate metadata during transactions. — [Kleros docs](https://docs.kleros.io/products/curate/kleros-scout-metamask-snaps)
- [INCIDENT/DATA] Uniswap Token Lists (Aug 26, 2020) went with **many competing off-chain lists hosted on domains the curators control**, so each list is tied to the curator's reputation. It rejected a single governance gatekeeper as a "naive approach." The Kleros T2CR list (t2crtokens.eth) was one of the initial lists, beside CoinGecko and CoinMarketCap. — [Uniswap blog](https://blog.uniswap.org/token-lists)
- [INCIDENT/DATA] Proof of Humanity (a Kleros TCR of humans): about 17,000 registrants within two years. The DAO forked in November 2022 after governance polarization. — [P2P Foundation wiki citing EUI report](https://wiki.p2pfoundation.net/Proof_of_Humanity). A July 2023 forum post says proposals that "would have seriously harmed the protocol came close to passing", which led to a forking vote. — [PoH governance forum](https://gov.proofofhumanity.id/t/the-way-forward-for-proof-of-humanity-origin/2861)
- [INCIDENT/DATA] Curve gauges as a stake-weighted curation analogue: "voting outcomes are strongly associated with the bribes set by higher-level protocols." Convex's fortnightly votes track Votium bribes, and Frax gained central influence indirectly through aggregators and vote markets. — [Lloyd, O'Broin, Harrigan, arXiv 2311.17589](https://arxiv.org/abs/2311.17589). So stake-weighted curation reliably turned into a **market for votes**. This is informative about willingness to pay, not about pool quality.

### Inferences
- What the survivors share: (1) an objective, checkable predicate (is this address the X contract? is this a unique human?), which matches Tabarrok's condition; (2) a separate dispute court instead of the registry's own token vote; (3) a continuous subsidy. Kleros spends roughly 366k PNK a month, which suggests organic demand alone does not keep submitters active. For agents, "does this endpoint answer to this schema / did this agent sign this" is the objective kind; "is this agent good" is the subjective kind that killed adChain and Civil.
- Uniswap's choice of many lists over one registry points to a pattern of **plural, reputation-bearing curators** rather than one canonical stake-voted list.
- Curve shows that wherever stake directs value, a bribe market appears. A staked reputation score that steers traffic or payments should expect a "Votium for agent rankings."
- Kleros pivoting to AI agents as submitters is direct evidence that agent-driven curation is already happening on a TCR.

### Gaps
- Primary sources for Mike Goldin's original TCR paper (2017), Aditya Asgaonkar's analyses and Vitalik's curation-market critiques were not retrieved. I found no reliable dated "TCRs are dead" post.
- No dated source for adChain's shutdown, FOAM's map-TCR abandonment, Messari dropping its TCR, or the Ocean, DXdao, Prospect Park and Relevant TCR experiments. Treat these as unverified "dormant" claims.
- No independent count of active Kleros Scout submitters, and no organic vs incentivized split.
- No current PoH v2 registration count.

## Q2. Web of trust: PGP, Keybase, Advogato

### Takeaway
Every permissionless web of trust in the brief died or stagnated. The causes were append-only open infrastructure that could be poisoned, privacy law (GDPR) colliding with immutable replication, acquisition, and trust metrics that were provably not attack-resistant.

### Cited Findings
- [INCIDENT/DATA] SKS keyserver poisoning, June 2019: attackers flooded certificates (Robert J. Hansen's, dkg's, Kristian's) so that importing them "wedges" GnuPG. Old, unpatched installs break, and users may read the attack as a software bug and give up. — [gnupg-users, Hansen, Jun 30 2019](https://lists.gnupg.org/pipermail/gnupg-users/2019-June/062100.html)
- [INCIDENT/DATA] The SKS pool stopped operating around mid-2021, citing GDPR takedown requests. Because SKS replicates every key to every node, a deletion on one node does not stick. keys.openpgp.org, the successor, hides user IDs by default, so many keys there are unusable without owner opt-in. — [iay.org.uk, Jul 5 2021](https://iay.org.uk/blog/2021/07/05/sks-key-servers-gone/)
- [INCIDENT/DATA] Keybase (social proofs: signed statements posted on GitHub, HN or domains linking identity to keys) was acquired by Zoom on May 7, 2020. "Development has stopped, but the service has been kept functional." — [Wikipedia: Keybase](https://en.wikipedia.org/wiki/Keybase); [CNBC May 7 2020](https://www.cnbc.com/amp/2020/05/07/zoom-buys-keybase-in-first-deal-as-part-of-plan-to-fix-security.html)
- [INCIDENT/DATA] Advogato (1999, Raph Levien) ran a PageRank-like peer certification trust metric. Its instance was shut down in 2016 and archived. Controversial users sometimes gained posting privileges. — [Wikipedia: Advogato](https://en.wikipedia.org/wiki/Advogato)
- [COMMENTARY/ANALYSIS] Jesse Ruderman (May 26, 2005) showed the Advogato metric is not attack-resistant as claimed. By confusing one high-capacity node that then certifies many cheap nodes, an attacker gains trust proportional to the **square** of attack cost. — [squarefree.com](https://www.squarefree.com/?p=263)

### Inferences
- Lesson for an agent layer: an append-only, permissionless store of signed claims needs a write cost and a read-side filter, or it gets poisoned the way SKS did. Privacy and deletion obligations conflict with immutable replication, so personal data should stay off-chain.
- Keybase's model of verifiable cross-platform proofs was technically sound, but it died commercially because one company owned it. Proof formats should not depend on one operator.
- Transitive-trust metrics leak trust through confused high-trust nodes. Any "endorsed by trusted agent" propagation needs per-hop damping and accountability for the endorser.

### Gaps
- No quantitative data on the decline in PGP web-of-trust usage. No Advogato spam data.

## Q3. PageRank-style package and repo metrics: stars, downloads, criticality

### Takeaway
Popularity signals for software are cheap to fake and miss real infrastructure. StarScout found about 3.8M to 6M fake GitHub stars, mostly used to promote malware. npm downloads were pumped past 1M for free. Metric-based project-health scores suffer a streetlight effect and Goodhart gaming.

### Cited Findings
- [INCIDENT/DATA] StarScout (He et al., arXiv 2412.13459, ICSE 2026): about 6.0M suspected fake stars before postprocessing and 3.81M after. 18,617 repos ran fake-star campaigns, involving 301k accounts. Activity "rapidly surged in 2024". In July 2024, 16.66% of popular repos (3,499) were affected. 90.42% of flagged repos and 57.07% of flagged accounts had since been deleted. Most fake stars promote short-lived phishing and malware repos, and the rest go to AI/LLM, blockchain and tool repos. Fake stars give a boost of under two months and then become a liability. — [arXiv html v2](https://arxiv.org/html/2412.13459v2); [ICSE 2026 listing](https://conf.researchr.org/details/icse-2026/icse-2026-research-track/14/Six-Million-Suspected-Fake-Stars-on-GitHub-A-Growing-Spiral-of-Popularity-Contests)
- [INCIDENT/DATA] Andy Richardson (Mar 9, 2021) got a package with "little to no users" past 1M npm downloads at no cost. — [DEV.to](https://dev.to/andyrichardsonn/how-i-exploited-npm-downloads-and-why-you-shouldn-t-trust-them-4bme/comments)
- [COMMENTARY] Andrew Nesbitt (May 9, 2026), "The Mismeasure of Open Source": downloads are dominated by CI, mirrors and bots (curl shows about 10k downloads a year); stars skew to web tooling (ICU, c-ares and libxml2 have few); CVE counts measure scrutiny, not insecurity; Dependabot, Renovate and scheduled coding agents make dead repos look maintained; projects tick OpenSSF Scorecard boxes without the underlying security work (Goodhart). — [nesbitt.io](https://nesbitt.io/2026/05/09/the-mismeasure-of-open-source)
- [COMMENTARY] OpenSSF explainer on the Criticality Score methodology and its intended use. — [OpenSSF blog, Jul 28 2023](https://openssf.org/blog/2023/07/28/understanding-and-applying-the-openssf-criticality-score-in-open-source-projects/)

### Inferences
- For agents and tools, "stars" or "invocations" as reputation will be farmed exactly as GitHub stars were, and scheduled coding agents already fake the "is maintained" signal. Signals should require costly, counterparty-attested events (paid calls, signed receipts from distinct payers) rather than unilateral counts.
- StarScout shows that **detection after the fact plus deletion** works at platform scale, which supports keeping a slashing or challenge path open retroactively.

### Gaps
- No sources retrieved on Libraries.io SourceRank gaming, npms.io, deps.dev or Drips/Gitcoin dependency funding outcomes.

## Q4. Stack Overflow reputation

### Takeaway
Stack Overflow's reputation system was well defended against vote fraud (daily automated serial-voting reversal since 2009). It still lost its input supply: questions fell from a 207k-a-month peak to about 1–3k a month in 2026. Reputation is worthless when the activity it measures moves elsewhere.

### Cited Findings
- [INCIDENT/DATA] A daily automated script detects anomalous voting, deletes sockpuppets and nullifies anomalous patterns. The checks are kept unpublished "so users can't work around them." — [Stack Overflow blog, Mar 21 2009](https://stackoverflow.blog/2009/03/21/more-voting-anomalies/)
- [INCIDENT/DATA] Questions began declining around 2014 (after moderation tightened), fell faster after June 2020 and again after ChatGPT (Nov 2022). By May 2025 they were back to 2009 levels. Data from SEDE. — [Pragmatic Engineer, May 2025](https://blog.pragmaticengineer.com/stack-overflow-is-almost-dead)
- [INCIDENT/DATA] Per SEDE figures reported by KuCoin News, which I have not verified independently: peak 207k questions (Mar 2014); about 1.34M questions in 2022; about 110k in 2025; Jan 2026 2,910; Jun 2026 1,072; Jul 2026 1,304. — [KuCoin news](https://www.kucoin.com/news/flash/stack-overflow-s-monthly-questions-drop-to-1-304-in-july-2026-down-99-from-2014)

### Inferences
- The decline was not caused by gaming. It came from substitution: AI answered the questions. A reputation layer's value depends on transaction flow running through it, and good anti-fraud does not protect against demand moving away.
- Hidden detection rules worked for Stack Overflow, but they conflict with the transparency expected of a permissionless on-chain score.

### Gaps
- No primary data on "rep inflation" (high-rep users accruing passive rep from old answers). The "Reputation Gaming in Stack Overflow" paper (ACM TOSEM, doi 10.1145/3691627) was found but not read.

## Q5. eBay and Amazon: inflation, retaliation, fake reviews

### Takeaway
Bilateral feedback inflates toward 100% because unhappy users stay silent or fear retaliation. eBay's mean is 99.3% positive and its median 100%. eBay removed seller-to-buyer negatives in 2008 to stop retaliation. Fake reviews became an industry, which led to the FTC's 2024 rule with penalties of up to $51,744 per violation.

### Cited Findings
- [INCIDENT/DATA] Nosko & Tadelis (NBER w20830, 2015): mean percent positive 99.3%, median 100%. "Effective percent positive" (positives divided by all transactions) has a mean of 64% and a median of 67%, and it predicts buyer behavior much better. Silence is a signal: in Oct 2011, 0.39% of transactions had negative feedback, but over 1% had a dispute opened. — [NBER](https://www.nber.org/papers/w20830.pdf)
- [INCIDENT/DATA] eBay announced in early 2008 that sellers could no longer leave negative feedback for buyers. [COMMENTARY] Brad Templeton: "Fear of revenge feedback was hurting the eBay system." — [4brad.com, Jan 31 2008](https://ideas.4brad.com/node/712)
- [INCIDENT/DATA] Amazon "proactively blocked over 200 million suspected fake reviews" in 2022. In 2023 it sued or referred about 163 bad actors (US 58, China 61, EU/UK 44). — [About Amazon, Feb 7 2024](https://aboutamazon.com/news/policy-news-views/amazons-latest-actions-against-fake-review-brokers-2023)
- [INCIDENT/DATA] FTC final rule announced Aug 14, 2024 and effective Oct 13, 2024. It bans fake and AI-generated reviews, buying reviews, undisclosed insider reviews, review suppression by threats, and buying or selling fake social-influence indicators (bot followers or views). Civil penalties run up to $51,744 per violation. — [Davis Wright Tremaine, Aug 2024](https://dwt.com/insights/2024/08/ftc-finalizes-rule-banning-fake-consumer-reviews)

### Inferences
- Agent-to-agent ratings will inflate the same way. Score against the denominator of all interactions (effective percent positive), and treat absence of feedback as information.
- Two-sided rating invites retaliation. eBay's fix was asymmetric rating rights.
- The FTC rule makes buying fake "indicators of influence" illegal in commercial use in the US. That could plausibly cover purchased endorsements or attestations of AI tools sold commercially (my inference, not legal advice).

### Gaps
- No post-2015 eBay positive-rate statistic retrieved.

## Q6. Stake-weighted reputation and sybils: Gitcoin, Optimism RetroPGF, EAS, Farcaster, Numerai, UMA, prediction markets. Testing "any score that weights a stake can be moved by whoever has the most capital"

### Takeaway
The belief is **partly true and partly contradicted**. UMA's March 2025 Polymarket incident is a documented case of a token whale moving a $7M resolution. The response was to add a permissioned whitelist of proposers selected by track record (Aug 2025), i.e. reputation layered over stake. Large capital also moved Polymarket prices in 2024 ("Théo", $42M+). Against that: across about 1M resolved contracts, prediction markets are "overall highly calibrated" (PNAS, Oct 2026). UMA's dispute rate is about 1.67% over 22k+ assertions. Numerai's stake-weighted meta model runs a fund with $700M AUM and a 25.45% net return in 2024. Stake stays informative when (a) the staker's own capital is at risk against an **exogenous, verifiable outcome** and (b) the stake-holder has no position in the thing being scored. It fails when the outcome is decided by the stake-holders themselves, as in token-vote resolution and gauge votes.

### Cited Findings
**Where capital moved the score**
- [INCIDENT/DATA] UMA / Polymarket, March 2025: the "Ukraine agrees to Trump mineral deal before April?" market ($7M) resolved YES against the facts after "a large holder of... UMA tokens" cast "a significant number of votes." Polymarket called it "unprecedented" and refused refunds because it "wasn't a market failure." — [The Block, Mar 26 2025](https://www.theblock.co/post/348171/polymarket-says-governance-attack-by-uma-whale-to-hijack-a-bets-resolution-is-unprecedented)
- [INCIDENT/DATA] UMA's response: UMIP-189 (passed Aug 6, 2025) moved Polymarket to the Managed Optimistic Oracle V2. Only 37 whitelisted addresses may propose: Risk Labs and Polymarket staff, plus users with more than 20 proposals at over 95% accuracy. Anyone may still dispute. Critics call it centralization. — [The Block, Aug 12 2025](https://www.theblock.co/post/366507/)
- [INCIDENT/DATA] A further controversy over the Zelenskyy "suit" market (Jul 2025). Users alleged a scam, and UMA said there was "no evidence" of foul play. — [The Defiant, Jul 9 2025](https://thedefiant.io/news/nfts-and-web3/polymarket-controversy-heats-up-after-the-zelenskyy-suit-market-resolves)
- [INCIDENT/DATA] Polymarket 2024: "Théo" placed $42M across four accounts on Trump and held over 20% of "yes" shares. Vanderbilt (Clinton & Huang) found that Polymarket's daily moves barely correlated with Kalshi or PredictIt, and that spikes reversed the next day in 58% of national presidential markets. They attribute this to uncapped stakes letting a single player move the market. Kalshi disputes the methodology. — [DL News, Dec 5 2025](https://www.dlnews.com/articles/markets/polymarket-kalshi-prediction-markets-not-so-reliable-says-study)
- [INCIDENT/DATA] Curve/Convex gauge votes track Votium bribes (see Q1). — [arXiv 2311.17589](https://arxiv.org/abs/2311.17589)

**Where stake stayed informative**
- [INCIDENT/DATA] A PNAS paper (doi 10.1073/pnas.2615627123) on about 1M resolved contracts across Polymarket, Kalshi, Manifold and Metaculus, 12 domains, horizons from hours to years: forecasts were "overall highly calibrated," with systematic biases in some high-consequence areas. — [Marginal Revolution, Oct 23 2026](https://marginalrevolution.com/marginalrevolution/2026/10/prediction-markets-are-accurate.html). Note that Manifold and Metaculus are not real-money platforms, so the result is not purely about stake.
- [INCIDENT/DATA] UMA Optimistic Oracle: 22,000+ assertions settled with a 1.67% dispute rate (Sep 2024, UMA's own figure, denominator undefined). — [UMA blog](https://blog.uma.xyz/articles/what-is-a-prediction-market-dispute)
- [INCIDENT/DATA] Numerai: 2024 net return of 25.45% with a single down month (company press release). AUM grew from about $60M to $550M over three years, and JPMorgan Asset Management committed up to $500M in capacity (Aug 2025). — [DL News press release, Nov 20 2025](https://www.dlnews.com/external/numerai-raises-30-million-series-c-led-by-top-university-endowments-at-500-million-valuation/). As of mid-2026: about $700M AUM, more than 1.1M NMR staked, and the "Stake-Weighted Meta Model continues to outperform" internal benchmarks (no numbers given). — [Numerai blog, Jul 15 2026](https://blog.numer.ai/numerais-third-strategic-buyback-of-nmr/)
- [COMMENTARY] Numerai's community rationale: without stake and burn, anyone could submit random predictions many times at no cost. I found no public evidence that stake-weighting beats equal-weighting. — [Numerai forum, Dec 2021](https://forum.numer.ai/t/on-the-existence-of-nmr/4658)

**Sybil-resistance attempts**
- [INCIDENT/DATA] Gitcoin GR14 (2022): the Sybil Defense summary shows 16,073 of 44,886 contributors (about 36%) under "Sybil attacks are way up!" My reading of the excerpt is that these are flagged accounts. — [Gitcoin gov forum](https://gov.gitcoin.co/t/gr14-governance-brief/11050)
- [COMMENTARY/DATA] Gitcoin Research (Oct 2024): Passport stamps plus an ML score are recommended in layers, and "some sophisticated attacks still succeed." Passport reportedly reduced flagged addresses by about 60% (attributed to GG23). — [Gitcoin Research](https://explore.gitcoin.co/research/quadratic-funding-sybil-resistance)
- [INCIDENT/DATA] Optimism Retro Funding retrospective (Nov 5, 2024): "mega rounds devolve into popularity contests." Badgeholders were overwhelmed in Round 3. Metrics-based Round 4 was easier but missed quality. In Round 5, projects split into multiple submissions to win more. OP "lack[s] data showing it produces superior outcomes." — [Optimism gov forum, ccerv1](https://gov.optimism.io/t/lessons-learned-from-two-years-of-retroactive-public-goods-funding/9239)
- [INCIDENT/DATA] Farcaster: the Neynar User Score (0–1, ML on public, protocol and on-chain data) is kept proprietary "so it can't be easily gamed." Its purpose is spam assessment, not proof of humanity, so "high-scoring agents and low-scoring humans both exist." Spam is described as cheap and lucrative because of airdrops. — [Neynar blog, Sep 30 2025](https://neynar.com/blog/neynar-scores-under-the-hood)

### Inferences
- A sharper version of the belief: a stake-weighted score can be bought **when the stakers decide the outcome** (token votes, gauges, DVM). It is hard to buy **when an exogenous outcome settles the stake** (market prices, future stock returns). Even then, deep pockets can distort thin markets temporarily, as Théo did. For agents, the analogue of an exogenous outcome is a verifiable task result, uptime probe or payment receipt, as opposed to a token-holder vote on "quality".
- UMA's fix (whitelisting proposers with a 95%+ accuracy record over 20 or more proposals) is reputation used to gate who can stake. It is evidence that pure stake was not enough and that a track record had to be added.
- Gitcoin, Optimism and Neynar each ended up with an opaque ML score or human judgment. There is a recurring tension between being transparent and being resistant to gaming.
- Optimism's "split into many projects" gaming maps directly onto agents. One operator can register many agents, so scores should be computed at operator or controller level.

### Gaps
- No usage stats for the Ethereum Attestation Service (one fetched page was about consensus attestations instead). No Lens spam data. No primary source for Augur's dispute history. A fork effort in Oct 2025 suggests Augur is dormant: [The Defiant](https://thedefiant.io/news/blockchains/rep-jumps-50-in-a-week-as-dev-gets-community-support-for-augur-fork).
- No exact figure on UMA token concentration in the March 2025 attack from a primary source.

## Q7. Uptime and liveness as reputation: Chainlink, Pocket, The Graph curation, Rated

### Takeaway
Measured liveness and performance is the most robust kind of reputation in this set. Rated has survived as an API business into 2026, though I found no revenue data. Stake-signalled curation of infrastructure failed at The Graph: bonding curves were front-run, and the signal was "noisy" relative to service quality. The Graph proposed replacing them with direct indexing fees.

### Cited Findings
- [INCIDENT/DATA] The Graph, GIP-0039 (Sep 29, 2022): under curation v1, late curators front-run query fees and capture most of early curators' fees. Bonding curves let early curators gain at later curators' expense ("rug pulling"), and developers can't tell how much GRT is needed to get indexed. The fix was to flatten the bonding curve on L2 and keep a 1% curation tax. — [The Graph forum](https://forum.thegraph.com/t/gip-0039-curation-v1-x/3613)
- [INCIDENT/DATA] The Graph, GIP-0058 (Aug 2023, Grana & Heaton): proposes replacing bonding curves with indexing fees, citing "a noisy relationship between curation signal and the quality of indexing service." — [The Graph forum](https://forum.thegraph.com/t/gip-0058-replacing-bonding-curves-with-indexing-fees/4425)
- [INCIDENT/DATA] Rated Labs ("Reputation for machines") raised $2.5M seed and later a Series A (Archetype). Its site was still operating in 2026, with an explorer and paid-tier APIs across Ethereum, Solana, EigenLayer and others. It shows no pricing, names no customers, and its metrics are placeholders. — [rated.network](https://www.rated.network); [The Defiant](https://thedefiant.io/rated-labs-validator-rep); [Archetype](https://www.archetype.fund/media/announcing-our-series-a-investment-in-rated)
- [INCIDENT/DATA] Pocket Network's Relay Mining paper (about May 2023) reports a peak of 2B relays a day. Its original design spent about 70% of each block on Merkle proofs, and quality of service was deferred to future work. — [arXiv 2305.10672](https://ar5iv.labs.arxiv.org/html/2305.10672)

### Inferences
- When "reputation" is computed from observed performance (Rated, StarScout-style detection), it holds up. When it is a stake signal about expected quality (Graph curation), speculators extract value and the signal decouples from service quality. For an agent reputation layer, stake should work as a bond, slashable on verifiable failure, rather than as a speculative signal of quality.
- Rated's survival without visible revenue suggests that reputation data for machines is a thin business. It is likely sold as B2B API and data, not monetized as a protocol token.

### Gaps
- No source found on the market.link shutdown or on Chainlink node reputation. No Rated revenue figures. No Pocket servicer QoS gaming data from a primary source.
