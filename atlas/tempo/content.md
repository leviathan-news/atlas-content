A payments-first Layer 1 blockchain incubated by Stripe and Paradigm, Tempo is designed to serve as shared financial infrastructure for stablecoin transactions at institutional scale — a purpose-built network intended to do for programmable money what Amazon Web Services did for cloud compute.

---

## What Tempo Is and Why It Exists

The stablecoin market crossed roughly $230 billion in total supply by early 2026, with on-chain settlement volume reaching approximately $390 billion — a level at which the limitations of general-purpose blockchains become economically meaningful. High gas fees, slow finality, and the absence of built-in compliance primitives all create friction that enterprises, banks, and payment processors cannot absorb.

Tempo's design premise is that payments require a different set of trade-offs than decentralized finance or NFT speculation. Rather than optimizing for censorship resistance or composability across arbitrary smart contracts, the network targets throughput, predictable fees, and compliance tooling as first-order properties. Stripe has described the positioning explicitly: Tempo as "AWS for money," a specialized, managed layer that businesses plug into rather than build from scratch.

The concept was first published by Paradigm in September 2025, framing the network as a "payments-first blockchain" — one where the gas token is not a volatile native asset but rather the stablecoins being transferred, removing a key UX barrier for non-crypto-native enterprises. Tempo's mainnet went live in March 2026.

## Technical Architecture

Tempo is EVM-compatible, meaning developers can port Solidity contracts and Ethereum tooling without rewriting from scratch. Its headline specifications target more than 100,000 transactions per second, finality in roughly 600 milliseconds, and fees below one-tenth of a cent per transaction — performance figures that position it closer to Visa's internal settlement infrastructure than to Ethereum's base layer.

Three design choices distinguish Tempo from general-purpose EVM chains:

**Gas paid in stablecoins.** Users do not need to hold a native token to pay for transactions. USDC, USDT, or other supported stablecoins serve as gas, reducing the friction of onboarding merchants and payroll providers who have no interest in token speculation.

**Issuer-level compliance controls.** Every token deployed on Tempo can carry issuer-defined rules: allowlists, blocklists, and freeze capabilities that travel with the asset across the entire network. When a stablecoin issuer updates a blocklist on mainnet, every part of the network enforces the change automatically. This is a direct response to the compliance gap that Jevgenijs Kazanins, Tempo's researcher on banking adoption, has publicly articulated: banks cannot scale stablecoin payments without embedded sanctions screening, fund-freeze capabilities, and AML controls — features that retrofitting onto a general-purpose chain is technically and legally complex.

**Permissioned validator entry.** Validators on Tempo are not anonymous proof-of-stake participants. The network has onboarded Visa, Stripe, and Standard Chartered's custody arm Zodia Custody as anchor validators, with MoneyGram serving as an anchor remittance validator. This gives the network a compliance pedigree that regulated financial institutions can point to when satisfying internal risk committees.

## The Validator Network and Institutional Buy-In

The decision by Visa to launch a validator node on Tempo — announced in April 2026 — is one of the clearest signals yet that the largest legacy payment networks are treating blockchain settlement as a production-grade concern rather than an experiment. Visa reported that configuring its node required six months of joint engineering work with Tempo's team to integrate Visa's secure infrastructure with the chain's requirements.

Visa had already expanded its stablecoin settlement pilot to include Tempo among several networks — alongside Base, Polygon, Canton, and Arc — and by early 2026 that pilot was processing approximately $7 billion in annualized volume, growing at roughly 50% quarter-over-quarter. The Tempo validator role deepens that relationship: Visa is no longer just settling transactions on the chain but participating in producing and attesting to blocks.

Standard Chartered's Zodia Custody joining simultaneously signals institutional custody providers positioning for a world where enterprise clients hold and move stablecoins on-chain. The combination of a global card network, a Tier 1 custodian, and the world's largest payment processor all operating validator infrastructure on the same chain is structurally unusual and reflects deliberate sequencing on Tempo's part — attract credibility anchors first, then use that credibility to onboard mid-market and emerging-market participants.

