The GENIUS Act — short for *Guiding and Establishing National Innovation for U.S. Stablecoins* — is the first comprehensive U.S. federal framework for regulating payment stablecoins, signed into law in 2025 after years of failed legislative attempts at governing digital dollar instruments.

---

## What the GENIUS Act Does

At its core, the law creates a licensing and reserve regime for "permitted payment stablecoin issuers" — companies that issue tokens pegged to the U.S. dollar and intended for payments, not investment. It does not cover algorithmic stablecoins or asset-backed tokens whose value floats.

Key provisions:

- **Reserve requirements.** Issuers must hold reserves equal to 100% of outstanding tokens in high-quality liquid assets: U.S. coins and currency, Federal Reserve balances, short-term Treasury bills, or Treasury-backed repurchase agreements. This is a harder constraint than most bank capital rules. J.P. Morgan Asset Management's JLTXX fund — a tokenized money market fund structured specifically to qualify as GENIUS Act-eligible collateral — illustrates how quickly Wall Street moved to supply compliant reserve instruments after the bill passed.
- **Interest prohibition.** Payment stablecoins cannot pay yield directly to holders. The law treats interest-bearing instruments as securities, not payments. Circle CEO Jeremy Allaire acknowledged the trade-off in March 2026, noting the real policy question has shifted to whether *distributors* — not issuers — can offer reward programs on top of compliant stablecoins.
- **Dual regulatory track.** Issuers can charter federally, falling under Office of the Comptroller of the Currency (OCC) supervision, or pursue a state license if their state's regime is "substantially similar" to the federal framework. Banks already regulated at the federal level may issue stablecoins under existing supervisory relationships.
- **Anti-money laundering baseline.** The act requires issuers to implement Bank Secrecy Act-equivalent AML and know-your-customer programs — a direct parallel to rules long applied to depository institutions.

## The Federal-State Tension

The dual-track structure is the act's most contested feature in its early implementation phase.

Bipartisan senators sent Treasury a formal letter urging the department not to freeze states out of the approval process for determining "substantial similarity" — the legal test that determines whether a state-licensed issuer can operate nationally. Their concern: if Treasury sets the bar too high or moves too slowly, state-chartered issuers face de facto federal preemption without a path to equivalence, chilling innovation and regulatory competition.

New York's Department of Financial Services responded proactively, releasing its first formal stablecoin regulations in mid-2026 to align its existing 2022 guidance letter with GENIUS Act standards, including explicit reserve limits. The proposal opened a 60-day public comment period. New York regulating the largest cluster of U.S. financial institutions makes its "substantially similar" determination a precedent-setting moment for the entire state track.

a16z, in a public letter to Treasury, argued that if state regimes diverge too far from the federal baseline, stablecoins issued under state licenses may not be treated as fungible equivalents of federally issued tokens — fragmenting liquidity and undermining the network effects that make payment stablecoins useful at scale.

## The AML Rule Dispute

The most technically contentious active rulemaking sits at the intersection of the GENIUS Act's AML mandate and how that mandate applies to on-chain stablecoin transfers.

Five U.S. regulators — Treasury's Financial Crimes Enforcement Network, the OCC, the FDIC, the Federal Reserve, and the NCUA — jointly proposed customer identification rules for payment stablecoin issuers, mirroring existing bank CIP (Customer Identification Program) requirements. Under the proposal, issuers would need to verify the identity of customers at onboarding, much as banks do when opening accounts.

The crypto industry broadly supports issuer-level CIP obligations. The dispute is about scope. Paradigm and the Hyperliquid Policy Center filed comments urging Treasury to narrow the rule's application to issuers and custodial intermediaries — not to decentralized protocols or smart contracts that settle transfers without taking custody of funds. Their argument: applying bank-style customer identification to on-chain settlement infrastructure is technically unimplementable and would effectively prohibit permissionless DeFi interaction with regulated stablecoins.

Consensys made a parallel filing, pushing the FDIC to narrow its proposed guidance on DeFi access and third-party yield arrangements. The concern is that overly broad "facilitation" language could sweep in front-end interfaces and protocol developers as regulated parties.

The Blockchain Association also submitted detailed comments to Treasury, drawing lines between custodial and non-custodial contexts and arguing the rule should track existing FinCEN money-services business guidance rather than importing bank charter obligations wholesale.

