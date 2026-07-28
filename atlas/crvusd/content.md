Curve Finance's native stablecoin, crvUSD, is a crypto-collateralized dollar soft-peg built around a novel automated market maker that converts collateral to stablecoin—and back again—rather than hard-liquidating borrowers in a single transaction.

---

## What crvUSD Is and Why It Works Differently

Most collateralized stablecoins borrow a framework pioneered by MakerDAO: borrowers lock up assets, maintain a minimum collateralization ratio, and face an abrupt liquidation if that ratio slips. The liquidation event is binary—assets sell in a single step, often at a disadvantage to the borrower.

crvUSD, launched by Curve Finance in May 2023 on Ethereum, abandons this model in favor of a continuous, AMM-mediated process. The core insight is that Curve already runs the deepest stablecoin liquidity in DeFi; crvUSD turns that liquidity infrastructure into the loan's safety mechanism rather than relying on external liquidation bots acting at discrete price thresholds. The result is a stablecoin whose stability and borrowing mechanics are inseparable from the exchange layer that underlies most of DeFi's dollar liquidity.

## LLAMMA: The Soft-Liquidation Engine

The critical building block is the Lending-Liquidating AMM Algorithm, or **LLAMMA**—a specialized AMM that holds a borrower's collateral across a series of discrete price ranges called "bands." When the collateral's market price falls into an active band, LLAMMA gradually sells a portion of that collateral into crvUSD, lowering the loan's risk exposure progressively rather than all at once. If the collateral price recovers and rises back through the bands, LLAMMA converts the crvUSD back into collateral, partially restoring the original position.

This behavior—commonly called **soft liquidation**—means a borrower in distress is not necessarily wiped out. Instead, they may endure a period of continuous small losses as collateral oscillates through the bands; sustained downward price movement eventually reaches a hard liquidation only after the position's health score deteriorates past a critical floor. The tradeoff is that prolonged sideways price action within the bands incurs slow, frictional losses even when the collateral price ultimately recovers.

