Perpetual futures — contracts that let traders take leveraged long or short positions on an asset without an expiry date — have become the dominant trading instrument in crypto, now extending into real-world assets, pre-IPO equity, and AI-driven automation.

---

## What a Perpetual Contract Actually Is

A perpetual future (commonly shortened to "perp") is a derivative instrument that tracks an underlying asset's price through a mechanism called the **funding rate**. Unlike traditional futures, which settle on a fixed date, perps never expire. Instead, a periodic payment — positive or negative — flows between long and short holders to keep the contract price anchored to the spot market. When longs dominate, longs pay shorts; when shorts dominate, shorts pay longs.

The core appeal is leverage without the administrative overhead of rolling contracts every quarter. A trader can open a 10x leveraged BTC position and hold it indefinitely, paying or collecting funding along the way. The risk, equally, is that a sufficiently adverse price move against an undercollateralized position results in liquidation.

Most perps are **inverse** (collateralized in the base asset) or **linear** (collateralized in a stablecoin like USDC or USDT). The linear, USDC-margined structure has become standard on both centralized and onchain venues because it simplifies profit/loss accounting in fiat terms.

---

## The Infrastructure: Centralized vs. Onchain

For most of crypto's history, perps were a centralized-exchange product. Binance, OKX, and Bybit built enormous books — handling trillions in annual notional — through traditional order-matching engines with custodial collateral.

The decentralized alternative emerged gradually. Early AMM-based perpetual protocols suffered from oracle manipulation and thin liquidity. The architecture that changed the competitive landscape was the **onchain order book**: a fully on-chain matching engine with transparent, verifiable settlement and non-custodial collateral.

**Hyperliquid** crystallized this model. Operating on its own purpose-built L1, Hyperliquid runs a central limit order book where every trade, funding payment, and liquidation is settled on-chain without a CEX intermediary. By May 2026, Hyperliquid's perps volume had reached a record **6.63% of total global CEX perpetual futures volume and 14.4% relative to Binance** — both all-time highs, driven largely by the HIP-3 framework that enables permissionless market creation. That growth is notable enough that the NYSE's parent company, ICE, publicly stated it was "learning from" Hyperliquid rather than dismissing it.

Hyperliquid's reach is also expanding through integrations. Infinex, for example, added spot markets — starting with the HYPE/USDC pair, which logged $138M in volume early on — directly inside its Hyperliquid-connected perps interface, blurring the line between spot and derivatives trading within a single UI.

---

## Who's Trading and How

The perps user base has broadened well beyond professional arbitrageurs and crypto-native funds. Several structural changes are driving wider adoption:

**Simplified onboarding.** PancakeSwap's perps product introduced a "Simple Mode" and launched a "Try Perps on Us" promotion covering first losses — an explicit effort to lower the psychological barrier for retail traders unfamiliar with funding rates or liquidation mechanics. AI-powered copilots on the same platform further reduce the learning curve.

**Autonomous trading.** The Virtuals protocol integration with Hyperliquid allows large-language models — Claude, ChatGPT, Codex — to execute perps trades programmatically through HIP-3 markets via its EconomyOS infrastructure. This turns perp markets into an execution layer for AI agents rather than a screen that requires human attention.

**Retail incentive design.** Venues like Rocket Perps (built on the DeFi App) route a share of trading revenue into token buybacks and structure products so that traders earn rewards even on losing trades, reframing perpetual trading as a yield-generating activity rather than a zero-sum bet.

---

## Expanding Asset Classes

The most significant structural shift in the perps market over the past year is the expansion beyond crypto-native assets.

**Real-world asset perps.** Coinbase, which became the first US exchange permitted to offer global crypto perps trading, has pushed aggressively into non-crypto underlyings. Within two months of launching stock and metals perps, the platform crossed **$1.5 billion in trading volume** across more than 20 real-world asset contracts — equities, commodities, and indices — all settling 24/7 rather than during the ~30% of the week that traditional markets are open. OKX expanded its X-Perps offering in Europe to include Magnificent Seven tech stocks alongside gold and oil. DecibelTrade, built on Aptos, added perps on SPY, QQQ, and the Korean index EWY with around-the-clock onchain execution.

