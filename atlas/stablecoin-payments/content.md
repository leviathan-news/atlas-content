Dollar-pegged digital tokens are reshaping how value moves across borders, between businesses, and between machines—settling in seconds at a fraction of traditional wire costs.

The stablecoin payments sector has moved from proof-of-concept to genuine infrastructure build-out in the span of roughly two years. What was once a niche used primarily for crypto trading settlement is now attracting banks, regulators, fintech startups, and institutional asset managers—all racing to lay claim to the rails that could one day carry a meaningful share of global commerce.

## What Stablecoin Payments Actually Are

A stablecoin is a blockchain-based token pegged to a reference asset—almost always the US dollar, though euro and other currency pegs exist. Unlike bitcoin or ether, the value doesn't float; one USDC or USDT is designed to always be redeemable for one dollar.

Stablecoin payments use these tokens as the unit of account and settlement medium in place of traditional bank transfers, card networks, or wire systems. The sender initiates a transfer on-chain; the recipient receives tokens on the same or a bridged chain; settlement is final within seconds rather than days. The payer and payee never need to agree on a shared bank or correspondent relationship—just a shared ledger.

The distinction from "crypto payments" broadly is important: stablecoins remove exchange-rate risk from the equation. A supplier in Lagos and a buyer in Chicago can transact in a common unit without either party speculating on token price.

## Why the Sector Is Growing Now

Several forces have converged simultaneously.

**Onchain volume is real.** Monthly stablecoin settlement volumes have crossed $390 billion according to industry tracking, a figure cited by Tempo's Jevgenijs Kazanins in his analysis of compliance requirements. That is no longer rounding-error territory relative to established payment networks.

**Correspondent banking is slow and expensive.** A cross-border wire between non-partner banks can take two to five business days and cost $25–$50 per transaction, often with additional intermediary fees invisible to the sender. Stablecoin rails, when they work cleanly, compress this to seconds and cents.

**Traditional institutions are entering directly.** Zelle—the P2P payments network jointly owned by Bank of America, JPMorgan Chase, Wells Fargo, and other major US banks—announced Zelle USD, a stablecoin specifically designed for international payments. The move is significant precisely because Zelle has no ideological stake in crypto; it is responding to a commercial gap.

**Developer platforms are maturing.** Coinbase's Developer Platform now bundles wallet infrastructure, payment capabilities, trading, stablecoin issuance, and treasury management into a single access point—including compatibility with AI agents. Coinbase's commercial stablecoin payments product promises custody, compliance, settlement, fiat rails, and agentic commerce as packaged infrastructure rather than components businesses must assemble themselves.

## The Cross-Border Use Case

Cross-border payments are the application layer where stablecoins have the clearest near-term advantage. The friction in legacy systems—correspondent banking chains, currency conversion, cutoff windows, SWIFT message formats—compounds into multi-day delays and significant cost.

Emerging markets are a particular focus. Ripple has made a strategic investment in Flutterwave at a $3.2 billion valuation specifically to bring stablecoin rails to African payment corridors. Polygon has expanded its DPTPay collaboration to push low-fee stablecoin payments across Africa. The IMF has weighed in on Nigeria, urging the government not to restrict stablecoins outright but instead to strengthen regulation, expand blockchain analytics, and modernize its payment infrastructure as adoption accelerates.

These are not fringe experiments. They reflect a recognition that in corridors where legacy banking infrastructure is thin, stablecoin rails can offer better service than the incumbent alternative.

ECB President Christine Lagarde has noted that US stablecoins are explicitly targeting the payments gap created by foreign schemes handling 60% of Europe's card volume—framing the stablecoin question as one of monetary sovereignty, not just technology.

## Infrastructure Being Built

The past 12 months have seen a wave of infrastructure investment designed specifically for stablecoin payment flows, not just general-purpose blockchains.

**Payments-first chains.** Alchemy Chain is being built as a payments-first Layer 1, designed for fast, predictable, and compliant stablecoin transactions. The argument is that general-purpose blockchains optimized for smart contract complexity create unnecessary variability in fees and finality—a problem when you need a predictable, low-cost payments substrate.

**Gasless transfers.** Sui has launched gasless stablecoin transfers to address a specific friction point: transactions stalling because a user holds a stablecoin but lacks a second token to pay gas. This is a genuine UX problem that has frustrated real payment use cases.

**Collective consortia.** The Avalanche Payments Collective launched with founding participants including Franklin Templeton, VanEck, Anchorage Digital, Paxos, Agora, Ethena, Rain, and others. The model aggregates players across the payments stack—stablecoin issuers, settlement providers, custodians, treasury managers—to create interoperability rather than fragmented silos.

**Agentic payment architecture.** An emerging whitepaper from InterlaceMoney and partners explores the standards and architecture needed for AI-native commerce, where software agents initiate, authorize, and settle payments autonomously. Stablecoins are the natural settlement layer for machine-to-machine commerce because they are programmable, atomic, and don't require a human to authorize each transaction through a bank's interface.

## Regulatory Pressure: The AML and Sanctions Layer

Growth has attracted regulatory attention, and the compliance buildout is now a core part of the infrastructure conversation—not an afterthought.

