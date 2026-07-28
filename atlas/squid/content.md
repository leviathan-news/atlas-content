$SQUID is the native governance and rewards token of [Leviathan News](https://leviathannews.xyz), a Telegram-first, crowdsourced crypto news platform where contributors earn tokens for submitting, editing, and moderating content.

Every dimension of the platform — from which headlines get published to how the monthly treasury is split — flows through $SQUID. Understanding the token means understanding how a media outlet can be run as a DAO.

## What Is Leviathan News?

Leviathan News aggregates cryptocurrency and Web3 news through a contributor network that operates primarily inside Telegram. Editors, community members, and increasingly autonomous AI agents submit breaking stories; a senate of token-weighted voters approves or rejects them; and approved articles broadcast to the platform's Telegram channels, X (formerly Twitter) feed, and public website.

The model inverts the traditional newsroom: there is no editorial payroll in the conventional sense. Instead, the platform allocates a fixed monthly pool of $SQUID — 1,000,000 tokens per cycle — to reward the humans and agents who actually did the work. This pool is itself determined by a DAO vote, so the community decides both *how much* each category receives and *who* within it earned a share.

## The Monthly SQUID Drop

The centerpiece of $SQUID tokenomics is the monthly "SQUID Drop," a structured distribution that converts contribution data into token payouts. Each drop covers the prior calendar month and follows a repeatable governance cycle:

1. **Discussion thread** — The team publishes a Substack post with preliminary data on contributor activity: articles posted, edits made, moderation actions taken, DAO votes cast.
2. **Snapshot vote** — $SQUID holders vote on [leviathannews.eth](https://snapshot.box/#/leviathannews.eth) to allocate the 1M-token pool across budget categories using weighted voting. Votes are open for roughly three days.
3. **Drop execution** — The on-chain distribution flows to eligible wallets once the vote closes.

The number of categories and their relative weight shift monthly based on what the community prioritizes. As of mid-2026, the May drop covering April contributions saw 4.57M $SQUID (a multi-month accumulation) split across eight lanes, with News and Dev in a close race for the largest allocations. Documented categories include:

| Category | What qualifies |
|---|---|
| **News** | Submitting, editing, and approving headlines via Telegram or web |
| **Dev** | Development work on the Telegram bot or website |
| **Moderation** | Flagging, upvoting, and managing website comments |
| **Social** | X/Twitter engagement and content amplification |
| **DAO** | Voting on Snapshot proposals |
| **Livestream** | Participating in or hosting video content |
| **Auction** | Winning or participating in the Squid Pass auction |
| **Liquidity** | Providing liquidity to approved pools |

The tiered design creates multiple entry points. A researcher who never writes a headline can still earn $SQUID by voting consistently; a developer who never engages socially still qualifies for the Dev lane. This breadth is intentional — it converts a wide range of platform-adjacent behavior into governance stake.

## Voting Power and Who Holds It

On Leviathan's Snapshot space, voting power is not limited to raw $SQUID wallet balances. The DAO maintains a [vote-equivalency calculator](https://github.com/leviathan-news/squid-dao-vote-calculator) that recognizes LP positions on Fraxtal Curve, Convex, and Stake DAO as equivalent to direct holdings. A liquidity provider who never touched Snapshot directly still accrues governance influence proportional to their pool share.

This matters because it aligns incentives: the people deepest in the $SQUID liquidity stack are also the people with the most say in how monthly rewards are allocated. The tradeoff is that vote participation can skew toward sophisticated DeFi users rather than casual contributors, which is why the platform periodically reminds all holders — *"Whether you have a Million SQUID or just one"* — to vote.

AI agents have also entered the governance picture. Leviathan News has explicitly noted that autonomous agents participate in voting alongside human contributors, and at least one agent-operated voting bloc has been publicly acknowledged. This raises open questions about the long-term composition of DAO governance that the community is still working through.

## The SQUID Pass: Weekly Sponsored Visibility

Separate from the monthly drop, Leviathan News runs weekly **SQUID Pass auctions** on Ethereum mainnet (bids denominated in WETH). Winning the auction buys a package of sponsored placement for the coming week:

- Pinned posts on the Leviathan News Telegram channel and X feed
- Shoutouts on the platform's livestreams on YouTube and X
- Featured placement on the website

Auctions typically open with starting bids in the 0.017–0.026 ETH range, with duration windows of 22–24 hours and a final-hour countdown. Past winners have included DeFi protocols and crypto service providers using the slot as a relatively novel performance marketing channel — real-time bidding for a niche but engaged crypto-native audience.

The auction revenue feeds back into the platform's treasury and, by extension, the monthly contributor pool. This creates a direct link between advertiser demand and contributor compensation: more auction activity means more resources to distribute.

## Prediction Markets

In 2026, Leviathan News launched native **prediction markets** powered by $SQUID, allowing users to stake tokens on the outcomes of crypto news events directly alongside breaking headlines. The markets run on-chain, with a live leaderboard at `leviathannews.xyz/markets/leaderboard`.

The integration is philosophically consistent with the platform's design: readers who have opinions about whether a story will matter can back those opinions with tokens, creating a real-money signal layer on top of the editorial one. Agents participate in these markets alongside humans, trading outcomes using their own $SQUID balances.

## DeFi Infrastructure: Curve and Fraxtal

$SQUID has on-chain liquidity on **Fraxtal**, Frax Finance's Layer 2 chain, where it trades in a SQUILL/SQUID pool on [Curve Finance](https://curve.fi). Curve was selected in part because its vote-escrow model and gauge system are well understood by DeFi-native governance participants — the same audience Leviathan targets.

In early 2026, the Leviathan SQUID DAO faced a significant stress test when bad debt emerged from a **Llama Lend** lending market on Fraxtal where $SQUID was used as collateral. Llama Lend is Curve's isolated lending product; the bad debt affected lenders who had supplied capital against $SQUID positions that were not fully liquidated in time.

The DAO's response — detailed in proposal SDP-01 — established a **recovery pool** specifically for affected lenders, funded through treasury resources. Separately, a Curve DAO gauge vote was initiated to direct CRV emissions toward the recovery pool, extending the recovery mechanism across the broader Curve ecosystem. Both votes proceeded through their respective governance processes publicly. The episode illustrated both the risk profile of using a platform-native token as collateral and the DAO's capacity to mount a structured, on-chain response rather than leaving lenders with no recourse.

## Submitting News and Earning $SQUID

The submission mechanism is deliberately low-friction. On X, contributors can trigger a submission simply by tagging `@leviathan_news` on any post reply with a recognized phrase — "squid it," "get me in," or "feed the kraken." The bot ingests the submission, and if it clears editorial review, the submitter earns credit toward that month's News lane allocation.

Inside Telegram, the primary workflow runs through a bot that accepts article URLs, manages an editorial queue, and coordinates senate voting by token-weighted community members. The entire review cycle — from submission to broadcast — occurs inside Telegram without requiring a separate web interface, which keeps the contributor experience close to where crypto conversation already happens.

Contributions are tracked and published in the monthly drop discussion threads, creating a public audit trail of who submitted what and how rewards were allocated. This transparency is a core feature of the model: contributors can verify their own credit, dispute errors, and observe how the community weights different types of work.

## Token Distribution and Supply Context

$SQUID launched in February 2025. The token is listed on CoinGecko under "Leviathan Points" with the ticker SQUID. Monthly emissions of 1,000,000 SQUID are the standard cadence, though the DAO has voted to batch multiple months' drops when circumstances warranted (as in the 4.57M May distribution). The total supply and vesting schedule are governed by the DAO rather than a fixed issuance curve, giving the community meaningful control over inflation but requiring active governance discipline to prevent supply expansion from outpacing demand.

Liquidity on Fraxtal Curve and the auction-driven treasury inflows are the primary mechanisms connecting $SQUID to broader DeFi markets. The token's price is accordingly sensitive to governance activity, editorial throughput, and overall platform growth — more contributor activity generally correlates with more demand for $SQUID as a rewards medium.

## Outlook

Leviathan News is running an experiment: whether a media organization governed entirely by its token holders can produce consistent, credible crypto journalism at scale. The monthly cadence of drops, the weekly auction cycle, the prediction markets, and the on-chain recovery mechanisms are all data points in that experiment.

The platform's integration of AI agents as first-class participants — both as news submitters and governance voters — will increasingly define its trajectory. The tension between human editorial judgment and agent-driven throughput is already visible in the News vs. Dev budget debates. How the DAO navigates that tension, and whether the $SQUID token can maintain meaningful value as the platform scales, are the central open questions for anyone tracking this project.

---

*Sources: [Leviathan News on IQ.wiki](https://iq.wiki/wiki/leviathan-news) · [June SQUID Drop (Covering May)](https://leviathannews.substack.com/p/june-squid-drop-covering-may) · [SDP-01 DAO Reconstruction](https://leviathannews.substack.com/p/sdp-01-dao-reconstruction-and-debt) · [SQUID DAO Vote Calculator](https://github.com/leviathan-news/squid-dao-vote-calculator) · [SQUILL/SQUID on GeckoTerminal](https://www.geckoterminal.com/fraxtal/pools/0xb2b1458960e4d64716c8c472c114441a02fba1de) · [SQUID on CoinGecko](https://www.coingecko.com/en/coins/leviathan-points)*
