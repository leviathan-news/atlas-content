Cryptographic algorithms that underpin nearly every blockchain — from Bitcoin's secp256k1 signatures to Ethereum's ECDSA — are mathematically breakable by a sufficiently powerful quantum computer, making post-quantum cryptography the most consequential infrastructure upgrade the crypto industry has yet to fully attempt.

---

## Why Quantum Computers Threaten Blockchain Security

Modern blockchains secure assets through public-key cryptography. When you hold Bitcoin or Ether, what you actually control is a private key — a large number whose corresponding public key can be derived mathematically, but whose reverse derivation is considered computationally infeasible for classical computers.

Quantum computers change that calculus. Peter Shor's algorithm, published in 1994, demonstrated theoretically that a quantum machine with enough stable qubits could factor large integers and solve discrete logarithm problems in polynomial time — breaking RSA, ECDSA, and elliptic-curve Diffie-Hellman, the three families of asymmetric cryptography that blockchain wallets overwhelmingly rely on.

The threat is not that quantum computers can do this today. They cannot. Current systems — including Google's Willow chip and IBM's Heron processors — operate in the range of hundreds to low thousands of physical qubits, and breaking a 256-bit elliptic curve key would require millions of error-corrected logical qubits. But the cryptographic community's concern is forward-looking: adversaries can harvest encrypted data or blockchain transactions now and decrypt them later, once sufficiently powerful hardware exists. For blockchains, where public keys are permanently on-chain, the exposure is structural.

Post-quantum cryptography (PQC) is the field of designing classical algorithms — running on today's hardware — that remain secure even against quantum attacks. It is distinct from quantum cryptography, which uses quantum physics itself to transmit keys.

## The NIST Standards: A Baseline for Migration

The clearest external forcing function for the crypto industry arrived in December 2025, when the U.S. National Institute of Standards and Technology (NIST) published its final crypto agility guidance. The core message: systems must be able to swap out their cryptographic primitives without breaking. NIST had previously standardized three post-quantum algorithms — CRYSTALS-Kyber for key encapsulation and CRYSTALS-Dilithium (now ML-DSA) plus SPHINCS+ for digital signatures.

These are not theoretical exercises. BNB Chain released a post-quantum cryptography migration report documenting a live testnet upgrade using ML-DSA-44 — the NIST-standardized lattice signature scheme — for transaction signatures, alongside pqSTARK for consensus vote aggregation. The design preserved backward compatibility with existing infrastructure, though BNB's own testing noted a roughly 40% reduction in transactions per second, illustrating that post-quantum upgrades carry non-trivial performance costs.

NIST's crypto agility framing has influenced how newer chains approach architecture. CKB (Nervos) has cited being designed from day one for cryptographic agility, able to support arbitrary signature schemes via a flexible virtual machine rather than hardcoding assumptions at the protocol layer — a structural contrast with most legacy blockchains.

## Bitcoin's Specific Exposure

Bitcoin presents a particularly stark version of the problem. An estimated 25–30% of all Bitcoin supply sits in addresses whose public keys are permanently exposed on-chain — either because the address reuses a P2PK format that reveals the public key directly, or because a transaction has already been broadcast that exposes it. Anyone who has ever spent from an address has revealed their public key.

Post-quantum security firm Project Eleven published a widely-discussed report warning that quantum computing could threaten BTC wallet security by 2030. BitGo CEO Mike Belshe pushed back, arguing the timeline is overstated and that the larger risk is coordination: even if a migration path exists technically, getting millions of users, exchanges, and custodians to move funds to quantum-resistant addresses in a coordinated window is an unprecedented social and logistical challenge.

MicroCloud Hologram has explored quantum key distribution approaches for Bitcoin, though upgrade uncertainties at the protocol level remain unresolved. Zcash has set a more concrete target, aiming for a post-quantum cryptography milestone by 2027.

The coordination problem Belshe identifies is real and underappreciated. Bitcoin governance moves by rough consensus, and any hard fork to mandate quantum-resistant signatures would need to address millions of dormant or abandoned coins — including those attributed to Satoshi Nakamoto — whose owners cannot migrate. Coinbase's Quantum Advisory Council addressed this directly, examining how a post-quantum migration should treat abandoned coins whose private key holders may no longer exist to participate in any migration.

## Ethereum's Upgrade Path

Ethereum's post-quantum situation is technically better than Bitcoin's in one respect: the roadmap discussion is more active and the developer surface for experimentation is larger. Researcher "Nico" published a proposal arguing that post-quantum account protection can be deployed today without a hard fork, at a cost of approximately $0.07 per account, with the approach undergoing further security audits.

On the signature verification side, the SPHINCS+ algorithm — one of NIST's standardized schemes — has been demonstrated verifying post-quantum Ethereum signatures at 127,000 gas, without requiring any precompile or protocol change. This matters because it means applications could begin experimenting with PQC signatures within the existing EVM execution environment today, rather than waiting for a consensus-layer upgrade.

