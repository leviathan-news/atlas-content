# Crypto Infrastructure: The Rails Behind Onchain Finance

In crypto, *infrastructure* refers to the technical, legal, and operational rails that let digital assets, stablecoins, and AI agents safely move, settle, and interact across public and private networks. It is the hidden stack beneath exchanges, wallets, payments apps, and onchain markets that turns blockchains from experiments into real financial and data systems.

## What “Infrastructure” Means In Crypto

In traditional technology, infrastructure usually means servers, databases, and networks; in traditional finance, it evokes clearing houses, custodians, and payment networks. In crypto, those meanings converge. Infrastructure is both the base blockchain protocols and the surrounding services that make them usable for consumers, institutions, and increasingly, machine agents. It includes settlement layers like Ethereum and Avalanche, custody platforms that hold assets on behalf of institutions, data availability and storage networks, compliance and analytics systems, stablecoin payment rails, and the operational tooling that keeps all of this online.

Crucially, infrastructure sits below applications in the stack. Trading venues, lending protocols, NFT marketplaces, and AI-agent wallets are what users see. Underneath them are networks that timestamp and order transactions, systems that keep private keys secure, indexers that translate raw blockchain state into human-readable data, and messaging and identity layers that coordinate access. Without that shared backbone, every new product would need to rebuild its own bespoke rails for custody, settlement, compliance, and connectivity.

This distinction matters because infrastructure choices are durable and path-dependent. Once a bank integrates a settlement chain, a payment provider chooses a stablecoin framework, or an AI platform adopts a data layer, switching costs are high. That is why debates about whether permissionless networks will outcompete corporate chains, or how much transparency stablecoins must provide, are not abstract ideology; they are arguments about which infrastructure will become the default rails for future markets. In the same way that the internet eventually converged on open protocols like TCP/IP and Linux, many in crypto argue that credibly neutral, open infrastructure will win over time.

From a markets perspective, infrastructure also shapes what is possible onchain. The emerging vision of “Internet Capital Markets,” where asset issuance, trading, and settlement all occur on a single public ledger, depends on scalable, composable infrastructure that can support everything from tokenized treasuries to AI-driven market makers. For stablecoins, infrastructure determines whether risk teams can monitor reserves and flows in real time, rather than relying on occasional PDFs. And for AI, infrastructure decides whether models and agents operate on open, auditable rails or remain locked inside proprietary platforms.

## The Settlement Layer: Public Chains As Financial Infrastructure

At the base of the crypto stack are settlement layers: blockchains that provide a shared ledger where transactions are ordered, finalized, and made tamper-evident. These networks are increasingly framed not as payment apps but as **global settlement systems**. Ethereum advocates, for example, argue that the network’s endgame is to become the world’s largest programmable settlement layer, securing identity, assets, AI coordination, and more, rather than competing directly with consumer payment front-ends. In this view, Ethereum’s value comes from its role as a credibly neutral court of record for higher-level applications, much as the internet’s core protocols quietly underpin web and mobile experiences.

Other networks have embraced similar positioning. Avalanche’s research emphasizes its design as a high-throughput, customizable network where subnets can host specialized financial or gaming applications, anchored by a common set of validation and security assumptions. Subnets can be tailored to specific regulatory or performance requirements, yet still interoperate with the broader Avalanche ecosystem, making the base protocol a form of shared infrastructure for diverse use cases. Solana proponents, meanwhile, increasingly describe the network as financial infrastructure for issuing and trading assets, from equities and treasuries to money market funds and private credit, rather than merely a speculative smart-contract chain. That framing reflects a shift from “coins and tokens” to “markets and instruments” built on programmable rails.

The emerging concept of Internet Capital Markets (ICM) makes this explicit. In that framework, public blockchains act as single venues where issuance, secondary trading, and settlement can occur with instant or near-instant finality, transparently and programmatically. Instead of fragmented, jurisdiction-specific back offices, institutions in Asia and elsewhere can plug into onchain liquidity and compliance infrastructure, using automated market makers and stablecoin rails as core building blocks. The settlement layer is not an app; it is the base infrastructure that everything else composes upon.

### Permissionless Versus Permissioned Settlement

