Curve Finance is a decentralized exchange (DEX) built specifically for low-slippage swaps between assets that should trade near parity—stablecoins, liquid staking tokens, and synthetic assets—underpinned by a governance and incentive system that became a template for DeFi protocol design.

---

## The StableSwap Problem Curve Was Built to Solve

Standard automated market makers (AMMs) like Uniswap use the constant-product formula `x · y = k`, which spreads liquidity across all prices. That works for volatile asset pairs, but it produces unnecessary slippage and capital inefficiency when swapping between assets that should always trade at roughly 1:1—think USDC to USDT, or stETH to ETH.

Curve's founder Michael Egorov published the [StableSwap whitepaper](https://curve.fi/files/stableswap-paper.pdf) in 2019, introducing a hybrid invariant that concentrates liquidity near the peg price. Curve launched on Ethereum mainnet in January 2020. The core insight: blend the constant-product formula with a constant-sum formula (`x + y = k`), weighting toward constant-sum when the pool is balanced and shifting toward constant-product at the extremes. The result is dramatically tighter spreads—typically 0.01–0.04% on major stablecoin pairs—versus 0.3% or more on Uniswap v2.

The protocol later extended this to volatile asset pairs through **Curve v2** (Cryptoswap), which introduced an internal price oracle and an amplification parameter that adjusts dynamically, enabling low-slippage swaps on pairs like BTC/ETH or CRV/ETH. This architecture underpins a large portion of on-chain stablecoin volume to this day.

:::newscard|243164

## CRV Token and the veCRV Model

The **CRV token** launched in August 2020 as Curve's governance and incentive token. It serves three interrelated purposes: rewarding liquidity providers (LPs), aligning long-term holders with protocol outcomes, and governing which pools receive emissions.

The key innovation is **vote-escrowed CRV (veCRV)**. Users lock CRV for between one week and four years; locking for four years grants 1 veCRV per CRV. The veCRV balance decays linearly toward zero as the unlock date approaches, creating an ongoing economic incentive to stay committed. In return, veCRV holders receive:

- **50% of all protocol trading fees**, distributed as 3CRV (a Curve LP token itself).
- **Gauge weight votes**, determining how weekly CRV emissions are allocated across liquidity pools.
- **LP boosts** of up to 2.5× on CRV rewards for liquidity they personally provide.

The gauge-weight mechanism spawned an entire sub-ecosystem sometimes called the **"Curve Wars"**: protocols such as Convex Finance and Yearn Finance accumulated large veCRV positions to direct emissions toward their preferred pools, extracting yield for their own token holders. Convex's [Resupply](https://www.convexfinance.com/) initiative, for instance, recently launched a stablecoin called `$reUSD` backed by yield-bearing positions in both Curve Lend and Fraxlend, illustrating how deeply Curve's incentive layer has been incorporated into third-party protocol design.

As of 2026, over 45% of circulating CRV supply remains locked in veCRV contracts—a figure that suggests substantial community alignment despite the token's price having fallen far from its 2021 peak. Circulating supply sits at roughly 1.47 billion CRV with an annual inflation rate of approximately 5%, down from earlier higher issuance.

:::newscard|245636

## crvUSD and LLAMMA: Rethinking Liquidations

Curve deployed its own overcollateralized stablecoin, **crvUSD**, in mid-2023. It is not a passive stablecoin design. The mechanism underneath it—the **LLAMMA (Lending-Liquidating AMM Algorithm)**—is the key architectural departure from protocols like Aave or Compound.

Traditional lending protocols rely on a hard liquidation price: when collateral value drops below a threshold, external keepers are incentivized to liquidate the position, often causing abrupt losses for borrowers and bad-debt risk for the protocol. LLAMMA replaces this with a soft, continuous rebalancing mechanism. A borrower's collateral is placed into bands—price ranges—within an AMM. As the collateral price falls, the LLAMMA gradually converts it into crvUSD; if the price recovers, crvUSD converts back into collateral. The borrower experiences a series of small partial losses rather than one catastrophic liquidation event. In Curve's terminology, the collateral "self-hedges" as it approaches risk.

