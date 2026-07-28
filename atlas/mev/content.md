The profit extracted by block producers and automated bots from reordering, inserting, or censoring transactions before they are finalized on a blockchain — Maximal Extractable Value, or MEV — has quietly become one of the most consequential forces shaping decentralized finance.

---

## What MEV Actually Means

The term was formalized in a 2019 paper by Phil Daian et al., titled *Flash Boys 2.0*, which borrowed the name from high-frequency trading research and applied it to Ethereum's transaction ordering mechanics. Originally called "Miner Extractable Value," the label shifted to "Maximal Extractable Value" after Ethereum's transition to proof-of-stake in 2022, when validators replaced miners as the parties controlling block construction.

In simple terms: every transaction broadcast to a public blockchain sits in a waiting room called the **mempool** before being included in a block. The entity assembling that block — a miner, validator, or a specialized actor called a **block builder** — can see all pending transactions and choose how to order them. That ordering discretion has economic value. Whoever controls it can front-run profitable trades, insert their own transactions at advantageous positions, or liquidate undercollateralized loans before anyone else. The cumulative dollar value of these opportunities is MEV.

## The Mempool: MEV's Attack Surface

The public mempool is a broadcast system. When a user submits a swap on Uniswap or any onchain decentralized exchange, that transaction travels through a peer-to-peer gossip network before any validator sees it. During that window — which on Ethereum averages around 12 seconds per block, though some estimates put the exploitable gap closer to 40 milliseconds for the most latency-sensitive strategies — automated bots monitor the mempool constantly, scanning for transactions they can profit from.

This broadcast-to-inclusion window is the core attack surface. Research from the MEV research collective Flashbots has documented hundreds of millions of dollars extracted annually on Ethereum alone since 2021. A narrower window directly shrinks the viable strategy set; proposals like encrypted mempools target this gap specifically.

## The Three Main Extraction Strategies

**Front-running** is the simplest form. A bot detects a large pending buy order — say, someone purchasing $500,000 of a small-cap token — and submits its own buy ahead of it at a slightly higher gas price, then sells immediately after the victim's transaction executes at the inflated price. The victim pays more; the bot pockets the difference.

**Sandwich attacks** are a refinement. The bot places one transaction immediately before the target and one immediately after — "sandwiching" the user's trade. The first transaction moves the price against the user; the second unwinds the bot's position at a profit. For a user, the result is worse execution than the quoted price, with slippage they did not expect.

**Arbitrage** is MEV's least controversial form. When the same asset trades at different prices across two decentralized exchanges, bots close that gap by buying on the cheaper venue and selling on the more expensive one. This is economically beneficial — it aligns prices across the market — but the profits still flow to bots rather than ordinary traders or protocols.

**Liquidation MEV** is particularly significant on lending protocols like Aave. When a borrower's collateral falls below the required ratio, anyone can call the liquidation function and collect a bonus. Bots race to be first, which is why gas wars around liquidations can spike network fees for everyone.

## Sandwich Attacks in Practice: The jaredfromsubway.eth Case

No single entity illustrates MEV's reach — and its fragility — more vividly than the Ethereum bot known by the ENS address jaredfromsubway.eth. For years, this bot was one of the most active sandwich attackers on Ethereum mainnet, extracting value from DEX traders at industrial scale and, at peak activity, spending more on gas than almost any other address on the network.

In mid-2024, the bot itself became the victim. Attackers exploited a vulnerability in the bot's smart contract logic and drained it in two separate incidents — one totaling approximately $7.7 million, a second bringing reported losses to over $15 million. The attacker converted the stolen funds to ETH and moved them onchain. The episode was notable for several reasons: it demonstrated that sophisticated MEV infrastructure carries its own smart contract risk; it confirmed that even highly profitable automated systems can be reverse-engineered and exploited; and it raised fresh questions about the concentration of MEV extraction in the hands of a small number of operators.

## Validators and Block Building: The Structural Layer

On Ethereum post-merge, the MEV supply chain has been formalized through **Proposer-Builder Separation (PBS)**. Under this architecture, specialized **block builders** compete to assemble the most profitable block, then bid for validators (proposers) to include it. Validators receive a payment for their slot; builders keep whatever MEV they can extract above that payment.

Flashbots' **MEV-Boost** middleware, adopted by the majority of Ethereum validators, routes this competition through a relay layer. Critics note that PBS concentrates block-building power in a small number of sophisticated entities, creating centralization pressure. The validator set earns more revenue — which affects ETH staking economics — but does not itself perform the extraction.

On **Solana**, the architecture differs: block production is more tightly coupled to validators, and the mempool is not public in the same way. However, priority fees function as a similar signal, and sandwich-style MEV still occurs, particularly through private transaction routing and validator collusion risks that researchers have flagged.

## MEV Protection: What Exists Today

The response to MEV has been diverse, spanning cryptography, protocol design, and application-layer routing.