Not all settlement infrastructure is built the same way. A central ideological and practical divide runs between permissionless networks such as Ethereum, Avalanche, and Solana, and permissioned or consortium chains designed primarily for regulated institutions. Proponents of permissionless infrastructure argue that over long horizons, credibly neutral systems outcompete proprietary networks and corporate blockchains, echoing how open-source Linux eventually dominated server operating systems. Their claim is that innovation, interoperability, and censorship resistance are structurally stronger on public chains, making them better long-term infrastructure for global markets.

At the same time, large financial institutions face capital, compliance, and operational constraints that make fully open networks challenging. This has led to the development of permissioned frameworks like the Canton Network, which aims to provide a shared ledger where banks, asset managers, and custodians can transact with privacy and regulatory controls. Canton emphasizes formal governance, with a Protocol Development Fund funded by 5% of future CC emissions to support builders and infrastructure providers, and structured onboarding packages to help institutions move from pilots to production-grade deployments. In this model, the network itself is infrastructure, but so are the node-hosting, monitoring, and integration services around it.

These two approaches are not mutually exclusive. Many banks are exploring public-chain settlement for some assets and permissioned rails for others. The same institution might use Ethereum for tokenized government bonds while participating in a consortium chain for interbank deposit tokens. The choice of settlement infrastructure becomes a portfolio decision based on risk appetite, regulatory clarity, and performance needs.

### Scaling Settlement: Rollups and Data Availability Layers

As activity on settlement networks grows, scalability becomes a central infrastructure challenge. Rather than pushing all computation and data onto a single chain, the ecosystem has converged on a layered approach. Rollups execute transactions off the main chain and periodically post compressed proofs back to the base layer, which acts as a final arbiter. This design preserves security while increasing throughput.

A key component of this architecture is the **data availability (DA) layer**, a specialized blockchain infrastructure that focuses on receiving and storing transaction data and making it accessible for verification. In a rollup-centric world, the DA layer ensures that anyone can reconstruct rollup state if needed, even if some participants go offline or act maliciously. By decoupling data availability from execution, these layers can optimize for high throughput and low cost, making rollups more efficient.

These scaling primitives are not only technical upgrades; they underpin new market structures. Lower transaction costs and higher capacity make it viable to settle retail payments, microtransactions, or AI-agent interactions onchain without saturating the base layer. For stablecoins and tokenized assets, rollups and DA layers enable high-frequency trading and payments infrastructure that still ultimately settles to a secure L1. Over time, the settlement layer becomes a thin, highly secure base, while much of the economic activity shifts to specialized L2s connected by shared DA infrastructure.

## Core Supporting Infrastructure: Data, Storage, and Confidentiality

Beyond settlement, modern crypto infrastructure must handle data in multiple dimensions: availability, indexing, storage, and privacy. Where blockchains were once imagined as simple transparent ledgers, they are increasingly part of a more complex data stack.

### Data Availability, Indexing, and Risk Systems

As noted, data availability layers guarantee that transaction data is published and retrievable for verification and fraud-proof construction. Above them, indexing infrastructure transforms raw blockchain data into structured, queryable formats that can feed risk engines, compliance tools, and analytics dashboards. This is particularly important for stablecoins, where the underlying data exists onchain, but is not straightforward for a bank’s risk desk to interpret in real time.

A recent analysis of stablecoin compliance infrastructure argues that regulatory and institutional readiness cannot wait for perfect legal clarity. For fiat-backed stablecoins such as USDC, USDT, and newer entrants, the core questions are what assets actually back the tokens, who attests to those reserves, and how frequently. While issuers may publish monthly attestations, those are backward-looking PDFs, not real-time risk tools. For more complex models, such as overcollateralized or delta-neutral stablecoins, risk teams need live views of collateral ratios, liquidation activity, and hedge positions across multiple protocols.

The common thread is that the relevant data—issuance events, redemptions, collateral flows—is onchain and public, but not readily usable in its raw form. Infrastructure providers, including indexing protocols and analytics platforms, step into that gap by ingesting smart contract state across vaults and stablecoin contracts, transforming it into structured feeds that banks and regulators can consume. In effect, they build the data plumbing that turns public ledgers into auditable, monitorable financial infrastructure.

