Sending payments using blockchain-based digital assets — whether bitcoin, ether, or dollar-pegged stablecoins — directly between parties or through merchant integrations, bypassing traditional banking rails.

---

The infrastructure that lets a coffee shop in Manila, an online sportsbook in New Jersey, or a government agency in Dubai accept digital assets as payment has matured significantly since the early days of QR-code bitcoin tips. What once required technical sophistication and tolerance for price volatility has evolved into a layered stack of wallets, stablecoin rails, compliance tooling, and regulated processors — with tens of billions of dollars flowing through it annually.

## What Crypto Payments Actually Are

At a technical level, a crypto payment is a signed transaction broadcast to a blockchain network, transferring value from one address to another. The receiver confirms settlement when the transaction reaches sufficient block confirmations. Unlike a credit card authorization — which is a promise to pay, later netted and settled through correspondent banks over days — an on-chain payment settles with finality in seconds to minutes, depending on the network.

Early implementations used bitcoin almost exclusively. Today the dominant medium for commerce is stablecoins: tokens pegged to fiat currencies, primarily the US dollar. USDC (issued by Circle) and USDT (issued by Tether) together account for the vast majority of payment-use stablecoin volume. Their stability removes the exchange-rate risk that made accepting raw BTC or ETH impractical for most merchants.

That said, Bitcoin payments remain active, particularly in markets where BTC is better known than any stablecoin. Coins.ph, the Philippines' largest crypto wallet, recently expanded QRPh-based payments to cover Bitcoin and Ethereum across 700,000 merchant endpoints — illustrating that the "bitcoin as payment" use case has not disappeared; it has simply been joined by a much larger stablecoin layer.

## The Compliance Layer: Why Licenses Matter

The phrase "crypto payments are easy; making them compliant is the hard part" captures a fundamental tension in the industry. Sending USDC peer-to-peer over a public blockchain requires no permission. Processing that payment for a business, converting it to fiat, holding customer funds, or offering a debit card linked to a crypto balance — each of these functions triggers financial regulation.

Jurisdictions vary sharply in how they classify crypto payment services. In the United States, processors typically need money-transmitter licenses (MTLs) on a state-by-state basis. Alchemy Pay recently obtained a Rhode Island Currency Transmitter License, extending its U.S. coverage to 16 states — a reminder that national reach in the U.S. requires assembling a patchwork of state approvals. At the federal level, the Clarity for Payment Stablecoins Act (passed by the Senate in 2025) created the first dedicated federal framework for stablecoin issuers, though broader crypto payment regulation remains fragmented.

Switzerland has issued only five FinTech licenses to date; Fiat24 holds one, powering products like the SafePal Mastercard, which gives users a Swiss IBAN account and global Mastercard acceptance with institutional-grade AML controls. The scarcity of such licenses signals how seriously regulators take the custody and compliance obligations attached to crypto payment products.

Regulatory risk is real and bilateral. Singapore's Monetary Authority (MAS) revoked BSQ's crypto payment license after uncovering what it described as "serious breaches" of regulatory requirements — a case study in how quickly operating permission can be withdrawn when compliance frameworks are not maintained. Aave Labs took a different approach, securing dual Financial Conduct Authority (FCA) licenses in the UK through a local subsidiary before launching any regulated payment infrastructure there.

The emerging consensus among serious operators: obtain licenses proactively, build AML and KYC into the payment flow from the start, and treat compliance as infrastructure rather than an afterthought.

## Stablecoins as the Default Payment Rail

The practical question for most merchants and processors is not "which blockchain?" but "which stablecoin, and how do I convert it to local currency?" USDC has become the preferred choice for regulated, dollar-denominated settlements, partly because Circle maintains reserve attestations and operates under U.S. money-transmitter frameworks. USDT leads in raw volume globally, particularly in emerging markets where dollar access is constrained.

AI agents have emerged as an unexpected driver of stablecoin payment volume. A 2025 report found that autonomous AI agents settled $73 million in crypto payments during a measured period, with stablecoins serving as the default settlement rail — partly because agents cannot hold bank accounts but can hold self-custodial wallets. This trend is still nascent but points toward a future where programmatic, machine-to-machine payments normalize stablecoin usage at scale.

WalletConnect's CEO has suggested that the ideal stablecoin payment integration — one merchants can onboard with minimal friction — is perhaps 18 months away from being routine. The company's WalletConnect Pay product is already targeting payment service providers (PSPs) and acquirers who want to offer on-chain payment options without building stablecoin infrastructure from scratch.

## Network-Level Infrastructure Pushes

Several Layer 1 and infrastructure projects are competing to become the default settlement layer for commercial crypto payments.

Avalanche launched a Payments Collective in 2025 bringing together 28 major firms, with the stated goal of scaling crypto payment rails across 150 countries, 96 currencies, and billions of payment endpoints. The consortium model reflects a recognition that no single company can build the full merchant-acquirer-processor stack alone; interoperability across networks and fiat on/off ramps requires coordinated industry effort.

B2BINPAY, a payment processor targeting enterprise clients, released Version 26.1 with enhanced access controls for crypto payment operations and secured a VASP license from the Financial Services Commission (FSC) in Mauritius — expanding its regulated footprint in Africa and the Middle East. ForumPay, another infrastructure provider, has been scaling its processor network as merchant adoption accelerates. These companies compete in the "business-facing" layer: merchants integrate once, access multiple blockchains, and receive fiat settlements.

