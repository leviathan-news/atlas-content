A tokenized money market fund (MMF) is a regulated fund holding short-term, high-quality assets—typically U.S. Treasury bills and overnight repurchase agreements—whose shares are issued and transferred as digital tokens on a blockchain rather than tracked solely on a transfer agent's ledger. The tokens represent legal ownership of fund shares, combining the yield and credit profile of a traditional cash-management vehicle with the programmability and near-instant settlement of onchain assets.

These products sit at the intersection of conventional asset management and the real-world asset (RWA) movement, and they have become one of the most visible ways that large financial institutions are putting regulated yield onchain.

## How the structure works

A traditional money market fund pools investor cash into a portfolio of short-duration instruments and aims to maintain a stable value while passing through interest. Tokenization does not change that underlying portfolio; it changes the *wrapper*. Instead of recording shares only in a fund administrator's books, a tokenized fund mints blockchain tokens that map one-to-one to shares. Ownership, transfers, and—in some designs—subscriptions and redemptions are recorded on a public or permissioned chain.

Most current offerings are *permissioned*: only wallets that have passed know-your-customer (KYC) and accreditation checks can hold the tokens, and transfers are restricted to a whitelist. This lets issuers satisfy securities law while still using public infrastructure. BNP Paribas, for example, tested tokenized shares of a French money market fund on the public Ethereum blockchain through its AssetFoundry platform under exactly this kind of permissioned, regulated framework.

The yield reaches holders in one of two ways: through a rebasing or accruing token whose balance or price grows over time, or through periodic distributions. Because the assets are short-dated Treasuries and repo, the funds are designed for capital preservation and liquidity rather than capital appreciation.

## Why it matters: collateral and "onchain cash"

The practical appeal is that a tokenized MMF share can move at the speed of a blockchain transaction while still earning a regulated yield. That makes these tokens attractive as *collateral* and as a yield-bearing alternative to idle stablecoins.

This collateral use case is driving much of the growth. Circle's USYC has become one of the largest tokenized money market funds, with reporting describing it surpassing $3 billion in assets under management and, in subsequent coverage, becoming the world's largest such fund—built to enable 24/7 creation and redemption against USDC via smart contracts for real-time collateral. The thesis is that trading desks, market makers, and DeFi protocols would rather hold an instrument that earns Treasury-bill yield and can be redeemed around the clock than park cash in a non-yielding token.

That collateral framing also explains the steady drumbeat of integrations. Uniform Labs' Multiliquid protocol, for instance, launched to offer instant swaps between tokenized money market funds and stablecoins, pitching itself as a fix for fragmented liquidity across these instruments. And Plume, together with Toku and WisdomTree, launched a payroll pilot letting eligible employees receive part of their wages in shares of WisdomTree's tokenized fund WTGXX—an early test of tokenized cash inside an everyday financial workflow rather than just a trading venue.

## The institutional wave

What separates the current cycle from earlier RWA experiments is who is participating. The largest names in traditional finance are now issuing these products directly.

J.P. Morgan, a bank whose asset-management arm oversees roughly $4 trillion, moved into the category in two steps. It first launched MONY—the "My OnChain Net Yield Fund"—a private vehicle on Ethereum seeded with about $100 million and opened to qualified investors. It followed in May with JLTXX, the JPMorgan OnChain Liquidity-Token Money Market Fund, which trades under that ticker on Ethereum and is designed to invest exclusively in U.S. Treasury securities and overnight repurchase agreements fully collateralized by Treasuries. JPMorgan structured JLTXX specifically to meet reserve requirements for stablecoin issuers, reflecting how the regulated cash layer of crypto is increasingly being built by incumbent banks. The move is consistent with chief executive Jamie Dimon's April shareholder letter, which named blockchain and stablecoins as technologies the bank intends to engage with even amid his long-standing skepticism of crypto more broadly.

BlackRock, the world's largest asset manager with roughly $14 trillion under management, has pushed in the same direction. After its BUIDL tokenized fund became a flagship product for the sector, the firm filed with the SEC in May to launch additional tokenized funds, including a blockchain-native money market vehicle structured to hold stablecoin reserves. Fidelity has likewise developed a tokenized money market offering.

