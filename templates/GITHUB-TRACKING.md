# GitHub assignment and metadata checklist v1.2

## Before Worker dispatch (Coordinator responsibility)

- [ ] Search for duplicate existing Issue and PR; reuse historical work/Worker when continuation.
- [ ] Primary Issue exists with objective, scope and acceptance criteria, or justified read-only `EXP` exception.
- [ ] Appropriate *existing* type/component labels; verify taxonomy, do not invent new labels without decision.
- [ ] Applicable milestone (when repository uses one); don't create a milestone merely to satisfy a checklist.
- [ ] GitHub Project item/status confirmed; preserve native status names; avoid fake `Done` when acceptance incomplete.
- [ ] Parent/sub-issue and blocking dependencies recorded where supported; separate hard vs file-overlap vs verification dependency.
- [ ] Branch/base & active Worker ownership recorded in Issue or coordinator-maintained stable note.
- [ ] Approved initiative and protected action boundaries unambiguous.

## Worker PR requirements

- [ ] Target correct integration branch; feature branch isolated.
- [ ] Linked Issue with correct semantics (`Fixes #N` only if closing Issue now is intended).
- [ ] PR title/body completed according to existing template, including security/privacy assessment.
- [ ] Tests, failure cases, local and latest-head CI results and relevant SHA documented.
- [ ] Docs/changelog/version updates obey repository rules.
- [ ] No secrets/sensitive vulnerability details in public records.
- [ ] Known missing metadata reported as `PENDING — NOT APPLIED`.

## Coordinator closeout checks

- [ ] Inspect actual diff, changed files, current PR head and target.
- [ ] Verify required checks/security results on latest relevant head; resolve unresolved review discussions.
- [ ] Check merge order and stacked PR integration; don't reuse stale CI after base/prerequisite updates.
- [ ] Request exact owner merge approval (separate for `dev`/`main` and publication/deployment).
- [ ] Reverify before an approved merge; confirm resulting SHA and update Issue/Project as appropriate.
- [ ] Preserve separate gates for merged, staging/NAS accepted, release published, production GO/accepted.

## Tools caveat

Current ChatGPT/GitHub connectors may not provide GitHub Projects or milestone mutations. Never claim a field was updated without supported tool confirmation. Provide manual GitHub UI or `gh` instructions and mark `PENDING — NOT APPLIED` instead. GitHub Project built-in automation can close/mark a PR item Done when merged; that does not certify associated Issue runtime acceptance.