This design also means external arbitrageurs continuously interact with the LLAMMA pool, keeping the mechanism active rather than dormant between liquidation events. The tradeoff is that active borrowers in soft liquidation accrue incremental losses even if the position eventually recovers—making LLAMMA well-suited for short-duration borrowing or positions where the borrower monitors actively.

Curve earns fees from crvUSD minting and from the LLAMMA pool activity itself. Those fees flow in part to veCRV holders, tying the stablecoin's success to the governance flywheel.

:::newscard|242099

## LlamaLend: Isolated Lending Markets Beyond crvUSD

**LlamaLend** (also called Curve Lend) extended the LLAMMA architecture into a general-purpose isolated lending market system. In early configurations, markets were primarily crvUSD-denominated—borrowers posted collateral to borrow crvUSD. The system's isolation prevents contagion: a bad market affects only its own pool, not the protocol at large.

**LlamaLend v2**, launched first on Optimism in June 2026 with a 250,000 OP token grant from the Optimism Foundation, significantly broadened the scope. The upgrade allows lending and borrowing in assets beyond crvUSD—the first live markets include ETH/wstETH, wstETH/USDC, and WBTC/USDC pairs. More significantly, v2 allows **Curve LP tokens to be used as collateral**, enabling liquidity providers to borrow funds against their market-making positions rather than withdrawing them. This compresses the opportunity cost of providing liquidity on Curve itself.

The v2 deployment also introduced **LlamaRisk** as an independent risk committee evaluating collateral assets and market lifecycle decisions. Mainnet deployment on Ethereum is planned for the second half of 2026. In parallel, Tangent, a newer protocol, recently launched with 2.5 million USG borrow capacity spread across 12 Curve pool-backed markets—a sign that third parties are building lending infrastructure directly on top of Curve's pool architecture.

