A Miami-founded fintech infrastructure company, MoonPay has grown from a simple fiat-to-crypto checkout widget into a multi-sided platform spanning consumer onramps, institutional custody, AI-native payments, and stablecoin settlement rails.

---

## What MoonPay Is

Founded in 2019 by Ivan Soto-Wright and Victor Faramond, MoonPay began as a lightweight embeddable widget that let any crypto wallet or exchange accept credit cards, debit cards, and bank transfers without building payment infrastructure in-house. That positioning — invisible to end users, indispensable to developers — earned it early distribution across hundreds of wallets, NFT marketplaces, and DeFi front-ends.

The company is privately held and has not disclosed total funding publicly, but its client roster has consistently included household-name crypto projects as well as mainstream financial institutions. Its regulatory footprint spans the United States, European Union, and United Kingdom, with money transmitter licenses in most U.S. states and FCA registration in the UK.

What distinguishes MoonPay architecturally from competitors is its aggregator model: rather than running a single payment processor, it routes transactions across a network of bank partners, card networks, and local payment methods to optimize for approval rate and cost. That infrastructure layer is now being extended well beyond simple buy flows.

---

## The Core Onramp Business

MoonPay's original product — letting someone go from a bank account or credit card to holding crypto in a self-custody wallet in minutes — remains the foundation of the business. The mechanics are straightforward: a user selects an asset and amount, provides payment details and identity verification (KYC), and receives cryptocurrency directly to a wallet address they control. MoonPay handles the fiat leg, the KYC/AML compliance stack, and the crypto purchase, then settles the asset on-chain.

For developers and platforms, this matters because the regulatory and banking overhead of accepting fiat and disbursing crypto is significant. A DeFi protocol or NFT platform integrating MoonPay's SDK can offer card purchases without holding a money transmitter license of its own in most jurisdictions — MoonPay's licenses cover the transaction.

A recent illustration: dYdX's mobile app integrated MoonPay to support instant fiat deposits via credit card, Apple Pay, and Google Pay, letting perpetuals traders fund positions directly from their bank accounts without bridging through a centralized exchange first.

---

## Moving Into Stablecoins and Virtual Accounts

The onramp model has an inherent limitation: it relies on traditional card rails, which carry chargebacks, interchange fees, and approval-rate friction. MoonPay's stablecoin pivot addresses this by building what it calls Virtual Accounts — bank account numbers (ACH and SWIFT-compatible) that route fiat inflows directly to non-custodial wallets as stablecoins, rather than going through a card transaction.

The company secured a New York BitLicense to operate these accounts in one of the strictest regulatory jurisdictions in the United States, enabling ACH and SWIFT transfers to settle as stablecoins (principally USDC and USDT) without the user going through a centralized exchange. This is meaningful for institutions and businesses that need to move large dollar amounts into on-chain environments without the friction and cost of card rails.

Practical deployments are already live. Ledgity, a DeFi treasury management platform, integrated MoonPay Virtual Accounts to let corporate treasuries fund on-chain positions via standard bank wire. Moto Card partnered with MoonPay to enable instant fiat funding for crypto-backed Visa Infinite cards — users top up via Virtual Account, the balance is held as stablecoins, and the card spends from that balance with up to 5% cashback. Franklin Templeton took this further by integrating its BENJI tokenized money market fund directly into MoonPay, enabling 24/7 swaps between stablecoins and yield-bearing tokenized assets — a real-time bridge between the dollar-denominated institutional settlement layer and on-chain yield.

---

## MoonPay Trade: Institutional and DeFi Access

In 2026 MoonPay launched MoonPay Trade, a unified platform giving institutions and enterprises access to more than 200 blockchain networks and DeFi protocols through a single interface. The product is positioned to let a bank, fund, or corporate treasury access DeFi liquidity — swaps, lending markets, yield protocols — without building and maintaining integrations to each protocol individually.

