Yearn is a Full Stack DeFi yield aggregator that automates capital allocation and market curation across lending and liquidity protocols through smart contract Vaults. Since creating the first DeFi Vault in 2020, Yearn has grown into one of DeFi's most battle-tested yield infrastructures, reaching over $8B in deposits, generating more than $300M in net profits, and processing billions in volume across Yearn Vaults and partner integrations.

Yearn's current evolution is defined by its modular ERC-4626 vault architecture which facilitates new cross-chain vault products, new governance and value accrual initiatives, and Flex, a new fixed-rate lending market. Yearn's codebase is the most proven DeFi vault architecture in the market, operating for nearly three years with more than 45,000 harvests across its ecosystem.

Beyond Vaults, Yearn has helped shape core DeFi infrastructure: creating the first DeFi security program, yAcademy, now yAudit; co-authoring the ERC-4626 vault standard; and building widely used tools such as Disperse, which has processed billions in volume.

---

## What Yearn Does

Most DeFi yield opportunities require constant attention: rates shift, incentives expire, and manually rebalancing across protocols is both time-consuming and gas-expensive. Yearn addresses this by pooling user deposits into **Vaults** — smart contracts that execute curated yield strategies on behalf of depositors. A user deposits an asset (say, USDC or ETH), receives a yield-bearing receipt token, and the vault handles the rest: allocating capital, harvesting rewards, compounding gains, and rebalancing as conditions change.

The protocol launched in July 2020, created by developer Andre Cronje with an unusual ethos: no venture capital, no pre-mine, no founder allocation. Its governance token, **YFI**, was distributed entirely to early liquidity providers over roughly ten days — a launch structure that made it a landmark event in DeFi history and influenced how subsequent protocols thought about fair launches.

## How Vaults Work

A Yearn Vault is a smart contract that accepts a single asset, delegates capital to one or more **strategies**, and issues depositors a proportional share token representing their claim on the pooled assets plus accrued yield. Strategies are modular pieces of code that interact with external protocols — lending markets, liquidity pools, staking contracts — to generate returns.

**V1 and V2 vaults** tied each strategy to a single vault in a one-to-one relationship. This worked, but made it difficult to diversify risk across multiple yield sources simultaneously and created tight coupling between vault logic and strategy code.

Yearn's current vault architecture (v3) makes every vault and strategy fully compliant with [ERC-4626](https://docs.yearn.fi/developers/v3/overview), the tokenized vault standard that Yearn developers helped draft. Strategies are now **Tokenized Strategies**: standalone ERC-4626 vaults that can plug into multiple parent vaults at once. The system uses an immutable proxy pattern, outsourcing standardized vault logic to a single implementation contract. This makes deploying a new strategy a relatively lightweight operation.

The design is intentionally **permissionless**. Anyone can write, deploy, and maintain a Yearn-compatible strategy without requiring endorsement from the core team. This shifts Yearn from a curated product into infrastructure — closer in spirit to Uniswap's open pool factory than to a managed fund.

## The YFI Token and Governance

**YFI** is Yearn's governance token, with a capped supply of 36,666 tokens. Holders vote on protocol parameters, strategy endorsements, treasury allocations, and structural changes to the DAO through on-chain proposals hosted on Snapshot.

