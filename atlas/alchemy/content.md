"Alchemy" refers to two unrelated crypto-industry companies that share a name: Alchemy, a U.S.-based blockchain developer-infrastructure platform, and Alchemy Pay (token: $ACH), a Singapore-rooted fiat-to-crypto payments network. Confusing the two is common, so this explainer treats each separately before mapping where their stories currently sit.

The naming overlap matters because both are active in 2026 news cycles and both touch payments, yet they are different businesses with different products, owners, and regulatory footprints. The sections below define each entity, explain its core technology, and summarize recent developments — including Alchemy's move into AI-agent payments with Visa and Alchemy Pay's expanding U.S. money-transmitter licensing.

## Alchemy the developer platform: what it is

Alchemy is a blockchain infrastructure company that provides the "plumbing" developers use to build applications on public chains — primarily node access via RPC (Remote Procedure Call) endpoints, plus higher-level APIs for tokens, transactions, webhooks, and wallets. In practice, an RPC endpoint is the connection a wallet or app uses to read blockchain state and submit transactions; running reliable nodes is operationally hard, so many teams outsource it to providers like Alchemy.

The company was founded by Stanford graduates Nikil Viswanathan (CEO) and Joe Lau, and raised a $200 million round in February 2022 that valued it at $10.2 billion, led by Lightspeed and Silver Lake — capping a funding run that earlier included a $250 million Series C led by Andreessen Horowitz ([CNBC](https://www.cnbc.com/2022/02/08/crypto-infrastructure-start-up-alchemy-tops-10-billion-valuation.html); [Alchemy](https://www.alchemy.com/blog/alchemy-equity-investment)). The company markets itself as the largest blockchain developer platform and says it has powered more than $4 trillion in onchain transaction value, a figure that appears throughout its 2026 partnership announcements ([Injective](https://injective.com/blog/alchemy-developer-platform)).

Its product surface has broadened beyond raw node access to include embedded smart wallets, gasless ("account abstraction") transactions, rollups-as-a-service, and token and portfolio APIs — tooling aimed at lowering the barrier to shipping consumer crypto apps.

## Alchemy's multi-chain and infrastructure expansion

Through 2026, Alchemy pursued a strategy of adding support for new chains and ecosystems so that developers can stay within familiar tooling while building across networks. Recent integrations include:

- **Injective**: Alchemy launched RPC infrastructure on the finance-focused layer-1, citing 99.99% uptime and its $4T transaction track record as selling points for onchain-finance builders ([Injective](https://injective.com/blog/alchemy-developer-platform); [BlockchainNews](https://blockchain.news/news/alchemy-launches-on-injective)).
- **Stellar**: Stellar became a first-class chain on Alchemy, targeting builders of real-world-asset (RWA) platforms and cross-border payment apps ([Alchemy](https://www.alchemy.com/blog/stellar-support-is-live-on-alchemy)).
- **Canton Network**: Alchemy joined a validator set positioned around tokenized institutional assets.
- **Solana and others**: Alchemy committed free developer credits to bootstrap building in specific ecosystems, a customer-acquisition tactic common among infrastructure vendors.
- **OVHcloud**: A partnership with the European cloud provider extended Web3 developer tooling on Arbitrum, signaling enterprise and data-sovereignty positioning.

The throughline is distribution: an infrastructure provider grows by being available wherever developers want to build, and by being the default RPC and tooling layer rather than one of several. These are incremental updates rather than single transformative launches, but together they widen Alchemy's addressable surface.

## Alchemy, AI agents, and Visa: AgentCard

The most consequential recent development for Alchemy is its expansion into payments for AI agents — software programs that can act autonomously on a user's behalf. In June 2026, Alchemy introduced **AgentCard**, described as a combined identity and payment platform for AI agents, built on **Visa Intelligent Commerce**, Visa's framework for letting authorized agents transact on its network ([CoinDesk](https://www.coindesk.com/business/2026/06/18/alchemy-s-ai-driven-identity-and-payment-service-gains-access-to-visa-network); [The Block](https://www.theblock.co/amp/post/405224/alchemy-unveils-visa-powered-virtual-payment-card-for-ai-agents)).

The pitch is that a developer can provision, via a single API in under a minute, everything an agent needs to operate in the real world: a Visa payment token, a dedicated email address, a phone number, and a cryptocurrency wallet. Once equipped, an agent built on models from providers such as OpenAI or Anthropic can book travel, order groceries, or renew subscriptions without a human touching a checkout screen ([PYMNTS](https://www.pymnts.com/partnerships/2026/alchemy-teams-with-visa-ai-agent-payment-stack/)).

Several design points are worth defining for a crypto audience:

- **Tokenized card credentials**: Rather than handing an agent a raw card number, AgentCard uses Visa-issued tokens. Tokenization replaces sensitive card data with a substitute value, so card rewards, credit lines, and existing benefits are preserved while limiting exposure ([CoinDesk](https://www.coindesk.com/business/2026/06/18/alchemy-s-ai-driven-identity-and-payment-service-gains-access-to-visa-network)).
- **Spending controls**: The platform supports spending limits, budget rules, and payment controls so a user or business can constrain what an agent may buy and how much it may spend — a guardrail layer that is central to agentic-commerce risk management.
- **Multi-rail support**: AgentCard is positioned to support emerging agent payment protocols, including crypto settlement where merchants accept it, alongside traditional card rails.

Alchemy has also referenced **AgentPay**, an effort to bridge payment rails from Coinbase, Stripe, Visa, and Circle into a single merchant integration. The strategic logic is that as autonomous agents proliferate, the scarce resource becomes a trusted way to give them identity and spending authority with auditable limits — a problem that sits at the intersection of payments, identity, and crypto wallets. Notably, Pantera Capital has warned that AI agents and generative models are straining legacy internet verification systems, naming Alchemy among the firms working on agent identity infrastructure — useful context, though such investor commentary is promotional in nature and should be read accordingly.

For readers, the key caveat is maturity: agentic commerce is early, and a launch announcement establishes capability and intent, not proven scale, fraud performance, or merchant adoption. Those will be measurable only over subsequent quarters.

## Alchemy Pay: a separate payments company

Alchemy Pay ($ACH) is a distinct company and should not be conflated with the developer platform above. It operates a fiat-to-crypto payment gateway — "on-ramp" and "off-ramp" rails that let users buy crypto with local currency and let merchants accept crypto settled in fiat. Its native token, ACH, trades on major exchanges, and its public messaging centers on regulatory compliance and localized payment coverage.

Recent Alchemy Pay developments fall into two buckets:

**Regulatory licensing in the United States.** Alchemy Pay has been steadily accumulating state money-transmitter and currency-transmitter licenses. It secured a Rhode Island currency transmitter license and, in June 2026, a Maine money transmitter license — bringing its U.S. state coverage to 17 states by mid-2026, per the company and trade press ([Blockchain Reporter](https://blockchainreporter.net/alchemy-pay-receives-maine-money-transmitter-license-expands-regulated-operations-to-17-us-states/); [Crypto Economy](https://crypto-economy.com/alchemy-pay-secures-maine-money-license/)). A money transmitter license is a state-level authorization required to move money or monetary value on behalf of others; accumulating them is the slow, jurisdiction-by-jurisdiction path to compliant U.S. operation, since the U.S. lacks a single federal license for this activity. (Newsroom coverage citing "16 states" reflects an earlier point in the same trajectory; the count rises with each approval.)

**Localized on-ramp and stablecoin expansion.** Alchemy Pay broadened its Malaysian on-ramp by adding GrabPay, Touch 'n Go eWallet, and Boost, letting users buy crypto with Malaysian Ringgit through popular local e-wallets. It also integrated the USDT0 stablecoin on Conflux Network and has built out "Alchemy Chain," which it describes as infrastructure for a global, dual-compliant stablecoin payment network with a mainnet now live. These moves emphasize stablecoin settlement and emerging-market payment access rather than developer tooling.

The two Alchemys do converge thematically — both ultimately touch the future of payments — but they are independent in ownership, products, and tokens (Alchemy the developer platform is a venture-backed private company with no public token; Alchemy Pay has the tradable ACH token).

## A note on unrelated "Alchemy" usage

The word also appears as branding unrelated to either company. For example, ETH treasury firm Bitmine has described nearing an "Alchemy of 5%" target — a phrase for its goal of holding roughly 5% of circulating ether — while its chairman characterized a market selloff as "superficial." This is a marketing metaphor, not a reference to Alchemy or Alchemy Pay, and is worth flagging precisely because the shared word invites confusion in headlines.

## How to tell them apart

For readers and editors, a few quick heuristics:

- **Mentions of RPC, node infrastructure, developer credits, multi-chain launches (Injective, Stellar, Solana), AgentCard, AgentPay, or Visa Intelligent Commerce** → the developer platform, Alchemy.
- **Mentions of $ACH, money transmitter licenses, fiat on-ramps, local e-wallets, or Alchemy Chain** → Alchemy Pay.
- **A tradable token** is present only for Alchemy Pay; the developer platform is privately held equity.

## Outlook

Both companies are pushing in directions that align with broader 2026 themes — the merging of AI and payments, and the steady regulatory formalization of crypto rails. For Alchemy the developer platform, AgentCard and the Visa relationship represent a bet that autonomous AI agents will need trusted identity and spending infrastructure, and that the firm's wallet and API tooling positions it to supply that layer; the open questions are adoption, fraud and dispute handling, and how agentic-commerce standards settle. For Alchemy Pay, the trajectory is more conventional: license-by-license U.S. expansion, localized on-ramps, and stablecoin settlement, where execution and sustained compliance — not novelty — will determine durability. Readers should continue to treat the two as separate entities and weigh each announcement against measurable usage rather than launch-day framing.