That risk arrangement is now in transition. LlamaRisk concluded its Curve engagement on June 30, 2026, and the DAO responded with a public [call for proposals](https://gov.curve.finance/t/call-for-proposals-curve-risk-assessment-and-market-monitoring/11106) for a successor covering crvUSD mint markets and LlamaLend's isolated markets. The mandate on offer is advisory: the selected team would supply analysis, monitoring, and parameter recommendations — including triaging LlamaRisk's handoff materials for what to reuse or rebuild — while decisions and execution stay with the DAO and eDAO. Prospective providers have already responded; as of late July 2026, no successor had been chosen.

A recent academic-style [paper from Curve researchers](https://news.curve.finance/) challenged a long-standing concern: the claim that Loss versus Rebalancing (LvR)—the cost arbitrageurs impose on passive LPs—is a structural drag on LP profitability. The paper derives a stochastic differential equation linking volatility and fees to arbitrage volume, providing a cleaner framework for understanding when LP positions are actually profitable. If confirmed by peer review, the result strengthens the case that Curve's fee structures can be tuned to compensate LPs fairly, which has implications for the protocol's forthcoming dynamic-fee work.

## YieldBasis: Leveraging crvUSD for Bitcoin Liquidity

**YieldBasis**, a newer protocol founded by Egorov and incubated under the Curve ecosystem, takes a different angle. It issues **ybBTC** as a claim on a 2×-leveraged BTC/crvUSD Curve LP position. The mechanics: depositors' BTC is looped against crvUSD borrowing to maintain a levered LP position, capturing amplified fees in exchange for increased exposure to the BTC/crvUSD price relationship.

The [Curve DAO approved](https://intellectia.ai/news/crypto/curve-dao-greenlights-yield-basis-protocol-as-staged-rollout-commences) a staged rollout of the HybridVault infrastructure, which migrated factory ownership to support scaling YieldBasis TVL while also acting as a stability mechanism for the crvUSD peg—if the BTC/crvUSD LP holds more crvUSD during drawdowns, it helps absorb peg pressure. YieldBasis expanded to an Ethereum liquidity pool in January 2026 and is preparing to launch v3 pools as Curve's underlying infrastructure upgrades.

The protocol represents a broader pattern: Curve's AMM primitives being composed into yield-bearing products that wouldn't function without both the StableSwap liquidity layer and crvUSD's mint-and-borrow mechanism underneath.

## The DAO and Governance in Practice

Curve's **DAO** is not a rubber-stamp body. Vote outcomes have meaningfully shaped the protocol's risk posture and allocation of resources, and the governance infrastructure is active enough that contested proposals regularly draw substantive debate.

Recent examples illustrate the range: the DAO opened a vote to allocate 5 million CRV via a veFunder gauge to compensate borrowers harmed by an sDOLA inflation attack in a third-party protocol that had integrated with Curve markets—an instance of using governance to address ecosystem contagion. Separately, the DAO debated a LlamaLend gauge for a SQUID recovery pool on Fraxtal, surfacing questions about how broadly the DAO should extend its incentive weight beyond core infrastructure. In June 2025, the DAO voted for the first time to direct 10% of all protocol revenue into a dedicated treasury rather than distributing everything to veCRV holders immediately, establishing a development reserve.

The development roadmap is partly funded through a proposed 17.45 million CRV grant to Swiss Stake AG, the entity behind Curve's core development team. This structure—a for-profit entity funded by DAO allocation—is increasingly common in DeFi but remains a point of governance scrutiny given the concentration of expertise and development capacity it implies.

## Ecosystem Liquidity Dynamics

Curve pools function as critical DeFi infrastructure. When liquidity in a given pool falls—due to incentive changes, competitive pressure, or protocol-specific events—the downstream effects ripple through any protocol that routes through or benchmarks against that pool.

The MIM/Spell ecosystem's recent experience illustrates this. After unexpected withdrawals disrupted MIM liquidity on Curve, the Spell DAO deployed 70 million SPELL tokens to reincentivize the MIM-2Pool and seeded a new Curve pool with $100,000 of mixed stablecoins (MIM, USDT, USDC) as a liquidity floor. This kind of remediation—using token incentives to attract Curve LP deposits—remains the dominant lever protocols pull when their Curve position deteriorates.

FXSwap, an emerging AMM design, has proposed structural solutions to what it characterizes as LP incentive misalignment, partially inspired by Curve's LLAMMA and innovations from the `f(x)` protocol, suggesting that Curve's architecture continues to set the terms of DeFi AMM debate even as competitors iterate on it.

Curve's weekly yield-and-metrics recaps (published regularly for weeks 16 through 22 of 2026) have shown sustained activity across its pools, with stablecoin yields and CRV reward boosts continuing to attract significant liquidity from major DeFi participants.

## Security Track Record and Posture

Curve's security history has been consequential. In August 2023, a [Vyper compiler bug](https://coinbureau.com/review/curve-finance-crv) allowed reentrant attacks that drained approximately $70 million from several Curve pools, triggering a prolonged recovery process and a high-profile personal liquidation crisis for Egorov, who had borrowed heavily against CRV collateral. Much of the drained funds were eventually returned by white-hat actors.

The incident prompted Curve to invest heavily in formal verification and audit processes. More recently, an AI security tool flagged a critical vulnerability in Curve's latest AMM design before any funds were at risk—a case study in how AI-assisted auditing is increasingly complementing traditional security reviews.

Egorov has publicly called for industry-wide DeFi security standards following separate hacks on Aave and rsETH, urging the Ethereum and Solana Foundations to take a coordinating role. Given Curve's technical depth and Egorov's influence, those calls carry weight within the broader ecosystem conversation.

## Outlook

Curve enters the second half of 2026 as a leaner but more architecturally sophisticated protocol than it was at its peak TVL in 2022. The core AMM is mature; the active frontier is LlamaLend v2's expansion to Ethereum mainnet, broader adoption of LP-token collateral, and the scaling of YieldBasis and crvUSD into new liquidity contexts. The veCRV governance model has proven durable, though it rewards long-term lockers in ways that concentrate influence among early accumulators and protocols like Convex.

The clearest near-term signal to watch: whether crvUSD supply grows meaningfully as LlamaLend v2 expands collateral options, and whether YieldBasis can establish ybBTC as a credible yield-bearing Bitcoin wrapper in a market that Lido demonstrated is winnable with the right primitive. Curve's advantage is that both products sit on infrastructure it controls end-to-end—from the AMM to the stablecoin to the lending markets—a vertical integration that few DeFi protocols have achieved.
