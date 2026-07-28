# Bad Debt in DeFi: What It Is, How It Happens, and Who Ultimately Pays

Bad debt in crypto and DeFi refers to loans or obligations that can no longer be repaid, even after collateral has been liquidated, leaving a lasting hole on a balance sheet. In decentralized lending markets, that shortfall is not absorbed by a central bank or broker; it must be borne by depositors, tokenholders, insurance funds, or external backers, which makes understanding bad debt central to assessing protocol risk.

  

## Defining Bad Debt: From TradFi to DeFi

Bad debt is an old concept with new consequences in crypto markets. In traditional finance and accounting, bad debt is simply money that a business determines it will never collect, such as unpaid invoices or loans to bankrupt customers. When an accounts receivable team concludes that a client will not pay, the receivable is written off as bad debt and reflected as an expense on the income statement. Insurers and risk managers have built entire product lines—such as trade credit insurance and bad-debt protection—to cushion firms against these losses, essentially allowing businesses to transfer the risk of non-payment to an insurance carrier for a premium.

In DeFi, the basic idea is similar but the mechanics are very different. A lending protocol like Aave, Compound, or Fluid records user deposits as liabilities and borrowers’ collateral as assets. When a borrower’s position becomes undercollateralized, the protocol allows liquidators to repay part of the debt and seize collateral at a discount, which is designed to keep the system solvent. Bad debt in this context emerges when the combination of collateral value and liquidation proceeds is no longer enough to cover the outstanding loan, even after the protocol has done everything it can to liquidate the position. The result is a residual shortfall that sits on the protocol’s books and must be absorbed somewhere in the system.

The nature of that shortfall is more structural in DeFi than in a typical corporate ledger. In an overcollateralized lending protocol, every unit of bad debt represents a mismatch between what depositors are owed and what the protocol can credibly recover from borrowers and collateral. Unlike a bank, a DeFi protocol cannot quietly recapitalize itself with central bank liquidity or shareholder injections. Instead, the loss manifests immediately in the protocol’s liquidity conditions, interest rates, and the value of its governance token, or is explicitly socialized via governance decisions and insurance mechanisms. This makes bad debt both an operational risk and a core design parameter for DeFi markets.

It is also important to distinguish between a borrower default and protocol-level bad debt. A single wallet can default in the sense that its health factor falls below one and its collateral is liquidated; if liquidations work as intended, the system may still suffer no lasting loss. Bad debt only appears when liquidations fail or collateral is fundamentally impaired, such that the protocol’s aggregate assets are no longer sufficient to meet its obligations to depositors. Events like MakerDAO’s “Black Thursday” in March 2020, the Fluid–Resolv exploit, and the KelpDAO rsETH incident on Aave all illustrate how this residual category of loss becomes a central governance challenge once it is on the books.

  

### Bad Debt as a Balance Sheet Problem

Thinking about bad debt as a balance sheet issue helps clarify its impact. At a high level, a lending protocol’s solvency can be expressed as the relationship between its assets, liabilities, and equity-like buffers such as treasuries or insurance funds. If we denote assets as \(A\), liabilities to depositors as \(L\), equity or reserves as \(E\), and bad debt as \(D\), a simplified solvency condition might be written as:

\[
A - D \geq L
\]

If \(A - D\) falls below \(L\), the protocol is effectively undercollateralized, and some stakeholder must bear the deficit. In practice, this deficit can be realized through depositors taking haircuts, tokenholders being diluted or having treasury assets deployed, external partners extending credit to patch the hole, or insurance funds paying out. The way a protocol chooses to handle \(D\) therefore encodes its political economy: who is senior, who is junior, and whose capital is implicitly underwriting risk in extreme scenarios.

  

## How Lending and Liquidations Are Supposed to Prevent Bad Debt

To understand how bad debt arises, it is useful to start with how DeFi lending protocols are designed to avoid it. Core money markets like Aave, Compound, and Morpho use overcollateralization, risk parameters, and liquidation incentives to ensure that borrowers cannot drain more value from the system than their collateral is worth under normal conditions.

  

