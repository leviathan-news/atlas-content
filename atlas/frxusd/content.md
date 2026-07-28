frxUSD is a fiat-redeemable, fully reserve-backed stablecoin issued by Frax Finance and designed as the protocol's default dollar for decentralized finance, with reserves held largely in tokenized U.S. Treasury funds such as BlackRock's BUIDL and Superstate's USTB. It is the rebranded successor to Frax's original FRAX stablecoin, repositioned around institutional-grade collateral and direct 1:1 redemption ([Frax](https://frax.com/frxUSD), [PR Newswire](https://www.prnewswire.com/news-releases/frax-launches-frxusd-stablecoin-backed-by-the-blackrocks-usd-institutional-digital-liquidity-fund-buidl-tokenized-by-securitize-302341497.html)).

## What frxUSD Is

A stablecoin is a crypto token engineered to hold a constant value, almost always one U.S. dollar, so that it can serve as a medium of exchange and a unit of account on-chain without the price swings of assets like bitcoin. frxUSD belongs to the fiat-collateralized category: every unit is intended to be backed by an equivalent dollar of cash-equivalent reserves rather than by an algorithm or by over-collateralized crypto.

Frax introduced frxUSD in early 2025 as an evolution of FRAX, the protocol's flagship stablecoin that had existed since 2020 ([DEXTools](https://www.dextools.io/tutorials/what-is-frax-finance-fxs-frax-stablecoin-defi-guide-2026)). The redesign moved away from the partially algorithmic mechanics of the original FRAX toward a model centered on tokenized real-world assets and direct redeemability. According to Frax's own disclosures, tokenized Treasury funds—principally Superstate's USTB and BlackRock's BUIDL—make up more than 90% of frxUSD's backing ([Frax](https://frax.com/frxUSD)).

The mechanism relies on what Frax calls "enshrined custodians": governance-approved real-world entities permitted to mint and burn frxUSD one-for-one against $1.00 of cash-equivalent reserves they hold. Because those reserves sit in bankruptcy-remote, regulated vehicles managed by firms such as BlackRock, Superstate, Securitize, Agora, and WisdomTree, holders can in principle redeem frxUSD 1:1 for dollars at a partner institution ([CoinMarketCap](https://coinmarketcap.com/cmc-ai/frax-usd/what-is/)). As of mid-2026 the token traded within a fraction of a cent of its $1 peg, with a market capitalization in the low hundreds of millions ([CoinMarketCap](https://coinmarketcap.com/currencies/frax-usd/)).

## The Savings Layer: sfrxUSD

frxUSD itself is a non-yield-bearing dollar; the yield lives in a companion token, sfrxUSD. Users deposit frxUSD into a savings vault and receive sfrxUSD, which accrues value as interest is earned. The vault's return is sourced from the underlying institutional Treasury funds plus a rotating set of yield strategies that have included Superstate's USCC, Ethena's USDe, and Sky's sUSDS ([Frax via search](https://frax.com/frxUSD)).

This two-token split—a plain transactional dollar and a separate interest-bearing wrapper—mirrors the structure adopted across much of the stablecoin market and is what allows frxUSD to circulate freely in trading pairs while sfrxUSD compounds in the background. The distinction matters for the integrations described below: lending markets and liquidity pools generally route the transactional frxUSD, while the yield engine sits one layer up in sfrxUSD.

## FRAX, FXS, and the Wider Frax Ecosystem

frxUSD does not exist in isolation. The Frax protocol also runs Fraxtal, an EVM-compatible Layer 2 rollup that batches and compresses transactions before settling to Ethereum, lowering fees for activity denominated in Frax assets ([IQ.wiki](https://iq.wiki/wiki/frax-finance)). Frax positions frxUSD as the native dollar of the Fraxtal economy, and recent newsroom coverage notes that token-launch frameworks on Fraxtal—such as the "Boardwalk" program—route value back to projects in frxUSD as they grow.

The naming around Frax's tokens has shifted over time: the legacy FRAX dollar, the governance token historically known as FXS, and the newer frxUSD/sfrxUSD pair coexist during a transition that Frax has framed as a move toward a unified, RWA-backed digital dollar. For readers, the practical point is that frxUSD is the current dollar product Frax is actively expanding, while older FRAX references describe the system it grew out of.

## frxUSD on Aave: Lending and ReserveLink

Much of frxUSD's 2026 momentum has come through Aave, the largest decentralized lending protocol. When Aave launched its V4 architecture, frxUSD was among a small group of stablecoins included on day one, and a smaller group featured in the protocol's "Bluechip" spoke. It quickly became the single largest deposited asset on Aave V4, reaching roughly $20 million in deposits and helping push total V4 deposits past $110 million ([CoinGecko](https://www.coingecko.com/en/coins/frax-usd)). It also ranked among the most-borrowed stablecoins on the venue, behind USDC and USDT.

That growth has been managed through allocation caps—ceilings on how much frxUSD can be deployed into a given market. Newsroom coverage shows caps on frxUSD deposits in V4 being raised to $30 million, with the borrow rate compressing to around 0.6% APY as supply filled in. Frax governance separately weighed a proposal (FIP-447) to lift the sfrxUSD-strategy allocation into Aave V4 from $20 million to $50 million, subject to market conditions ([HTX](https://www.htx.com/en-in/news/frax-governance-weighs-raising-sfrxusd-aave-v4-allocation-ca-VOFmwiOp/)).

The more structurally novel integration is **frxUSD ReserveLink on Aave**. In conventional stablecoin design, the yield generated by reserves is captured at the issuer level, separate from the applications that create demand for the coin. ReserveLink routes a portion of that reserve yield back to the lending market itself, so Aave depositors share in the return the reserves earn rather than leaving it entirely with the issuer. It is an attempt to close the gap between where stablecoin demand is created and where reserve value accrues—a recurring theme in Frax's messaging that capital efficiency should flow to the protocols and users generating the activity.

This expansion has not been free of scrutiny. Some coverage has flagged that raising caps on a relatively new asset in a freshly launched V4 market carries risk, citing liquidity gaps and the general solvency, depeg, and incident-response questions that attach to any reserve-backed stablecoin under stress. Those critiques are worth keeping in view: caps and conservative deployment are precisely the tools meant to contain such risks, and they are only as good as the monitoring behind them.

## Curve, PegKeepers, and crvUSD

Beyond lending, frxUSD has built out liquidity on Curve, the dominant decentralized exchange for stablecoin trading. A liquidity pool is a smart contract holding two or more tokens that traders swap against; deep pools keep prices stable and slippage low. Curve's PegKeeper system is a stabilization mechanism that mints or burns Curve's own crvUSD stablecoin into designated pools to defend pegs.

According to recent newsroom coverage, June 2026 was on track to be a record month for volume in frxUSD PegKeeper pools, even against a soft bitcoin price, with the crvUSD/frxUSD pool among the leaders alongside Metronome's msUSD. A Llama Risk onboarding review of frxUSD as a PegKeeper asset underscores that this is a vetted integration rather than an ad hoc listing ([Llama Risk](https://research.llamarisk.com/research/pegkeeper-onboarding-frxusd)). The strategic value for Frax is that PegKeeper pools anchor frxUSD inside Curve's liquidity, making it a natural base pair for other stablecoins to route through.

## Onchain FX and Cross-Border Pairs

One of the more distinctive uses emerging around frxUSD is foreign-exchange (FX) liquidity. FX refers to trading one currency for another; bringing it on-chain means letting users swap tokenized versions of, say, dollars and euros directly through liquidity pools. Frax, Curve, and Polygon deployed a suite of six onchain FX pools pairing major non-U.S. stablecoins against frxUSD as the base dollar, positioning frxUSD as the settlement leg for cross-border, stablecoin-denominated payments. The pitch is that as more of the world's currencies move on-chain, a deeply liquid dollar pairing is needed to bridge them—and Frax wants frxUSD to be that pairing.

## Multi-Chain Reach and Interoperability

frxUSD is designed to travel. Frax has reported the asset live across a dozen or more networks, with additional LayerZero-based frxUSD deployments on chains including Solana, Linea, and Sonic ([Frax](https://frax.com/frxUSD)). Recent coverage describes a frxUSD bridge spanning roughly 25 chains with zero bridging fees for users and integrations, and a Base-to-Canton bridge that added frxUSD as a Day 1 asset (circulating there as a Send-bridged variant, frxUSD.B).

Frax has also signaled participation in stablecoin "clearinghouse" efforts aimed at letting different issuers' stablecoins move 1:1 across platforms—an interoperability layer that, if it matures, would reduce the friction of holding any single dollar token. For comparison, USDC, issued by Circle, remains the benchmark for multi-chain reach and institutional acceptance; frxUSD's strategy is less about displacing it outright than about being the default DeFi-native dollar with reserve economics that flow back to integrators.

## Risks and Open Questions

frxUSD's reliance on tokenized Treasury funds is its principal strength and its principal dependency. The backing is only as sound as the custodians and tokenization providers behind BUIDL, USTB, and similar instruments, and redemption guarantees ultimately route through those off-chain entities. Critics have raised solvency, depeg, and incident-response concerns common to any reserve-backed dollar, and the rapid cap increases on Aave V4 have drawn caution about whether liquidity depth keeps pace with deposits. Frax's own positioning—"security is our product"—acknowledges that durable trust, not distribution or incentives, is the binding constraint for a digital dollar meant to be held for years.

Readers evaluating frxUSD should watch three things: the composition and transparency of reserves, the behavior of the peg during volatile periods, and how governance manages caps and yield-strategy exposure across Aave, Curve, and newer venues.

## Outlook

frxUSD has spent 2026 expanding along three fronts at once—lending depth on Aave, liquidity on Curve's PegKeeper and FX pools, and cross-chain reach via bridges and LayerZero. The recurring theme is reserve value flowing back to integrators rather than staying with the issuer, most concretely through ReserveLink on Aave. Whether that model can scale without straining liquidity or peg stability is the open question, and it will be answered less by launch announcements than by how the system performs under stress. For now, frxUSD reads as a serious contender for the role of default DeFi dollar, distinguished more by where its yield goes than by anything novel in how it holds its peg.
