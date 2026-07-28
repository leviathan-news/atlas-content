Tornado Cash is an Ethereum-based, non-custodial privacy protocol that uses zero-knowledge cryptography to sever the on-chain link between depositing and withdrawing wallets — making it both a legitimate financial-privacy tool and the most heavily used money-laundering infrastructure in the history of decentralized finance.

---

## What Tornado Cash Actually Does

Launched in 2019, Tornado Cash operates as a set of immutable smart contracts deployed on Ethereum (and later on BNB Chain, Polygon, Avalanche, and Optimism). Users deposit a fixed denomination of ETH or ERC-20 tokens — such as 0.1 ETH, 1 ETH, 10 ETH, or 100 ETH — and receive a cryptographic "note," a zero-knowledge proof of deposit. They can then withdraw the same amount to any fresh wallet at any later time, with no on-chain connection to the original depositor.

The privacy mechanism relies on zkSNARKs (zero-knowledge succinct non-interactive arguments of knowledge). The contract maintains a Merkle tree of deposit commitments. When a user withdraws, they prove knowledge of a valid leaf in that tree without revealing which one — effectively making the source of funds untraceble without off-chain analytics.

This is technically elegant and has legitimate applications: employees paid publicly on-chain, donors who want anonymity, and users in surveillance states all have reasonable privacy interests. The problem is scale. Blockchain analytics firm Chainalysis has documented that a substantial fraction of Tornado Cash volume — at various points estimated above 30% — originated from sanctioned entities, protocol exploits, and criminal wallets.

## The OFAC Sanctions and Their Legal Novelty

In August 2022, the U.S. Treasury's Office of Foreign Assets Control (OFAC) sanctioned Tornado Cash under its authority to block property of foreign adversaries, citing its use by North Korea's Lazarus Group to launder over $455 million stolen from Ronin Network. The action was legally unprecedented: for the first time, OFAC sanctioned not a person or an organization, but a piece of open-source software and its associated smart contract addresses.

The move immediately froze front-end access through providers like Infura and Alchemy and removed the protocol's GitHub repository. It also raised a fundamental constitutional question: can the U.S. government sanction code itself?

The Coin Center advocacy organization filed a lawsuit arguing it cannot. Their position — that publishing cryptographic code is protected First Amendment speech — gained traction in the Fifth Circuit Court of Appeals in 2024, which ruled that the immutable smart contracts could not be sanctioned as "property" of a foreign national. The mutable components, including the governance token and the GitHub repositories, remained sanctionable. Treasury updated its sanctions list in response, but the core legal dispute over code-as-speech continued to reverberate through subsequent prosecutions. Coin Center has extended that argument explicitly to challenge not only the Tornado Cash case but also the conviction of Samourai Wallet developers on similar grounds.

## How Hackers Use It — and Why It Keeps Appearing in Exploit Postmortems

The protocol's utility for obscuring stolen funds is precisely what makes it a recurring character in DeFi exploit reports. Across the coverage of recent incidents, the pattern is consistent: an attacker drains a protocol, bridges ETH to a fresh wallet, and routes it through Tornado Cash in tranches to break the trail before attempting to cash out through centralized exchanges or OTC desks.

Recent examples illustrate the breadth of the problem. The KyberSwap exploiter laundered 2,900 ETH (approximately $6.8 million) through Tornado Cash after a $47 million reentrancy attack. A compromised Gnosis Safe multisig drained Aave progressively, laundering 6,300 ETH — roughly $19.4 million — through the mixer as the attack unfolded in real time. The Fluid protocol suffered a Merkle proof exploit where an attacker drained 125,000 FLUID and 51,900 GHO tokens and immediately routed proceeds through Tornado Cash while the team quietly paused claims without public disclosure. In a separate, physically coerced theft, a Kraken and Coinbase user lost $6.7 million, with $5.3 million of that routed through Tornado Cash. Even exploits on other chains frequently bridge to Ethereum specifically to access Tornado Cash's liquidity depth — the Polkadot ecosystem saw $269,000 laundered this way, and a BNB Chain attacker drained over $3.1 million from GANA Payment before doing the same.

The reason Tornado Cash remains the dominant laundering venue even after sanctions, even after front-end takedowns, is that the core contracts are immutable and live on a permissionless blockchain. No entity can delete them. Blocking front-end access inconveniences casual users; determined attackers interact directly with the contract addresses.

## The Prosecutions: Roman Storm and the Developer Liability Question

The U.S. Department of Justice moved beyond OFAC's civil sanctions to pursue criminal liability against the humans behind the protocol. The most consequential ongoing case is that of Roman Storm, a U.S.-based co-founder of Tornado Cash, who was arrested in August 2023 and charged with conspiracy to commit money laundering, conspiracy to violate sanctions, and operating an unlicensed money-transmitting business — charges that collectively carry decades in prison.

Storm's trial in late 2024 ended in a partial verdict: the jury hung on two of the three charges, convicting him on operating an unlicensed money-transmitting business. His legal team subsequently filed motions to overturn that conviction and to dismiss the remaining charges before a potential retrial. Storm argued, among other things, that Tornado Cash's smart contracts could not constitute a "money-transmitting business" because the contracts are autonomous software — he was a developer, not an operator who controlled customer funds or could block transactions.

