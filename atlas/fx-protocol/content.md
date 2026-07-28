f(x) Protocol is an Ethereum-based system that connects fxUSD, individual xPOSITION longs, sPOSITION shorts, and a Stability Pool inside a shared reserve design. That current product map appears across the protocol's [homepage](https://fx.aladdin.club/) and [V2.1 whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf).

The useful way to understand f(x) is as a balance sheet whose parts place different demands on the same reserve. Long positions help create fxUSD. Short positions lock fxUSD while borrowing reserve collateral. Stability Pool deposits provide liquidity for peg management and stressed operations. When the first defenses fail, the system's published design specifies where losses move next.

That architecture changes the shape of familiar leveraged-trading costs without eliminating market risk. The protocol describes funding as normally inactive rather than impossible, and liquidation as a later defense after rebalancing rather than an event the system can never trigger.

## The Current V2.1 Product Map

The protocol's public interface offers leveraged ETH and WBTC markets, but its homepage conflicts on whether fxUSD is backed by both wstETH and WBTC or solely by stETH. The same [homepage](https://fx.aladdin.club/) also describes redemption for stETH or WBTC. Because those first-party statements conflict, the mechanism can be explained more confidently than the exact current reserve composition.

An **xPOSITION** is an individually tracked leveraged long. Opening an xPOSITION is accompanied by minting a proportional amount of fxUSD. The [V2.1 whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf) describes that paired creation as necessary to support the chosen target leverage.