A meaningful validation arrived from the ratings agencies. Moody's awarded its top AAA rating to tokenized money market funds—covering products from issuers including Fidelity and BlackRock—a signal that the agency views the credit quality and liquidity of these onchain instruments as comparable to their traditional counterparts. Coverage tying that milestone to sector data placed the tokenized Treasury segment at roughly $15 billion in assets under management. WisdomTree, Franklin Templeton (an early mover with its onchain U.S. Government Money Fund), and Circle round out a field that now spans both crypto-native firms and legacy managers.

## Stablecoins, the GENIUS Act, and reserves

A key tailwind is regulation of stablecoins. In the United States, the GENIUS Act established a federal framework for payment stablecoins, including requirements that issuers back their tokens with high-quality, liquid reserves. Tokenized money market funds are being explicitly engineered as eligible reserve assets: J.P. Morgan structured JLTXX to satisfy those reserve requirements, and BlackRock's planned vehicle is likewise aimed at holding stablecoin reserves.

The logic is that a stablecoin issuer must hold reserves in safe, liquid instruments anyway. A tokenized Treasury fund lets the issuer hold those reserves in a form that is itself onchain, auditable in near real time, and transferable—potentially tightening the operational loop between the reserve asset and the stablecoin it backs. This has also drawn scrutiny: regulators are examining *yield-bearing* stablecoin models, where the line between a payment token and an investment product becomes blurry, which is part of why tokenized MMFs (clearly structured as securities) are emerging as the compliant way to deliver onchain yield.

To define the adjacent terms: a *stablecoin* such as USDC is a token pegged to a fiat currency and generally does not pass yield to ordinary holders; a *tokenized money market fund* is a registered security that does pay yield and is sold to qualified or accredited investors under securities law. The two are complementary—stablecoins for payments and settlement, tokenized funds for the reserve and collateral layer beneath them.

## The role of Ethereum and public chains

Most of the high-profile launches have chosen Ethereum as the issuance venue, including JPMorgan's MONY and JLTXX and BNP Paribas's pilot. Ethereum's deep tooling, established custody and compliance integrations, and large base of institutional infrastructure make it the default settlement layer for regulated tokenization, even when access to the tokens themselves is restricted to permissioned wallets. Other funds operate across multiple chains to reach different liquidity pools, but the pattern of "public chain, permissioned access" has become the dominant compliance model.

## Risks and open questions

The category is young and carries real caveats. Liquidity is one: tokenization promises 24/7 transfer, but underlying Treasury and repo markets do not trade around the clock, so redemption mechanics depend on the issuer's design and on intermediaries. Uniform Labs framed a multi-billion-dollar liquidity gap as the core problem its protocol exists to solve, underscoring that secondary markets for these tokens remain thin.

Smart-contract and custody risk add a layer not present in conventional funds, and the legal enforceability of token ownership relative to the official share register varies by jurisdiction and structure. Regulatory treatment is still settling: South Korea's Financial Services Commission planned to release detailed tokenized-securities rules in July covering tokenized stocks, bonds and money market funds, ahead of a fuller framework taking effect in February 2027—an example of how the rulebook is being written in real time across major markets.

There is also concentration risk. A small number of large issuers and a handful of underlying custodians and chains account for most of the assets, so the sector's resilience has not yet been tested through a serious market or liquidity stress.

## Outlook

Tokenized money market funds have moved from proof-of-concept to a multibillion-dollar segment in a short span, propelled by AAA ratings, the entrance of the world's largest asset managers and banks, and stablecoin reserve rules that give the products a clear institutional buyer. The near-term trajectory will likely be defined by three forces: regulatory clarity in the U.S. and Asia, the maturation of secondary-market liquidity and interoperability between funds and stablecoins, and the extent to which these tokens become standard collateral across both DeFi and traditional trading. If those pieces fall into place, tokenized MMFs could become the default "onchain cash" layer; if liquidity or regulation disappoints, growth may stay concentrated among a few institutional issuers. Either way, the building blocks are now being laid by some of the largest balance sheets in finance.
