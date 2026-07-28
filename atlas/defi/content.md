Decentralized finance (DeFi) is an umbrella term for financial services — lending, trading, yield generation, and derivatives — that run on public blockchains through self-executing smart contracts, removing the need for banks, brokerages, or other intermediaries.

---

## What DeFi Actually Is

Traditional finance depends on trusted intermediaries: a bank holds your deposit, a clearinghouse settles your trade, a credit bureau decides your loan eligibility. DeFi replaces those institutions with code. Smart contracts — programs that execute automatically when predefined conditions are met — hold collateral, calculate interest, match buyers with sellers, and settle transactions without any single party controlling the outcome.

The result is a financial system that is, in principle, open to anyone with an internet connection and a crypto wallet. There are no business hours, no account minimums set by a compliance officer, and no geographic restrictions baked into the product layer. In practice, the picture is more complicated — but those properties explain why DeFi attracted tens of billions of dollars in capital and thousands of developers over a compressed few years.

Most DeFi activity runs on Ethereum and a cluster of Ethereum-compatible chains, though ecosystems on Solana, BNB Chain, and newer validity-proof networks such as Starknet have grown substantially. The canonical metric is **total value locked (TVL)** — the aggregate dollar value of assets deposited into DeFi protocols — tracked in real time by platforms such as [DefiLlama](https://defillama.com).

## The Core Primitives

### Decentralized Exchanges (DEXs)

A DEX lets users swap tokens directly from their wallets. Instead of a central order book maintained by a company, most DEXs use **automated market makers (AMMs)**: liquidity pools funded by depositors who earn a share of trading fees in return. Curve Finance specializes in low-slippage swaps between assets that should trade near parity — stablecoins and liquid staking tokens — and its architecture became foundational to how stablecoin liquidity is organized across DeFi. Protocols ranging from stablecoin issuers to lending markets route trades through Curve pools for this reason.

Hyperliquid, a newer perpetuals exchange, illustrates how quickly the competitive landscape shifts: in mid-2026 it was generating more daily fee revenue than Ethereum, Solana, Bitcoin, and BNB Chain combined — with just eleven employees — by shipping a purpose-built layer-1 optimized entirely for on-chain derivatives.

### Lending and Borrowing

Lending protocols let users deposit assets to earn yield and borrow against collateral. Aave is the most widely cited example: it runs on multiple chains, supports dozens of assets, and uses algorithmic interest rates that rise as utilization climbs. Borrowers must maintain collateral above a liquidation threshold; if prices move against them, automated liquidators seize collateral to repay the debt, keeping the protocol solvent.

Morpho has built a modular layer on top of Aave and Compound that matches lenders and borrowers peer-to-peer when possible, improving rates for both sides. Venus Protocol operates a similar model on BNB Chain and in 2026 introduced a fixed-term vault built on the ERC-4626 standard, giving depositors predictable rates rather than the variable rates typical of AMM-style lending pools.

### Stablecoins

Stablecoins are the connective tissue of DeFi. USDC (issued by Circle) and USDT (Tether) dominate volume, but a growing share of liquidity is shifting toward **yield-bearing stablecoins** — tokens that automatically accrue returns from treasuries, money-market strategies, or delta-neutral positions. Five distinct models have emerged, from simple T-bill pass-throughs to more complex hedged designs. This is a direct response to users recognizing the opportunity cost of holding inert dollar tokens when on-chain rates exist.

Novel designs push further: Tangent's USG issues loans at 0% interest, funding the zero-cost borrowing by redirecting the yield emissions from the borrower's own Curve LP collateral back to the protocol. That kind of composability — one protocol's output feeding another's input — is distinctly DeFi.

## Bitcoin's Complicated Relationship with DeFi

Bitcoin is the largest crypto asset by market cap, but its base layer has no native smart contract functionality. For years, the only way to use BTC in DeFi was through custodial wrapped tokens like WBTC, which require trusting a centralized custodian to hold the underlying bitcoin. That trust assumption is precisely what DeFi is supposed to eliminate.

Several approaches are narrowing the gap. Citrea, a Bitcoin ZK-rollup, has enabled what its developers describe as the first trust-minimized BTC-backed lending market through an integration with Morpho — using cryptographic proofs rather than a custodian to anchor the BTC collateral. This matters because Bitcoin holders represent a large pool of capital that has historically sat outside the DeFi yield ecosystem entirely. Bridging that capital in without reintroducing custodial risk is an unsolved problem that multiple teams are actively competing to solve.

## Real-World Assets Enter the Stack

One of the more significant structural shifts in DeFi since 2023 is the tokenization of real-world assets (RWAs): US Treasuries, private credit, commodities, real estate, and equities issued as blockchain tokens. DefiLlama's *State of RWAfi Q1 2026* report documents macro growth across all of these categories.

The appeal is straightforward: on-chain yield from government bonds is more transparent and composable than off-chain equivalents, and DeFi protocols can integrate tokenized T-bills as collateral or reserve assets. Securitize, one of the larger tokenized-securities platforms, expanded its multichain reach to TRON in 2026 specifically to access that network's large stablecoin payment userbase.

IPOR Labs has proposed a utility-pricing model for RWA liquidity, helping investors choose algorithmically between instant token redemption versus delayed redemption using risk-adjusted certainty equivalents — an example of DeFi tooling catching up to the complexity of the assets being imported.

The institutional interest in RWAs is real, but executives at events like Proof of Talk have been direct: major banks will not embrace DeFi at scale until the industry addresses its security track record. Multimillion-dollar exploits remain common, and the perception that smart contract risk is uncontrollable is a meaningful barrier.

## Where DeFi Has Failed

The honest account of DeFi includes its failures, and they are instructive.

**Uncollateralized lending** is the clearest case study. Goldfinch, backed by Coinbase Ventures and a16z, used social trust to extend uncollateralized loans to businesses in Africa and Asia — promising approximately 10% yields to depositors. By 2023–2024, the protocol disclosed $53.8 million in troubled loans and an official 19.95% loss rate; some depositors estimate their realized losses far exceed that figure. The experience illustrates a fundamental tension: DeFi's enforcement mechanisms work well for overcollateralized positions where liquidation is automated, but they break down when real-world credit is involved and collateral cannot be seized by a smart contract.

**Governance attacks** expose a different fragility. A 2026 attack on Moonwell — a lending protocol — used just $1,800 in governance tokens to attempt to drain $1 million in protocol funds. The attack failed, but it demonstrated that low-token-cap governance systems can be cheaper to attack than to defend. Protocol governance is an unsolved design problem, and the history of DeFi is littered with exploits that moved faster than governance could respond.

**Protocol near-collapses** happen even among established names. Balancer, one of the original AMMs, came within days of a full shutdown before its founder intervened with a tokenomics overhaul. Governance proposals that emerge from those crises often reveal how much informal power sits with founding teams despite the "decentralized" branding.

## Privacy, Infrastructure, and the Builder Layer

Privacy has historically been DeFi's weak point. Every transaction on a public blockchain is visible by default, which suits transparency advocates but creates problems for institutional users who do not want their trading strategies, treasury positions, or counterparties exposed. Starknet's STRK20 privacy token standard and Starkzap v2 SDK — which packages swaps, lending, DCA, bridging, and confidential payments into a unified developer interface — represent attempts to add privacy as a first-class property of DeFi primitives rather than as an afterthought.

The builder culture that produced these protocols is worth understanding. Inverse Finance founder Nour Haridy has documented DeFi's iterative, "drop a protocol and see what sticks" ethos — exemplified by figures like Andre Cronje, who launched and sometimes abandoned protocols weekly during the 2020–2021 cycle. Solidly's rebirth as Aerodrome on Base is another example of ideas that failed under one set of market conditions being rebuilt and succeeding under different ones.

## Regulatory Context

DeFi sits in legal grey zones across most jurisdictions. In the United States, the CLARITY Act — championed in the Senate by Cynthia Lummis with bipartisan support as of 2026 — attempts to draw a clearer line between digital assets that function as commodities and those that are securities, with provisions intended to provide developers of non-custodial protocols explicit legal protection. Whether those protections hold up to enforcement is untested.

The broader regulatory trend is toward requiring compliance infrastructure — KYC, AML screening — for any DeFi interface that touches institutional capital or retail users in regulated markets. This creates a layered reality: the underlying protocols remain permissionless, but the front-ends and integrations that most users actually use are becoming compliance surfaces.

## Key Metrics to Watch

- **Total Value Locked (TVL):** The aggregate collateral deployed in DeFi protocols, tracked by DefiLlama. TVL fluctuates with asset prices as well as genuine inflows or outflows.
- **Protocol revenue and fees:** A better signal of genuine usage than TVL alone. Hyperliquid's fee dominance in mid-2026 is a concrete example of revenue as a competitive signal.
- **Stablecoin composition:** The market share split between yield-bearing stablecoins and inert dollar tokens indicates how much capital is actively working on-chain.
- **RWA TVL:** The value of tokenized real-world assets deployed in DeFi protocols, a proxy for institutional participation.
- **Exploit frequency and magnitude:** Tracked by security firms and DefiLlama's hack tracker. Trends here affect institutional confidence more than almost any other metric.

## Outlook

DeFi's trajectory runs in two directions simultaneously. On one side, the infrastructure is maturing: modular lending, privacy-preserving transaction layers, trust-minimized Bitcoin integration, and RWA tokenization are all closing gaps that kept institutional capital at arm's length. Kairos bringing interest rate swaps on-chain after $300 million in notional beta volume, and Polymarket acquiring Brahma for DeFi execution infrastructure, suggest that the stack is solidifying.

On the other side, the failures — governance attacks for $1,800, uncollateralized loan books with 70%+ real loss rates, and protocols that nearly collapse before founder intervention — are reminders that much of DeFi's governance and risk management remains experimental. Security flaws are not an edge case; they are a recurring structural feature.

The most likely medium-term outcome is a bifurcation: a regulated, compliance-wrapped layer of DeFi that institutions and large retail users access through audited front-ends, and a permissionless core that remains accessible to anyone willing to interact directly with contracts and accept the associated risks. Both layers will grow, but they will serve different needs and operate under different risk profiles.

---
