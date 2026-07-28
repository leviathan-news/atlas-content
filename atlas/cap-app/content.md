Cap is a stablecoin and covered-credit protocol built around two dollar products: **cUSD**, a reserve-backed stablecoin, and **stcUSD**, the yield-bearing token received by staking cUSD. A third token, **CAP**, is the protocol's governance token. Keeping those three assets separate is the first requirement for understanding Cap.

The protocol combines a reserve vault with a lending system. Users deposit approved dollar-denominated assets to mint cUSD. Some reserve capital can earn returns in external strategies or be borrowed by approved borrowers. Those borrowers need collateral delegated by restakers or delegators—the economic underwriters—before they can borrow. If a borrower's position becomes unhealthy, the protocol can liquidate the delegated collateral to repay debt.

That structure is more specific than a generic private-credit marketplace. It does not mean every dollar sits idle in a vault, every borrower is secured by its own assets, or every holder is insulated from loss. Cap's contracts, reserve assets, borrowers, underwriters, oracles, external integrations, and administrative controls each create a different risk surface.

## cUSD: Minting, Burning, and Redeeming

Cap's [current introduction](https://docs.cap.app/) describes cUSD as a dollar-denominated stablecoin issued on Ethereum. As checked on July 13, 2026, its documentation listed USDC, USDT, pyUSD, BUIDL, and BENJI as examples of approved reserve assets. The whitelist is mutable, so the documentation and [published contract addresses](https://docs.cap.app/developers/addresses) are better sources than a frozen list in launch copy.

