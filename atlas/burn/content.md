In crypto, a burn is the permanent removal of coins or tokens from circulation, usually by sending them to an address nobody can spend from or by invoking a contract function that reduces supply. The mechanism is simple. Its economic meaning is not.

Burns can offset issuance, connect protocol revenue to a token, reconcile assets moving between chains, or maintain the backing of a redeemable stablecoin. They can also serve as promotional theater: a large number disappears, the project celebrates scarcity, and nothing important changes about demand, revenue, security, or governance.

The right category is therefore not “bullish token event.” A burn is a supply-accounting operation whose significance depends on its funding source, relationship to issuance, effect on liquidity, and connection to real usage. It can be economically substantive, operationally necessary, or almost entirely cosmetic.

## What “burn” means in crypto

At its core, a token burn is a deliberate and irreversible destruction of digital units recorded on a blockchain. The familiar implementation sends tokens to a verifiably unspendable address, sometimes called a burn or eater address. Its private key is unknown or constructed so that no usable key should exist. Once a transfer is confirmed, the tokens remain visible on the ledger but cannot return to circulation.

Some token contracts use an explicit burn function instead. Rather than placing units in an inaccessible account, the contract subtracts the amount from the holder’s balance and reduces its recorded total supply. The accounting route differs, but the intended result is the same: the holder gives up control permanently, and the system recognizes fewer outstanding units.

That distinction matters when interpreting data. Tokens parked at a recognizable dead address may remain included in a contract’s raw supply calculation even though they are economically inaccessible. A native burn function may reduce the reported total directly. Circulating-supply services can apply still other rules. A serious analysis therefore checks both the transaction and the supply convention instead of assuming every dashboard uses “burned” in exactly the same way.

Burns appear in several economic categories that should not be conflated. A treasury burn destroys units already controlled by a project. A fee burn destroys value paid by users. A buyback-and-burn spends revenue or reserves to acquire tokens from the market before destroying them. A redemption burn cancels tokens returned to an issuer. A bridge burn can be one leg of moving an asset between networks. Proof-of-Burn sacrifices capital to obtain participation rights in a consensus or distribution mechanism.

All remove tokens, but they do not transfer value in the same direction. Burning an idle treasury allocation can reduce the possibility of future dilution without creating new demand. Buying tokens from sellers with earned revenue creates market demand before reducing supply. Burning a transaction fee converts network activity into supply contraction. Burning a redeemed stablecoin records the departure of capital rather than a reward to remaining holders.

That is the first useful test: identify what economic event the burn records. The transaction alone proves that specified units became inaccessible or were removed from the contract’s supply. It does not prove that the token became more valuable, that the protocol earned revenue, or that demand will persist.

## How burns work onchain

A conventional burn address behaves like a one-way sink. A wallet or contract submits a normal transfer, the network validates it, and the destination balance increases. Anyone can inspect the transaction, amount, sender, destination, and block time. The crucial assumption is that nobody can authorize a later transfer from the destination.

Recognizable addresses such as zero-like accounts or addresses ending in “dead” make the intent easy to see, but appearance is not proof. An unusual address is only safely treated as a burn destination when its unspendability follows from the network’s rules or is otherwise well established. Sending tokens to an ordinary wallet and labeling it “burn” merely replaces circulating supply with custodial trust.

Contract-level burning is more direct. A properly implemented function checks that the caller may destroy the specified amount, subtracts it from the relevant balance, updates total supply, and emits an event that indexers can follow. The operation should obey the same authorization and arithmetic constraints as transfers and minting. Weak access controls, inconsistent accounting, or faulty proof verification can turn a supply-management primitive into a security boundary.

This is where “publicly auditable” needs careful treatment. A transaction can be visible while the mechanism surrounding it remains difficult to evaluate. Readers may be able to verify that units reached a sink but not whether an undisclosed mint function can recreate them. They may see a supply reduction without knowing whether another chain issued matching representations. They may observe a buyback wallet without being able to distinguish earned revenue from treasury recycling.

A complete audit trail therefore has several layers: the burn transaction, the contract’s resulting supply, any issuance during the same period, the origin of assets used for a buyback, and the governance rules that can alter the mechanism. Visibility is a necessary property, not a substitute for understanding the whole accounting system.

### Stablecoin redemption burns