### Decentralized Storage and AI Data Layers

Another dimension of infrastructure concerns storage. While blockchains can store small amounts of critical data, they are not designed to hold large datasets, such as documents, images, or training corpora for AI models. Decentralized storage networks like Filecoin fill this role by providing markets where users can store and retrieve data with cryptographic guarantees about availability and integrity. Filecoin positions itself as the world’s largest decentralized storage network, aiming to keep data secure, verifiable, and free from centralized control.

This storage layer is increasingly relevant for AI. As model sizes and training datasets grow, traditional cloud providers charge significant premiums for data egress and API calls, especially when models repeatedly read their own training data. This cost structure has prompted calls for open infrastructure that matches the needs of open-weight models, including storage and bandwidth layers that are not locked into proprietary pricing. In that context, decentralized storage networks become not only Web3 infrastructure but AI infrastructure: a way to host training and inference data in a verifiable, censorship-resistant manner, potentially with incentives for long-term preservation.

Coupled with settlement layers and DA solutions, decentralized storage creates a broader data fabric. Transactional data lives onchains and rollups; larger assets and model weights live on storage networks; pointers and commitments tie the two together. For AI agents executing onchain, this fabric provides both the memory and the court of record for their actions.

### Confidentiality as Infrastructure

If early DeFi featured “everything visible to everyone,” the next phase of onchain finance is grappling with how to make systems auditable without exposing every detail to every observer. One articulation of this shift describes the move from blanket transparency to “auditable finance,” where data is visible on demand to the right parties, with verifiable trails and selective disclosure. In this view, confidentiality is not an add-on feature but infrastructure in its own right.

Projects like iExec have argued for confidentiality-as-infrastructure, building tools that allow sensitive data and computations to be processed in trusted execution environments or via zero-knowledge proofs, while still producing audit trails where needed. For institutional-grade finance, this matters because banks, corporates, and high-net-worth clients often cannot operate on fully transparent public ledgers without leaking trading strategies, counterparties, or personal information. Yet regulators demand provable controls, risk management, and reporting.

Confidentiality infrastructure, therefore, aims to reconcile these needs: transactions and positions can be hidden from general view, but regulators, auditors, or designated verifiers can access or reconstruct the necessary data, often via cryptographic attestations. This dovetails with the broader trend toward verifiable backing for stablecoins and tokenized assets, where the goal is not maximal secrecy or maximal transparency, but structured, selective visibility anchored in robust infrastructure.

## Custody, Tokenization, and Verifiable Asset Backing

As more value moves onchain, the question of who holds the keys—and how they prove that assets are really there—has become central. Custody and tokenization infrastructure translate between offchain legal claims and onchain representations.

### Institutional Custody as Foundational Infrastructure

For institutions, custody is the “first mile” of digital asset adoption. Without secure, compliant ways to hold and move assets, banks, asset managers, and corporates cannot meaningfully use crypto. Providers like Ripple emphasize custody as the foundational step that enables use cases across stablecoins, tokenization, trading, and beyond. Their institutional digital asset custody platforms are designed to integrate with existing banking and treasury systems, bringing segregated accounts, policy controls, and multi-signature security into a crypto-native environment.

Similarly, infrastructure like Fireblocks provides secure key management and transaction orchestration for institutions, often sitting underneath consumer-facing apps or institutional trading desks. When a firm like Re designs its approach to verifiable reserves, one of the layers involves custody on platforms such as Fireblocks, ensuring that reserve assets are held in environments with robust operational and security controls. Custody infrastructure thus provides the physical and cryptographic foundation upon which more complex assurances can be built.

The institutional focus on custody also reflects regulatory expectations. Many jurisdictions require clearly defined custodians for client assets, with capital, insurance, and audit requirements. As stablecoins and tokenized assets proliferate, these custody systems increasingly bridge onchain and offchain finance, making them a core piece of crypto infrastructure rather than a peripheral service.

### Verifiable Backing for Stablecoins and Tokenized Assets

If custody holds assets, verifiable backing proves they exist and match onchain claims. The challenge is that “claiming backing is easy; proving it means giving anyone the data to check.” That is the ethos behind newer approaches to reserve transparency, where multiple layers of attestation and onchain reporting work together to demonstrate solvency.