### Overcollateralization and Risk Parameters

In most DeFi money markets, a borrower must post collateral worth more than the value of the assets they borrow, measured using on-chain price oracles. Protocols define a maximum loan-to-value ratio and a liquidation threshold for each collateral asset, reflecting its volatility, liquidity, and correlation with other assets. A blue-chip asset like ETH or staked ETH derivatives might be allowed a relatively high collateral factor, while thinly traded or experimental tokens are assigned conservative parameters or excluded entirely.

These risk parameters are not static; they are tuned by risk teams and DAOs based on quantitative models and stress tests of price, liquidity, and user behavior. When everything is functioning normally, borrowers who drift close to the liquidation threshold either top up their collateral, repay part of their debt, or accept liquidation. This continuous adjustment process is what keeps the protocol solvent.

  

### Liquidation Mechanics and Incentives

Liquidations are the enforcement mechanism that connects individual borrower risk to protocol solvency. When a position’s health factor falls below one, liquidators are permitted to repay a portion of the borrower’s debt and receive collateral at a discount, often called the liquidation bonus. This bonus, combined with the ability to arbitrage off-chain markets, is intended to give liquidators a strong economic incentive to step in quickly, even during volatile market conditions.

The architecture of liquidation systems has evolved since early DeFi. Some protocols rely on open auctions, while others use fixed-parameter “seize and sell” mechanisms; MixBytes, for example, has documented a range of traditional and novel liquidation designs and their respective vulnerabilities. Parameters like the close factor, which specifies how much of a position can be repaid in a single liquidation, and minimum transaction sizes are tuned to balance gas costs, partial liquidations, and market impact. When these systems work, undercollateralized positions are rapidly deleveraged, collateral is sold into the market, and lenders are kept whole.

Aave’s v3.3 design illustrates how refined this process has become. In v3.3, certain small positions can be liquidated up to a full 100% close factor when the total principal or total debt on a specific reserve is below a configured threshold, in order to avoid leaving “dust” positions that are uneconomical to liquidate. To support this, the protocol defines thresholds such as `MIN_BASE_MAX_CLOSE_FACTOR_THRESHOLD` and `MIN_LEFTOVER_BASE`, ensuring that, within a certain size range, a full liquidation can be performed without leaving tiny residual amounts of debt or collateral behind. These mechanics are meant to minimize the chances that small, hard-to-liquidate positions accumulate into non-trivial pockets of bad debt over time.

  

### Protocol-Level Treatment of Bad Debt

Despite these safeguards, there are scenarios where even aggressive liquidations cannot restore solvency. Aave v3 explicitly recognizes this by introducing a protocol-level notion of bad debt: situations where, after liquidation, a borrower ends up with zero collateral but non-zero debt. In such cases, v3.3 includes a verification step that checks whether the liquidation will produce a “bad debt” account, and if so, it burns the remaining variable debt tokens and records the deficit at the reserve level.

This change has two important implications. First, it prevents interest from continuing to accrue on positions that are already irrecoverable, which would otherwise distort accounting and health-factor calculations. Second, it formalizes bad debt as a measurable quantity at the reserve level, allowing risk managers and governance to track and respond to deficits as they emerge. Rather than being an undefined residual, bad debt becomes a first-class concept in the protocol’s accounting.

Margin and derivatives platforms such as Deepbook’s margin pools operate with similar principles but often tighter collateral parameters, because leverage and maturity structures can amplify losses more quickly. An undercollateralization vulnerability in a Deepbook USDC margin pool recently led to approximately 239,700 USDC of bad debt, which the protocol identified as a shortfall that had to be covered by its insurance fund. Even though the absolute number was modest compared to large money markets, it illustrates the same accounting move: recognizing that a subset of loans will never be repaid and explicitly funding the gap.

  

