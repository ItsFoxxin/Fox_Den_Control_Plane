# Fox Den Control Plane

**Public governance and prompt library · v1.3 proposal**

Versioned, reusable instructions for human-supervised development across multiple GitHub repositories. The Control Plane provides the **rules and handoff contracts**; FoxForge can later implement an execution engine without owning or overriding those rules.

## Operating model

- **Owner / Command Center**: priorities, cross-repository oversight and protected decisions.
- **Repository Manager**: independent, read-only audit; only actionable handoffs.
- **Architect**: exploratory design with the owner; sends an approved specification to the Coordinator.
- **Coordinator**: scopes Issues, assigns focused Workers, handles GitHub metadata and authorized integration.
- **Worker**: one narrowly bounded Issue/PR, implementation, tests, documentation, and evidence.

Use the shortest route: Command Center → Coordinator for known authorized work; → Manager for investigation; → Architect for design. Manual full-response copy/paste is the initial relay mechanism. Chats do not independently message one another. **No acknowledgment loops:** only route when a real action, owner decision, or material escalation is necessary.

## Get started

1. Review [START-HERE.md](START-HERE.md) and [governance](governance/).
2. Configure project-level instructions from `project-instructions/`.
3. Copy the relevant role prompt from `roles/` into each permanent chat.
4. Fill `repository-profile/REPOSITORY-PROFILE.template.md` for each repository; keep sensitive completed profiles private.
5. Use `launch/` for initial bootstraps, `templates/` for handoffs and `tests/` for acceptance tests.

## Authority and safety

GitHub is authoritative for Issues, PRs, checks, dependencies and releases. A prompt does not enforce credentials or permissions. The owner separately authorizes merges, source promotion, package/release publishing, protected-environment changes and production deployments. Existing repository policies and security controls remain in effect.

**This repository is public.** Do not commit secrets, real infrastructure topology, private operational profiles, vulnerable-service details, unredacted security findings, personal data, or confidential Worker transcripts. Read [Public Data Policy](docs/PUBLIC-DATA-POLICY.md). Examples must use synthetic data.

## Status

This initial governance import is a proposal for review, not approval of agent autonomy, changed repository protections, or a deployment. No license has been selected by the owner.