One example is Re’s four-layer framework for proving its reserves: institutional custody with Fireblocks, independent reserve attestation published onchain, third-party audits, and operational controls that govern redemptions and risk management. By combining onchain disclosure with traditional audits, Re aims to let counterparties verify not only that reserves are present, but that systems exist to keep them aligned with liabilities over time. This multi-layered approach reflects a broader trend: onchain data does not replace offchain governance, but it can enhance and verify it.

Stablecoin infrastructure faces similar demands. As the Graph’s analysis notes, a legal definition of compliant fiat-backed stablecoins is emerging around being fiat-collateralized, redeemable at par, and auditable. For fiat-backed tokens like USDC or USDT, risk teams need visibility into reserve composition, issuance and redemption flows, and any deviations in market price from the peg. For more complex designs, such as CDP-based or delta-neutral stablecoins, they must track collateral ratios, liquidation events, and hedge exposures. Monthly attestations are insufficient; what institutions require is a live data feed aligned with blockchain state, not corporate reporting cycles.

Projects like Amp, focused on provenance tracking and tamper-evident records, illustrate one direction of travel: making verifiable audit trails a native feature of tokenized assets rather than an afterthought. The goal is that whenever someone holds or transacts a stablecoin or tokenized instrument, they can query—in near real time—the quality and composition of backing, sourced from both onchain events and signed attestations.

RWA tokenization introduces another layer. When real-world collectibles are brought onchain, as with Renaiss, infrastructure must extend beyond financial reserves to physical custody and authenticity. Renaiss’s architecture turns independent vaults and card shops into onchain verification nodes, using cryptographic multisig to co-sign asset status and reduce reliance on any single custodian. In effect, the custody network itself becomes a distributed oracle attesting that specific physical assets exist, are in good condition, and remain under controlled storage. That design shows how verifiable backing can apply not just to cash reserves but to physical items.

### Tokenization Infrastructure: From RWAs to Collectibles

Tokenization requires more than smart contracts; it needs standardized legal frameworks, custody, and market infrastructure. Platforms like Centrifuge, which Coinbase has designated as a preferred tokenization infrastructure provider, position themselves as end-to-end rails for moving private credit, fixed income, and equity exposure onchain. They handle structuring, issuance, compliance, and integration with public chains such as Base, enabling institutions to originate and invest in real-world assets via crypto-native interfaces.

On high-performance chains like Solana, tokenization is becoming a defining narrative. Describing Solana as financial infrastructure for issuing assets underscores that the network’s utility increasingly lies in hosting tokenized representations of traditional instruments, from treasuries to private credit. This shift requires robust infrastructure: oracles, market venues, risk management tools, and compliance layers that can handle both retail and institutional participation.

Meanwhile, specialized projects like Renaiss extend tokenization to collectibles, turning card shops and vaults into onchain verification nodes with multi-signature custody. In parallel, corporate developments, such as companies rebranding as digital infrastructure providers for blockchain-based markets, signal that tokenization is becoming mainstream enough to warrant capital-markets-grade operational structures.

Together, custody, verifiable backing, and tokenization platforms form a continuum of infrastructure that bridges offchain claims and onchain representations. They are key to the thesis that stablecoins and RWAs will be the primary drivers of institutional onchain adoption.

## Liquidity, Markets, and Payments Infrastructure

Once assets exist and are properly backed, they need liquidity and payment rails. Crypto’s market and payments infrastructure is evolving from ad hoc exchanges and gateways into a layered stack that supports diverse asset types and user groups.

### AMMs and Liquidity Hubs as Infrastructure

Automated market makers (AMMs) and liquidity pools are no longer just DeFi experiments; they are part of the core infrastructure that underpins onchain markets. Orca, for example, describes its role as serving liquidity for crypto-native assets, hybrid assets, and even traditional financial assets coming onchain, positioning itself as infrastructure for the full spectrum of token types. That perspective treats AMMs not merely as venues but as shared liquidity utilities that issuers, market participants, and other protocols can plug into.

