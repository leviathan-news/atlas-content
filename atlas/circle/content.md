Founded in 2013, Circle Internet Group is the payments technology company behind USDC, the world's second-largest stablecoin by market capitalization and the dominant regulated dollar-denominated token on institutional and compliant trading venues.

Where Tether operates with minimal public disclosure and an offshore legal structure, Circle has pursued the opposite strategy: U.S. regulatory approvals, full reserve attestations, and a June 2025 NYSE listing under the ticker **CRCL**. That strategic divergence now underpins Circle's pitch as the stablecoin issuer that regulated finance can trust — and shapes nearly every product decision the company makes.

## Origins and the Stablecoin Bet

Jeremy Allaire and Sean Neville co-founded Circle in Boston in 2013 as a consumer bitcoin wallet. Over several years and pivots, the company exited consumer crypto retail entirely and concentrated on the infrastructure layer: dollar-denominated digital money that moves on public blockchains.

USDC launched in 2018 as a joint venture with Coinbase under the Centre Consortium umbrella. Circle later acquired full ownership of USDC in 2023 when Centre was wound down, giving it sole control over issuance, reserve management, and compliance policy. The partnership with Coinbase remains commercially close — Coinbase earns a revenue share on USDC held on its platform and is a primary distribution channel — but Circle now makes all product decisions unilaterally.

## USDC: The Core Product

USDC is a fiat-backed stablecoin: every token in circulation is backed 1:1 by cash and short-duration U.S. Treasury securities held in segregated reserve accounts. Grant Thornton and Deloitte conduct monthly attestations of those reserves, a transparency practice Tether's USDT does not match to the same standard.

From roughly $33 billion in early 2024, USDC's circulating supply grew to approximately $60 billion by early 2026 — an increase of about 80% in two years — driven by renewed demand from exchanges, DeFi protocols, and cross-border payment providers. Despite that growth, USDC remains well behind Tether's USDT, which held approximately $140 billion in circulation over the same period. The gap reflects Tether's deep entrenchment in offshore trading pairs and emerging-market dollar substitution use cases, where regulatory compliance matters less than raw liquidity depth.

Where USDC consistently leads is in regulated venues, U.S.-licensed exchanges, and institutional on-chain finance. That positioning has made it the reference stablecoin for DeFi protocols aiming at institutional capital, and the token of choice for cross-border B2B payments on modern fintech rails.

Circle also issues **EURC**, a euro-denominated equivalent, and **USYC**, a tokenized money market fund product, though neither has reached the scale or ecosystem penetration of USDC.

## How Circle Makes Money

Circle's revenue model is straightforward: it earns yield on the short-term Treasuries and cash equivalents backing USDC in reserve, then shares a portion of that income with distribution partners — most notably Coinbase. In 2024, Circle reported approximately $1.68 billion in revenue and reserve income, with net income of $156 million.

That model creates a structural sensitivity to interest rates. When the Federal Reserve cuts rates, the yield on reserves compresses, squeezing margins without any offsetting reduction in operating costs. Circle's IPO prospectus acknowledged this explicitly, and analysts have flagged it as a meaningful risk as the rate cycle turns. Circle's strategic response is to diversify revenue by building payment infrastructure, developer tooling, and now its own blockchain — products that generate fee income independent of reserve yields.

## The Circle Payments Network

Circle operates the **Circle Payments Network (CPN)**, a set of APIs and protocol connections that lets banks, fintechs, and payment providers use USDC as the settlement layer for cross-border transfers. Participants like UQPAY have integrated CPN to power multi-market payouts and FX execution, replacing slow correspondent banking wires with on-chain settlement that clears in seconds rather than days.

The **Cross-Chain Transfer Protocol (CCTP)** is the technical mechanism that moves native USDC across blockchains — burning tokens on the source chain and minting them on the destination chain, rather than locking them in a bridge contract. CCTP has expanded to Stellar among other networks, broadening USDC's cross-chain reach while also exposing it to the security assumptions of those additional chains. Complementing CCTP, Circle's **Forwarding Service for Gateway** automates cross-chain USDC transfers for developers, handling destination-chain gas and minting coordination without requiring projects to manage multi-chain infrastructure manually.

USDC's position on Solana has grown particularly quickly in 2026, with Circle's activity on that network contributing to a sharp rise in Solana's stablecoin supply — a sign that the chain's throughput and low fees make it a preferred venue for high-frequency payment flows.

Mastercard has expanded stablecoin settlement capabilities to include USDC alongside competitors, adding another institutional endorsement to Circle's payment network narrative.

## Arc: Circle's Layer-1 Bet

The company's most ambitious infrastructure play is **Arc**, an EVM-compatible Layer-1 blockchain purpose-built for stablecoin-native finance. Unlike general-purpose chains, Arc uses USDC natively for gas fees, targets sub-second transaction finality, and is designed from the ground up for financial applications: payments, tokenized real-world assets, institutional DeFi, and FX settlement.

Circle describes Arc as the "economic operating system" for on-chain finance — a public settlement layer optimized for the workflows that matter in regulated markets. DeFi protocols Aave and Aerodrome have both committed to deploying on Arc, giving it immediate liquidity infrastructure at launch. In May 2026, Circle raised $222 million in an Arc token presale at a $3 billion valuation, with investors including BlackRock and Apollo — a significant institutional endorsement for what remains a pre-mainnet network.

