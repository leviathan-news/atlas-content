Dollar-pegged tokens and their equivalents that keep a fixed value on blockchain networks, stablecoins have evolved from a niche trading tool into core infrastructure for global payments, decentralized finance, and sovereign-currency alternatives.

---

## What a Stablecoin Is — and How It Holds Its Peg

A stablecoin is a cryptographic token whose value is designed to track a reference asset — almost always the U.S. dollar, though Swedish krona, euro, and other currency variants exist. Unlike bitcoin or ether, whose prices float freely, stablecoins achieve price stability through one of three mechanisms:

**Fiat-backed reserves.** The issuer holds cash, Treasury bills, or money-market instruments worth at least one dollar for every token in circulation. Tether (USDT) and Circle's USDC are the dominant examples. Circle publishes weekly reserve attestations; USDC's reserves are held primarily in short-duration U.S. Treasuries and cash held at regulated financial institutions, which is why Fidelity recently launched a GENIUS Act-aligned money market fund specifically designed as a reserve vehicle for stablecoin issuers.

**Crypto-collateralized designs.** Protocols like MakerDAO's DAI hold excess collateral in other crypto assets to absorb volatility. Because the collateral itself can fall in price, these systems are typically overcollateralized — a $1 DAI might be backed by $1.50 in ETH — and rely on liquidation mechanisms when collateral ratios deteriorate.

**Algorithmic or hybrid approaches.** These attempt to maintain the peg through code-driven supply expansion or contraction, sometimes backed by a volatile secondary token. The catastrophic collapse of TerraUSD in 2022 demonstrated the systemic risk of poorly designed algorithmic models, setting back the category significantly. Ethereum co-founder Vitalik Buterin has more recently proposed an options-based design that would leverage ETH upside buyers to create stability without debt, liquidations, or funding rates — an approach that has reignited academic debate but has yet to see production adoption at scale.

---

## The Reserve Yield Question

Fiat-backed stablecoins generate significant revenue because their issuers earn interest on the reserves backing each token — yet, historically, retail holders earned nothing. A 2024 BIS Bulletin (No. 125) formalized what practitioners already understood: centralized exchanges pay stablecoin holders using either reserve returns (yield that tracks policy interest rates) or activity-based income from their own trading operations. Reserve-based yields move predictably with central bank rates; activity-based yields are volatile and opaque.

This bifurcation matters for macro-financial stability. If stablecoins become effective substitutes for bank deposits, their reserve portfolios become a meaningful channel through which Federal Reserve rate decisions transmit into crypto markets. Conversely, if exchanges are funding stablecoin yields through risky proprietary trading, a sharp drawdown could force rapid redemptions — a dynamic regulators are watching closely.

Coinbase has moved aggressively here. Its partnership with Circle gives Coinbase a revenue share on USDC reserves, a relationship that became a material line item as rates rose post-2022. The model illustrates how the stablecoin yield question is not just a product feature but a structural business question: who captures the carry, and under what disclosure obligations?

---

## Stablecoins as Payment Rails

The most consequential near-term use case is payments. On-chain stablecoin volume crossed $390 billion according to recent industry data — a figure that rivals some mid-sized national payment networks. The appeal for cross-border transfers is straightforward: settlement in seconds rather than days, no correspondent banking fees, and 24/7 availability.

Several recent launches underscore how quickly institutional players are moving onto stablecoin rails:

- **MoneyGram** launched MGUSD on the Stellar network, allowing remittance recipients to hold and spend digital dollars — though the product comes with the same caveats as any custodial stablecoin, including freeze risk and limits on redemption.
- **Zelle**, the P2P payments brand operated by the largest U.S. banks, announced Zelle USD for international payments, a striking signal that traditional financial infrastructure is treating stablecoins as a viable rails extension rather than a competitive threat.
- **Shinhan Card** scaled Solana-based stablecoin rails across a customer base of 28 million South Koreans, one of the largest deployments of stablecoin payments infrastructure outside the United States.
- **AllUnity** launched SEKAU, a fully reserved Swedish krona stablecoin, across Ethereum, Solana, Base, Tempo, and Polygon — illustrating the multi-chain, multi-currency direction the market is heading.

Integrating stablecoins into a payment product, however, is not simply a matter of accepting USDC at checkout. Compliance infrastructure — sanctions screening, anti-money-laundering controls, transaction monitoring — must be built before or alongside any stablecoin payment flow. Tempo's Jevgenijs Kazanins has argued publicly that banks cannot scale stablecoin payments without rigorous sanctions screening and fund-freeze capabilities, a position that's gaining ground as regulatory scrutiny intensifies. Solutions such as WalletConnect Pay now offer pre-settlement sanctions screening, indicating the compliance tooling layer is maturing rapidly.