The launch came alongside the acquisition of Decent, a multichain protocol aggregator, which brought cross-chain execution infrastructure into the stack. That followed the acquisition of DFlow, described as Solana's fastest-growing execution layer, which added over $50 billion in trading volume and order-routing technology to MoonPay's stack. DFlow's infrastructure handles smart order routing — splitting and routing trades across liquidity venues to minimize slippage — which is the same function that institutional trading desks build proprietary systems to perform.

The combination positions MoonPay Trade as a one-stop access layer: a financial institution that wants exposure to on-chain yield or DeFi liquidity can route through MoonPay rather than managing direct protocol relationships, custody arrangements, and RPC connections to dozens of chains.

---

## AI Integration: MoonAgents and the ChatGPT Onramp

Perhaps the most strategically distinctive move in MoonPay's recent history has been its push into AI-native payments. As large language models become interfaces for consumer activity — research, shopping, task execution — MoonPay has positioned its payment rails as the default way those AI systems handle financial transactions.

The flagship product in this area is MoonAgents, a desktop application that lets AI agents (including Claude and Codex, two widely used coding and reasoning assistants) initiate and complete crypto transactions on a user's behalf. Rather than the user manually navigating to an exchange, the agent handles the transaction flow end-to-end within the conversation interface.

More prominently, MoonPay became the first crypto onramp integrated directly into OpenAI's ChatGPT App Store. Users can purchase Bitcoin and other assets via direct checkout links inside ChatGPT, with Apple Pay support for frictionless payment. The integration lets OpenAI's hundreds of millions of users encounter crypto purchasing as a native feature of the assistant they already use daily, rather than as a separate destination they must navigate to.

This expansion has not been without criticism. Security researchers and analysts raised concerns about buying Bitcoin or XRP through AI chat interfaces — specifically around the risk that malicious prompts or compromised sessions could initiate unintended transactions, and that the conversational UI obscures the transaction confirmation steps that standard exchange UIs make explicit. MoonPay's response has centered on its standard KYC and confirmation flows remaining intact regardless of the UI surface through which the transaction is initiated.

The MoonAgents Card extends this concept further: a Mastercard-network card that AI agents themselves can hold and spend, denominated in stablecoins. The practical implication is that an autonomous AI workflow — say, an agent managing a business's vendor payments — can hold a stablecoin balance and spend it at any Mastercard-accepting merchant without a human intermediary approving each transaction. MoonPay integrated this into OpenClaw AI agents running on Rumble Cloud, enabling chat-native crypto management with no wallet setup required from the end user.

The acquisition of Dawn Labs, an AI trading infrastructure startup, added an AI Trading Copilot and tooling for prediction market participation, rounding out MoonPay's suite of agent-facing financial primitives.

---

## Institutional Security and the Sodot Acquisition

As MoonPay deepens its institutional business, custody and key management become load-bearing concerns. A single breach of a large institution's private keys could result in losses that would be existential for a service provider. In 2026, MoonPay acquired Sodot, an Israeli cryptographic security firm, in a $100 million all-stock transaction.

Sodot's core technology is multi-party computation (MPC) — a cryptographic technique that distributes private key signing across multiple parties such that no single party ever holds or sees the complete key. This is the dominant approach to institutional-grade custody, used by firms like Fireblocks and Anchorage. Bringing Sodot's technology in-house allows MoonPay to offer MoonPay Institutional with a proprietary MPC stack rather than relying on third-party custody providers, which matters for large financial institutions that are unwilling to place their key management in a vendor's hands.

MoonPay's institutional ambitions are also reflected in its regulatory positioning. Brian Quintenz, the company's policy lead and former CFTC Commissioner, has been a visible advocate for the view that technology enables compliance rather than undermining it — framing MoonPay's expanding regulatory footprint as a feature for institutional partners rather than a cost center.

---

## Payments at Physical Retail

The stablecoin-at-checkout use case has historically been hampered by merchant adoption friction: most point-of-sale systems do not natively accept crypto, and real-time fiat settlement (which merchants require) has required intermediaries to convert on the fly.

