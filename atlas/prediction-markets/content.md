Prediction markets are exchanges where participants buy and sell contracts whose payouts are tied to the outcome of future events — functioning as a real-money mechanism for aggregating dispersed information into probabilistic forecasts.

---

## How They Work

At their core, prediction markets operate on a binary or scalar settlement model. A contract might ask: "Will the S&P 500 close above 5,500 on July 31?" Traders buy "Yes" or "No" shares, each priced between $0 and $1. If the market resolves in favor of "Yes," Yes-share holders receive $1; No-share holders receive nothing. The price at any moment — say, $0.63 for Yes — reflects the crowd's aggregate estimate that the event has a 63% probability of occurring.

This mechanism dates to the Iowa Electronic Markets in the early 1990s and has a robust academic literature supporting its forecasting accuracy relative to polls, expert panels, and traditional models. The key insight is that prices incorporate private information: traders who know more than the consensus have a financial incentive to bet, and their activity moves prices toward better-calibrated probabilities.

Modern platforms extend the model beyond binary events. Scalar markets resolve on a numerical range (e.g., exact vote share in an election); order-book markets allow limit orders; automated market makers (AMMs) use algorithmic pricing curves. Crypto-native platforms use stablecoins or protocol tokens for collateral and smart contracts for settlement, removing the need for a central custodian to hold funds.

## From Niche to Mainstream: The Volume Inflection Point

For most of their existence, prediction markets were a fringe curiosity — hamstrung by low liquidity, regulatory uncertainty, and limited awareness. The 2024 U.S. election cycle changed that calculus. Polymarket, a decentralized platform built on Polygon, processed billions in volume on presidential election contracts, drawing mainstream press coverage and demonstrating that retail and institutional traders would engage with the format at scale.

According to data cited by Andreessen Horowitz, prediction markets hit $10 billion in weekly volume at their recent peak — a milestone that would have been implausible five years earlier. That growth has pulled in an entirely new class of participants. Charles Schwab announced plans to offer yes/no event-based options on the S&P 500 in partnership with Cboe, joining Coinbase and Robinhood, which had already moved into the sector. The entry of a legacy brokerage managing trillions in client assets signals that prediction markets are no longer a crypto-only phenomenon — they are becoming a recognized financial instrument class.

Trading Technologies, which provides professional-grade execution infrastructure to institutional desks, integrated Kalshi — a federally regulated prediction market exchange — into its platform, giving prop traders and hedge funds direct access through tools they already use.

## The Regulatory Landscape

The legal architecture governing prediction markets in the United States is fragmented and actively contested, and that fragmentation is the single largest constraint on the sector's growth.

Kalshi, founded in 2021, took the path of operating as a designated contract market (DCM) regulated by the Commodity Futures Trading Commission (CFTC). That federal imprimatur gives it legitimacy but also subjects it to CFTC oversight — an agency that has historically been skeptical of event contracts on political and sporting outcomes. The CFTC under its prior leadership attempted to block Kalshi from listing contracts on U.S. congressional election outcomes; Kalshi sued and won, with the D.C. Circuit ruling in its favor in 2024.

The regulatory picture has since shifted. SEC Chair Paul Atkins has publicly backed CFTC Chairman Brian Quintenz amid concerns that the CFTC lacks the resources to oversee both the booming prediction markets sector and incoming crypto regulation responsibilities. That resource tension is real: the CFTC's budget has not scaled commensurate with the asset classes now under its jurisdiction.

The offshore model, used by platforms like Polymarket, sidesteps domestic regulatory requirements by barring U.S. users at the account level while remaining accessible via wallets. Former CFTC Commissioner Dan Berkovitz — who had been a vocal critic of permissionless DeFi trading — has flagged the legal ambiguity around these structures, describing a seascape of regulatory risk that operators navigate at their own peril. A ruling in the Sixth Circuit found that sports prediction markets do not fall under CFTC jurisdiction, adding another layer of jurisdictional uncertainty and creating conflicting signals across circuits.

## The Sports Betting Fight

The most politically charged regulatory battleground involves sports prediction markets. Kalshi began listing contracts on NFL and other sporting outcomes, which established gaming operators — casinos, tribal gaming authorities, and state lottery commissions — argue are functionally equivalent to sports bets and should be subject to state gambling laws, not federal commodities law.

Gaming industry coalitions have lobbied Congress aggressively to include a prohibition on sports prediction markets in the CLARITY Act, the pending legislation aimed at creating a comprehensive federal crypto framework. They are joined by unions and advocacy groups who argue the CFTC route is regulatory arbitrage that undermines the consumer protections built into state gaming regimes. A bipartisan tension has emerged: the Trump administration has signaled general support for expanded prediction market access, creating an unusual alignment with financial innovation advocates, while some red states — including Kentucky — have moved independently to restrict the platforms, potentially placing themselves at odds with federal policy direction.

