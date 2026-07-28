BOLD is the native stablecoin of Liquity V2, a decentralized borrowing protocol on Ethereum that lets users mint a dollar-pegged asset against ETH and liquid staking tokens at borrowing rates they set themselves.

Designed to be censorship-resistant and fully crypto-collateralized, it sits at the center of a growing class of "decentralized stablecoins" that aim to avoid the custodial and regulatory dependencies of fiat-backed coins like USDC.

## What BOLD Is

BOLD is an overcollateralized, ETH-backed stablecoin issued by [Liquity V2](https://www.liquity.org/blog/liquity-v2-is-live), the second-generation version of the Liquity borrowing protocol that originally launched its LUSD stablecoin in 2021. A *stablecoin* is a crypto token engineered to hold a stable value—here, roughly one US dollar. Unlike fiat-backed stablecoins that hold cash and Treasury bills in bank accounts, BOLD is minted only when a user locks crypto collateral into a smart contract, making it a fully on-chain, "crypto-backed" dollar.

Users mint BOLD by opening a *Trove*, a collateralized debt position. They deposit ETH or an approved liquid staking token (LST)—such as Lido's wstETH or Rocket Pool's rETH—and borrow BOLD against it, subject to a minimum collateralization ratio ([Liquity Docs](https://docs.liquity.org/v2-faq/borrowing-and-liquidations)). The collateral remains the borrower's; BOLD is destroyed (burned) when the loan is repaid. Because every BOLD in circulation is backed by more than a dollar of volatile crypto collateral, the system depends on liquidations and redemptions to stay solvent and on peg.

The protocol describes BOLD as "the Ethereum Dollar," emphasizing that it is native to Ethereum, governance-minimal, and not reliant on any company or off-chain reserve.

## The User-Set Interest Rate Model

The defining innovation of Liquity V2—and the mechanism most relevant to understanding BOLD—is that **borrowers choose their own interest rate**. In most lending protocols, rates are set algorithmically by utilization curves or by governance. In Liquity V2, each borrower picks the annual rate they are willing to pay on their debt when they open a Trove, and can adjust it later ([Liquity blog](https://www.liquity.org/blog/liquity-v2-why-user-set-interest-rates)).

This is not merely a pricing choice; it is the core of BOLD's peg-stabilization mechanism. The rate a borrower sets determines their *redemption risk*. Redemptions are the process by which any holder can swap BOLD back for $1 of underlying collateral directly from the protocol. When a redemption occurs, it targets the Troves paying the **lowest interest rates first**, repaying their debt and removing their collateral in exchange. A borrower who sets a very low rate saves on interest but is first in line to have their position partially closed if redemptions hit.

That trade-off creates an automatic feedback loop around the $1 peg ([Liquity Docs](https://docs.liquity.org/v2-faq/bold-and-earn)):

- When BOLD trades **above $1**, redemption pressure is low, so borrowers tend to lower their rates. Cheaper borrowing encourages more minting, increasing BOLD supply and pushing the price back toward $1.
- When BOLD trades **below $1**, redemptions become profitable, raising the risk of being redeemed. Borrowers respond by raising their rates to move down the redemption queue. Higher rates make borrowing less attractive (slowing new supply) while increasing the yield available to BOLD holders, lifting demand and the price.

In effect, a decentralized market of borrowers continuously prices the cost of keeping BOLD on peg, replacing a single governance-controlled rate with a competitive, self-balancing system.

## Yield, the Stability Pool, and Revenue Routing

BOLD is also a yield-bearing asset, and that yield comes from real protocol revenue rather than token emissions. All interest paid by borrowers is collected and redistributed, with Liquity V2 directing **100% of protocol revenue to users** ([Liquity](https://www.liquity.org/blog/liquity-v2-bold-stability-pool-opportunities)). Newsroom coverage has cited BOLD yields in the range of roughly 7–10% APR sourced from these protocol revenues, with the protocol marketing the absence of leverage loops or rehypothecation in its base earning products.

The main place BOLD holders earn is the **Stability Pool**, sometimes branded "Earn." Depositors place BOLD into the pool, which serves as the first line of defense in liquidations: when a Trove falls below its required collateral ratio, its debt is canceled against pooled BOLD and the seized collateral is distributed to depositors, typically at a discount. Stability Pool participants therefore earn a blend of borrowing-interest yield and liquidation gains.

Revenue is split between two venues. The protocol routes the majority share to the Stability Pools and the remainder to incentivize BOLD liquidity on external decentralized exchanges via an "InterestRouter," which funds protocol-incentivized liquidity ([Liquity](https://www.liquity.org/blog/forkonomics-update---august-2025)). Documentation has described this split as 75% to Stability Pools and 25% to liquidity incentives. The design goal is a stablecoin that pays holders without depending on inflationary rewards.

## The Yearn Layer: yBOLD

For users who want passive, optimized yield, [Yearn](https://yearn.fi/) has built a wrapper called **yBOLD**. Rather than requiring a holder to monitor and rebalance across Liquity's multiple Stability Pools (each collateral type has its own), yBOLD automates the process. According to Yearn's release materials, yBOLD auto-compounds liquidation rewards, allocates deposits across Stability Pools, charges zero withdrawal fees, and remains 1:1 redeemable as a composable DeFi primitive. To actually capture yield, holders stake into the `st-yBOLD` form, per Yearn's published documentation.

The arrival of yBOLD illustrates a pattern common to *DeFi* (decentralized finance, the ecosystem of permissionless on-chain financial applications): a base primitive like BOLD quickly accumulates higher-order products built on top of it. That composability adds convenience but also stacks smart-contract risk—an important caveat for anyone weighing yBOLD against holding raw BOLD.

## Adoption and Market Position

Liquity V2 went live on **May 19, 2025**, after a redeployment that followed a five-week audit contest involving hundreds of researchers and multiple re-audits ([Liquity](https://www.liquity.org/blog/liquity-v2-redeployment)). Public data points from the launch period show roughly $17M deposited and about 7.3M BOLD minted on day one, with the token holding near $1.00. By August 2025, Liquity reported V2 reaching around $160M in TVL with a BOLD supply near 43M ([Liquity](https://www.liquity.org/blog/forkonomics-update---august-2025)). Our newsroom independently tracked the protocol crossing $100M in total value locked within three weeks of relaunch, and noted the milestone of BOLD's circulating supply surpassing that of Liquity's older LUSD stablecoin—a symbolic "flippening" of the project's first-generation token.

BOLD has also drawn external validation on the decentralization axis that is its main selling point. The credit-ratings firm Bluechip awarded BOLD an A- rating—reportedly the first decentralized stablecoin to earn one—with perfect 1.0 scores in management, decentralization, and governance. The assessment underscored that BOLD cannot be frozen and has no admin keys, framing the choice between BOLD and centralized coins as a trade-off between *counterparty risk* (the chance an issuer freezes funds or fails) and *smart-contract risk* (the chance code is exploited).

Ecosystem integrations have expanded steadily. Curve Finance launched a BOLD/LUSD pool on its Stableswap NG factory, and BOLD has been featured alongside other decentralized stablecoins—such as fxUSD and crvUSD—in initiatives promoting the diversification of stablecoin liquidity away from custodial assets. Asymmetry's DegenBoxAF teased a "DeFi Stable Avengers" liquidity pool combining USDaf, USDC, BOLD, and fxUSD. On the payments side, BOLD has been listed for crypto merchant settlement through services like Yodl, though such consumer-facing rails carry their own fees, KYC requirements, and uneven regional availability.

## Relationship to Bitcoin, ETH, and Arbitrum

BOLD's collateral base is firmly *ETH*-centric: Ether and ETH liquid staking tokens are what back the supply, tying BOLD's risk profile to the price and staking economics of Ethereum rather than to *Bitcoin*. That distinction matters in a market where corporate treasuries—Metaplanet's accumulation of more than 25,000 BTC is a prominent example—are concentrating balance sheets in Bitcoin as a reserve asset. BOLD plays a different role: it is a spending and earning instrument for on-chain ETH holders, not a long-term store-of-value bet.

On distribution, Liquity has historically pursued a multi-chain strategy through "friendly forks" rather than a single canonical deployment everywhere. The protocol's "forkonomics" model encourages independent teams to redeploy the codebase—including on Layer 2 networks such as *Arbitrum*—while routing a portion of fork revenue back to the LQTY governance token. Users should always confirm whether they are interacting with the canonical Ethereum mainnet BOLD or a fork-issued variant on another chain, as risk parameters and backing can differ.

## Risks and Trade-offs

BOLD's design removes some risks and introduces others. Because there are no admin keys and the contracts are immutable, governance cannot rescue users through emergency intervention—the resilience that earns top decentralization marks also means there is no off-switch if something goes wrong. The May 2025 launch itself surfaced a Stability Pool bug that prompted the team to advise closing positions; it was resolved without reported user losses, but it is a reminder that immutable code raises the stakes on correctness.

Other considerations include:

- **Volatility of collateral**: Because BOLD is backed by ETH and LSTs, sharp drawdowns can trigger liquidations. Stability Pool depositors absorb that collateral, which is the source of their yield but also exposes them to receiving devalued assets in fast markets.
- **Redemption exposure**: Borrowers who underprice their interest rate risk having Troves redeemed against them, effectively forcing a sale of collateral at $1-equivalent.
- **Peg durability under stress**: The user-set-rate feedback loop is elegant in theory but relatively young in practice; its behavior in a severe, prolonged depeg event is still being established by live market history.
- **Composability stacking**: Products like yBOLD and third-party pools add convenience and yield but layer additional contract dependencies.

## Outlook

BOLD enters a crowded but shifting stablecoin landscape with a clear thesis: a dollar that no one can freeze, backed only by crypto and stabilized by a market of borrowers rather than a corporate balance sheet. Early traction—nine-figure TVL within months of relaunch, an A- decentralization rating, and a fast-growing layer of integrations from Curve to Yearn—suggests genuine product-market fit among DeFi-native users seeking yield without custodial exposure. The key questions ahead are whether the user-set-rate peg mechanism holds up through a full market cycle, how broadly BOLD propagates across Layer 2s and forks without fragmenting liquidity, and whether decentralized stablecoins can collectively claim meaningful share from incumbents. For now, BOLD stands as one of the more closely watched experiments in making a credibly neutral on-chain dollar.
