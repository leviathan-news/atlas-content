The de facto source for decentralized finance data, DefiLlama is an open-source analytics aggregator that tracks total value locked (TVL), fees, revenue, stablecoin flows, and protocol-level metrics across hundreds of blockchains and thousands of DeFi applications.

---

## What DefiLlama Is — and Why It Matters

Before DeFi had a scoreboard, measuring the health of the ecosystem meant piecing together on-chain data from disparate explorers and project dashboards. DefiLlama, launched in 2020 and built by the pseudonymous developer 0xngmi alongside a distributed volunteer team, filled that gap with a single aggregator that anyone — retail user, institutional researcher, or regulator — could consult for a neutral read on the market.

The platform's significance goes beyond convenience. Because DefiLlama is open-source, its methodology for calculating TVL can be audited, forked, and disputed in public. That transparency is a deliberate design choice: the team explicitly rejects paid listings and refuses to let protocols influence how their numbers are reported. When 0xngmi publicly caught an AI-generated DeFi project faking arbitrage profits using JavaScript's `Math.random()` function in a bid to game a DefiLlama listing, the episode illustrated why independent vetting matters in a space where on-chain data is easily manipulated at the application layer.

## TVL: The Metric DefiLlama Made Famous

Total Value Locked is the aggregate dollar value of crypto assets deposited into DeFi smart contracts — lending pools, liquidity pools, yield vaults, bridges, and more. It is an imperfect but widely-used proxy for ecosystem activity, analogous to assets under management in traditional finance.

DefiLlama is the primary source most publications cite when reporting TVL figures. Its cross-chain methodology counts collateral deposited directly on each network and attempts to avoid double-counting assets that move between protocols. As of mid-2026, the platform reported DeFi TVL at roughly $85.65 billion — a decline of approximately 50% from the $171 billion peak reached in October of the prior cycle, a data point the platform itself surfaced. That willingness to publish unflattering aggregate numbers, without editorializing, is part of what makes the source trusted across the industry.

TVL figures from DefiLlama are now routinely cited in regulatory and policy contexts. When the U.S. Federal Reserve and other oversight bodies assess stablecoin markets or broader DeFi risk, they lean on third-party aggregators — a dynamic that has prompted commentary about the accountability gaps in that dependency and whether public institutions should be building more sovereign data infrastructure.

## Beyond TVL: The Full Data Suite

DefiLlama has grown well beyond a single-metric tracker. Its current dashboard surfaces:

**Fees and Revenue.** Protocol-level fee income, broken down by chain and application. This is one of the most-watched sections for analysts trying to distinguish protocols with genuine economic activity from those running on token incentives. DefiLlama recently added tracking for the OPEN Stablecoin Index to its Fees & Revenue dashboard, expanding coverage of stablecoin-related income streams.

**Stablecoins.** Supply, peg deviation, and chain distribution for major stablecoins. Given that stablecoins are the primary medium of exchange in DeFi — and an area of intense regulatory scrutiny — this section sees significant institutional traffic.

**DEX volumes.** Aggregated trading volumes across decentralized exchanges, useful for tracking liquidity migration between chains and protocols.

**Bridges.** Cross-chain bridge volume and total bridged value, a critical risk-monitoring surface after several high-profile bridge exploits.

**Yields.** An aggregator of yield opportunities across lending and liquidity protocols, helping users compare returns across the ecosystem.

