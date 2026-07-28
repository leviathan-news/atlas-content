MakerDAO is the Ethereum-based protocol that pioneered decentralized, overcollateralized stablecoins and on-chain governance; in August 2024 its community rebranded the system to **Sky**, introducing the USDS stablecoin and SKY governance token alongside the original DAI and MKR ([The Block](https://www.theblock.co/post/313235/makerdao-mkr-sky-dai-stablecoin-usds)).

For most of its history it has been one of decentralized finance's foundational pieces of infrastructure: a smart-contract network that lets users lock crypto collateral and mint a dollar-pegged stablecoin without a bank or custodian.

## Origins and Core Mechanism

The project launched in December 2017 with DAI, a stablecoin soft-pegged to the U.S. dollar but backed entirely by crypto assets held in smart contracts rather than by dollars in a bank. The mechanism is **overcollateralization**: a user deposits collateral (originally only ETH) worth more than the DAI they want to borrow, and the protocol mints new DAI against it. If the collateral's value falls below a required ratio, the position is automatically liquidated through on-chain auctions to keep the system solvent.

Three concepts anchor the design. A **vault** (originally called a Collateralized Debt Position, or CDP) is the individual loan a user opens against deposited collateral. The **stability fee** is the interest rate charged on minted DAI, set by governance. The **liquidation ratio** defines how much collateral must back each unit of debt. Together these levers let the protocol expand or contract DAI supply and defend the peg without a central operator.

This made MakerDAO an early proof that a stablecoin could be **decentralized** — governed by token holders and executed by code on Ethereum — rather than relying on a company holding reserves, the model used by USDT and USDC.

## Governance and the DAO

Maker is also one of the original examples of a **DAO** (decentralized autonomous organization): an entity whose decisions are made by token-holder voting rather than by executives. Holders of the governance token — historically **MKR**, now optionally upgraded to **SKY** — vote on risk parameters, which collateral types to accept, interest rates, and treasury spending.

The economics tie governance to system health. When the protocol earns more in fees than it spends, surplus revenue is used to buy back and burn the governance token, reducing supply. When liquidations fail to cover bad debt, the protocol can mint and sell new governance tokens to recapitalize, diluting holders. This creates a direct incentive for governance to manage risk prudently: token holders are effectively the backstop of last resort.

Over time, Maker governance evolved an elaborate apparatus of **delegates**, risk teams, and "core units" that functioned like decentralized departments. Critics long argued the structure was slow and bureaucratic, with low voter turnout concentrating effective power among a handful of large holders and professional delegates — a recurring tension across the **DAO** landscape.

## The Endgame and the Sky Rebrand

In 2022, co-founder Rune Christensen proposed "Endgame," a multi-year plan to make the protocol more resilient, more decentralized, and easier to govern. The most visible result arrived in August 2024, when MakerDAO rebranded to **Sky** and shipped a new token set ([Blockworks](https://blockworks.com/news/maker-rebrands-as-sky-dai-will-be-changed-to-usds)).

Under the rebrand, **USDS** became the upgraded stablecoin, convertible from DAI at a fixed 1:1 rate through an on-chain converter, while **SKY** replaced MKR as the governance token at a fixed ratio of 1 MKR to 24,000 SKY ([The Block](https://www.theblock.co/post/313235/makerdao-mkr-sky-dai-stablecoin-usds)). Importantly, the upgrade was designed to be optional and coexistent: DAI and MKR continue to circulate alongside USDS and SKY, and the converter contracts run in both directions indefinitely.

Endgame also introduced semi-autonomous units originally called **SubDAOs** and now branded **Stars** — each with its own focus, token, and treasury but tied to the core protocol through shared reserves and USDS integration. The lending front-end **Spark** is the most prominent of these, operating as a borrowing-and-savings layer built on Sky's liquidity.

By 2026, USDS supply had grown above $9 billion, and Sky's total value locked reached roughly $7.5 billion in March 2026, ranking it among the largest DeFi protocols ([Eco](https://eco.com/support/en/articles/11752998-usds-sky-protocol-2026-yield-guide)). Major exchanges scheduled automatic DAI-to-USDS conversions, with Binance migrating balances on April 7, 2026 and Coinbase following in early May ([BlockEden](https://blockeden.xyz/blog/2026/04/03/dai-usds-migration-makerdao-sky-protocol-stablecoin-rebrand/)).

## How DAI/USDS Stays Pegged Today

The peg mechanism has changed substantially since 2017. Early DAI was backed almost entirely by ETH. Today the collateral mix is far more diversified and, controversially, far less crypto-native. As of early 2026, Sky's backing was roughly 40% **real-world assets** (mostly short-term U.S. Treasury bills allocated through institutional partners), about 35% USDC routed through the Peg Stability Module, and the remainder in ETH, staked ETH, and other crypto collateral ([Eco](https://eco.com/support/en/articles/15197990-usds-vs-dai-2026-sky-s-migration-from-makerdao)).

The **Peg Stability Module (PSM)** lets users swap USDC for DAI/USDS at a fixed rate, which keeps the peg tight but means a large share of the "decentralized" stablecoin is ultimately backed by a centralized, freezable asset. The pivot into Treasury bills, meanwhile, transformed the protocol into one of the larger on-chain holders of U.S. government debt, generating most of its revenue but exposing it to traditional-finance counterparties and interest-rate cycles.

To pass yield back to users, Sky operates the **Sky Savings Rate (SSR)**, a contract that pays holders who deposit USDS a variable return — between roughly 3.75% and 4.5% APY in early 2026 — funded largely by the protocol's Treasury-bill income ([Eco](https://eco.com/support/en/articles/11752998-usds-sky-protocol-2026-yield-guide)). This savings rate has become a key competitive lever for attracting deposits and stablecoin float.

## Treasury Reform and Capital Rotation

In 2026 the protocol moved to overhaul how it manages money. Founder Rune Christensen proposed simplifying the **Treasury Management Function** after the transfer of Genesis Capital to a unit called Grove marked the end of the protocol's bootstrap "Genesis Capitalization" phase ([Cryptopolitan](https://www.cryptopolitan.com/sky-protocol-treasury-overhaul-genesis/)).

The proposal collapses a five-step conditional spending waterfall into four fixed allocations — security and maintenance, aggregate backstop capital, the Smart Burn Engine (which funds token buybacks), and USDS staking rewards — and caps expenses at a fixed percentage of revenue ([The Defiant](https://thedefiant.io/news/defi/sky-proposes-to-streamline-treasury-management)). The intent is to shift from ad hoc, **governance**-decided outflows to rules-based, predictable spending. The reform reflects a broader maturation: less improvisation, more mechanical policy.

That discipline coincided with notable capital rotation across DeFi. Reporting in 2026 described billions of dollars flowing out of competing lender **Aave** toward Sky's Spark, USDC, and other lower-risk venues as yields compressed and capital sought safer parking ([Blockworks](https://blockworks.com/news/sky-pivots-beyond-treasuries)). Sky governance simultaneously pruned Spark's exposure — offboarding certain Aave-deployed positions and adjusting supply caps on Bitcoin-pegged collateral — illustrating how actively the protocol now reallocates capital across **markets**.

## Risks and Criticisms

For all its longevity, the protocol carries real and debated risks. **Centralization of collateral** is the most cited: heavy reliance on USDC and Treasury bills means regulators or counterparties could, in theory, freeze assets that back a supposedly decentralized stablecoin. The 2023 USDC depeg, when Circle's reserves were briefly trapped at a failing bank, temporarily dragged DAI off its peg and underscored that dependency.

**Governance risk** is structural. Because token holders control collateral onboarding and risk parameters, a concentrated or compromised vote could alter the system's safety profile. **Smart-contract risk** persists as well — the entire edifice runs on **Ethereum** code, and the broader DeFi sector continues to suffer **hacks** and exploits, a reminder that even battle-tested contracts are not risk-free.

Skepticism reaches the protocol's own peers. In recent commentary, OpenZeppelin co-founder Manuel Aráoz said he now regards all of DeFi — including blue chips such as Aave, Compound, and Maker/Sky — as carrying systemic risk he was no longer comfortable with, urging a broad retreat from on-chain exposure. Such views are not consensus, but they capture an ongoing debate about whether DeFi's complexity has outrun its safety guarantees. Users should treat any stablecoin, custodied in a **wallet** or not, as carrying counterparty and contract risk rather than a guaranteed dollar.

## Why It Matters

Maker/Sky occupies an unusual position in **crypto**: simultaneously one of the most decentralized stablecoin systems and one of the most entangled with traditional finance. DAI and USDS function as base money across DeFi — used as collateral, trading pairs, and yield instruments throughout the **Ethereum** ecosystem. Changes to its parameters ripple outward, which is why governance votes draw intense scrutiny.

It also remains a live experiment in whether a **DAO** can manage a multibillion-dollar balance sheet responsibly over years, not months. The 2026 treasury reforms — trading discretionary governance for fixed rules — suggest the answer the community reached: at scale, predictability beats improvisation.

## Outlook

The protocol's trajectory points toward consolidation rather than reinvention. The Sky rebrand, the rules-based treasury, and the Stars/Spark architecture all aim to make a sprawling system simpler to govern and more resilient to shocks. The central tension is unlikely to resolve soon: deepening reliance on Treasury bills and USDC stabilizes the peg and funds the savings rate, but at the cost of the censorship-resistance that originally defined DAI. How Sky balances yield, decentralization, and regulatory exposure — while DAI and USDS coexist through a multi-year migration — will shape not just its own future but the template other stablecoin issuers follow.
