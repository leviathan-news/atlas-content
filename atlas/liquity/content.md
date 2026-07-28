Liquity is a non-custodial borrowing protocol on Ethereum. Its current V2 deployment lets users borrow the **BOLD** stablecoin against ETH and selected liquid-staking tokens through immutable, non-upgradeable core contracts. Borrowers select adjustable interest rates, and the system uses separate collateral branches, Stability Pools, redemptions, and automatic safety states to manage debt.

The most important qualification is that Liquity does not remove every form of control. It removes discretionary operator control over the current core. LQTY stakers have a narrow voting role over liquidity incentives, while predefined code can restrict or permanently shut down an individual collateral branch under specified conditions.

## Two Liquity Systems Continue Side by Side

Liquity V1 launched on Ethereum on April 5, 2021. It allows users to open a Trove, deposit ETH, and borrow LUSD without ongoing interest. V1 instead charges one-time, algorithmically determined borrowing and redemption fees. Its contracts are immutable and governance-free, and ETH is its only collateral type. Liquity's [V1 documentation](https://docs.liquity.org/liquity-v1), [launch announcement](https://www.liquity.org/blog/liquity-launch-details), and [borrowing FAQ](https://docs.liquity.org/liquity-v1/faq/borrowing) describe that original design.

V2 does not terminate that system. Liquity's [current V2 FAQ](https://docs.liquity.org/v2-faq) says V1 is “here to stay” and positions LUSD as an option for users who prefer pure ETH backing. BOLD therefore should not be described as having replaced or superseded LUSD. V1/LUSD and V2/BOLD are distinct systems with different debt, collateral, interest, redemption, and governance mechanics.

## Why the Current Deployment Date Matters

The current Liquity V2 deployment went live on Ethereum mainnet on May 19, 2025. That was a redeployment, not simply the continuation of the first V2 release.

In February 2025, Liquity disclosed an issue affecting the earlier deployment's Stability Pool. The team advised users to close positions and said the earlier deployment would become a legacy version. Liquity then ran another audit contest and additional reviews before launching the current contracts. The official [redeployment chronology](https://www.liquity.org/blog/liquity-v2-redeployment) records the incident response and relaunch, while the [current-deployment announcement](https://www.liquity.org/blog/liquity-v2-is-live) identifies May 19 as the go-live date.

That history makes immutability concrete. The earlier deployed core could not be patched in place. Liquity advised users to close positions in that deployment, then reviewed and launched a new deployment. Immutability reduces the risk of an administrator changing rules after deposit, but it also narrows the response available when deployed code is wrong.

## BOLD and the Collateral Branches

BOLD is a soft USD-pegged, overcollateralized stablecoin. The current V2 system accepts ETH—represented as WETH at the contract level—plus wstETH and rETH. These accepted collateral types are fixed in the immutable deployment.

Each collateral has a separate borrowing branch with its own Troves, risk parameters, aggregate collateralization, and Stability Pool. This separation contains some risks but not all of them. A borrower is directly exposed to the collateral in that borrower's own Trove. A Stability Pool depositor receives liquidation collateral from the selected branch. A BOLD holder, however, depends on the effective liquidation and backing of all active branches because BOLD is common debt across the system.

Liquity's [borrowing and liquidation FAQ](https://docs.liquity.org/v2-faq/borrowing-and-liquidations) and [risk disclosure](https://docs.liquity.org/v2-documentation/risk-disclosure) identify the accepted assets and explain the branch-specific structure. Exact collateral ratios and frontend-displayed rates can change with position and market conditions, so this guide does not freeze live values into the explainer.

## Borrower-Set Interest Rates

A V2 borrower opens a Trove and chooses an annual interest rate. The rate is adjustable rather than fixed for a term, and a borrower may delegate rate management to another address. Interest accrues to the Trove's BOLD debt.

Borrowers can delegate to a specialized batch manager that charges a fee, to an automated contract strategy, or to another wallet of their own choosing, such as a hot wallet or a friend. In every case, the delegate can do nothing but set the interest rate within a predetermined range, which significantly limits the borrower's risk.