## Stablecoins and the Asset Ecosystem

Tempo does not issue its own stablecoin. Instead, it serves as a settlement layer for assets issued by others. USDT0 — a cross-chain version of Tether's USDT — was supported from launch, with Kraken becoming the first major U.S. exchange to enable USDT0 deposits and withdrawals via Tempo.

The MiCA-regulated asset ecosystem has arrived on the network as well. AllUnity launched SEKAU, a fully reserved Swedish krona stablecoin, across Tempo alongside Ethereum, Solana, Base, and Polygon. AllUnity's MiCA-regulated euro stablecoin EURAU also expanded to Tempo via market maker Flowdesk. Frax expanded its frxUSD stablecoin to the network, with a Morpho vault built on top reaching $1 million in deposits shortly after launch.

The Morpho integration — Tempo tapping the $7.5 billion DeFi lender — is notable because it represents the network moving beyond pure payment settlement into yield-bearing stablecoin infrastructure. For enterprises holding large stablecoin balances for treasury or payroll purposes, the ability to earn yield on idle funds without leaving the network reduces the opportunity cost of on-chain adoption.

## Machine Payments and the AI Agent Layer

Tempo's mainnet launch in March 2026 was paired with the Machine Payments Protocol, an open standard co-developed with Stripe for AI agent-to-service payments. The protocol allows software agents to pay autonomously for compute time, API calls, and data access without requiring human sign-off for each transaction — a capability that addresses a bottleneck in agentic workflows where human-in-the-loop payment approval negates the automation benefit.

Paradigm and Tempo subsequently open-sourced Centaur, a self-hosted agent runtime designed for secure multi-user workflows. Centaur allows enterprises to run AI agents with defined spending authorities on-chain without routing sensitive data or credentials through a third-party cloud service. The combination of the Machine Payments Protocol and Centaur positions Tempo as a target network for the emerging category of autonomous AI commerce — a market that does not yet exist at scale but where the infrastructure decisions made now will be path-dependent.

## Zones: Private Stablecoin Rails

The most architecturally significant post-launch development has been Zones, introduced to testnet in 2026. A Zone is an EVM-compatible private chain that runs in parallel to Tempo mainnet. Enterprises deploy a Zone, process transactions inside it — where those transactions are invisible to the public blockchain — and then bridge to and from mainnet for external settlement or liquidity.

The designed use case is payroll and treasury operations where confidentiality is a business requirement. A company can onramp stablecoins to mainnet, move them into a payroll Zone, and distribute wages to employees without exposing individual payment amounts or recipient identities on a public ledger. Recipients can withdraw to mainnet for off-ramps or DeFi access.

Crucially, issuer compliance controls carry through Zone boundaries automatically. A sanctioned address that is blocklisted on mainnet remains blocked inside every Zone without additional configuration — a design that attempts to resolve the tension between privacy and regulatory compliance.

The feature has drawn scrutiny. Privacy advocates note that Zone-level confidentiality depends entirely on the Zone operator's honesty, and critics have raised the possibility of hidden transaction flows that regulators in the EU and Hong Kong — where stablecoin frameworks are either in force or imminent — may find difficult to audit. Whether Zones satisfy the transparency requirements of MiCA or Hong Kong's stablecoin licensing regime remains an open legal question as of mid-2026.

## Real-World Adoption: Payroll, Remittance, and Commerce

The use cases Tempo has publicly announced follow a pattern: high-volume, cross-border, or payroll-adjacent payments where stablecoin settlement offers a speed and cost advantage over legacy rails.

**DoorDash** announced an integration to allow its delivery workers — Dashers — to receive payouts in stablecoins via Stripe's infrastructure and Tempo's settlement layer. For gig economy workers who may be underbanked or who operate cross-border, stablecoin payroll removes several days of ACH clearing and foreign exchange spread.

**MoneyGram**, whose core business is consumer remittance, joined Tempo as an anchor remittance validator. The partnership formalizes MoneyGram's deepening blockchain payments strategy and gives Tempo a distribution network with established last-mile cash-out infrastructure across more than 200 countries and territories.

