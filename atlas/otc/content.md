Over-the-counter (OTC) trading in crypto refers to the direct, bilateral negotiation of large digital-asset transactions outside of public exchange order books — a market structure that now underpins a significant share of institutional crypto volume globally.

---

## What OTC Means in a Crypto Context

On a centralized exchange, every buy and sell order passes through a shared order book visible to all participants. OTC trading bypasses that infrastructure entirely. A buyer and seller — typically a large institution or high-net-worth entity on one side, and a specialized desk or market maker on the other — negotiate price, size, and settlement terms privately.

The term carries over from traditional finance, where OTC markets handle everything from foreign exchange to corporate bonds. In crypto, OTC desks emerged partly because exchange liquidity, even on the largest venues, is insufficient to absorb nine- or ten-figure trades without moving the market against the buyer. A fund attempting to acquire $50 million in Bitcoin through a public order book would reveal its intent, drive up the price mid-execution, and likely achieve a far worse average fill than a privately negotiated block trade.

OTC is distinct from derivatives trading, though the two intersect. Derivatives desks — contracts that derive value from an underlying asset — can also be traded OTC, away from regulated futures exchanges. Galaxy Digital's 2026 launch of an OTC prediction-market trading desk for institutions, seeded with a reported $10 million Kalshi trade, illustrates how the OTC format is extending beyond spot and vanilla derivatives into newer structured products.

---

## How OTC Desks Operate

A crypto OTC desk functions as an intermediary or principal. In the **agency model**, the desk finds a counterparty willing to take the other side of a trade and charges a spread or fee for the service. In the **principal model**, the desk takes the trade onto its own books and manages the resulting exposure — essentially acting as a market maker.

Execution typically follows a request-for-quote (RFQ) flow:

1. A client specifies asset, size, and desired settlement currency.
2. The desk streams a two-sided quote (bid/ask) valid for a short window.
3. The client hits the quote, and both sides confirm terms.
4. Settlement occurs — either bilaterally, through a trusted custodian, or increasingly via on-chain atomic delivery-versus-payment mechanisms.

Speed and confidentiality are the core value propositions. Because no order appears on a public book, the trade does not telegraph intent to the broader market.

Custody is a parallel concern. Liquid Mercury's decision to select **BitGo**'s Custody-as-a-Service (CaaS) platform to secure its OTC and real-world asset trading operations reflects the industry norm of pairing OTC execution with OCC-regulated custody — the same framework that governs bank-grade asset safekeeping in traditional finance.

---

## Why Institutions Use OTC

### Price Impact and Slippage

Large orders fragment public liquidity. Even on deep venues, a multi-thousand BTC purchase would absorb multiple order book levels, moving price against the buyer with each fill. An OTC desk pre-arranges a single price for the entire block, eliminating incremental slippage.

### Confidentiality

Public blockchains are transparent by design, but the negotiation phase of an OTC trade can remain private until settlement. Some desks offer additional settlement privacy through confidential transaction frameworks — a topic that surfaced at the FHE.org 2026 presentation, where confidential OTC trade on T-REX Ledger technology was discussed alongside the front-running risks that still exist in partially disclosed systems.

### Regulatory Fit

Institutions operating under fiduciary mandates need counterparties with verifiable compliance programs. OTC desks increasingly hold formal regulatory authorizations: **B2C2** secured a MiCA license in Luxembourg in 2026, becoming the first global OTC liquidity provider cleared under the EU's unified crypto framework. **OSL** secured an Australian AFSL covering wholesale stablecoin payments, custody, and OTC trading. **Kraken** received Dubai VARA authorization covering OTC among other services. These licenses give institutional clients the legal certainty their compliance teams require.

### Access to Illiquid or Pre-Market Assets

OTC channels also handle assets not yet listed on public venues, private allocations, and large secondary-market block sales by funds. On-chain investigators have documented this pattern extensively: Grayscale-linked addresses reportedly accumulated significant positions in **HYPE** via OTC desks including Wintermute, FalconX, and Coinbase. Multicoin Capital received over 338,000 AAVE tokens from a Galaxy Digital OTC wallet between October and November 2025. These flows are often only visible retrospectively through on-chain forensics.

---

## The Ethereum Foundation's ETH Sale — An OTC Case Study

One of the cleaner recent illustrations of institutional OTC mechanics involved the **Ethereum Foundation**, which finalized a sale of 10,000 **ETH** at an average price of $2,387 per coin to **BitMine**, the Bitcoin mining and treasury company led by Tom Lee. The transaction was structured as a direct OTC deal rather than a market sale — had the Foundation simply sold 10,000 ETH on spot exchanges, the order would have been visible, potentially triggering front-running and depressing the realized price. The OTC route allowed both parties to agree on terms privately and execute without market impact.

The episode also illustrates why OTC pricing is closely watched: a large seller transacting below the prevailing spot price can signal bearish conviction from an important holder, and the market interprets these deals as information. In this case, the ETH Foundation's willingness to sell and the price achieved became a reference point for sentiment analysis.

---

## Market Makers and Sentiment Signals

