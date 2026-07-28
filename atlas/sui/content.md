A Layer-1 blockchain built by former Meta engineers, Sui is designed from the ground up for high throughput and low latency — using a novel object-centric data model and the Move programming language to target consumer-scale decentralized applications.

---

## What Sui Is and Where It Came From

Sui is a proof-of-stake Layer-1 network developed by Mysten Labs, a company founded in 2021 by engineers who worked on Meta's abandoned Diem blockchain project and its Move-based successor Novi. The network launched on mainnet in May 2023 and is named after the Japanese word for water, reflecting its design goal of flowing seamlessly around bottlenecks that have plagued earlier blockchains.

Its native token, **SUI**, is used for gas fees, staking, and governance. Unlike most smart-contract platforms that model blockchain state as a global key-value store, Sui treats assets as discrete **objects** owned by addresses. This distinction is not cosmetic — it allows unrelated transactions to be processed in parallel rather than sequentially, which is how Sui achieves claimed throughput figures in the hundreds of thousands of transactions per second on benchmarks, though real-world sustained throughput under adversarial conditions is lower.

## The Move Language and Object Model

Sui uses a variant of **Move**, a programming language originally developed at Meta specifically to make digital asset handling safer. Move encodes ownership rules directly into the type system, making an entire class of reentrancy and asset-duplication bugs impossible to write rather than merely easy to avoid.

The object model extends this: every asset on Sui is an object with an explicit owner (an address, another object, or the shared object pool). Transactions that touch non-overlapping objects can be certified and finalized without global consensus — a protocol called **FastPath** — enabling sub-second finality for simple transfers. Transactions that touch shared objects (like an AMM liquidity pool) go through full Byzantine fault-tolerant consensus via the Narwhal/Bullshark mempool/consensus engine.

This architecture directly addresses a core tradeoff in blockchain design: Solana achieves high throughput through a single global leader and aggressive hardware requirements, while Ethereum achieves security through slower, more redundant consensus. Sui attempts a middle path where parallelism is a property of data structure rather than of hardware.

## DeFi Ecosystem: Growth and Growing Pains

Sui's decentralized finance ecosystem grew quickly through 2024 and into 2025, with total value locked reaching multi-billion dollar levels at peak. The two most prominent protocols are:

**Cetus Protocol** — Sui's largest decentralized exchange by volume, using a concentrated liquidity model similar to Uniswap V3. Cetus has been central to Sui's DeFi narrative but also to its most significant security incident: in May 2024, an overflow vulnerability in Cetus's smart contracts was exploited for approximately $223 million in assets. Mysten Labs and Cetus validators controversially used Sui's governance mechanisms to freeze and recover a portion of the stolen funds, a decision that drew debate about the practical limits of blockchain immutability.

**Scallop** — a lending protocol on Sui. In mid-2025, Scallop froze the rewards contract on its sSUI spool after an exploit of approximately 150,000 SUI; core lending functions were reported unaffected. The incident illustrates that despite Move's safety properties, complex DeFi protocol logic remains an attack surface.

Sui also hosts **Hashi**, a cross-chain infrastructure project positioning Sui as an access layer for Bitcoin-held capital — claiming to enable $1.4 trillion in BTC to interact with DeFi through smart contracts and cross-chain automation.

**USDC** from Circle is available natively on Sui, providing the network's primary dollar-denominated liquidity. In late 2025, Sui also launched **USDsui**, a native stablecoin whose backing yield is committed to the ecosystem: the protocol uses yield from reserve assets to repurchase and burn SUI or deploy capital into DeFi liquidity pools, creating a designed deflationary pressure mechanic tied to stablecoin adoption.

## Institutional Access: Futures, ETFs, and On-Chain Compliance

Sui's institutional narrative accelerated materially in early 2025. **CME Group** — the world's largest derivatives exchange — announced in April 2025 that it would list SUI futures contracts beginning May 4, 2025, alongside Avalanche (AVAX) futures. This placed SUI in a small group of cryptocurrencies with CFTC-regulated futures markets, alongside Bitcoin, Ether, and Solana.

The significance is practical: institutional investors — hedge funds, pension allocators, proprietary trading desks — often require regulated, cash-settled derivatives to gain or hedge exposure without holding spot assets. CME listing signals sufficient liquidity and market maturity to meet the exchange's listing standards, and gives those investors a familiar instrument. Crypto.com and other venues also launched SUI and AVAX futures products around the same period.

On the equity side, **Grayscale** filed for a **Sui Staking ETF** (proposed ticker: $GSUI), which would hold spot SUI and pass staking yield to shareholders. The filing faced delays and questions about verification, and Grayscale's track record with altcoin ETF approvals is mixed. However, staking ETFs represent a structural shift from pure price exposure to yield-bearing crypto equity products — a category that regulators have been cautiously engaging with post-Bitcoin ETF approval in January 2024.

