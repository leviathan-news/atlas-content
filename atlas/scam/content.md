Deceptive schemes designed to separate crypto holders from their funds have cost victims billions of dollars annually, making fraud one of the most persistent threats facing anyone who participates in digital asset markets.

---

Cryptocurrency's core properties—irreversible transactions, pseudonymous addresses, global reach, and no central authority to reverse a transfer—make it an attractive vehicle for criminals. Unlike a fraudulent credit card charge, a misdirected crypto payment cannot be recalled by a bank. That asymmetry sits at the heart of every scheme discussed below.

## A Taxonomy of Crypto Fraud

No single technique dominates. Fraudsters adapt to whatever combination of technology and psychology offers the lowest resistance, and the landscape shifts constantly. Broadly, schemes fall into a handful of recurring categories:

- **Investment fraud**: fake platforms, Ponzi structures, and "yield" schemes that pay early participants with later victims' money
- **Phishing and impersonation**: spoofed websites, fake customer-support contacts, and lookalike communications designed to harvest credentials or transfer approvals
- **Social engineering**: relationship-based manipulation ("pig butchering"), romance scams, and confidence tricks that build trust before a financial ask
- **On-chain exploitation**: smart contract manipulation, fake token liquidity, and MEV-adjacent attacks that target protocol mechanics rather than people directly
- **AI-augmented fraud**: synthetic voice, deepfake video, and large-language-model-generated correspondence that erodes the last line of human verification

These categories overlap. A pig-butchering operation, for example, typically begins with social engineering, transitions to an investment fraud premise, and often ends with an approval-phishing step to drain the victim's wallet.

## Investment Fraud: The Largest Loss Category

By dollar volume, fake investment platforms consistently rank as the most damaging class of crypto fraud. The FBI's Internet Crime Complaint Center (IC3) has tracked investment fraud as the leading category of crypto-related losses for several consecutive years, with reported figures running into the billions annually—figures widely understood to represent a fraction of actual losses because most victims never file a report.

The template is durable: a platform promises outsized, low-risk returns; early "investors" see profits (funded by incoming deposits, not real trading); withdrawal requests are refused or require ever-larger "tax" or "fee" payments; eventually the operators disappear.

HyperFund, a scheme that reached at least $1.8 billion before collapsing, followed exactly this script. One of its promoters, known publicly as "Bitcoin Rodney," pleaded guilty to charges stemming from his role in recruiting participants. HyperFund marketed itself as a crypto mining reward program and attracted victims globally by promising returns of up to 0.5 percent daily. No sustainable mining operation could support those numbers; the math required a constant stream of new money.

## Social Engineering and Pig Butchering

"Pig butchering"—a translation of the Chinese term *shā zhū pán*—describes a prolonged confidence scheme in which fraudsters invest weeks or months cultivating a relationship with a target before steering them toward a fake investment platform. Contact often begins on dating apps, WhatsApp, or LinkedIn; the fraudster poses as a successful investor and gradually introduces the target to a platform they control.

On-chain investigator ZachXBT regularly surfaces the downstream money flows from these operations. In one documented cluster, he traced 5.73 BTC frozen at the exchange Changelly back to a scam network responsible for losses exceeding $1 million. In a separate case, he recovered $475,000 in frozen Bitcoin tied to social engineering scams targeting elderly Americans—the trail surfaced only because a suspected money mule messaged him directly, apparently unaware of his role in the broader scheme.

These operations are frequently run out of scam compounds in Southeast Asia, often staffed by trafficking victims forced to work as online fraudsters. In 2024 and 2025, the DOJ and FBI executed coordinated seizures that recovered 127,000 Bitcoin from networks linked to forced-labor compounds—at the time described as the largest asset seizure in U.S. history. Coinbase has separately documented its cooperation with law enforcement to disrupt criminal networks operating out of the same region, having frozen over $3 million in potentially fraudulent transactions and assisted investigations that identified specific compound operators.

## Approval Phishing: Stealing Without a Password

A technically distinct category has grown sharply as more users interact with DeFi protocols: approval phishing. Here, no password is stolen. Instead, the victim is tricked into signing a blockchain transaction that grants a malicious address unlimited permission to transfer tokens from their wallet.

