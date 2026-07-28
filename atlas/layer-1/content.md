A Layer 1 (L1) is the base blockchain itself — the settlement layer that defines its own consensus rules, validator set or miners, native asset, and the canonical record of every transaction ([Cyfrin](https://www.cyfrin.io/blog/what-is-a-layer-1-blockchain); [CoinMarketCap](https://coinmarketcap.com/academy/glossary/layer-1-blockchain)). Bitcoin, Ethereum, and Solana are the canonical examples.

Everything else in crypto — wallets, exchanges, decentralized applications, and even the "Layer 2" rollups that batch transactions — ultimately reports back to a Layer 1 for final settlement. Understanding what an L1 is, how the major ones differ, and where the design space is heading is foundational to reading any crypto news story.

## What "Layer 1" actually means

The "layer" framing describes a stack. The base layer is the blockchain that achieves consensus and stores state permanently; higher layers are protocols built on top to extend throughput or functionality without changing the base rules ([Built In](https://builtin.com/blockchain/layer-1-blockchain)).

A Layer 1 is responsible for the hard parts:

- **Consensus** — agreeing on a single ordered history without a central authority.
- **Settlement** — making transactions final and irreversible.
- **Data availability** — guaranteeing the transaction data exists and can be checked.
- **Native security** — paying validators or miners (usually in the chain's native token) to behave honestly.

When a project says it is launching a Layer 1, it is claiming to operate its own validator network and security budget rather than renting security from an existing chain. That is a far heavier lift than deploying an app or a rollup, which is why an L1 **launch** and the moment its **mainnet** goes live are treated as major milestones. *Mainnet* is the live, real-value network, as opposed to a testnet where tokens have no monetary value. Several entries in current coverage mark exactly this threshold — Naoris Protocol announcing its post-quantum mainnet is "live," and Aster celebrating the launch of Aster Chain.

## Consensus: how an L1 stays honest

The consensus mechanism is the single most defining choice a Layer 1 makes; it dictates the chain's speed, security model, energy use, and degree of decentralization ([Cherry Servers](https://www.cherryservers.com/blog/blockchain-layers-explained)).

- **Proof of Work (PoW)** requires miners to expend computation to add blocks. It is battle-tested (Bitcoin has used it since 2009) but energy-intensive and slow.
- **Proof of Stake (PoS)** selects validators based on the value of the native token they lock as collateral. Misbehavior can be punished by "slashing" that stake. PoS underpins Ethereum (since its 2022 Merge) and most newer L1s.

Many recent designs are variations on PoS. Pharos, set for listing on South Korea's Upbit, runs an "asynchronous BFT-based PoS" consensus; Conflux, a Leviathan News partner, uses a hybrid PoW/PoS model. Core's "Satoshi Plus" — being adopted by the Zcash-focused Z Protocol — blends Bitcoin mining with staking. The variety reflects an unresolved engineering question: how to maximize throughput without sacrificing the decentralization that makes a base layer trustworthy.

## The blockchain trilemma and the scaling problem

L1 design is constrained by what is commonly called the *blockchain trilemma*: the difficulty of simultaneously maximizing decentralization, security, and scalability. Pushing on one usually strains the others.

The numbers make the tension concrete. Ethereum's base layer processes roughly 15–30 transactions per second; Solana achieves several hundred TPS in practice against a much higher theoretical ceiling; Avalanche advertises thousands ([Cherry Servers](https://www.cherryservers.com/blog/blockchain-layers-explained)). Higher raw throughput typically demands more powerful validator hardware, which can shrink the validator set and concentrate control.

Two broad responses have emerged:

1. **Scale at Layer 1** — make the base chain itself faster through better consensus, parallel execution, or new cryptography. Solana, Sui, and Aptos take this route, betting that a single high-performance chain can serve mass-market applications. Coverage describing Solana's "speed advantages" and Sui as a "next-gen" chain for "internet speed" reflects this thesis.
2. **Scale at Layer 2** — keep the base chain conservative and move execution to rollups that post compressed proofs back to L1. This is Ethereum's dominant strategy.

The trade-off is live and contested. Some newer chains, like the "Zero" blockchain described in current coverage, argue that L2s only *claim* to inherit base-layer security and that doing the work natively on L1 is preferable.

## Ethereum, the EVM, and "onchain" gravity

Ethereum is the most consequential Layer 1 because of the **EVM** — the Ethereum Virtual Machine, the runtime that executes smart contracts. The EVM became a de facto standard, so "EVM-compatible" chains can run existing Ethereum applications and tooling with minimal changes. Much of current L1 activity is explicitly EVM-compatible: Pharos, Z Protocol, and others advertise compatibility precisely to inherit Ethereum's developer base and liquidity.

This is why so much value is described as living **onchain** — recorded directly on a blockchain's ledger rather than in a private database. Stablecoins such as **USDC** are a primary driver: they are tokens issued on L1s (and L2s) and have become the settlement asset for a large share of onchain volume. One sobering data point from recent coverage: through 2025, undifferentiated L1 and L2 tokens struggled as users consolidated and revenue increasingly flowed to stablecoins and derivatives rather than to base-layer tokens — a direct challenge to chains without a clear reason to exist.

Ethereum itself is not standing still. Researchers have outlined a roadmap to make the base layer verify blocks through zero-knowledge proofs rather than full re-execution, an effort associated with the "Lean Ethereum" initiative. Ethereum Foundation figures have suggested the chain could become a fully zero-knowledge-proof-based protocol within three to five years, which proponents argue would strengthen base-layer scalability and improve composability between Ethereum and its rollups ([The Block](https://www.theblock.co/amp/post/404185/ethereum-fully-zero-knowledge-proof-based-protocol-3-to-5-years-joe-lubin); [CoinDesk](https://www.coindesk.com/business/2026/01/11/ethereum-s-future-hinges-on-zero-knowledge-proofs-ef-director-says)). The L1-zkEVM work aims to let validators confirm blocks via succinct proofs, a path its backers tie to far higher throughput without abandoning decentralization ([Blockonomi](https://blockonomi.com/ethereum-plans-major-shift-to-zero-knowledge-proof-block-validation-in-2026)).

## Tokenomics: why the native token matters

Every Layer 1 has a native token, and its **tokenomics** — the supply schedule, issuance, fee model, and how value flows to holders — are inseparable from the chain's security. Validators are paid in the native token to secure the network; users pay transaction fees ("gas") in it; and in PoS systems, the token's value directly underwrites the cost of attacking the chain.

The hard question is *value capture*: does activity on the chain translate into durable demand for the token? Recent coverage is blunt that many chains failed this test in 2025 — "weak tokenomics and poor value capture left undifferentiated chains under pressure." Fee revenue migrating to stablecoins and derivatives, rather than accruing to L1 tokens, is a structural headwind. A token launch is easy; a sustainable security budget that the market is willing to fund over time is not.

## A diversifying landscape: specialization and new threat models

The current crop of L1 launches shows the category fragmenting from "general-purpose world computer" toward purpose-built and institution-grade chains:

- **Application-specific execution.** AFX launched a "sovereign" L1 optimized for onchain perpetual-futures DEXes, and Aster Chain is a privacy-first L1 purpose-built for derivatives using zero-knowledge techniques to hide positions while still settling onchain. The pitch is CEX-like performance in a decentralized stack.
- **Institutional and RWA settlement.** Canton Network positions itself as a privacy-preserving, institution-focused L1 used for repo settlement and tokenized real-world assets (RWAs), with large traditional-finance participants reportedly running production systems. Startale and SBI Holdings' Strium targets tokenized securities, and panels like Aptos's "Layer 1 as Basic Infrastructure in the Tokenization Era" reflect the same RWA thesis.
- **Bitcoin-anchored programmability.** Projects such as Stacks (where Zest Protocol launched Bitcoin vaults for BTC lending) and OP_NET's argument that Bitcoin needs native L1 smart contracts aim to extend programmability to the largest, most secure chain.
- **Post-quantum security.** A distinct cohort — Naoris Protocol and Diamante among them — is building L1s designed to resist future quantum computers that could threaten the cryptography securing Bitcoin and Ethereum. This is a long-horizon bet, but it shows the threat models L1 designers now weigh.
- **AI and payments rails.** Coverage points to demand for "financial-grade" L1s to underpin an emerging AI-agent economy, alongside payments providers (NHN KCP building a custom L1 on Avalanche) experimenting with their own base-layer infrastructure.

Not every story is a fresh launch. Movement, after a token-dumping controversy, is described as seeking "new life as a Layer 1" — a reminder that an L1's credibility depends as much on governance and token distribution as on raw technology.

## How to evaluate a Layer 1

For readers parsing the next L1 announcement, a few durable questions cut through the marketing:

- **What is its security model?** Who validates, how are they paid, and what does an attack cost?
- **Is it differentiated?** A general-purpose chain entering a crowded field faces the 2025 consolidation problem; a purpose-built chain needs a real user base in its niche.
- **Where does value accrue?** If fees and activity bypass the native token, the tokenomics may not sustain security long-term.
- **Is the mainnet actually live and open?** Invite-only or testnet-stage networks carry different risk than a permissionless, battle-tested mainnet.
- **What is the L1-versus-L2 stance?** Does it scale on the base layer, or lean on rollups — and does its security claim hold up?

## Outlook

The Layer 1 category is maturing into two divergent paths: a handful of large, general-purpose chains competing on performance and developer gravity, and a long tail of specialized L1s targeting derivatives, real-world assets, Bitcoin programmability, payments, and post-quantum security. The 2025 squeeze on undifferentiated tokens suggests the bar for launching a credible base layer is rising — durable value capture and a defensible niche now matter more than raw throughput claims. Meanwhile, Ethereum's zero-knowledge roadmap could reshape what "scaling Layer 1" even means over the next several years. Expect consolidation among me-too chains alongside continued experimentation at the institutional and specialized edges.
