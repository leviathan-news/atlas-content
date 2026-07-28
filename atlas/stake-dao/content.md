Stake DAO is a non-custodial DeFi protocol that converts long-duration governance locks into liquid receipt tokens and uses the pooled voting power across boosted strategies, vote incentives, and governance. Its current product stack centers on Liquid Lockers, Votemarket, Curve strategies through Only Boost, Morpho lending, and vlSDT governance, as summarized in Stake DAO's [current Liquid Lockers and protocol documentation](https://docs.stakedao.org/).

The word liquid needs a qualification. An sdToken can be transferable even while the underlying governance asset remains locked, but transferability does not guarantee a one-to-one market price, deep exit liquidity, or immediate redemption. Users exchange an individual locked position for exposure to a shared system of contracts, markets, incentives, and protocol operations.

## How Liquid Lockers Work

Vote-escrow systems reward users for locking governance tokens, often by granting voting power and boosted protocol rewards. The tradeoff is that a maximum-duration position can remain illiquid for years. A Liquid Locker pools deposits into a protocol-managed locked position and issues an sdToken representing the depositor's economic interest.

The flagship example is sdCRV. The [current CRV locker](https://www.stakedao.org/lockers/crv) says deposited CRV contributes to Stake DAO's veCRV position. In return, sdCRV holders can access underlying rewards, market liquidity, vote replication, and vote-incentive distributions without each holder maintaining a separate veCRV lock. The [Stake DAO application](https://www.stakedao.org/) currently lists CRV alongside several other governance-token lockers.

This structure does not make the wrapper identical to the underlying asset. The sdToken's market price can diverge from the asset locked behind it, secondary-market liquidity can contract, and the locked position can be affected by changes in the underlying protocol. Smart-contract, oracle, incentive, and operational risks are added to the market risk of the deposited token.

## A Product Map That Changes Over Time

Stake DAO has extended the locker model beyond Curve. The current application lists a live YB locker, for example, but an evergreen guide should not freeze its voting-power totals, reward rates, or incentive terms into prose. Those values can change faster than the explanation around them.

sdPENDLE shows why product status matters more than a launch-era milestone. Stake DAO's [current PENDLE locker page](https://www.stakedao.org/lockers/pendle) says Pendle has moved from vePENDLE toward sPENDLE, new sdPENDLE minting is disabled, staked sdPENDLE positions continue earning rewards, and one-to-one redemption for PENDLE is expected when the underlying vePENDLE lock expires in February 2028.

A separate terminal distribution covers residual voting-power rewards. [SDGP-69](https://gov.stakedao.org/t/sdgp-69-claim-deadline-for-sdpendle-and-sdbal-voting-power-rewards/1130) set October 30, 2026 as the final claim date for those residual sdPENDLE and sdBAL rewards, and the [Snapshot vote](https://snapshot.org/#/s:stakedao.eth/proposal/0x2691bbe0f82d14a4e1a5086fc9c1c69ef17aba98ba0d614c746473dcf596c86c) closed entirely in favor. The terminal voting-power-reward claim should not be confused with a claim that every sdPENDLE reward has ended or that the receipt token has already become redeemable.

The broader lesson is that a liquid locker can move from growth to maintenance, migration, or wind-down when the underlying protocol changes its own governance model. That lifecycle risk belongs in the product explanation.

## Votemarket and Only Boost

Pooled voting power has economic value because governance votes can influence where protocols direct token incentives. Votemarket provides an on-chain venue where protocols create campaigns offering rewards for eligible gauge votes, while voters can earn additional returns for directing their governance power. Stake DAO's [Votemarket v2 whitepaper](https://docs.stakedao.org/assets/Votemarket_v2__whitepaper.pdf) describes support for multiple vote-escrow systems; the exact supported set belongs to the live application rather than a fixed list here.

Only Boost uses Stake DAO's accumulated veCRV position in a different way. The [Only Boost documentation](https://docs.stakedao.org/only-boost) says the product is currently for Curve strategies and calculates an allocation between Stake DAO and Convex using the providers' veCRV balances, including delegated boost. It is not a generic optimizer across every protocol.

Reward timing also deserves precision. Stake DAO's [strategy documentation](https://docs.stakedao.org/strategies) says standard strategy rewards become claimable after harvest. Users may claim or re-compound them, but the normal flow should not be described as automatic compounding.

## Morpho Lending and Curated Vaults

Stake DAO also lets users borrow against a limited set of strategy positions. Its [Morpho Blue lending overview](https://docs.stakedao.org/lending) describes Morpho Blue as the supported lending protocol. Supported reward-vault shares or raw Curve liquidity-provider tokens are wrapped into non-transferable collateral while the underlying position continues accruing rewards.

That continued reward exposure does not eliminate lending risk. Borrowers remain subject to interest, collateral-price changes, oracle behavior, and liquidation. The current [market documentation](https://docs.stakedao.org/lending/markets) describes USDC as the borrowed asset for these wrapper markets, but supported collateral and parameters remain mutable.

Those borrowing markets are distinct from Stake DAO's curated Morpho vaults. Governance has separately considered and approved collateral additions for the frxUSD v2 vault, including a Stake DAO LP position for frxUSD/sDOLA through [LMAP #2](https://gov.stakedao.org/t/lmap-2-add-frxusd-sdola-stake-dao-lp-as-collateral-to-the-stake-dao-frxusd-v2-vault/1133) and its [Snapshot decision](https://snapshot.org/#/s:stakedao.eth/proposal/0x1ac2569d8768a8f89d30ebc40b7592f67abd5daf70e84eb2410de2a643f24e6c). An approved market addition is not the same thing as a guarantee of present liquidity, borrowing capacity, or safety.

## vlSDT Governance

Stake DAO's native governance token is SDT. The protocol has replaced new veSDT locks with vlSDT, while allowing existing veSDT positions to continue participating in Snapshot governance. The [current governance documentation](https://docs.stakedao.org/vesdt_governance) distinguishes the two balances and says only vlSDT now provides boost for sdToken-vault voting rewards.

Under the live model, one staked SDT supplies one unit of non-decaying vlSDT voting power. The [vlSDT staking guide](https://docs.stakedao.org/guides/stake-vlsdt) says an unstake request removes voting and fee-earning power immediately and starts an eight-week withdrawal queue. The [migration guide](https://docs.stakedao.org/guides/migrate-vesdt) says conversion from veSDT is one-way, has no migration deadline, and credits the originally locked SDT amount rather than the decayed voting balance.

Earlier governance materials contemplated an instant exit with a penalty, but the current user-facing guide does not document that route. The live eight-week path is therefore the appropriate mechanism for an evergreen description.

Stake DAO also publishes a [read-only Agent Skill and Hub API guide](https://docs.stakedao.org/ai-skill) that gives compatible agents protocol documentation and access to public Hub API data for lockers, strategies, claims, and lending positions. It does not sign transactions, control a wallet, or turn an informational interface into an autonomous financial agent.

## Two 2026 Incidents, Two Recovery Paths

Stake DAO experienced two materially different incidents in 2026. They should not be collapsed into one exploit narrative, and a governance vote should not be confused with execution or completed claims.

On March 12, an oracle-related Votemarket incident caused approximately $176,000 in lost user rewards. [SDGP-65](https://gov.stakedao.org/t/sdgp-65-allow-the-refund-of-affected-users-from-the-march-12-2026-incident-from-the-treasury/1117) proposed treasury reimbursement, and its [Snapshot vote](https://snapshot.org/#/s:stakedao.eth/proposal/0xf0630034b91b5b10897e758d8219f79dd45dae34e2915794d2a0cdb23703f4f4) passed. Stake DAO later [said](https://x.com/StakeDAOHQ/status/2033687560128467274) all impacted rewards were reimbursed in USDC and made claimable for eligible veCRV voters. That is an attributed account of the eligible set, not evidence that every claimant completed a transaction.

The May 27 vsdCRV incident had a different cause. Stake DAO's [Arbitrum vsdCRV incident disclosure](https://www.stakedao.org/blog/incident-disclosure-27-05-2026) says a deployer account retained the owner role on an Arbitrum cross-chain token contract because the intended governance handover had never been completed. After that account was compromised, the attacker forged unbacked vsdCRV and realized roughly 43.8 ETH of value. Stake DAO moved about 1.329 million staked sdCRV of backing to a governance multisig wallet within 47 minutes, closed the mint path, moved remaining live privileges to the governance multisig, and deprecated the Arbitrum contract.

The response then moved through governance. [SDGP-70](https://gov.stakedao.org/t/sdgp-70-authorize-a-voluntary-ex-gratia-support-distribution-to-users-affected-by-the-may-27-2026-vsdcrv-incident/1134) proposed 1,535,421.76 sdCRV in voluntary, ex gratia support, and the [Snapshot vote](https://snapshot.org/#/s:stakedao.eth/proposal/0xf99c2d8b5124acc9ffcbb78cb53846a86396d3cb08424e770747788e6fc2e1a0) passed. Stake DAO's [June report on the Merkle distribution](https://gov.stakedao.org/t/stake-dao-association-june-2026-report/1143), published July 13, says the Merkle distribution was deployed and integrated into the interface; a July 9 forum update directs eligible wallets to the claim route. The safe conclusion is that the approved distribution was deployed and claimable, not that every affected person was covered or had claimed.

A separate [asdCRV LlamaLend assessment](https://gov.stakedao.org/t/extend-sdgp-70-to-cover-users-that-were-liquidated-due-to-the-vsdcrv-exploit/1138) reported about 17,681 sdCRV of exploit-attributable losses across five addresses and said a new governance proposal would follow. At the July 13 source cutoff, the reviewed public record established a discussion and loss assessment, not a passed second distribution or a claim route.

## Authorization Is Not Execution

The same distinction applies outside incident recovery. [SDGP-57](https://gov.stakedao.org/t/sdgp-57-authorization-of-a-second-vecrv-boost-delegation-agreement/1093) sought authorization for a second delegation of roughly 48.5 million veCRV boost from Michael Egorov under specified commercial terms. Its [Snapshot vote](https://snapshot.org/#/s:stakedao.eth/proposal/0xd8862c42205674c7d3945519e629d1e265fcc6c45b053d926119e9453567c8d0) passed unanimously.

That vote proves governance authorization. The forum thread, later reports, current documentation, and reviewed application materials did not provide a primary record showing that the second delegation executed. Atlas therefore does not count it as a completed transaction. A transaction record or an official execution announcement would resolve the question.

## Risks and What to Watch

Stake DAO's architecture combines several layers whose risks can interact.

**Wrapper liquidity and peg risk:** An sdToken can trade below the asset locked behind it. A holder may depend on secondary-market depth or a future redemption process rather than immediate withdrawal of the underlying governance token.

**Smart-contract and integration risk:** Liquid Lockers, strategies, Votemarket, oracles, bridges, Morpho markets, Curve pools, and third-party protocols create separate failure paths. A position that remains productive inside Stake DAO can still be impaired by an external protocol.

**Lending and liquidation risk:** Reward-bearing collateral can lose value. Borrowing against it adds interest, oracle, liquidity, and liquidation exposure.

**Governance and operational risk:** Votes can authorize changes, but execution still depends on contracts, signers, deployments, and operational controls. The May incident showed the cost of a privileged role that remained with a deployer account.

**Product-lifecycle risk:** A locker depends on the economics and governance design of its underlying protocol. sdPENDLE's transition illustrates how emissions, minting, rewards, and redemption can change after a locker launches.

Stake DAO says in its June report that it expanded ownership verification, monitoring, automated pause coverage, escalation, and deployment controls after the May incident. Those are relevant first-party remediation claims, not an independent conclusion that the controls will prevent another failure.

## Outlook

Stake DAO's durable proposition is that pooled governance positions can remain economically useful through liquid wrappers, boosted strategies, vote-incentive markets, and collateralized integrations. Its current product map also shows the cost of that breadth: the protocol must track changing governance systems, wrapper liquidity, third-party contracts, lending risk, and operational authority across multiple surfaces.

Two questions remain appropriately open for partner review. First, whether the SDGP-57-authorized second boost delegation ever executed. Second, whether the five-address asdCRV assessment has advanced into a proposal, vote, or claim route. Keeping those questions explicit is more useful than converting incomplete public records into confident claims.
