# Copy-ready handoff templates v1.2

## A. Command Center -> Coordinator for known, approved work

```md
FROM: Fox Den — Command Center
TO: <Repo> — Coordinator
TYPE: ACTION
REPOSITORY: owner/repo
AUTHORITY: Owner authorized implementation of <exact scope>; NOT merge/publish/deploy.
ISSUE/PR: <known refs, otherwise verify/search>
EVIDENCE: <verified GitHub facts, SHA, links, uncertainty>
OBJECTIVE: Reconcile existing assignments, maintain Issue/Project tracking and prepare complete independent Worker prompts for each authorized READY deliverable.
BOUNDARIES: Preserve current branches, no duplicates, no unrelated work, no protected actions.
REQUIRED OUTPUT: Separate COPY TO existing/new Worker prompts, or blocking condition / owner decision. No immediate report back to Command Center merely for dispatch.
NEXT ROUTE: Coordinator
```

## B. Manager -> Coordinator for new findings

```md
FROM: <Repo> — Manager
TO: <Repo> — Coordinator
TYPE: ACTION
REPOSITORY: owner/repo
ISSUE/PR: <references>
EVIDENCE: <source SHA, PR heads, check results, findings + uncertainties>
PRIORITY: <critical/high/normal; grounded explanation>
PREREQUISITES: <merge order, design, authorization, active Workers>
OBJECTIVE: Determine ready authorized work, correct registry/metadata, and produce per-Worker prompts as appropriate.
AUTHORITY: Read-only recommendation; check owner-approved initiative before starting new scope.
REQUIRED OUTPUT: Worker Dispatch Pack or explicit blocker/decision. Do not reply to Manager solely acknowledging receipt.
NEXT ROUTE: Coordinator
```

## C. Architect -> Coordinator after approval

```md
FROM: <Repo> — Architect
TO: <Repo> — Coordinator
TYPE: ACTION
DESIGN STATE: OWNER-APPROVED
IMPLEMENTATION AUTHORITY: APPROVED | NOT YET APPROVED
REPOSITORY: owner/repo
ISSUE: <existing or search/create under authority>
OBJECTIVE: <design summary>
SCOPE / NON-GOALS: <clear lists>
INTERFACES / SECURITY / MIGRATION: <concrete contracts>
TESTS / ACCEPTANCE: <measurable>
DEPENDENCIES: <order and overlap>
REQUIRED OUTPUT: Decomposition into independently reviewable, documented Worker assignments only when execution authorized.
NEXT ROUTE: Coordinator
```

## D. Coordinator -> Worker

```md
FROM: <Repo> — Coordinator
TO: Issue #<N> | PR #<M or Pending> — <Task>
TYPE: ACTION
WORKER: EXISTING | NEW
REPOSITORY: owner/repo
PRIMARY ISSUE: URL
CURRENT PR: URL | Pending
BASE / FEATURE BRANCH: <confirmed names or exact verification instruction>
REFERENCE SHA / EVIDENCE: <verified>
AUTHORITY: <approved initiative and exact bounded operation>
OBJECTIVE: <one deliverable>
IN SCOPE: <specific>
OUT OF SCOPE: <specific>
PRESERVE: <existing contracts/changes>
DEPENDENCIES: <upstream PRs, file ownership, stops>
GITHUB TRACKING: Update own PR/evidence; Coordinator owns Issue labels, Project and milestones; flag missing/unsupported updates.
DOCS & SECURITY: Read actual AGENTS/CONTRIBUTING/SECURITY/versioning policy; never bypass checks/disclose secrets.
TESTS: <exact expected local/CI/negative/staging tests>
ACCEPTANCE: <definition of done>
PROTECTED: No merges, source promotion, publication, production/NAS or unauthorized policy changes.
REPORT BACK: Exact head SHA, diff summary, tests/security/current CI, docs, metadata exceptions, blockers, PR readiness.
NEXT ROUTE: Coordinator
```

## E. Worker -> Coordinator

```md
FROM: Worker — Issue #N | PR #M — Task
TO: <Repo> — Coordinator
TYPE: ACTION | RECORD
REPOSITORY / BRANCH / HEAD SHA: ...
ISSUE / PR URL / STATE: ...
IMPLEMENTED: ...
TESTS & SECURITY: commands, results, current check URLs / head SHA
DOCUMENTATION / TRACKING: applied vs PENDING — NOT APPLIED
DEPENDENCIES / BLOCKERS: ...
GATES: implementation complete? PR ready? merged? runtime acceptance? release? production?
COORDINATOR DECISION NEEDED: corrections | review | test | approval | closeout
NEXT ROUTE: Coordinator
```

## F. Routine record — deliberate terminal response

```md
FROM: <role>
TYPE: RECORD
REPOSITORY: owner/repo
VERIFIED: <links, SHAs, what changed>
TRACKING: APPLIED | PENDING — NOT APPLIED
DECISION: No new action. No material blocker or approval at this stage.
NEXT ROUTE: NONE
```

Do not produce a `COPY TO` section unless a recipient must genuinely act. The destination should not generate a reciprocal acknowledgement.