Fiat-backed stablecoins illustrate why a burn is not automatically deflationary value accrual. When users deposit eligible fiat with an issuer, corresponding stablecoins can be minted. When they redeem, the issuer receives the tokens, destroys or cancels them, and returns fiat under its redemption process. The circulating token supply falls because the issuer’s outstanding onchain liability has fallen.

This resembles canceling a redeemed stored-value certificate, not repurchasing equity. A large redemption burn may indicate that holders are leaving the asset or moving capital offchain. Remaining units are not supposed to appreciate through scarcity; each is supposed to continue tracking its redemption value. The burn helps keep claims aligned with reserves.

The gain is cleaner liability accounting and a supply that can contract with redemptions. The cost is dependence on the issuer’s custody, banking access, compliance systems, and offchain books. Onchain destruction proves that tokens were removed. It does not by itself prove that every reserve asset exists, is liquid, or is available under stress.

### Bridges and burn-and-mint accounting

Cross-chain systems use burns differently. A representation may be burned on one network before an equivalent amount is minted or released on another. If the system is correctly designed, local supplies change while aggregate claims remain consistent. The burn is not intended to make the asset scarcer; it is an accounting leg in relocation.

Other bridges lock the original asset and mint a wrapped claim elsewhere. Returning requires burning the wrapped asset before unlocking the original. In either design, the core invariant is that transferable claims across all supported networks should not exceed the assets or authorized supply backing them.

This makes bridge burns closer to warehouse-receipt cancellation than to corporate buybacks. Their value lies in preserving one-for-one accounting across separate ledgers. Their risk lies in the messaging, verification, custody, and minting authorities that connect those ledgers. A flawless burn on the destination chain cannot compensate for an unauthorized mint, compromised validator set, or falsely released collateral elsewhere.

When a bridge closes or a migration window expires, projects may use manual burn-and-remint procedures. A user destroys a stranded representation, submits evidence, pays any required fee, and waits for an issuer to recognize the claim on another chain. That can restore value, but it replaces automatic composability with operational trust. The burn is irreversible while settlement may be delayed, reviewed, or processed in batches.

The reader’s test is concrete: determine what must happen after the burn, who controls that step, what evidence they accept, and whether the system exposes a reliable record of outstanding claims. If the user must trust a team to complete the other side, the procedure is not trustless merely because the first transaction is onchain.

## Burns within tokenomics and supply design

Tokenomics describes how a token is created, distributed, used, vested, governed, and removed. Burns affect only one side of that system. The decisive measure is net supply change, not gross destruction.

Let M represent all units minted during a period and B represent all units burned. Net supply change is ΔS = M − B. If the result is positive, supply expanded despite the burn. If it is negative, supply contracted during that period. If it is near zero, burns mainly offset issuance.

A project that mints 10 million units and burns 5 million can truthfully advertise a 5 million-token burn, yet holders still experienced 5 million units of net inflation. A project that mints one million and burns two million contracted by one million. Quoting the burn without issuance is like quoting a company’s revenue without its costs: the number is real but analytically incomplete.

The time window also matters. A token may be net deflationary during a week of unusually high activity and inflationary across a year. Emissions can change as vesting schedules, staking rewards, ecosystem grants, or governance decisions evolve. Claims about “deflationary” design should specify whether they describe a permanent rule, a current run rate, or an observed historical period.

Bitcoin offers a useful contrast. Its issuance declines according to a fixed schedule and its maximum supply is capped, but ordinary transfers do not depend on a systematic burn. Its scarcity comes primarily from constrained issuance. Burn-oriented tokens instead modify supply by destroying units after creation. Both can reduce future dilution, but they do so through different mechanisms and expose holders to different governance risks.

Some systems combine continuing issuance with transaction-fee burns. Under low usage, issuance may exceed burns; under high usage, burns may catch up or move ahead. This creates an activity-sensitive supply curve. The advantage is that greater demand for block space can directly reduce net issuance. The trade-off is that monetary conditions become dependent on usage, fee markets, and validator compensation rather than on a simple fixed schedule.

Other projects define a supply ceiling and use burns to keep issuance within it. A ceiling can make long-run dilution easier to bound while preserving rewards for security or participation. But a ceiling does not answer who receives newly issued tokens before the limit is reached, how quickly supply approaches it, or whether governance can amend the parameters.

The relevant reclassification is simple: token supply is a flow system, not a headline stock number. Minting, vesting, unlocking, bridging, staking rewards, fee collection, and burning all enter that flow. A burn mechanism deserves attention only in relation to the other pipes.