The selected rate affects two things. First, it determines ongoing borrowing cost. Second, it affects where the Trove sits in the redemption order within its collateral branch. A lower rate costs less but increases relative exposure to redemption. A higher rate costs more but places the Trove behind lower-rate debt in that branch.

The rate does **not** determine whether a Trove can be liquidated. Liquidation risk follows the position's collateralization and the applicable branch rules. Treating redemption and liquidation as the same event obscures the different risks a borrower manages.

Opening a Trove or increasing its debt also incurs an upfront borrowing fee. Liquity calculates that fee from seven days of the average interest rate in the relevant branch. Changing a rate again within seven days can trigger a premature-adjustment fee based on the same seven-day average. These rules make rapid rate changes costly rather than letting borrowers move around the redemption order for free. The current [borrowing FAQ](https://docs.liquity.org/v2-faq/borrowing-and-liquidations) documents these fees and the distinction between rate and liquidation risk.

## How Standard Redemptions Work

A BOLD holder can redeem BOLD for a combination of WETH, wstETH, and rETH, less the applicable redemption fee. Standard redemptions can occur at any time, although they are economically most likely when BOLD trades below one dollar after accounting for the fee.

The protocol does not send every redemption into one global list of borrowers. It first divides the redemption among active collateral branches according to each branch's **outside debt**:

**outside debt = branch debt − BOLD in that branch's Stability Pool**

A branch with more debt outside its Stability Pool receives a larger share of the redemption. Within each selected branch, the protocol then processes the lowest-interest Troves first. When two Troves have the same rate, the Trove whose rate was set most recently is redeemed first.

A redemption burns BOLD supplied by the redeemer, reduces some or all of the affected borrower's debt and collateral, and transfers corresponding collateral to the redeemer, but it can change the borrower's intended exposure without the borrower choosing to close. Rate selection is therefore position management, not merely price shopping. Liquity's [redemptions and delegation FAQ](https://docs.liquity.org/v2-faq/redemptions-and-delegation) describes the current cross-branch allocation and in-branch ordering.

## Stability Pools and Liquidations

Each collateral branch has its own Stability Pool. Depositors place BOLD into the pool associated with the collateral they are willing to receive. When a Trove in that branch is liquidated, Stability Pool BOLD cancels the liquidated debt and depositors receive the corresponding collateral.

Liquity describes Stability Pool liquidation gains as effectively acquiring collateral at about a five-percent discount before liquidator gas compensation slightly reduces the pool's gain. That is a mechanism description, not a guaranteed profit: an oracle lag or a rapid collateral decline can turn a nominal gain into a loss. Depositors also remain separately exposed to a broader BOLD depeg.

The Stability Pool is the primary liquidation path, not the only possible path. If it cannot cover all liquidated debt, V2 can use just-in-time liquidation or redistribute remaining debt and collateral among borrowers in the same branch. The [BOLD and Earn FAQ](https://docs.liquity.org/v2-faq/bold-and-earn), [borrowing FAQ](https://docs.liquity.org/v2-faq/borrowing-and-liquidations), and [risk disclosure](https://docs.liquity.org/v2-documentation/risk-disclosure) explain these flows and their failure cases.

Stability Pool deposits have no protocol lockup, but “withdrawable” does not mean risk-free. Depositors take branch-specific collateral exposure through liquidations and remain BOLD holders exposed to the backing of the system as a whole.

## Where Borrower Interest Goes

The current V2 rules split Trove interest in a fixed ratio:

- **75%** goes to depositors in the Stability Pool for that collateral branch, paid in BOLD.
- **25%** goes to Protocol Incentivized Liquidity, or PIL.

LQTY stakers with voting power decide which external initiatives receive the PIL stream. Liquity presents those initiatives as support for BOLD liquidity. The 75/25 split is hard-coded; voting does not change the split or confer control over the core contracts.

It is therefore inaccurate to say either that Liquity has no governance or that all system revenue goes to Stability Pool depositors or BOLD holders. Liquity has limited incentive governance, and borrower interest is divided between branch depositors and PIL recipients. The [LQTY staking FAQ](https://docs.liquity.org/v2-faq/lqty-staking) and Liquity's [V2 voting explainer](https://www.liquity.org/blog/voting-in-liquity-v2) define that scope.

## Immutability With Automatic Safety States

Liquity documents the current core as immutable and non-upgradeable. It says there are no administrator-controlled upgrade, pause, freeze, or manual shutdown functions, and no whitelist, blacklist, or transfer-freeze function for BOLD. Accepted collateral and core parameters cannot be changed after deployment.

Those properties do not mean that every branch must continue normal operation forever. V2 includes automatic branch-specific safety states.

A branch enters **Safety Mode** when its aggregate collateralization falls below its critical level. Safety Mode restricts actions that would further weaken the branch, including certain debt increases, collateral withdrawals, and premature rate changes. It is reversible if the branch recovers.

A branch enters **Shutdown Mode** if collateralization deteriorates past a lower threshold or if the branch's price oracle fails. Shutdown Mode is permanent for that branch. It prevents new loans and ordinary position adjustments, stops interest accrual, and permits closing, surplus claims, and a special shutdown-redemption process. Standard redemptions continue against active branches and skip the shutdown branch.

This is not an administrator deciding when to intervene. It is automatic logic committed in advance. “No discretionary admin off switch” is therefore more precise than “no off switch.” The [borrowing and liquidation FAQ](https://docs.liquity.org/v2-faq/borrowing-and-liquidations) and [risk disclosure](https://docs.liquity.org/v2-documentation/risk-disclosure) describe both modes and the absence of manual controls.

## The Risk Model

Liquity's design changes who can act and when; it does not eliminate financial or technical risk. Liquity's own [risk disclosure](https://docs.liquity.org/v2-documentation/risk-disclosure) covers branch, oracle, bad-debt, liquidation, and peg failure cases.

**Collateral and liquidation risk:** ETH, wstETH, and rETH can fall in value. A highly leveraged Trove has less room before liquidation. LST collateral also adds staking, slashing, liquidity, and smart-contract risks beyond ETH itself.

**Redemption risk:** Low-rate Troves are reached first within a branch after the protocol allocates redemptions across branches. A borrower can lose the intended debt-financed exposure even without liquidation.

**Stability Pool risk:** Liquidation collateral can decline faster than the mechanism's discount protects depositors. A depositor also remains exposed to a broader BOLD depeg.

**Oracle and branch risk:** Oracle failure can permanently shut down one branch. Severe collateral impairment can create bad debt that the available liquidation paths do not fully clear.

**Smart-contract and immutability risk:** Audits and review can reduce implementation risk, not remove it. If an immutable deployment contains a material flaw, the response may require users to exit and a successor deployment to launch rather than an in-place patch.

**Liquidity and peg risk:** Redemption supports BOLD's soft peg, but the practical experience of entering, exiting, or liquidating a position also depends on available BOLD and collateral liquidity. The redemption mechanism does not guarantee frictionless market liquidity at every size or moment.

These risks are not arguments for or against Liquity by themselves. They are the costs attached to a system that substitutes predefined mechanisms for discretionary administration.

## What Liquity's Design Actually Claims

Liquity V2's central claim is narrower than “trustless money without an off switch.” The current Ethereum core lets users verify collateral, debt, interest, redemption, liquidation, revenue allocation, and safety rules in immutable contracts. No administrator can upgrade those contracts, change their accepted collateral, freeze BOLD transfers, or manually pause a branch.

At the same time, LQTY voting directs a limited liquidity-incentive stream; automatic code can restrict or wind down a distressed branch; frontends and external integrations remain separate trust surfaces; and users still bear collateral, oracle, peg, liquidity, redemption, and implementation risk.

That distinction is the useful one. Liquity does not promise that nothing can go wrong or that no system component can change. It promises that the current core's rules cannot be changed at an administrator's discretion. The May 2025 redeployment shows both sides of that wager: immutability can make the rules legible and resistant to capture, while making recovery from a deployed-code failure more operationally demanding.
