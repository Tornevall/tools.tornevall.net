# Agent guidance for tools.tornevall.net

This repository is the public support and release-information front for Tornevall Tools.

## Repository purpose

- Keep this repository public and safe for end users.
- Users may report bugs and feature requests through GitHub Issues here without exposing the implementation repository or infrastructure.
- Application source code, infrastructure, deployment configuration, credentials, internal architecture, operational details, private endpoints, server names, filesystem paths, logs, database details, worker internals, and other implementation material must never be added here.
- The implementation source of truth is the private `Tornevall/toolsApi` repository.

## Allowed repository content

The repository is intentionally documentation-only. Keep tracked content limited to:

- `README.md` - public project/support entrypoint.
- `CHANGELOG.md` - public user-facing history synchronized from released or otherwise user-visible ToolsAPI changes.
- `AGENTS.md` - these internal repository-handling rules.

Do not add application code, build assets, package manifests, workflows, issue automation, infrastructure files, generated artifacts, or implementation documentation unless the operator explicitly changes this repository contract.

## Public issue intake and transfer workflow

When a bug report or feature request in this repository is selected for active work:

1. Read the full public issue and preserve its user-visible problem statement, acceptance context, and public issue URL.
2. Search `Tornevall/toolsApi` for an existing issue or active PR covering the same work. Reuse existing work when appropriate and do not create duplicates.
3. If no matching implementation issue exists, create one in `Tornevall/toolsApi`. The internal issue must contain the relevant public report details and a backlink to the public issue, while following ToolsAPI rules about secrets and internal data.
4. Only after the implementation issue exists and work is actually being taken up, add a closing comment to the public issue stating that the report is now **in progress** and has been transferred to the internal implementation tracker.
5. Close the public issue after that note. Do not expose a private implementation issue URL, private repository contents, infrastructure details, or other internal information in the public closing comment.
6. Continue implementation, verification, documentation, review, conflict checks, and PR work in `Tornevall/toolsApi` under that repository's applicable `AGENTS.md` rules.
7. User-visible completed changes should later be reflected in this repository's `CHANGELOG.md` without leaking internal implementation details.

A public report remains open while it is only waiting in the intake queue. Do not close it merely because it has been read or triaged.

## Website and support linkage

- Keep the repository visibly connected to the live Tools site without pretending to be the application source repository.
- `README.md` should link to `https://tools.tornevall.net/`, the public service catalogue at `https://tools.tornevall.net/services`, and the built-in suggestion board at `https://tools.tornevall.net/suggestions`.
- GitHub Issues in this repository are the public bug/feature-request intake. The built-in suggestion board remains a complementary feedback route.
- Public text must make clear that a public issue closed with an **in progress** handoff note has moved to internal implementation work and is not necessarily released yet.

## Public changelog rules

- Keep `CHANGELOG.md` user-facing and implementation-agnostic.
- Record released or otherwise user-visible behavior changes from ToolsAPI.
- Do not copy private engineering notes, internal diagnostics, infrastructure changes, secret/configuration values, or implementation paths into this repository.
- Prefer plain descriptions of what changed for users and administrators.
- Keep the changelog aligned with the canonical ToolsAPI engineering changelog and public release communication where applicable, but this repository never replaces those sources.

## Change discipline

- Read this file before modifying the repository.
- Preserve the documentation-only boundary.
- Use branches and pull requests after the initial repository bootstrap.
- Before declaring a PR ready, inspect current review comments where available and check mergeability/conflicts against the target branch.
- Documentation-only changes normally need content review and link/Markdown sanity checks rather than expensive CI.