Coinbase has been a persistent presence in the payment infrastructure space, both through Base (its Layer 2 network, which dramatically reduces transaction costs for USDC transfers) and through merchant tools that allow businesses to accept crypto with next-day fiat settlement. Base's low fees — fractions of a cent per transaction — address one of the oldest objections to crypto payments: that on-chain fees make small-value transactions uneconomical.

## Vertical Markets Gaining Traction

Crypto payment adoption is not uniform across industries. Several verticals are seeing concentrated activity:

**Online gaming and sports betting.** Research from Paysafe found significant consumer appetite for crypto payment options in U.S. online sports betting, driven partly by pseudonymity preferences and partly by faster settlement compared to ACH or credit cards. iGaming operators are adopting crypto payments to reduce chargebacks, enable cross-border player funding, and compete in markets where card acceptance rates are low. The trend is not without friction: Argentina has proposed legislation targeting crypto payments to illegal gambling platforms, illustrating the regulatory complexity when crypto payments intersect with gaming regulation.

**Emerging markets.** Fasset, a stablecoin-powered neobank, raised $51 million to expand Shariah-compliant banking and crypto payment services in emerging markets — regions where dollar-denominated stablecoins provide a practical hedge against local currency devaluation and where banking penetration is incomplete. Oobit, backed by Tether, launched in Colombia (its ninth market) with a mobile-first crypto payment app targeting the unbanked and underbanked population. Thailand saw Antarctic Wallet begin operations as smartphone-based crypto payment usage grows in Southeast Asia.

**Government and institutional services.** Crypto.com secured the first UAE Central Bank Stored Value Facility (SVF) license, enabling crypto payments for government services in the Emirates — a notable milestone given that government payment acceptance has historically been one of the last frontiers for alternative payment methods.

**Self-custody and tax treatment.** South Carolina enacted legislation in 2025 banning state taxes on crypto payments, protecting self-custody rights, and prohibiting state agencies from accepting or testing CBDCs. The law signals a policy direction — at least at the state level — toward treating crypto payments like other payment instruments rather than taxable property disposals, a distinction that has historically been a significant barrier to everyday use.

## Key Technical Challenges

Several problems remain unsolved or only partially addressed:

**Cross-chain complexity.** A merchant that accepts USDC on Ethereum, Base, Solana, and Avalanche is technically accepting four different assets on four different networks. Processors like B2BINPAY and ForumPay abstract this complexity, but the underlying fragmentation creates reconciliation, liquidity, and security challenges.

**Risky funds and compliance screening.** The iGaming sector has highlighted a specific problem: crypto payments can arrive from wallets associated with sanctioned addresses, mixers, or stolen funds. Processors must screen incoming funds in real time — a non-trivial technical and legal obligation. The next-generation payment flows in iGaming are specifically designed to reduce "exposure to risky funds" through on-chain compliance checks before settlement.

**Fiat on and off ramps.** For most merchants, the end goal is local currency. The conversion from crypto to fiat — and the fees, delays, and banking relationships that entails — remains the most expensive and regulated step in the payment chain. Geographic gaps in fiat off-ramp availability continue to limit deployment in certain markets.

**User experience at the point of sale.** QR-code-based payments (like Coins.ph's QRPh integration or Oobit's merchant app) have made in-person crypto payments viable for everyday retail, but the experience still differs enough from card-tap payments to create friction. Wallet UX and confirmation time remain work in progress.

## Economics of the Infrastructure Layer

The payment processing layer is a competitive, multi-sided market. Processors charge merchants a percentage fee (typically 0.5–2%), take a spread on currency conversion, and may charge network fees. They compete on coverage (how many blockchains and currencies), settlement speed, compliance tooling, and integration quality.

The stablecoin issuers — Circle (USDC) and Tether (USDT) — earn yield on the treasury assets backing their reserves. As stablecoin payment volumes grow, so does the reserve base, making issuance itself highly profitable at scale. This creates a structural incentive for issuers to support payment infrastructure investment.

Layer 2 networks like Base reduce the per-transaction cost of on-chain settlement to the point where micropayments become viable, changing the economics for content, gaming, and machine-to-machine use cases.

## Regulatory Outlook by Region

The global regulatory picture is fragmenting along predictable lines. The United States has moved toward a federal stablecoin framework while leaving broader crypto payment rules to state MTL regimes and CFTC/SEC jurisdiction disputes. The European Union's MiCA regulation (Markets in Crypto-Assets) provides a harmonized framework for crypto payment service providers operating across member states. Singapore and Hong Kong are tightening licensing requirements after a period of relatively open market access. Gulf states — particularly the UAE — are actively licensing crypto payment operators to position themselves as regional fintech hubs. Emerging markets vary widely, from relatively permissive (El Salvador's bitcoin legal tender law) to actively restrictive.

## Outlook

The direction of travel in crypto payments is toward stablecoin-dominated, compliance-first infrastructure that resembles traditional payment processing in its regulatory posture while retaining the settlement speed and programmability advantages of blockchains. The 28-firm Avalanche Payments Collective, the wave of VASP and MTL licensing activity, and the rapid growth in iGaming and emerging-market adoption all point to an industry that has moved past proof-of-concept and into deliberate infrastructure buildout.

The remaining obstacles — cross-chain fragmentation, fiat off-ramp gaps, and inconsistent global regulation — are engineering and policy problems with known solutions, not fundamental blockers. Whether crypto payments displace a meaningful share of card and ACH volume over the next five years will depend less on technology and more on whether regulatory frameworks stabilize enough for large merchants to commit to integration at scale. Current trajectory suggests they will.
