Holding private keys is holding real money — custody in crypto refers to who controls the cryptographic keys that authorize movement of digital assets, and getting it wrong means those assets can be lost, frozen, or stolen with no recourse.

---

## What Custody Actually Means

Every Bitcoin, token, and stablecoin balance on a blockchain is controlled by a private key — a string of cryptographic data that authorizes transactions. Whoever holds that key holds the asset. "Custody," borrowed from traditional finance where banks hold stocks and bonds on behalf of clients, maps imperfectly onto this model because crypto keys are bearer instruments: possession is ownership.

This creates a binary that does not exist in conventional finance. When a bank holds your shares, the shares still exist in a regulated registry; the bank is a legal intermediary. When a crypto exchange holds your Bitcoin, the coins exist on a ledger the exchange controls. If the exchange is hacked, goes bankrupt, or freezes withdrawals, you are an unsecured creditor — as millions of FTX, Celsius, and Mt. Gox customers discovered.

That risk calculus drives the entire custody industry.

## Self-Custody: The Baseline Option

Self-custody means the end user generates and stores their own private keys, typically through a hardware wallet (a physical device that signs transactions offline) or a software wallet running on a phone or desktop. The appeal is absolute: no counterparty risk, no KYC requirement, no withdrawal limits set by a third party.

The tradeoff is equally absolute. Lose the seed phrase — a human-readable backup of the private key — and the funds are gone permanently. There is no customer support line, no password reset, no regulatory body to appeal to. Chainalysis estimates that somewhere between 17% and 23% of all Bitcoin in existence is permanently inaccessible due to lost keys, representing millions of coins at current prices.

Self-custody is increasingly well-documented and accessible — hardware wallets from Ledger and Trezor now retail for under $100, and most major software wallets guide users through secure seed phrase backup — but it remains a poor fit for institutions managing assets on behalf of clients, where fiduciary duty, audit requirements, and operational complexity demand a different model.

## Third-Party Custody: The Institutional Layer

When a fund manager, corporation, or high-net-worth individual needs to hold digital assets, they typically turn to a qualified custodian: a regulated entity that holds private keys on behalf of clients under legal agreements, insurance coverage, and segregated account structures.

The mechanics vary, but most institutional custodians use some combination of:

- **Cold storage**: Keys generated and stored on air-gapped hardware, never touching an internet-connected device. Appropriate for assets that move infrequently.
- **Multi-party computation (MPC)**: Cryptographic key-splitting across multiple parties or devices, so no single point of failure can expose the full key. Widely used by firms like Fireblocks, BitGo, and Copper.
- **Hardware security modules (HSMs)**: Tamper-resistant physical chips that perform signing operations without ever exposing the raw key material.
- **Threshold signature schemes (TSS)**: Similar to MPC but operating at the signature level, enabling distributed signing without reconstructing a complete key.

Most enterprise deployments layer multiple controls. BitGo, for instance, recently integrated HPP (High Performance Protocol) natively into its platform, extending institutional-grade custody — including MPC key management, settlement rails, and compliance tooling — to the HPP ecosystem. That kind of integration signals what institutional clients now expect: custody is not just key storage but a full operational stack covering on-chain settlement, reporting, and connectivity to trading venues.

## The Qualified Custodian Question and SEC Scrutiny

In traditional finance, the Securities and Exchange Commission's Investment Advisers Act requires registered investment advisers to hold client securities with a "qualified custodian" — generally a bank, broker-dealer, or registered futures commission merchant. The question of whether existing crypto custodians meet that definition has been fiercely contested.

In 2023, the SEC proposed expanding the custody rule to cover crypto assets, which would have required advisers to use only bank-chartered custodians — a standard few crypto-native firms met at the time. The proposal drew heavy industry opposition. Under new leadership in 2025, the SEC rescinded Staff Accounting Bulletin 121, which had required banks to hold custodied crypto as liabilities on their balance sheets — a rule that had made bank custody economically punitive. That reversal opened the door for traditional financial institutions to enter the market at scale.

Kraken's parent company, Payward, has applied to the Office of the Comptroller of the Currency (OCC) for a national trust company charter to establish Payward National Trust Company — a federally chartered entity designed explicitly for regulated digital asset custody. If granted, it would give Kraken a custody credential comparable to what state-chartered trust companies like Anchorage Digital already hold.

Anchorage Digital, which holds the only OCC-chartered federal digital asset bank license currently in existence, recently launched regulated TRX (TRON) custody for U.S. institutions, broadening the asset coverage available under its federal charter. The UK is separately targeting October 2027 for comprehensive crypto regulation covering both trading and custody under the Financial Services and Markets Act.

## Traditional Finance Moves In

The most significant structural shift in custody over the past 18 months has been the entry of major traditional financial institutions — not as investors in crypto firms, but as direct custody providers.

**BNY Mellon**, the world's largest custodian bank with roughly $50 trillion in assets under custody, received regulatory approval to hold Bitcoin and Ether for institutional clients and has since expanded its crypto custody push to Abu Dhabi through a partnership with Finstreet and the Abu Dhabi Investment Authority ecosystem. The UAE move reflects a broader Gulf region race to establish institutional digital asset infrastructure.