The mechanics exploit a legitimate Ethereum standard (ERC-20's `approve` function) that allows users to authorize third-party contracts to move tokens on their behalf—necessary for decentralized exchange interactions. Fraudsters create fake minting pages, fake airdrop claims, or impersonate legitimate DeFi platforms to get victims to sign approval transactions. Once approved, the attacker can drain the wallet at any point, often waiting until a favorable moment.

Security researchers have noted a significant increase in approval phishing campaigns. The attack is effective partly because the victim sees a transaction confirmation screen that looks similar to ordinary DeFi interactions; many users do not carefully verify what permissions they are granting. Hardware wallets and permission-review tools like Revoke.cash can mitigate exposure, but awareness remains low among newer participants.

## Exchange Spoofing and Impersonation

Established exchange brands carry trust built over years—and fraudsters exploit that directly. In one prominent case, Indian authorities filed charges against eight defendants allegedly involved in a $20 million scheme in which operators impersonated Coinbase, creating convincing fake support channels and interfaces to extract credentials and funds from victims who believed they were interacting with the legitimate platform.

Google recently sued a Chinese criminal organization it alleged was running Gemini AI-branded phishing campaigns—fake pages and communications leveraging the reputation of a major AI product to establish credibility before requesting wallet access or credentials. The lawsuit underscores how quickly criminals adapt to whatever brand name carries the most public recognition.

Spoofing attacks frequently begin with search engine ads or social media posts. A user searching for a wallet recovery tool, a specific DeFi protocol, or exchange support may click a paid advertisement that leads to a pixel-perfect replica of a legitimate site. The FBI regularly issues warnings about this vector; users who type URLs directly rather than following search results or links substantially reduce their exposure.

## On-Chain Exploitation: When the Code Is the Attack Surface

Not every crypto fraud is aimed at an individual wallet holder. Some target protocol mechanics directly.

Jaredfromsubway.eth became one of the best-known addresses in Ethereum's MEV (maximal extractable value) ecosystem—an automated sandwich bot that profited by front-running ordinary traders. In a demonstration of the ecosystem's dark irony, the operator behind the bot was later drained of approximately $7.5 million through a fake token liquidity scam. The attack used a pattern where fraudsters created tokens with manipulated liquidity pools designed to look profitable to automated arbitrage systems; when the bot interacted with the pool, a hidden mechanism siphoned the funds.

The incident illustrates that on-chain sophistication does not guarantee safety. Automated systems that process millions of transactions can be more vulnerable to targeted bait than ordinary users, because they are designed to act on apparent opportunity without human verification.

## AI's Role in Scaling Fraud

Artificial intelligence has begun to lower the labor cost of running scams at scale. Large language models produce fluent, grammatically correct messages in any language, eliminating the telltale errors that once helped recipients identify phishing attempts. Synthetic voice cloning allows fraudsters to impersonate known individuals in audio messages. Deepfake video has been used in at least documented cases to impersonate executives during video calls.

For crypto fraud specifically, AI enables fraudsters to maintain many more simultaneous "relationships" in pig-butchering campaigns—a single operator can manage dozens of targets where manual effort would limit them to a handful. It also enables rapid creation of credible-looking fake platforms, complete with fabricated trading history and customer testimonials.

Law enforcement and the private sector are developing detection tools in response. Google's suit against the group running Gemini-branded phishing campaigns signals that major technology companies are beginning to treat AI-powered fraud as a direct legal and reputational threat, not merely a nuisance.

## The Regulatory and Legislative Response

Governments are moving, though not always at the pace the scale of losses demands. U.S. lawmakers have called for a coordinated federal response to crypto theft and fraud, noting that current enforcement is fragmented across the FBI, FTC, DOJ, SEC, CFTC, and state attorneys general. Delaware lawmakers advanced legislation to ban or heavily restrict crypto ATMs after the state recorded $26.9 million in crypto scam losses in 2025 alone—ATMs are a common cash-out mechanism for phone-based fraud targeting older Americans.

The FBI has made crypto-related financial crime an enforcement priority. High-profile operations, including the recovery of funds from Southeast Asian scam compounds, demonstrate law enforcement's increasing technical capability to trace blockchain flows even through mixing services and cross-chain bridges. ZachXBT and other independent on-chain investigators have become informal partners in this effort, publicly documenting fund flows that eventually lead to formal seizures.

Industry participants are also acting. Coinbase has published details of proactive monitoring programs that flag unusual transaction patterns and freeze funds pending investigation. TRM Labs and similar blockchain analytics firms provide the surveillance infrastructure that both exchanges and law enforcement rely on to connect wallet addresses to real-world actors. At major international events—the FIFA World Cup being a recurring example—TRM and other firms issue specific warnings about event-themed scams targeting fans, ranging from fake ticket NFTs to fraudulent merchandise storefronts.

## Protecting Yourself

No single measure eliminates risk, but the following reduce exposure materially:

**Verify before signing.** Every wallet transaction that requests token approvals should be reviewed carefully. If you did not initiate the interaction, reject it.

**Use direct navigation.** Type exchange and protocol URLs directly rather than following links from emails, social media, or search results. Bookmark the sites you use regularly.

**Treat unsolicited contact as suspect.** Legitimate exchanges, protocols, and government agencies do not contact users via Telegram DM, WhatsApp, or social media to resolve account issues. No legitimate platform will ask for your seed phrase.

**Audit existing approvals.** Tools that display all outstanding token approvals on your connected address allow you to revoke permissions you no longer need or recognize.

**Independently verify investment claims.** Promised returns that exceed what legitimate yield sources offer—even in high-yield DeFi—are a reliable signal of fraud. Verify that trading platforms have regulatory registration before depositing.

**Report losses.** Underreporting is significant in this space. FBI IC3 (ic3.gov) and relevant national authorities maintain databases that help identify patterns and direct resources. Early reports of frozen funds sometimes enable partial recovery.

## Outlook

The trajectory of crypto fraud follows the adoption curve of the technology itself. As blockchain-based assets move further into mainstream financial activity—institutional custody, ETF products, payment integrations—the pool of potential victims grows and so does the sophistication of attacks. AI will make social engineering faster, cheaper, and harder to detect by traditional means. Regulatory frameworks are emerging but remain incomplete in most jurisdictions.

The most durable countermeasure is structural: the industry's gradual shift toward more legible transaction interfaces, user-facing permission explanations, and on-chain monitoring that can flag anomalous approvals before funds leave a wallet. Combined with steadily improving law enforcement capability to trace and seize blockchain assets, these tools create real friction for criminals—though they do not eliminate the risk. For individual participants, skepticism remains the most effective defense.

---
