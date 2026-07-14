# Platform

The ARGC platform is the technical infrastructure that makes the club's operations visible and accountable. It tracks XP, evaluations, node activity, and voting — and it has two surfaces: a member-facing layer restricted to active contributors, and a public layer open to the full 42 Amman student body. The platform is built and maintained by ARGC members under production standards.

## What the Platform Does

The platform is the source of truth for three things:
1. **Member records** — XP, tier, evaluation history, event participation
2. **Club operations** — node output, voting records, advancement cycle data
3. **Public presence** — handbook, events calendar, and information for students considering ARGC

Nothing tracked informally overrides the platform. If it is not on the platform, it did not happen for the purposes of advancement, voting, or accountability.

## Two Surfaces

**Member surface** — accessible only to active ARGC members after authentication. Contains XP data, node dashboards, evaluation logs, and voting interfaces. This surface is private.

**Public surface** — accessible to anyone. Contains the handbook, event listings, and general information about ARGC. This surface is the club's public face and must always be accurate and up to date.

## Architecture

The platform runs on:
- **Next.js** — frontend and API proxy layer
- **PocketBase** — backend data store and authentication
- **GitHub** — source control for all code and handbook content

The architecture enforces one rule: the frontend never communicates directly with PocketBase. All requests from the browser go through the Next.js proxy layer. This is a security boundary, not a preference — it is never bypassed.

## Development Standards

All platform work follows production standards:
- Conventional Commits format for all commits
- No force-pushes to main; no bypassing code review
- Features are complete before they are merged — no half-finished work in the main branch
- Documentation is updated in the same commit as the code it describes

The platform is maintained by ARGC's platform node. Contributions from other nodes are welcome through the standard pull request process.

---

[← Back to Handbook](../README.md)