## How Bad Debt Emerges: From Market Volatility to Exploits and Toxic Collateral

Bad debt appears when the mechanisms described above fail to fully protect the protocol’s balance sheet. In practice, the root causes tend to fall into three broad categories: extreme market moves and oracle or liquidation failures, smart contract or bridge exploits that create toxic collateral, and deliberate design choices that socialize bad debt directly to lenders.

  

### Market Crashes, Oracle Issues, and Auction Failures

The most straightforward path to bad debt is a market crash that overwhelms the liquidation system. If asset prices move too far, too fast, liquidators may not be able to close positions at prices that fully cover debts, especially if on-chain liquidity is thin or gas prices spike. In some cases, oracles may lag or fail, causing collateral valuations to be stale just when they are needed most.

MakerDAO’s Black Thursday event in March 2020 remains a canonical example. During a sharp ETH price crash, Maker’s collateral auctions malfunctioned under extreme network congestion, allowing some liquidators to win auctions with zero bids. Collateral that should have been sold to cover DAI-denominated debt was effectively given away for free, leaving the system with around 2.5 million USD worth of bad debt. Maker ultimately addressed this shortfall by minting new MKR and auctioning it to recapitalize the system, but this experience seared into DeFi’s collective memory how quickly a combination of market moves and technical stress can create protocol-level bad debt.

  

### Exploits and “Toxic Collateral”

The second major pathway to bad debt arises from smart contract or bridge exploits that produce “toxic collateral”—assets that appear valid to a lending protocol but are, in fact, unbacked or vastly overvalued. In such cases, a protocol can be tricked into accepting worthless collateral in exchange for real, liquid assets like ETH or stablecoins, creating an immediate risk of bad debt once the fraud is recognized.

The KelpDAO rsETH exploit on April 18, 2026, is a vivid example. An attacker exploited a single-signer configuration in KelpDAO’s LayerZero bridge to mint approximately 116,500 rsETH on Ethereum with no underlying backing, worth around 292 million USD at the time. Within minutes, this unbacked rsETH was deposited as collateral into Aave’s Ethereum and Arbitrum markets, where it was used to borrow large quantities of WETH and some wstETH. On Aave v3/v4 Ethereum alone, the attacker is reported to have borrowed over 52,000 WETH, with additional large WETH and wstETH borrows on Arbitrum and smaller positions on other protocols.

Once the exploit became public and KelpDAO acknowledged that part of the rsETH supply was unbacked, the collateral supporting these loans was effectively worthless. Aave’s risk teams responded quickly by freezing rsETH markets and urging WETH suppliers to withdraw while they assessed the situation. However, because the attacker had borrowed real ETH against bogus collateral, the WETH reserves on Aave’s Ethereum and Arbitrum deployments became heavily utilized, and analysts began estimating the potential bad debt facing the protocol’s WETH and wstETH reserves.

On-chain risk firms such as LlamaRisk and Chaos Labs modeled potential Aave bad debt in the range of roughly 123 million to 230 million USD, depending on assumptions about liquidations and cross-chain positions. A frequently cited figure has been around 177 million USD of bad debt sitting in the WETH reserves, with other estimates as high as 196 million USD depending on how partial liquidations and wstETH positions are treated. As suppliers rushed to withdraw ETH from Aave in response, the protocol’s total value locked (TVL) reportedly fell by around 6.6 billion USD, showing how fast markets can react to a perceived risk of unresolved bad debt.

This episode illustrates how bad debt in DeFi can emerge not only from market volatility but from the composability that makes DeFi powerful. A single bridge exploit at KelpDAO turned rsETH into toxic collateral, and because that collateral had been widely integrated across chains and protocols, the downstream impact spanned Aave, other lenders, and a web of wrapped derivatives on L2s and sidechains. Once an asset’s backing is compromised, any protocol that accepted it as collateral has to confront the potential for bad debt.

  

### Design-Choice Bad Debt: Socialized Losses by Construction