---

## The Regulatory Landscape: GENIUS Act and Beyond

The United States passed the GENIUS Act in mid-2025, establishing the first federal framework for payment stablecoins. Five U.S. agencies — including the Federal Reserve and FinCEN — have since jointly proposed customer identification requirements for stablecoin issuers modeled on existing bank rules. The proposal would require issuers to verify the identity of holders at onboarding, bringing stablecoin customer due diligence broadly in line with the Bank Secrecy Act.

In Europe, MiCA (Markets in Crypto-Assets) created a licensing framework for electronic money tokens and asset-referenced tokens, but the crypto industry is already lobbying for a MiCA 2.0 that would address gaps around DeFi composability and cross-border stablecoin flows that the original regulation did not anticipate.

In Australia, OSL secured an Australian Financial Services Licence (AFSL) specifically authorizing wholesale stablecoin payments, custody, and OTC trading — a sign that regulated stablecoin infrastructure is being built jurisdiction by jurisdiction, rather than waiting for a single global standard.

The compliance argument is increasingly straightforward: stablecoin compliance infrastructure cannot wait for full regulatory clarity. Issuers that build AML and KYC controls now will be better positioned when rules solidify, while those that defer risk being locked out of regulated payment corridors entirely.

---

## Non-Dollar Stablecoins and Emerging Use Cases

The narrative that stablecoins are inherently "dollar instruments" is eroding. AllUnity's SEKAU (Swedish krona) joins a growing list of non-dollar stablecoins targeting regional treasury management, FX hedging, and local payment ecosystems. The euro-backed EURC from Circle and various pound-denominated experiments reflect demand from multinational firms that need to settle in local currencies without touching traditional correspondent banking.

Beyond currency pegging, stablecoin primitives are finding novel applications:

**Tokenized deposit hybrids.** Custodia Bank and Vantage are testing a token that toggles between a bank deposit and a stablecoin on Ethereum — maintaining FDIC-adjacent protection when the holder wants it, and on-chain composability when they don't. This architecture could become the template for how chartered banks enter the stablecoin market without abandoning deposit insurance frameworks.

**Real-world asset financing.** USDAI is using stablecoins to fund GPU loans for non-crypto AI cloud infrastructure, addressing a genuine financing gap in the AI buildout where traditional lenders lack the speed and flexibility operators require. This represents a maturation of the "RWA" (real-world asset) thesis: stablecoins as working capital, not just trading instruments.

**DeFi capital layers.** Protocol designers increasingly distinguish between stablecoins optimized for DeFi composability (where programmability and permissionlessness matter most) and those designed for institutional use (where regulated custody, clean yield structures, and AML compliance are non-negotiable). Products like USDf and fUSD are being explicitly positioned to serve both audiences without conflating them.

---

## Market Structure and Concentration Risk

USDT and USDC together account for the substantial majority of all stablecoin market capitalization, creating concentration risk that regulators and protocol designers have flagged repeatedly. Tether's reserve disclosures have historically been less granular than Circle's, though both have maintained their pegs through periods of significant market stress.

Token Terminal's redesigned stablecoin dashboards — tracking product mix, market share, and chain distribution by issuer — reflect growing investor demand for granular visibility into how stablecoin supply is distributed across chains and custody relationships. The fragmentation of stablecoin supply across Ethereum, Solana, Base, Tron, and other networks complicates both risk assessment and regulatory oversight.

FV Bank's launch of a unified fintech platform for stablecoins, payments, and programmable finance signals another trend: the convergence of banking services and stablecoin infrastructure into single products rather than parallel stacks that require bridging.

---

## Outlook

Stablecoins are no longer a crypto-native instrument being considered for mainstream use; they are mainstream payment infrastructure being formalized into regulatory frameworks. The coming years will be defined by several parallel contests: fiat-backed versus crypto-collateralized models, U.S. dollar dominance versus multi-currency expansion, and compliance-first issuers versus permissionless protocol designs.

Yield distribution — who earns the reserve carry and under what rules — will likely become a central regulatory and competitive battleground as stablecoins approach deposit-like scale. The institutions entering the space in 2025 and 2026, from Zelle to Fidelity to Shinhan Card, suggest that the answer will look more like regulated financial products than the bearer instruments early stablecoin pioneers envisioned. What remains to be determined is how much of the original permissionless architecture survives contact with that regulatory reality.
