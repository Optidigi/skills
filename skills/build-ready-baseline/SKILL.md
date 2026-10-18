---
name: build-ready-baseline
description: >-
  Create or explicitly revise a SaaS build brief/specification and a separate
  preflight-only startup prompt for a local implementation agent. Use for product
  discovery, initial architecture, feasibility planning, or a requested planning
  refresh. Do not use for ordinary coding, CI repair, routine delivery, reviewing
  this skill, unrelated business plans, or executing the plan.
---

# Build-ready baseline

Create **two first-session deliverables**: (1) an evidence-based, implementation-ready **Build Brief / Specification** (`BUILD_BASELINE.md`), and (2) a **Local Implementation Agent Startup Prompt** (`LOCAL_AGENT_STARTUP_PROMPT.md`). The brief defines the product and the capabilities an engineer must establish; the prompt starts the local agent in **preflight and environment preparation only**. The local agent must report readiness and **stop for explicit user approval after preflight, even if everything passes**. Implementation is a separate, later phase.

This skill plans and hands off; it does not configure the local agent, grant permissions, execute product work, or authorize deployment. Preserve existing project contracts and user decisions. Distinguish agreed facts and choices from proposals and untested assumptions.

## 1. Establish the starting point

Read supplied requirements, examples, designs and authoritative project documents. For existing projects inspect current source/refs when accessible, identify conflicting or superseded guidance, and avoid silently replacing contracts or prescribing a rewrite. Record what was actually read and the access limits: a shared URL or named connector does not prove its contents or operations were inspected.

Ask only a small set of questions whose answers materially change the offering, scope, feasibility, authority or acceptance. Continue independent planning while answers are pending; mark unresolved choices with their owner rather than inventing consent. Do not infer that a request to prepare a brief also authorizes tool installation, credentials, paid resources or implementation.

## 2. Specify an observable product contract

Define users/jobs, supported conditions, goals and exclusions, critical journeys, features, business/data rules, UI and accessibility expectations, and relevant privacy, security, reliability, lifecycle or commercial obligations. Include representative successes, failures, recovery and edge cases. Write requirements so a local engineer can determine what would count as passing acceptance without relying on the first conversation.

For material requirements use stable `REQ-...` identifiers and observable `AC-...` acceptance conditions; map them to journeys and delivery increments (`M-...`). Keep traceability lightweight for small projects, but do not lose features or make unverifiable promises. Explicitly distinguish:

- **Requirement** — an obligation to satisfy, with its authoritative source.
- **Agreed decision** — an adopted choice, with rationale and change authority.
- **Proposal** — a recommended choice not yet adopted; mark whose decision is needed.
- **Hypothesis** — an unverified claim, its possible impact and necessary proof.

## 3. State architectural intent without pretending the environment is known

Describe system context, responsibility boundaries, key integrations, significant interfaces and data flows. Recommend the simplest plausible stack and design consistent with requirements and existing code; prefer compatible, supported defaults unless there is a reason not to. Treat the stack as a **proposal** unless already decided. Include only architecture views/diagrams that reduce ambiguity. Leave ordinary implementation tactics and final tool/version selection to the local engineering owner.

Research load-bearing platform/integration claims against current primary sources when possible, opening the relevant source rather than trusting a snippet. Record platform/version/distribution context, source/date, restrictions and the cheapest meaningful test. Distinguish external documentation, direct observation and inference. An unexecuted proof is **pending**, not passed. For each high-impact unknown specify the allowed environment, access, success/failure criterion, consequence and owner of the probe.

## 4. Plan connected outcomes, not tasks masquerading as value

Name the smallest end-to-end journey that delivers a real result to its intended user, including necessary authentication, persistence, asynchronous processing, provider integration and downstream access. An isolated page or mocked API does not establish a product-dependent journey. Order subsequent increments by dependency and user value; retain all required later scope. For each increment state working outcome, requirements covered, prerequisites, acceptance evidence and remaining native/provider/release qualification. Distinguish local completion from real-provider or release readiness. Do not commit to dependent features while feasibility assumptions that could invalidate them remain unproved.

**Important phase boundary:** the end-to-end product journey and any application scaffold needed for it belong to **implementation after approval**. Preflight may inspect an existing scaffold, run existing builds/tests, configure authorized infrastructure and execute narrow, safe *non-product* tooling probes. If proving a load-bearing assumption requires new product code or a substantial scaffold, record that proof as the first *post-approval* implementation task. Never redefine preflight so broadly that it silently becomes development.

## 5. Specify capabilities; delegate tooling ownership locally

Define the capabilities required to prepare and execute the first milestone, with `CAP-...` identifiers where useful. Each capability includes its purpose, criticality/timing, relevant access limits and an **objective verification check**. Typical categories, only when applicable: repository and instructions, runtimes/build/tests/CI, local application/browser interaction, logging and diagnostics, sandbox providers, private credential entry, safe resource isolation, and independent review.