An **sPOSITION** starts with fxUSD collateral and constructs the opposite exposure atomically. To open an sPOSITION, the user supplies fxUSD; an atomic transaction flash-borrows wstETH or WBTC, sells it for additional fxUSD, deposits the combined fxUSD as collateral, borrows the corresponding asset from the long-side reserve, and uses that borrowing to repay the flash loan. The sequence is documented in both the [whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf) and the current [sPOSITION guide](https://fxprotocol.gitbook.io/fx-docs/f-x-protocol-mechanisms/creating-a-leveraged-short-position-sposition). Every step completes together or the transaction reverts.

These products are not conventional perpetual-futures accounts. The protocol's [funding documentation](https://fxprotocol.gitbook.io/fx-docs/faq/how-does-f-x-protocol-minimize-funding-costs-or-annual-interests) describes trade execution against concentrated-liquidity pools, while reserve assets, position debt, peg conditions, and utilization determine exposure and any temporary funding charge.

Atlas uses up to 7x long and 6x short as the most specific current first-party ceiling while noting that official pages also describe 7x in either direction and an older 10x design goal. Those competing statements appear on the current [homepage](https://fx.aladdin.club/), in the [V2.1 whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf), and in the current [risk parameters](https://fxprotocol.gitbook.io/fx-docs/risk-management/risk-parameters), which list a 1.1x-to-7x range without splitting the ceiling by side. Leverage limits are mutable market parameters, so the live interface remains the operational reference for a trade.

## One Reserve, Several Claims

Under the V2.1 accounting design, adjusted reserve value equals the combined net asset value of fxUSD, xPOSITIONs, and sPOSITIONs. The [whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf) expresses this as the core invariant. A long requires the reserve to support both the position and fxUSD created alongside it; a short locks fxUSD while borrowing an asset from the long-side reserve.

Price changes alter the value and leverage of individual positions, but every product remains part of the same accounting system. That invariant is a design rule, not a promise that every exit will execute at a preferred price or time. Settlement still depends on oracle updates, market liquidity, keeper execution, smart contracts, and configured risk controls.

## The Liquidation Brake Rebalances First

Both position types are designed to rebalance at a threshold before reaching a separate liquidation threshold; failed or insufficient rebalancing can still end in liquidation. The sequence is described by the [homepage](https://fx.aladdin.club/), the current [Liquidation Brake documentation](https://fxprotocol.gitbook.io/fx-docs/f-x-protocol-mechanisms/rebalancing-the-position-liquidation-brake), and the current [risk framework](https://fxprotocol.gitbook.io/fx-docs/risk-management/risk-framework).

For an xPOSITION, keepers repay part of the fxUSD debt and reduce the position toward the rebalance line. For an sPOSITION, keepers repay part or all of the borrowed reserve asset. The trader retains a smaller exposure rather than being closed immediately. Rebalancing carries execution and bounty costs, and it cannot prevent losses when the underlying market moves against a leveraged position.

The [current Stability Pool documentation](https://fxprotocol.gitbook.io/fx-docs/f-x-protocol-mechanisms/stability-pool) and [V2.1 whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf) describe an additional liquidity dependency. xPOSITION rebalances and liquidations can redeem fxUSD from the Stability Pool and exchange reserve collateral for USDC. If pool liquidity is insufficient, additional collateral may be sold, and settlement may proceed synchronously or asynchronously depending on market conditions.

## The Stability Pool Does Several Jobs

The Stability Pool accepts fxUSD or USDC, supplies liquidity for stressed operations, earns stated protocol rewards, and trades around the fxUSD/USDC market as a peg keeper. Its current [documentation](https://fxprotocol.gitbook.io/fx-docs/f-x-protocol-mechanisms/stability-pool) lists reserve yield, position fees, external strategy yield, and FXN emissions among possible reward sources. The precise mix depends on the pool and current program.

As a peg keeper, the pool can use USDC to buy fxUSD below parity and exchange fxUSD for USDC when the reverse trade is favorable. Deposits are valued with a Chainlink USDC price, and the documented design suspends deposits and some peg-keeping actions during a USDC depeg.

These roles connect yield to system function. Depositors supply liquidity that may be used under stressed conditions, so returns remain exposed to smart-contract, oracle, stablecoin, strategy, and withdrawal-liquidity risk.

## Funding Is Normally Off, Not Impossible

Protocol funding is normally off but can activate during fxUSD peg stress or high short-side reserve utilization. The [whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf) and current [funding FAQ](https://fxprotocol.gitbook.io/fx-docs/faq/how-does-f-x-protocol-minimize-funding-costs-or-annual-interests) describe temporary charges intended to reduce excess fxUSD supply, attract Stability Pool liquidity, or discourage shorts from consuming too much long-side collateral. Opening, closing, rebalance, liquidation, and swap costs can also apply according to the event.

For ETH shorts, current documentation says debt is wstETH-denominated, so its value rises with wstETH yield even when temporary protocol funding is off. The [sPOSITION guide](https://fxprotocol.gitbook.io/fx-docs/f-x-protocol-mechanisms/creating-a-leveraged-short-position-sposition) states this separately from the protocol's temporary funding levels. An inactive funding switch therefore does not make ETH-short debt economically costless.

Exact funding thresholds and rates are governance-adjustable. They belong in a live parameter surface rather than an evergreen prose snapshot.

## V1 Used Pooled xTokens, Not xPOSITIONs

V1 used pooled, fungible, variable-leverage xTokens, whereas V2/V2.1 uses individually tracked xPOSITIONs and sPOSITIONs. That version distinction is supported by the current [homepage](https://fx.aladdin.club/), the [V2.1 whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf), and the official [version FAQ](https://fxprotocol.gitbook.io/fx-docs/faq/what-is-the-difference-between-f-x-protocol-v1-and-v2).

In V1, holders of a fungible xToken shared pooled amplified exposure while reserve yield accrued to the stability side. V2 changed the unit of risk: a trader now has an individual position with its own collateral, debt, rebalance path, and liquidation path. Adding sPOSITIONs extended that per-position structure to shorts. Calling V1's xTokens xPOSITIONs erases the central design change.

## What Happens After Rebalancing Fails

Current official risk materials describe a sequence of rebalancing, liquidation, Reserve Fund coverage, same-side bad-debt redistribution, recapitalization, and system-level deleveraging. The sequence appears in the [V2.1 whitepaper](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/whitepapers/f%28x%29_2.1_whitepaper.pdf), the recently updated [risk framework](https://fxprotocol.gitbook.io/fx-docs/risk-management/risk-framework), and the [V2.1 audit report](https://github.com/AladdinDAO/audit-reports/blob/main/SECBIT_f%28x%29_V2.1_Report_v1.0_20250722.pdf).

The Reserve Fund is intended to absorb bad debt after rebalancing and liquidation are exhausted. If it is insufficient, short-side debt is first allocated across healthy sPOSITIONs and long-side debt across active xPOSITIONs. More extreme states can force recapitalization, one-off charges, position reductions, or system-level deleveraging. These rules allocate losses; they do not erase them. Their protection also depends on live funding balances, liquidity, keeper performance, and deployed parameters that are not frozen into this page.

## Contracts, Audits, and Control Surfaces

The current site says 16 audits were conducted and all deployed code is audited; Atlas treats that as a team claim rather than an independent guarantee. The wording appears on the [current site](https://fx.aladdin.club/), while the official [audit index](https://fxprotocol.gitbook.io/fx-docs/risk-management/audit-reports) lists scope-specific reports.

The July 2025 SECBIT V2.1 report covers long and short pools, funding, liquidation, reserve-pool, and bad-debt paths, and marks five High findings as fixed. The [report](https://github.com/AladdinDAO/audit-reports/blob/main/SECBIT_f%28x%29_V2.1_Report_v1.0_20250722.pdf) identifies reviewed commits and also discusses short-pool insolvency socialization and position reductions. An audit remains limited to its code, commits, assumptions, and dates; it is not a warranty against economic failure, oracle failure, governance mistakes, or later code changes.

The public sources reviewed for this page do not provide a canonical current address map connecting the audited V2.1 commits to every live proxy and authority. Accordingly, the page does not repeat the former Atlas page's precise timelock or multisig configuration.

## What Readers Should Track

f(x) combines a stablecoin, leveraged longs, leveraged shorts, and an active liquidity buffer inside one reserve design. Its central distinction is progressive risk handling: rebalancing before liquidation, pool liquidity before broader settlement, and explicit rules for allocating tail losses.

Readers should track leverage caps by market and side, the current composition of fxUSD backing, Stability Pool liquidity and reward sources, funding activation, oracle and keeper performance, the funded size of the Reserve Fund, deployed contract versions, and current administrative authorities.

This page was checked against first-party public sources on July 15, 2026. A previously missed correction now separates the pooled xTokens used in V1 from the individual xPOSITIONs used in V2/V2.1. f(x) and AladdinDAO did not participate in or endorse this replacement. Source-linked factual corrections are always free and do not imply endorsement, sponsorship, partnership, or co-authorship.
