In decentralized governance, a "snapshot" is a record of token balances frozen at a specific block height, used to determine who can vote, who qualifies for an airdrop, or what an entity held at a moment in time. The word also names the most widely used off-chain voting platform in crypto, Snapshot, which has made the practice synonymous with how DAOs make decisions.

This page explains both senses of the term, how they relate, and why "snapshot" appears everywhere from governance proposals to exchange reserve reports.

## What a Snapshot Is

At its most literal, a snapshot is a point-in-time capture of on-chain state. Because blockchains record balances at every block, anyone can ask, "Who held this token at block N?" and get a deterministic answer. That answer becomes the basis for an allocation of rights or rewards.

Snapshots solve a specific problem: they prevent gaming. If eligibility were measured live, a user could borrow tokens, claim a benefit, and return them minutes later. By fixing the measurement to a block that has often already passed and is sometimes kept secret until after the fact, organizers ensure that only genuine holders at the relevant moment qualify. This is why airdrop and governance announcements frequently warn about "snapshot risk": once the block is mined, late buyers are excluded and sellers forfeit their claim.

Three uses dominate. The first is governance, where a snapshot sets each address's voting weight. The second is token distribution, where a snapshot defines an airdrop's eligible set. The third is auditing and attestation, where a snapshot freezes balances so a third party can verify them, as in exchange proof-of-reserves reporting.

## Snapshot the Platform

