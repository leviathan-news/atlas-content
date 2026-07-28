A specialized DeFi risk research firm operating at the intersection of protocol governance and quantitative finance, LlamaRisk has become one of the most influential independent risk managers in the Ethereum ecosystem — holding mandates across Aave and Ethena, and formerly Curve Finance.

---

## What LlamaRisk Does

Risk management in decentralized finance is not a single discipline. It spans collateral assessment, oracle integrity, liquidity modeling, regulatory analysis, and governance participation. LlamaRisk positions itself as a full-stack risk partner: it produces public research, submits governance proposals, sits on risk committees, and in some cases builds the infrastructure — oracles, monitoring tools, analytical frameworks — that protocols use to protect themselves.

The firm operates differently from a traditional auditing shop. Rather than one-time code reviews, LlamaRisk embeds in protocol governance over multi-month or multi-year terms, giving it longitudinal visibility into how risk evolves as markets, collateral types, and code change. That continuity is a meaningful structural advantage in an industry where the threat surface shifts constantly.

## The Curve Finance Partnership

LlamaRisk's longest-running mandate was with Curve Finance, Ethereum's stablecoin and pegged-asset liquidity protocol. Curve was the firm's first client, in 2022, and became its longest continuous engagement. The Curve DAO renewed the partnership in April 2026 with [the intent to serve through April 2027](https://gov.curve.finance/t/llamarisk-services-proposal-april-2025-2026/10489), but LlamaRisk [concluded the engagement early, effective June 30, 2026](https://gov.curve.finance/t/llamarisk-concluding-our-curve-engagement/11090) (announced May 29), to concentrate on its expanded, sole-provider mandate at Aave — "a structural decision about where LlamaRisk concentrates its resources going forward, not a reflection of our view of Curve." The transition covered five workstreams: LlamaLend v1 deprecation, impaired-market resolution including sDOLA, LlamaLend v2 preparation, emergency-control recommendations, and knowledge handoff to Swiss Stake; and LlamaRisk returned unused crvUSD and post-June CRV vesting to the DAO treasury. The Curve DAO opened a call for successor risk teams that July.

The scope is broad. In Q3–Q4 2024 alone, LlamaRisk drove 26 active governance proposals and helped administer a 250,000 OP grant from the Optimism ecosystem. On the product side, the firm worked directly on crvUSD — Curve's native stablecoin — including reviewing peg-defense mechanisms during periods of "unusually severe" market conditions and publishing analysis on which monetary policy configurations best protect borrowers.

A notable example of applied research: LlamaRisk's examination of Curve's LlamaLend platform identified that the Quadratic variant of the Semilog Monetary Policy best balanced market performance with user protection — a recommendation grounded in empirical market data rather than theoretical preference. The firm also produced a post-mortem on the LlamaLend sDOLA exploit, attributing the incident to unsmoothed vault oracle reads. A $190,000 donation inflated the price-per-share by 13.79%, triggering hard liquidations for 27 borrowers. The technical specificity of that finding — tracing the damage to a single oracle design choice — illustrates the depth LlamaRisk brings to incident analysis.

LlamaRisk was also active on crvUSD expansion, formally proposing the onboarding of Frax's frxUSD stablecoin as a PegKeeper asset for crvUSD with an initial $3 million debt ceiling, and separately proposing disabling all gauges in the Elixir marketplace. Each proposal represents a direct governance action with protocol-level consequences, not just advisory commentary.

Jointly with Pangea, LlamaRisk identified that structural flows from Curve's YieldBasis product tightly coupled the crvUSD system to Bitcoin price movements, with a 1% BTC move able to trigger roughly [$3.51 million in crvUSD sales](https://blog.pangea.foundation/scaling-yieldbasis-to-1bn/). LlamaRisk proposed scaling the credit line from $300 million toward $1 billion in phased increments, starting with an $80 million initial tranche, to balance YieldBasis's growth against Curve's credit exposure.

## Aave: Scaling the Mandate

The other major pillar of LlamaRisk's work is Aave, the dominant decentralized lending protocol. What began as advisory engagement has grown into a [formal, renewed mandate](https://governance.aave.com/t/llamarisk-ensuring-continuity-of-aaves-risk-management/24397) covering the full Aave protocol fleet — including Aave V3, V4, and Aave Horizon, the protocol's institutional lending product.

The scope of the Aave relationship reflects how protocols think about risk as they scale. Rather than treating each deployment independently, LlamaRisk has proposed a unified risk framework designed to standardize asset evaluation and provide protocol-wide oversight across all versions. That kind of systemic view matters especially as Aave operates across multiple chains and serves increasingly heterogeneous collateral types.

The firm's incident modeling has been particularly prominent. When the Kelp rsETH bridge was exploited, LlamaRisk modeled potential bad debt exposure between $123 million and $230 million across Layer 1 and Layer 2 scenarios — a range that reflected genuine uncertainty about how the exploit would propagate through Aave's liquidation mechanics. The analysis informed emergency freezes, rate changes, and coverage planning. A full incident report followed, detailing the exploit mechanics, Aave's response, and recommendations to contain protocol risk and protect users.

On the product development side, LlamaRisk published research on the Aave V4 Reinvestment Controller — a mechanism designed to improve capital efficiency by deploying idle reserves into yield-generating strategies. The firm also analyzed GHO, Aave's native stablecoin, examining its backing composition and its growing integration with real-world assets. Separately, LlamaRisk released a preliminary analysis of the GENIUS Act, a proposed U.S. stablecoin regulatory framework, concluding that GHO does not qualify as a "payment stablecoin" under the act's statutory definition — and recommending that Aave maintain GHO's current architecture rather than restructure it to fit the regulatory category.