**Standard Chartered** has moved decisively through its subsidiary Zodia Custody. The bank recently announced it will acquire the remainder of Zodia Custody's core business and absorb it directly, while spinning out Zodia's technology operations as a separate entity called Zodia Solutions. Zodia Custody itself secured a Luxembourg payment institution license — a significant credential for EU stablecoin custody and transfers under the Markets in Crypto-Assets (MiCA) regulation, which came into full effect in 2024. BitMEX has also partnered with Zodia Custody to enable off-exchange collateral trading, letting institutions post derivatives margin while assets remain in segregated custody — a structure known as "off-exchange settlement" that has become a key risk management primitive.

**Charles Schwab** has announced a 2027 target for a crypto trading and custody rollout aimed specifically at registered investment advisers — a channel representing trillions of dollars in managed assets that currently has almost no regulated crypto custody access.

**Northern Trust** is piloting tokenized asset custody on the Canton Network, the privacy-preserving DeFi infrastructure developed by Digital Asset. The integration is designed to give institutions custody not just of native crypto assets but of tokenized versions of traditional securities — a category that regulatory frameworks are only beginning to address.

**Copper**, a London-based crypto custodian known for its ClearLoop off-exchange settlement network, has reportedly been put up for sale at approximately $500 million, reflecting both the consolidation pressure on mid-tier custodians and the valuation compression in the sector since the 2021 peak.

## Stablecoins and the New Custody Demand

Stablecoin volumes have reached all-time highs in 2026, driven by corporate treasury adoption, cross-border payments infrastructure, and the launch of regulated stablecoin frameworks in the EU (MiCA), UK, and the U.S. This surge is creating a distinct custody challenge.

Stablecoins are not simply "digital dollars" — they are smart contract claims on reserves held by issuers like Circle (USDC) or Tether (USDT), and their custody involves securing both the on-chain tokens and, in the case of institutional holders, the documentation of reserve verification. The emerging field of **Digital Asset Custody Reserve Verification** addresses how custodians prove that stablecoin reserves actually back the tokens in circulation.

Coinbase has positioned its Payments product as an integrated solution covering custody, compliance, settlement, fiat conversion, and what it terms "agentic commerce" — automated payment flows executed by AI agents on behalf of businesses. The bundling of custody with settlement rails reflects an industry recognition that, for corporate stablecoin use, the custody question is inseparable from the payments infrastructure question.

Zodia Custody's Luxembourg payment institution license is specifically designed for this intersection: EU stablecoin custody requires both digital asset security and the payment institution status needed to move fiat in and out of the eurozone.

## Emerging Structures: DeFi, Staking, and Cross-Chain Custody

Institutional custody is no longer limited to passive asset storage. As DeFi protocols and proof-of-stake networks have matured, custodians face demand for what might be called **active custody** — holding assets while simultaneously deploying them into yield-generating or governance-active positions.

Cactus Custody recently added access to Lido V3's stVault product through its Cactus Link integration, allowing institutional ETH stakers to access liquid staking while maintaining custodial-grade key security. The structural challenge is significant: staking involves broadcasting signed transactions to validator contracts on a live network, which conflicts with the air-gap security model of cold storage. MPC-based custody architectures are better suited to this use case, since they can generate threshold signatures without moving key material to a hot environment.

Cross-chain custody presents further complexity. The launch of wXRP on Solana through Hex Trust — a wrapped version of Ripple's XRP token — illustrates the bridge risk inherent in cross-chain asset representation: the custodian of the native XRP must be trusted to back every wrapped unit 1:1, and bridge exploits have historically been one of the largest sources of institutional crypto losses.

Taiwan Mobile, SYSTEX, and Liminal Custody have joined forces to establish institutional digital asset infrastructure in Taiwan — a sign that custody buildout is now a genuinely global phenomenon, not confined to New York, London, and Singapore.

## What Institutions Should Evaluate

For any institution selecting a custody solution, the relevant dimensions include:

- **Regulatory status**: Is the custodian chartered (OCC, state trust, EU payment institution) or operating under a less formal framework? What happens to client assets in bankruptcy?
- **Key management architecture**: Cold storage, MPC, HSM, or hybrid? Has the architecture been independently audited?
- **Insurance**: Does coverage address hot wallet breaches, cold storage losses, and employee malfeasance? What are the sublimits?
- **Asset coverage**: Not all custodians support all chains or token standards. Staking, DeFi, and cross-chain activity may require specialized infrastructure.
- **Settlement integration**: Can the custodian connect to exchanges and OTC desks for off-exchange settlement, or must assets leave custody to trade?
- **Compliance tooling**: Transaction monitoring, AML screening, and reporting for tax and audit purposes.

## Outlook

The custody landscape is consolidating rapidly around two poles: traditional financial giants (BNY, Standard Chartered, Schwab) bringing balance-sheet strength and regulatory credibility, and crypto-native specialists (BitGo, Anchorage, Copper, Fireblocks) offering deeper protocol coverage and more flexible architecture. The gap between these camps is narrowing as banks acquire or absorb custody firms and as native players pursue federal charters.

Regulatory clarity — expected in the U.S. through 2025-2026 legislative activity, in the EU via MiCA implementation, and in the UK by 2027 — will increasingly reward firms with formal custodian status and penalize those operating in gray areas. Stablecoin growth will add a payments-infrastructure dimension to custody that traditional models were not designed to handle. And as tokenized real-world assets move from pilot to production, the question of who holds the keys will extend to securities, commodities, and real estate — making custody not a crypto-specific niche but a foundational layer of the next financial system.
