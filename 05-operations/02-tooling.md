# Tooling

ARGC runs on a defined stack: Next.js for the platform frontend and proxy layer, PocketBase for the data backend, GitHub for all code and handbook content. Tools are chosen for reliability and maintainability, not novelty. The frontend never calls PocketBase directly — all requests go through the Next.js backend layer.

## The Stack

| Tool | Role | Notes |
|------|------|-------|
| **Next.js** | Frontend + API proxy | App Router. TypeScript. Tailwind CSS. |
| **PocketBase** | Backend + auth | Self-hosted on Railway. Admin access restricted. |
| **GitHub** | Version control + handbook | All repos under the ARGCoders org. |
| **Railway** | Hosting | Next.js platform and PocketBase both deployed here. |

## Why These Tools

The stack was chosen for three reasons:
1. **Operational simplicity** — fewer moving parts means fewer things to break and fewer people needed to maintain it.
2. **Member familiarity** — 42 Amman students come with JavaScript and Git. The stack does not require a learning curve before contributing.
3. **Reliability** — each tool in the stack has a track record. We are not running experiments on production infrastructure.

New tools are not added because they are interesting. A tool earns its place by solving a real problem that the existing stack cannot solve, reviewed and approved by the platform node.

## Rules Per Tool

### GitHub
- All work lives in the ARGCoders org. No personal forks for production work.
- Conventional Commits format is enforced on all repos.
- Main branches are protected. Nothing merges without review.
- Handbook content lives in `argc-handbook`. Platform code lives in `argc_platform`.

### PocketBase
- Admin credentials are not shared in chat or stored in any repo.
- The frontend never calls PocketBase directly. The Next.js proxy is not optional.
- Schema changes go through the platform node and are documented before they are applied.

### Railway
- Environment variables are set through the Railway dashboard, never in `.env` files committed to the repo.
- Deployments are triggered by pushes to main. No manual deployments from local machines except in an incident.

---

[← Back to Handbook](../README.md)
