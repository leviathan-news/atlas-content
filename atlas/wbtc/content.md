Bringing the largest cryptocurrency by market value onto smart-contract platforms requires a bridge, and for years the most-used one has been a token called Wrapped Bitcoin. It is an ERC-20 token on Ethereum (and several other chains) that is backed 1:1 by bitcoin held in custody, letting BTC holders participate in decentralized finance (DeFi) without selling their underlying coins.

## What WBTC Is and Why It Exists

Bitcoin and Ethereum are separate blockchains with incompatible architectures. Bitcoin's scripting language is intentionally limited and does not natively support the complex smart contracts that power lending markets, decentralized exchanges, and yield protocols. As a result, native BTC cannot move directly into Ethereum-based applications such as Aave, Uniswap, or Maker.

Wrapped Bitcoin solves this by representing bitcoin as a token that conforms to Ethereum's ERC-20 standard. Each WBTC is intended to be redeemable for one bitcoin, with the underlying BTC held in reserve by a custodian. This lets a bitcoin holder supply WBTC as collateral, earn lending yield, provide liquidity, or trade — all while maintaining price exposure to BTC ([Coin Bureau](https://coinbureau.com/education/what-is-wrapped-bitcoin)).

The rationale is significant in scale. Bitcoin is a multi-trillion-dollar asset class, yet only a small fraction of it is active in DeFi. Newsroom coverage citing on-chain data notes that roughly 1.2% of BTC supply sits in DeFi, while about 34% of WBTC supply has been deposited into protocols — a sign that holders who do wrap their coins are actively putting them to work as collateral and for borrowing.

## How WBTC Works

WBTC operates on a mint-and-burn model administered by a set of defined roles:

