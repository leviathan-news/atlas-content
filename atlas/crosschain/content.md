The ability for separate blockchain networks to communicate, transfer assets, and share data without a central intermediary — that is the core problem crosschain infrastructure exists to solve.

Blockchain's foundational design treats each network as sovereign: Ethereum, Solana, and hundreds of other chains each maintain their own state, consensus rules, and token standards. Assets and data created on one chain cannot natively exist on another. Crosschain technology is the engineering discipline — and increasingly the product category — that bridges those gaps, enabling value and information to move between otherwise isolated networks.

## Why Interoperability Matters

The proliferation of Layer 2 rollups, application-specific chains, and alternative Layer 1s has made isolation worse, not better. Liquidity fragments across dozens of mainnets; developers must maintain separate deployments on each network; users face friction choosing which chain to hold assets on. By 2026, bridges and routing protocols collectively route hundreds of billions of dollars annually, making crosschain infrastructure one of the most consequential — and most attacked — layers in decentralized finance.

The economic argument is straightforward: a dollar of liquidity accessible across all chains is worth more than a dollar locked on one. Unified liquidity pools reduce slippage, lower borrowing costs, and make yield-bearing instruments more competitive with traditional finance alternatives.

## How Crosschain Transfers Work

At a technical level, crosschain protocols follow one of several trust models:

**Lock-and-mint bridges** lock a token in a smart contract on the source chain and mint a synthetic "wrapped" equivalent on the destination. The user holds an IOU backed by the locked collateral. This model is simple to implement but concentrates risk: the lock contract becomes a high-value target. The $292 million Kelp exploit — which prompted Kraken to migrate more than $3 billion in locked crosschain assets away from LayerZero and onto Chainlink's infrastructure for kBTC bridging — illustrates how catastrophically this can fail.

**Burn-and-mint (native issuance)** eliminates the IOU by burning the token on the source chain and minting a canonical version on the destination. Circle's Cross-Chain Transfer Protocol (CCTP) and its successor CCTPv2 use this model for USDC. Because Circle — the issuer — controls minting rights, there is no wrapped intermediary and no lock contract holding reserves. CCTPv2 extends the original by introducing "fast transfers" that allow liquidity providers to front funds on the destination chain and be reimbursed once the burn proof is confirmed, cutting settlement from minutes to seconds.

**Intent-based protocols** invert the flow: a user states what they want on the destination chain, solvers compete to fulfill the intent using their own capital, and the protocol reimburses them from the source chain after the fact. Across Protocol operates on this model and reports zero exploits and $28 billion in bridged volume in 2026 — a track record that has made it a preferred choice for teams sensitive to smart-contract risk.

**Oracle and messaging layers** like Chainlink's Cross-Chain Interoperability Protocol (CCIP) focus on passing arbitrary data and token values between chains using decentralized oracle networks as the trust layer. This underpins institutional use cases such as crosschain collateral management systems, where positions on one chain must be repriced against data from another.

## Stablecoins as the Crosschain Unit of Account

Stablecoins have emerged as the dominant asset class in crosschain flows, and USDC in particular has become infrastructure-grade. Circle has systematically expanded CCTP to new networks — Injective and Hedera among the most recent integrations announced — making the burn-and-mint path for dollar-denominated value increasingly ubiquitous.

Circle's Gateway service adds a layer above CCTP: developers can route USDC across chains without managing destination-chain gas or maintaining separate on-chain deployments. The Forwarding Service within Gateway automates destination-chain minting, meaning a developer building a multi-chain application can treat USDC as a single asset that "appears" on whichever chain the user happens to be on. Circle has also released open-source AI skills — compatible with tools like Cursor, Claude Code, and Codex — that let developers and AI agents generate USDC and crosschain integration code directly from natural language prompts.