The deeper challenge is at the protocol level itself, where Ethereum's consensus and execution layers both rely on BLS12-381 elliptic curve operations. Migrating those is a harder problem. Succinct Labs released VEIL, a compiler designed to address one component: Succinct's SP1 proving system — the ZK infrastructure Google used for generating ZK proofs in certain workloads — relies on a Groth16 wrapper that has an elliptic-curve dependency. VEIL swaps that dependency for a hash-based post-quantum scheme, representing a meaningful step toward quantum-resistant ZK proof systems.

CertiK, the blockchain security firm, has published separate research on post-quantum signature schemes, focusing on practical risks in scaling from tree-based signature schemes like SPHINCS+ to larger forest-based constructions — a niche but important engineering concern as signature sizes in hash-based schemes are substantially larger than ECDSA, which has throughput implications at scale.

## Chains That Have Moved First

Several chains have announced or shipped post-quantum capabilities ahead of the broader migration:

**Aptos** has gone furthest among large layer-1 networks in publicly claiming production readiness. Post-quantum signatures are reported live on Aptos, and Coinbase's Quantum Advisory Council characterized the chain as "well-positioned for the transition to post-quantum secure transactions." Aptos uses the Move language and was architected more recently than Ethereum or Bitcoin, giving its developers more design freedom.

**NEAR Protocol** has published a technical roadmap for post-quantum preparation, framing it as an infrastructure challenge the ecosystem is actively solving.

**Blockstream** has included a post-quantum security push in its Liquid Network roadmap, alongside zero-confirmation payment work and BitVM research, signaling that sidechains and second-layer systems are also in scope.

**Algorand** saw its token spike and then retrace during a brief "post-quantum rally" in mid-2025, illustrating how market participants have begun pricing post-quantum credibility into asset valuations — though such moves are often speculative and disconnected from technical delivery timelines.

**BNB Chain** completed testnet validation of its post-quantum upgrade but saw TPS decline approximately 40%, a result that will require engineering work before mainnet deployment.

At the application and wallet layer, a first-generation of post-quantum MPC wallets has launched — one developed with Eigen Labs as an early supporter — and crypto wallet providers broadly are accelerating post-quantum research in response to rising awareness of the risk.

## The Crypto Agility Imperative

NIST's December 2025 guidance introduced "crypto agility" as a first-class design principle: the idea that systems should be upgradeable at the cryptographic layer without requiring wholesale replacement. This reframes the question from "which post-quantum algorithm should we use" to "can our system swap algorithms without breaking?"

For most legacy blockchains, the honest answer is no — or at least, not without significant coordination cost. Elliptic curve assumptions are baked into the signature scheme, the key derivation path, the address format, and sometimes the consensus mechanism. Unwinding those requires hard forks with all the governance friction they entail.

Newer chains with more flexible virtual machines, pluggable signature verification, or account abstraction (which can allow smart-contract wallets to define their own signature verification logic) are structurally better positioned. Ethereum's ERC-4337 account abstraction standard, for instance, creates a path where individual smart accounts can implement post-quantum signature verification without a protocol-level change.

NEAR's approach leverages a similar flexibility. STRK20s, a privacy-focused protocol launching with post-quantum security, represents the application layer beginning to ship PQC features to end users, not just researchers.

## Sizing the Actual Risk Window

Honest estimates from cryptographers vary significantly on when a "cryptographically relevant" quantum computer might exist. Google's Willow chip in late 2024 was a genuine engineering milestone but operates in a regime far from breaking elliptic curve cryptography — by most technical estimates, a machine capable of attacking Bitcoin's secp256k1 would need fault-tolerant logical qubits in the millions, not the hundreds of physical qubits that exist today.

The relevant planning horizon is roughly a decade — long enough that acting now seems premature to some, short enough that infrastructure systems should be in migration by the end of the current decade. Bitcoin's blockchain and Ethereum's state are permanent; public keys revealed in 2015 are still on-chain in 2026 and will be in 2035. The asymmetry of that exposure is what makes the problem urgent despite the hardware being years away.

## Outlook

The post-quantum transition in crypto is no longer hypothetical or distant — it is an active engineering and governance project across the industry. NIST's finalized standards provide the cryptographic foundation. Early movers like Aptos and BNB Chain have demonstrated that post-quantum signatures can be deployed in production blockchain environments, with documented trade-offs. Ethereum's research community has outlined low-friction near-term options, and zero-knowledge proof systems are beginning to shed their elliptic-curve dependencies.

The harder problems remain coordination and performance. Bitcoin's enormous installed base of exposed public keys, the throughput costs of larger post-quantum signature schemes, and the governance challenge of executing hard forks across decentralized networks are not solved by algorithm selection alone. Coinbase's advisory council framing — treating abandoned coins and coordination failure as the central risks, not hardware timelines — is likely the correct lens for the next five years.

Chains that have built cryptographic agility into their architecture from the start are best positioned. Those that did not face a decade of migration work, and the governance negotiations that come with it.

---