The prosecution's position, maintained even under the Trump administration's DOJ, is that Storm was aware the protocol was being used for sanctions evasion and money laundering, that he failed to implement controls, and that the business model specifically required operating without registering as a money services business with FinCEN. The U.S. Attorney for the Southern District of New York formally rejected Storm's dismissal motions in April 2026, and prosecutors subsequently characterized his copyright defense as "outright misdirection," signaling intent to retry the hung charges.

The trial itself surfaced notable procedural drama. A presiding federal judge pointedly rebuked a prosecutor during a pretrial hearing, and a Chainalysis expert witness reportedly invoked Fifth Amendment protections to avoid self-incrimination — an unusual development in a case built substantially on blockchain analytics testimony.

In the Netherlands, Tornado Cash's other co-founder, Alexey Pertsev, was convicted by a Dutch court in May 2024 of money laundering and sentenced to over five years in prison. Roman Semenov, a third co-founder, remains at large and was indicted in the U.S.

## The Crypto Industry's Response

The Storm prosecution has become a flashpoint for the broader question of developer liability in open-source software. Over 65 crypto advocacy groups formally urged the Trump administration to halt the Tornado Cash retrial, arguing that open-source code is not a crime and that prosecuting developers for how third parties use their software sets a precedent that would chill legitimate development across the industry.

Financial backing for the defense has come from unexpected directions. The Solana Policy Institute committed $500,000 toward legal defenses for both Storm and Pertsev. An Ethereum developer known as "Fede's intern," who was held in Turkish detention over alleged Ethereum misuse, pledged another $500,000 to Storm's defense upon release. Even Dragonfly Capital, an early Tornado Cash investor, saw DOJ scrutiny — before prosecutors ultimately backed away from pursuing charges against the firm.

These developments have forced a public recalibration inside the DOJ itself. Matthew Galeotti, a senior DOJ official, stated publicly that "writing code without ill intent is not a crime," and that prosecutors would focus on developers who knowingly enable fraud, sanctions evasion, or money laundering — not those simply writing software. While that framing was welcomed by parts of the industry, defense attorneys noted that the Tornado Cash prosecution was precisely the test case for where that line falls, and the DOJ had not dropped it.

## The Privacy-vs.-Compliance Tension

Tornado Cash sits at the intersection of two genuine goods that current regulatory frameworks have not reconciled. Financial privacy is a recognized human right in most democratic societies. On-chain transactions are pseudonymous, not anonymous — every transfer is visible to anyone with a blockchain explorer. For individuals operating in countries with authoritarian financial surveillance, or journalists, activists, or anyone making politically sensitive donations, the ability to transact privately has real value.

At the same time, the same properties that make a mixer useful for those individuals make it useful for state-sponsored hackers funneling stolen cryptocurrency, ransomware operators converting extortion payments, and exploit developers liquidating DeFi protocol drains. The Lazarus Group's documented use of Tornado Cash to launder hundreds of millions from protocol exploits is not hypothetical.

The legal and technical question that neither prosecutors nor defenders have fully answered is whether the appropriate response is to hold the developer criminally liable for the downstream acts of independent users, or whether the analogy is closer to prosecuting the designer of a lock-picking tool because burglars use it. Coin Center's First Amendment argument frames writing and publishing code as expressive speech; the DOJ's money-transmitter theory frames running an accessible financial service as a business that triggers regulatory obligations regardless of the underlying technology.

## How Blockchain Analytics Engages With Tornado Cash

Despite its privacy guarantees, Tornado Cash is not impenetrable to analysis. Chainalysis, Elliptic, TRM Labs, and similar firms have developed heuristics that can, under certain conditions, link deposits to withdrawals. These include timing analysis (correlating deposit and withdrawal timing), denomination analysis, and gas price patterns. In high-profile cases where law enforcement has access to metadata — IP logs from front-end providers, exchange KYC records, or cooperating witnesses — these statistical signals can be triangulated against known wallet activity.

The U.S. government's case against Storm relied partly on Chainalysis testimony about traced funds flows — which makes the reported Fifth Amendment invocation by a Chainalysis witness particularly consequential for the prosecution's retrial strategy.

## Outlook

The Tornado Cash saga is unlikely to resolve cleanly in the near term. On the legal front, Roman Storm faces a potential retrial on the two hung counts while simultaneously appealing his existing conviction. The outcome will have lasting implications: a conviction under the money-transmitter theory would establish that operating a non-custodial privacy protocol can constitute a federal crime; an acquittal or dismissal would push regulators toward legislative rather than prosecutorial solutions.

On the protocol level, Tornado Cash's smart contracts continue to function and will continue to attract both legitimate privacy-seeking users and criminal funds, because no authority can disable them. The policy challenge — building financial privacy tools that are resistant to surveillance while being resistant to large-scale abuse — remains unsolved. Successor protocols and regulatory sandboxes for privacy-preserving DeFi are under active discussion in both the EU and the U.S., but no jurisdiction has yet produced a workable legal framework that distinguishes the cases clearly.

What is clear is that Tornado Cash has permanently shifted how regulators, prosecutors, and developers think about the liability surface of open-source financial software — and the debate it triggered will outlast the protocol itself.

---