## Major burn models

### Treasury burns and launch-stage cleanup

The simplest model destroys tokens held by a project treasury, foundation, or launch contract. Unsold sale inventory, unclaimed allocations, or surplus reserves may be removed so they cannot enter circulation later. The immediate benefit is reduced overhang: holders no longer need to price the possibility that those particular units will be distributed or sold.

The limitation is equally important. A treasury burn does not necessarily purchase anything from current holders, generate protocol revenue, or improve the product. If the tokens were already excluded from circulating supply, the event may change total supply without changing tradable scarcity today. Its economic effect depends on whether the market reasonably expected those units to circulate.

A treasury burn can still be a credible commitment. Destroying an allocation removes managerial discretion and can narrow the range of future dilution. Yet commitment cuts both ways. The project also gives up assets that might have funded security, development, incentives, or emergency response. The decision trades flexibility for a harder supply promise.

Launch-stage burns are particularly susceptible to large-number framing. A token may begin with an enormous nominal supply, destroy a similarly enormous portion, and leave ownership concentration almost unchanged. Percentages, fully diluted supply, circulating supply, and holder distribution are more informative than the raw number of units burned.

### Buyback-and-burn funded by revenue

Buyback-and-burn is the closest crypto analogue to a corporate share repurchase. A protocol uses fees or other assets to buy its token from willing sellers, then destroys the acquired units. The purchase creates demand in the market; the burn prevents the protocol from later reselling what it bought.

The analogy is useful but imperfect. Equity represents legal rights in a company, while a token’s rights vary widely and may amount only to governance or utility. A corporate repurchase operates inside established accounting, disclosure, and capital rules. A token program may depend on mutable smart contracts, informal governance, thin liquidity, or a treasury controlled by a small group.

The strongest versions specify the revenue source, allocation percentage, execution schedule, eligible markets, custody path, and burn transaction. They let observers trace value from user activity to collected fees, from fees to purchases, and from purchased tokens to destruction. This turns the mechanism into an observable claim rather than a slogan.

The benefit is direct linkage between protocol use and token demand. The cost is capital allocation. Every dollar spent buying and destroying tokens is a dollar unavailable for audits, development, insurance, liquidity incentives, contributor pay, acquisitions, or reserves. A mature protocol with recurring surplus faces a different decision from a young project sacrificing runway to support its token price.

Execution design matters too. Predictable market purchases can be front-run. Large buys in shallow pools can move price temporarily and transfer value to traders who anticipate them. Discretionary purchases invite concerns about timing and manipulation. Auctions, time-weighted execution, transparent mandates, and governance limits can reduce these problems, though none eliminates the underlying liquidity constraint.

A buyback funded by new token sales is economically weaker than one funded by external revenue. The first can amount to rotating value among holders while presenting the result as income-driven scarcity. The second demonstrates that users paid the protocol in assets other than the token being destroyed. Readers should trace where the purchasing assets came from before treating the burn as value accrual.

### Protocol fee burns

Fee burns occur inside a network or application’s normal operation. Users pay for block space, swaps, or another service, and a predetermined share is destroyed. Ethereum’s EIP-1559 popularized the model at the base layer: transactions pay a dynamically adjusted base fee that is burned, while a separate priority fee can compensate block producers.

This changes the economic role of fees. Instead of transferring the entire payment from users to validators, the protocol removes the base-fee portion from supply. When demand for block space is high, more ETH is burned; when activity is weak or fees are low, less is burned. Whether total supply contracts depends on the relationship between those burns and issuance to validators.

The gain is that network usage feeds directly into the token’s monetary policy. The cost is that value no longer paid to validators must be balanced against security incentives, while users still bear the fee. Burning does not make transactions free; it determines where the economic value of part of the fee goes.

At the application layer, fee burns compete with other recipients. Trading fees can reward liquidity providers, fund a treasury, cover insurance, pay contributors, subsidize users, or buy and destroy tokens. Shifting a percentage toward burns benefits holders through lower supply or market demand but can reduce compensation for the participants producing the service.

Governance around those splits is therefore distributional politics expressed as protocol parameters. “Turning on value accrual” sounds technical, but it decides which constituency gives up revenue and which gains. A robust analysis identifies the payer, the displaced recipient, the beneficiary, and the authority able to change the percentage later.

