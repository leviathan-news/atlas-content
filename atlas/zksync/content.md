A zero-knowledge rollup built on Ethereum, ZKsync uses cryptographic validity proofs to bundle transactions off-chain and settle them on L1 with full security guarantees — making it one of the most technically ambitious Layer 2 scaling projects in the ecosystem.

---

## What Is ZKsync?

ZKsync is a Layer 2 (L2) scaling protocol for Ethereum developed by Matter Labs. It was first deployed in 2020 as a simple payment network and has since evolved into a full smart-contract environment. Unlike optimistic rollups, which assume transactions are valid and rely on a fraud-proof challenge window, ZKsync uses **zero-knowledge proofs** (ZK proofs) — mathematical constructions that let a prover demonstrate the validity of a computation without revealing the underlying data.

This distinction matters for finality. On ZKsync, a batch of transactions is considered final on Ethereum as soon as the validity proof is verified on L1 — typically within minutes to a few hours, versus the seven-day withdrawal delay common on optimistic rollups. The tradeoff is computational cost: generating ZK proofs is intensive, though hardware acceleration and algorithmic improvements have reduced this burden significantly over time.

---

## How ZK Rollups Work

At a high level, ZK rollups operate in three stages:

1. **Sequencing** — Users submit transactions to an off-chain sequencer, which orders and executes them, producing a new state root.
2. **Proving** — A prover generates a succinct cryptographic proof (in ZKsync's case, a SNARK-based proof) attesting that the state transition was computed correctly.
3. **Settlement** — The proof and compressed transaction data are posted to Ethereum L1. The on-chain verifier contract checks the proof; if valid, the new state root is accepted.

Because the proof cannot be faked, the security of ZKsync ultimately inherits from Ethereum's consensus. No honest node needs to watch for fraud or run a full re-execution of every transaction. This makes ZK rollups attractive for applications that require fast, trustless finality — including financial infrastructure like tokenized deposits and cross-border payments.

---

## ZKsync Lite vs. ZKsync Era

ZKsync has operated two distinct networks simultaneously for most of its history.

**ZKsync Lite** (originally "ZKsync 1.0") launched in 2020 as a payments-focused chain supporting token transfers and simple swaps but not general-purpose smart contracts. It served as a proving ground for the underlying proof system and processed hundreds of millions of dollars in volume during Ethereum's peak congestion periods.

In May 2026, Matter Labs formally deprecated ZKsync Lite, consolidating the project around **ZKsync Era** as the single production environment. The phase-out was orderly: the first 100,000 withdrawal fees to Ethereum L1 were covered by the protocol, and user funds remained fully recoverable after the deprecation date. The migration is a milestone — it marks ZKsync's full transition from a narrow payments tool to a general-purpose smart-contract platform.

**ZKsync Era** (previously "ZKsync 2.0") supports the Ethereum Virtual Machine (EVM) with modifications. Developers can deploy Solidity contracts with relatively minor changes, and the network maintains compatibility with standard Ethereum tooling. Era has attracted a growing set of DeFi protocols, including **Aave** — which deployed its v3 lending markets on the chain — and Circle's **USDC**, which is natively issued on Era, removing the need for bridged wrapped versions.

---

## The ZK Stack and Elastic Chain Vision

Beyond Era itself, Matter Labs has built the **ZK Stack**: an open-source framework that lets any project launch its own ZK-powered blockchain using the same proof system that underpins Era. These chains can be configured as sovereign L2s settling directly to Ethereum, or as L3s settling to Era.

The broader ambition is the **Elastic Chain** — a network of interoperable ZK chains that share liquidity and communicate natively via ZK proofs rather than through traditional bridging. In this model, moving assets between two ZK Stack chains would eventually be as seamless as moving between accounts within a single chain, with cryptographic proofs guaranteeing correctness at each hop rather than relying on a multisig bridge committee.

This architecture positions ZKsync not merely as a single L2 but as a coordination layer for an ecosystem of specialized chains — each optimized for a particular use case (payments, gaming, institutional finance) while remaining connected to Ethereum's security and liquidity.

---

## Institutional Infrastructure: Prividium and the Bank Stack

The most consequential recent development in ZKsync's trajectory is its pivot toward regulated financial institutions. Matter Labs introduced **Prividium**, a permissioned deployment model built on the ZK Stack that gives banks and asset managers programmable compliance controls: whitelisting counterparties, enforcing jurisdictional rules, and maintaining privacy for transaction details while still settling proofs on a public chain.

This is the infrastructure behind the **Cari Network**, launched in 2025–2026 by a consortium of five U.S. regional banks. Cari uses ZKsync's Prividium rails to issue **tokenized deposits** — on-chain representations of bank deposits that remain FDIC-eligible and subject to existing banking regulation. The network targets the 24/7 settlement window that stablecoins currently provide but that regulated deposit institutions cannot offer through legacy rails. **BitGo** has partnered with ZKsync to build custody and transfer infrastructure for these tokenized deposit rails.

Matter Labs and Phylax have also introduced the **Bank Stack**, a reference architecture for financial institutions wanting to issue tokenized money and real-world assets (RWAs) with enforceable on-chain controls. The stack layers Prividium's compliance framework with standard EVM tooling, giving compliance officers the programmable rule-enforcement they require without forcing developers onto proprietary infrastructure.

This puts ZKsync in direct competition with Canton Network, a privacy-first institutional blockchain backed by Digital Asset. Matter Labs has been pointed in its criticism of bank-led private networks, arguing that systems without global rule enforcement lack the interoperability needed for open digital asset markets. The debate reflects a genuine architectural tension: permissioned chains optimize for compliance and privacy; public ZK chains optimize for censorship resistance and composability. Prividium's bet is that ZK proofs can thread the needle — providing the privacy institutions require while anchoring settlement to a permissionless L1.

---

## DeFi Ecosystem and Key Integrations

For retail and DeFi users, ZKsync Era is increasingly a live market with real liquidity.

**Aave** v3 on ZKsync Era enables lending and borrowing against major collateral types including ETH, WBTC, and USDC, with the same risk parameters and governance oversight as Aave deployments on other networks. The integration gives ZKsync Era a mature money-market primitive that DeFi applications can build on top of.

**USDC** native issuance by Circle on Era eliminates the smart-contract risk associated with bridged stablecoins, where users hold a wrapped representation backed by tokens locked in a bridge contract. Native USDC is minted and burned directly by Circle on the ZKsync Era chain, making it the canonical form of the asset on the network.

A range of DEXs, yield protocols, and infrastructure projects have deployed on Era, though the ecosystem remains smaller than Arbitrum or Optimism by total value locked. ZKsync's native account abstraction — which allows smart-contract wallets as first-class accounts, enabling features like gas payment in ERC-20 tokens and social recovery — provides a differentiated developer primitive that projects building consumer-facing applications have begun to leverage.

---

## Governance and the ZK Token

ZKsync has a native governance token, **ZK**, used to participate in on-chain governance of the protocol. The governance system has been migrating to a more robust on-chain infrastructure: recent development saw ZKsync governance launch an **Ethereum fee flow system** with on-chain smart contracts, routing a portion of sequencer fees through a transparent, governance-controlled mechanism rather than an off-chain multisig.

The protocol also navigated a transition in its governance tooling, moving away from Tally (a popular governance front-end) while keeping its staking pilot operational — a practical test of whether ZK token holders can actively direct protocol decisions rather than serving as a passive check on Matter Labs.

Decentralization of the sequencer remains an open roadmap item. Currently, Matter Labs operates the primary sequencer, which creates a liveness dependency on a single entity even if the validity proofs guarantee that no funds can be stolen. Progressive decentralization — allowing external parties to submit proofs and eventually sequence transactions — is a stated goal but not yet implemented at the protocol level.

---

## Security Considerations

ZKsync Era's security model is strong by L2 standards, but not without caveats.

The validity proof system ensures that the chain cannot post an invalid state transition to Ethereum — any attempt would fail the on-chain verifier. However, several other risk surfaces exist:

- **Bridge contracts**: In mid-2025, Lido paused the ZKsync wstETH bridge after a potential weakness was reported in the bridge endpoint contract. No funds were exploited, and wstETH holders on ZKsync were not affected, but the incident illustrated that bridge code — not the proof system itself — remains a common attack surface for L2 ecosystems.
- **Sequencer centralization**: A single sequencer can censor transactions or go offline. Users retain the ability to force-include transactions via L1 under ZKsync's escape hatch mechanism, but this requires on-chain interaction and costs more.
- **Upgrade keys**: Like most L2s, ZKsync Era's contracts are upgradeable, meaning a compromised upgrade multisig could theoretically alter the system. The governance system is being hardened, but upgrade key management remains a trust assumption.
- **EVM differences**: ZKsync Era is not byte-for-byte EVM-equivalent; it uses a custom virtual machine (zkEVM) that compiles EVM bytecode. Some low-level opcodes behave differently, which has historically caused subtle bugs in contracts ported from Ethereum without testing.

---

## Outlook

ZKsync enters a pivotal phase in 2026. The deprecation of Lite consolidates development effort on Era. The Elastic Chain roadmap, if executed, would make ZKsync a substrate for a diverse set of application-specific chains rather than a single generalist L2. And the institutional push — through Prividium, Cari Network, BitGo, and the Bank Stack — represents the most concrete attempt yet by any ZK rollup to capture regulated financial flows, not just crypto-native DeFi activity.

The key uncertainties are sequencer decentralization, proof generation costs at scale, and whether banks will commit to public-chain settlement (even a ZK-anchored one) once regulatory clarity arrives. ZKsync's technical foundation is among the most rigorous in the L2 landscape; whether that foundation translates into dominant market position depends on ecosystem growth, developer experience, and how the institutional-versus-decentralized tension resolves across the broader Ethereum scaling universe.

---