The [cUSD mechanics](https://docs.cap.app/protocol-overview/cusd-mechanics) distinguish three operations. Minting deposits an approved reserve asset and creates cUSD at oracle value, subject to the protocol's fee and validation rules. Burning exchanges cUSD for a selected underlying asset. Redeeming exchanges cUSD for a proportional basket of the reserve assets.

That proportional redemption matters during a reserve-asset depeg. Instead of allowing early redeemers to take only the strongest asset and leave later users with the impaired one, the design distributes the basket proportionally. The loss is socialized across cUSD rather than erased. Dynamic burn fees are another balancing mechanism; they are not a guarantee that every reserve asset remains worth one dollar.

The [Vault documentation](https://docs.cap.app/concepts/vault) calls this module the protocol's liquidity backbone. It stores reserve assets, issues and redeems cUSD, tracks borrowing, and can deploy idle capital through fractional-reserve strategies. Cap's [cUSD mechanics](https://docs.cap.app/protocol-overview/cusd-mechanics) describes money-market-fund revenue sharing and Aave, while its [stcUSD mechanics](https://docs.cap.app/protocol-overview/stcusd-mechanics) also names Morpho as an example external integration. That adds yield, but it also adds exposure to those external assets and protocols.

## stcUSD: The Yield-Bearing Layer

A cUSD holder can stake cUSD to receive stcUSD. According to Cap's [stcUSD mechanics](https://docs.cap.app/protocol-overview/stcusd-mechanics), rewards can come from idle-reserve strategies and interest paid by approved borrowers. stcUSD therefore represents the reward-accruing layer; cUSD remains the spendable and redeemable stablecoin.

Cap sets a hurdle rate for reserve assets. A borrower needs a strategy expected to clear that rate, plus a negotiated rate paid to the underwriter or delegator whose collateral supports the loan. The borrower keeps any return above its borrowing and underwriting costs. These rates and utilization conditions are dynamic, so an evergreen explainer should describe the mechanism without promising a fixed annual yield.

The protocol describes stcUSD principal as covered against borrower default through delegated collateral and slashing. That is a design objective, not a risk-free promise. Coverage can be affected by the value and liquidity of delegated collateral, execution of liquidation, smart-contract behavior, oracle data, reserve-asset losses, and the solvency or performance of external systems.

## Borrowers, Underwriters, and Delegated Collateral

Cap's [actor model](https://docs.cap.app/protocol-overview/protocol-actors) distinguishes cUSD holders, stcUSD holders, the borrowing side, restakers, and liquidators. This guide refers to the borrowing-side participant as the **borrower**. Its partnership material also uses **underwriter** for the economic role played by a restaker or delegator that puts collateral at risk behind a borrower. Borrowers, underwriters, depositors, and protocol-governance participants remain distinct roles.

Borrowers must be approved. The [Borrow documentation](https://docs.cap.app/concepts/lender/borrow) says a borrower must be whitelisted, unpaused, within borrowing limits, and supported by sufficient delegated collateral and a healthy position. Borrowed assets leave the Vault, while non-transferable debt tokens track principal and accruing interest.

This is an overcollateralized protocol relationship even when the borrower uses the capital for an offchain or institutionally managed credit strategy. Cap's [Lender documentation](https://docs.cap.app/concepts/lender) expresses borrowing capacity through loan-to-value and health-factor rules based on slashable delegation. The collateral belongs to the underwriter or delegator and stands behind the borrower's debt; it is not necessarily collateral posted by an end borrower in the underlying credit strategy.

The [Delegation module](https://docs.cap.app/concepts/delegation) connects Cap to shared-security networks. As checked on July 13, 2026, the documentation listed Symbiotic and EigenLayer, describes coverage as isolated by network and by each borrowing participant, and says the protocol initially whitelists borrowers and delegators. Delegators—described as underwriters in Cap's partnership material—negotiate a fixed restaker rate for putting collateral at risk. They must evaluate the borrower because their delegated assets can be slashed.

## Default and Liquidation

When a borrower's health factor falls below the required level, a liquidator can start the process described in Cap's [Liquidation documentation](https://docs.cap.app/concepts/lender/liquidation). The documented flow includes a grace period under ordinary conditions and an emergency path when the position deteriorates further. A liquidator repays some of the outstanding reserve-asset debt and receives delegated collateral plus a time-dependent bonus.

The objective is to restore the borrower's health and return reserve assets to the Vault. It is not accurate to describe Cap as simply making undercollateralized loans and hoping a third party pays. The enforceable onchain backstop is delegated collateral. It is equally inaccurate to call that backstop certain: a fast collateral decline, weak auction liquidity, delayed execution, oracle failure, or shared-security failure can reduce what liquidation recovers.

## Current Institutional Examples

Cap's own [Q1 2026 update](https://www.cap.app/blog/cap-investor-update-q1-2026) reported a $100 million revolving credit facility for Susquehanna Crypto and said 60% of its USD reserves were lent at the end of the quarter. Those are dated, self-reported Q1 figures, not live totals and not a promise about future utilization or credit performance.

A separate [March 2026 collaboration announcement](https://www.cap.app/blog/institutional-restaking-partnership-real-yield-arrives-in-defi) identifies a bounded set of roles: EtherFi as underwriter and delegator, Symbiotic as shared-security infrastructure, M11 Credit (Maven 11) as borrower, and FalconX as loan originator and yield generator. That example helps explain the architecture, but it should not be generalized into a claim that every Cap loan uses those firms or the same legal and credit structure.

## CAP Governance and Two Different Auctions

CAP is distinct from cUSD and stcUSD. The [Cap Tokens documentation](https://docs.cap.app/cap-tokens) assigns CAP governance over protocol parameters, collateral management, borrower onboarding, and protocol fees. The same page labels protocol-integration staking mechanisms for borrowers, delegators, and depositors as **TBD**. An explainer should not present those unimplemented integrations as current utility.

Uniswap Labs wrote on June 24, 2026 that Cap had already used a [Continuous Clearing Auction](https://blog.uniswap.org/launch-auctions-from-uniswap-web-app) for token distribution. By June 24, 2026, Cap's launch auction was a past event, not a live upcoming sale. It is also separate from Cap's internal [Fee Auction](https://docs.cap.app/concepts/fee-auction), which sells accumulated protocol-fee assets for cUSD as part of the reward-distribution machinery. Sharing the word auction does not make the two mechanisms interchangeable.

## Controls and Risk Boundaries

Cap is not an immutable, administration-free system. Its [Access Controls](https://docs.cap.app/concepts/access-controls) page describes function-level permissions managed by an administrator listed as Cap's multisig when checked on July 13, 2026. The Vault documentation includes asset-level and protocol-level pauses, while borrower and delegator participation begins with whitelisting. These controls may help respond to incidents, but they also create governance, key-management, and intervention risk.

Price and rate calculations depend on the [Oracle module](https://docs.cap.app/concepts/oracles). As checked on July 13, 2026, the documentation named RedStone for reserve assets, Chainlink for some delegation assets, and protocol adapters for cUSD, stcUSD, and rate calculations. Stale or incorrect data can affect minting, borrowing capacity, health factors, and liquidation.

Cap's own [risk disclosure](https://docs.cap.app/risks) identifies smart-contract, reserve-collateral, delegation-collateral, shared-security, bridge, oracle, idle-asset, depeg, redemption, and slashing risks. Those categories are the right starting point.

Independent [Federal Reserve research on private credit](https://www.federalreserve.gov/econres/notes/feds-notes/private-credit-characteristics-and-risks-20240223.html) describes generic risks including illiquidity, limited price discovery, and low recovery in default. Those observations are not measurements of Cap, but delegated collateral does not erase the performance risk of either the approved borrower or its underlying loans.

Cap's [Platform Terms of Use](https://docs.cap.app/resources/terms-and-conditions/platform-terms-of-use), last revised March 26, 2025, identify Covered Agents S.A. in Panama and provide for individual arbitration under Panama law. Those public platform terms do not disclose the separate legal agreements governing institutional facilities or underwriter recourse.

The practical questions remain concrete:

- Can reserve assets be redeemed, frozen, or impaired?
- How much reserve liquidity is immediately available rather than borrowed or deployed?
- Is delegated collateral liquid enough to cover debt during stress?
- Are borrower and underwriter exposures concentrated?
- Can oracle, bridge, external-protocol, or multisig failures compound one another?
- What legal recourse exists outside the contracts, and in which jurisdiction?

Cap's architecture makes reserve composition, debt, delegated collateral, and liquidation rules more observable than a wholly offchain credit arrangement. It does not make credit, liquidity, governance, or implementation risk disappear. The durable Atlas view is therefore neither that Cap is an unsecured private-credit pool nor that stcUSD is guaranteed yield. It is a reserve-backed stablecoin system that uses approved borrowers and slashable underwriter collateral to add a covered-credit yield layer—and whose protections are only as strong as the assets, institutions, contracts, controls, and liquidation paths beneath them.