### Elastic and event-driven mint-and-burn systems

Some designs allow supply to rise or fall in response to prices, external events, oracle inputs, or algorithmic rules. Burns are only one side of an elastic system. A win, milestone, or favorable condition may trigger destruction; an adverse condition may trigger minting. The supply becomes a state variable tied to something beyond ordinary transactions.

Sports-linked fan tokens illustrate the appeal. Match outcomes can be translated into programmed scarcity, turning a real-world event into an onchain supply event. The mechanism makes fandom measurable and creates a recurring narrative. It also introduces oracle risk, game-like incentives, and a weak connection between scarcity and enduring utility.

The benefit is engagement: users can understand that an external result has a defined token consequence. The cost is that supply becomes dependent on data feeds and event definitions. If the oracle fails, the rule is ambiguous, or administrators retain discretion, the apparently automatic mechanism can become a governance dispute.

Algorithmic stablecoin systems have used mint-and-burn rules for a much more demanding objective: defending a peg. Burning one asset to mint another can create arbitrage incentives, but it cannot manufacture reliable collateral or demand. When confidence breaks, reflexive issuance can overwhelm the burn mechanism. An equation that balances during normal markets may fail precisely when holders all want the exit.

The useful distinction is between a fully collateralized redemption loop and an expectation-driven stabilization loop. Both may burn tokens. Only the former necessarily pairs the canceled liability with identifiable backing under its stated model.

### Proof-of-Burn and burn-based distribution

Proof-of-Burn replaces some form of continuing physical expenditure or stake locking with permanent capital sacrifice. Participants destroy coins to gain mining power, allocation rights, or access to a new system. The burn acts like purchasing equipment that cannot be resold: the participant pays an irreversible cost in pursuit of future rewards.

Its appeal is reduced dependence on energy-intensive competition and a visible commitment from participants. Its drawback is capital inefficiency. Destroyed assets cannot secure another system, provide liquidity, or be recovered if the new network fails. Wealthy holders may also obtain an advantage simply because they can afford larger irreversible sacrifices.

Burn-based launches can distribute a new token to users who destroy an older one. This can avoid a conventional sale and align early ownership with people willing to commit value. It also transfers risk sharply to participants: they surrender the original asset before knowing whether the replacement ecosystem will attract users, developers, or liquidity.

Proof-of-Burn remains a niche design because permanent destruction is a severe instrument. Proof-of-Stake can penalize misconduct while preserving capital in ordinary operation; Proof-of-Work consumes resources continuously; Proof-of-Burn front-loads an irreversible cost. None is free, but the timing and recoverability of the cost differ.

## Burns as security and recovery operations

Burning is not only tokenomics. It can be a remediation tool after an exploit, accounting failure, unauthorized issuance, or migration. Compromised units may be destroyed after recovery. Excess rewards or mistakenly issued supply may be removed through an upgrade. Wrapped assets can be burned before legitimate claims are restored elsewhere.

This category should be separated from shareholder-like value accrual. A remediation burn may prevent invalid or compromised units from remaining spendable, but it does not erase the incident that created them. The important questions concern who absorbed the loss, whether all affected units were recovered, whether the vulnerability was fixed, and what authority performed the correction.

Burn proofs can themselves become security-critical inputs. A system may release value, recognize a withdrawal, or authorize a mint after receiving evidence that tokens were destroyed elsewhere. If a verifier accepts an invalid proof, the attacker can obtain the benefit of burning without bearing the cost. The conceptual invariant is broken even if the destination chain’s later transactions appear normal.

This reframes a burn proof as a receipt accepted by another financial system. The receipt must establish the correct asset, amount, owner, chain, state transition, and uniqueness. It must not be replayable, forged, or detached from the event it claims to represent. Cryptographic sophistication does not excuse a verifier from checking the right statement.

Recovery burns also highlight the difference between supply repair and user restitution. Destroying unauthorized units can restore an accounting total while leaving victims uncompensated. Conversely, making users whole from reserves can address losses without changing supply. A complete incident assessment tracks both ledgers: the token supply and the economic claims of affected users.

## Why protocols burn

One motive is to offset inflation. Staking rewards, liquidity incentives, contributor grants, and ecosystem emissions expand supply. Burning a portion of fees can reduce the dilution borne by existing holders without eliminating the incentives that help operate or grow the network.