OTC desks are not passive conduits — they take views. **Wintermute**, one of the largest crypto market makers and OTC desks globally, publicly warned in mid-2024 that Bitcoin's rebound from the low-$60,000 range did not constitute a structural bottom, pointing to ETF flows, stablecoin data, and DAT (digital asset transfer) metrics as lacking a clear reversal signal. When a major OTC desk publishes macro commentary of this kind, it carries weight: the firm is continuously warehousing risk across spot and derivatives, meaning its stated view is grounded in real order flow, not speculation.

This market-making function connects OTC to broader crypto price discovery. Because desks intermediate large block trades, their aggregate positioning influences where prices clear. A desk that has absorbed significant long exposure will naturally hedge on public markets, creating feedback between private OTC flow and public price action.

---

## OTC in Derivatives and Prediction Markets

The product scope of OTC has widened considerably. Beyond spot and vanilla options, **Galaxy Digital** launched an institutional OTC prediction-markets trading desk in 2026, initially offering contracts tied to Kalshi markets. This segment — structured OTC access to event-contract payoffs — represents a genuinely new asset class for institutional desks, combining the high-margin bilateral negotiation model with the growing prediction-market infrastructure.

Separately, **Crossover** launched CROSSx Disclosed, positioning it as an institutional venue connecting participants to more than 30 OTC crypto market makers with customizable liquidity pools and fees starting from 0.5 basis points. The proliferation of such aggregation layers reflects that as the OTC market matures, institutional buyers want competition among desks rather than a single bilateral relationship.

---

## OTC's Role in On-Chain Data Markets

An underappreciated dimension of OTC is its role in data infrastructure. **SGX FX**, a technology provider for the institutional foreign-exchange ecosystem, integrated Chainlink's DataLink to bring OTC FX rate data on-chain — making the same benchmark rates that underpin trillions in global forex trading accessible to over 2,600 decentralized applications across 75+ blockchain networks. **Pyth** launched a similar data marketplace in 2026, with Fidelity, Tradeweb, Euronext, OTC Markets, SGX FX, and EDI publishing market data on-chain.

This convergence between traditional OTC pricing infrastructure and blockchain-native applications is a structural shift. DeFi protocols that use stale or thin on-chain prices as collateral oracles have historically been vulnerable to manipulation; piping institutional-grade OTC reference rates on-chain narrows that gap.

---

## Risks and Abuse Vectors

OTC's privacy features are also its principal risk surface.

**Regulatory opacity.** Before the current licensing wave, OTC desks operated in regulatory gray zones. Even today, unregistered desks operating in permissive jurisdictions may handle volume that would not pass compliance review on licensed exchanges.

**Lazarus Group and sanctions evasion.** North Korea's Lazarus Group — which blockchain intelligence firms estimate has stolen over $6 billion in crypto since 2017 — has used OTC desks as one node in its laundering infrastructure, alongside mixers and cross-chain bridges. The fact that settlement can occur off-chain, between pseudonymous counterparties, without automatic exchange KYC checks, makes OTC a persistent money-laundering vector. This is the primary reason regulators have been moving to bring OTC desks under the same AML/KYC frameworks as exchanges.

**Market manipulation.** OTC deals have also appeared in alleged manipulation schemes. ZachXBT's 2025 allegations around the $LAB token included accusations that insiders used OTC transactions to obscure supply control, private loans, and vesting changes while public markets were unaware of the full picture. The structural asymmetry — insiders transact privately while retail observers have only public data — is a recurring critique.

**Counterparty risk.** Without a central clearinghouse guaranteeing settlement, bilateral OTC trades depend entirely on the creditworthiness and integrity of the desk. The collapse of several crypto lenders and trading firms in 2022 left OTC counterparties exposed to significant unsecured losses. Regulated custodians like BitGo and exchange-backed desks have partially addressed this, but the risk does not disappear entirely.

---

## Regulatory Trajectory

The direction is clearly toward licensing and disclosure. MiCA in the EU, VARA in the UAE, AFSL in Australia, and equivalent frameworks in Hong Kong and Singapore are all extending exchange-style obligations — registration, KYC, AML programs, capital requirements — to OTC desks. HashKey Exchange in Hong Kong added OTC services for professional investors following its HKEX listing. The trend means the distinction between "exchange" and "OTC desk" is narrowing in legal terms, even as the execution model remains structurally different.

Pre-trade reporting requirements for large OTC trades — analogous to block-trade reporting in traditional equity markets — remain an open regulatory question in most jurisdictions. If implemented, they would significantly reduce the informational asymmetry that currently characterizes large crypto OTC flow.

---

## Outlook

OTC infrastructure is becoming a standard feature of mature crypto markets rather than an exotic workaround. The licensing wave underway across major financial centers is converting previously informal bilateral desks into regulated entities with defined capital and compliance obligations, while purpose-built custody providers like BitGo supply the settlement infrastructure required by institutions. At the same time, the product set is expanding — from spot block trades into structured derivatives, prediction-market contracts, and OTC-sourced reference data feeding DeFi protocols on-chain. As digital-asset allocations grow within traditional institutional portfolios, OTC volume is likely to scale proportionally, with price discovery increasingly split between the public order book and a parallel, privately negotiated layer that only becomes visible through on-chain forensics and regulatory filings after the fact.
