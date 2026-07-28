The Ethereum Foundation (EF) is the Switzerland-based nonprofit that funds and coordinates core research and development for the Ethereum protocol — one of the world's largest blockchain networks by total value locked, developer activity, and stablecoin settlement volume.

---

## What the Ethereum Foundation Does

Founded in 2014 alongside Ethereum itself, the EF is not a company that owns or controls Ethereum. Its legal structure — a *Stiftung* (foundation) under Swiss law — is deliberately chosen to make it impossible for any single actor to "own" the network. The organization funds protocol research, client development teams, developer tooling, education initiatives, and ecosystem grants.

Key functions include:

- **Protocol research**: Teams working on cryptographic primitives, consensus design (proof-of-stake), and scaling approaches like rollup architecture.
- **Client diversity**: Supporting independent Ethereum execution and consensus clients (Geth, Nethermind, Besu, Lighthouse, Prysm, etc.) so no single implementation can become a single point of failure.
- **Grants**: Distributing ETH and fiat to external teams building infrastructure, security tooling, and public goods across the ecosystem.
- **Standards coordination**: Contributing to EIPs (Ethereum Improvement Proposals) — the formal process through which protocol changes are proposed, debated, and adopted.

What the EF explicitly does *not* do: it does not set monetary policy for ETH, it does not control who can deploy on Ethereum, and it does not direct the hundreds of independent companies — from DeFi protocols to stablecoin issuers to AI infrastructure projects — building on top of the network.

## Treasury and Funding Model

The EF holds a treasury composed primarily of ETH, which it has historically sold periodically to fund operations in fiat (USD, CHF). This model has drawn increasing scrutiny as ETH's price has underperformed relative to competing Layer 1 tokens during recent market cycles.

Critics, including researcher Dankrad Feist, have argued that the EF's relatively small ETH holdings and lack of ongoing protocol revenue create a structural misalignment: the foundation bears the cost of stewarding Ethereum but does not benefit proportionally from the network's growth the way economically aligned stakeholders would. Feist has called for a new, well-funded organization that holds meaningful ETH and remains directly accountable to the community.

The EF's response, articulated by co-founder Vitalik Buterin, is that the foundation will move toward selling *less* ETH going forward, extending the runway of its existing treasury rather than expanding the breadth of its activities. Buterin framed this as a shift toward long-term sustainability over short-term scope — a "smaller ship" operating with greater focus.

## Leadership Turnover and the 2025–2026 Restructuring

The most turbulent chapter in the EF's recent history has been a wave of senior departures that accelerated through late 2025 and into 2026. Eight senior staff members and both executive directors — including co-ED Hsiao-Wei Wang — have stepped down or departed amid an internal restructuring effort.

The departures are not all equivalent. Some reflect natural career transitions; others are tied to substantive disagreements about the organization's direction, including debates over the "CROPs" (Coordination, Research, Operations, and Protocol Support) mandate and how aggressively the EF should weigh in on Ethereum's competitive positioning relative to rival networks.

Buterin, in a widely-read post on X, acknowledged the changes while defending the rationale: the EF should remain a neutral steward of core technology and values, rather than pivoting to aggressively market ETH or compete on transactions-per-second benchmarks. "Ethereum won't race on raw speed and TPS alone," he wrote, a comment directed at critics who argue the network has ceded ground to Solana and other chains that have prioritized throughput.

Former EF contributor Trent VanEpps offered a more sobering read: he warned in mid-2026 that Ethereum could face a "slow-burning funding crisis" for core protocol development within three to nine months, citing the EF's reduced headcount and the absence of a clear replacement funding mechanism for the researchers and client teams who have depended on foundation grants.

## Governance: Who Speaks for Ethereum?

The leadership churn has reignited a long-standing question in the Ethereum community: who, if anyone, is responsible for Ethereum's strategic direction?

The EF's official position is that it is one node among many — an important one, but not the apex of a hierarchy. This is philosophically consistent with Ethereum's decentralization ethos. In practice, however, the EF has historically been the dominant funder of core research, making its choices functionally determinative for protocol direction even without formal authority.

Consensys founder Joseph Lubin, who co-founded Ethereum alongside Buterin, publicly dismissed crisis narratives around the departures. Lubin argued the organization's core mandate — stewarding Ethereum's protocol and values — remains intact, and that ecosystem companies are increasingly capable of funding their own development. He framed the EF's contraction as a natural and healthy evolution rather than a failure of governance.

Others are less sanguine. The tension Dankrad Feist identified — between an EF that prioritizes ideological neutrality and an ecosystem that wants a more economically aggressive posture — reflects a genuine strategic disagreement, not just a personnel story. Critics argue the EF's emphasis on the L2/rollup scaling roadmap (which reduced fees on Ethereum's base layer and therefore reduced ETH "burn" under EIP-1559) came at the expense of ETH's narrative as "ultrasound money," while competing Layer 1 networks pursued aggressive market share strategies.

