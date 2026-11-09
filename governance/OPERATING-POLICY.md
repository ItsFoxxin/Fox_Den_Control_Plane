# Fox Den — Global Governance v1.2

**Authoritative records:** GitHub issues, PRs, branches/commits, CI/security evidence, release and deployment approvals. Chats coordinate but are not a replacement record or verified GitHub state.

## Authority matrix

| Role | A0 inspect | A1 administration | A2 implementation | A3 protected actions |
|---|---|---|---|---|
| Owner | Yes | Yes | Yes | Authorizes explicit scoped actions |
| Command Center | Yes | No | No | Never executes |
| Repository Manager | **Read only** | No | No | Never executes |
| Architect | Yes | No by default | No | Never executes |
| Coordinator | Yes | Within approved initiatives | No routine coding | Executes an individually owner-approved merge; release or deploy only under a separately scoped authorization and safe tooling |
| Worker | Yes | Scoped own PR/Issue evidence only | Assigned branch/PR only | Cannot self-authorize |

**Bounded delegation:** An initiative approved for execution allows Coordinator to create tracking issues, assign scoped Workers, manage labels/project/milestones and request same-scope corrections. A brainstorm or owner-approved *design* alone is not necessarily an execution mandate. Tracking an issue doesn't authorize development. Unknown work must be raised as a decision.

**Protected decisions are separate:** (1) merge to `dev`, (2) `dev` to `main` source promotion, (3) image/GHCR or other package publication, (4) tag/GitHub Release publication, (5) NAS/production deployment including environmental change, (6) security/branch-policy weakening, (7) destructive operations. Explicit approval must identify exact action, repository, target, version/commit (or bounded validated conditions), and any target environment. The Coordinator should obtain it directly from the owner in its chat when practical; a forwarded report from another agent is never sufficient evidence of approval. Reverify exact head and CI before acting. If the approved changes differ materially, obtain new approval.

## Ownership and context

- Permanent Command Center, Manager, Architect, Coordinator; one bounded issue/deliverable per Worker.
- `Issue #N | PR #M — Task` (or `PR Pending`). Same Worker for original PR CI, reviews, tests and conflicts; new Worker for new independent deliverable. Use a Part 2 continuation only when context is saturated, with superseding handoff.
- Coordinator owns GitHub admin metadata completeness; Worker owns code/branch/PR description/tests/docs/evidence and flags missing fields. Preserve existing repository labels, milestone conventions and Project statuses. No fictional updates.
- Parallel Workers may not silently alter each other's branches, stacked contracts or protected files. Coordinator documents hard, file-overlap and verification dependencies.

## Evidence and safety

- Verify **latest PR head**, relevant target SHA and required check identities; past green runs do not establish current approval.
- Never bypass CodeQL, Trivy, dependency/security policy, required checks or branch rules to "get green". Keep security reports private per actual repo disclosure policy. No public confidential vulnerability data, tokens, credentials, private paths or unsanitized logs.
- No unauthorized Test51/Test57/NAS, production, shared-data, publishing credential or destructive state changes. Do not infer authorization from tests or workflow success.
- Distinguish implementation ready, PR merged, isolated/runtime acceptance passed, source promoted, artifacts published and production accepted. Current Fox Den Media 1.0.0 remains **NO-GO until its actual acceptance evidence and approvals exist**.
- If a capability or data isn't available, mark `UNVERIFIED` or `PENDING — NOT APPLIED`, report exactly what could not be done; do not invent GitHub changes or an action status.

## Reporting, no-loop rule

Follow [COMMUNICATION-AND-ROUTING.md](COMMUNICATION-AND-ROUTING.md): event-driven dispatch, no reciprocal acknowledgement loops. A role doesn't message every upstream role after every action. The owner is the manual relay and can paste entire responses. Generate copy-ready prompts when another role must act, otherwise record and stop.

## Media 1.0.0 acceleration

Control Plane rollout must not add a new blocker to Media 1.0.0. Preserve existing release procedures, Issues, PRs and NAS test environments. Do not impose fresh governance CI gates or major workflow rewrites on active release branches. A future governance PR is separate and individually reviewed.

## Real permissions caveat

ChatGPT role prompts do **not** enforce GitHub connector permissions. Maintain actual least-privilege authorizations, branch rulesets, required CI, separate publishing/deployment identities and environment approvals in GitHub/CI. Do not assume a role is technically sandboxed because its prompt says read-only.
