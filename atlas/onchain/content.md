The term "onchain" describes any action, asset, or data recorded directly on a public blockchain ledger — permanently, transparently, and without requiring trust in a central intermediary.

Every financial system in history has faced the same tension: efficiency versus trust. Traditional banks clear transactions in batches, markets settle in two days (T+2), and reconciliation consumes entire back-office departments. Blockchains propose a different architecture — one where the ledger itself is the settlement layer, available to anyone, auditable by everyone, and open around the clock. Understanding what "onchain" actually means, and what it does not, is prerequisite knowledge for following any meaningful development in crypto today.

## What "Onchain" Means

When a transaction or piece of data is recorded onchain, it is written to a decentralized ledger maintained by thousands of independent nodes. No single party controls it, no single party can reverse it unilaterally, and anyone with an internet connection can verify it. The opposite is "offchain" — data or activity that exists in a private database, a centralized exchange's internal ledger, or a traditional banking system.

The distinction matters enormously in practice. When an exchange holds user funds internally without settling to a blockchain — as FTX did — users hold an IOU. When a decentralized exchange executes a swap onchain, the transaction is final the moment it is included in a block. The ledger is the receipt.

Blockchains store more than simple transfers. Smart contracts — self-executing code deployed onchain — can encode lending rules, governance votes, token distributions, and increasingly complex financial logic. Once deployed, that logic runs exactly as written, without human intervention at the point of execution.

## The Infrastructure Layer

Not all blockchains are the same, and the design choices differ meaningfully. Ethereum, the dominant platform for decentralized finance (DeFi), processes transactions using a proof-of-stake consensus mechanism. Solana prioritizes throughput and speed, aiming for sub-second finality — a property its advocates argue is essential for bringing professional trading infrastructure onchain. Solana's next growth phase, according to its foundation, could be driven by faster finality and programmable liquidity, positioning the chain at the center of onchain trading activity.

Base, Coinbase's Layer 2 network built on Ethereum's rollup architecture, targets everyday payments and consumer applications. Its positioning — "built for fast, onchain access" — reflects how the infrastructure layer is maturing from a developer curiosity into a product proposition aimed at mainstream users.

Canton Network, backed by Digital Asset, is purpose-built for institutional use and is where JPMorgan, Citi, Bank of America, Wells Fargo, and more than a dozen other banks are building shared tokenized deposit infrastructure, with a first-half 2027 launch target. The Clearing House, which processes over $2 trillion in daily settlements, is part of this consortium. The significance is not the technology itself but who is building on it — and what they intend to settle there.

## DeFi: Onchain Finance in Practice

Decentralized finance refers to financial applications built entirely on public blockchains. Lending, borrowing, trading, derivatives, and yield generation all occur through smart contracts that anyone can inspect. The key mechanisms include:

**Automated market makers (AMMs)**: Liquidity pools governed by mathematical formulas replace order books. Orca, the Solana-based AMM, describes its infrastructure as serving "the whole spectrum" from crypto-native assets to traditional finance assets coming onchain — a phrase that captures exactly where the space is heading.

**Lending protocols**: Aave is the largest onchain lending platform. Its founder, Stani Kulechov, has argued that Aave V4 has the potential to bring the $12.6 trillion repo market, $1.3 trillion margin lending market, and $4.6 trillion securities lending industry fully onchain. That claim deserves scrutiny — incumbents won't migrate voluntarily, and regulatory hurdles are substantial — but it illustrates the scale of what proponents believe is addressable.

**Perpetual contracts**: Hyperliquid is an onchain perpetuals exchange that has attracted significant volume. CFTC Chairman Mike Selig, speaking in June 2026, addressed the regulatory pathway for bringing decentralized perpetual contract platforms like Hyperliquid to the United States, stating that blockchain-based venues could be accommodated under existing or amended frameworks — a notable shift in regulatory tone.

## Stablecoins and the Onchain Payment Stack

Stablecoins are the connective tissue of onchain finance. USDC, issued by Circle, is the dominant dollar-denominated stablecoin on regulated, compliant infrastructure. Onchain stablecoin volume has reached $390 billion, according to recent industry figures — a scale that is forcing traditional financial institutions to take the technology seriously.

Banks wanting to participate in stablecoin payments face a specific constraint: they cannot simply pass raw blockchain transactions through their compliance systems. Sanctions screening, fund freezes, and AML controls are legal requirements, not optional features. Tempo's Jevgenijs Kazanins has argued that banks cannot scale stablecoin payments without these controls embedded at the protocol or middleware level — a tension the industry is actively working through.

The repo market example is instructive about how far this integration can go. Repo agreements — where institutions lend cash overnight against collateral like U.S. Treasuries — average $12.6 trillion in daily exposures and are among the most operationally intensive products in traditional finance. HIFI and DRW, with Marex as prime broker, recently settled a USDCx-denominated repo transaction on Canton Network against U.S. Treasuries, with automatic reversal at maturity. The transaction happened onchain. The collateral was real-world.

## Real World Assets: Bridging Ledgers