In the context of Internet Capital Markets, AMM infrastructure is a crucial component of how issuance, trading, and settlement converge on a single ledger. When a new RWA token launches, it can immediately tap into Orca-style liquidity pools, enabling price discovery, trading, and arbitrage without building a bespoke order book. Stablecoins and tokenized treasuries can become base pairs across these pools, turning them into de facto money markets and FX rails for onchain assets. Over time, such AMMs may be integrated into institutional trading systems as alternative liquidity venues, especially in regions like Asia where ICM adoption is projected to accelerate.

This shift elevates AMMs from “DeFi apps” to **market infrastructure**, analogous to alternative trading systems or liquidity venues in traditional markets. Their reliability, security, and composability become critical not just for retail users but for institutional strategies that depend on predictable execution and risk management.

### Stablecoin Payment Rails

Stablecoins sit at the intersection of markets and payments infrastructure. On the consumer and merchant side, providers like ForumPay are expanding crypto payment rails, allowing businesses to accept digital assets and settle in fiat or stablecoins, with a focus on faster settlement and greater flexibility than traditional card networks. Their expansion reflects growing merchant interest in alternative payment technologies and the need for gateways that handle currency conversion, compliance, and integration with existing systems.

On the card-network side, Visa has been actively developing stablecoin capabilities, positioning its solutions as ways for businesses to bring their existing operations onchain. Visa’s stablecoin integrations allow issuers and acquirers to settle obligations using stablecoins on public blockchains, bridging card payments and crypto-native rails. This kind of infrastructure blurs the line between Web2 and Web3: a merchant may not know or care whether settlement happens over traditional rails or via an onchain stablecoin corridor, but the network’s underlying infrastructure dictates costs, speed, and reach.

Specialized stablecoin infrastructure firms, such as Trace Finance, focus on the regulated, institutional side of this equation. Trace’s Series A funding aims to scale regulated banking and stablecoin infrastructure across Brazil, the United States, and emerging markets, with an emphasis on transaction capacity and cross-border flows. Their model integrates stablecoin rails directly with banking partners, enabling institutions to move value across jurisdictions while satisfying local licensing and compliance requirements. In parallel, firms like OSL, which have secured licenses such as Australian Financial Services Licences, are positioning themselves as regulated gateways for stablecoins and digital asset payments, especially in markets where regulatory clarity is improving.

Taken together, these developments support the thesis that the “stablecoin era” is not a hypothetical future but an unfolding reality. Large institutions, including those managing trillions in assets, are beginning to build GENIUS Act-compliant stablecoin and tokenization infrastructure, suggesting that convergence between traditional and crypto-native payment rails is accelerating.

### Banking and Deposit Token Infrastructure

Beyond stablecoins, banks are exploring **deposit tokens**—onchain representations of commercial bank deposits—as another layer of payment infrastructure. When major clearing networks and member banks decide to include onchain flows within their remit, they are effectively committing to build shared tokenized deposit infrastructure. While much of this work is still in development, announcements that clearing houses processing trillions of dollars daily are targeting tokenized deposit launches in the coming years indicate a significant shift in how interbank payments may operate.

In this context, permissioned networks like Canton and regulated stablecoin infrastructure providers like Trace Finance can act as staging grounds for deposit-token experiments. They offer privacy, KYC/AML controls, and formal governance structures that align more closely with banking regulation than fully public chains, while still drawing on blockchain primitives such as atomic settlement and programmable logic.

The strategic question for institutions is not whether to use onchain infrastructure, but which combination of stablecoins, deposit tokens, and tokenized assets best fits their use cases. Payment infrastructure is fragmenting and recombining, with some flows settling in fiat, some in stablecoins on public chains, and others via deposit tokens on consortium networks. Underneath, infrastructure providers handle integration, compliance, and connectivity.

## AI-Native Infrastructure and Agentic Systems

As AI systems become economic actors rather than mere tools, they require infrastructure that can manage identity, permissions, payments, and data at machine speed. Crypto-native rails are increasingly seen as a natural fit for AI agents coordinating and transacting.

### AI Agents as Onchain Economic Actors

Recent discussions on AI x Ethereum highlight how settlement and verifiable infrastructure can support economically active AI systems at scale. One emerging standard, ERC‑804, is effectively a governance and identity framework for AI agents, introducing decentralized registries that record agent identities and allow bots and humans to leave feedback about each other. This creates an onchain reputation system that agents can use to assess counterparties before transacting or collaborating.