[Curve's own documentation on loan concepts](https://resources.curve.finance/crvusd/loan-concepts/) and [LlamaRisk's lending primer](https://research.llamarisk.com/research/curve-lending) provide detailed walkthroughs of the band mechanics for readers who want to model specific positions.

## PegKeepers: Algorithmic Peg Defense

Maintaining the $1.00 peg is handled by a set of smart contracts called **PegKeepers** (more recently branded as the Peg Stabilization Reserve, or PSR). Each PegKeeper is paired with a specific Curve stablecoin pool:

- When crvUSD trades *above* $1, the PegKeeper mints and deposits crvUSD into the pool, increasing supply and pushing the price back down.
- When crvUSD trades *below* $1, the PegKeeper withdraws and burns its deposited crvUSD, reducing supply and supporting the price.

The PegKeeper basket has expanded over time. Aave's GHO stablecoin was added to the basket in 2025 after LlamaRisk cleared a review of peg stability risks, with a $3 million debt ceiling. Frax Finance's frxUSD is also paired in PegKeeper pools, and as of June 2026, those frxUSD PegKeeper pools are on track for a record monthly volume—evidence that the mechanism generates meaningful arbitrage throughput and that multiple actors now anchor crvUSD's peg from different directions. PegKeeper arbitrage activity has generated thousands of dollars per cycle in realized revenue, even during quiet market periods.

The PSR architecture means crvUSD's peg is not just a function of collateral ratios; it is continuously arbitraged through pool balances, making it responsive to market conditions in real time.

## Minting and Supported Collateral

Borrowers mint crvUSD by depositing collateral into a LLAMMA vault on Ethereum. Supported collateral types as of mid-2026 include:

- **WETH / ETH** – the primary collateral by volume
- **wstETH** – Lido's liquid-staked Ethereum
- **sfrxETH** – Frax's staked ETH (v2, with v1 being phased out)
- **WBTC** – wrapped Bitcoin
- **tBTC** – trustless wrapped Bitcoin via Threshold Network

Each collateral type has its own LLAMMA market with independent parameters—different loan-to-value ceilings, band counts, and fee configurations. Yield-bearing assets like wstETH and sfrxETH carry a 2% premium on the base borrow rate to account for their accruing yield; WBTC and ETH markets price closer to the base rate. Average borrow rates across markets in early 2026 ranged roughly from 4% to 5%, following a governance vote that cut rates from a prior range of approximately 11.5% to bring them into line with broader DeFi lending markets like Aave and Compound.

## Borrow Rates and Monetary Policy

crvUSD's borrow rate is not fixed; it is set by an on-chain monetary policy contract that responds to how much crvUSD the PegKeepers are currently holding. When PegKeeper balances are high—meaning crvUSD supply already exceeds demand—the monetary policy raises rates to discourage new minting and reduce circulating supply. When PegKeeper balances are low, rates fall to attract borrowers.

Curve's engineering team published a detailed investigation in 2026 exploring EMA-smoothing of the "debt fraction" variable the monetary policy uses—a change designed to prevent borrow rates from spiking sharply during brief moments of pool imbalance. The goal is a rate surface that is self-correcting but does not punish borrowers with sudden, large rate jumps during volatility. A separate governance-approved change smoothed the rate curve further by adjusting the formula's shape, reducing the biggest source of rate volatility while preserving the self-correcting mechanism. These updates reflect an ongoing engineering effort to make crvUSD competitive with centralized stablecoins on predictability of borrowing costs.

## scrvUSD: The Savings Layer

Borrowers pay interest; that interest goes somewhere. **Savings crvUSD (scrvUSD)** is the mechanism that distributes a portion of protocol revenue to passive crvUSD holders. Users deposit crvUSD into the scrvUSD vault and receive a yield-bearing token that appreciates in value as fees accumulate—the same model as sDAI for MakerDAO's DAI.

Curve built scrvUSD in partnership with **Yearn Finance**, using Yearn's V3 Vault architecture. The DAO controls what fraction of crvUSD borrowing revenue flows into scrvUSD, currently bounded between a 5% minimum and a 50% maximum. Since its launch, scrvUSD has delivered approximately 3.8% total yield over a six-month window to depositors, though the actual rate fluctuates with borrowing demand. Governance has revisited the fee-share allocation multiple times—including a vote to increase the maximum fee share during periods when peg stress required additional incentives—highlighting the tension between rewarding savers and defending the peg.

Stake DAO and Morpho have both integrated scrvUSD and related LP tokens as curated vault collateral, extending the composability of the savings wrapper into third-party yield strategies. Yodl Pay, a mobile payments interface, demonstrated real-world crvUSD spending at a point-of-sale in 2025, quoting a 4% FX advantage over conventional payment rails—an early signal of crvUSD in consumer-facing contexts.

## LlamaLend: Extending the Stablecoin into Isolated Markets

**LlamaLend** (now at v2) is Curve's generalized lending market, separate from but complementary to the core crvUSD minting system. Where the minting markets create new crvUSD from collateral, LlamaLend enables borrowing of *any* token using LP tokens and other assets as collateral—including Curve LP positions themselves.

In June 2026, Curve deployed LlamaLend v2 on **Optimism** with a 250,000 OP grant, launching three isolated markets: ETH/wstETH, wstETH/USDC, and WBTC/USDC. The Optimism deployment is notable for accepting LP tokens as collateral—a step that brings idle Curve liquidity into productive use and deepens the connection between Curve's AMM and its lending layer. This expansion reflects Curve's strategy of positioning itself as not just a stablecoin DEX but a comprehensive credit layer for Ethereum-ecosystem assets.

## Cross-Chain Expansion: FastBridge and L2s

One structural friction for any Ethereum-native stablecoin is the withdrawal delay imposed by optimistic rollup bridges—typically seven days for assets leaving networks like Optimism, Base, or Arbitrum. Curve addressed this with **FastBridge**, a LayerZero-powered messaging relay that reduces crvUSD L2-to-Ethereum transfer times to approximately 15 minutes. FastBridge debuted in early 2026 and supports transfers from Arbitrum, Optimism, Base, and Frax's Fraxtal network.

650,000 crvUSD was minted specifically to capitalize the FastBridge liquidity reserve. The mechanism works by having a counterparty on Ethereum advance the crvUSD immediately while the L2 burn is verified via cross-chain message; the counterparty earns a fee for fronting liquidity. For traders and protocols managing positions across chains, this removes a significant usability gap without relying on third-party bridges that introduce additional smart contract risk.

## Yield Basis and the crvUSD Growth Flywheel

**Yield Basis** is a protocol designed to let concentrated liquidity providers hedge impermanent loss using crvUSD. The mechanism creates pools that pair BTC and ETH exposure with crvUSD stability, allowing LPs to capture volatility-driven fee income while keeping stablecoin collateral at the base. In late 2025, the Curve DAO approved expanding YieldBasis's crvUSD credit line from $60 million to $300 million—an expansion that added hundreds of millions in TVL to the Curve ecosystem in a single governance action.

In 2026, Yield Basis is rolling out **Hybrid Vaults** that introduce per-LP caps, enabling the protocol to scale participation while maintaining crvUSD peg stability. Curve founder Michael Egorov published a forum post laying out how scaling Yield Basis and crvUSD simultaneously creates a reinforcing loop: more LP activity generates more fees, which raises scrvUSD yields, which attracts more crvUSD depositors, which deepens PegKeeper liquidity, which stabilizes the peg for the next generation of borrowers.

## Risk Management: LlamaRisk

Curve extended its partnership with **LlamaRisk**—an independent DeFi risk research firm—through April 2027. LlamaRisk handles ongoing monitoring of crvUSD parameters, reviews proposals to add new collateral types or expand PegKeeper baskets, and publishes public research reports on peg events and market conditions.

When the crvUSD peg sustained an "unusually severe" multi-week wobble in late 2024 (including an upward depeg incident in June 2024 documented in a [LlamaRisk incident report](https://research.llamarisk.com/research/crvusd-incident-report-20240612)), LlamaRisk published a detailed post-mortem and a review of remediation actions. Having an independent risk layer with a formal mandate and published research record is a meaningful differentiator from stablecoin projects that rely entirely on internal teams or informal community monitoring. Inverse Finance also weighed in with concerns about peg stability in discussions around sunsetting certain crvUSD LP markets on their FiRM platform—illustrating that crvUSD's integration across DeFi means its peg health is a concern for third-party protocols as well.

## Peg Stability: The Track Record

crvUSD has maintained a general proximity to $1.00 since launch, but not without stress. Bitcoin and Ethereum price crashes place acute pressure on the LLAMMA vaults holding these assets as collateral; when prices fall sharply, the PegKeepers absorb selling pressure from soft-liquidation mechanics, and crvUSD can trade below peg for extended periods. A notable multi-week depeg in 2024 tested the protocol's response mechanisms and led to direct governance interventions—rate adjustments, PegKeeper rebalancing, and parameter changes.

The borrow rate volatility has also been a known friction point: rates that could spike to double digits during market stress deterred borrowers and amplified peg instability. The EMA smoothing changes and the June 2026 governance vote to cut rates from roughly 11.5% toward 5% represent a deliberate effort to smooth the feedback loop between rate policy and peg health.

## Outlook

crvUSD enters the second half of 2026 with a maturing infrastructure stack: smoothed monetary policy, a savings wrapper integrated with Yearn, a generalized lending market expanding on L2s with LP-token collateral, a fast cross-chain bridge, and an independent risk partner under a multi-year mandate. The Yield Basis Hybrid Vault rollout and the ongoing strength of frxUSD PegKeeper volumes suggest the crvUSD liquidity layer is deepening, not stagnating.

The unresolved challenges are familiar to the decentralized stablecoin category: supply remains small relative to fiat-backed peers like USDC, peg stability under extreme market volatility has required active intervention, and reliance on ETH and BTC collateral means crvUSD's health is exposed to the same cycles it exists to hedge against. Whether the flywheel of borrower demand → fee revenue → scrvUSD yield → depositor growth can sustain itself through a sustained bear market is the central question for the protocol's next phase.

---
