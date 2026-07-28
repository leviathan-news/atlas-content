"Mining" in cryptocurrency refers to two distinct but often conflated mechanisms: the computational process by which proof-of-work blockchains validate transactions and mint new coins, and the DeFi practice of earning token rewards by providing liquidity or staking assets in a protocol.

---

## Proof-of-Work Mining: The Foundational Model

When Satoshi Nakamoto launched Bitcoin in 2009, the word "mining" was a deliberate analogy. Just as gold miners expend physical effort to extract scarce metal, Bitcoin miners expend computational work to earn newly issued BTC — and in doing so, they perform the essential function of securing the network.

The mechanics are straightforward in principle: miners race to find a number (a "nonce") that, when combined with a block of pending transactions and hashed, produces an output below a target value set by the protocol. This is a brute-force probabilistic search. The miner who finds a valid hash first broadcasts the block, claims the block reward and transaction fees, and the process resets. The difficulty of the target adjusts roughly every two weeks on Bitcoin so that blocks arrive approximately every ten minutes, regardless of how much or how little total computing power is pointed at the network.

This cumulative computational effort — the network's total hash rate — is what makes Bitcoin's ledger practically immutable. Rewriting history requires outpacing the honest majority of miners, a feat that becomes exponentially more expensive as the network grows.

Other proof-of-work chains use variations on this model. Zcash (ZEC), a privacy-focused chain that traces its lineage to the Zerocash academic paper, uses the Equihash algorithm, which was originally designed to be memory-hard and therefore more resistant to the ASICs (application-specific integrated circuits) that came to dominate Bitcoin mining. Litecoin uses Scrypt. Each algorithm was intended to shape the hardware landscape for mining, with varying success.

## The Hardware Arms Race

Bitcoin mining began on ordinary CPU chips. Within two years, miners had moved to GPUs; within five, to FPGAs; and by 2013, purpose-built ASICs had rendered all prior hardware economically obsolete. Today, Bitcoin mining is an industrial activity dominated by machines from manufacturers such as Bitmain, MicroBT, and Canaan, consuming hundreds of watts each and producing heat that serious operations must actively manage.

The shift toward large-scale, institutionally funded mining operations accelerated after each Bitcoin halving — the protocol-mandated event that cuts the block subsidy in half roughly every four years. With the April 2024 halving reducing the block reward from 6.25 BTC to 3.125 BTC, miners' revenue per block fell sharply, squeezing out less efficient operators and pushing the survivors toward cheaper electricity and newer hardware. A 2026 report examining Bitcoin mining profitability found that the "hashprice" — revenue earned per unit of hash rate deployed — remained compressed compared to pre-halving peaks, a dynamic that mining companies listed on public markets have been navigating openly.

Foundry USA, a subsidiary of Digital Currency Group, became one of the largest mining pools in the world in part by aggregating North American institutional miners and offering financing for hardware purchases. Its rise reflected a broader professionalization of the sector.

## Energy, Geography, and Regulation

Mining's energy appetite is its most politically contentious attribute. Estimates of Bitcoin's annualized electricity consumption have ranged widely — the Cambridge Centre for Alternative Finance's Bitcoin Electricity Consumption Index has placed it at roughly the level of mid-sized countries at various points — though the geographic composition of that consumption matters as much as the aggregate.

After China banned cryptocurrency mining in 2021, hash rate migrated rapidly to the United States, Kazakhstan, Russia, and Canada. The redistribution created new regulatory flashpoints. Russia's Government Commission recommended banning cryptocurrency mining in the Moscow region amid concerns about strain on the power grid, a position consistent with restrictions already imposed in several Russian regions during peak winter demand. Iran, where subsidized electricity has long made mining attractive, has grappled with illegal mining operations that tap industrial power allocations; recent commentary from Iranian analysts framed addressing illicit mining as an opportunity to restructure electricity pricing more equitably rather than simply a law enforcement problem.

In Canada, a Saskatchewan resident faced extradition to the United States over allegations of hacking university computing infrastructure to run unauthorized mining — an example of the legal exposure that comes with operating mining rigs on infrastructure that does not belong to you.

## Mining Economics and the Profitability Equation

The economics of proof-of-work mining reduce to a simple but volatile equation: revenue (block rewards plus fees, denominated in the mined asset) minus costs (electricity, hardware depreciation, hosting, and capital). The three variables that move most dramatically are the asset's price, the network's difficulty, and electricity cost.

For publicly traded mining companies, profitability reports have become a regular disclosure item. Luxxfolio, a Canadian miner, marked a milestone by mining its 500th Litecoin as it scaled operations to 60 machines — small relative to major Bitcoin miners, but illustrative of the range of scale at which mining remains viable. Bit Digital reported a 14% Q1 2026 revenue decline, citing weaker Ethereum staking rewards (as the company diversifies away from proof-of-work) and lower mining income. DMG Blockchain Solutions reported stable April mining results, underscoring that operational consistency matters as much as headline numbers.

TeraWulf, a U.S.-listed miner that built its infrastructure around low-carbon power sources, illustrates a more complicated picture: the company reported a $427 million quarterly loss even as its AI-related revenue doubled. The loss stemmed largely from impairments and the cost of pivoting data center capacity toward AI compute — a strategic bet that mining economics alone could not justify expansion at scale.

## The AI Pivot: Mining Infrastructure Repurposed

The overlap between Bitcoin mining infrastructure and AI compute is not coincidental. Both require large-scale power delivery, dense server deployment, sophisticated cooling, and robust network connectivity. As AI demand for GPU clusters has surged, several mining companies have begun marketing their sites as potential AI data centers, either by retrofitting existing facilities or by designing new ones with dual-use in mind.