**Tokens.** DefiLlama's [token rankings](https://defillama.com/tokens) track price, market capitalization, fully diluted valuation, and upcoming unlock schedules across thousands of assets, pairing price with the unlock schedule that governs future supply. Each token also has its own detail page; [Ethereum's token page](https://defillama.com/token/ETH), for instance, breaks out quarterly income statements — gross protocol revenue, fees, and earnings — a running table of yield-bearing pools across lending and staking protocols, and a split of 24-hour trading volume between centralized and decentralized exchanges, plus dedicated tabs for token usage across DeFi and for liquidations.

**Real-World Assets (RWA).** A separate [RWA dashboard](https://defillama.com/rwa) ranks tokenized treasuries, commodities, private credit, and other off-chain assets by active and onchain market capitalization, and reports what share of each asset's value is actually deployed inside DeFi rather than sitting idle in custody — the same issuance-versus-use question DefiLlama Research examined in its RWAfi report, but as a live, per-asset breakdown instead of a point-in-time study. Redemption terms, KYC requirements, and custody model are listed per asset, the due-diligence detail institutional allocators look for before touching tokenized exposure.

**Raises and Hacks.** Fundraising announcements and a running ledger of DeFi exploits, both sourced semi-automatically and manually curated.

In 2026, DefiLlama expanded its data surface further by acquiring Bulletin, a platform that provided structured valuation and OTC data for private crypto companies. The acquisition signals an ambition to connect on-chain public-market data with private-market fundamentals — giving investors a view into how a protocol's publicly-visible TVL and revenue numbers align with its private valuation and OTC pricing.

## LlamaAI: Bringing Analytics to Conversational Interfaces

A notable recent expansion is LlamaAI, an AI assistant built on top of DefiLlama's proprietary data layer. Rather than requiring users to navigate dashboards, LlamaAI accepts natural-language queries and returns analysis, charts, and actionable insights drawn from DefiLlama's aggregated data.

The product has been progressively opened up. After an initial subscriber-only rollout for paying users who wanted to turn a single prompt into in-depth protocol analysis and original charts, DefiLlama made LlamaAI free for a limited period to lower the barrier for users exploring on-chain analytics. The platform also integrated LlamaAI directly into Telegram — first as a chat-based assistant offering instant DeFi analytics and on-chain insights, then as a customizable alert system delivering daily notifications about on-chain trends and DeFi news. That Telegram-native distribution strategy reflects a broader industry pattern of meeting crypto users where they already communicate.

The move into AI-assisted analytics positions DefiLlama in a competitive space, but its structural advantage is the underlying data: LlamaAI's outputs are only as reliable as the protocol adapters and methodology behind them, and DefiLlama's transparent, community-maintained adapter system is harder to replicate than the AI layer itself.

## DefiLlama Research: The Publishing Arm

Alongside its data platform, DefiLlama operates a research publishing function under the DefiLlama Research banner, which distributes work through its own Telegram channel and publishes in-depth reports on DeFi sector trends.

DefiLlama Research's [catalog](https://defillama.com/research) runs across tokenized-equities adoption, DAO treasury management, credit-ratings infrastructure, and RWA sector analysis in 2026 alone, alongside protocol-specific reports.

One example is [The State of RWAfi: Q1 2026](https://defillama.com/research/report/the-state-of-rwafi-q1-2026-report), which used DefiLlama's own RWA data to size the gap between issuance and use: the report's measure of the active real-world-asset market grew from roughly $4.1 billion in early 2025 to about $25.2 billion by March 2026, while against the broader total onchain RWA market capitalisation of about $28.6 billion, only around $2.81 billion was actually deployed inside DeFi protocols. The report treats that gap — assets issued onchain but sitting outside DeFi entirely — as the sector's real constraint, not a rounding error.

Another dated example is [Katana: Bringing ve(3,3) to the Chain Level](https://defillama.com/research/report/katana-bringing-ve33-to-the-chain-level) (DefiLlama Research, 10 February 2026), which examined how Katana routes chain-level revenue — Vaultbridge yield, AUSD yield, chain-owned-liquidity returns, and sequencer fees — back to vKAT holders rather than to validators or a foundation treasury.

DefiLlama Research describes itself as offering "bespoke digital asset research and market intelligence," publishes a "Trusted by" client list that includes exchanges such as Binance and Bybit, and marks some catalog entries as sponsored. That combination cuts both ways: it lets DefiLlama monetize the credibility its neutral dashboard built, while asking a reader to judge each report on its own terms rather than assume the same independence that governs the TVL numbers.



## The DL News Closure and What It Signals

DefiLlama's affiliated media outlet, DL News, announced in May 2026 that it would shut down at the end of that month. The publication, which had operated as a standalone crypto news outlet, cited declining crypto media traffic and worsening conditions for search and content distribution as the primary causes of an unsustainable business model.

The closure illustrates a structural challenge for vertical crypto media: advertising markets for crypto publications have contracted, search traffic has fragmented across AI-generated summaries and social platforms, and audience attention has concentrated on a small number of dominant destinations. Blockworks, one of the more established crypto media brands, reportedly pivoted its strategy in the period around DL News's closure — a sign that even better-capitalized outlets are rethinking their content models.

DL News shutting down does not affect DefiLlama's core data platform, which operates separately and is not revenue-dependent on media advertising. But it removes one of the few journalistically-oriented voices that was closely aligned with on-chain data sourcing from DefiLlama's own infrastructure.

## Data Integrity and Fraud Detection

One under-appreciated aspect of DefiLlama's operation is the ongoing curation work required to maintain data integrity across thousands of protocol adapters. Unlike financial data providers in traditional markets, DefiLlama cannot rely on regulated filings or audited financial statements. Protocol teams submit adapters — code snippets that tell DefiLlama how to read their smart contracts — and those adapters must be reviewed for accuracy.

The fraud-detection dimension is real. When 0xngmi caught a project using randomized number generation to fake trading profits in its listing application, he documented the case publicly. DefiLlama has also built a search tool that indexes thousands of protocols with manually-vetted links and accurate rebrand mapping — preventing the common confusion that arises when projects rename themselves and old URLs become vectors for phishing or misinformation.

The platform's hiring of additional developers (fully async, distributed positions) reflects the scale of maintenance work required to keep adapters current as protocols upgrade contracts, migrate chains, or rebrand.

## Who Uses DefiLlama — and How

**Retail users** consult DefiLlama primarily through its yield aggregator and TVL rankings when deciding where to deploy capital. The dashboard's accessibility — no account required, no paywall for core data — has made it a default first stop.

**Researchers and journalists** use the platform as a primary citation source for TVL, fee, and stablecoin data. The platform's transparent methodology makes it defensible in published work in a way that proprietary data terminals often are not.

**Protocol teams** monitor their own TVL rankings, fee metrics, and yield listings. Placement and accuracy on DefiLlama can affect capital inflows, since many users treat the rankings as a quality signal.

**Institutional and regulatory observers** are increasingly in the audience. The Federal Reserve's use of third-party stablecoin data — and the governance questions that raises — points to a future where aggregators like DefiLlama may occupy a quasi-infrastructure role in financial oversight, without having been formally designated as such.



## Outlook

DefiLlama enters the back half of the decade in a structurally strong position: its data is widely trusted, its methodology is open to scrutiny, and its product surface has expanded well beyond the TVL tracker that established its reputation. The acquisitions of private-market data via Bulletin, the development of LlamaAI as a consumer-facing product, and the continued output of DefiLlama Research position the platform as something closer to a full-stack DeFi data company than a single-purpose aggregator.

The risks are proportional to that ambition. Maintaining data quality across thousands of protocols on dozens of chains is operationally demanding, and the team's reputation depends on the accuracy that aggressive growth could threaten. The adjacent media experiment — DL News — failed, which suggests that building editorial credibility and data credibility in parallel is harder than it looks.

If TVL recovers toward prior highs and DeFi activity broadens to encompass more RWA flows and institutional participation, DefiLlama's dashboard will likely be the first place those trends become legible. That makes it one of the more important pieces of neutral infrastructure in a space that has historically been short of it.

---
