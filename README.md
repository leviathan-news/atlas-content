# Leviathan Atlas content mirror

This repository is a deterministic public mirror of the currently published
Leviathan Atlas territories. It is a proposal surface, not a Git-backed CMS:
the canonical record remains Leviathan's audited PostgreSQL publication state.

## Public-history contract

Every territory that is active and published at an export is represented under
`atlas/<slug>/`. The initially stubbed Convex and Resupply territories are not
included. If a mirrored territory is later held, stubbed, drafted, or
unpublished, its generated directory will be removed in a later commit. Its
earlier body and the removal itself remain ordinary public Git history; this
repository does not promise historical redaction.

## Files

- `atlas/<slug>/content.md` is the pristine editorial body.
- `atlas/<slug>/metadata.json` holds the bounded, contributor-proposable
  summary and citation list.
- `atlas/<slug>/snapshot.json` is generated reference state and is not
  contributor-editable.
- `catalog.json` and `schema/` are generated repository-wide indexes and
  schemas.

## Pull requests

Pull requests are public, attributable editorial proposals. They do not publish
content, create a database revision, verify an identity, or give a contributor
authority over risk, history, or editorial framing. See
[CONTRIBUTING.md](CONTRIBUTING.md) for the bounded proposal format.

There are no GitHub Actions, self-hosted runners, executable contribution
scripts, secrets, Issues, or Discussions in this repository. Do not include
confidential information, credentials, or security reports in a pull request.

## Rights

Atlas editorial content is publicly inspectable but remains copyrighted by
Leviathan News; see [LICENSE-CONTENT](LICENSE-CONTENT). The repository schemas
and helper materials are available under [LICENSE-CODE](LICENSE-CODE).