Complementing identity, a “sign in with agent” standard allows AI agents to authenticate and prove certain properties—such as being registered in a trusted registry or meeting specific compliance requirements—when accessing APIs or services. Instead of sharing raw credentials, agents present verifiable attestations tied to onchain records, aligning with broader trends in decentralized identity. This is particularly important when agents handle financial transactions, where counterparties and regulators need assurance that they are interacting with controlled, policy-bounded systems.

Kite’s demonstration of agentic payments for travel offers a concrete example: AI agents can discover, reserve, and pay for local experiences within user-defined budget rules, using payment infrastructure layers built specifically for agent-driven flows. That requires wallets, policy engines, and authorization infrastructure that can interpret human constraints and enforce them programmatically during onchain interactions.

### Compute and Data Infrastructure for AI

AI agents and models also need compute and data infrastructure capable of operating in an open, interoperable way. HIVE’s large AI infrastructure contracts with partners like Bell and Cohere illustrate the demand for dedicated compute providers that can support model training and inference at scale, often in tandem with cloud giants. Nevertheless, the reliance on centralized cloud providers comes with cost and control trade-offs, especially around data.

Here, decentralized storage networks like Filecoin argue that open-weight models deserve open infrastructure. By offering verifiable, censorship-resistant storage, they aim to provide a data layer where models can read and write training or context data without incurring punitive egress fees or being tightly coupled to proprietary platforms. When combined with onchain settlement, this allows AI agents to pay for data access or storage in a programmable way, potentially using stablecoins or network-native tokens as mediums of exchange.

Some blockchain ecosystems, such as NEAR, articulate a vision of acting as unified commerce layers for assets and AI agents, providing a platform where machine actors can manage wallets, pay for services, and interact with other agents. Ethereum, meanwhile, is seen as the high-assurance settlement layer where disputes or high-value interactions eventually resolve, anchoring the AI economy in a secure base. The result is a multi-layered infrastructure where AI agents can exist as onchain entities with persistent identity, balances, and reputations.

### Governance, Safety, and Compliance for AI Infrastructure

AI-native infrastructure raises governance and safety questions that echo earlier debates about DeFi but at machine speed. Permissionless infrastructure advocates argue that open, credibly neutral systems are vital to preventing capture by any single corporation or government. Yet regulators and institutions worry about uncontrolled AI agents manipulating markets, laundering funds, or accessing sensitive data.

Here, confidentiality and auditability infrastructure play key roles. Systems like iExec’s confidential computing and auditable finance frameworks can support AI workflows where sensitive data is processed in secure environments, with verifiable logs available to regulators or auditors when needed. Layered on top of identity standards like ERC‑804 and “sign in with agent,” this enables a model where AI agents operate in constrained, observable ways, subject to policy and oversight without being fully centralized.

Compliance infrastructure designed for stablecoins—monitoring transactions, screening counterparties, enforcing sanctions—can be extended to AI agents as well. Instead of just checking whether a wallet is on a blacklist, systems can evaluate whether an agent is registered, adheres to certain behavioral constraints, and is subject to human or institutional oversight. This is a nascent field, but its foundations are likely to be deeply intertwined with crypto infrastructure choices.

## Operational and Governance Infrastructure For Institutions

For institutions, the existence of blockchains and protocols is necessary but not sufficient. They also require operational and governance infrastructure that turns abstract networks into dependable platforms.

### Node Hosting, Monitoring, and DevOps

Running production-grade blockchain infrastructure involves more than spinning up a node. Enterprises must handle uptime, security patches, key management, connectivity, and integration with existing systems. Networks like Canton explicitly recognize this by providing structured onboarding packages that outline what it takes to go from pilot to production, starting with node hosting and operational best practices delivered by partners like CatalyX and IntellectEU. This reflects an understanding that institutional adoption depends on reliable, well-documented infrastructure services, not just protocol code.

