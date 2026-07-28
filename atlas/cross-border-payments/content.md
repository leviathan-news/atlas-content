Sending money across borders has always extracted a toll — in fees, delays, and opacity. Blockchain-based rails and dollar-pegged stablecoins are now forcing a structural renegotiation of who collects that toll and how much it should cost.

---

## Why Cross-Border Payments Are So Expensive Today

The global cross-border payments market moves roughly $150 trillion per year in wholesale flows and several trillion more in retail remittances, according to BIS estimates. Despite that scale, the infrastructure underneath it was built in layers over decades. A payment from the United States to a recipient in the Philippines often routes through a correspondent bank in New York, a regional hub in Singapore, and a local bank before reaching a peso account — each leg adding fees, FX conversion spreads, and settlement delays measured in days rather than seconds.

The World Bank's Remittance Prices Worldwide database has long documented average retail costs of 6–7% per transfer. Those numbers have improved slowly, but the cost structure remains largely intact because the correspondent banking model depends on pre-funded nostro/vostro accounts — pools of idle capital held at each leg of the chain to cover liquidity needs. Correspondent banks earn revenue by controlling access to those pools.

El Dorado, a Latin American payments app that raised a $9M Series A led by Paradigm, is targeting a regional cross-border market the company estimates at up to $1 trillion annually. The round illustrates how much venture capital has concluded that this cost structure is an attack surface, not a fixture.

## The Stablecoin Layer: Speed, But Not Always Cheaper

Stablecoins — tokens whose value is pegged to a reference asset, most commonly the US dollar — have emerged as the primary blockchain-native instrument for cross-border settlement. Their appeal is structural: a USDC transfer on a public blockchain settles in seconds, is visible to both counterparties, and does not require a correspondent bank relationship. The sender and receiver bear only the on-chain gas fee and whatever conversion cost exists at the endpoints.

USDC, issued by Circle, has positioned itself explicitly as payments infrastructure. Circle's Payments Network (CPN) has attracted integrations from payment service providers worldwide; UQPAY, a Singapore-headquartered global account provider, joined CPN specifically to streamline multi-market payouts, FX execution, and cross-border flows across its business client base.

MoneyGram — whose agent network spans 200+ countries and territories — launched MGUSD, a native US dollar stablecoin built on the Stellar network. The move is significant because MoneyGram already has the last-mile cash distribution infrastructure that blockchain rails lack; MGUSD is meant to make the settlement leg of those transactions near-instant rather than T+1 or T+2. Stellar's low transaction costs and fast finality have made it a recurring choice for this use case: AllUnity launched EURAU, a MiCAR-compliant euro stablecoin, on the same network for euro-denominated institutional settlement.

Ripple's RLUSD has taken a different integration path. Using Wormhole's Native Token Transfers (NTT), RLUSD can now move natively across multiple blockchain ecosystems rather than being locked to a single chain — a practical requirement for institutional on/off-ramps that need to meet counterparties wherever liquidity exists.

One important caveat: stablecoins speed up cross-border payments but do not always make them cheaper. Stablecoin FX firms have raised over $100M in recent funding rounds precisely because FX conversion at the endpoints remains a margin-bearing service. Moving USDC cheaply across chains solves the rail problem; converting to local currency on either end is a separate and often expensive transaction. Industry analysis has flagged that HSBC and Deutsche Bank face up to 7% revenue risk as corporates shift cross-border flows to stablecoin rails, but that risk flows to those banks' correspondent revenue — not necessarily to lower costs for end recipients.

## Incumbent Rails: SWIFT Responds

SWIFT, the messaging network that underpins most interbank cross-border payments, launched a new cross-border payments framework with more than 50 participating banks — including major global institutions — promising instant settlement, fixed fees, and end-to-end traceability across major remittance corridors by the end of June 2026. That commitment to fixed fees and traceability directly mirrors the value proposition blockchain advocates have been making for years.

SWIFT's framework does not require banks to abandon existing ledgers; it layers settlement guarantees and transparency on top of correspondent relationships rather than replacing them. This is the incumbent's characteristic response: absorb the feature set of the challenger while preserving the network effects of the existing infrastructure.

KBank, Thailand's largest commercial bank, and Ant International have separately enlisted JPMorgan's Kinexys platform to improve cross-border payment processing. Kinexys operates a permissioned blockchain for wholesale settlement and represents a middle path: institutional-grade blockchain infrastructure controlled by a systemically important bank rather than a public chain.

## Central Banks and the Tokenization Frontier