A third category of bad debt arises by design. Some protocols explicitly structure their markets so that certain classes of users, usually lenders, absorb all shortfalls from failed liquidations or defaults. This is the case in some fixed-rate credit markets, such as those built with Morpho’s Midnight product, where bad debt is socialized among lenders in a pool rather than being absorbed by a protocol treasury or governance token.

In such models, liquidity providers effectively become junior lenders in a credit structure. If a borrower fails and liquidations do not fully cover the debt, the remaining lenders in the pool share the loss pro rata. This design can provide more predictable returns in normal markets but makes parameters like loan-to-value limits, maturity profiles, and liquidation incentives absolutely critical, since there is no independent equity layer or insurance fund to buffer extreme events. Coverage of Morpho Midnight has emphasized how this shifts risk from protocols to users, making the exact configuration of LLTV, liquidation premiums, and incentive mechanisms central to the lender’s risk–return profile.

These architectures are not inherently flawed; they simply encode a different answer to the question of who should hold tail risk. What unites all three categories—market failures, exploits, and socialized-by-design defaults—is that they generate a residual shortfall that must be explicitly recognized and funded. At the moment bad debt becomes visible, questions about governance, fairness, and long-term credibility become as important as any on-chain parameter.

  

## Case Studies: Aave, Fluid, Deepbook, Maker, and Others

Concrete incidents help illustrate how bad debt is handled in practice and how different choices shape both user outcomes and market confidence. Recent episodes across Aave, Fluid, and Deepbook, along with earlier events at Maker and risk-averse responses from protocols like Venus, offer a useful cross-section.

  

### Aave, rsETH, and the KelpDAO Exploit

The rsETH incident has become a stress test for one of DeFi’s largest lending markets. After the KelpDAO bridge exploit allowed the attacker to mint hundreds of millions of dollars’ worth of unbacked rsETH, Aave’s v3 and v4 markets on Ethereum and Arbitrum became the primary venue where that forged collateral was used to borrow ETH. Aave’s risk teams responded by freezing rsETH markets, adjusting interest rates, and coordinating with external risk providers like LlamaRisk and Chaos Labs to quantify potential bad debt and propose mitigation paths.

The core problem is straightforward: the attacker walked away with roughly 200–236 million USD of borrowed WETH and wstETH, while the rsETH collateral backing those loans is now viewed as worthless or severely impaired. Because Aave’s design is overcollateralized and there is no direct recourse against the attacker, this shortfall manifests as potential bad debt in the WETH reserve. As suppliers withdrew liquidity en masse, the WETH utilization rate on Aave hit 100%, leaving remaining depositors unable to withdraw until new liquidity arrived or the bad debt was resolved.

Governance discussions quickly turned toward coverage mechanisms. Aave’s official communications noted that service providers were working to assess two main bad debt scenarios and that ecosystem participants were already making indicative commitments to help address any final deficit. One notable proposal came from MantleCore, which submitted a draft governance proposal (MIP-34) to authorize the Mantle Treasury to lend up to 30,000 ETH to the Aave DAO to cover bad debt tied to the rsETH exploit, priced at Lido’s staking yield plus a 1% spread. In parallel, rsETH had to be frozen or delisted on other protocols, with some platforms like Spark managing to exit exposures early enough to avoid direct bad debt risk.

Whether and to what extent Aave’s bad debt is ultimately socialized among depositors, absorbed by the DAO’s treasury and safety mechanisms, or mitigated by external backers will define the long-term narrative of this incident. For now, it stands as a clear example of how composability, restaking tokens, and cross-chain bridges can transform a seemingly isolated exploit into a protocol-level bad debt crisis for a major market, sparking liquidity flight and governance-intensive negotiations about who will pay.

  

### Fluid and the Resolv USR Exploit: Fast Cleanup, Socialized Cost