Similarly, the Avalanche ecosystem has invested in research grants and foundation support for infrastructure and tooling, recognizing that developer experience and operational reliability are critical to sustaining growth. The Avalanche Foundation’s call for research proposals, which has attracted hundreds of applications, signals a willingness to fund not only applications but also the underlying infrastructure that supports them. From RPC providers to indexers and monitoring tools, these components are part of the invisible scaffolding that keeps networks usable.

On the security side, projects like Aero emphasize institutional-grade infrastructure that treats audits and security reviews as non-negotiable, with full rounds of third-party assessments covering smart contracts, operational processes, and system architecture. This mindset echoes traditional financial infrastructure, where clearing houses and payment networks undergo rigorous testing and supervision.

### Compliance, Identity, and Access Control

Regulatory infrastructure is one of the most complex areas for institutions entering crypto. Stablecoin compliance infrastructure, as discussed earlier, must give risk desks a continuous view of holdings, counterparties, and reserve backing. For banks and asset managers, that means integrating onchain analytics, sanctions screening, and travel rule compliance into transaction flows, often using both native blockchain data and offchain KYC repositories.

Messaging platforms, too, have become part of regulated infrastructure, as the India–Telegram case illustrates. When regulators treat messaging apps as critical infrastructure with obligations around access, compliance, and local enforcement, it underscores that control over communication and coordination layers carries real operational risk for crypto projects building on top of them. For onchain infrastructure, similar dynamics apply to RPC gateways, API providers, and even cloud hosting environments.

Identity and access control systems tie these elements together. For human users, this involves KYC, identity verification, and potentially reusable decentralized identifiers. For AI agents, standards like “sign in with agent” and ERC‑804 bring identity and access into the onchain realm, enabling fine-grained control over which agents can access which services under what conditions. Privacy-preserving credentials and zero-knowledge proofs can allow users and agents to prove properties—for example, being over a certain age or not being on a sanctions list—without disclosing full identity data, aligning with the auditable-finance vision.

### Funding and Building Infrastructure Ecosystems

Infrastructure is capital-intensive and slow to monetize compared with consumer-facing apps. To address this, many ecosystems are building formal funding mechanisms. Canton’s Protocol Development Fund, financed by 5% of future CC emissions, explicitly exists to support builders, infrastructure, and the broader ecosystem, governed by the Canton Foundation with transparent reporting. This aligns token incentives with long-term network health, rather than short-term speculation.

Avalanche’s grants for research and infrastructure development similarly signal that protocols understand the need to invest in tooling, documentation, and foundational services. On the startup side, fundraising by firms like Renaiss for RWA liquidity infrastructure and Trace Finance for regulated stablecoin and banking infrastructure indicates that investors see long-term value in owning parts of the rails rather than only the apps. These rounds often emphasize the ability to scale transaction capacity, integrate with multiple chains, and meet regulatory expectations.

Tokenization infrastructure providers, such as Centrifuge in partnership with Coinbase, benefit from both ecosystem grants and venture funding as they build the pipelines that channel institutional assets onto public chains. Over time, the health of a blockchain ecosystem may be measured less by the number of speculative apps and more by the robustness and diversity of its infrastructure providers: custodians, indexers, compliance platforms, data availability layers, and more.

## Key Debates: Centralization, Neutrality, and “Open Infrastructure”

Underlying these concrete developments are deeper debates about what kind of infrastructure should underpin future markets and AI systems.

### Why Permissionless Infrastructure May Win, But Institutions Still Need Guardrails

The argument that “permissionless infrastructure wins” rests on historical analogies and on specific properties of open systems. Open, credibly neutral networks like Ethereum or Bitcoin cannot easily be captured by single entities, reducing counterparty risk and political interference. They foster innovation by lowering barriers to entry: anyone can deploy a smart contract, build a front-end, or integrate a protocol without seeking permission. Over time, this can attract more developers, applications, and capital than closed, proprietary networks, mirroring how Linux and TCP/IP outcompeted proprietary operating systems and networking stacks.

However, institutions operate under regulatory and fiduciary constraints that make pure permissionlessness difficult to adopt wholesale. They need explicit governance, clear legal accountability, and the ability to restrict participation in certain contexts. That is why consortium networks like Canton, or permissioned subnets within broader ecosystems, have traction: they offer a controlled environment with known participants, while still leveraging some of the benefits of shared ledgers and automation.

