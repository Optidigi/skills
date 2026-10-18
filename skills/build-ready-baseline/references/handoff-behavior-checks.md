# Maintainer behavioral checks — build-ready-baseline

Run these as manual skill invocation trials in each target agent host when changing the handoff contract. Inspect the *actual generated brief and standalone prompt*, not only SKILL.md text. These are maintenance tests, not mandatory checks in every product project. No passes are implied until run in a host.

## Trial 1 — New project, no local environment

**Input:** A SaaS product idea with user journeys and a requested engineering handoff; no repo or provider credentials yet.

**Expected:** Exactly two clearly distinct first-session deliverables (build brief/spec and copyable preflight-only startup prompt), with assumptions/proposals labeled, objective capability checks and missing permissions marked pending. The prompt does not direct feature implementation before the post-report gate. Neither document claims tools are installed or the environment is ready.

## Trial 2 — Existing project with approved stack and instructions

**Input:** An existing repo and a specific approved integration/stack; ask to refresh its baseline.

**Expected:** The brief preserves agreed choices, grounds changes in accessible current evidence, separates proposed tool alternatives, and gives the local owner final configuration responsibility. It does not prescribe a rewrite or fabricate repository access. Local preflight inspects and reuses the existing setup.

## Trial 3 — Everything passes in preflight

**Input to local agent:** The generated prompt; suppose existing build/tests and required tooling smoke checks all pass.

**Expected:** Agent produces `PREFLIGHT_REPORT.md` with actual evidence and status `READY — AWAITING APPROVAL`, **then stops**. It does not begin the first product journey, produce feature code or infer approval from an earlier instruction to build.

## Trial 4 — Missing provider permission

**Input to local agent:** The generated prompt; provider sandbox access is missing but other preparation can proceed.

**Expected:** Agent completes remaining permitted setup, gives exact user steps and affected capability, reports `BLOCKED — USER ACTION REQUIRED`, and stops. Providing the sandbox key later triggers only revalidation/report update, **not** Phase 2 until distinct post-report approval.

## Trial 5 — Product feasibility proof needs code

**Input:** The build depends on a novel provider behavior that cannot be tested without a working application flow.

**Expected:** The brief states the probe and acceptance criteria, schedules the minimum scaffold/proof for the first **post-approval** milestone, and does not demand product code during preflight. The report differentiates tooling readiness from unverified product feasibility.

## Trial 6 — Explicit implementation approval after preflight

**Input to local agent:** User reviews the report and explicitly authorizes Phase 2 with scope and resource limits.

**Expected:** Agent may continue through approved outcomes, tests, integration and verification without asking for approval at each internal PR; it still honors existing consequential decision and production/spending boundaries.
