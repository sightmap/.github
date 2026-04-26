# Governance

This document describes how decisions are made in the Sightmap project. It is deliberately simple and will evolve as the project grows.

## Stewardship

Sightmap is currently **stewarded by the [Subtext](https://subtext.fullstory.com) team at Fullstory**. The Subtext team funds development, employs the current maintainers, and retains final decision authority over the spec and its reference implementations.

Stewardship is not ownership of the ideas. The spec is MIT-licensed and will remain so. Anyone can fork it, build on it, or implement it. Stewardship means we take responsibility for:

- Keeping the spec coherent across SDKs and versions
- Reviewing proposals in a timely way
- Maintaining the public artifacts (website, JSON Schema, reference examples)
- Enforcing the [Code of Conduct](CODE_OF_CONDUCT.md)

As the project matures and the contributor base grows, we expect to move toward a more distributed governance model. This document will be updated to reflect that when it happens.

## Roles

### Contributor

Anyone who opens an issue, files a PR, participates in a discussion, or otherwise contributes to the project.

No formal onboarding. Start by reading [`CONTRIBUTING.md`](CONTRIBUTING.md).

### Maintainer

Listed in [`MAINTAINERS.md`](MAINTAINERS.md). Maintainers have commit access and PR approval rights. They are responsible for:

- Triaging incoming issues and PRs
- Reviewing and merging contributions
- Shepherding SEPs through the [process](seps/README.md)
- Cutting releases
- Upholding the Code of Conduct
- Representing the project publicly

Becoming a maintainer: a sustained history of high-quality contributions + nomination by an existing maintainer + consensus of existing maintainers. There is no fixed contribution threshold — judgment call. We prefer to add maintainers deliberately over adding them often.

Stepping down: any maintainer may step down at any time by opening a PR to `MAINTAINERS.md`. Maintainers who are inactive for 12+ months without explanation may be moved to emeritus by consensus of the active maintainers.

### Steward

The Subtext team at Fullstory. The steward:

- Holds the GitHub organization and domain ownership
- Breaks deadlocks on significant decisions when maintainers cannot reach consensus
- Ultimately decides what ships in an official release

In practice, day-to-day decisions are made by maintainers. Steward authority is a backstop, not a daily mechanism.

## How decisions get made

### Everyday changes

Typo fixes, wording polish, small website tweaks, small example additions, dependency bumps: any maintainer may review and merge. One approval is sufficient.

### Non-trivial code or docs changes

Two maintainer approvals recommended, one required. The second reviewer exists to spread context across the team, not to gate the change.

### Spec changes

Any change to the semantics, schema, or behavior of the Sightmap spec goes through the [SEP process](seps/README.md). In short:

1. Draft SEP as a PR.
2. Discussion period (minimum 7 days for minor changes, 14 days for anything that affects the JSON Schema or existing sightmaps).
3. All maintainers have a chance to weigh in. Explicit approvals from at least two maintainers required. Any maintainer may block — blocks must be accompanied by a concrete objection.
4. If consensus is reached, the SEP is accepted and implementation PRs follow.
5. If maintainers deadlock, the steward decides. This should be rare.

Breaking changes (anything that makes a previously valid sightmap invalid) require broad consensus. See [`spec/VERSIONING.md`](spec/VERSIONING.md) for what constitutes a breaking change.

### Decisions about governance itself

Changes to this document, to `MAINTAINERS.md`, or to the SEP process require:

- A PR with a clear rationale
- Approval from the steward
- Approval from a majority of active maintainers
- Public announcement in Discussions once merged

## Transparency

- All significant decisions are visible as GitHub issues, PRs, or SEPs. Private Slack threads are fine for logistics but should not be where substantive decisions get made.
- Maintainer meetings, if they happen, are summarized publicly.
- Deviations from this process should themselves be discussed publicly.

## Conflict resolution

Disagreements that can't be resolved on a thread:

1. Take it to a Discussion with a clear written summary of positions.
2. If still unresolved, ask the steward to weigh in.
3. The steward's decision is final for that specific question.

Repeated conflicts involving the same contributors may indicate a Code of Conduct concern. In that case, see [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).

## Changes to this document

This document is itself subject to the process it describes. Propose changes via PR.