Fluid’s experience with the Resolv USR exploit offers a contrasting story of rapid bad-debt cleanup. When Resolv’s USR stablecoin suffered a depegging event after a hack, Fluid had roughly 100 million USD in exposure through its lending markets. As the peg broke, around 21 million USD of positions on Fluid went underwater, turning into bad debt sitting against the protocol’s shared liquidity layer.

Several safeguards worked as designed. Fluid’s automated market ceilings prevented borrowers from excessively levering into USR, which helped contain the scale of the loss. Still, the protocol faced a material amount of bad debt that, if left unresolved, would have impaired user deposits or significantly undermined confidence in the platform. In response, Fluid used a pre-approved internal credit line from its shared liquidity layer to immediately sweep thousands of scattered bad-debt positions into one address and balance the books. This effectively fronted the funds needed to make depositors whole while converting the problem into a debt owed by the protocol’s governance and partners.

The eventual resolution split the roughly 21 million USD loss three ways. Around 9.7 million USD was absorbed by Resolv, the issuer of USR, which agreed to take the largest share of the loss. The Fluid governance treasury contributed approximately 8.2 million USD, and the Fluid core team took responsibility for about 1.5 million USD, to be reimbursed from future protocol revenues. According to Fluid’s reporting and subsequent coverage, around 19.3 million USD of bad debt was fully repaid through this coordination, and malicious USR was burned at the contract level so that healthy positions could remain redeemable.

From a bad-debt perspective, the key point is that user deposits were not haircut, and the bad debt was metabolized through a combination of treasury resources, issuer support, and commitments of future cash flow. This outcome required a relatively centralized operational response—a single multisig pulling funds through an internal credit line—but it demonstrated that, under some conditions, DeFi protocols can treat bad debt as a surmountable operational crisis rather than an existential threat.

  

### Deepbook’s Insurance Fund Response

Deepbook’s recent undercollateralization incident provides a smaller-scale but instructive example of how insurance funds can absorb bad debt. At approximately 3:18 AM UTC on the day of the incident, a vulnerability in Deepbook’s USDC margin pool allowed certain positions to become undercollateralized, resulting in around 239,700 USDC of bad debt. Margin trading was immediately paused as the team evaluated the issue, and the Deepbook Insurance Fund injected the missing funds back into the affected pools.

After the injection, deposits and withdrawals were resumed, and margin trading was brought back online once the vulnerability had been addressed. Here, the bad debt was explicitly treated as a pool-level loss that the insurance fund was designed to cover. The episode showed how a pre-funded insurance mechanism can function as a dedicated equity layer for a protocol, absorbing modest tail losses without requiring governance token dilution or depositor haircuts.

  

### MakerDAO’s Black Thursday Aftermath

MakerDAO’s handling of its early bad debt episode illustrates a different governance trajectory. In the wake of Black Thursday, the protocol’s malfunctioning auctions left about 2.5 million USD of bad debt in the system. Maker’s solution was to mint new MKR and auction it to raise funds to cover the deficit, a move that effectively diluted existing MKR holders in exchange for system solvency.

Later, some users who had lost 100% of their collateral in the event pushed for Maker governance to compensate them via additional MKR issuance. However, MKR holders ultimately voted not to reimburse these losses through further token minting. This decision underscored that, in Maker’s architecture, MKR holders function as a kind of backstop capital: they can be diluted to recapitalize the system when bad debt appears, but they also have discretion over whether to offer additional socialized compensation to affected users. The handling of Black Thursday set precedents about who bears losses and how far governance should go in redistributing them after the fact.

  

### Venus and the Choice to Avoid Exposure

Not every protocol faced direct bad debt during the rsETH turmoil. Venus Protocol, for example, publicly emphasized that it had zero exposure to rsETH and therefore incurred no bad debt from the KelpDAO exploit. At the same time, as a precautionary measure and on the advice of its risk management partner, Venus temporarily set the collateral factors of several other assets, including USDe, sUSDe, SolvBTC, xSolvBTC, USD1, and XAUM, to zero. Users could still repay and withdraw these assets, but they were not allowed to post them as collateral during the risk event.

