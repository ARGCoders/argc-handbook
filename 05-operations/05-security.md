# Security

ARGC's platform handles member data, evaluation records, and voting history. Access is scoped: members see what they need, nothing more. The backend is never exposed directly to the frontend. Credentials are not shared, hardcoded, or stored in version control. Security is not a feature added later — it is a constraint in the initial design.

## The Principle

Security in ARGC is not a compliance checklist. It is a design constraint: every system is built assuming it will be attacked, misused, or accessed by someone who should not have access.

This is especially true for the member platform, which holds contribution data and voting records that affect real membership outcomes.

## Access Model

**Public surface** — no authentication required. Handbook, events, public information.

**Member surface** — requires active ARGC membership and authentication via 42 Amman OAuth. Members see their own data and their node's aggregated data. They do not see other members' individual records.

**Node Leader surface** — Node Leaders see their node's full contribution records. They do not see records for other nodes.

**Admin surface** — Super Peers only. Full access to XP records, voting data, and member management. PocketBase admin access is held by Super Peers only and is not delegated.

## Specific Rules

**Credentials are never:**
- Shared via any communication channel
- Stored in a `.env` file that is committed to any repo
- Hardcoded in any source file

**The frontend never calls PocketBase directly.** All data requests from the browser go through the Next.js proxy layer. This boundary is enforced at the architecture level and is not bypassed under any circumstances.

**Admin access is not delegated.** If a Super Peer leaves ARGC, their PocketBase admin credentials are rotated before they are removed from the platform. There are no exceptions.

**Platform schema changes are reviewed.** No production schema change is applied without a written description of what is changing, reviewed by at least one other Super Peer.

## Incident Response

If you discover a security issue — a credential in a repo, unauthorized access, a data exposure — you report it immediately to Super Peers via direct message. You do not post it in a shared channel.

The response steps:
1. Super Peer assesses severity within 1 hour
2. If credentials are involved, they are rotated immediately
3. Affected members are notified of any data exposure within 24 hours
4. A written incident report is produced and stored on the platform

Security incidents are not punished when reported in good faith. They are punished when hidden.

---

[← Back to Handbook](../README.md)