Snapshot (the platform, at snapshot.org and its newer snapshot.box interface) is an off-chain, gasless voting tool built by Snapshot Labs. It lets a DAO publish a proposal and collect votes without anyone paying gas, because votes are not transactions ([Snapshot docs](https://docs.snapshot.box/)).

The mechanism works as follows. When a member votes, their wallet produces a digital signature using the EIP-712 typed-data standard. That signature encodes the proposal ID, the voter's address, the chosen option, and a timestamp. Snapshot's backend verifies the signature, computes the voter's weight, and stores the signed message on IPFS, the InterPlanetary File System, so the record is content-addressed and publicly retrievable ([IPFS case study](https://docs.ipfs.tech/case-studies/snapshot/)). No on-chain transaction occurs, so there is no gas cost and no congestion penalty.

Voting weight is determined by "strategies," small modules that read on-chain data to assign power. The default strategy reads an ERC-20 balance, but strategies can also count NFTs, staked positions, vesting tokens, POAPs, or custom logic, and a space can combine several at once ([Snapshot docs](https://docs.snapshot.box/)). Each proposal pins a specific block number, the snapshot block, at which those balances are read. That block is the link between the platform's name and the underlying concept: a Snapshot vote is literally tallied against a balance snapshot.

The platform supports several voting types, including single choice, approval, weighted, quadratic, and ranked choice, plus basic for/against/abstain. Some spaces use shielded voting (via Shutter) to keep ballots encrypted until the window closes, reducing the bandwagon effect of visible early results.

Because Snapshot is off-chain, a passed vote is a signal, not an automatic execution. Most DAOs treat a Snapshot result as a binding mandate that a multisig or an on-chain governance module then enacts. This separation is the platform's defining trade-off: it is cheap, fast, and inclusive, but final settlement depends on a trusted execution step.

## How Snapshot Voting Works in Practice

A typical cycle illustrates the flow. SQUID DAO, the token-holder body that governs Leviathan News, runs a monthly distribution of its 1,000,000 SQUID emissions. Each month token holders and liquidity providers vote on Snapshot to decide how that month's rewards are split across contribution categories, such as headline submissions, shows, articles, development, and editing. The recurring "SQUID Drop" votes, like the May drop covering April contributions, open on Snapshot with a fixed close time, and holders cast weight proportional to their SQUID at the snapshot block. The result then drives the actual token distribution.

Larger protocols follow the same pattern at greater scale. In May 2026, Lido DAO ran a batch of live Snapshot votes covering an automated LDO buyback proposal (NEST), a node-operator assessment framework, a transition from GateSeals to a CircuitBreaker mechanism, and changes to Easy Track transfer limits. Orderly put its third governance proposal on Snapshot to simplify its revenue model, retire a buybacks wallet, burn 3.25 million ORDER, and redirect flows to growth, with staker rewards unchanged. Aave likewise routed a contested DeFi proposal through a Snapshot vote that has since closed.

These examples also surface Snapshot's social dimension. When Aave Labs submitted a proposal carrying a contributor's name without notifying them, the dispute centered not on the tooling but on process: critics argued that opening a Snapshot vote "while the community is still trying to have an open discussion" cuts against DAO norms. Snapshot makes voting frictionless, but it does not, by itself, guarantee deliberation. That remains a governance culture question.

## Governance Beyond a Single Vote

Snapshot sits inside a broader governance stack. A healthy process usually moves from forum discussion, to a temperature-check Snapshot poll, to a formal Snapshot vote, and finally to on-chain execution. Off-chain voting handles the high-frequency, low-stakes, and signaling decisions cheaply; on-chain voting reserves gas costs for binding treasury moves and contract upgrades.

The platform has been evolving toward closing the off-chain/on-chain gap. Snapshot Labs launched Snapshot X, a fully on-chain voting protocol that performs its computation on Starknet, an Ethereum layer-2, to make voting 10x to 50x cheaper than mainnet and proposal creation far cheaper still ([Starknet](https://www.starknet.io/blog/snapshot-x-onchain-voting/)). Snapshot X uses storage proofs, via an integration with Herodotus, to verify token balances across chains without bridging them, which lets a vote on one chain reflect holdings on another ([Snapshot Labs](https://snapshot.mirror.xyz/F0wSmh8LROHhLYGQ7VG6VEG1_L8_IQk8eC9U7gFwep0)). Snapshot Labs has also shipped interface upgrades, including custom domains for spaces, giving DAOs branded voting endpoints rather than a shared link ([Snapshot docs](https://docs.snapshot.box/)).

The relevance for readers is that "voting on Snapshot" increasingly spans a spectrum: pure off-chain signatures at one end, fully on-chain execution at the other, and hybrids in between. The underlying snapshot-of-balances concept persists across all of them.

## Snapshots and Airdrops

The same balance-freezing logic powers most airdrops. A project picks a snapshot block, records every eligible wallet's holdings or activity at that point, and distributes new tokens accordingly. Because the cutoff is fixed, an airdrop snapshot creates winners and losers in an instant, which is why coverage of campaigns so often pairs the word "snapshot" with "risk" or "hazard."

Recent examples show the range. IOST holders faced a thirteenth airdrop structured around snapshot-timed trading and a prolonged multi-round schedule that dilutes over time. Spacecoin's SPACE airdrop opened a second season with both vesting and snapshot timing as gating factors. Soft-launch campaigns such as AZZY pushed users to link wallets before a hard snapshot date, after which late participants would be excluded. The practical takeaway for holders is consistent: an airdrop snapshot rewards the state of your wallet at a block you may not know in advance, so behavior around rumored cutoffs carries real consequences.

Snapshots also mark the end of a token's life cycle. When a chain migrates or shuts down, operators take a final snapshot to lock balances for a successor. nilChain halted at block 222,000 and took a final snapshot to freeze accounts and balances ahead of a NIL migration claim process; missing the snapshot meant relying on a later, separate claim path. In a different vein, the Kelp protocol weighed using a pre-exploit snapshot as one of three options for socializing $292 million in losses, illustrating that a snapshot can also define a fairness baseline rather than a reward.

## Snapshots in Proof of Reserves

Exchanges and stablecoin issuers borrow the same technique for transparency. A proof-of-reserves (PoR) report takes a snapshot of customer liabilities and on-chain reserve assets at a stated date, then attests that reserves cover liabilities.

Binance, the largest crypto exchange by user count and volume, publishes monthly PoR reports keyed to a snapshot date. Its 43rd report used a June 1 snapshot showing user BTC holdings up 4.26% from May 1 to roughly 630,000 BTC, an increase of about 25,838 BTC. The 41st report, dated April 1, showed roughly 619,000 BTC, down 1.93% from March 1, alongside about 3.69 million ETH (down 4.6%) and about 35.1 billion USDT (down 3.68%). The month-over-month deltas are meaningful precisely because each figure is a snapshot at a fixed date, making consecutive reports comparable.

The PoR use case also exposes the limits of snapshots. A balance frozen on the first of the month says nothing about the other 29 days, and a snapshot of assets does not prove the absence of off-balance-sheet liabilities or borrowed funds staged for the audit. Industry commentary has argued that institutions "need more than a snapshot" for trustless reserves, and reports continue to flag that a verified balance is not the same as proven solvency. Treasury disclosures follow the same convention: periodic "treasury snapshot" updates, such as recurring foundation reports anchoring portfolio value at month-end, are explicitly point-in-time and should be read as such.

## Reading Snapshot Claims Critically

Because the word carries weight in announcements, a few habits help. First, identify which sense is meant: a governance balance cutoff, an airdrop eligibility cutoff, or an audit attestation. Second, find the exact block or date; a snapshot without a stated reference point is not verifiable. Third, ask what the snapshot omits. A governance snapshot ignores tokens acquired after the block; an airdrop snapshot can be gamed by wallet-splitting if no anti-Sybil logic accompanies it; a PoR snapshot reveals nothing between reporting dates. Treating any single snapshot as a complete picture is the most common error.

## Outlook

Snapshots are likely to remain foundational because they are simple, cheap, and verifiable, and because they map cleanly onto how blockchains already record state. The most consequential change underway is the narrowing gap between off-chain signaling and on-chain execution, as tools like Snapshot X push verifiable voting on-chain at lower cost and use storage proofs to read balances across multiple chains. Expect governance to keep layering forum debate, off-chain Snapshot polls, and on-chain finality rather than collapsing into one method. For holders, the enduring lesson is mechanical, not speculative: rights and rewards in crypto are frequently decided by your balance at a single block you do not control, so understanding when a snapshot is taken matters as much as what you hold.
