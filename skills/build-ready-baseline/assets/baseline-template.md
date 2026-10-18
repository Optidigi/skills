# [Product] — Build Brief / Specification

**Revision/date:** [value]  
**Owner:** [person/role or PENDING]  
**Evidence inspected:** [documents, source refs, relevant source dates; access limits]  
**Baseline status:** [READY FOR LOCAL PREFLIGHT / PRODUCT DECISION PENDING]  
**Next authorized phase:** Phase 1 — Preflight & Preparation **only**, subject to actual setup permissions.

> This is the initial agent's product and preparation contract, **not** a report that the local environment has been verified. Replace placeholders. Use this as a coverage guide; keep detail proportional, but preserve the handoff and post-preflight approval gate. No proposal or requested permission is an approved grant.

## 0. Handoff snapshot

- **Intended outcome:** [one-paragraph product and user value]
- **First connected user journey:** [entry → meaningful action → real processing/durable state → result accessible to intended user]
- **Most important unknowns / decisions:** [risks, decision owners, what they block]
- **Next action:** [local owner starts preflight, prepares report, STOPS for approval]

## 1. Product contract and boundaries

- **Users/jobs and problem:** [who, why, critical jobs]
- **Goals/outcomes:** [observable success and relevant metrics]
- **Supported platforms/customer conditions:** [browser/device/regions/roles when material]
- **Scope/non-goals:** [included features and explicit exclusions]
- **UX/UI direction:** [flows, existing references, accessibility and interaction expectations]
- **Domain rules:** [data entities, lifecycle, money/ownership/privacy/business constraints]

## 2. Journeys, requirements and acceptance

Use stable IDs on material requirements and their acceptance conditions. Keep requirements traceable to delivery outcomes, not just descriptive prose. Include success, failure/recovery and relevant edge behavior.

| Requirement | Journey / observable obligation | Acceptance evidence (`AC-...`) | Increment (`M-...`) | Source/status |
|---|---|---|---|---|
| REQ-001 | [actor, trigger, system response and business/data rule] | AC-001: [given/when/then; pass/fail, error/recovery condition] | M-01 | [user requirement / existing contract / PENDING] |

**Important quality and operating constraints:** [performance, security, privacy, resilience, accessibility, auditability and lifecycle targets where relevant; measurable threshold or pending decision]

## 3. Architecture intent and interfaces

- **Current system / constraints:** [observed code/ref or new-project assumption; do not claim unseen source]
- **Proposed architecture/stack:** [components and rationale; label PROPOSED unless decided]
- **Boundaries/data flow:** [critical actors, services, persistence, jobs and external interfaces]
- **Integration contracts:** [auth, billing, storage, APIs, platforms and limits that matter]
- **Design trade-offs:** [what was chosen/agreed vs what the local owner must validate]
- **Diagrams/annexes:** [links only when useful; primary brief remains usable alone]

## 4. Evidence, decisions and unresolved assumptions

| ID/item | Kind: REQUIREMENT / AGREED DECISION / PROPOSAL / HYPOTHESIS | Rationale, source and date | Decision owner / validation needed |
|---|---|---|---|
| DEC-001 | PROPOSAL | [why and current support] | [owner to adopt; local validation] |

| Risk/claim | Evidence and applicable version/context | Cheapest meaningful proof, pass/fail | Phase and affected work |
|---|---|---|---|
| [load-bearing unknown] | [opened primary source / observed behavior / unavailable] | [allowed environment, required access, effect if false] | [non-product setup probe during Phase 1 OR product feasibility test in Phase 2] |

A documentation claim is not proof of working project integration. Any code/scaffold necessary for a product proof belongs to Phase 2 after approval. Mark unavailable evidence honestly.

## 5. Outcome-based implementation roadmap (NOT YET AUTHORIZED)

| Increment | Working outcome + requirements | Dependencies/critical proofs | Acceptance/qualification |
|---|---|---|---|
| M-01 — Connected journey | [end-to-end user value; REQ/AC IDs] | [preflight capability, access, hypotheses] | [tests, runtime observation, provider checks, limits] |
| M-02 — Expansion | [next needed features; REQ/AC IDs] | [preceding outcomes] | [tests and integrated evidence] |
| M-Release | [supported product scope] | [security/commercial/native/release requirements] | [release criteria and actual rollout authority] |