Bernstein analysts charted a $100 price target for IREN (formerly Iris Energy) on the basis of its AI cloud business, while flagging dilution risk and the declining contribution from mining operations. The pattern — mining as a cash-flow bridge while building toward AI workloads — recurred across several companies in 2025 and 2026. GAIB, an infrastructure financing platform, formalized a similar logic by deploying mining resources into the Gonka network before opening access to broader market participants.

This convergence raises an important distinction: hosting GPU clusters for AI inference or training is not "mining" in any blockchain sense, but the companies making the pivot often carry "mining" in their brand identity, creating terminological confusion for investors and journalists alike.

## Liquidity Mining: DeFi's Parallel Meaning

In decentralized finance, "liquidity mining" (also called yield farming) refers to a completely different mechanism: users deposit assets into a protocol — typically a decentralized exchange, lending platform, or automated market maker — and receive the protocol's native governance token as an additional reward on top of any trading fees or interest earned.

The term was popularized during DeFi's 2020 surge when Compound began distributing COMP tokens to borrowers and lenders. It spread rapidly because protocols discovered that token emissions were an efficient way to bootstrap liquidity from zero.

Examples from current activity illustrate the variety of forms this takes. JustLend DAO launched Phase 19 of its USDD 2.0 Supply Mining program in June 2026, offering roughly 4% APY (dynamically adjusted) in USDD rewards to users who supply stablecoins to the protocol. KyberSwap's FairFlow Liquidity Mining Season 4 distributed 200,000 KNC tokens over eight weeks to liquidity providers on Arbitrum across three income streams: trading fees, an earnings-sharing mechanism, and direct KNC rewards. Fractal Bitcoin opened a beta program for non-custodial staking and "index mining" rewards for holders of Fractal Bitcoin assets.

Bittensor, an AI-focused network, uses a variant called "subnet mining" in which participants contribute compute or model outputs to subnets and earn TAO rewards, though validators have increasingly tightened criteria to exclude participants gaming rewards without producing genuine utility — a dynamic its community calls "self-mining patterns."

Critics of liquidity mining have long argued that token emissions primarily attract mercenary capital that exits as soon as reward rates decline, creating boom-bust cycles in protocol TVL. The more durable programs tend to be those where the underlying protocol generates sufficient fee revenue to make emissions a modest supplement rather than the primary incentive.

## Tax and Legal Landscape

Taxation of mining income has been a source of regulatory uncertainty in most jurisdictions. In the United States, the IRS has treated proof-of-work mining rewards as ordinary income at the fair market value of the asset on the date of receipt since at least 2014 guidance. Subsequent sale of mined coins triggers capital gains treatment.

In June 2026, the House Ways and Means Committee circulated a package of seven digital asset tax discussion drafts intended to codify and update U.S. crypto tax rules. The drafts addressed mining and staking income specifically, alongside wash sale rules, stablecoin transactions, and crypto lending — representing the most comprehensive Congressional effort yet to legislate across the full range of crypto activity rather than treating it piecemeal.

For liquidity mining, the tax treatment is more contested: whether token rewards are income when received, or only taxable upon sale, remains an open question in many jurisdictions and has been litigated in at least one U.S. federal case (Jarrett v. United States).

Institutional miners have additional compliance obligations around depreciation schedules for ASIC hardware, which the IRS has generally allowed to be depreciated over a five-to-seven year useful life under MACRS, and around the classification of hosting arrangements (owned facility versus colocation) for balance sheet treatment.

## Cloud Mining and Fraud Risk

A persistent category of consumer harm involves "cloud mining" services that sell contracts entitling buyers to a share of hash rate allegedly operated by the provider. Because the hash rate is remote and unverifiable, cloud mining has been fertile ground for Ponzi structures.

ZachXBT, an on-chain investigator, published accusations in 2026 that BlockDAG — which had promoted itself as a mining project — was operated by a founder who allegedly extracted $350 million from retail investors before pivoting the project to a casino venture. The allegations illustrate a recurring pattern: mining's legitimate capital intensity makes it easy for fraudulent operations to claim that investor funds are tied up in hardware procurement or hosting contracts while actually being misappropriated.

Due diligence for any cloud mining offer should include verifiable proof of hash rate (ideally via a mining pool dashboard), clarity on electricity costs that would make the advertised returns plausible, and independent identification of the operating company.

## Outlook

Proof-of-work mining's long-term trajectory is shaped by three forces pulling in different directions: halving cycles that mechanically compress block rewards every four years, long-run transaction fee growth that Bitcoin's designers intended to eventually replace subsidies, and the ongoing regulatory and energy pressure that determines where mining can operate at scale.

The AI compute pivot represents a genuine optionality for mining infrastructure operators, but it also introduces new competitive dynamics against hyperscalers and specialized AI data center developers. Whether companies like TeraWulf, IREN, and Bit Digital can successfully straddle both markets — or whether they ultimately choose one — will shape how "mining company" is defined by the end of the decade.

DeFi liquidity mining is likely to become less central as protocols mature and achieve sustainable fee revenue, but token emissions as a bootstrapping mechanism are probably permanent fixtures of the landscape for new launches.

The regulatory environment is moving toward greater clarity in the United States, with the 2026 Congressional drafts suggesting that mining income, staking rewards, and related activities will receive explicit statutory treatment rather than relying on decades-old IRS guidance applied by analogy. How those rules land will meaningfully affect where mining operations are domiciled and how DeFi protocols structure their reward programs.