MoonPay's partnership with WalletConnect and Ingenico (a major global POS hardware manufacturer) addresses this directly. The integration routes stablecoin payments at Ingenico terminals through MoonPay Virtual Accounts, which settle in fiat to the merchant instantly. The merchant never touches crypto; the buyer pays in stablecoins from their wallet; MoonPay handles the conversion and settlement layer invisibly. This is the same model PayPal pursued with its "checkout with crypto" feature but built on non-custodial infrastructure rather than requiring users to hold assets inside PayPal's own system.

Separately, MoonPay's partnership with Paysafe — a major online payments processor serving gaming, gambling, and digital commerce — extends MoonPay's onramp capabilities into Paysafe's merchant network, adding another high-volume distribution channel that doesn't require direct integration work from individual merchants.

---

## Regulatory and Compliance Positioning

MoonPay operates in a compliance-heavy environment by design. Its business model depends on maintaining banking relationships and regulatory licenses; a single license revocation in a major market would remove access to card networks and bank rails simultaneously. The company has invested heavily in KYC/AML infrastructure, sanctions screening, and geofencing.

The New York BitLicense acquisition for Virtual Accounts is the most recent regulatory milestone. New York's BitLicense is among the most demanding crypto-specific regulatory frameworks globally, requiring detailed compliance programs, capital reserves, and ongoing reporting. Holding it signals to institutional counterparties — banks, asset managers, payment networks — that MoonPay can operate as a compliant financial institution rather than a lightly regulated tech company.

The company's regulatory strategy also reflects a broader industry shift: as stablecoins move toward formal frameworks (the U.S. GENIUS Act, EU MiCA stablecoin provisions), infrastructure providers that can demonstrate existing compliance programs are better positioned than those building compliance retroactively under pressure.

---

## Competitive Landscape

MoonPay competes across several overlapping categories. In consumer onramps, its primary competitors are Transak, Ramp Network, and Banxa — all pursuing similar SDK-based distribution strategies. Coinbase and Stripe's crypto infrastructure arm also compete at the checkout layer. In institutional settlement, it overlaps with Fireblocks, Anchorage Digital, and BitGo. In stablecoin payment rails, it faces Circle's own distribution efforts and emerging neobanks building directly on USDC rails.

What distinguishes MoonPay's current positioning is the breadth of the stack it is assembling: onramp + Virtual Accounts + institutional MPC custody + DeFi access via Trade + AI agent payment primitives is a combination none of its direct competitors currently offers end-to-end. The risk in that breadth is execution — building and maintaining all of those product lines simultaneously is operationally demanding, and the acquisitions (four in 2026 alone, by their own count) introduce integration complexity.

---

## Outlook

MoonPay's trajectory in 2026 is unmistakably toward becoming infrastructure for the next wave of financial abstraction — where AI agents, institutional desks, and retail users interact with crypto and stablecoins through familiar interfaces (chat, card, bank transfer) without managing technical complexity directly.

The ChatGPT integration is the highest-visibility bet: if AI assistants become the dominant interface for consumer financial decisions, the first payment provider embedded in those assistants captures substantial distribution. The institutional push via Sodot and MoonPay Trade addresses the other end of the market — large capital allocators who need compliant, auditable, MPC-secured access to on-chain assets.

Whether MoonPay can sustain its acquisition pace while integrating disparate technology stacks into coherent products remains the central execution question. The stablecoin regulatory environment, particularly in the U.S., will also determine how quickly the Virtual Account and retail checkout products can scale. If the GENIUS Act passes and creates a clear federal framework for stablecoin issuers and payment processors, MoonPay's existing compliance infrastructure becomes a durable competitive advantage. If the regulatory environment fragments or tightens unexpectedly, the compliance overhead could constrain growth.

For now, MoonPay's bet is that payments, AI, and on-chain finance are converging — and that building the rails connecting all three is the durable position in that convergence.

---