## Aave Horizon and Real-World Assets

One of the more forward-looking areas of LlamaRisk's work is Aave Horizon, the protocol's dedicated lending environment for tokenized real-world assets (RWAs). Horizon reached $550 million in deposits as RWA lending surged, and LlamaRisk has been building risk infrastructure alongside that growth.

The centerpiece is LlamaGuard NAV, a next-generation oracle for tokenized RWAs built in collaboration with Chainlink and Aave Labs. Traditional price oracles are designed for liquid, continuously traded assets. Tokenized RWAs — which might represent treasury bills, private credit, or real estate — have different pricing dynamics: infrequent valuations, legal risk dimensions, and redemption mechanics that don't map cleanly onto spot price feeds. LlamaGuard NAV addresses this by delivering dynamic, risk-adjusted net asset value feeds with automated safeguards, setting a new technical standard for how DeFi lending can safely accept RWA collateral.

The firm also published a legal risk cartography of tokenized RWAs — a taxonomy of the legal risks embedded in different asset structures, jurisdictions, and issuer arrangements. That kind of cross-disciplinary work, combining legal analysis with DeFi protocol design, is relatively rare and speaks to the breadth of competency LlamaRisk has built.

## The Ethena Risk Committee

Beyond Aave, and following its former Curve engagement, LlamaRisk has secured a [fourth consecutive term](https://gov.ethenafoundation.com/t/ethena-risk-committee-elections-fourth-term-results/750) on the Ethena Risk Committee. Ethena is the issuer of USDe, a synthetic dollar backed by hedged crypto positions rather than fiat reserves. The risk profile of USDe is meaningfully different from collateral-backed stablecoins: it depends on funding rate dynamics, derivative market liquidity, and custodian counterparty risk.

LlamaRisk's continued presence on the committee reflects both Ethena's complexity and the market's recognition that the firm has developed relevant domain expertise. Sitting on multiple risk committees across different protocol architectures also gives LlamaRisk a cross-protocol view of systemic risk that few single-protocol teams can match.

## Emerging Research Areas

LlamaRisk's research agenda in 2025–2026 has pushed into several new areas that reflect where DeFi risk is evolving.

**Risk oracles.** LlamaRisk has expanded its [LlamaGuard oracle stack](https://www.llamarisk.com/research/llamaguard-release), interpreting observable on-chain and market data as risk signals that trigger automated safeguards — freeze-at-last-good states, circuit breakers — rather than manual governance intervention. The stack is accessible through the firm's [research portal](https://portal.llamarisk.com/).

**RWA integration to DeFi.** Each category of tokenized financial instrument — treasury bills, private credit, real estate — carries unique features requiring adjustment to pricing strategy, risk management, and often protocol design and parameter changes. LlamaRisk's Aave Horizon work, detailed above, is one expression of this research area.

**Regulatory analysis.** The GENIUS Act analysis demonstrates that LlamaRisk is tracking legislative developments that could materially affect protocol design. As stablecoin regulation advances in the U.S. and Europe, protocols will increasingly need formal legal-technical analysis to guide architecture decisions. LlamaRisk appears to be positioning itself to provide that.

## How LlamaRisk Gets Paid and Governed

LlamaRisk's engagements are structured as governance proposals — typically multi-month or annual terms approved by token holder votes. The firm submits renewal proposals, subject to community scrutiny. The [Aave community renewed LlamaRisk for a year](https://governance.aave.com/t/arfc-renew-llamarisk-as-risk-service-provider-epoch-4/24446); the Curve DAO's mandate concluded on June 30, 2026, after which the DAO opened a call for proposals for a successor risk provider. LlamaRisk's April 2026 Curve renewal itself faced scrutiny amid a broader DeFi risk landscape debate — governance-based contracting is not automatic, and the firm must continuously demonstrate value to token holders who control the budget.

This model has meaningful implications for how LlamaRisk operates. Its research and proposals are public by design, since the community needs to evaluate them. Transparency is structural, not optional. That differs from how traditional risk consulting firms work, where analysis is typically client-confidential.

## Limitations and Criticisms

No risk management process eliminates risk, and LlamaRisk's track record includes incidents that occurred on protocols under its watch. The LlamaLend sDOLA exploit, the rsETH event's potential for Aave bad debt, and the crvUSD peg stress events all occurred during active engagement. The firm's post-mortems on these incidents are valuable precisely because they acknowledge failures honestly — but it is worth being clear that risk management is a mitigation discipline, not a prevention guarantee.

The governance-based funding model also creates potential tensions. A firm that depends on community votes for revenue has incentives to maintain good relationships with protocol teams, which can create subtle pressure against strongly critical assessments. Whether LlamaRisk navigates this tension successfully is a question that community observers continue to monitor.

## Outlook

LlamaRisk enters the second half of 2026 with its current mandate centered on the full Aave fleet — including V4 and Horizon — and a fourth term on the Ethena Risk Committee, following the June 2026 conclusion of its four-year Curve engagement, historically its most significant mandate. Its research surface has expanded from collateral evaluation into oracle infrastructure, regulatory analysis, and cross-system correlated risk modeling.

The structural trends driving demand for its work are durable: more complex collateral types (RWAs, synthetic assets, prediction market positions), more cross-chain deployments creating arbitrage and liquidation complexity, and a regulatory environment demanding more formal documentation of risk frameworks. LlamaRisk's multi-protocol positioning also means it accumulates pattern recognition across ecosystems that single-protocol risk teams cannot develop internally.

The open question is whether a governance-funded model can sustain the staffing and analytical depth required as DeFi's risk surface keeps expanding — and whether the firm can maintain critical independence as its revenue becomes more dependent on the goodwill of the communities it advises.