**Pre-IPO and private-company perps.** Coinbase launched pre-IPO perps with a SpaceX contract, allowing traders to express a view on private valuations before a public listing. The model is nascent and carries unique risks — price discovery on illiquid private markets is inherently noisier — but it addresses genuine demand for exposure to companies that have stayed private longer than historical norms. Ventuals briefly offered private-company perps on Hyperliquid before shutting down, illustrating both the appetite and the operational difficulty of sustaining such markets.

**Prediction market perps.** Kalshi's perps product, launched into private rollout, topped **$1 billion in volume within one week** before its public debut — a signal that time-based and event-based derivatives have a deep liquidity pool waiting for the right interface. Coinbase has also announced time-based prediction markets as part of its expanded derivatives suite.

---

## Privacy-Preserving Perps

A smaller but technically ambitious frontier is **private perpetuals** — contracts where position sizes, directions, and strategies remain encrypted from public view while still settling on a verifiable blockchain.

PriveX is building in this direction using garbled circuits, a cryptographic technique from secure multi-party computation. The premise: current onchain order books are fully transparent, which creates front-running and information leakage for large traders. Encrypting trade intent at the protocol level could attract institutional flow that currently avoids onchain venues for precisely this reason. PremiumBlock's non-custodial Risk Hub takes a parallel approach, bundling user-created prediction markets, perps, and other instruments in a self-custody framework.

These architectures are early-stage, and the tradeoff between privacy and auditability remains unresolved — but the direction reflects a maturation in what onchain perps are expected to offer.

---

## The US Regulatory Shift

For most of crypto's history, US traders were effectively locked out of the highest-leverage perpetual products. The CFTC's jurisdiction over derivatives combined with ambiguity about crypto's asset classification pushed most perps activity offshore.

That is changing. Coinbase becoming the first US exchange authorized to offer global crypto perps was a landmark, and the platform now markets its offering as "US Perps" — 22 assets, no expiration, institutional-grade liquidity. Regulatory frameworks crystallizing around stablecoins and crypto market structure more broadly are creating pathways for other venues. Orderly's infrastructure is positioning itself to let any developer launch a compliant perpetual trading platform in under an hour for $10, treating regulation as infrastructure-ready rather than a blocker.

The failure of some ventures in this space is equally instructive. Satori Finance, a Coinbase-backed perps exchange, shut down — a reminder that regulatory legitimacy alone doesn't guarantee product-market fit in a competitive market. Distribution, liquidity depth, and fee structure still determine survival.

---

## Risks Traders Should Understand

No explainer of perpetuals is complete without the mechanics of loss:

- **Funding rate drag.** A persistent one-sided market means the losing side pays continuously. A long position in a strongly bullish market may pay 0.1% or more per 8-hour funding period, which annualizes to over 100% cost.
- **Liquidation cascades.** High leverage amplifies small price moves into account-wiping events. Cascading liquidations can create feedback loops where forced selling drives prices further against other leveraged positions.
- **Oracle risk.** Perps price themselves off external oracles; a manipulated or stale oracle can trigger incorrect liquidations. Onchain venues have addressed this to varying degrees, but the risk is never zero.
- **Counterparty risk.** Centralized perps carry custodial risk. Onchain perps carry smart contract risk. Non-custodial doesn't mean risk-free.
- **Basis risk on RWA perps.** Perps on stocks or commodities settle in crypto-native stablecoins, not the underlying asset. Settlement is synthetic; traders don't acquire the actual stock.

---

## Outlook

The perps market is compounding in two directions simultaneously: deeper penetration of existing crypto markets, and lateral expansion into equities, commodities, private companies, and prediction markets. Hyperliquid's order book model has demonstrated that onchain venues can capture meaningful share from CEX incumbents when execution quality is competitive. Coinbase's regulatory clearance in the US opens a geography that was structurally excluded from the highest-volume products.

The next credible inflection points are privacy-preserving execution reaching production quality, AI agents becoming meaningful perps volume contributors through platforms like Virtuals, and further regulatory clarity enabling more asset classes — particularly equity derivatives — to trade 24/7 in crypto-settled markets. The instrument that started as a way to short Bitcoin without borrowing BTC is becoming infrastructure for a parallel, always-on global financial system.