The most consequential long-term question in cross-border payments is whether central bank money itself can move on blockchain rails. The Bank for International Settlements convened Project Agorá — a collaboration involving the Federal Reserve Bank of New York, the Bank of England, and the Bank of Japan, among others — to test whether tokenized central bank reserves could improve cross-border settlement. The BIS concluded the project with positive findings and announced it would proceed to real-value testing on blockchain rails, a material escalation from the simulation and sandbox phases that typically precede such announcements.

If tokenized central bank reserves become interoperable across jurisdictions, the fundamental friction of cross-border payments — the need to pre-fund nostro accounts in foreign currencies — could be substantially reduced. Settlement would occur at the level of central bank liabilities rather than commercial bank IOUs, eliminating counterparty credit risk from the equation.

China's mBridge project — a central bank digital currency (CBDC) platform backed by China and designed for cross-border wholesale payments — is preparing for commercial rollout. mBridge involves the central banks of China, Hong Kong, Thailand, and the United Arab Emirates and has completed multiple pilot transactions. Its commercial launch would represent the first large-scale deployment of multi-CBDC infrastructure for cross-border use, potentially enabling settlement between participating jurisdictions without involving the US dollar correspondent banking system.

## Emerging Markets: Infrastructure and Regulation

Cross-border payment innovation is disproportionately relevant to emerging markets, where remittances represent a larger share of GDP and costs are often highest. AWARP, a project focused on sovereign-grade financial infrastructure, secured strategic investment to work on real-world asset (RWA) tokenization and cross-border payment networks specifically for emerging markets. Avalanche's L1 architecture has been cited as a platform for lowering payment costs and accelerating settlement for businesses in frontier markets.

The NEAR AI ecosystem is partnering with a financial super-app targeting Indians abroad — one of the world's largest remittance corridors — to deploy AI financial agents for cross-border payments, combining language model interfaces with stablecoin rails.

Regulatory response has been uneven. Brazil's central bank banned crypto use within its regulated cross-border eFX payment rails, requiring providers to route through traditional FX transactions and tightening control over stablecoin flows within the regulated perimeter. This is not a ban on stablecoins per se, but a jurisdictional assertion: the regulated FX corridor is for regulated instruments. Providers operating in Brazil must now choose between the regulatory perimeter and the crypto rail, not both simultaneously.

In Europe, MiCA (Markets in Crypto-Assets Regulation) has provided a framework that licensed stablecoin issuers are using as a competitive differentiator. Bison Bank launched the first Portuguese MiCA-compliant stablecoin explicitly for institutional cross-border payments. MiCA compliance signals that a stablecoin meets reserve, audit, and operational standards — a requirement for banks and regulated financial institutions to use it without additional legal risk.

## The FX Liquidity Question

Stablecoins solve the settlement rail problem. They do not automatically solve the FX liquidity problem — the need for deep, low-spread conversion between currencies at scale. On-chain FX is an active development area. Multiple projects have launched on-chain FX liquidity pools pairing major stablecoins: six global stablecoin pairs running on Polygon, using frxUSD as the base dollar pairing, are one example of an attempt to build deep on-chain FX liquidity specifically for cross-border payment use cases.

The logic is that if USDC-to-EURC, USDC-to-MXNC, or similar pairs have sufficient on-chain liquidity, a business can execute an FX conversion and a cross-border settlement atomically, with transparent pricing, rather than routing through a bank's FX desk at an opaque spread. This remains an early-stage market; on-chain FX depth is thin relative to traditional FX markets, and large transactions would move prices significantly. But the infrastructure is being assembled.

Modern Treasury, a payment operations platform, has launched global USD accounts enabling instant cross-border payments for platforms in more than 90 countries — a product that routes through both traditional and blockchain rails depending on what is available in each corridor, illustrating that the practical reality is hybrid rather than pure.

## Outlook

The cross-border payments landscape is undergoing simultaneous pressure from multiple directions: public-chain stablecoins from below, permissioned institutional blockchain platforms from the middle, and tokenized central bank reserves from above. SWIFT's fee and transparency commitments signal that the incumbent network recognizes the threat. The BIS's move to real-value testing on Project Agorá is a slow but consequential signal that central banks are willing to experiment with the underlying architecture of international settlement.

Near-term, the most impactful developments will likely be in retail and SME corridors — Latin America, South Asia, Southeast Asia — where stablecoin rails combined with last-mile networks like MoneyGram's can displace meaningful correspondent bank revenue. Regulatory clarity, particularly MiCA in Europe and equivalent frameworks elsewhere, will determine how quickly licensed stablecoins can be adopted by banks and payment providers at scale. The Brazil central bank's stance is a reminder that regulatory harmonization across jurisdictions is not guaranteed, and that the map of where crypto rails are permitted to operate in regulated payments will remain uneven for years.

---