This stance highlights a different approach to bad-debt risk: rather than relying primarily on ex post mechanisms like treasuries or insurance funds, some protocols attempt to minimize their exposure in the first place by maintaining conservative asset listings and dynamically adjusting collateral parameters when systemic risk is perceived. In choosing not to integrate rsETH and to temporarily furl collateral sails on related assets, Venus avoided both the direct risk of bad debt and the indirect reputational damage of being entangled in a high-profile exploit.

  

### Comparative Snapshot

The differences among these cases can be summarized as follows:

| Protocol / Case | Cause of Bad Debt or Risk | Who Primarily Absorbed or Would Absorb Losses | Notable Mechanism |
|-----------------|---------------------------|-----------------------------------------------|-------------------|
| MakerDAO Black Thursday | Auction failure during ETH crash | MKR holders via token dilution | Governance token as recapitalization tool |
| Aave rsETH / KelpDAO | Unbacked rsETH used as collateral | Pending mix of DAO treasury, external partners, possibly safety mechanisms | v3 accounting for bad debt; external ETH loan proposals |
| Fluid–Resolv USR | Stablecoin depeg after exploit | Resolv issuer, Fluid treasury, Fluid core team (future revenue) | Internal credit line; fast sweep and socialized cost |
| Deepbook USDC margin | Undercollateralization vulnerability | Deepbook Insurance Fund | Pre-funded insurance pool covers shortfall |
| Venus rsETH response | Avoided risk ex ante | No bad debt incurred | Conservative listings; collateral factors cut to zero |

While each case is unique, the constant is that bad debt forces a protocol to reveal its capital structure and risk priorities. Whether the burden falls on tokenholders, issuers, treasuries, insurance funds, or lenders determines not just who is made whole, but how markets perceive the protocol’s long-term trustworthiness.

  

## Who Ultimately Pays? Socialization, Treasuries, and Insurance

Bad debt is not just a technical event; it is a social and political one. Once a deficit exists, the key question becomes who will bear it. In DeFi, that answer is encoded partly in protocol design and partly in governance decisions made under pressure.

  

### Depositors and Liquidity Providers

In some architectures, particularly those with explicitly socialized bad debt, lenders in a given pool are the first and last line of defense. Fixed-rate markets like those built on Morpho Midnight, where bad debt is socialized among lenders by design, make this explicit. If a borrower’s collateral cannot be fully liquidated, the remaining lenders in that pool share the deficit, effectively functioning as junior credit investors rather than traditional depositors.

Even in protocols not structured around explicit socialization, depositors may find themselves de facto bearing bad debt if other buffers fail. When Aave’s WETH reserve hit 100% utilization after the rsETH exploit, remaining depositors were effectively locked in, unable to withdraw until either new liquidity arrived or governance found a way to cover the shortfall. While they may ultimately be made whole through treasury actions or external support, the period of illiquidity and uncertainty represents real risk.

  

### Protocol Treasuries and Governance Tokens

Many protocols maintain treasuries funded by fees or token distributions, alongside governance tokens that can be diluted in extreme scenarios. Maker’s use of MKR auctions to cover bad debt after Black Thursday is the clearest example of token dilution as a recapitalization mechanism. Fluid’s use of its governance treasury to cover part of the Resolv bad debt likewise shows how treasuries can be deployed as a buffer between users and losses.

In Aave’s case, the DAO’s treasury and safety mechanisms are expected to be central to any eventual resolution of rsETH-related bad debt. Aave’s official communications emphasized that DAO service providers are leading efforts to address bad debt and that multiple ecosystem participants have indicated willingness to contribute resources. The MantleCore proposal to lend up to 30,000 ETH to Aave DAO is one such contribution, structured as a loan with yield rather than an outright grant. In both models, the treasury and governance framework are the arena where losses are negotiated and allocated among stakeholders.

  

### External Partners, DAOs, and Credit Lines

