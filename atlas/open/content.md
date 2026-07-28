The OPEN Stablecoin Index is a permissionless, equal-weight onchain index that bundles the governance tokens of leading DeFi stablecoin networks into a single redeemable ERC-20, built on Reserve Protocol's Decentralized Token Folio (DTF) standard and governed by its own token, SQUILL.

This explainer focuses on that index — the project most crypto readers mean when they say "$OPEN" in a DeFi context. The ticker is reused elsewhere (Figure's onchain public-equity network "OPEN" on Provenance, and unrelated masternode projects), so it is worth stating up front that those are distinct from the subject here. ([CoinGecko](https://www.coingecko.com/en/coins/open-stablecoin-index), [Reserve docs](https://reserve.org/protocol/index_dtfs/))

## What OPEN Is

OPEN is an Index DTF deployed on Reserve Protocol on Ethereum mainnet (contract `0x323c...Ce21`). A DTF — Decentralized Token Folio — is Reserve's generic name for any onchain, asset-backed index: a single ERC-20 token that is 100% collateralized by a basket of other onchain assets held on the same chain, redeemable at any time for the underlying components without a custodian or intermediary. ([Reserve app](https://app.reserve.org/ethereum/index-dtf/0x323c03c48660fE31186fa82c289b0766d331Ce21/overview), [Reserve docs](https://reserve.org/protocol/index_dtfs/overview/))

Where most crypto indices track market-cap leaders or layer-1 tokens, OPEN takes a narrower thesis: it holds the governance and network tokens of *stablecoin issuers* — the protocols that mint and manage decentralized dollars. The stated framing is an equal-weight basket of "stablecoin networks advancing transparency, composability, and user-led governance." Holding OPEN is therefore a bet on the infrastructure layer beneath stablecoins rather than on any single dollar token. ([512m.io](https://512m.io/blog/open-stable-capturing-the-stablecoin-economy), [DefiLlama](https://defillama.com/protocol/open-stablecoin-index))

Because it is a DTF, OPEN inherits three properties worth understanding:

- **Full backing.** Every OPEN token is redeemable for its share of the underlying basket. There is no leverage or synthetic exposure at the wrapper level.
- **Permissionless mint/redeem.** Anyone can mint OPEN by supplying the constituent tokens, or redeem OPEN to receive them, without approval.
- **Onchain governance of composition.** The basket's contents and weights are set by tokenholder vote rather than by a fund manager. ([Reserve docs](https://reserve.org/protocol/index_dtfs/overview/))

## The Index Methodology

OPEN targets **equal weights** across its constituents and rebalances on a quarterly cadence the project brands "ReGenesis." Each quarter, candidate protocols are evaluated against inclusion criteria, the community votes on which assets make the cut, and the basket is reconstituted toward equal weighting. ([Reserve forum RFC Q4](https://forum.reserve.org/t/rfc-open-stablecoin-index-regenesis-q4-2025/1250))

Methodology is itself a live governance topic. The index has opened discussions on refining inclusion criteria and moving toward parameterized weightings rather than strict equal weighting — a sign the framework is still maturing. Constituents rotate meaningfully between quarters: the Q3 reconstitution expanded the basket to ten DeFi stablecoin networks, and the Q4 rebalance pitted eleven protocols against one another for ten slots, with Resupply displacing Sky Protocol (formerly MakerDAO/DAI) in the final basket. ([Reserve forum RFC Q3](https://forum.reserve.org/t/rfc-open-stablecoin-index-regenesis-q3-2025/1158))

### Rebalance Auctions

Reconstitution is executed through onchain auctions: when weights change, the protocol auctions the over-weighted assets for the under-weighted ones to bring the basket back to target. This mechanism is the point where index theory meets execution risk. A post-mortem from analytics firm Pangea found roughly **7.5% misallocation** in the Q3 rebalance, attributing it to a flawed auction mechanism. That issue was addressed in Reserve Protocol's 4.0.0 upgrade, and subsequent rebalances ran on the corrected mechanism. The episode is a useful reminder that for onchain indices, the rebalance plumbing matters as much as the asset-selection thesis. ([Reserve docs — rebalancing](https://metalamp.io/magazine/article/reserve-finance))

## SQUILL: Governance and Fee Capture

OPEN's composition, parameters, and rebalances are controlled by a separate governance token, **SQUILL**, which is hard-capped at 10,000,000 tokens. SQUILL is not the index itself — it is the steering wheel. ([Season 3 drop](https://leviathannews.substack.com/p/season-3-squill-drop-is-open))

The core mechanic is **vote-locking**. Holders lock SQUILL into **vlSQUILL** to gain voting power over the index — which assets are added or removed, how weights are set, and how the methodology evolves — and in exchange earn a share of the protocol's TVL and minting fees. This is a familiar "vote-escrow" design borrowed from Curve's vlCRV/veCRV lineage: lock the governance token, direct the protocol, and receive a cut of the revenue it generates. Governance happens directly on mainnet rather than through an off-chain committee. ([Season 3 drop](https://leviathannews.substack.com/p/season-3-squill-drop-is-open), [Reserve forum — governance params](https://forum.reserve.org/t/open-governance-parameters-update-q2-2026/1528))

A notable governance development: **ABC Labs**, the team behind Reserve Protocol, announced a SQUILL acquisition ahead of the Q4 rebalance — aligning the index's underlying protocol developer with its governance layer. Separately, **DefiLlama** added OPEN to its Fees & Revenue dashboard, giving the index third-party, transparent revenue tracking rather than self-reported figures. ([DefiLlama](https://defillama.com/protocol/open-stablecoin-index))

## The SQUILL Airdrop

SQUILL has been distributed primarily through a multi-season airdrop rather than a sale. The early seasons seeded the token among the communities most likely to participate in governance:

- **Season 1** targeted contributors to Leviathan News.
- **Season 2** expanded to DeFi governance and liquidity contributors.
- **Season 3** added roughly **2,000,000 SQUILL** to the broader OPEN community, explicitly including Llama lockers, DefiLlama subscribers, GEAR (Gearbox) governors, and Lobster DAO NFT holders — alongside OPEN holders, vote-locked SQUILL holders, and OPEN/WETH and SQUILL/WETH liquidity providers on Curve and Uniswap. ([Season 3 drop](https://leviathannews.substack.com/p/season-3-squill-drop-is-open), [squill-drop repo](https://github.com/open-stablecoin-index/squill-drop))

The eligibility design is deliberate. By rewarding lockers, LPs, and governance participants of *adjacent* DeFi protocols, the distribution concentrates SQUILL in hands that already understand vote-escrow systems and stablecoin governance — the cohort most likely to lock into vlSQUILL and steer the index actively. Claims are made directly through an onchain contract within a fixed window, with eligibility verifiable via the project's GitHub or the contract's read functions.

## The Leviathan Connection

OPEN and SQUILL sit inside the orbit of **Leviathan News**, a decentralized crypto-news platform whose native token is **$SQUID**. The lineage is reflected in the naming (SQUID → SQUILL) and in Season 1's targeting of Leviathan contributors. Leviathan functions as a media and community layer around the index — its livestreams (e.g., the recurring "Llama Party") regularly cover OPEN alongside Curve, Yield Basis, and related DeFi topics, and it runs bounties for "DeFi storytellers" rewarded in SQUILL. ([Season 3 drop](https://leviathannews.substack.com/p/season-3-squill-drop-is-open))

For readers, the practical distinction is: **SQUID** is the media/community token of Leviathan News; **SQUILL** is the governance token of the OPEN index; **OPEN** is the index product itself. They are related by community and origin but serve different functions.

## Curve Integration

OPEN's economic design leans heavily on **Curve**. Liquidity for both OPEN and SQUILL is concentrated in Curve pools (OPEN/WETH and SQUILL/WETH), and the project has advanced **gauge proposals** to bring those pools into Curve's gauge system — which would make them eligible for CRV emissions and the broader Curve incentive flywheel. The vote-escrow model SQUILL uses is itself an adaptation of Curve's veCRV mechanism. This tight coupling means OPEN's liquidity health and SQUILL's governance economics are partly downstream of Curve's incentive markets. ([CurveCap on X](https://x.com/CurveCap/status/1923352165562667190), [Embracing Curve with OPEN arms](https://curve.substack.com/p/embracing-curve-with-open-arms))

## How OPEN Performs and Why It Might Matter

The investment case for OPEN rests on a structural claim: as more economic activity moves to stablecoins, the protocols that issue decentralized dollars capture value, and an equal-weight basket of them offers diversified exposure to that trend without picking a single winner. The project has circulated a backtest suggesting the index would have outperformed ETH over the measured period — a claim that should be read as a backtest, not a guarantee, and evaluated against the usual caveats about survivorship bias and changing constituents. ([512m.io](https://512m.io/blog/open-stable-capturing-the-stablecoin-economy))

Risk factors a reader should weigh:

- **Constituent risk.** The basket holds governance tokens of stablecoin protocols, which carry the smart-contract, peg, and governance risks of those underlying systems.
- **Rebalance execution.** As the Q3 misallocation showed, auction mechanics can introduce slippage; the fix in Reserve 4.0.0 mitigates but does not eliminate this category of risk.
- **Liquidity dependence.** OPEN and SQUILL liquidity is concentrated in a small number of Curve/Uniswap pools and partly reliant on incentive emissions.
- **Governance concentration.** Vote-escrow systems reward large, long-term lockers, which can centralize decision-making over the index's composition.

## Outlook

OPEN is best understood as an experiment in putting an actively governed, fully onchain thematic index into production — and doing it permissionlessly. The near-term signposts to watch are concrete: how the methodology debate resolves (strict equal weighting versus parameterized weights), whether the Curve gauge proposals pass and deepen liquidity, how cleanly post-4.0.0 rebalance auctions execute, and whether DefiLlama-tracked fees grow enough to make vlSQUILL's revenue share materially attractive. ABC Labs' involvement and the steady cadence of quarterly ReGenesis rebalances suggest the project intends to keep iterating rather than ship-and-forget. For now, OPEN occupies a small but instructive niche: a live test of whether onchain index governance can outperform — and outlast — the discretionary fund managers it aims to replace.

Sources:
- [Open Stablecoin Index — DefiLlama](https://defillama.com/protocol/open-stablecoin-index)
- [Open Stablecoin Index — Reserve app](https://app.reserve.org/ethereum/index-dtf/0x323c03c48660fE31186fa82c289b0766d331Ce21/overview)
- [Reserve Docs — Index DTFs](https://reserve.org/protocol/index_dtfs/)
- [RFC: $OPEN Stablecoin Index ReGenesis Q4 2025](https://forum.reserve.org/t/rfc-open-stablecoin-index-regenesis-q4-2025/1250)
- [RFC: $OPEN Stablecoin Index ReGenesis Q3 2025](https://forum.reserve.org/t/rfc-open-stablecoin-index-regenesis-q3-2025/1158)
- [OPEN Governance Parameters Update Q2 2026](https://forum.reserve.org/t/open-governance-parameters-update-q2-2026/1528)
- [Season 3 SQUILL Drop is OPEN — Leviathan News](https://leviathannews.substack.com/p/season-3-squill-drop-is-open)
- [open-stablecoin-index/squill-drop — GitHub](https://github.com/open-stablecoin-index/squill-drop)
- [Open Stable: Capturing the Stablecoin Economy — 512M](https://512m.io/blog/open-stable-capturing-the-stablecoin-economy)
- [Embracing Curve with OPEN arms — crv.mktcap.eth](https://curve.substack.com/p/embracing-curve-with-open-arms)
- [Open Stablecoin Index — CoinGecko](https://www.coingecko.com/en/coins/open-stablecoin-index)