Meanwhile, a Republican lawmaker introduced a proposal to ban insider trading in prediction markets, though the initial draft conspicuously excluded White House officials from its scope — an omission that drew criticism given public speculation about information asymmetries around policy announcements.

## The Oracle Problem and Infrastructure

For crypto-native prediction markets, the mechanism for settling contracts — determining what the correct outcome was — is as important as the trading infrastructure itself. This is the oracle problem: smart contracts are deterministic and isolated from external data, so they require a trusted feed to report real-world outcomes.

Poor oracle design has produced some of the sector's most damaging incidents, including markets that resolved on contested or ambiguous data, or where the resolution mechanism was manipulated by large holders. The issue mirrors the oracle exploits that plagued DeFi protocols in 2020, where price feeds were subject to flash-loan manipulation. Chainlink, which addressed much of that earlier wave through decentralized price feeds, has positioned itself as a resolution infrastructure provider for prediction markets — powering official FIFA World Cup 2026 contracts on Predictstreet, among other deployments.

The oracle challenge is closely tied to the question of institutional adoption. Institutional counterparties require deterministic, auditable, and legally defensible settlement — not a community vote on a Discord server. Building that infrastructure layer, including dispute resolution mechanisms, regulated custodians, and audit trails, is the prerequisite for hedge funds and asset managers to participate at meaningful size.

PremiumBlock's launch of a non-custodial risk hub that supports user-created prediction markets alongside perpetuals and other derivatives illustrates where the builder community is pushing: toward permissionless market creation with credible, on-chain settlement, rather than platform-gated contract listings.

## The AI Angle

Artificial intelligence intersects with prediction markets in two distinct ways. First, AI agents are emerging as market participants: language models and autonomous agents can monitor news flows, update probability estimates, and place orders faster than human traders. Coinbase has highlighted agent-driven trading as a use case for its prediction market and derivatives offerings, where AI advisors can act on behalf of users. The efficiency implications cut both ways — AI participants may improve price discovery, but they also raise questions about whether retail traders can compete in markets increasingly dominated by algorithmic speed.

Second, AI-generated content and synthetic media create new resolution challenges. A prediction market on whether a public figure said something specific becomes harder to settle when deepfakes are plausible. Robust oracle design has to account for epistemically contested events in a way that earlier market designs never needed to.

## Who Is Competing and How

The competitive landscape has stratified into three rough tiers:

**Regulated domestic platforms**: Kalshi operates under a CFTC license, which grants it access to U.S. customers and the ability to connect to traditional brokerage infrastructure like Trading Technologies. Cboe, partnering with Schwab, is exploring a similar regulated path for index event contracts.

**Brokerage-integrated offerings**: Coinbase, Robinhood, and now Schwab are integrating prediction market-style products into existing retail brokerage apps, lowering friction for mainstream users who have no interest in self-custodying USDC on Polygon. The format being tested — yes/no options on index levels — is structurally similar to binary options, a product class that regulators banned in many retail contexts after widespread fraud in the 2010s. How regulators distinguish these offerings from legacy binary options will be a defining question.

**Crypto-native and permissionless platforms**: Polymarket, built on Polygon, and newer entrants like PremiumBlock prioritize non-custodial design and permissionless market creation. They accept the trade-off of U.S. user restrictions in exchange for minimal regulatory overhead and global accessibility. Their volume has historically spiked around high-salience events — elections, major sporting events, macro announcements — suggesting deep sensitivity to news cycles.

The art auction house Sotheby's opened prediction markets on hammer prices for specific lots in June 2025, indicating the format is migrating into cultural and entertainment verticals beyond finance and politics.

## Outlook

Prediction markets appear to have passed an inflection point where volume, institutional interest, and regulatory attention have all arrived simultaneously — a combination that historically precedes either rapid legitimation or significant restriction. The CLARITY Act negotiations will likely set the terms for sports-adjacent contracts; the CFTC's resource constraints will shape how aggressively it can police or enable the broader market. The oracle infrastructure buildout is a near-term bottleneck that platforms like Chainlink are actively trying to solve, and institutional adoption will track closely behind credible settlement mechanisms. Whether the sector consolidates around a small number of regulated venues or fragments across dozens of permissionless protocols will depend on how those regulatory and infrastructure questions resolve over the next two to three years.

## Outlook

The prediction market sector is at a crossroads between mainstream financial integration and unresolved regulatory conflict. Charles Schwab's entry signals legitimacy; the ongoing CLARITY Act fight signals that legitimacy is still contested terrain. For crypto-native participants, the priority is infrastructure credibility — oracle reliability, dispute resolution, and audit trails — that can satisfy institutional counterparties. The $10 billion weekly volume milestone is a proof of concept; whether it becomes a durable asset class depends on whether the legal and technical foundations can bear the weight of that interest.

---