Implementation is **not** authorized by the existence of this roadmap. The local owner may execute it only after reviewing and completing preflight and receiving explicit user approval to proceed.

## 6. Local environment capability contract

Specify **what must work**, not an obligatory tool bundle. Candidate tools/skills/MCPs may be suggested with a rationale, but the local agent chooses and verifies the actual setup. Mark capabilities `REQUIRED NOW` vs `LATER` so preflight does not become unlimited.

| Capability | Why / needed by | Objective preflight verification | Candidate approaches (non-binding) | Access/limits |
|---|---|---|---|---|
| CAP-01 — Repository & host instructions | [M-01] | [read current source/ref/rules; verify permitted change mechanism] | [existing host-native tools] | [known/pending] |
| CAP-02 — Runtime/build/test | [M-01] | [existing commands run with recorded outcome/version] | [repo package manager/native runner] | [known/pending] |
| CAP-03 — UI/runtime inspection | [if applicable] | [inspect a safe running target or clearly mark not runnable yet] | [host browser, Playwright, browser MCP] | [known/pending] |
| CAP-04 — Provider sandbox | [if applicable] | [authorized harmless connection smoke test, or specific unverified blocker] | [CLI/SDK/API/MCP chosen locally] | [known/pending] |

**Local tooling ownership:** [the local implementation agent researches current options, reuses existing setup, selects tools/skills/MCPs/permissions within grants, configures them, and verifies effective versions/operations. No first-agent suggestion binds that selection.]

## 7. Authority and mandatory Phase 1 stop

**Phase 1 — Preflight & Preparation only**

- **Allowed within existing grants:** [repo/context inspection, tooling research, minimal host/config changes, non-product tests, existing build/test, safe sandbox/tooling probes]
- **Not allowed before post-report approval:** [implementing features, substantial application scaffolding, migrations, product milestones, development deployment of application changes, production/external effects outside existing authorization]
- **Confirmed resources/permissions with source:** [scope, environment, worktree/branch, ops; or PENDING]
- **Pending access or decisions:** [who supplies, private credential entry route, which test/work is blocked]
- **Spending/security/production restrictions:** [limits; if not granted, say pending—not implied]
- **Required Phase 1 output:** `PREFLIGHT_REPORT.md` [or repo convention] + chat summary (full report in chat if file write is not permitted), with setup changes, rationale, capability-by-capability `PASS/FAIL/NOT TESTED/NOT APPLICABLE` evidence, missing user steps, risks, readiness and proposed M-01.
- **Readiness labels:** `READY — AWAITING APPROVAL` if critical preparation is qualified; `BLOCKED — USER ACTION REQUIRED` if missing required inputs/permissions/checks prevent readiness. List unverified nonblocking items explicitly.
- **Mandatory gate:** after the report, **STOP and request explicit user approval to start Phase 2**. Stop when ready *or* blocked. Fixing a blocker or granting an individual setup permission is not implementation approval; update/revalidate the report and stop again.
- **Phase 2 (only after approval):** [scope/outcome that may then be autonomously implemented, test/review/integration/verification expectations, any further consequential decisions reserved for owner].

## 8. Local handoff

- **Brief readiness:** [READY FOR LOCAL PREFLIGHT / PRODUCT DECISION PENDING; never claim environment verified]
- **Open product decisions:** [owner, options/recommendation, impact]
- **Missing local inputs:** [provider, access, exact work blocked]
- **Standalone startup prompt:** [`LOCAL_AGENT_STARTUP_PROMPT.md` or attached prompt]

### Copyable local startup prompt

[Insert the **verbatim**, project-filled contents of `LOCAL_AGENT_STARTUP_PROMPT.md` generated from `assets/local-startup-prompt-template.md`. This keeps one-file handoff possible while also providing the prompt separately. Do not replace the prompt with a one-line pointer in the only delivered copy of the brief.]