**Five US regulators have jointly proposed** customer identification requirements for payment stablecoin issuers, modeled on existing bank rules and embedded within the GENIUS Act's AML framework. The Federal Reserve Board separately requested comment on a proposal requiring certain payment stablecoin issuers to maintain effective customer identification programs.

The core challenge, as Tempo's Kazanins argues, is that banks cannot scale stablecoin payments without sanctions screening, fund freeze capabilities, and anti-money-laundering controls. Onchain volume of $390B per month is large enough that regulators treating stablecoins as a payments instrument—rather than a speculative asset—makes structural sense.

WalletConnect Pay has built pre-settlement sanctions screening into its payment flow, allowing checks to run before a transaction finalizes rather than flagging after the fact. OSL has secured an Australian Financial Services Licence (AFSL) covering wholesale stablecoin payments, custody, and OTC trading—one of the first regulated frameworks to treat stablecoins as a distinct payments instrument under an existing financial services regime.

The regulatory direction, at least in the US and Australia, appears to be toward incorporating stablecoins into existing financial compliance frameworks rather than creating an entirely separate regime. That has practical implications: issuers will need BSA/AML programs, know-your-customer procedures, and transaction monitoring comparable to what banks already operate.

## Startup Funding and Market Signals

Venture capital is tracking the infrastructure build closely.

Trace Finance raised a $32 million Series A—with Coinbase and CoinFund as backers—at a valuation reportedly ten times its seed-round figure. Trace is building stablecoin payment infrastructure for businesses, competing in the stack layer that sits between raw blockchain infrastructure and end-user applications: treasury management, multi-currency settlement, and fiat conversion.

FV Bank has launched a unified platform combining stablecoins, traditional payments, and programmable finance. The positioning reflects a broader pattern: the most credible stablecoin payment startups are not trying to replace banking entirely but to bridge between blockchain settlement and existing financial plumbing.

## How Businesses Integrate Stablecoin Payments

For a company evaluating stablecoin payments, the practical integration path involves several decisions:

**Custody.** Who holds the stablecoin between receipt and conversion or settlement? Custodians range from regulated institutions (OSL, Anchorage Digital) to software wallets with multi-party computation key management. The answer affects counterparty risk, insurance, and regulatory status.

**On/off ramps.** Receiving USDC is only useful if you can convert it to local currency when needed, or pay suppliers who accept it directly. Ramp quality varies significantly by jurisdiction.

**Compliance screening.** At scale, transactions need wallet screening against OFAC and other sanctions lists, ideally pre-settlement. WalletConnect Pay's model and similar approaches address this programmatically.

**Chain selection.** USDC runs natively on Ethereum, Solana, Avalanche, Base, and several other chains. Settlement speed, gas costs, and ecosystem depth vary by chain. Avalanche and Solana are common choices for payment use cases because of lower costs and higher throughput compared to Ethereum mainnet.

**Fiat settlement timing.** Treasury teams need to decide whether to hold stablecoins on balance sheet (introducing counterparty risk on the issuer) or convert immediately to fiat (introducing conversion friction). Most enterprise implementations opt for a hybrid.

Coinbase's packaged offering—combining these components into a single commercial product—reflects the market need: most businesses don't want to assemble a payments stack from primitives.

## Risks and Unresolved Questions

The growth narrative has genuine counterweights.

**Counterparty risk on issuers.** USDC is backed by Circle; USDT by Tether. Both maintain reserves, but the opacity and composition of those reserves have been subject to scrutiny. A depeg event—even a temporary one—in a large stablecoin would cause serious disruption to any payment system relying on it.

**Regulatory fragmentation.** The US is moving toward a regulatory framework via the GENIUS Act, but global standards are not harmonized. A payment that is compliant in Australia may not be compliant in the EU under MiCA or in the UK under its emerging stablecoin regime.

**Execution risk at scale.** Industry analysis cautions that while stablecoin payments represent "an inevitable tide, the crypto ships built for them may not weather the storm"—a reference to the gap between current infrastructure capabilities and the demands of high-volume, compliance-grade payment flows.

**Gas and UX friction.** Despite improvements like Sui's gasless transfers, the UX of stablecoin payments for non-technical users remains more complex than a Zelle or Venmo transfer. Bridging that gap without centralizing key functions is an unsolved design problem.

## Outlook

The stablecoin payments infrastructure build-out is real, well-funded, and attracting institutional participants who were skeptical or absent two years ago. The entry of Zelle—an institution created by the largest US banks specifically to defend their position in domestic payments—into the stablecoin space signals that incumbent financial institutions now view stablecoin rails as a strategic necessity for cross-border flows rather than a threat to be lobbied against.

Regulatory clarity is arriving, if unevenly. US proposals modeled on bank compliance frameworks suggest stablecoin payment issuers will operate under familiar but meaningful obligations. That should accelerate enterprise adoption by reducing legal uncertainty while raising the compliance bar for new entrants.

The next 18 months will likely determine which infrastructure layer—chains, compliance tooling, custody, or developer platforms—captures the most durable margin in the stack. Businesses and developers building on this infrastructure should track regulatory developments in the US, EU, and Australia closely, and evaluate stablecoin issuers not just on their current peg stability but on the robustness of their reserve structures and compliance programs.