## Reserve Assets: A New Product Category

The interest prohibition creates an interesting market dynamic: stablecoin issuers need to earn yield on reserves to fund operations and distributor incentives, but holders cannot receive that yield directly. This makes the quality and liquidity of reserve assets commercially significant in a way they weren't when stablecoins were lightly regulated.

Coinbase's investment in ProShares' IQMM — billed as the first money market ETF specifically structured to satisfy GENIUS Act reserve requirements — signals that asset managers see a durable new market in GENIUS-compliant instruments. Morgan Stanley launched a stablecoin reserves portfolio targeting the same compliance need. J.P. Morgan's JLTXX is the highest-profile example, coming from a bank that manages roughly $4 trillion in assets and whose chairman Jamie Dimon has publicly endorsed blockchain infrastructure.

The OCC has separately designated Augustus Bank NA as a compliance flagship for GENIUS Act stablecoin and AI regulation — an early signal that the agency intends to use charter grants strategically to model compliant behavior.

## Systemic Risk and Political Flashpoints

Senator Elizabeth Warren raised concerns that X Money — Elon Musk's payments product — could operate under a carveout in the GENIUS Act's definition of "payment stablecoin," potentially allowing a large-scale dollar-pegged instrument to avoid the full regulatory framework. Warren's letters to Treasury flagged the structural similarity to a lightly regulated bank-like product operating at social-media scale, a risk profile she argues the act's drafters did not adequately address.

Treasury's implementation guidance will determine how broadly "payment stablecoin" is defined in practice. The depegging risk section of Treasury's early guidance acknowledged that reserve composition rules alone may not prevent runs if market confidence collapses — a lesson drawn from the 2022 TerraUSD collapse and the 2023 USDC temporary depeg during the Silicon Valley Bank failure.

## Market Scale and Adoption Signals

Stablecoin transaction volume reached ten consecutive quarters of growth as of mid-2026, with acceleration attributed partly to GENIUS Act passage creating regulatory certainty for enterprise adoption. That certainty matters most for large institutions: a $5 trillion asset manager building GENIUS-compliant custody infrastructure is a different kind of commitment than an offshore exchange listing a new token.

The convergence of TradFi settlement infrastructure with on-chain rails is measurable in the product launches above. Tokenized money market funds, GENIUS-eligible reserve portfolios, and OCC-supervised stablecoin charters all represent institutional capital allocating to an asset class that did not have a legal definition twelve months ago.

For enterprise payment teams, the practical consequence is that dollar stablecoin payments can now be structured as a regulated product with defined counterparty obligations, audit rights, and reserve verification — rather than a contractual promise from a crypto company. That is a qualitatively different risk profile for corporate treasury departments evaluating payment rails.

## Key Definitions Under the Act

**Payment stablecoin.** A digital asset designed to maintain a fixed value relative to a reference asset (the U.S. dollar), used primarily for payment or settlement, not investment. Yield-bearing instruments are excluded.

**Permitted payment stablecoin issuer.** An entity licensed under the GENIUS Act — either a federally chartered entity supervised by the OCC or a state-licensed entity under a substantially similar regime.

**Substantially similar.** The legal standard Treasury must apply to determine whether a state regulatory framework provides equivalent consumer protection, reserve requirements, and AML compliance to the federal baseline. The exact criteria are subject to active rulemaking.

**CIP (Customer Identification Program).** The bank-standard requirement to verify customer identity at onboarding, now proposed to apply to stablecoin issuers under the joint agency rule.

## Outlook

Implementation is now the dominant story. Treasury's "substantially similar" determination process will set the effective map of which states can run parallel licensing regimes — a decision with direct consequences for issuer geography, charter arbitrage, and DeFi protocol design. The AML rule's final scope will determine whether on-chain stablecoin settlement remains permissionless at the protocol layer or becomes subject to identity verification at every hop.

The interest prohibition will continue to generate creative product design: expect distributor-level reward programs, tokenized reserve instruments, and yield-bearing wrappers that sit outside the GENIUS Act's perimeter. Regulators will likely revisit that boundary once the market tests it.

What is not in dispute: the stablecoin era has a legal foundation in the United States for the first time. The debate has shifted from whether stablecoins will be regulated to how, and by whom.

---