For most of its history, Yearn experimented with various value-accrual models for YFI, including a vote-escrow system (modeled loosely on Curve's veToken design) that saw limited adoption. In late 2025, governance passed [YIP-88](https://gov.yearn.fi/t/yip-88-governance-overhaul-styfi/14552), a three-part overhaul that scrapped the veToken model and introduced **stYFI** — a staked version of YFI that entitles holders to 90% of all protocol revenue. At the time the proposal passed, Yearn was generating just under $200,000 per month in protocol earnings. The remaining 10% is directed to the DAO treasury for operations and contributor incentives, including a formalized pool of 1,700 YFI earmarked for long-term contributor retention.

stYFI launched in early 2026 and represents a meaningful shift in how Yearn aligns token holder incentives with protocol performance: rather than governance influence accruing to long-term lockers, revenue flows to anyone willing to stake.

## The Builders Collective and DAO Structure

Yearn operates through a distributed contributor model rather than a traditional corporate structure. The **Yearn Builders Collective** is an expansion of this model, aiming to onboard a wider pool of developers and protocol contributors under a structured incentive framework tied to the stYFI revenue stream. On-chain team management tooling has been rolled out to make contributor coordination more transparent and governance-linked.

The DAO's treasury holds a mix of YFI, stablecoins, and protocol-owned liquidity. Post-YIP-88, treasury management is more explicitly separated from protocol revenue distribution: stakers get revenue, the treasury gets a smaller allocation earmarked for operations, and contributor YFI allocations are structured as long-term retention rather than immediate issuance.

## Key Products and Integrations

Yearn's product roadmap centers on new cross-chain vaults like yvUSD, its Curve and Convex integrations, and an emerging institutional stack.

### yvUSD: Cross-Chain Stablecoin Yield

Launched in January 2026, **yvUSD** is Yearn's most ambitious product deployment to date. It is a [cross-chain V3 vault](https://blog.yearn.fi/yvusd-a-cross-chain-yearn-vault-for-stablecoin-yield) for USD-pegged assets — primarily USDC — that moves capital across chains exclusively through [native bridging infrastructure](https://blog.yearn.fi/yvusd) — no third-party or wrapped-asset bridges — via Circle's CCTP burn-and-mint mechanism for most chains, and Katana's native Polygon zkEVM bridge for deposits routed there.

The vault charges zero management fees and zero performance fees. It runs nine active strategies simultaneously, including leveraged looping approaches that automate compounding of external incentives. Depositors can choose between a standard redemption mode or a **Locked yvUSD** mode, which enforces a 14-day cooldown and a 7-day withdrawal window in exchange for an additional yield boost sourced from vault fee revenue. The locked mode is analogous to a CD in traditional finance — slightly less liquid, meaningfully higher yield.

yvUSD's cross-chain routing is architecturally notable: Yearn's TVL figures no longer map neatly to a single chain's on-chain data, and because the routing relies on native bridging rather than third-party bridge contracts, the residual cross-chain risk is narrower than it would otherwise be (see Security Model and Trust Assumptions below).

### Curve and crvUSD

Yearn's relationship with **Curve Finance** is one of DeFi's more durable partnerships. Curve's **Savings crvUSD (scrvUSD)** — a yield-bearing version of Curve's native stablecoin — was [built using Yearn's custom V3 Vaults](https://news.curve.finance/introducing-scrvusd/). The yield on scrvUSD is funded by a portion of the interest paid by crvUSD minters, with Curve DAO acting as a policy-setting body over the rate. Yearn provides the vault infrastructure; Curve provides the yield source and the stablecoin. This integration made Yearn infrastructure rather than a standalone product from Curve's perspective — a model that has since extended to other partners.

**Convex Finance**, which launched in 2021 specifically to accumulate Curve's veCRV voting power, emerged as a competitive pressure on Yearn's own Curve-focused strategies. Both protocols compete for the same Curve liquidity provider tokens that confer voting weight and fee revenue. Over time the two protocols moved from zero-sum competition toward selective coordination: the **Resupply Protocol**, a joint subDAO between Convex and Yearn, allows users to deposit yield-bearing stablecoin positions from Curve Lend and Fraxlend to source additional liquidity, with both protocols sharing in the resulting TVL.

### The Institutional Stack

On the institutional side, Birch Hill and Groma launched what they described as the first institutional on-chain REIT lending market, using a Morpho-Yearn stack to enable $150 million in tokenized real estate to back USDC loans. This represents a meaningful expansion of Yearn's vault infrastructure into real-world asset collateral — a category that was largely theoretical two years ago.

## Security Model and Trust Assumptions

Depositing into a Yearn Vault involves a layered set of trust assumptions that users should understand clearly:

1. **Smart contract risk**: Yearn's vault contracts, the individual strategy contracts, and any external protocols they interact with can contain bugs. Yearn's V3 vaults have been audited by firms including [ChainSecurity](https://www.chainsecurity.com/security-audit/yearn-v3-vaults) and MixBytes. V3's permissionless factory lets outside developers deploy their own vaults without Yearn's involvement, and those third-party deployments may not get the same scrutiny as Yearn's own; strategies hosted in Yearn's UI or attached to its vaults, by contrast, are role-gated and — per Yearn — pass an internal two-developer peer review plus a security-team review before launch ([security process](https://github.com/yearn/yearn-security)).

   Two incidents illustrate that this risk is non-theoretical. A February 2021 exploit drained roughly $11M from an early V1 DAI vault, though Yearn's security team recovered most of the remaining funds — 24 of 35 million DAI — within about 11 minutes ([disclosure](https://github.com/yearn/yearn-security/blob/master/disclosures/2021-02-04.md); [CoinDesk](https://www.coindesk.com/tech/2021/02/04/yearn-finance-dai-vault-has-suffered-an-exploit-11m-drained)). In November 2025, **yETH** — an LST-basket product on a standalone weighted-stableswap AMM codebase with its own team and structure, separate from the V3 vault line — suffered a roughly $9M infinite-mint exploit; about $3M moved through Tornado Cash before Yearn's post-mortem recovered 857.49 pxETH for pro-rata distribution ([Check Point](https://research.checkpoint.com/2025/16-wei/); [The Block](https://www.theblock.co/post/381740/yearn-finance-9-million-yeth-exploit-confirms-partial-recovery-outlines-remediation)).

2. **Strategy risk**: Each strategy interacts with external protocols. A failure in an underlying lending market or AMM pool affects Yearn depositors proportionally to their allocation.

3. **Governance risk**: Protocol parameters are changed through YFI holder votes. A governance attack or a low-participation vote could alter withdrawal conditions, fee structures, or strategy whitelists in ways unfavorable to depositors.

4. **Cross-chain risk**: Products like yvUSD route capital across chains using native bridging — Circle's CCTP burn-and-mint and Katana's native zkEVM bridge — not third-party bridge contracts. The residual exposure is narrower than typical wrapped-asset bridge risk, but not zero: message-relay reliability and reliance on Circle as a centralized USDC attestor remain.

Yearn publishes a [public security repository](https://github.com/yearn/yearn-security) with disclosure history and audit reports. The team has recently received new security reports covering stYFI specifically, and developer Wavey launched an automated bot to accelerate exploit investigation — a response to the broader trend of attackers leveraging AI to uncover novel vulnerabilities in DeFi protocols that traditional audits missed.

## Risks and Considerations

Beyond the technical risks above, Yearn operates in a competitive market for yield. Protocols like Morpho, Aave, Fluid, and Pendle each capture portions of the yield aggregation and structured-yield market with different technical approaches. Yearn's comparative advantage lies in its vault infrastructure quality, its integrations (Curve, Convex, emerging RWA stacks), and its brand as one of the oldest yield protocols in DeFi. Whether that advantage translates into sustainable TVL growth depends partly on continued product innovation and partly on maintaining a clean security track record — which the 2025 yETH exploit complicated.

The permissionless V3 design is a double-edged sword: it enables rapid ecosystem expansion and allows external developers to build on Yearn's rails without permission, but it also means the Yearn brand can be associated with third-party strategies over which the core team has limited control.

## Outlook

Yearn enters mid-2026 in a period of deliberate structural consolidation. The stYFI revenue-sharing model provides a clearer incentive alignment than any previous tokenomics iteration. The yvUSD cross-chain vault represents genuine product differentiation rather than incremental iteration. And the crvUSD savings integration positions Yearn vault infrastructure as a building block for other protocols rather than solely a consumer-facing product.

The near-term questions center on security — whether the AI-driven auditing paradigm the team is experimenting with can keep pace with increasingly sophisticated attacker tooling — and on whether the permissionless V3 ecosystem generates enough organic strategy development to grow TVL without centralized coordination. If both hold, Yearn's vault standard could become as foundational to yield infrastructure as Curve's AMM math became to stablecoin liquidity.

---
