# The Leviathan Atlas

[![The Leviathan Atlas — a living map of crypto](https://digest.leviathannews.xyz/content/images/2026/07/ghost-feature-1200x630.png)](https://digest.leviathannews.xyz/the-leviathan-atlas-a-living-map-of-crypto/)

**[Explore the live Atlas →](https://leviathan.news/atlas)** ·
**[Read the launch story →](https://digest.leviathannews.xyz/the-leviathan-atlas-a-living-map-of-crypto/)**

The Leviathan Atlas is a living map of crypto, drawn from everything
[Leviathan News](https://leviathan.news) has ever covered. At launch it
charted [657 territories](https://digest.leviathannews.xyz/the-leviathan-atlas-a-living-map-of-crypto/)
— protocols, chains, concepts, and the people who move them — spanning
3.6 million words of explainer content distilled from 53,757 curated
articles and joined by 5,288 cross-links between territories.

Curation is compression. A headline decays in a day; editorial judgment
accumulates. Every territory is a long-form explainer with live reporting
attached, so fresh coverage keeps redrawing the map instead of piling up
beside it. And the cartography is done in the open: corrections are
logged, credited, and attributed — never silently rewritten.

This repository is that map's public, diffable mirror.

## What this repository is

A deterministic public mirror of the currently published Atlas
territories. It is a proposal surface, not a Git-backed CMS: the
canonical record remains Leviathan's audited PostgreSQL publication
state, and the live pages remain the reading surface. Each mirrored
territory links back to its live page at
`https://leviathan.news/atlas/<slug>`.

A few places to drop anchor:

| Territory | Live page |
|---|---|
| [Yearn](atlas/yearn/) | [leviathan.news/atlas/yearn](https://leviathan.news/atlas/yearn) |
| [Curve](atlas/curve/) | [leviathan.news/atlas/curve](https://leviathan.news/atlas/curve) |
| [Ethereum](atlas/ethereum/) | [leviathan.news/atlas/ethereum](https://leviathan.news/atlas/ethereum) |
| [Stablecoins](atlas/stablecoins/) | [leviathan.news/atlas/stablecoins](https://leviathan.news/atlas/stablecoins) |

The full roster lives in [`catalog.json`](catalog.json), one directory
per territory under [`atlas/`](atlas/).

## Public-history contract

Every territory that is active and published at an export is represented
under `atlas/<slug>/`. If a mirrored territory is later held, stubbed,
drafted, or unpublished, its generated directory is removed in a later
commit. Its earlier body and the removal itself remain ordinary public
Git history; this repository does not promise historical redaction.

## Files

- `atlas/<slug>/README.md` is a generated navigation cover linking the
  live territory; it is not contributor-editable.
- `atlas/<slug>/content.md` is the pristine editorial body.
- `atlas/<slug>/metadata.json` holds the bounded, contributor-proposable
  summary and citation list.
- `atlas/<slug>/snapshot.json` is generated reference state and is not
  contributor-editable.
- `catalog.json` and `schema/` are generated repository-wide indexes and
  schemas.

## Proposing an edit

The Atlas takes corrections seriously enough to make them public. Pull
requests here are public, attributable editorial proposals. They do not
publish content, create a database revision, verify an identity, or give
a contributor authority over risk, history, or editorial framing. See
[CONTRIBUTING.md](CONTRIBUTING.md) for the bounded proposal format.

There are no GitHub Actions, self-hosted runners, executable
contribution scripts, secrets, Issues, or Discussions in this
repository. Do not include confidential information, credentials, or
security reports in a pull request.

Beyond pull requests, the live Atlas accepts
[wallet-signed map requests](https://leviathan.news/atlas) for unmapped
territories, and comment-based corrections on every territory page.

## Rights

Atlas editorial content is publicly inspectable but remains copyrighted
by Leviathan News; see [LICENSE-CONTENT](LICENSE-CONTENT). The
repository schemas and helper materials are available under
[LICENSE-CODE](LICENSE-CODE).