**Mesh** formalized a partnership with Tempo to advance stablecoin payment connectivity at scale, integrating Tempo into Mesh's financial connectivity layer.

Taken together, these adoption vectors illustrate why Tempo's internal research has focused on preparing banks for stablecoin pilots now — before retail customer demand materializes at scale. The argument, articulated by Kazanins and others on Tempo's advisory team, is that operational expertise in compliance, treasury management, and stablecoin settlement cannot be acquired overnight. Banks that delay will find themselves technologically behind partners and competitors when regulatory clarity fully arrives.

## Compliance, Regulation, and the Banking Question

The central policy question surrounding Tempo and stablecoin payments more broadly is whether the compliance architecture is sufficient for regulated financial institutions. Tempo's issuer-level controls — blocklists, freezes, allowlists — are a direct answer to the objection that public blockchains are incompatible with AML and sanctions obligations.

However, on-chain compliance tools are only as good as the data feeding them. Sanctions screening requires near-real-time access to lists maintained by OFAC, the EU, and equivalent bodies, and the responsibility for updating those lists on-chain falls somewhere between the stablecoin issuer, the network operator, and the enterprise deploying the asset. Kazanins has publicly acknowledged this, framing bank involvement as a structural requirement: banks bring the compliance infrastructure, customer identity data, and regulatory relationships that pure-crypto entities do not have.

The mainnet launch itself noted regulatory risk in the EU and Hong Kong — the two jurisdictions where stablecoin frameworks are most developed — suggesting that Tempo's legal status in those markets will evolve alongside regulatory implementation rather than being settled at launch.

## Outlook

Tempo's near-term trajectory depends on two variables moving in parallel: stablecoin regulatory clarity in major markets, and enterprise willingness to commit production payment volume to a chain that went live only months ago. The validator roster — Visa, Stripe, Zodia Custody, MoneyGram — suggests the credibility problem is being solved from the top of the financial stack downward. Zones extends the addressable market into enterprise treasury and payroll use cases that would have been non-starters on a fully transparent public ledger.

The deeper question is whether a payments-specialized chain can sustain a defensible position as general-purpose L2s improve their throughput and fee profiles and as regulatory frameworks increasingly define what compliance controls are *required* rather than optional. If compliance primitives become table stakes for all stablecoin infrastructure, Tempo's advantage becomes its institutional network and its distribution partnerships rather than its technical architecture alone. The Stripe positioning — infrastructure that enterprises plug into rather than build — is the thesis being tested in real production environments for the first time.

---

Sources:
- [Paradigm: Tempo — The Blockchain Designed for Payments](https://www.paradigm.xyz/2025/09/tempo-payments-first-blockchain)
- [Stripe-led payments blockchain Tempo goes live — CoinDesk](https://www.coindesk.com/tech/2026/03/18/stripe-led-payments-blockchain-tempo-goes-live-with-protocol-for-ai-agents)
- [Visa Launches Validator Node on Tempo Blockchain — Visa Newsroom](https://usa.visa.com/about-visa/newsroom/press-releases.releaseId.22311.html)
- [Tempo Onboards Visa, Stripe and Zodia Custody as Validators — The Defiant](https://thedefiant.io/news/blockchains/tempo-onboards-visa-stripe-and-zodia-custody-as-validators)
- [Stripe-backed Tempo taps Morpho — CoinDesk](https://www.coindesk.com/business/2026/05/18/stripe-backed-tempo-taps-usd7-5-billion-defi-lender-morpho-to-expand-beyond-payments)
- [Tempo Unveils Zones for Private Enterprise Stablecoin Transactions — The Defiant](https://thedefiant.io/news/blockchains/tempo-unveils-zones-for-private-enterprise-stablecoin-transactions)
- [Introducing Tempo Zones — Tempo Blog](https://tempo.xyz/blog/introducing-tempo-zones/)
- [Tempo homepage](https://tempo.xyz/)