**Revolut**, the European fintech with over 45 million users, added SUI staking support in-app, reportedly adding approximately $200 million in market capitalization around the announcement. Retail staking access through fintech apps lowers friction considerably compared to native wallet staking.

**Chainalysis** added native support for SUI and its fungible tokens in 2025, enabling transaction monitoring, investigations, and fund tracing across the network. This is a prerequisite for many regulated exchanges and financial institutions to list or interact with any token. However, expanded surveillance tooling also raises concerns within the community about privacy — a genuine tension between compliance infrastructure and the permissionless ethos of public blockchains.

## Agentic Payments and AI Infrastructure

Sui co-founder **Adeniyi Abiodun** has publicly positioned agentic payments — cryptocurrency transactions executed autonomously by AI agents — as a primary target market for the network. The argument is structural: AI agents need to transact programmatically, at high frequency, with low cost and instant finality, without human confirmation loops that are native to traditional payment rails. Sui's sub-second finality and low gas costs make it a plausible candidate.

This thesis is being built out concretely. **Talus Protocol v1.0** launched on Sui mainnet in 2025, introducing verifiable AI agents that execute onchain with transparent, auditable action histories — described as a "closed mainnet" phase indicating early but live infrastructure. Separately, **SUI Group** (a distinct entity from Mysten Labs) announced a $15 million funding round in a company called Nof1 and made a strategic investment in Recursive Superintelligence, a further bet on AI/crypto convergence.

Sui also shipped a **Messaging SDK beta** to mainnet featuring end-to-end encrypted, wallet-linked chat — built on two of Sui's own infrastructure layers: **Seal** (threshold encryption) and **Walrus** (decentralized storage). The integration of encrypted messaging at the protocol level, linked to wallet identity, is an attempt to make Sui an application platform rather than just a settlement layer.

## Token Economics and Supply Risk

SUI has a total supply of 10 billion tokens, with a significant portion locked at genesis for the founding team, investors, and the Mysten Labs treasury. Token unlock schedules are a persistent structural concern for newer Layer-1s, and SUI is no exception.

In mid-2025, SUI was repeatedly cited in unlock risk analyses — one report flagged $643 million or more in scheduled unlocks across a cohort including SUI, Hyperliquid (HYPE), and ENA, with cliff-style releases (large one-time unlocks) alongside linear vesting streams. A separate tracker flagged $555 million in token unlocks in a single week, with SUI among the leaders alongside SOL and OMNI.

Cliff unlocks create predictable downward price pressure windows because early investors and team members may have held tokens at cost bases well below market price. The market pricing mechanism for known future supply is theoretically efficient, but in practice, actual sell execution by unlock recipients often creates observable short-term volatility.

SUI experienced a network **outage** that shut down block production for several hours — a significant event for a network positioning itself as production-grade infrastructure. The incident contributed to a price decline of over 5%. The causes and postmortem details matter for evaluating the reliability claims of any high-throughput blockchain.

## Competitive Position

Sui competes directly with **Solana** as a high-performance Layer-1 targeting applications that Ethereum cannot support at base layer economics. The comparison is direct enough that $SUI token is now accessible on Solana via bridging infrastructure, indicating cross-ecosystem liquidity demand.

Against Solana, Sui's differentiation arguments are architectural (Move vs. Rust/SVM, object model vs. account model) and ecosystem-stage (Solana has more mature DeFi, NFT, and meme coin liquidity; Sui has more architectural headroom, arguably). Against Ethereum, the comparison is latency and cost versus security and decentralization.

Avalanche (AVAX) is frequently paired with SUI in institutional contexts — both received CME futures listings simultaneously, and both are positioned as EVM-alternative smart contract platforms with enterprise ambitions. The pairing reflects a market categorization rather than deep technical similarity.

## Outlook

Sui's trajectory through 2025 reflects a network in late-infrastructure build-out: regulated derivatives markets established, institutional vehicles in filing, retail staking via fintech apps, compliance tooling integrated, and application-layer bets placed on AI agents and encrypted messaging. The network has demonstrated both its technical ambitions and its vulnerabilities — the Cetus exploit and subsequent governance intervention, the outage, and ongoing unlock overhang are real risks that any serious analysis must weigh.

The stablecoin strategy — native USDsui with yield-to-ecosystem mechanics plus USDC presence — is a meaningful DeFi building block. Whether the agentic payments thesis materializes as a growth driver depends largely on how quickly AI-native financial workflows become mainstream, and on whether Sui can maintain the reliability standards that use case requires. The network's institutional access story is more developed than most altcoins at a comparable stage, but competitive pressure from Solana and the continued dominance of Ethereum as a trust anchor means execution — on uptime, ecosystem liquidity, and developer retention — will determine whether Sui's architectural advantages translate into durable market position.

---
