# Fox Den — Handoff Protocol v1.2

**Transport:** Copy the sending chat's complete final response into the addressed destination chat. Recipients should infer identity and purpose from the envelope, not require the full previous chat history. No agent-to-agent messaging is assumed.

## Four message classes

- **ACTION:** The receiver must do a defined task; provide an entire paste-ready prompt.
- **DECISION:** Owner must approve or choose; stop without invoking protected actions.
- **ESCALATION:** A genuine design/security/dependency blocker requires one specialist; provide a self-contained handoff.
- **RECORD:** Information updated or verified; **no onward forwarding**. Use `NEXT ROUTE: NONE`.

**Prefer one hop:** Command Center -> Coordinator for known work; Command Center -> Manager for unknown status; Command Center/owner -> Architect for major design. Coordinator -> Worker for implementation. Worker -> Coordinator with completion evidence. Coordinator -> Architect only for unresolved design issue. Manager -> Command Center only on requested or meaningful portfolio updates.

## Mandatory envelope for a routed prompt

```text
FROM: <role and repository>
TO: <single destination role / exact chat title>
TYPE: ACTION | DECISION | ESCALATION | RECORD
REPOSITORY: owner/name
ISSUE/PR: #N / #M or Pending
AUTHORITY: Read-only | approved initiative | owner action required
EVIDENCE: current SHA, PR/Issue links, verified state and freshness
OBJECTIVE: exact recipient action
BOUNDARIES: unchanged rules, prohibited scope, dependencies
REQUIRED OUTPUT: full completion evidence / decision / handoff
NEXT ROUTE: <destination or NONE>
```

New Worker prompts also require exact branch, base, acceptance criteria, metadata/docs/tests/security/approval constraints. Existing PR corrections must go to the existing chat, not a new one. Use one complete standalone prompt per ready Worker; do not force users to manually assemble text.

## Duplicate and loop controls

If the same Issue/PR, same latest commit and same requested action have already been processed, return `RECORD — NO CHANGE` unless there is new GitHub evidence or a new owner decision. Do not generate a return-to-sender prompt as acknowledgement. Coordinator can keep work cycling between itself and a Worker until the original task is done, without periodically involving Architect/Manager.

## On unavailable features

If direct Project field/milestone manipulation is unsupported by connected tooling, declare `PENDING — NOT APPLIED`; supply the exact manual or `gh` step to the owner. Never report simulated metadata as completed.

## Completion and escalation

- A Worker report should contain Issue, PR, branch, commit, tests, current check status, docs, security result, remaining risk, merge readiness and requested Coordinator decision.
- Coordinator checks live evidence and chooses: correct same Worker, new independent Worker, test, wait, request owner approval, or closeout.
- A Coordinator closeout does **not** automatically generate Manager, Architect and Command Center prompts. Summarize major milestones when needed; ordinary progress is a GitHub record.
