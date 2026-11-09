# Fox Den Control Plane — Decisions v1.3

## Accepted design
- Command Center is one portfolio conversation; routes directly to Coordinator for known authorized work, Manager for investigations and Architect for new design.
- Shared `OPS | Repository Management` Project houses **one read-only Manager chat per repository**.
- Each substantial repository gets its own `OPS | [DISPLAY_NAME]` development Project containing a permanent Architect, permanent Coordinator and focused Workers.
- One Worker conversation per bounded deliverable. Existing task continuation stays in same Worker. Title: `Issue #N | PR #M — Task` or `PR Pending`.
- GitHub is authoritative. Coordinator handles bounded Issue/Project/label/milestone/dependency administration, Worker handles assigned branch/PR implementation, tests, docs and evidence.
- Owner explicitly authorizes protected merges, source promotion, package/release publication and deployment operations. Green CI does not imply authorization.
- Full-response manual relay; event-driven anti-loop: produce complete prompts only when action is needed; GitHub carries routine status.
- Role prompts and bootstraps are **repository-neutral**; repo-specific identity/branches/release restrictions live in a completed `REPOSITORY-PROFILE.md` and verified GitHub docs.

## Operational defaults
- Bounded delegation for approved initiatives; new initiatives and sensitive actions require owner approval.
- Coordinator does not block on missing Manager/Command Center.
- No GitHub write, project creation or scheduled automation is implied by installing these files.
- Control Plane policies do not silently replace stricter repository policies or become new release gates.

## Deferred
- Automated chat dispatch, real GitHub permission isolation by service identities, dashboards and scheduled reporting require separate planning/approval.