Another motive is to connect usage with the token. A governance token that receives no fees and has no required role may be weakly linked to the protocol it governs. Routing revenue into purchases or burns creates a measurable channel through which greater use can affect token supply or demand.

That connection should not be overstated. A fee-funded burn can improve token economics while the product loses market share, margins shrink, or governance becomes captured. It creates a transmission mechanism, not a guarantee of value. The protocol still needs users willing to pay, defensible services, sound security, and governance capable of allocating capital.

Burns also signal commitment. A team that destroys treasury holdings gives up the option to sell them. A network that codifies fee destruction constrains how future fees are distributed. An issuer that burns redeemed tokens demonstrates that canceled claims are not quietly recycled.

Signals are strongest when costly, verifiable, and hard to reverse. They are weaker when administrators can mint replacement units, change the schedule immediately, or move tokens to an address they still control. Governance permissions belong in any assessment of the burn’s credibility.

Finally, burns are narrative instruments. Supply reduction is easy to visualize and market. Dashboards can show a rising cumulative total; social posts can celebrate milestones; every event can be framed as increased scarcity. That communicative clarity is useful, but it encourages analysis by numerator alone. A rising burn total may coexist with greater issuance, declining demand, lower revenue, or thinner liquidity.

## Risks, limitations, and common misunderstandings

### Scarcity does not create demand

Reducing supply can support price if demand is stable or rising. If demand collapses, a smaller supply can still lose value. Burning changes the quantity available; it does not create product-market fit, useful governance, reliable cash flow, or trust.

This is the central trade-off. Burns can concentrate the economic exposure of remaining holders, but they cannot supply the reason anyone wants that exposure. A protocol that spends heavily on burns while neglecting its product may improve a ratio and weaken the business producing it.

### Gross burns can disguise net inflation

A cumulative burn counter almost always rises because destroyed tokens do not return. That makes it a flattering metric. Issuance, however, can rise faster. Vesting unlocks may also increase tradable supply even when total supply declines.

Readers should compare burns with all minting and with changes in circulating supply. The relevant denominator should be explicit: one million tokens is enormous for a ten-million-token asset and negligible for a trillion-token asset.

### Liquidity can deteriorate

A lower circulating supply does not necessarily mean healthier markets. If burns remove tokens from already thin pools or if buybacks temporarily consume available offers, spreads and volatility can increase. Price may rise during execution but become easier to move in either direction afterward.

For tokens used as collateral, payment assets, or trading pairs, liquidity may be part of utility. Destroying supply can therefore trade nominal scarcity for worse market function. Volume, depth, concentration, and slippage should be evaluated alongside the burn rate.

### Governance can redirect the mechanism

Many burn programs are controlled by governance, multisignatures, or upgradeable contracts. That flexibility permits adaptation but weakens permanence. Future voters can alter fee splits, stop purchases, change authorized markets, or revise issuance.

A current parameter is not the same as an immutable monetary guarantee. The reader can test this by checking who holds upgrade authority, what delay applies to changes, and whether token holders or a smaller administrative group make the final decision.

### Buybacks can be manipulated or poorly funded

Opaque execution creates opportunities for selective timing, insider positioning, and exaggerated impact. A project can announce future purchases before securing the revenue needed to make them. It can also count transfers between affiliated wallets as economic activity.

A credible program exposes actual fee inflows, acquisition transactions, execution rules, and final burn events. Even then, transparency establishes that the policy was followed; it does not establish that buying tokens was the best use of capital.

### Bridge burns add operational dependencies

Burning a wrapped token may be irreversible even when the corresponding release or remint depends on human review. Users can send the wrong asset, use the wrong chain, miss a deadline, or fail to preserve required evidence. A support process may have limited remedies because the initial burn cannot be undone.

The safe mental model is a multi-step settlement, not a single transaction. Completion occurs only when the user receives the destination asset or underlying collateral, not when the source-chain burn succeeds.

### Stablecoin burns are flow indicators

A large stablecoin burn often records redemption and capital exit. It can reflect routine treasury management, exchange flows, or broader risk reduction. Calling it bullish because supply fell mistakes liability cancellation for value creation.

The number becomes useful when compared with minting, reserves, redemption conditions, exchange balances, and broader activity. Its meaning comes from flows, not from scarcity rhetoric.

## How to evaluate a burn announcement