The expansion of USDT0 (a crosschain-native variant of Tether's USDT) to Hedera follows a similar logic: stablecoin issuers understand that distribution across chains is a competitive moat.

## Developer Infrastructure and Routing

For developers building on multiple chains simultaneously, the operational burden historically included deploying separate contracts, managing separate gas wallets, and handling separate token approvals on each network. Routing aggregators have emerged to abstract most of this away.

LI.FI, for example, provides APIs and SDKs that cover swap, bridge, and deposit routing across more than 60 chains. Its recent integration with Somnia — an "Agentic L1" optimized for AI-driven applications — illustrates how new chain entrants increasingly treat multichain routing as table-stakes infrastructure rather than a later-stage addition. Developers building on Somnia gain access to LI.FI's existing liquidity network from mainnet launch rather than bootstrapping their own.

Polygon's Trails module within the Open Money Stack takes a payment-oriented approach: it enables one-click crosschain payments, swaps, and deposits using any input token, routing the conversion internally. More than $250,000 in volume has moved through Trails, with consumer applications like Levr.bet using it to let users fund positions from whichever chain holds their assets.

Uniswap's 2026 product updates reflect the same direction from the consumer side: the addition of one-click crosschain swaps across 11 networks, an in-app wallet, and portfolio P&L tracking moves the DEX from a single-chain trading venue toward a multichain financial interface. Users no longer need to manually bridge before trading; the routing layer handles it.

## Security: The Persistent Challenge

Crosschain infrastructure has been disproportionately targeted by attackers. Bridge hacks have accounted for a substantial share of total DeFi losses since 2021, for structural reasons: bridges aggregate large sums in lock contracts, rely on complex cross-chain message verification, and often involve off-chain validator sets that can be compromised.

The Kelp/LayerZero incident that led Kraken to switch to Chainlink for kBTC is a recent case study in how even established protocols can fail. Kraken's migration of $3 billion in assets was notable both for its scale and for the explicit attribution to a security decision rather than a feature comparison.

Across Protocol's zero-exploit record through $28 billion in volume has drawn attention to intent-based designs as potentially more resilient: solvers bear the capital risk of fulfilling transfers, and the settlement mechanism is simpler than complex lock contract logic.

DeFi.com's CEO, among others, has raised concerns about crosschain identity unification — the idea that a single identity layer across chains could simplify user experience but simultaneously create a larger attack surface for linking on-chain behavior across networks. The privacy implications of unified crosschain identity remain an open research problem.

## Institutional Crosschain Infrastructure

Institutional adoption of blockchain is increasingly crosschain by nature. Traditional financial firms typically operate across multiple custody providers, networks, and settlement venues. A collateral management system that reprices positions in real time must pull data from several chains simultaneously — exactly the use case Espresso Systems demoed at a recent institutional DeFi event, combining their shared sequencer layer with Chainlink's data infrastructure.

Espresso's membership in the Linux Foundation Decentralized Trust consortium signals a deliberate push to meet enterprise governance standards. Institutional infrastructure requires audit trails, defined counterparty relationships, and regulatory clarity — none of which is inherently chain-specific but all of which are complicated when assets span multiple networks.

Chainlink CCIP has become the preferred messaging layer for many institutional integrations precisely because its decentralized oracle network model maps onto familiar concepts of data validation with multiple independent sources, rather than novel cryptographic trust assumptions.

## The Liquidity Fragmentation Problem

Despite significant infrastructure investment, liquidity fragmentation remains severe. Each new chain launch splits existing capital thinner, and bridge deposits represent capital temporarily removed from productive use on both ends of a transfer. Native yield during in-flight transfers is an active area of research.

USDC's burn-and-mint model partially addresses this: because there is no wrapped intermediary, liquidity providers on the destination chain can operate against canonical USDC rather than a chain-specific synthetic. CCTPv2's fast-transfer mechanism lets LPs earn yield on the capital they front during settlement, turning bridge facilitation into a yield-generating activity.

Across Protocol's integration with Hyperliquid — enabling crosschain deposits into USDC-denominated perpetual futures — is an example of connecting crosschain routing directly to financial products. A user on Arbitrum can open a perpetual position on Hyperliquid without manually moving funds; Across handles the settlement in the background.

Uniswap's crosschain swap feature operates similarly: the user selects input and output tokens across different networks, and the protocol routes the transfer and swap in a single transaction flow from the user's perspective.

## Standards and Governance

No single crosschain standard has achieved dominance, which creates integration overhead for developers but also preserves competitive pressure on protocol security and cost. CCTP is close to a de facto standard for USDC specifically, given Circle's role as issuer. For arbitrary messaging, CCIP, LayerZero, and Wormhole each have substantial deployment bases.

The governance question — who decides when a bridge is secure enough to trust — is largely unresolved. Most protocols rely on their own audits and bug bounty programs. Espresso Systems' move toward Linux Foundation governance represents an early attempt to externalize some of that trust, though membership in a foundation does not itself certify security.

## Outlook

Crosschain infrastructure is converging toward a set of patterns that were still experimental three years ago: intent-based routing, burn-and-mint for stablecoins, and oracle-secured arbitrary messaging. The remaining frontier is making these mechanisms invisible to end users — the goal being that neither a consumer using a DEX nor a developer building a financial application needs to reason about which chain an asset lives on.

The security track record will continue to be the decisive factor in institutional adoption. Protocols that accumulate years of exploit-free operation while handling meaningful volume — Across's $28 billion figure is the most prominent current benchmark — will attract the capital and integration partnerships that entrench network effects. Meanwhile, Circle's CCTP expansion, Chainlink's institutional partnerships, and routing aggregators like LI.FI commoditizing the developer experience all point toward a near future where crosschain is less a distinct category and more a standard feature of blockchain infrastructure.