Researcher William Mougayar offered a counterpoint: the EF's role is protocol stewardship, not price support. In a decentralized ecosystem, he argued, the ecosystem markets itself — expecting the EF to pump ETH conflates a nonprofit research body with a token treasury operation.

## Technical Context: What the EF Is Actually Building

Amid the governance noise, the EF's technical teams have continued shipping significant work. Recent research has focused on:

- **PBS (Proposer-Builder Separation)** and related MEV (maximal extractable value) mitigation to reduce centralization pressure on Ethereum validators.
- **Verkle trees** — a cryptographic data structure change that would dramatically reduce the state data Ethereum nodes need to store, lowering the hardware bar for running a full node.
- **SSF (Single Slot Finality)** — a consensus redesign that would allow Ethereum to achieve economic finality within a single ~12-second slot rather than the current ~15-minute finality window.
- **Blob scaling (EIP-4844 / Dencun)** — already shipped, this reduced data costs for rollups by roughly 10–100x, enabling the L2 ecosystem (Arbitrum, Optimism, Base, etc.) to scale transaction throughput at low cost.

EF researchers have also articulated the design philosophy behind Ethereum's consensus choices. One researcher recently explained publicly why Ethereum prioritizes continuous block production over "halts" — deliberately choosing a two-layer consensus design that preserves liveness even during major network disruptions, accepting slower finality in exchange for a chain that keeps producing blocks under adversarial conditions.

## Ethereum's Competitive Position and the Stablecoin Factor

The EF's internal debates take place against a backdrop of real competitive pressure. Ethereum remains the dominant settlement layer for stablecoins — USDC, USDT, DAI, and newer entrants collectively settle trillions of dollars annually on Ethereum and its L2s. Institutional interest in tokenized real-world assets and stablecoin infrastructure has grown substantially, with both traditional finance entrants and crypto-native projects choosing Ethereum's security model for high-value settlements.

AI infrastructure projects and data availability networks are also increasingly building on Ethereum's ecosystem, treating its rollup-native architecture as a foundation for permissionless compute markets. BitMine and similar crypto-native treasury strategies have also emerged as adjacent signals of ETH's expanding institutional appeal.

But stablecoin and institutional dominance has not translated cleanly into ETH price performance. Critics argue the Dencun upgrade — while technically successful — reduced fee revenue on the base layer, weakening the deflationary dynamics that underpinned the "ultrasound money" thesis. The EF's roadmap choices, in this reading, optimized for decentralization and scale at the expense of ETH tokenomics.

Buterin has pushed back on this framing, arguing that sound base-layer design and ETH value are not in tension over the long run, and that prioritizing short-term tokenomics over protocol correctness would be a category error for a nonprofit research foundation.

## The Funding Crisis Question

The most practically urgent question heading into late 2026 is whether core Ethereum development can remain adequately funded through the transition period.

Client teams — the developers maintaining execution and consensus software that actually runs Ethereum nodes — have historically relied heavily on EF grants. If EF grant budgets contract substantially and no alternative funding source scales up to replace them, the risk is not that Ethereum breaks immediately, but that maintenance work, security audits, and protocol upgrades slow down in ways that compound over time.

The Ethereum Protocol Guild, a collective of independent core contributors, and various client team fundraising efforts represent partial responses to this problem. But the scale of EF historical grants has been significant, and replacing that funding through decentralized mechanisms requires both coordination and willingness among large ETH holders and L2 operators to contribute.

Lubin's position — that ecosystem companies are increasingly mature enough to fund this work — is an optimistic read that assumes those companies see sufficient incentive to fund public goods rather than free-riding on EF spending. That assumption has not yet been stress-tested at scale.

## Outlook

The Ethereum Foundation's current moment is a stress test of its foundational design philosophy. A leaner, more focused EF with a smaller treasury drawdown rate is theoretically more sustainable — but only if the rest of the ecosystem fills the funding gap for core development that the EF deliberately created.

The leadership transitions and restructuring, while disruptive, have not produced any fundamental break in protocol continuity. Ethereum continues to produce blocks, process stablecoin settlements, and serve as the base layer for a large share of crypto economic activity. The technical roadmap — Verkle trees, SSF, continued blob scaling — remains ambitious and substantially resourced.

What remains genuinely unresolved is the governance question: whether a smaller, more neutral EF can maintain the coordination function the ecosystem needs to execute complex, multi-client protocol upgrades, and whether the broader community will develop the funding mechanisms to support the public goods work the EF has long underwritten. How that question is answered over the next twelve to eighteen months will shape Ethereum's competitive position as much as any technical upgrade.

---