Real world assets (RWAs) are the tokenization of traditionally illiquid or privately held instruments — private credit, real estate, treasury bills, trade receivables — onto public or permissioned blockchains. The thesis is that tokenization unlocks programmability, 24/7 transferability, fractional ownership, and composability with DeFi protocols.

Kaia Investment Partners is bringing collateral-backed Korean private credit onchain via KaiaChain. Cap, a private credit protocol, is working through what it means to make loan origination and servicing truly onchain — including the uncomfortable reality that enforcement of defaulted loans still happens in courts, not smart contracts. Private credit onchain fixes some things (transparency, composability, settlement speed) while leaving others unchanged (legal recourse, credit underwriting).

Orca's contribution to the 2026 Internet Capital Markets report, co-authored with Tiger Research, maps how issuance, trading, and settlement are converging on a single public ledger — a development with profound implications for asset managers and custodians in Asia and globally. The core claim: capital markets workflows that once required multiple intermediaries and days of settlement can be compressed into a single atomic transaction.

## AI Agents and Onchain Identity

Artificial intelligence is entering the onchain stack in two ways: as a tool for security and auditing, and as an autonomous economic actor.

On the security side, AI-powered tools are making smart contract audits faster, cheaper, and more accessible. Historically, a formal audit required weeks and tens of thousands of dollars — a barrier that kept smaller projects under-reviewed. AI-assisted audit tooling is raising the baseline quality of code deployed onchain, though it does not eliminate risk. The exploit of MEV bot "jaredfromsubway" — drained of over $15 million in a suspected onchain attack — is a reminder that sophisticated actors operate in this space and that even well-known, battle-tested bots can be compromised. The incident raised fresh concerns about DeFi risk even among technically proficient participants.

On the agency side, Injective's platform gives AI agents an onchain identity through the ERC-8004 standard — described as "a passport for AI with portable reputation and a verifiable track record." Trading fees route back to agents programmatically. This is a nascent but structurally significant development: economic actors that are neither human nor corporation, operating transparently on a shared ledger, earning and spending autonomously. The implications for market microstructure, compliance, and liability are not yet resolved.

## Transparency, Privacy, and Tradeoffs

The permanent public nature of blockchains is simultaneously their greatest strength and a real operational constraint. Onchain investigator zachxbt traced $475,000 in frozen Bitcoin back to social engineering scams targeting elderly Americans by following the ledger — work that would have been impossible in a traditional banking system without law enforcement subpoenas. Transparency enables accountability.

But transparency also leaks information. Arc's structured financial memos add complexity and potential privacy tradeoffs to onchain transactions. Institutions managing large positions cannot always afford to broadcast their activity to competitors. Aptos Labs has launched Confidential APT on Aptos mainnet — opt-in privacy features that encrypt transaction amounts and balances while keeping sender and recipient visible onchain. This design preserves auditability while reducing front-running risk. The design space between full transparency and full privacy is where significant engineering effort is currently concentrated.

## Onchain Metrics and the Revenue Question

How do you measure the health of an onchain ecosystem? Token price is one signal, but it conflates speculation with utility. A more rigorous approach examines onchain fee revenue, unique active addresses, and transaction volume attributable to genuine economic activity rather than wash trading or bot arbitrage.

The Solana Foundation's research team has argued that revenue — real onchain fees paid by users for real services — is "crypto's new north star." Chains that fail to generate meaningful fee revenue risk losing builders and capital to platforms that do. The metric aligns incentives: high fee revenue requires genuine demand, and genuine demand requires useful applications.

User growth in specific protocols supports this framing. One token ecosystem reported growth from 69,000 unique wallets to over 506,000 unique traders in a matter of months — a signal of expanding participation, though distinguishing organic users from airdrop farmers requires deeper data analysis. The point stands: onchain data makes this kind of measurement possible in near-real time, without relying on company-reported figures.

## Regulatory Context

Regulators have historically struggled with onchain activity because it doesn't map cleanly onto existing categories. Is a liquidity pool a commodity? A security? An exchange? The CFTC's June 2026 signals around onchain perpetuals suggest regulators are moving toward engagement rather than blanket prohibition — a shift that, if sustained, would allow institutional capital to enter onchain markets through regulated structures.

The bank consortium's tokenized deposit infrastructure represents a different vector: regulated institutions building their own onchain rails rather than adapting to existing public chains. Whether these permissioned ledgers interoperate meaningfully with public blockchains, or become parallel systems, will shape the architecture of onchain finance for the next decade.

## Outlook

The direction of travel is clear: more of the world's financial activity will happen onchain, and the infrastructure to support it — faster finality, better privacy tools, AI-augmented security, compliant stablecoin rails — is being built now. The open questions are speed and distribution. Will the primary settlement layer be a public chain accessible to anyone, or a consortium of permissioned networks controlled by incumbent institutions? Will onchain AI agents operate under legal frameworks that don't yet exist? Will RWA tokenization deliver on its promise of democratizing access to private markets, or simply replicate existing gatekeeping in a new format?

What is not in question is the underlying mechanism: a shared, auditable, programmable ledger that executes without trusted intermediaries is a genuine technical innovation. How that innovation is governed, who gets access, and which use cases prove durable under real-world conditions — those are the questions the next few years will answer.

---