Arc is still in public testnet as of mid-2026, with developer documentation, RPC access, and a testnet explorer live. Its debut signals that Circle intends to compete directly with Ethereum, Solana, and Coinbase's Base for the financial application layer, not merely supply stablecoin liquidity to those networks. Whether Arc can attract enough independent developer activity to justify that positioning — rather than serving as a captive chain for Circle's own products — is an open question.

Circle has also published a post-quantum security roadmap for both USDC and Arc, outlining cryptographic migration plans in anticipation of future quantum computing threats. That level of forward planning is consistent with Circle's broader pitch to institutional users for whom long-horizon infrastructure reliability matters.

## Developer Tools and AI Agent Infrastructure

Circle has expanded its developer platform to address the emerging category of AI agent payments. The **Circle Agent Stack** gives developers a framework for building autonomous agents that can hold USDC-funded wallets, discover services through an Agent Marketplace, pay for API access through Circle Gateway, and execute on-chain actions — all without requiring the agent to interact with traditional banking infrastructure.

This positions Circle at the intersection of AI and on-chain payments, a use case that is still nascent but has attracted significant developer attention. EarnOS, a startup building anti-AI-slop content tools, raised $6 million in a round that included Circle and Coinbase as investors — an example of Circle deploying capital to seed the ecosystem it wants to serve.

## cirBTC: Entering the Wrapped Bitcoin Market

In a notable product extension beyond dollar stablecoins, Circle launched **cirBTC** on Ethereum in 2026 — a 1:1 BTC-backed wrapped bitcoin token designed to bring bitcoin collateral into DeFi. The move puts Circle in direct competition with Coinbase, whose **cbBTC** product holds a substantial share of the wrapped bitcoin market.

Circle has positioned cirBTC as a more neutral, institutionally accessible alternative to Coinbase's offering, emphasizing that it is issued by an entity without its own exchange business and therefore without potential conflicts around custody and trading. Arc integration and multichain expansion are planned for cirBTC, suggesting Circle intends it to be a broader DeFi collateral asset rather than an Ethereum-only product.

## Compliance Architecture and Its Limits

Circle's regulatory-first positioning carries real operational consequences. USDC tokens can be frozen or blacklisted at the contract level — a power Circle exercises when compelled by legal process or law enforcement. In 2026, Circle froze approximately $12.6 million in USDC linked to privacy protocol Zama following a court order connected to the Overnight Finance lawsuit. The freeze swept an entire smart contract rather than individual addresses, trapping funds belonging to Zama Protocol users who were not parties to the underlying dispute — a form of collateral damage that drew sharp criticism from privacy advocates in the DeFi community.

Circle has submitted formal comment letters to U.S. regulators in support of anti-money-laundering frameworks, positioning itself as a cooperative actor in the regulatory process. That posture has helped it maintain banking relationships and exchange partnerships, but it also makes USDC a less suitable settlement asset for applications where censorship-resistance is a design requirement. Circle's compliance infrastructure is an asset for institutional use cases and a constraint for censorship-sensitive ones; builders need to understand which side of that line their application sits on.

Circle won Newsweek's 2026 AI Impact Award for best outcomes in financial services, reflecting its internal adoption of AI-assisted development workflows — a secondary signal of the company's orientation toward institutional legitimacy and recognition rather than its crypto-native roots.

## Competitive Position vs. Tether

The comparison to Tether defines how Circle is valued both as a business and as a stablecoin issuer. Tether's USDT is larger by nearly every volume metric and deeply embedded in offshore trading. Circle's USDC is smaller but more transparent, more compliant, and more accessible to regulated entities.

Pending U.S. stablecoin legislation — including frameworks that would require full reserve backing, public attestation, and licensing — could materially advantage Circle if enacted. Conversely, a permissive regulatory environment that validates Tether's approach would reduce Circle's compliance premium. The company has lobbied actively for stronger stablecoin rules, an unusual posture that reflects genuine belief that regulation expands its addressable market.

## Outlook

Circle enters the second half of 2026 executing on multiple fronts simultaneously: managing a public company's reporting obligations while shipping Arc testnet, expanding USDC supply across Solana and other networks, building out the Circle Payments Network for B2B cross-border use, and competing in the emerging wrapped bitcoin market with cirBTC.

The core risk remains interest rate sensitivity in the reserve model — a structural constraint that makes revenue diversification into fee-based products existential rather than optional. Arc's success or failure will likely define whether Circle is remembered as a stablecoin issuer that built durable infrastructure or one that over-expanded at the wrong moment in the cycle.

What is not in doubt is Circle's strategic clarity: it is betting that regulated, dollar-denominated, programmable money is the foundation of a future internet financial system, and that being the most trusted issuer of that money is a durable competitive advantage. The evidence so far — $60 billion in USDC circulation, a $3 billion Arc round, Mastercard and BlackRock as partners — suggests the bet has merit.

## Outlook

Regulatory tailwinds from U.S. stablecoin legislation, combined with Arc's mainnet launch and expanding CPN partnerships, give Circle multiple catalysts heading into 2027. Execution risk is real: Arc must attract independent developers, interest rate headwinds persist, and Tether's liquidity depth remains a formidable moat in trading-focused markets. Circle's differentiated position — regulated, publicly traded, audit-transparent — grows more valuable the further financial institutions move on-chain, and less valuable if crypto-native users remain the dominant settlement market.

---
