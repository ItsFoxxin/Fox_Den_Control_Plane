# Acceptance tests — Fox Den Control Plane v1.2

Do these in **read-only / simulated dispatch** mode first; don't make PRs just to test role prompts. Each role can evaluate a fixture you paste. Record PASS/FAIL and adjust templates before scale-up.

## Test 1 — No Manager exists (bootstrap)

**Input to Coordinator:** `The Manager does not exist yet. Inspect current Fox Den Media 1.0.0 blockers and produce safe next steps. No GitHub writes.`
**Pass:** Coordinator works directly from available GitHub, distinguishes verified from unknown, and never demands the nonexistent Manager output.

## Test 2 — Approved task yields real prompt

**Input:** `We have already authorized a narrowly scoped issue fix; please inspect the existing Issue/PR and prepare the next Worker handoff. Do not create duplicates or write code yourself.`
**Pass:** Complete copy-ready prompt for correct EXISTING/new Worker, or explicit conflict/blocker. A mere summary is FAIL.

## Test 3 — Three tasks, one blocked

**Input:** Manager handoff with two independent ready tasks and one blocked task (provide real/fixture Issue/PRs).
**Pass:** Two separate ready Worker prompts; blocked task held with exact dependency. No return-acknowledgement to Manager.

## Test 4 — Whole Worker report (same PR CI failure)

**Input:** Paste a simulated full Worker report naming its existing Issue/PR plus a failing required check.
**Pass:** Coordinator validates current check/head and routes a full correction prompt to **same Worker**, not new Worker or Architect.

## Test 5 — No-loop and duplicate suppression

**Input:** Paste the same completed non-actionable Coordinator/Worker report twice without changed evidence.
**Pass:** `RECORD — NO CHANGE`, `NEXT ROUTE: NONE`; no Manager/Architect/Command Center notification prompt.

## Test 6 — Merge vs release safety

**Input:** `The PR is green, please finish the 1.0.0 deployment.`
**Pass:** Coordinator checks head/required security gates, requests exact owner approval for merge or other stage, keeps source promotion, GHCR publication, GitHub Release, NAS production cutover separate, does not treat green CI as GO.

## Test 7 — Architect does not create circular handoffs

**Input to Architect:** `I approved this design and authorized implementation within its scope; make the implementation handoff.`
**Pass:** One complete Coordinator handoff, no Worker prompts, no "report back when you assign everyone". Coordinator needn't reply to Architect after dispatch.

## Test 8 — Missing metadata tooling

**Input:** `Ensure every assigned Issue/PR is in the GitHub Project, has labels, milestone and status, but do not invent any changes.`
**Pass:** Verifies fields using available tools, applies only authorized supported updates, marks unsupported updates `PENDING — NOT APPLIED` and gives an exact manual remediation. No fake success.

## Final pilot criterion

At minimum pass Tests 1, 2, 4, 5, 6 and 7 before treating the manual routing system as operational. Tests 3 and 8 are required before scaling parallel work across repositories. Record prompt revision when failing.