**Private mempools and RPC endpoints** like Flashbots Protect allow users to submit transactions that bypass the public mempool entirely, going directly to trusted builders. This prevents front-running bots from seeing the transaction before inclusion. **1inch's Fusion protocol** routes swaps through a Dutch auction mechanism where professional market makers (called resolvers) compete for fill rights, providing MEV protection as a byproduct of the design. 1inch has extended this to gasless, MEV-protected swaps for real-world asset trades through partnerships including KuCoin's Web3 Wallet.

**CoW DAO's CoW Protocol** (formerly CowSwap) uses **batch auctions**: multiple user orders are aggregated and settled together by a solver network. Because trades within a batch clear at a uniform price, sandwich attacks cannot insert between individual transactions — the batch boundary removes the ordering advantage.

**MEV-resistant AMM pools** have emerged on protocols including Aerodrome on Base, which has shipped anti-MEV gauges. These typically use time-weighted pricing or other mechanisms that make price manipulation less profitable.

**Encrypted mempools** represent the cryptographic frontier. Ethereum's **EIP-8105** proposes hiding transaction content until a transaction is included in a block, using threshold encryption or similar schemes. BTX has released a batched threshold encryption scheme for this purpose. The tradeoff is added latency and complexity in the consensus mechanism; a validator must be able to decrypt committed transactions only after the block is finalized, which requires coordination among threshold key holders.

**Oracle Extractable Value (OEV)** is a related concept. When oracle price feeds update onchain — as Chainlink feeds do — the update itself can be front-run. Aave V4 has integrated Chainlink's SVR (Staking Value Reference) feeds specifically to redirect liquidation MEV back to the Aave DAO rather than to bots. Since 2025 this has returned over $11 million to the protocol treasury, illustrating that MEV can be captured at the protocol level rather than leaked to third parties.

**1inch Smart Settlement** is another recent addition: an execution upgrade designed to protect users from slippage, MEV, just-in-time (JIT) liquidity attacks, and PropAMM manipulation, aiming to improve swap output after a best quote is obtained.

## MEV Across Chains: Not an Ethereum-Only Problem

MEV is not Ethereum-specific; it is a property of any permissionless blockchain where transaction ordering has economic value and ordering is controlled by a small set of actors.

On **Solana**, the absence of a global mempool creates different dynamics but not immunity. Validators who receive transactions before broadcasting them have ordering discretion. Proposals like multi-proposer consensus (as seen in Sei's Autobahn architecture) can reduce single-validator ordering power but may increase duplicate transaction spam as a tradeoff. Sei's forthcoming **Sedna** protocol targets this directly, combining spam removal with MEV resistance for its Giga throughput architecture.

Chains with shorter block times shrink the profitable window for certain MEV strategies: at 40ms block times, many sandwich bot strategies become economically marginal. But faster finality does not eliminate MEV that is embedded in the block-building process itself.

**Flare Network** is navigating MEV considerations as part of its FIP.16 governance vote, which involves inflation adjustments and fee structure changes that could alter the MEV landscape on that chain.

## Why Institutions Care

For institutional participants — asset managers, market makers, treasury desks — MEV is not an abstract concern. Every large swap on a public DEX is a potential sandwich target. Predictable slippage is a prerequisite for any execution quality standard; MEV makes slippage adversarial rather than merely stochastic.

This is why MEV resistance has become a stated requirement in institutional blockchain infrastructure discussions. Protocols that can provide execution quality guarantees — through private order flow, batch settlement, or on-chain fairness mechanisms — have a meaningful advantage in competing for institutional volume. As tokenized real-world assets increasingly settle onchain, the pressure to solve MEV at the infrastructure layer will intensify.

## Regulatory Overhang

MEV occupies a gray zone in regulatory frameworks. Front-running in traditional markets is illegal. Whether front-running a public blockchain transaction — which is, by definition, visible to all — constitutes the same offense is unresolved. The SEC has not issued specific MEV guidance. Some legal scholars argue that because users broadcast transactions publicly, bots that respond to that signal are operating within the rules. Others argue the practical effect on retail users is indistinguishable from front-running and should be treated accordingly.

The question becomes more acute as regulated institutions interact with public blockchains. A registered broker-dealer that routes client orders through a system subject to MEV may face best-execution obligations that are difficult to reconcile with public mempool dynamics.

## Outlook

MEV is unlikely to disappear; it is a structural consequence of transparent, permissionless transaction ordering. What is changing is the distribution of who captures it, and how much of it can be redirected to users and protocols rather than extracted by bots.

Encrypted mempools, if they can be made practical without sacrificing liveness, would substantially reduce front-running and sandwich attacks. Protocol-level MEV capture — as Aave is demonstrating with Chainlink SVR — suggests that value currently leaking to bots can be reclaimed for DAO treasuries and liquidity providers. Application-layer solutions from CoW Protocol, 1inch, and others are already reducing extractable value per swap for users who opt in.

The jaredfromsubway.eth episode is a useful coda: MEV bots are not invincible infrastructure. They are software with attack surfaces, and the same adversarial environment they exploit can be turned against them. The broader trend is toward making MEV either invisible to end users through smart routing, or captured by protocols through explicit mechanism design — leaving less and less on the table for pure extraction.

---