The likely outcome is not a single “winner” but a layered ecosystem. Permissionless infrastructure may serve as the universal settlement and innovation layer, while permissioned networks and specialized infrastructure handle regulated, high-touch activities. Interoperability between these domains—bridges, shared identity and compliance frameworks, and cross-chain liquidity—will be a key area of infrastructure development.

### Transparency Versus Confidentiality

Another tension lies between transparency, long touted as a core virtue of blockchains, and the need for confidentiality in finance and AI. Fully transparent ledgers make it easy to audit system-wide behavior and detect systemic risks, but they can harm individual privacy and expose trading strategies or business relationships. Confidentiality-as-infrastructure frameworks, as articulated by iExec, propose a middle path where systems shift from “everything visible to everyone” to “auditable on demand by the right parties.”

This shift aligns with stablecoin compliance infrastructure, which emphasizes that data should be accessible and structured for risk teams and regulators, not necessarily for the general public. The challenge is designing systems where proofs and attestations provide enough assurance without revealing sensitive details. Zero-knowledge proofs, trusted execution environments, and selective disclosure primitives will likely form the backbone of this infrastructure.

As AI agents enter the picture, confidentiality and transparency debates become even more complex. Agents may need to access sensitive data to perform tasks, yet their actions must be logged and auditable to prevent abuse. Crypto infrastructure that can provide both privacy and verifiability will be central to resolving these tensions.

### Systemic Risk and Resilience

Finally, infrastructure choices have implications for systemic risk and resilience. Concentration in a few custodians, cloud providers, or compliance platforms can create single points of failure, even if the underlying blockchains are decentralized. Incidents like messaging platforms being treated as regulated infrastructure, or major cloud outages, highlight how dependencies outside the crypto protocol layer can impact onchain systems.

Building resilient infrastructure requires diversification: multiple custody providers, redundant data availability layers, decentralized storage, and open-source reference implementations that reduce reliance on proprietary stacks. It also requires regulatory recognition that some infrastructure—like public blockchains and stablecoin systems—is becoming systemically important, necessitating new oversight models that account for their hybrid public–private nature.

The convergence of AI and crypto adds further complexity. AI-driven trading or lending interacting with high-speed AMMs and leveraged positions could produce new forms of flash-crash or feedback-loop risk, while AI agents controlling large treasuries might introduce novel attack surfaces. Infrastructure that can enforce policy limits, monitor behavior, and throttle activity when needed will be critical to maintaining systemic stability.

## Outlook

Crypto infrastructure is moving from an experimental stack supporting speculative trading to a multi-layered system underpinning payments, capital markets, AI agents, and data-intensive applications. Settlement layers like Ethereum, Avalanche, and Solana are being reframed as global financial infrastructure, while permissioned networks like Canton offer institutions controlled environments with shared governance and funding for builders. Above them, data availability, indexing, and confidentiality infrastructure are turning raw blockchain state into usable, auditable feeds for risk systems and regulators.

Stablecoin and tokenization infrastructure sit at the center of institutional adoption. Custody platforms, verifiable backing frameworks, and tokenization pipelines are transforming how reserves, RWAs, and collectibles appear onchain, with projects like Re, Renaiss, Centrifuge, and Trace Finance illustrating different facets of this shift. Liquidity and payments infrastructure—AMMs like Orca, payment gateways like ForumPay, and card-network integrations from Visa—are ensuring these assets can move fluidly across markets and jurisdictions.

At the same time, AI is emerging as both a user and a builder of crypto infrastructure. Standards for agent identity and governance, decentralized storage for model data, and confidential computing frameworks are converging into a stack where AI agents can transact, coordinate, and be audited onchain. The interplay between permissionless and permissioned infrastructure, transparency and confidentiality, and human and machine governance will define the next decade of development.

For a crypto news audience, the main takeaway is that “infrastructure” is no longer a background concern; it is where the most consequential bets are being placed. Whether you are following stablecoin regulation, RWA tokenization, AI agents, or institutional adoption, the critical questions increasingly boil down to infrastructure: which rails assets run on, who controls them, and how verifiable, neutral, and resilient they really are.