The initial agent **may suggest** tools, skills, MCP servers, CLIs, SDKs or services with relevant rationale. Suggestions are not an install list or a claim that a tool is available. **The local implementation agent owns** inspecting existing tooling; researching current supported alternatives; selecting the least-complex sufficient approach; installing/configuring host tools, skills, MCPs, instructions and permissible permissions; and verifying what actually loads and operates. CLI/API/native host features may be preferable to MCPs. Inspect skill provenance, trigger, duplication and instruction conflicts; prefer compatible changes with rollback over unnecessary upgrades. Identify required secrets by purpose and private entry method, never their values.

## 6. Write an explicit two-phase authority contract

The **first local session is Phase 1 — Preflight & Preparation**, not an implementation kickoff. Give the local agent these instructions explicitly:

1. Inspect the actual repository, worktree, current implementation, project rules and host/runtime constraints; reconcile the brief with current evidence, reporting material conflicts instead of silently overruling agreed requirements.
2. Map the brief's capability requirements to existing and candidate tools. Research and select appropriate tools/skills/MCPs and document trade-offs, provenance/compatibility and rationale.
3. **Within already granted authority**, configure or repair necessary development tooling, host instructions, skill connections, permissions and safe test/sandbox access. Reuse existing infrastructure; do not create duplicate resources unnecessarily.
4. Run bounded environment validation and tooling smoke tests. Distinguish `PASS`, `FAIL`, `NOT TESTED` and `NOT APPLICABLE`, providing commands or reproducible observations, actual versions/configuration where visible, and unverified limits. Do not conflate an installed tool with a tested capability.
5. Produce `PREFLIGHT_REPORT.md` (or the repository's equivalent) plus a concise chat summary; if file writes are not permitted, provide the full report in chat and flag persistence as pending. Include repository/ref and brief revision, setup changes, capability-by-capability evidence, missing inputs, exact user actions, blocked work, risks, and the proposed first implementation milestone. Report status as **READY — AWAITING APPROVAL** or **BLOCKED — USER ACTION REQUIRED**, qualifying mixed/untested capabilities.
6. **STOP. Do not implement product features, create a substantial product scaffold, run product migrations, expand into delivery milestones or deploy application changes before explicit user approval given *after reviewing the preflight report*.** This applies even when all checks pass, when the user originally said “build it,” or when no blockers remain.

Preflight may use authorized configuration changes, existing build/tests and ephemeral non-product connection probes; it must not create production effects, incur costs, weaken security, install dependencies of dubious provenance or request broader privileges without authorization. An existing authorization within its scope remains usable; the mandatory **post-report implementation approval** is a separate gate, not repeated authorization for every safe setup action. Providing a credential, answering a blocker question or approving a single setup operation **does not** itself approve Phase 2. If a blocker is resolved, revalidate and update the report, then still stop.

After the user expressly approves Phase 2 against the reviewed brief/report and any limits, the local engineering owner may implement, test, review, integrate and verify the **approved outcome** without stopping at every task or PR. Preserve existing milestones and consequential owner decisions, ask before out-of-scope spending/external/destructive/production effects, and return for genuine blockers or outcome acceptance. Require meaningful behavior/boundary tests, runtime/browser/provider checks as relevant, proportionate independent review where truly available, integrated-build verification and project documentation updates. Do not call sequential self-review independent. Host permissions and runtime controls—not the prompt—govern actual operations.

## 7. Produce the brief and the copyable prompt

Use [assets/baseline-template.md](assets/baseline-template.md) for the build brief and [assets/local-startup-prompt-template.md](assets/local-startup-prompt-template.md) for the standalone prompt. Replace placeholders with observed facts or explicitly `PENDING` information. The brief must contain the project-specific preflight contract and point to the prompt; **also include the exact copyable prompt at the end of the brief when practical** so a single document can be handed over, but supply it separately as well. Keep the two copies consistent.

Default outputs:

- **`BUILD_BASELINE.md`** — the authoritative, portable build brief/specification: product, traceable acceptance, architecture intent, evidence/risks, connected roadmap, capability verification matrix, preflight scope, limits and approval gate.
- **`LOCAL_AGENT_STARTUP_PROMPT.md`** — a short, self-contained startup prompt that locates the brief, grants *only* known preflight permissions, instructs environment preparation/verification, requires `PREFLIGHT_REPORT.md`, and ends at the mandatory stop.

Use project naming conventions if appropriate; if not allowed to write files, return both clearly labeled in chat. Save only to authorized destinations. Do not create the preflight report or claim it was executed: that is the local agent's work.

## 8. Check first-session quality

Before handoff verify: every required journey/feature has measurable acceptance; material requirements link to milestones; architecture proposals are not mislabeled as decisions; important risks have evidence or assigned post-approval probes; capabilities have objective checks; the first connected journey finishes at user value; setup authority and pending permissions are distinct; the standalone prompt identifies the brief; and **both the brief and prompt make the Phase 1 report → mandatory stop → explicit post-report approval → Phase 2 sequence unambiguous**.

Report baseline status as **READY FOR LOCAL PREFLIGHT** or **PRODUCT DECISION PENDING**, and specify important unresolved decisions and access. This status does **not** mean local readiness, user approval, provider qualification or launch readiness. Keep documentation proportional: combine or omit inapplicable explanatory subsections, never omit the two deliverables or the approval contract. For maintainers, use [references/handoff-behavior-checks.md](references/handoff-behavior-checks.md) for behavioral regression scenarios; these are not extra project gates.