An emerging pattern is the use of external partners and DAOs to shoulder part of the burden. In the Fluid–Resolv case, Resolv as the issuer of USR absorbed nearly half of the total loss, recognizing that its stablecoin’s failure had directly harmed Fluid’s lenders. In the Aave rsETH incident, Mantle’s proposed ETH loan represents a form of external credit support, where a partner DAO sees strategic or reputational value in helping a major money market avoid a drawn-out bad debt overhang.

Credit lines and shared liquidity layers blur the boundaries further. Fluid used a pre-approved internal credit line against its shared liquidity layer to clean up bad-debt residues, effectively borrowing from its own future cash flows and treasury to make users whole in the present. Such structures resemble, in some respects, TradFi bad-debt protection arrangements where specialized financial providers underwrite receivable risk in exchange for fees. The difference is that in DeFi, these arrangements are encoded in smart contracts and governance structures rather than bilateral legal agreements.

  

### Insurance Funds and Recovery DAOs

Insurance funds like Deepbook’s serve as designated capital buffers specifically earmarked for covering shortfalls when things go wrong. By pre-funding such pools, protocols can credibly commit that small to moderate bad-debt events will not touch user deposits, which can meaningfully improve risk perception. In return, users accept somewhat lower yields, as a portion of protocol revenues is diverted to maintain the insurance pool.

Beyond internal insurance, external recovery DAOs and community-led rescue efforts have begun to appear wherever bad debt leaves lenders stranded in smaller protocols. In the wake of persistent bad debt at Llama Lend on Fraxtal, for example, community actors have launched specialized recovery pools to help lenders regain partial value over time, introducing a quasi-distressed-asset market around bad debt. Although these initiatives are not yet as institutionalized as internal insurance funds, they signal an evolving ecosystem where bad debt is not always the end of the story but the beginning of a secondary process of workouts and recoveries.

  

### Comparative Lessons

Across these mechanisms, two themes recur. First, there is no free lunch: someone always bears the loss, whether quietly via lower treasury balances and diluted tokenholders or explicitly via depositor haircuts and socialized pool losses. Second, protocols that clearly predefine their loss-absorption hierarchies and maintain credible buffers—through treasuries, insurance, or external partnerships—tend to fare better in market perception than those improvising solutions in the middle of a crisis.

  

## Measuring and Managing Bad Debt Risk

If bad debt cannot be eliminated, it can at least be measured and priced. Risk managers and sophisticated users are increasingly focused on understanding not just whether a protocol has experienced bad debt, but how likely it is to do so under plausible stress scenarios.

  

### Risk Modeling and Stress Testing

Academic and industry research on DeFi risk emphasizes that borrower defaults and bad debt are among the core risks facing lending protocols. TOBAM’s analysis of DeFi lending, for instance, highlights how liquidation mechanisms, collateral volatility, and liquidity depth interact to determine the probability and severity of bad debt events. By simulating price paths, liquidity shocks, and user responses, risk teams can estimate the distribution of potential losses and set parameters accordingly.

Parameters such as loan-to-value limits, liquidation thresholds, and bonuses must be chosen in light of these modeled distributions. Conservative settings reduce the probability of bad debt but can depress borrowing demand and yields, while aggressive settings boost activity at the cost of higher tail risk. Fixed-rate markets like Morpho Midnight add another dimension, since maturity structures and liquidation incentives over time become critical in ensuring that lenders are compensated for taking on bad-debt risk implicitly.

  

### Asset Listing Frameworks and Collateral Selection

The rsETH incident has renewed focus on asset-listing frameworks and the risks of integrating complex derivatives such as liquid restaking tokens (LRTs). LRTs like rsETH inherit not only the risks of their underlying staked ETH positions but also additional layers from restaking protocols, bridges, and wrapper contracts. When KelpDAO’s bridge configuration allowed unbacked rsETH to be minted, this entire risk stack collapsed onto Aave and other lenders that had accepted rsETH as collateral.

