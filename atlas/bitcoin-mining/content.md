The process by which new bitcoin enters circulation and transactions are permanently recorded on a shared ledger — Bitcoin mining — is also the mechanism that keeps the entire network secure, decentralized, and resistant to manipulation.

Bitcoin mining is simultaneously a computational puzzle, an energy market, a global financial industry worth tens of billions of dollars, and, increasingly, a geopolitical asset that nation-states are racing to control.

## How Bitcoin Mining Works

At its core, Bitcoin mining is the execution of Proof of Work (PoW): competing computers race to find a number (called a *nonce*) that, when combined with a block of pending transactions and run through the SHA-256 cryptographic hash function twice, produces an output below a dynamically adjusted target value. The first machine to find a valid hash wins the right to append that block to the blockchain and claim the block reward — currently **3.125 BTC** following the April 2024 halving — plus transaction fees paid by users whose transfers were included in the block.

This process is deliberately expensive. The computational cost is what makes rewriting history prohibitively difficult: to alter a past block, an attacker would need to redo the proof-of-work for every block that came after it, faster than the honest network is extending the chain. The more total hashing power (hashrate) the network has, the more costly such an attack becomes.

**Key terms:**
- **Hashrate** — the total computational power dedicated to mining, measured in hashes per second (H/s). The Bitcoin network currently sits near **1.05 ZH/s** (zettahashes per second), meaning roughly one sextillion hash attempts per second ([CoinWarz](https://www.coinwarz.com/mining/bitcoin/hashrate-chart)).
- **Difficulty** — a unitless number that adjusts every ~2,016 blocks (roughly two weeks) to keep average block time at 10 minutes. When more miners join, difficulty rises; when they leave, it falls.
- **ASIC** — Application-Specific Integrated Circuit, a chip built exclusively for SHA-256 hashing. Modern ASICs from manufacturers like Bitmain, MicroBT, and Canaan achieve efficiencies around 14–18 joules per terahash (J/TH), compared to 1,000+ J/TH for early GPU rigs.
- **Block reward** — the subsidy (plus fees) a miner earns for finding a valid block. The subsidy halves approximately every four years in an event called the *halving*.

## The Economics of Mining

Mining profitability is a function of three variables: BTC price, network difficulty (which determines your share of block rewards for a given amount of hardware), and electricity cost.

**Halvings** compress miner revenue periodically by design. After each halving, the block subsidy falls by 50%, meaning miners must rely on either a higher BTC price or lower operating costs to remain solvent. The most recent halving cut the reward from 6.25 BTC to 3.125 BTC. The next halving, expected around 2028, will drop it to 1.5625 BTC.

**Difficulty adjustments** act as a market-clearing mechanism. In mid-June 2026, Bitcoin's mining difficulty fell roughly **10%** — the 11th-largest downward adjustment in network history and the second-largest negative adjustment of 2026 — bringing difficulty to approximately **124.93 trillion**, its lowest level since July 2025 ([The Block](https://www.theblock.co/post/404702/bitcoin-mining-difficulty-drops-10-in-second-largest-negative-adjustment-of-2026)). The drop followed a period of sustained BTC price weakness in which miner margins fell to record lows, triggering a wave of under-capitalized operators shutting down machines or selling existing inventory.

This kind of contraction — sometimes called miner *capitulation* — is a normal part of the mining cycle, not a sign that the network is failing. Weaker operators exit; the difficulty falls to compensate; surviving and new operators become more profitable; new hardware comes back online; difficulty rises again.

**Break-even cost** for miners varies enormously by geography and hardware vintage. Industrial operators with sub-$0.03/kWh power contracts and the latest-generation ASIC fleets can remain profitable at BTC prices well below $50,000. Operators running older hardware at retail electricity prices may break even only above $80,000 or higher.

## Mining Pools

Individual miners today have a negligible probability of solving a block solo. The standard solution is *mining pools*, where participants combine their hashrate and split rewards proportionally, smoothing out income.

Major pools — including Foundry USA, AntPool, F2Pool, and ViaBTC — collectively account for the majority of global hashrate. Pool concentration has been a recurring topic in Bitcoin governance debates, as a sufficiently dominant pool could theoretically attempt to reorganize recent blocks. In practice, pool operators have strong financial incentives not to attack a network they depend on.

A notable development: Wang Chun, co-founder of F2Pool, has been announced as a crew member on SpaceX's first crewed Starship mission to Mars — a two-year interplanetary journey. The mission signals the degree to which Bitcoin's infrastructure has become intertwined with the broader frontier tech ecosystem.

## Energy and Environment

Bitcoin mining consumes an estimated **128 TWh per year** globally — roughly comparable to a mid-sized country's electricity use, but less than 0.5% of total world electricity consumption ([KuCoin research](https://www.kucoin.com/blog/bitcoin-mining-energy-consumption-how-btc-mining-compares-to-global-power-demand-in-2026)). The energy debate often obscures nuance:

**The case for concern:** Coal still supplies a substantial portion of the network's power globally. At scale, that translates into material carbon emissions. Per-transaction energy comparisons — often cited at 1,300–1,400 kWh — are technically accurate but misleading, since Bitcoin's security model doesn't scale transaction cost linearly with energy.

**The case for nuance:** Bitcoin mining is uniquely *location-flexible*. Miners seek the cheapest power, which frequently means stranded or curtailable electricity: hydropower surplus in wet seasons, flared natural gas at oil fields, excess wind and solar capacity that would otherwise be wasted. This makes mining one of the few industries that can profitably consume energy that has no other buyer.

Tether-backed agricultural company Adecoagro is preparing to launch Bitcoin mining operations in Brazil using electricity generated by burning sugarcane *bagasse* — the fibrous waste left after sugar extraction. The project is a real-world example of using an otherwise-discarded energy stream for mining.

Some U.S. mining operators participate in demand-response programs with grid operators, agreeing to curtail power consumption during peak demand periods in exchange for reduced rates — effectively acting as a flexible load that improves grid stability.

## Geographic Shifts and Sovereign Mining

Since China's 2021 mining ban, the industry has redistributed dramatically. The United States — particularly Texas, Kentucky, and Wyoming — hosts the largest share of global hashrate. Other significant mining jurisdictions include Kazakhstan, Canada, Russia, Iceland, and the UAE.

Several sovereign states are now moving from passive tolerance to active participation:

**Oman** recently launched *Omanhash*, the country's official national Bitcoin mining pool, a joint initiative between Oman's Ministry of Transport, Communications and Information Technology and Frontier Technologies. The pool will serve licensed miners operating within Oman's regulatory framework, making it one of the most formal examples of state-level Bitcoin mining infrastructure anywhere in the world. Oman is the second country Frontier Technologies' parent company Enegix has worked with for a sovereign mining mandate, after Kazakhstan.

**Bhutan** began quietly accumulating BTC through state-run mining operations using Himalayan hydropower several years ago. The kingdom's holdings — disclosed through corporate filings — made it one of the most disproportionate sovereign Bitcoin holders globally relative to its GDP.

**United States** political dynamics have also shifted. Under the current Trump administration, regulatory posture toward mining has become more favorable; a CleanSpark executive and a Bitcoin miner CEO were appointed to serve on the administration's Strategic Bitcoin Reserve committee, signaling the industry's growing policy influence.

**South Carolina** passed legislation explicitly protecting the right to use cryptocurrency and run Bitcoin mining operations, while banning central bank digital currencies (CBDCs) — part of a broader trend of U.S. states establishing pro-mining legal frameworks.

## The AI Pivot

One of the most significant structural trends reshaping Bitcoin mining in 2025–2026 is the pivot by publicly traded miners toward artificial intelligence and high-performance computing (HPC) infrastructure.

The economics are straightforward: data centers built for ASIC mining — grid connections, cooling infrastructure, industrial power contracts — are also valuable for running AI training and inference workloads. The conversion isn't trivial, but the core physical assets overlap substantially.

**IREN** (formerly Iris Energy) entered European markets through its acquisition of Nostrum, accelerating what the company describes as an AI-first strategy. **TeraWulf** acquired a Kentucky site specifically to convert it into an AI data campus, with its stock rising sharply on the announcement. **Cipher Mining** and **Hut 8** both hit fresh highs as investors re-rated Bitcoin mining stocks on AI infrastructure potential.

This pivot creates an interesting dynamic: some companies are effectively using their Bitcoin mining legacy as a capital-efficient path to becoming AI infrastructure providers, while retaining BTC operations as an option on a price recovery.

## Hardware and the ASIC Arms Race

ASIC manufacturing is dominated by a small number of Chinese firms, principally Bitmain (Antminer series) and MicroBT (Whatsminer series), with Canaan (AvalonMiner) a third significant player. Canaan reported a net loss in Q1 2026, with its CEO noting publicly the challenging economics of the current mining environment.

Hardware efficiency improvements have been continuous but are now approaching physical limits with chips manufactured at 3–5nm process nodes. The efficiency frontier is approximately 14–16 J/TH for the best current-generation machines. Incremental gains remain possible, but the step-change improvements of earlier generations — when moving from 28nm to 16nm to 7nm chips yielded massive efficiency gains — are behind the industry.

This matters for the energy debate: as newer machines displace older ones, the network's energy intensity per unit of hashrate falls, even as total hashrate grows.

## Regulatory Environment

Regulatory treatment of Bitcoin mining varies enormously across jurisdictions:

- **United States:** No federal ban; state-level variation. Texas has become a major hub partly because of its deregulated grid and demand-response incentives. Some municipalities have imposed noise and environmental ordinances on large facilities.
- **European Union:** Mining is legal but subject to general energy regulations. The EU's MiCA framework does not specifically target PoW mining, though energy-related disclosure requirements may apply to large operators.
- **China:** Mining remains banned following the 2021 crackdown, though some activity continues in border regions.
- **Central Asia / Middle East:** Kazakhstan, UAE, Oman, and others are actively courting mining investment, sometimes with specific regulatory frameworks as Oman has demonstrated.

Environmental impact reporting requirements for publicly listed miners are tightening in the U.S. and EU, which is driving more operators to formally quantify and document their energy sourcing.

## Security Properties and Threat Model

Bitcoin's PoW mechanism provides a specific security guarantee: altering any confirmed transaction requires re-doing more proof-of-work than the entire honest network has done since that transaction was included. At current hashrates near 1 ZH/s, executing a *51% attack* on Bitcoin would require acquiring and operating hardware equivalent to the entire existing network — an investment of tens of billions of dollars, with the reward being the ability to double-spend transactions or disrupt confirmation, at the cost of destroying confidence in — and therefore the value of — the very asset being attacked.

This self-defeating nature of large-scale attacks is a key reason Bitcoin has operated without a successful network-level security breach since its 2009 launch, even as the ecosystem around it (exchanges, custodians, smart contract protocols) has suffered numerous exploits.

## Outlook

Bitcoin mining is entering a period of structural consolidation. Miner margins are under pressure from a combination of post-halving economics and recent BTC price weakness, and difficulty data confirms that less efficient operators have been exiting. That pressure tends to accelerate industry maturation: capitalized, low-cost operators survive and expand; marginal operators are replaced by more efficient entrants.

Longer-term, the mining industry faces a question the 2028 halving will sharpen: can transaction fees grow enough to compensate for a declining block subsidy? Bitcoin's fee market is still developing, and whether it can sustainably support the level of hashrate the network has accumulated remains an open empirical question.

The AI pivot among listed miners introduces a new variable: companies that successfully build dual-purpose data center infrastructure may be less exposed to pure Bitcoin price cycles than their predecessors, potentially creating a more resilient ownership class for the underlying network security.

Sovereign participation — from Oman to Bhutan — suggests that state actors increasingly view hashrate as a strategic asset, not merely a regulatory headache. That geopolitical dimension is likely to intensify as the network's value grows and energy politics around it become more complex.

---