- **Custodian** — holds the underlying bitcoin in reserve. WBTC launched in 2019 with BitGo as sole custodian; in 2024, BiT Global was added as a co-custodian ([Cointelegraph](https://cointelegraph.com/research/wrapped-bitcoin-in-defi-evaluating-wbtc-cbbtc-and-tbtc)).
- **Merchants** — intermediaries (typically exchanges, market makers, or trading firms) that initiate the minting and burning of tokens on behalf of users.
- **wBTC DAO** — a governance body of industry participants that controls the smart-contract permissions, including which addresses can act as merchants and custodians.

To **mint** WBTC, a merchant sends bitcoin to the custodian, who verifies receipt and then issues an equivalent amount of WBTC on the destination chain. To **redeem**, the process runs in reverse: WBTC is burned and the corresponding bitcoin is released from custody. Because every token is meant to be backed by reserved BTC, WBTC's price tracks bitcoin closely, and the system publishes proof-of-reserve data so the on-chain supply can be checked against custodial holdings.

This design makes WBTC **custodial**. Users must trust that the custodian holds the reserves and will honor redemptions. That trust assumption is the central trade-off distinguishing WBTC from non-custodial alternatives, and it is the main axis along which competitors position themselves.

## Custody, Governance, and the BiT Global Transition

WBTC's custody arrangement has been in transition. After BiT Global joined as co-custodian in 2024, the network announced a phased move toward a multi-party key structure. Under the plan, the transition was expected to complete around May 1, 2026, with BiT Global holding the user key and the backup key — one in Hong Kong and one in Singapore — while BitGo retains one of the three private keys in a multi-signature wallet and continues to support minting and redemption infrastructure ([WBTC Network](https://wbtc-network.medium.com/bit-global-to-complete-next-phase-of-wbtc-custody-transition-ac4049691210)).

The custodial changes drew scrutiny. When the arrangement was first announced, redemptions reportedly outpaced new minting for a period as some users and protocols reassessed their exposure ([Unchained](https://unchainedcrypto.com/wrapped-bitcoin-wbtc-redemptions-vastly-outpaced-minting-since-bitgos-custodial-changes-announcement/)). Major DeFi protocols responded with their own governance debates. Newsroom coverage shows lending platforms such as Spark Protocol cautiously weighing the reactivation of WBTC as collateral, and Maker-aligned markets re-examining risk parameters — reminders that WBTC's collateral status across DeFi is not static but is continually re-litigated through protocol governance.

## Supply, Reach, and Market Position

WBTC remains the largest wrapped-bitcoin token by supply, with a circulating supply on the order of 150,000+ BTC — claims on roughly 0.8% of the total bitcoin supply ([WEEX](https://www.weex.com/wiki/article/what-is-wrapped-bitcoin-wbtc-a-beginners-guide-in-2026-e0xragjorh5ulde2ad1w42wh)). It has expanded beyond Ethereum to Layer 2 networks including Arbitrum, Optimism, and Base, as well as other chains such as Solana, Tron, and Polygon.

That cross-chain reach continues to grow through liquidity and routing infrastructure. Recent newsroom items note WBTC being added to cross-chain liquidity layers — for example, WBTC on Optimism going live on the SODAX SDK alongside Optimism's OP token, making the asset tradable from across more than 18 integrated networks, and consumer apps such as Pump.fun adding WBTC support. Each integration deepens WBTC's role as a base settlement asset for bitcoin liquidity in DeFi, while also raising questions about routing and bridge risk that observers have flagged.

## Competition: cbBTC, tBTC, and the "Neutrality" Debate

WBTC's dominance has narrowed as alternatives have scaled, each making a different custody pitch:

- **cbBTC** is Coinbase's wrapped bitcoin, launched in September 2024 with reserves held in Coinbase Custody. It grew quickly across Ethereum, Base, Arbitrum, and Solana, reaching a multi-billion-dollar market capitalization and an estimated quarter of the wrapped-BTC market ([Eco](https://eco.com/support/en/articles/15220191-wrapped-bitcoin-2026-cirbtc-wbtc-cbbtc-tbtc-fbtc-compared)). Its appeal is the brand trust and regulatory posture of a large U.S.-listed exchange.
- **tBTC**, from Threshold Network, uses threshold ECDSA cryptography to distribute custody across a network of signers, positioning itself as more decentralized than single-custodian models.
- **BTC.b**, FBTC, and newer institutional entrants compete on credible neutrality, fee structure, and ecosystem fit.

As newsroom commentary on "neutral Bitcoin infrastructure" argues, the most useful comparison among wrapped-BTC products is not a feature table of fees but the underlying custody model and trust assumptions. A token backed by a single corporate custodian carries different counterparty risk than one secured by a signer network or a more geographically and institutionally distributed key arrangement. For users, the practical questions are: who holds the bitcoin, how is redemption guaranteed, and how concentrated is control of the smart contract?

## Risks and Recent Incidents

Wrapped bitcoin concentrates several categories of risk that holders should weigh:

**Custodial and counterparty risk.** Because reserves sit with custodians, WBTC's value depends on those institutions remaining solvent, honest, and operational. A failure or seizure at the custody layer could break the 1:1 peg. This is the core distinction from holding native BTC in self-custody.

**Smart-contract and protocol risk.** Once WBTC enters DeFi, it inherits the risk of the protocols it touches. Recent coverage underscores how wrapped-BTC assets become targets and instruments in exploits. In one reported incident, an attacker who minted bitcoin-pegged tokens on the Monad network used them to max-borrow WBTC on a lending market, then bridged the WBTC to Ethereum and swapped it for ETH. Separately, a hacked decentralized-exchange solver lost a basket of assets including WBTC, and a phishing drainer reportedly took WBTC from a victim shortly after an Aave withdrawal via a malicious approval signature. None of these were flaws in WBTC's own contract, but they illustrate that wrapped BTC moves through — and can be drained from — the broader DeFi stack.

**Liquidity and de-peg risk.** During market stress, the price of a wrapped token can briefly diverge from the asset it represents if redemption is slow or liquidity thin. Cross-chain bridges add another surface, since bridged WBTC depends on the security of each bridge it traverses.

**Concentration risk.** Large holders can move WBTC in size. Newsroom on-chain coverage repeatedly highlights whales rotating tens of millions of dollars between ETH and WBTC — timing crashes, selling before drawdowns, and buying back lower — alongside accounts linked to large miners accumulating ETH and WBTC. Such flows can amplify volatility in WBTC-dependent markets and in the collateral pools that hold it.

## Where WBTC Fits Alongside Stablecoins and ETH

In practice, WBTC sits next to assets like ETH and stablecoins such as USDC as a core building block of DeFi collateral. On lending platforms, WBTC is commonly supplied as collateral to borrow stablecoins or ETH, and yield programs frequently pair it with WETH or USDC in incentive pools — recent examples include supply-mining campaigns rewarding WBTC deposits and vault products bundling USDC, WETH, and WBTC. Yield Basis, for instance, raised caps in its WBTC, cbBTC, and tBTC markets and filled them within minutes, signaling continued appetite for productive bitcoin collateral. WBTC thus functions less as a speculative token in its own right and more as bitcoin's passport into the dollar- and ETH-denominated machinery of on-chain finance.

## Outlook

WBTC's near-term trajectory hinges on two questions: whether its evolving multi-custodian structure restores confidence after the redemption wobble around the custody changes, and whether it can defend share against cbBTC and non-custodial models that pitch stronger neutrality or brand trust. The wrapped-bitcoin category itself looks set to expand as more issuers enter and compress fees, while bitcoin's still-small DeFi footprint leaves substantial room for growth. For users, the durable lesson is that all wrapped BTC trades self-custody for utility — and the right choice depends less on which token is largest than on which custody model and protocol exposure best matches one's own risk tolerance.