Responsible asset listing requires evaluating not just price volatility and on-chain liquidity, but also governance quality, bridge designs, signer configurations, and cross-chain liquidity fragmentation. Venus’s decision to avoid rsETH exposure and to temporarily set collateral factors of several high-risk assets to zero exemplifies a conservative approach that prioritizes minimizing bad-debt risk over maximizing collateral diversity. In contrast, protocols that aggressively integrate new assets without fully mapping these dependencies face higher odds of being caught in the blast radius when something goes wrong.

  

### Operational Playbooks for Emerging Bad Debt

Once signs of potential bad debt appear—such as rapidly deteriorating collateral, exploit reports, or undercollateralized pools—operational responses can materially alter outcomes. Aave’s quick move to freeze rsETH markets and adjust interest rates helped contain further borrowing against compromised collateral and signaled to users that risk teams were actively managing the situation. Fluid’s immediate use of its internal credit line to sweep bad-debt positions similarly prevented panic and preserved user confidence. Deepbook’s prompt pause of margin trading and rapid injection from its insurance fund did the same on a smaller scale.

These responses show that risk management in DeFi is not purely parametric; it is also procedural. Protocols that maintain clear playbooks for freezing markets, raising or lowering rates, deploying treasuries, and communicating with users are better positioned to handle bad debt when it appears. Governance processes and operational centralization levels shape how quickly these playbooks can be executed.

  

### User-Level Risk Management

For individual users and institutional lenders, understanding bad-debt risk is an essential part of due diligence. When evaluating a protocol, users can examine its history of bad debt (if any), the presence of treasuries or insurance funds, and the clarity of its loss-absorption hierarchy. Reading governance forums, incident reports, and risk-provider analyses—such as LlamaRisk’s modeling of Aave’s rsETH bad debt scenarios—can provide insight into how serious different tail risks are and how they might be handled.

In practical terms, users may choose to limit exposure to assets with complex or opaque backing, such as certain LRTs and cross-chain derivatives, especially when yields seem unusually high relative to perceived risk. They may also diversify across multiple protocols and avoid concentrating deposits in markets that show signs of stress, like sustained 100% utilization or large, unresolved governance debates over bad debt. Ultimately, users in DeFi are not just savers; they are creditors, and their returns are compensation for taking on credit and protocol risk that includes the possibility of bad debt.

  

## Outlook

Bad debt in DeFi is not going away; if anything, it is likely to become more central as protocols integrate increasingly complex assets, cross-chain architectures, and restaking layers. The KelpDAO rsETH exploit and its impact on Aave demonstrate that composability amplifies both opportunities and vulnerabilities, turning a bridge configuration error into a multi-hundred-million-dollar bad-debt question for one of the ecosystem’s flagship money markets. At the same time, the Fluid–Resolv and Deepbook episodes show that well-designed treasuries, insurance funds, and operational playbooks can turn bad debt from an existential crisis into a manageable, if painful, incident.

Over the medium term, several trends seem likely. First, asset listing frameworks will tighten, with more protocols adopting conservative approaches reminiscent of Venus’s response to rsETH, at least for collateral that sits at the core of large lending markets. Second, explicit socialization of bad debt—whether among lenders in fixed-rate pools or through governance-determined treasury deployments—will become more transparent, enabling users to choose the risk–return profile they prefer. Third, specialized insurance funds, credit lines, and cross-DAO support arrangements like Mantle’s proposed ETH loan to Aave DAO will proliferate, creating a more layered capital structure around DeFi credit risk.

For a crypto news audience, bad debt will remain a key lens through which to interpret market events. When you see headlines about exploits, liquidations, or depegs, the critical follow-up questions are always the same: how much bad debt has been created, who is on the hook for it, and what does the response tell us about the protocol’s resilience? The answers to those questions will continue to shape not just the fortunes of individual protocols like Aave, Fluid, and Deepbook, but the credibility of DeFi as a whole as it seeks to scale from speculative experiments to durable financial infrastructure.