Start with classification. Is this a treasury burn, market buyback, protocol fee burn, redemption, bridge operation, incident response, or distribution mechanism? If an announcement mixes categories, separate them before judging the economics.

Then ask what funded it. Existing treasury tokens cost the project flexibility. Fee-funded market purchases consume earned assets. User-paid fee burns redirect transaction value. Redemption burns correspond to liabilities being canceled. Each source tells a different story.

Next calculate net supply change over a relevant period. Include ordinary issuance, staking rewards, incentives, vesting, administrative mints, and burns. Compare the result with both total and circulating supply. A percentage rate is usually more informative than a raw token count.

Trace control. Identify who can mint, burn, upgrade, pause, redirect fees, or change parameters. Determine whether changes require a public vote, a timelock, a multisignature, or a single key. A transparent burn can coexist with concentrated monetary authority.

Examine demand. What requires or rewards holding the token? Does the protocol have recurring users and fees? Are those fees paid in an external asset or primarily in newly issued tokens? Is the burn large relative to revenue, liquidity, and dilution?

Inspect market structure. A buyback executed in shallow liquidity may create an impressive price candle without durable value. Look at depth and trading concentration, not just volume. Determine whether treasury purchases dominate organic demand.

For bridges or recovery systems, verify the complete state transition. A source-chain burn should correspond to an authorized destination-chain mint, release, or claim reduction. Check for delays, manual approvals, fees, supported assets, and replay protection.

For proof-based systems, ask what the proof actually establishes and what the verifier checks. “Zero knowledge” or “cryptographically verified” describes a technique, not the correctness of the statement being verified. The security boundary includes circuit logic, public inputs, implementation, deployment, and upgrade controls.

Finally, distinguish evidence from interpretation. An onchain transaction can establish that specified tokens moved to a sink. Contract state can establish a reported supply after execution. Fee records can establish revenue received. None alone establishes future demand or a justified valuation.

## A practical comparison

| Burn model | Funding source | What it can accomplish | Principal trade-off |
|---|---|---|---|
| Treasury burn | Existing project allocation | Remove future supply overhang | Sacrifices treasury flexibility; may not change circulation |
| Buyback-and-burn | Fees, revenue, or reserves | Create market demand and reduce supply | Competes with development, security, and reserves |
| Protocol fee burn | User transaction or application fees | Tie usage to supply contraction | Redirects value from validators, providers, or treasury |
| Redemption burn | Returned redeemable tokens | Align outstanding claims with backing | Often signals capital exit, not holder value accrual |
| Bridge burn-and-mint | Cross-chain settlement | Move representations without expanding aggregate claims | Depends on messaging, verification, and mint authority |
| Elastic mint-and-burn | Oracles, prices, or external events | Adjust supply dynamically | Adds complexity, reflexivity, and oracle risk |
| Proof-of-Burn | Permanently sacrificed capital | Allocate participation or security rights | Capital is irrecoverable and can favor wealthy participants |
| Recovery burn | Recovered or invalid units | Repair supply accounting after an incident | Does not by itself restore users or fix governance failures |

The table’s central lesson is that “burn” names a mechanism, not a strategy. The same primitive can manage liabilities, distribute rights, move value between chains, repair an exploit, or advertise scarcity. Its meaning comes from the surrounding system.

## Outlook

Burn mechanisms are likely to remain common because they give protocols a programmable way to connect fees, governance, and supply. As onchain applications mature, the most credible designs will increasingly be judged by complete capital allocation: how much revenue goes to security, contributors, reserves, incentives, direct distributions, and burns.

The strongest burn systems will make their invariants observable. Users should be able to trace issuance and destruction, identify the assets funding purchases, understand who can change the rules, and reconcile cross-chain claims. The strongest economic cases will also show that the product earns durable demand before celebrating how it distributes the proceeds.

More sophisticated infrastructure will not remove the need for judgment. Automated burns can execute a weak policy perfectly. Transparent dashboards can display a deteriorating business accurately. Immutable rules can lock in an allocation that later starves development or security.

The durable conclusion is deliberately narrower than the marketing promise. Burns can reduce dilution, enforce accounting, or transmit usage into token supply. They cannot substitute for demand, solvency, security, or sound governance.

If fees come from real use, issuance remains below destruction, liquidity stays functional, and governance cannot casually reverse the mechanism, a burn can become a meaningful component of value accrual. If those conditions fail, the burn is merely a smaller supply of the same unresolved problem.
