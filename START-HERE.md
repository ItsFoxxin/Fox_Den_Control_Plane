# Start Here — Fox Den Control Plane v1.3 (Any Repository)

This setup works from an empty ChatGPT workspace. It is entirely manual; no GitHub changes are required.

## A. One-time shared Projects

**1. Command Center:** Create ChatGPT Project `OPS | Fox Den Command Center`. Paste `project-instructions/COMMAND-CENTER-PROJECT.md` into Project instructions. Upload the three `governance/*.md` reference files. Create chat `Fox Den — Command Center`, paste `roles/COMMAND-CENTER.md`, then `launch/BOOTSTRAP-COMMAND-CENTER.md`.

**2. Repository Management:** Create ChatGPT Project `OPS | Repository Management`. Paste `project-instructions/REPOSITORY-MANAGEMENT-PROJECT.md` into its settings. Upload `governance/*.md`. This Project will contain separate read-only Manager chats for each repository. It has **no global repository profile**.

## B. Repeat this setup for every repository

**3. Complete repository identity:** Make a copy of `repository-profile/REPOSITORY-PROFILE.template.md` named `REPOSITORY-PROFILE.md`. Fill `[DISPLAY_NAME]` and exact `[OWNER/REPO]`. Verify actual branches/checks with GitHub, or record `UNKNOWN` rather than guessing.

**4. Development Project:** Create/reuse `OPS | [DISPLAY_NAME]`. Paste the universal `project-instructions/REPOSITORY-DEVELOPMENT-PROJECT.md` into its Project instructions. Upload `REPOSITORY-PROFILE.md`, the three `governance/` docs, plus `templates/` when useful. The Project instructions stay the **same for every repository**.

**5. Repo Manager:** Inside the shared `OPS | Repository Management`, create `[DISPLAY_NAME] — Manager`. Paste `roles/REPOSITORY-MANAGER.md`, then `launch/BOOTSTRAP-REPOSITORY-MANAGER.md` with `[DISPLAY_NAME]`, `[OWNER/REPO]`, and current objective filled. Role is read-only by policy.

**6. Architect:** Inside the new repo development Project, create `[DISPLAY_NAME] — Architect`. Paste `roles/ARCHITECT.md`, then the filled `launch/BOOTSTRAP-ARCHITECT.md`. It is a brainstorming chat until explicit owner design/execution approvals.

**7. Coordinator:** Create/reuse `[DISPLAY_NAME] — Coordinator` inside that development Project. Paste `roles/COORDINATOR.md`, then a filled `launch/BOOTSTRAP-COORDINATOR.md`. Its first reply should confirm the repository, not immediately generate work without a task. If an existing Coordinator is already managing PRs, reuse it instead of restarting and preserve ownership.

**8. Workers:** Keep existing task chats. If needed, paste `launch/BOOTSTRAP-EXISTING-WORKER.md` once; don't change original Issue/PR identity. For a NEW task, use `roles/WORKER.md` and **the complete Coordinator-issued assignment**, not just a bootstrap. See `launch/BOOTSTRAP-NEW-WORKER.md`.

## C. Start operating

**9. First audit (optional):** Ask `[DISPLAY_NAME] — Manager` for read-only status with exact current repo; paste an actionable Manager handoff to `[DISPLAY_NAME] — Coordinator` only if needed. The Coordinator can also receive **direct owner requests** before any Manager exists.

**10. Normal execution:** Coordinator produces full copy-ready Worker prompts for authorized READY work. The owner sends each to the correct existing/new Worker. When Worker reports substantive results, copy the whole last response to Coordinator. Coordinator independently verifies and sends a correction/testing prompt, requests owner approval, records completion, or reports a true blocker. No automatic messages back to all upstream roles.

**11. Test:** Run `tests/ACCEPTANCE-TESTS.md` using synthetic/read-only examples. Confirm no duplicate Workers, no Manager requirement, no wrong-repository context bleed and no approval bypass.

## D. What to do with all the files

- `governance/*.md`: shared reference docs in every operational ChatGPT Project.
- `project-instructions/*.md`: paste one appropriate file in each Project's settings.
- `roles/*.md`: paste the matching permanent role prompt into each role chat.
- `launch/*.md`: initial/one-time bootstrap **for that role**; fill repository identity fields first.
- `repository-profile/`: create one completed copy per repository development Project; don't upload unresolved template as configuration.
- `templates/*.md`: reusable handoff and GitHub tracking references, especially for coordinators/workers.
- `repository-baselines/AGENTS.template.md`: uncommitted proposal for adding repo-local agent guidance after reviewing existing docs.
- `examples/fox-den-media/`: optional example/reconciliation, **not universal governance**.
- `tests/`: manual behavior acceptance tests. `README`, `CHANGELOG`, `SETUP-CHECKLIST`: kit maintenance.

## E. Limits

Separate ChatGPT chats cannot automatically relay messages. Prompts cannot enforce actual GitHub permission boundaries; use GitHub protections and scoped credentials. These files do not create Projects, change GitHub, schedule automations, or authorize merges/releases/deployments.
